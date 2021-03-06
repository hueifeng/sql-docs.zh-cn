---
title: SQL Server dacpac 扩展
description: 安装和使用 Azure Data Studio 的 SQL Server dacpac 扩展
ms.custom: seodec18
ms.date: 11/04/2019
ms.reviewer: alayu, maghan, sstein
ms.prod: azure-data-studio
ms.technology: ''
ms.topic: conceptual
author: yualan
ms.author: alayu
ms.openlocfilehash: 2062c32f5af698f635abba684eb1ea1bbe59250b
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "85758331"
---
# <a name="sql-server-dacpac-extension"></a>SQL Server dacpac 扩展

“数据层应用程序向导”提供了一种易于使用的体验，可用于部署和提取 .dacpac 文件以及导入和导出 bacpac 文件   。


## <a name="features"></a>功能

* 将 dacpac 部署到 SQL Server 实例
* 将 SQL Server 实例提取到 dacpac
* 从 bacpac 创建数据库
* 将架构和数据导出到 bacpac

![dacpac 扩展演示 gif](media/extensions/sql-server-dacpac-extension/dacpac-extension-demo.gif)


## <a name="why-would-i-use-the-data-tier-application-wizard"></a>为什么要使用数据层应用程序向导？

通过该向导，可以更轻松地管理 dacpac 和 bacpac 文件，从而简化支持应用程序的数据层元素的开发和部署。 若要了解有关使用数据层应用程序的详细信息，[请查看我们的文档。](https://docs.microsoft.com/sql/relational-databases/data-tier-applications/data-tier-applications?view=sql-server-2017)


## <a name="install-the-extension"></a>安装扩展

1. 选择“扩展”图标以查看可用扩展。

    ![扩展管理器图标](media/extensions/extension-manager-icon.png)

2. 搜索“SQL Server dacpac”扩展并选择它以查看其详细信息  。 单击“安装”，以添加扩展  。

3. 安装后，重载以启用 Azure Data Studio 中的扩展（仅在第一次安装扩展时需要进行此操作）  。


## <a name="launch-the-data-tier-application-wizard"></a>启动数据层应用程序向导

若要启动该向导，请右键单击“数据库”文件夹，或右键单击对象资源管理器中的特定数据库。 然后，单击“数据层应用程序向导”  。

![dacpac 扩展启动菜单](media/extensions/sql-server-dacpac-extension/dacpac-extension-launch.png)


## <a name="next-steps"></a>后续步骤

若要了解有关 dacpac 的详细信息，[请查看我们的文档。](https://docs.microsoft.com/sql/relational-databases/data-tier-applications/data-tier-applications?view=sql-server-2017)
请在[此处](https://github.com/microsoft/azuredatastudio/issues)报告问题和提出功能请求。