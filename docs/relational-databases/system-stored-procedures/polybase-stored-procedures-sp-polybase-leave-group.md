---
title: sp_polybase_leave_group （Transact-sql） |Microsoft Docs
description: Sp_polybase_leave_group Transact-sql 命令从 PolyBase 组中删除用于扩展计算的 SQL Server 实例。
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.technology: polybase
ms.topic: conceptual
f1_keywords:
- sp_polybase_leave_group
- sp_polybase_leave_group_TSQL
helpviewer_keywords:
- sp_polybase_leave_group
ms.assetid: ef87a8f1-5407-47b5-b8bf-bd7d08c0f0fe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 82bcad58a97fa41938f127c0a814c312c4e22ec9
ms.sourcegitcommit: 703968b86a111111a82ef66bb7467dbf68126051
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052705"
---
# <a name="sp_polybase_leave_group-transact-sql"></a>sp_polybase_leave_group （Transact-sql）
[!INCLUDE [sqlserver2016](../../includes/applies-to-version/sqlserver2016.md)]

  从 PolyBase 组中删除用于扩展计算的 SQL Server 实例。 
 
 SQL Server 实例必须安装[PolyBase 指南](../../relational-databases/polybase/polybase-guide.md)功能。  PolyBase 启用了非 SQL Server 数据源，如 Hadoop 和 Azure blob 存储。 另请参阅[sp_polybase_join_group](../../relational-databases/system-stored-procedures/polybase-stored-procedures-sp-polybase-join-group.md)。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "“主题链接”图标") [Transact-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_polybase_leave_group;  
  
```  
  
## <a name="return-code-values"></a>返回代码值  
 0（成功）或 1（失败）  
  
## <a name="permissions"></a>权限  
 需要 CONTROL SERVER 权限。  
  
## <a name="remarks"></a>注解  
 只能从组中删除计算节点。  
  
 运行存储过程后，重新启动计算机上的 PolyBase 引擎和 PolyBase 数据移动服务。 验证在头节点上运行以下 DMV： **sys. dm_exec_compute_nodes**。  
  
## <a name="example"></a>示例  
 该示例从 PolyBase 组中删除当前计算机。  
  
```sql  
EXEC sp_polybase_leave_group ;  
```  
  
## <a name="see-also"></a>另请参阅  
 [PolyBase 入门](../../relational-databases/polybase/get-started-with-polybase.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
