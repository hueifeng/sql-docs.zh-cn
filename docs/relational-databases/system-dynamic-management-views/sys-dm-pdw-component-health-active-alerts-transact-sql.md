---
title: sys. dm_pdw_component_health_active_alerts （Transact-sql）
ms.custom: seo-dt-2019
ms.date: 03/07/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: conceptual
ms.assetid: c53e4a36-b841-424a-b8e2-255b1878deb6
author: CarlRabeler
ms.author: carlrab
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 0a8a1808e20accfadd3adc6f5a5c326f78870ed7
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2020
ms.locfileid: "87395191"
---
# <a name="sysdm_pdw_component_health_active_alerts-transact-sql"></a>sys. dm_pdw_component_health_active_alerts （Transact-sql）
[!INCLUDE [pdw](../../includes/applies-to-version/pdw.md)]

  在组件上存储活动警报 [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] 。  
  
|列名|数据类型|说明|范围|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**|节点的唯一标识符 [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] 。<br /><br /> pdw_node_id、component_id、component_instance_id、alert_id 和 alert_instance_id 构成此视图的键。|NOT NULL|  
|component_id|**int**|组件的 ID。 请参阅[sys.databases &#40;transact-sql&#41;pdw_health_components ](../../relational-databases/system-catalog-views/sys-pdw-health-components-transact-sql.md)。<br /><br /> pdw_node_id、component_id、component_instance_id、alert_id 和 alert_instance_id 构成此视图的键。|NOT NULL|  
|component_instance_id|**nvarchar(255)**|pdw_node_id、component_id、component_instance_id、alert_id 和 alert_instance_id 构成此视图的键。|NOT NULL|  
|alert_id|**int**|警报类型的 ID。 请参阅[sys.databases &#40;transact-sql&#41;pdw_health_alerts ](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md)。<br /><br /> pdw_node_id、component_id、component_instance_id、alert_id 和 alert_instance_id 构成此视图的键。|NOT NULL|  
|alert_instance_id|**nvarchar （36）**|标识给定警报的实例。<br /><br /> pdw_node_id、component_id、component_instance_id、alert_id 和 alert_instance_id 构成此视图的键。|NOT NULL|  
|current_value|**nvarchar(255)**|当警报的类型为 StatusChange 时使用。 这是当前的组件状态。 对于阈值类型的警报，值为 NULL。 有关警报类型的列表，请参阅[&#40;transact-sql&#41;pdw_health_alerts](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md) 。|Null|  
|previous_value|**nvarchar(255)**|当警报的类型为 StatusChange 时使用。 这是之前的组件状态。 对于阈值类型的警报，值为 NULL。 有关警报类型的列表，请参阅[&#40;transact-sql&#41;pdw_health_alerts](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md) 。|Null|  
|create_time|**datetime**|生成警报的时间和日期。|NOT NULL|  
  
 有关此视图保留的最大行的信息，请参阅中的 "最小值和最大值" [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)] 。  
  
## <a name="see-also"></a>另请参阅  
 [SQL 数据仓库和并行数据仓库动态管理视图 &#40;Transact-sql&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
