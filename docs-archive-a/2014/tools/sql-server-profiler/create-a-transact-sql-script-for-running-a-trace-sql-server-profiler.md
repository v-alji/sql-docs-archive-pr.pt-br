---
title: Criar um script Transact-SQL para executar um rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], running
- scripts [SQL Server], traces
ms.assetid: 6b0e2519-998d-40d5-b8ba-5e6a773f91a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3d4b4bebb2a3e05e3de12e59c53ccca9c980afd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678404"
---
# <a name="create-a-transact-sql-script-for-running-a-trace-sql-server-profiler"></a><span data-ttu-id="81a3e-102">Criar um script Transact-SQL para executar um rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="81a3e-102">Create a Transact-SQL Script for Running a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="81a3e-103">Este tópico descreve como criar um script Transact-SQL a partir de um arquivo ou tabela de rastreamento existente, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81a3e-103">This topic describes how to create a Transact-SQL script from an existing trace file or table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-create-a-transact-sql-script-to-run-a-trace"></a><span data-ttu-id="81a3e-104">Para criar um script Transact-SQL para executar um rastreamento</span><span class="sxs-lookup"><span data-stu-id="81a3e-104">To create a Transact-SQL script to run a trace</span></span>  
  
1.  <span data-ttu-id="81a3e-105">Abra um arquivo ou tabela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="81a3e-105">Open a trace file or table.</span></span> <span data-ttu-id="81a3e-106">Para obter mais informações, consulte [Abrir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) ou do [Abrir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="81a3e-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
2.  <span data-ttu-id="81a3e-107">No menu**Arquivo**, aponte para **Exportar**, **Definição de Rastreamento do Script**e clique na versão correspondente ao servidor que você deseja rastrear.</span><span class="sxs-lookup"><span data-stu-id="81a3e-107">On the**File**menu, point to **Export**, point to **Script Trace Definition**, and then click the version that corresponds to the server you want to trace.</span></span>  
  
3.  <span data-ttu-id="81a3e-108">Na caixa de diálogo **Salvar como** , digite um nome para o arquivo de script e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="81a3e-108">In the **Save As** dialog box, enter a name for the script file, and then click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81a3e-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81a3e-109">See Also</span></span>  
 <span data-ttu-id="81a3e-110">[Modelos e permissões do SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="81a3e-110">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="81a3e-111">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="81a3e-111">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
