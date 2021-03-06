---
title: Synchronize 方法（RDS） |Microsoft Docs
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.prod: sql
ms.prod_service: connectivity
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- Synchronize method [ADO]
ms.assetid: 7af42866-7db2-4174-8251-388a2cf741f2
author: rothja
ms.author: jroth
ms.openlocfilehash: 98254c2f26db08b7c5308248c596b7f70264f10c
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2020
ms.locfileid: "82750569"
---
# <a name="synchronize-method-rds"></a>Synchronize 方法 (RDS)
使用连接字符串指定的数据库同步给定的记录集，以便在 ADO 2.5 和更高版本中使用。  
  
> [!IMPORTANT]
>  从 Windows 8 和 Windows Server 2012 开始，Windows 操作系统中不再包含 RDS 服务器组件（有关详细信息，请参阅 Windows 8 和[Windows Server 2012 兼容性指南](https://www.microsoft.com/download/details.aspx?id=27416)）。 在 Windows 的未来版本中将删除 RDS 客户端组件。 请避免在新的开发工作中使用该功能，并着手修改当前还在使用该功能的应用程序。 使用 RDS 的应用程序应迁移到[WCF 数据服务](https://go.microsoft.com/fwlink/?LinkId=199565)。  
  
## <a name="syntax"></a>语法  
  
```  
  
object.Synchronize(ConnectionString As String, HandlerString As String, lSynchronizeOptions As Long, ppRecordset As Object, pStatusArray, [lcid As Long], [pInformation)  
```  
  
#### <a name="parameters"></a>参数  
 *ConnectionString*  
 一个字符串，用于连接到将在其中发送请求的 OLE DB 提供程序。 如果使用处理程序，则处理程序可以编辑或替换连接字符串。  
  
 *HandlerString*  
 字符串标识要与此执行一起使用的处理程序。 该字符串包含两个部分。 第一部分包含要使用的处理程序的名称（ProgID）。 字符串的第二部分包含要传递给处理程序的参数。 如何解释参数字符串是处理程序特定的。 这两个部分由字符串中逗号的第一个实例分隔（尽管参数字符串可能包含其他逗号）。 这些参数是可选的。  
  
 *lSynchronizeOptions*  
 同步选项的位掩码。  
  
 1 = 对数据库的*UpdateTransact*更新包装在事务中。 如果有任何更新失败，则事务将中止。  
  
 2 =*RefreshWithUpdate*导致在不设置*刷新*和*RefreshConflicts*时返回行状态。  
  
 4 =*刷新*记录集，并通过数据库中的当前数据进行刷新。 挂起的更新不会推送到数据库。 如果未设置此位，则不会刷新记录集，任何挂起的更新都将推送到数据库。  
  
 8 =*RefreshConflicts*包含挂起的更改的所有行都无法更新。 未能更新的行将用数据库中的当前数据进行刷新。  
  
 *ppRecordset*  
 指向要同步的记录集的指针。  
  
 *pStatusArray*  
 一个变体，用于返回受同步影响的行的行状态安全数组。 如果未设置以下任何同步选项，则不设置： *RefreshWithUpdate*、 *Refresh*和*RefreshConflicts*。  
  
 *lcid*  
 LCID，用于生成在*pInformation*中返回的任何错误。  
  
 *pInformation*  
 一个指针，指向**执行**返回的信息错误。 如果为 NULL，则不返回错误信息。  
  
## <a name="remarks"></a>备注  
 *HandlerString*参数可以为 null。 在这种情况下会发生什么情况取决于 RDS 服务器的配置方式。 "MSDFMAP" 的处理程序字符串指示应使用 Microsoft 提供的处理程序（Msdfmap）。 "MASDFMAP" 的处理程序字符串指示应使用 Msdfmap 处理程序，并且应将参数 "sample" 传递到处理程序中，。 然后，Msdfmap 会将参数解释为一个方向，以使用 schema.ini 检查连接和查询字符串。  
  
## <a name="applies-to"></a>应用于  
 [DataFactory 对象 (RDSServer)](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)


