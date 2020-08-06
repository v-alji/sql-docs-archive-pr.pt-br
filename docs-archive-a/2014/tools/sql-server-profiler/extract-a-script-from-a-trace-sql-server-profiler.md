---
title: Extrair um script de um rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], traces
- extracting script from trace [SQL Server]
ms.assetid: 431126a6-ff91-4818-8763-4442152bd571
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6633fafb8a39b189093044ef39694afa601af7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678399"
---
# <a name="extract-a-script-from-a-trace-sql-server-profiler"></a><span data-ttu-id="c9116-102">Extrair um script de um rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="c9116-102">Extract a Script from a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="c9116-103">Este tópico descreve como extrair eventos [!INCLUDE[tsql](../../includes/tsql-md.md)] de um arquivo ou tabela de rastreamento e salvá-los em um arquivo de script [!INCLUDE[tsql](../../includes/tsql-md.md)] usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9116-103">This topic describes how to extract [!INCLUDE[tsql](../../includes/tsql-md.md)] events from a trace file or table and save them as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-extract-a-transact-sql-script-from-a-trace-file-or-table"></a><span data-ttu-id="c9116-104">Para extrair um script Transact-SQL de um arquivo ou tabela de rastreamento</span><span class="sxs-lookup"><span data-stu-id="c9116-104">To extract a Transact-SQL script from a trace file or table</span></span>  
  
1.  <span data-ttu-id="c9116-105">Abra o arquivo ou tabela de rastreamento que contém os eventos [!INCLUDE[tsql](../../includes/tsql-md.md)] que você deseja salvar em um arquivo de script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9116-105">Open a trace file or table that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] events that you want to save to a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="c9116-106">Para obter mais informações, consulte [Abrir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) ou do [Abrir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="c9116-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
2.  <span data-ttu-id="c9116-107">No menu **Arquivo** , aponte para **Exportar**, aponte para **Extrair Eventos do SQL Server**e clique em **Extrair Eventos Transact-SQL**.</span><span class="sxs-lookup"><span data-stu-id="c9116-107">On the **File** menu, point to **Export**, point to **Extract SQL Server Events**, and then click **Extract Transact-SQL Events**.</span></span>  
  
3.  <span data-ttu-id="c9116-108">Na caixa de diálogo **Salvar Como** , digite um nome para o arquivo [!INCLUDE[tsql](../../includes/tsql-md.md)] e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c9116-108">In the **Save As** dialog box, type a name for the [!INCLUDE[tsql](../../includes/tsql-md.md)] file, and click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9116-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c9116-109">See Also</span></span>  
 [<span data-ttu-id="c9116-110">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c9116-110">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
