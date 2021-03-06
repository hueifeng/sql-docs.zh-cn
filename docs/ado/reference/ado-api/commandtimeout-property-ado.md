---
title: CommandTimeout 属性（ADO） |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Command15::CommandTimeout
helpviewer_keywords:
- CommandTimeout property [ADO]
ms.assetid: c611f857-d6b0-4dca-8925-f4a02e769eb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 0b708b2b79c22240468811732d2ffae0955ea204
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "87242777"
---
# <a name="commandtimeout-property-ado"></a>CommandTimeout 属性 (ADO)
指示在终止尝试并生成错误之前执行命令时等待的时间。  
  
## <a name="settings-and-return-values"></a>设置和返回值  
 设置或返回一个**长整型**值，该值指示等待命令执行所用的时间（以秒为单位）。 默认值为 30。  
  
## <a name="remarks"></a>备注  
 使用[连接](../../../ado/reference/ado-api/connection-object-ado.md)对象或[命令](../../../ado/reference/ado-api/command-object-ado.md)对象上的**CommandTimeout**属性，以允许取消[执行](../../../ado/reference/ado-api/execute-method-ado-command.md)方法调用，因为网络流量或服务器使用的时间延迟。 如果在命令完成执行之前， **CommandTimeout**属性中设置的时间间隔已过，则会发生错误并且 ADO 将取消该命令。 如果将属性设置为零，则 ADO 将无限期等待，直到执行完成为止。 请确保编写代码的访问接口和数据源支持**CommandTimeout**功能。  
  
 **连接**对象上的**CommandTimeout**设置对同一**连接**上**命令**对象上的**CommandTimeout**设置不起任何作用;也就是说，**命令**对象的**CommandTimeout**属性不继承**Connection**对象的**CommandTimeout**值。  
  
 在**连接**对象上， **CommandTimeout**属性在**连接**打开后保持为读/写。  
  
## <a name="applies-to"></a>适用于  

:::row:::
    :::column:::
        [命令对象 (ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
    :::column-end:::
    :::column:::
        [连接对象 (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>另请参阅  
 [ActiveConnection、CommandText、CommandTimeout、CommandType、Size 和 Direction 属性示例（VB）](../../../ado/reference/ado-api/activeconnection-commandtext-commandtimeout-commandtype-size-example-vb.md)   
 [ActiveConnection、CommandText、CommandTimeout、CommandType、Size 和 Direction 属性示例（VC + +）](../../../ado/reference/ado-api/activeconnection-commandtext-commandtimeout-commandtype-size-example-vc.md)   
 [ActiveConnection、CommandText、CommandTimeout、CommandType、Size 和 Direction 属性示例（JScript）](../../../ado/reference/ado-api/activeconnection-commandtext-timeout-type-size-example-jscript.md)   
 [ConnectionTimeout 属性 (ADO)](../../../ado/reference/ado-api/connectiontimeout-property-ado.md)
