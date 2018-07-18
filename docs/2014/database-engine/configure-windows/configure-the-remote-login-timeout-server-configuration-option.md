---
title: 配置 remote login timeout 服务器配置选项 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- remote login timeout option
ms.assetid: 077adebe-0e3f-42a5-a75e-5e6d04847e2b
caps.latest.revision: 26
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 1ede757326f8cfc22b6334c0e7b7116c588bd17a
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37259193"
---
# <a name="configure-the-remote-login-timeout-server-configuration-option"></a>配置 remote login timeout 服务器配置选项
  本主题说明如何使用 **或** 在 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 中配置 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] remote login timeout [!INCLUDE[tsql](../../includes/tsql-md.md)]服务器配置选项。 **remote login timeout** 选项指定从登录远程服务器失败返回前等待的秒数。 例如，如果您尝试登录到一个远程服务器而该服务器已关闭， **remote login timeout** 帮助确保您在计算机停止登录尝试前不必无限期地等待下去。 此选项的默认值为 10 秒。 如果该值为 0，则允许无限期等待。  
  
> [!NOTE]  
>  此选项的默认值在 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]中为 20 秒。  
  
 **本主题内容**  
  
-   **开始之前：**  
  
     [限制和局限](#Restrictions)  
  
     [Security](#Security)  
  
-   **配置 remote login timeout 选项，使用：**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
-   **跟进：**[在配置 remote login timeout 选项之后](#FollowUp)  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Restrictions"></a> 限制和局限  
  
-   **remote login timeout** 选项影响与 OLE DB 访问接口之间为异类查询建立的连接。  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> Permissions  
 默认情况下，所有用户都具备不带参数或仅带第一个参数的 **sp_configure** 的执行权限。 若要执行带两个参数的 **sp_configure** 以更改配置选项或运行 RECONFIGURE 语句，则用户必须具备 ALTER SETTINGS 服务器级别的权限。 ALTER SETTINGS 权限由 **sysadmin** 和 **serveradmin** 固定服务器角色隐式持有。  
  
##  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a>配置 remote login timeout 选项  
  
1.  在对象资源管理器中，右键单击服务器并选择 **“属性”**。  
  
2.  单击 **“高级”** 节点。  
  
3.  在 **“网络”** 下，为 **“远程登录超时值”** 框选择一个值。  
  
     使用 **remote login timeout** 选项可以指定从远程登录失败返回前等待的秒数。  
  
##  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a>配置 remote login timeout 选项  
  
1.  连接到[!INCLUDE[ssDE](../../includes/ssde-md.md)]。  
  
2.  在标准菜单栏上，单击 **“新建查询”**。  
  
3.  将以下示例复制并粘贴到查询窗口中，然后单击“执行” 。 此示例说明如何使用 [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) 将 `remote login timeout` 选项的值设置为 `35` 秒。  
  
```tsql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote login timeout', 35 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 有关详细信息，请参阅 [服务器配置选项 (SQL Server)](server-configuration-options-sql-server.md)版本的组合自动配置的最大工作线程数。  
  
##  <a name="FollowUp"></a> 跟进：在配置 remote login timeout 选项之后  
 该设置将立即生效，无需重新启动服务器。  
  
## <a name="see-also"></a>请参阅  
 [RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql)   
 [服务器配置选项 (SQL Server)](server-configuration-options-sql-server.md)   
 [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  