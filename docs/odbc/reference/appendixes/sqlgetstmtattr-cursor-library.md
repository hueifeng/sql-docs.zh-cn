---
title: SQLGetStmtAttr （游标库） |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLGetStmtAttr function [ODBC], Cursor Library
ms.assetid: 6c34e1ef-4273-4afb-a7d3-f9017ab69c5e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a9b29d21c166751f5a57b7951cb6c028861cb501
ms.sourcegitcommit: 99f61724de5edf6640efd99916d464172eb23f92
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "87362947"
---
# <a name="sqlgetstmtattr-cursor-library"></a>SQLGetStmtAttr（游标库）
> [!IMPORTANT]  
>  此功能将在 Windows 的将来版本中删除。 避免在新的开发工作中使用此功能，并计划修改当前使用此功能的应用程序。 Microsoft 建议使用驱动程序的游标功能。  
  
 本主题讨论如何在游标库中使用**SQLGetStmtAttr**函数。 有关**SQLGetStmtAttr**的常规信息，请参阅[SQLGetStmtAttr 函数](../../../odbc/reference/syntax/sqlgetstmtattr-function.md)。  
  
 游标库支持**SQLGetStmtAttr**的以下语句属性：  

:::row:::
    :::column:::
        SQL_ATTR_CONCURRENCY  
        SQL_ATTR_CURSOR_TYPE  
        SQL_ATTR_FETCH_BOOKMARK_PTR  
        SQL_ATTR_PARAM_BIND_OFFSET_PTR  
        SQL_ATTR_PARAM_BIND_TYPE  
    :::column-end:::
    :::column:::
        SQL_ATTR_ROW_ARRAY_SIZE  
        SQL_ATTR_ROW_BIND_OFFSET_PTR  
        SQL_ATTR_ROW_BIND_TYPE  
        SQL_ATTR_ROW_NUMBER  
        SQL_ATTR_SIMULATE_CURSOR  
    :::column-end:::
:::row-end:::
