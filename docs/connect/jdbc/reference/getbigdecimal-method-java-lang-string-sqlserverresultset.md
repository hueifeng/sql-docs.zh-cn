---
title: getBigDecimal 方法 (java.lang.String) (SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.getBigDecimal (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b0ded929-d5f5-4573-bf75-ce5bd32328a5
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 5942987ca612dfe272ecf8cdfb5d1830973e645f
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "80920590"
---
# <a name="getbigdecimal-method-javalangstring-sqlserverresultset"></a>getBigDecimal 方法 (java.lang.String) (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索此 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 对象的当前行中指定列名称作为具有全精度 java.math.BigDecimal 的值。  
  
## <a name="syntax"></a>语法  
  
```  
  
public java.math.BigDecimal getBigDecimal(java.lang.String columnName)  
```  
  
#### <a name="parameters"></a>parameters  
 *columnName*  
  
 一个包含列名的字符串  。  
  
## <a name="return-value"></a>返回值  
 BigDecimal 对象。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>备注  
 此 getBigDecimal 方法是由 java.sql.ResultSet 接口中的 getBigDecimal 方法指定的。  
  
## <a name="see-also"></a>另请参阅  
 [getBigDecimal 方法 (SQLServerResultSet)](../../../connect/jdbc/reference/getbigdecimal-method-sqlserverresultset.md)   
 [SQLServerResultSet 成员](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 类](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
