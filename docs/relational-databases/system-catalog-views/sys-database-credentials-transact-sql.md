---
title: sys. database_credentials （Transact-sql） |Microsoft Docs
ms.custom: ''
ms.date: 02/27/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.database_credentials
- sys.database_credentials_TSQL
- database_credentials
- database_credentials_TSQL
helpviewer_keywords:
- sys.database_credentials catalog view
ms.assetid: 796322df-e62a-45bf-b519-89e1d521abce
author: VanMSFT
ms.author: vanto
monikerRange: =azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 5b78875b7c6f3440bd747045d1b90d0f8ef323c4
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2020
ms.locfileid: "87394882"
---
# <a name="sysdatabase_credentials-transact-sql"></a>sys. database_credentials （Transact-sql）
[!INCLUDE [sqlserver2016-asdb-asdbmi-asa](../../includes/applies-to-version/sqlserver2016-asdb-asdbmi-asa.md)]

  为数据库中的每个数据库作用域凭据返回一行。  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]改用[sys.databases database_scoped_credentials](../../relational-databases/system-catalog-views/sys-database-scoped-credentials-transact-sql.md) 。    
  
|列名称|数据类型|说明|  
|-----------------|---------------|-----------------|  
|credential_id|**int**|数据库作用域凭据的 ID。 在数据库中是唯一的。|  
|name|**sysname**|数据库作用域凭据的名称。 在数据库中是唯一的。|  
|credential_identity|**nvarchar(4000)**|要使用的标识的名称。 这通常是一个 Windows 用户。 它不必是唯一的。|  
|create_date|**datetime**|创建数据库作用域凭据的时间。|  
|modify_date|**datetime**|上次修改数据库作用域凭据的时间。|  
|target_type|**nvarchar （100）**|数据库作用域凭据的类型。 对于数据库范围的凭据，返回 NULL。|  
|target_id|**int**|将数据库范围凭据映射到的对象的 ID。 对于数据库范围的凭据，返回0|  
  
## <a name="permissions"></a>权限  
 需要对数据库拥有 `CONTROL` 权限。  
  
## <a name="see-also"></a>另请参阅  
 [凭据 &#40;数据库引擎&#41;](../../relational-databases/security/authentication-access/credentials-database-engine.md)   
 [&#40;Transact-sql&#41;创建数据库作用域凭据](../../t-sql/statements/create-database-scoped-credential-transact-sql.md)   
 [更改数据库作用域凭据 &#40;Transact-sql&#41;](../../t-sql/statements/alter-database-scoped-credential-transact-sql.md)   
 [&#40;Transact-sql&#41;删除数据库范围的凭据](../../t-sql/statements/drop-database-scoped-credential-transact-sql.md)   
 [CREATE CREDENTIAL &#40;Transact-SQL&#41;](../../t-sql/statements/create-credential-transact-sql.md)   
 [sys.credentials (Transact-SQL)](../../relational-databases/system-catalog-views/sys-credentials-transact-sql.md)  
  
  
