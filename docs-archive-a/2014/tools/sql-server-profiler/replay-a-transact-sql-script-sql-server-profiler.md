---
title: Reproduzir um Script Transact-SQL (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- scripts [SQL Server], traces
- replaying traces
ms.assetid: 9c0eb222-e6e3-4bc1-a25f-a41e962d361b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5abf22a1201ac927f12ef9e4cfdd1f6d3026d00a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683836"
---
# <a name="replay-a-transact-sql-script-sql-server-profiler"></a><span data-ttu-id="7fa58-102">Repetir um script Transact-SQL (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="7fa58-102">Replay a Transact-SQL Script (SQL Server Profiler)</span></span>
  <span data-ttu-id="7fa58-103">Ao testar possíveis soluções para um problema de desempenho, use o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para repetir scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] e compare o desempenho antes e depois das alterações.</span><span class="sxs-lookup"><span data-stu-id="7fa58-103">When you test possible solutions to a performance problem, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to replay [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, and compare performance before and after your changes.</span></span>  
  
### <a name="to-replay-a-transact-sql-script"></a><span data-ttu-id="7fa58-104">Para repetir um script Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7fa58-104">To replay a Transact-SQL script</span></span>  
  
1.  <span data-ttu-id="7fa58-105">No menu **Arquivo** , aponte para **Abrir**e clique em **Arquivo de Script**.</span><span class="sxs-lookup"><span data-stu-id="7fa58-105">On the **File** menu, point to **Open**, and then click **Script File**.</span></span>  
  
2.  <span data-ttu-id="7fa58-106">Selecione o arquivo de script [!INCLUDE[tsql](../../includes/tsql-md.md)] que deseja abrir.</span><span class="sxs-lookup"><span data-stu-id="7fa58-106">Select the [!INCLUDE[tsql](../../includes/tsql-md.md)] script file you want to open.</span></span> <span data-ttu-id="7fa58-107">Certifique-se de que o script [!INCLUDE[tsql](../../includes/tsql-md.md)] contenha os eventos necessários para a repetição.</span><span class="sxs-lookup"><span data-stu-id="7fa58-107">Make sure that the [!INCLUDE[tsql](../../includes/tsql-md.md)] script contains events necessary for replay.</span></span> <span data-ttu-id="7fa58-108">Para obter mais informações, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fa58-108">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
3.  <span data-ttu-id="7fa58-109">No menu **Repetir** , clique em **Iniciar**e conecte-se ao servidor em que deseja repetir o script.</span><span class="sxs-lookup"><span data-stu-id="7fa58-109">On the **Replay** menu, click **Start**, and connect to the server where you want to replay the script.</span></span>  
  
4.  <span data-ttu-id="7fa58-110">Na caixa de diálogo **Configuração de Repetição** , verifique as definições e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7fa58-110">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa58-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7fa58-111">See Also</span></span>  
 <span data-ttu-id="7fa58-112">[Repetir rastreamentos](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="7fa58-112">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="7fa58-113">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="7fa58-113">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
