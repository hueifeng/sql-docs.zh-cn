---
title: setSQLXML 方法 (SQLServerCallableStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: de095cb3-1111-4154-8996-3c2e529e3000
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 82e8d1507760591b4e019d5d785eb0cc6a93c3ac
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "80924917"
---
# <a name="setsqlxml-method-sqlservercallablestatement"></a>setSQLXML 方法 (SQLServerCallableStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  将指定参数设置为指定的 SQLXML 对象。  
  
## <a name="syntax"></a>语法  
  
```  
  
public final void setSQLXML(java.lang.String parameterName,  
                            java.sql.SQLXML xmlObject)  
```  
  
#### <a name="parameters"></a>parameters  
 parameterName   
  
 指示参数名称的 String  。  
  
 xmlObject   
  
 包含参数值的 SQLXML 对象。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>备注  
 此 setSQLXML 方法是由 java.sql.CallableStatement 接口中的 setSQLXML 方法指定的。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerCallableStatement 成员](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
