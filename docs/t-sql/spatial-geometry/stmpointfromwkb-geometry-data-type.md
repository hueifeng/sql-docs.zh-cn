---
title: STMPointFromWKB（geometry 数据类型）| Microsoft Docs
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- STMPointFromWKB (geometry Data Type)
- STMPointFromWKB_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STMPointFromWKB (geometry Data Type)
ms.assetid: 01d4117f-01a0-4bc3-8762-7382a1cdbd6c
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: f538896347f5ca9148b422d992450314a6cde50f
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "86552785"
---
# <a name="stmpointfromwkb-geometry-data-type"></a>STMPointFromWKB（geometry 数据类型）
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

从开放地理空间信息联盟 (OGC) 已知二进制 (WKB) 表示形式返回 **geometryMultiPoint** 实例。
  
## <a name="syntax"></a>语法  
  
```  
  
STMPointFromWKB ( 'WKB_multipoint' , SRID )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>参数
 WKB_multipoint   
 希望返回的 **geometryMultiPoint** 实例的 WKB 表示形式。 WKB_multipoint 是一个 varbinary(max) 表达式   。  
  
 SRID   
 一个 int 表达式，表示希望返回的 geometryMultiPoint 实例的空间引用 ID (SRID)   。  
  
## <a name="return-types"></a>返回类型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 返回类型：geometry   
  
 CLR 返回类型：SqlGeometry   
  
 OGC 类型：MultiPoint   
  
## <a name="remarks"></a>备注  
 如果输入的格式不正确，此方法将引发 FormatException  。  
  
## <a name="examples"></a>示例  
 下面的示例使用 `STMPointFromWKB()` 创建 `geometry` 实例。  
  
```  
DECLARE @g geometry;   
SET @g = geometry::STMPointFromWKB(0x010400000002000000010100000000000000000059400000000000005940010100000000000000000069400000000000006940, 0);  
SELECT @g.STAsText();  
```  
  
## <a name="see-also"></a>另请参阅  
 [OGC 静态几何图形方法](../../t-sql/spatial-geometry/ogc-static-geometry-methods.md)  
  
  

