---
title: sys. dm_pdw_errors (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 944eac31-5691-432b-b9f5-f1e11c05191f
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: 0ce09955508fa3743be9d8ef600e05f0e36c4467
ms.sourcegitcommit: 01297f2487fe017760adcc6db5d1df2c1234abb4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "86197103"
---
# <a name="sysdm_pdw_errors-transact-sql"></a>sys. dm_pdw_errors (Transact-sql) 
[!INCLUDE[applies-to-version/asa-pdw](../../includes/applies-to-version/asa-pdw.md)]

  保存在执行请求或查询过程中遇到的所有错误的相关信息。  
  
|列名|数据类型|说明|范围|  
|-----------------|---------------|-----------------|-----------|  
|error_id|**nvarchar (36) **|此视图的键。<br /><br /> 与错误关联的唯一数字 id。|系统中所有查询错误都是唯一的。|  
|source|**nvarchar (64) **|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]|  
|类型|**nvarchar(4000)**|发生的错误的类型。|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]|  
|create_time|**datetime**|发生错误的时间。|小于或等于当前时间。|  
|pwd_node_id|**int**|涉及的特定节点的标识符（如果有）。 有关节点 id 的其他信息，请参阅[transact-sql&#41;&#40;dm_pdw_nodes ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-nodes-transact-sql.md)。||  
|session_id|**nvarchar(32)**|涉及的会话的标识符（如果有）。 有关会话 id 的其他信息，请参阅[transact-sql&#41;&#40;dm_pdw_exec_sessions ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-sessions-transact-sql.md)。||  
|request_id|**nvarchar(32)**|涉及的请求的标识符（如果有）。 有关请求 id 的其他信息，请参阅[&#40;transact-sql&#41;dm_pdw_exec_requests ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md)。||  
|spid|**int**|涉及的 SQL Server 会话的 spid （如果有）。||  
|thread_id|**int**|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]||  
|详细信息|**nvarchar(4000)**|保存完整的错误文本说明。||  
  
 有关此视图保留的最大行的信息，请参阅[容量限制](/azure/sql-data-warehouse/sql-data-warehouse-service-capacity-limits#metadata)主题中的元数据部分。  
  
## <a name="see-also"></a>另请参阅  
 [SQL 数据仓库和并行数据仓库动态管理视图 &#40;Transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
