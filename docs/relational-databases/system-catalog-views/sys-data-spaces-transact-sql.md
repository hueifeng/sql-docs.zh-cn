---
title: sys. data_spaces （Transact-sql） |Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- data_spaces
- sys.data_spaces_TSQL
- sys.data_spaces
- data_spaces_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.data_spaces catalog view
ms.assetid: f39d55fe-2c0f-472d-a77f-cebc6fea95b5
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: df3dd7f9680860455ec6291e8ba4a945f4db2043
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2020
ms.locfileid: "87394052"
---
# <a name="sysdata_spaces-transact-sql"></a>sys.data_spaces (Transact-SQL)
[!INCLUDE [sql-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdbmi-asa-pdw.md)]

  每个数据空间在表中对应一行。 数据空间可以是文件组、分区方案或 FILESTREAM 数据文件组。  
  
|列名称|数据类型|说明|  
|-----------------|---------------|-----------------|  
|name|**sysname**|数据空间的名称，在数据库中唯一。|  
|data_space_id|**int**|数据空间 ID 号，在数据库中唯一。|  
|type|**char(2)**|数据空间类型：<br /><br /> FG = 文件组<br /><br /> FD = FILESTREAM 数据文件组<br /><br /> FX = 内存优化表文件组<br /><br /> **适用于**：[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] 及更高版本。<br /><br /> PS = 分区方案|  
|type_desc|**nvarchar(60)**|数据空间类型的说明：<br /><br /> FILESTREAM_DATA_FILEGROUP<br /><br /> MEMORY_OPTIMIZED_DATA_FILEGROUP<br /><br /> **适用于**：[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] 及更高版本。<br /><br /> PARTITION_SCHEME<br /><br /> ROWS_FILEGROUP|  
|is_default|**bit**|1 = 这是默认数据空间。 如果在 CREATE TABLE 或 CREATE INDEX 语句中没有指定文件组或分区方案，将使用默认数据空间。<br /><br /> 0 = 这不是默认数据空间。|  
|is_system|**bit**|**适用于**：[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] 及更高版本。<br /><br /> 1 = 数据空间用于全文检索片段。<br /><br /> 0 = 数据空间不用于全文检索片段。|  
  
## <a name="permissions"></a>权限  
 要求具有 public 角色的成员身份。 有关详细信息，请参阅 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="see-also"></a>另请参阅  
 [数据空间 &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/data-spaces-transact-sql.md)   
 [目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [sys.databases (Transact-SQL)](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md)   
 [sys. destination_data_spaces &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-destination-data-spaces-transact-sql.md)   
 [sys.filegroups (Transact-SQL)](../../relational-databases/system-catalog-views/sys-filegroups-transact-sql.md)   
 [sys. partition_schemes &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-partition-schemes-transact-sql.md)   
 [查询 SQL Server 系统目录常见问题](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)   
 [内存中 OLTP（内存中优化）](../../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
