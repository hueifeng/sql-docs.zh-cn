---
title: setLoginTimeout 方法 (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.setLoginTimeout
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b63d1cf4-dc1b-4e35-9a56-50436642eaaf
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 83d6869075e296465ee9c60b0c5032407d4fe2da
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "80925756"
---
# <a name="setlogintimeout-method-sqlserverdatasource"></a>setLoginTimeout 方法 (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  设置此 [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md) 对象在尝试建立连接时将等待的秒数。  
  
## <a name="syntax"></a>语法  
  
```  
  
public void setLoginTimeout(int loginTimeout)  
```  
  
#### <a name="parameters"></a>parameters  
 *loginTimeout*  
  
 一个表示要等待的秒数的 int  值。 零表示该超时为默认系统超时，默认情况下指定为 15 秒。  
  
## <a name="remarks"></a>备注  
 此 setLoginTimeout 方法是由 javax.sql.DataSource 接口中的 setLoginTimeout 方法指定的。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerDataSource 成员](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 类](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
