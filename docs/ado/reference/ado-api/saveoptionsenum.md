---
title: SaveOptionsEnum |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- SaveOptionsEnum
helpviewer_keywords:
- SaveOptionsEnum enumeration [ADO]
ms.assetid: 59339100-6e29-48d1-aea3-6873796d186b
author: rothja
ms.author: jroth
ms.openlocfilehash: 3423d215fa4a52286509769bb2ac0b75d2283a02
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2020
ms.locfileid: "82755842"
---
# <a name="saveoptionsenum"></a>SaveOptionsEnum
指定在从[流](../../../ado/reference/ado-api/stream-object-ado.md)对象保存时是否应创建或覆盖文件。 这些值可以是**adSaveCreateNotExist**或**adSaveCreateOverWrite**。  
  
|返回的常量|值|说明|  
|--------------|-----------|-----------------|  
|**adSaveCreateNotExist**|1|默认。 如果*FileName*参数指定的文件尚不存在，则创建一个新文件。|  
|**adSaveCreateOverWrite**|2|如果*Filename*参数指定的文件已存在，则使用当前打开的**流**对象中的数据覆盖该文件。 如果*Filename*参数指定的文件不存在，则创建新的文件。|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC 等效项  
 这些常量没有 ADO/WFC 等效项。  
  
## <a name="applies-to"></a>应用于  
 [SaveToFile 方法](../../../ado/reference/ado-api/savetofile-method.md)
