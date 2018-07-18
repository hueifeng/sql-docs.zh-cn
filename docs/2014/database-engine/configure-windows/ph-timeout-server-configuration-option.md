---
title: PH timeout 服务器配置选项 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- time limit for protocol handler wait [SQL Server]
- timeout options [SQL Server], ph timeout option
- protocols [SQL Server], timing out
- ph timeout option
ms.assetid: ed19a07c-83fe-4582-9c9e-41b1ce571850
caps.latest.revision: 28
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: f0458fbfc8df8a2b662eb78131c43646f10618a4
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37171408"
---
# <a name="ph-timeout-server-configuration-option"></a>PH timeout 服务器配置选项
  使用 PH timeout 选项可以指定全文协议处理程序在超时前等待连接到数据库的时间（秒）。默认值为 60 秒。 如果连接尝试因临时的网络问题而超时，可以增加 ph timeout 值。  
  
 全文协议处理程序宿主在筛选器后台程序宿主中，用于从 SQL Server 中提取要进行全文索引的数据。 有关全文搜索组件的详细信息，请参阅 [全文搜索](../../relational-databases/search/full-text-search.md)。  
  
 尝试提取数据行时，如果协议处理程序无法在指定时间内连接到 SQL Server，它将为该行报告超时错误。 全文收集器稍后将重试该行。 有关全文收集器的详细信息，请参阅 [填充全文索引](../../relational-databases/indexes/indexes.md)。  
  
## <a name="see-also"></a>请参阅  
 [全文搜索](../../relational-databases/search/full-text-search.md)   
 [RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql)   
 [服务器配置选项 (SQL Server)](server-configuration-options-sql-server.md)   
 [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  