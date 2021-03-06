---
title: Refresh 方法（RDS） |Microsoft Docs
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.prod: sql
ms.prod_service: connectivity
ms.topic: conceptual
apitype: COM
f1_keywords:
- Refresh
- RDS.DataControl::Refresh
- DataControl::Refresh
helpviewer_keywords:
- Refresh method [RDS]
ms.assetid: c90a8050-0ff4-4c83-9925-261f2f2ccfe9
author: rothja
ms.author: jroth
ms.openlocfilehash: 3e9fa606aab5d42a7b56171ca3720742d4d119a0
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2020
ms.locfileid: "82751052"
---
# <a name="refresh-method-rds"></a>Refresh 方法 (RDS)
重新查询[连接](../../../ado/reference/rds-api/connect-property-rds.md)属性中指定的数据源，并更新查询结果。  
  
> [!IMPORTANT]
>  从 Windows 8 和 Windows Server 2012 开始，Windows 操作系统中不再包含 RDS 服务器组件（有关详细信息，请参阅 Windows 8 和[Windows Server 2012 兼容性指南](https://www.microsoft.com/download/details.aspx?id=27416)）。 在 Windows 的未来版本中将删除 RDS 客户端组件。 请避免在新的开发工作中使用该功能，并着手修改当前还在使用该功能的应用程序。 使用 RDS 的应用程序应迁移到[WCF 数据服务](https://go.microsoft.com/fwlink/?LinkId=199565)。  
  
## <a name="syntax"></a>语法  
  
```  
  
DataControl.Refresh  
```  
  
#### <a name="parameters"></a>参数  
 *DataControl*  
 表示 RDS 的对象变量[。DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md)对象。  
  
## <a name="remarks"></a>备注  
 必须先设置[Connect](../../../ado/reference/rds-api/connect-property-rds.md)、 [Server](../../../ado/reference/rds-api/server-property-rds.md)和[SQL](../../../ado/reference/rds-api/sql-property.md)属性，然后才能使用**Refresh**方法。 窗体上的所有与 RDS 关联的数据绑定控件 **。DataControl**对象将反映新的记录集。 将释放任何预先存在的[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)对象，并放弃任何未保存的更改。 **Refresh**方法自动使第一条记录成为当前记录。  
  
 在处理数据时，最好定期调用**Refresh**方法。 如果检索数据，然后将数据保留在客户端计算机上一段时间，则可能会过时。 您所做的任何更改都可能会失败，因为其他人可能已在您之前更改了记录并提交了更改。  
  
## <a name="applies-to"></a>应用于  
 [DataControl 对象 (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)  
  
## <a name="see-also"></a>另请参阅  
 [Refresh 方法示例（VB）](../../../ado/reference/ado-api/refresh-method-example-vb.md)   
 [Refresh 方法示例（VBScript）](../../../ado/reference/rds-api/refresh-method-example-vbscript.md)   
 [通讯簿命令按钮](../../../ado/guide/remote-data-service/address-book-command-buttons.md)   
 [CancelUpdate 方法（RDS）](../../../ado/reference/rds-api/cancelupdate-method-rds.md)   
 [Refresh 方法（ADO）](../../../ado/reference/ado-api/refresh-method-ado.md)   
 [SubmitChanges 方法 (RDS)](../../../ado/reference/rds-api/submitchanges-method-rds.md)


