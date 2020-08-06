---
title: Pausar um rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- pausing traces
- temporarily stopping traces
- traces [SQL Server], pausing
- stopping traces
ms.assetid: 432b9b0c-b5e7-47f3-a71b-310fb3bf2445
author: stevestein
ms.author: sstein
ms.openlocfilehash: cdc9dbbd01099b1d33787a72b0bd59b65cea722e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678400"
---
# <a name="pause-a-trace-sql-server-profiler"></a><span data-ttu-id="64566-102">Pausar um rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="64566-102">Pause a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="64566-103">Pausar um rastreamento impede que mais dados de eventos sejam capturados até que o rastreamento seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="64566-103">Pausing a trace prevents further event data from being captured until the trace is restarted.</span></span>  
  
 <span data-ttu-id="64566-104">Pausando um rastreamento, você impede que sejam capturados dados de eventos até que o rastreamento seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="64566-104">When you pause a trace, you prevent event data from being captured until the trace is restarted.</span></span> <span data-ttu-id="64566-105">Reiniciar um rastreamento permite que as operações de rastreamento sejam retomadas.</span><span class="sxs-lookup"><span data-stu-id="64566-105">Restarting a trace lets trace operations resume.</span></span> <span data-ttu-id="64566-106">Nenhum dado capturado anteriormente é perdido após o reinício.</span><span class="sxs-lookup"><span data-stu-id="64566-106">No previously captured data is lost after a restart.</span></span> <span data-ttu-id="64566-107">Quando o rastreamento é reiniciado, a captura de dados é retomada daquele ponto em diante.</span><span class="sxs-lookup"><span data-stu-id="64566-107">When the trace is restarted, data capturing resumes from that point onward.</span></span> <span data-ttu-id="64566-108">Enquanto um rastreamento está pausado, você pode alterar o nome, os eventos, as colunas e os filtros.</span><span class="sxs-lookup"><span data-stu-id="64566-108">While a trace is paused, you can change the name, events, columns, and filters.</span></span> <span data-ttu-id="64566-109">Porém, você não pode alterar os destinos para os quais estão sendo enviados os dados de rastreamento, nem a conexão do servidor.</span><span class="sxs-lookup"><span data-stu-id="64566-109">However, you cannot change the destinations to which you are sending the trace data, nor change the server connection.</span></span>  
  
### <a name="to-pause-a-trace"></a><span data-ttu-id="64566-110">Para pausar um rastreamento</span><span class="sxs-lookup"><span data-stu-id="64566-110">To pause a trace</span></span>  
  
1.  <span data-ttu-id="64566-111">Selecione uma janela que contenha um rastreamento em execução.</span><span class="sxs-lookup"><span data-stu-id="64566-111">Select a window that contains a running trace.</span></span>  
  
2.  <span data-ttu-id="64566-112">No menu **Arquivo** , clique em **Pausar Rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="64566-112">On the **File** menu, click **Pause Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64566-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="64566-113">See Also</span></span>  
 [<span data-ttu-id="64566-114">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="64566-114">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
