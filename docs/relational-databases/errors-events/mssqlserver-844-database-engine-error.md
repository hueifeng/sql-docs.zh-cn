---
title: MSSQLSERVER_844 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 844 (Database Engine error)
ms.assetid: 2060c886-1226-4066-bc0c-de90a1cfb82b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bdc05bbc2cf4db3875149ed35ac82dd922800484
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "85767821"
---
# <a name="mssqlserver_844"></a>MSSQLSERVER_844
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>详细信息  
  
| Attribute | 值 |  
| :-------- | :---- |  
|产品名称|SQL Server|  
|事件 ID|844|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|BUFLATCH_TIMEOUT_CONTINUE|  
|消息正文|等待缓冲区闩锁时出现超时 - 类型 %d，bp %p，页 %d:%d，stat %#x，数据库 ID: %d，分配单元 ID: %I64d%ls，任务 0x%p : %d，等待时间 %d，标志 0x%I64x，所属任务 0x%p。  将继续等待。|  
  
## <a name="explanation"></a>说明  
进程正在等待获取闩锁。 此问题可能是由所用时间太长而无法完成的 I/O 操作导致的。 通常，此类型的错误是其他任务阻塞系统进程的结果。 在一些实例中，此错误可能是硬件故障引起的。  
  
## <a name="user-action"></a>用户操作  
尝试执行以下操作以防止出现此错误：  
  
-   减少工作负荷。  
  
-   在错误日志或事件日志中检查关联的 I/O 故障。 I/O 故障通常是指磁盘故障。  
  
-   检查错误日志以查找非生成任务和其他错误。  
  
-   如果频繁出现诸如断定之类的错误，请解决这些问题。  
  
如果错误仍存在，请与 Microsoft 客户服务与支持部门联系。  
  
