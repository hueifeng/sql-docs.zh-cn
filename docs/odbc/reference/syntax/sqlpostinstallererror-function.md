---
title: SQLPostInstallerError 函数 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLPostInstallerError
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLPostInstallerError
helpviewer_keywords:
- SQLPostInstallerError function [ODBC]
ms.assetid: 4c60d827-b2d2-4f27-b220-daa9e1fcdd8d
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: cdceff5c4e175ba9f135c6e5e4405933b1a86b7c
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "81306888"
---
# <a name="sqlpostinstallererror-function"></a>SQLPostInstallerError 函数
**度**  
 引入的版本： ODBC 3。0  
  
 **摘要**  
 **SQLPostInstallerError**提供了一种机制，使驱动程序或转换器安装程序库将**ConfigDriver**、 **ConfigDSN**和**ConfigTranslator**函数的错误报告给安装程序错误队列。 应用程序不使用此 API;它们使用**SQLInstallerError**来检索错误。  
  
## <a name="syntax"></a>语法  
  
```cpp  
  
RETCODE SQLPostInstallerError(  
     DWORD    fErrorCode,  
     LPSTR    szErrorMsg);  
```  
  
## <a name="arguments"></a>参数  
 *fErrorCode*  
 送安装程序错误代码。  
  
 *szErrorMsg*  
 送错误消息文本。  
  
## <a name="returns"></a>返回  
 SQL_SUCCESS 或 SQL_ERROR。  
  
## <a name="diagnostics"></a>诊断  
 **SQLPostInstallerError**不会为自身发布错误值。 如果错误已成功发布到安装程序错误队列（使用**SQLInstallerError**可检索），则返回 SQL_SUCCESS。 如果*dwErrorCode*参数中的值不是指定的安装程序错误代码之一，将返回 SQL_ERROR。  
  
## <a name="related-functions"></a>相关函数  
  
|有关以下方面的信息|查看|  
|---------------------------|---------|  
|添加、修改或删除驱动程序|[ConfigDriver](../../../odbc/reference/syntax/configdriver-function.md)|  
|添加、修改或删除数据源|[ConfigDSN](../../../odbc/reference/syntax/configdsn-function.md)|  
|设置翻译选项|[ConfigTranslator](../../../odbc/reference/syntax/configtranslator-function.md)|
