---
title: SQL Server 次要副本到主要副本读/写连接重定向 - Always On 可用性组 | Microsoft Docs
ms.custom: ''
ms.date: 08/09/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology:
- dbe-high-availability
ms.topic: article
helpviewer_keywords:
- connection access to availability replicas
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], readable secondary replicas
- active secondary replicas [SQL Server], read-only access to
- readable secondary replicas
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: ''
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: On Demand
monikerRange: '>=sql-server-ver15||>=sql-server-linux-ver15||=sqlallproducts-allversions'
ms.openlocfilehash: 2ed23533850897e34e3411ac041585a351e2b287
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47840895"
---
# <a name="secondary-to-primary-replica-readwrite-connection-redirection-always-on-availability-groups"></a>次要副本到主要副本读/写连接重定向（Always On 可用性组）
[!INCLUDE[appliesto](../../../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]

[!INCLUDE[sssqlv15-md](../../../includes/sssqlv15-md.md)] CTP 2.0 引入了 Always On 可用性组的次要副本到主要副本读/写连接重定向。 读/写连接重定向适用于任何操作系统平台。 它允许客户端应用程序连接定向到主要副本，而不考虑在连接字符串中指定的目标服务器。 

例如，连接字符串可以针对次要副本。 根据可用性组 (AG) 副本的配置和连接字符串中的设置，连接可以自动重定向到主要副本。 

## <a name="use-cases"></a>用例

在 [!INCLUDE[sssqlv15-md](../../../includes/sssqlv15-md.md)] 之前，AG 侦听器和相应的群集资源将用户流量重定向到主要副本，以确保在故障转移后重新连接。 [!INCLUDE[sssqlv15-md](../../../includes/sssqlv15-md.md)] 继续支持 AG 侦听器功能，并为不能包含侦听器的方案添加副本连接重定向。 例如：

* SQL Server 可用性组集成的群集技术不提供类似于侦听器的功能 
* 多子网配置，如在云中或具有 Pacemaker 的多子网浮动 IP，其中配置变得复杂，容易出错，并且由于涉及多个组件而难以排除故障
* 读取扩展或灾难恢复和群集类型是 `NONE`，因为没有简单的机制来确保在手动故障转移时进行透明重新连接

## <a name="requirement"></a>要求

为使次要副本重定向读/写连接请求：
* 次要副本必须处于联机状态。 
* 副本规范 `PRIMARY_ROLE` 必须包含 `READ_WRITE_ROUTING_URL`。
* 连接字符串必须将 `ApplicationIntent` 定义为 `ReadWrite`，这是默认设置。

## <a name="set-readwriteroutingurl-option"></a>设置 READ_WRITE_ROUTING_URL 选项

若要配置读/写连接重定向，请在创建 AG 时为主要副本设置 `READ_WRITE_ROUTING_URL`。 

在 [!INCLUDE[sssqlv15-md](../../../includes/sssqlv15-md.md)] 中，`READ_WRITE_ROUTING_URL` 已添加到 `<add_replica_option>` 规范。 请参阅下列主题： 

* [CREATE AVAILABILITY GROUP](../../../t-sql\statements\create-availability-group-transact-sql.md)
* [ALTER AVAILABILITY GROUP](../../../t-sql\statements\alter-availability-group-transact-sql.md)


### <a name="primaryrolereadwriteroutingurl-not-set-default"></a>PRIMARY_ROLE(READ_WRITE_ROUTING_URL) 未设置（默认值） 

默认情况下，未对副本设置读/写副本连接重定向。 次要副本处理连接请求的方式取决于是否将次要副本设置为允许连接以及连接字符串中的 `ApplicationIntent` 设置。 下表显示次要副本如何处理基于 `SECONDARY_ROLE (ALLOW CONNECTIONS = )` 和 `ApplicationIntent` 的连接。

||`SECONDARY_ROLE (ALLOW CONNECTIONS = NO)`|`SECONDARY_ROLE (ALLOW CONNECTIONS = READ_ONLY)`|`SECONDARY_ROLE (ALLOW CONNECTIONS = ALL)`|
|-----|-----|-----|-----|
|`ApplicationIntent=ReadWrite`<br/> ，则“默认”|连接失败|连接失败|连接成功<br/>读取成功<br/>写入失败|
|`ApplicationIntent=ReadOnly`|连接失败|连接成功|连接成功

上表显示默认行为，与 [!INCLUDE[sssqlv15-md](../../../includes/sssqlv15-md.md)] 之前的 SQL Server 版本相同。 

### <a name="primaryrolereadwriteroutingurl-set"></a>PRIMARY_ROLE(READ_WRITE_ROUTING_URL) 集 

设置读/写连接重定向后，副本处理连接请求的行为方式有所不同。 连接行为仍然取决于 `SECONDARY_ROLE (ALLOW CONNECTIONS = )` 和 `ApplicationIntent` 设置。 下表显示包含 `READ_WRITE_ROUTING` 集的次要副本如何处理基于 `SECONDARY_ROLE (ALLOW CONNECTIONS = )` 和 `ApplicationIntent` 的连接。

||`SECONDARY_ROLE (ALLOW CONNECTIONS = NO)`|`SECONDARY_ROLE (ALLOW CONNECTIONS = READ_ONLY)`|`SECONDARY_ROLE (ALLOW CONNECTIONS = ALL)`|
|-----|-----|-----|-----|
|`ApplicationIntent=ReadWrite`<br/>，则“默认”|连接失败|连接失败|连接路由到主要副本|
|`ApplicationIntent=ReadOnly`|连接失败|连接成功|连接成功

上表显示，当主要副本包含 `READ_WRITE_ROUTING_URL` 集时，次要副本会在 `SECONDARY_ROLE (ALLOW CONNECTIONS = ALL)` 时将连接重定向到主要副本，并且连接会指定 `ReadWrite`。

## <a name="example"></a>示例 

在此示例中，可用性组有三个副本：
* COMPUTER01 上的主要副本
* COMPUTER02 上的同步次要副本
* COMPUTER03 上的同步次要副本

下图表示可用性组。

![原始可用性组](media/replica-connection-redirection-always-on-availability-groups/01_originalAG.png)

以下 Transact-SQL 脚本创建此 AG。 在此示例中，每个副本都会指定 `READ_WRITE_ROUTING_URL`。
```sql
CREATE AVAILABILITY GROUP MyAg   
     WITH ( CLUSTER_TYPE =  NONE )  
   FOR   
     DATABASE  <Database1>   
   REPLICA ON   
      'COMPUTER01' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER01.<domain>.<tld>:5022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = MANUAL,  
         SECONDARY_ROLE (ALLOW_CONNECTIONS = ALL,   
            READ_ONLY_ROUTING_URL = 'TCP://COMPUTER01.<domain>.<tld>:1433' ),
         PRIMARY_ROLE (ALLOW_CONNECTIONS = READ_WRITE,   
            READ_ONLY_ROUTING_LIST = (COMPUTER02, COMPUTER03),
            READ_WRITE_ROUTING_URL = 'TCP://COMPUTER01.<domain>.<tld>:1433' )   
         SESSION_TIMEOUT = 10  
         ),   
      'COMPUTER02' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER02.<domain>.<tld>:5022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = MANUAL, 
         SECONDARY_ROLE (ALLOW_CONNECTIONS = ALL,   
            READ_ONLY_ROUTING_URL = 'TCP://COMPUTER02.<domain>.<tld>:1433' ),  
         PRIMARY_ROLE (ALLOW_CONNECTIONS = READ_WRITE,   
            READ_ONLY_ROUTING_LIST = (COMPUTER01, COMPUTER03),  
            READ_WRITE_ROUTING_URL = 'TCP://COMPUTER02.<domain>.<tld>:1433' )   
         SESSION_TIMEOUT = 10  
         ),   
      'COMPUTER03' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER03.<domain>.<tld>:5022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = MANUAL,  
         SECONDARY_ROLE (ALLOW_CONNECTIONS = ALL,   
            READ_ONLY_ROUTING_URL = 'TCP://COMPUTER03.<domain>.<tld>:1433' ),  
         PRIMARY_ROLE (ALLOW_CONNECTIONS = READ_WRITE,   
            READ_ONLY_ROUTING_LIST = (COMPUTER01, COMPUTER02),  
            READ_WRITE_ROUTING_URL = 'TCP://COMPUTER03.<domain>.<tld>:1433' )  
         SESSION_TIMEOUT = 10  
         );
GO  
```
   - `<domain>.<tld>`
      - 完全限定域名的域和顶级域。 例如， `corporation.com`。


### <a name="connection-behaviors"></a>连接行为

在下图中，客户端应用程序连接到 COMPUTER02，且 `ApplicationIntent=ReadWrite`。 连接重定向到主要副本。 

![原始可用性组](media/replica-connection-redirection-always-on-availability-groups/02_redirectionAG.png)

次要副本会将读/写调用重定向到主要副本。 与任一副本的读写连接将重定向到主要副本。 

在下图中，主要副本已手动故障转移至 COMPUTER02。 客户端应用程序连接到 COMPUTER01，且 `ApplicationIntent=ReadWrite`。 连接重定向到主要副本。 

![原始可用性组](media/replica-connection-redirection-always-on-availability-groups/03_redirectionAG.png)


## <a name="sql-server-instance-offline"></a>SQL Server 实例脱机

如果连接字符串中指定的 SQL Server 实例不可用（发生中断），则无论目标服务器上的副本扮演何种角色，连接都将失败。 若要避免长时间的应用程序故障时间，请在连接字符串中配置备用 `FailoverPartner`。 应用程序必须实现重试逻辑，以适应在实际故障转移期间未联机的主要副本和次要副本。 有关连接字符串的信息，请参阅 [SqlConnection.ConnectionString 属性](http://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx)。

## <a name="see-also"></a>另请参阅  
[AlwaysOn 可用性组概述 (SQL Server)](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 
[关于对可用性副本的客户端连接访问 (SQL Server)](../../../database-engine/availability-groups/windows/about-client-connection-access-to-availability-replicas-sql-server.md)   

[可用性组侦听程序、客户端连接和应用程序故障转移 (SQL Server)](../../../database-engine/availability-groups/windows/listeners-client-connectivity-application-failover.md) 