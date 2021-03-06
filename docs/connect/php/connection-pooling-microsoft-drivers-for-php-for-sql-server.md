---
title: 连接池 (Microsoft Drivers for PHP for SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 08/01/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- connection pooling support
ms.assetid: 4d9a83d4-08de-43a1-975c-0a94005edc94
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 714a3436cc79f3568e14c5e2609e16fd408f288e
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "80900983"
---
# <a name="connection-pooling-microsoft-drivers-for-php-for-sql-server"></a>连接池 (Microsoft Drivers for PHP for SQL Server)
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

有关 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]中的连接池，需要注意以下要点：  
  
-   [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] 使用 ODBC 连接池。  
  
-   默认情况下，连接池在 Windows 中处于启用状态。 在 Linux 和 macOS 中，只有在为 ODBC 启用了连接池的情况下才会将连接入池（请参阅[启用/禁用连接池](#enablingdisabling-connection-pooling)）。 启用连接池并连接到服务器时，驱动程序会在创建新的连接之前尝试使用已入池的连接。 如果在池中未找到等效连接，将创建新的连接，并将其添加到该池中。 该驱动程序将基于连接字符串的比较结果确定连接是否等效。  
  
-   当使用池中的某个连接时，会重置该连接状态。  
  
-   关闭连接会将该连接返回到池。  
  
若要详细了解连接池，请参阅[驱动程序管理器连接池](../../odbc/reference/develop-app/driver-manager-connection-pooling.md)。  
  
## <a name="enablingdisabling-connection-pooling"></a>启用/禁用连接池
### <a name="windows"></a>Windows
可以将连接字符串中的 ConnectionPooling  属性值设置为 false  或 0，强制驱动程序新建连接，而不是在连接池中查找等效连接。  
  
如果在连接字符串中省略了 ConnectionPooling  属性，或将此属性值设置为 true  或 1，那么仅当连接池中没有等效连接时，驱动程序才会新建连接。  
  
有关其他连接属性的信息，请参阅 [Connection Options](../../connect/php/connection-options.md)。  
### <a name="linux-and-macos"></a>Linux 和 macOS
不能使用 ConnectionPooling  属性来启用/禁用连接池。 

可以通过编辑 odbcinst.ini 配置文件来启用/禁用连接池。 应重新加载驱动程序，使更改生效。

将 `Pooling` 设置为 `Yes`，并且在 odbcinst.ini 文件中设置一个正 `CPTimeout` 值后，将启用连接池。 
```
[ODBC]
Pooling=Yes

[ODBC Driver 13 for SQL Server]
CPTimeout=<int value>
```
  
odbcinst.ini 文件至少应类似于以下示例：

```
[ODBC]
Pooling=Yes

[ODBC Driver 13 for SQL Server]
Description=Microsoft ODBC Driver 13 for SQL Server
Driver=/opt/microsoft/msodbcsql/lib64/libmsodbcsql-13.1.so.3.0
UsageCount=1
CPTimeout=120
```

将 odbcinst.ini 文件中的 `Pooling` 设置为 `No` 会强制使程序创建一个新连接。
```
[ODBC]
Pooling=No
```

## <a name="remarks"></a>备注
- 在 Linux 或 macOS 中，如果在 odbcinst.ini 文件中启用池，则所有连接都将入池。 这意味着 ConnectionPooling 连接选项不起作用。 若要禁用池，请在 odbcinst.ini 文件中设置 Pooling=No，并重新加载驱动程序。
  - unixODBC <= 2.3.4（Linux 和 macOS）可能不会返回正确的诊断信息，例如错误消息、警告和信息性消息
  - 出于此原因，SQLSRV 和 PDO_SQLSRV 驱动程序可能无法正确地提取 long 型数据（如 xml 数据、二进制数据）作为字符串。 作为一种解决方法，可以提取 long 型数据作为数据流。 请参阅 SQLSRV 的以下示例。

```
<?php
$connectionInfo = array("Database"=>"test", "UID"=>"username", "PWD"=>"password");

$conn1 = sqlsrv_connect("servername", $connectionInfo);

$longSample = str_repeat("a", 8500);
$xml1 = 
'<ParentXMLTag>
  <ChildTag01>'.$longSample.'</ChildTag01>
</ParentXMLTag>';

// Create table and insert xml string into it
sqlsrv_query($conn1, "CREATE TABLE xml_table (field xml)");
sqlsrv_query($conn1, "INSERT into xml_table values ('$xml1')");

// retrieve the inserted xml
$column1 = getColumn($conn1);

// return the connection to the pool
sqlsrv_close($conn1);

// This connection is from the pool
$conn2 = sqlsrv_connect("servername", $connectionInfo);
$column2 = getColumn($conn2);

sqlsrv_query($conn2, "DROP TABLE xml_table");
sqlsrv_close($conn2);

function getColumn($conn)
{
    $tsql = "SELECT * from xml_table";
    $stmt = sqlsrv_query($conn, $tsql);
    sqlsrv_fetch($stmt);
    // This might fail in Linux and macOS
    // $column = sqlsrv_get_field($stmt, 0, SQLSRV_PHPTYPE_STRING(SQLSRV_ENC_CHAR));
    // The workaround is to fetch it as a stream
    $column = sqlsrv_get_field($stmt, 0, SQLSRV_PHPTYPE_STREAM(SQLSRV_ENC_CHAR));
    sqlsrv_free_stmt($stmt);
    return ($column);
}
?>
```


## <a name="see-also"></a>另请参阅  
[如何：使用 Windows 身份验证进行连接](../../connect/php/how-to-connect-using-windows-authentication.md)

[如何：使用 SQL Server 身份验证进行连接](../../connect/php/how-to-connect-using-sql-server-authentication.md)  
  
