---
title: SQLRowCount （游标库） |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLRowCount function [ODBC], Cursor Library
ms.assetid: 781cf5a5-325e-4523-8633-d96d9e98277c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: bf9fe597f54ecb4bc82439251e2228ac5fdc4ea3
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "81300577"
---
# <a name="sqlrowcount-cursor-library"></a>SQLRowCount（游标库）
> [!IMPORTANT]  
>  此功能将在 Windows 的将来版本中删除。 避免在新的开发工作中使用此功能，并计划修改当前使用此功能的应用程序。 Microsoft 建议使用驱动程序的游标功能。  
  
 本主题讨论如何在游标库中使用**SQLRowCount**函数。 有关**SQLRowCount**的常规信息，请参阅[SQLRowCount 函数](../../../odbc/reference/syntax/sqlrowcount-function.md)。  
  
 当应用程序使用与光标关联的语句调用**SQLRowCount**时，游标库将返回它从驱动程序检索的数据行数。  
  
 当应用程序使用与定位的 update 或 delete 语句相关联的语句调用**SQLRowCount**时，游标库将返回受该语句影响的行数。  
  
 当应用程序在**SELECT**语句之后调用**SQLRowCount**时，游标库将返回-1。
