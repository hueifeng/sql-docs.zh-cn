---
title: ADOStreamConstruction 接口 |Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- ADOStreamConstruction
helpviewer_keywords:
- ADOStreamConstruction interface [ADO]
ms.assetid: 92f5a939-3e1a-4b14-a9dd-90e6ce2dec74
author: rothja
ms.author: jroth
ms.openlocfilehash: 75af8d899c4fb0b97f4ee09795888ef773999b60
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "87242807"
---
# <a name="adostreamconstruction-interface"></a>ADOStreamConstruction 接口
**ADOStreamConstruction**接口用于从 c/c + + 应用程序中的 OLE DB **ISTREAM**对象构造 ADO**流**对象。  
  
## <a name="properties"></a>属性  
  
|属性|描述|  
|-|-|  
|[流](../../../ado/reference/ado-api/stream-property.md)|读/写。 获取/设置 OLE DB**流**对象。|  
  
## <a name="methods"></a>方法  
 无。  
  
## <a name="events"></a>事件  
 无。  
  
## <a name="remarks"></a>备注  
 给定一个 OLE DB **IStream**对象（ `pStream` ），将 ADO**流**对象（）的构造 `adoStr` 分为以下三个基本操作：  
  
1.  创建 ADO**流**对象：  
  
    ```  
    Stream20Ptr adoStr;  
    adoStr.CreateInstance(__uuidof(Stream));  
    ```  
  
2.  查询**Stream**对象上的**IADOStreamConstruction**接口：  
  
    ```  
    adoStreamConstructionPtr adoStrConstruct=NULL;  
    adoStr->QueryInterface(__uuidof(ADOStreamConstruction),  
                         (void**)&adoStrConstruct);  
    ```  
  
 调用 `IADOStreamConstruction::get_Stream` 属性方法，设置 ADO**流**对象上的 OLE DB **IStream**对象：  
  
```  
IUnknown *pUnk=NULL;  
pRowset->QueryInterface(IID_IUnknown, (void**)&pUnk);  
adoStrConstruct->put_Stream(pUnk);  
```  
  
 生成的 `adoStr` 对象现在表示从 OLE DB **IStream**对象构造的 ADO**流**对象。  
  
## <a name="requirements"></a>要求  
 **版本：** ADO 2.0 或更高版本  
  
 **库：** msado15.dll  
  
 **UUID：** 00000283-0000-0010-8000-00AA006D2EA4  
  
## <a name="see-also"></a>另请参阅  
 [ADO API 参考](../../../ado/reference/ado-api/ado-api-reference.md)
