---
title: SQLWriteDSNToIni 函数 |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLWriteDSNToIni
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLWriteDSNToIni
helpviewer_keywords:
- SQLWriteDSNToIni [ODBC]
ms.assetid: dc7018b2-18d4-4657-96d0-086479a47474
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b8bb141c8f54c49ca3a5c6fc4bc15d434f91795c
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "81286957"
---
# <a name="sqlwritedsntoini-function"></a>SQLWriteDSNToIni 函数
**度**  
 引入的版本： ODBC 1。0  
  
 **摘要**  
 **SQLWriteDSNToIni**将数据源添加到系统信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
  
BOOL SQLWriteDSNToIni(  
     LPCSTR   lpszDSN,  
     LPCSTR   lpszDriver);  
```  
  
## <a name="arguments"></a>参数  
 *lpszDSN*  
 送要添加的数据源的名称。  
  
 *lpszDriver*  
 送显示给用户的驱动程序描述（通常为关联 DBMS 的名称），而不是物理驱动程序名称。  
  
## <a name="returns"></a>返回  
 如果此函数成功，则返回 TRUE，否则返回 FALSE。  
  
## <a name="diagnostics"></a>诊断  
 当**SQLWriteDSNToIni**返回 FALSE 时，可以* \** 通过调用**SQLInstallerError**获取关联的 pfErrorCode 值。 下表列出了可由**SQLInstallerError**返回的* \*pfErrorCode*值，并说明了此函数的上下文中的每个值。  
  
|*\*pfErrorCode*|错误|说明|  
|---------------------|-----------|-----------------|  
|ODBC_ERROR_GENERAL_ERR|常规安装程序错误|出现错误，但没有特定的安装程序错误。|  
|ODBC_ERROR_INVALID_DSN|DSN 无效|*LpszDSN*参数包含对于 DSN 无效的字符串。|  
|ODBC_ERROR_INVALID_NAME|无效的驱动程序或转换器名称|*LpszDriver*参数无效。|  
|ODBC_ERROR_REQUEST_FAILED|申请失败。|安装程序无法在注册表中创建 DSN。|  
|ODBC_ERROR_OUT_OF_MEM|内存不足|由于内存不足，安装程序无法执行此功能。|  
  
## <a name="comments"></a>说明  
 **SQLWriteDSNToIni**将数据源添加到系统信息的 [ODBC 数据源] 部分。 然后，它为数据源创建规范部分，并添加一个关键字（**driver**），其中包含驱动程序 DLL 的名称作为其值。 如果 "数据源规范" 部分已存在，则**SQLWriteDSNToIni**会在创建新节之前删除旧部分。  
  
 此函数的调用方必须将所有特定于驱动程序的关键字和值添加到系统信息的 "数据源规范" 部分。  
  
 如果数据源的名称为默认值，则**SQLWriteDSNToIni**还会在系统信息中创建默认的驱动程序规范部分。  
  
 只应从安装程序 DLL 调用此函数。  
  
## <a name="related-functions"></a>相关函数  
  
|有关以下方面的信息|查看|  
|---------------------------|---------|  
|添加、修改或删除数据源|[ConfigDSN](../../../odbc/reference/syntax/configdsn-function.md)（在安装程序 DLL 中）|  
|添加、修改或删除数据源|[SQLConfigDataSource](../../../odbc/reference/syntax/sqlconfigdatasource-function.md)|  
|从系统信息中删除数据源名称|[SQLRemoveDSNFromIni](../../../odbc/reference/syntax/sqlremovedsnfromini-function.md)|
