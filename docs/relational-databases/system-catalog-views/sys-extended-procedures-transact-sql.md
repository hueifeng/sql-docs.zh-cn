---
title: sys. extended_procedures （Transact-sql） |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- extended_procedures
- sys.extended_procedures
- sys.extended_procedures_TSQL
- extended_procedures_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.extended_procedures catalog view
ms.assetid: 310e0f87-0044-4fdf-bd12-51a723a74ce6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4baab44b81ff3e2a2b4a4c6a653527190140f24b
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "85892186"
---
# <a name="sysextended_procedures-transact-sql"></a>sys.extended_procedures (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  为扩展存储过程的每个对象都包含一个包含**sys.databases** = X 的行。因为扩展存储过程安装在**master**数据库中，所以它们只会在该数据库上下文中可见。 从任何其他数据库上下文中的**sys.databases extended_procedures**视图中进行选择将返回一个空结果集。  

  
|列名称|数据类型|说明|  
|-----------------|---------------|-----------------|  
|**\<Columns inherited from sys.objects>**||有关此视图所继承的列的列表，请参阅[sys.databases &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)。|  
|**dll_name**|**nvarchar(260)**|此扩展存储过程的 DLL 的名称，包括路径。|  
  
## <a name="permissions"></a>权限  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 有关详细信息，请参阅 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [&#40;Transact-sql&#41;的对象目录视图](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
