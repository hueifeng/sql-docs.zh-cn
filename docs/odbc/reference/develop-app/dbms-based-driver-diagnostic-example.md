---
title: 基于 DBMS 的驱动程序诊断示例 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- DBMS-based driver diagnostic [ODBC]
- diagnostic information [ODBC], examples
- error messages [ODBC], diagnostic messages
ms.assetid: a80d54b0-43ff-4dfd-b6cb-f4694a5ed765
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 117f43548d2b57233dea6f7423e6bad67b6233b0
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "81304348"
---
# <a name="dbms-based-driver-diagnostic-example"></a>基于 DBMS 的驱动程序诊断示例
基于 DBMS 的驱动程序向 DBMS 发送请求，并通过驱动程序管理器将信息返回给应用程序。 由于驱动程序是与驱动程序管理器进行交互的组件，因此它将格式化并返回**SQLGetDiagRec**的参数。  
  
 例如，如果使用 SQL/Services，用于 Oracle Rdb 的 Microsoft 驱动程序遇到无效的游标名称，则它可能从**SQLGetDiagRec**返回以下值：  
  
```  
SQLSTATE:         "34000"  
Native Error:      0  
Diagnostic Msg:   "[Microsoft][ODBC Rdb Driver]Invalid cursor name: EMPLOYEE_CURSOR."  
```  
  
 由于此错误发生在驱动程序中，因此它会将前缀添加到供应商的诊断消息（[Microsoft]）和驱动程序（[ODBC Rdb 驱动程序]）。  
  
 如果 DBMS 找不到表 EMPLOYEE，驱动程序可能会设置格式并从**SQLGetDiagRec**返回以下值：  
  
```  
SQLSTATE:         "42S02"  
Native Error:      -1  
Diagnostic Msg:   "[Microsoft][ODBC Rdb Driver][Rdb] %SQL-F-RELNOTDEF, Table EMPLOYEE "  
                  "is not defined in schema."  
```  
  
 由于错误发生在数据源中，因此驱动程序将数据源标识符（[Rdb]）的前缀添加到了诊断消息。 由于驱动程序是与数据源接口的组件，因此它向诊断消息添加了其供应商（[Microsoft]）和标识符（[ODBC Rdb 驱动程序]）的前缀。
