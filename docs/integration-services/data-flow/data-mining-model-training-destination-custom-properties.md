---
title: 数据挖掘模型定型目标自定义属性 | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f0a70216-fdac-44ae-af29-35f65626217c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2ffa0b82f393172f92b17e7bbe78302372c9b8ca
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86916776"
---
# <a name="data-mining-model-training-destination-custom-properties"></a>数据挖掘模型定型目标自定义属性

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  数据挖掘模型定型目标具有自定义属性和所有数据流组件通用的属性。  
  
 下表介绍了数据挖掘模型定型目标的自定义属性。 所有属性均可读/写。  
  
|properties|数据类型|说明|  
|--------------|---------------|-----------------|  
|ASConnectionId|String|连接管理器的唯一标识符。|  
|ASConnectionString|String|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 的实例或 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 项目的连接字符串。|  
|ObjectRef|String|标识转换使用的数据挖掘结构的 XML 标记。|  
  
 数据挖掘模型定型目标的输入和输入列没有自定义属性。  
  
 有关详细信息，请参阅 [Data Mining Model Training Destination](../../integration-services/data-flow/data-mining-model-training-destination.md)。  
  
## <a name="see-also"></a>另请参阅  
 [Common Properties](https://msdn.microsoft.com/library/51973502-5cc6-4125-9fce-e60fa1b7b796)  
  
  
