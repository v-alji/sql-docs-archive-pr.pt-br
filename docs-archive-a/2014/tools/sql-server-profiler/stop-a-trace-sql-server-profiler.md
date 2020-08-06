---
title: Parar um rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], stopping
- stopping traces
ms.assetid: 47c4f33d-63e0-4444-bec8-4c1c91f8e25c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 501ea4a4838f8e2ea42fc475c486466d48020a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681986"
---
# <a name="stop-a-trace-sql-server-profiler"></a><span data-ttu-id="a89a7-102">Interromper um rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="a89a7-102">Stop a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="a89a7-103">Este tópico descreve como interromper um rastreamento que está sendo executado, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a89a7-103">This topic describes how to stop a trace that is running by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="a89a7-104">Interromper um rastreamento impede que os dados sejam capturados.</span><span class="sxs-lookup"><span data-stu-id="a89a7-104">Stopping a trace stops data from being captured.</span></span> <span data-ttu-id="a89a7-105">Depois que um rastreamento é interrompido, ele não pode ser reiniciado sem a perda dos dados já capturados, a menos que eles se encontrem em um arquivo ou tabela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a89a7-105">After a trace is stopped, it cannot be restarted without losing previously captured data, unless the data has been captured to a trace file or trace table.</span></span> <span data-ttu-id="a89a7-106">Você também pode salvar os dados coletados em uma tabela ou arquivo após interromper o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="a89a7-106">You can also save the collected data to a table or file after stopping a trace.</span></span> <span data-ttu-id="a89a7-107">Todas as propriedades de rastreamento selecionadas anteriormente são preservadas quando um rastreamento é interrompido.</span><span class="sxs-lookup"><span data-stu-id="a89a7-107">All trace properties that were previously selected are preserved when a trace is stopped.</span></span> <span data-ttu-id="a89a7-108">Quando um rastreamento é interrompido, você pode alterar o nome, os eventos, as colunas e os filtros.</span><span class="sxs-lookup"><span data-stu-id="a89a7-108">When a trace is stopped, you can change the name, events, columns, and filters.</span></span>  
  
### <a name="to-stop-a-trace"></a><span data-ttu-id="a89a7-109">Para interromper um rastreamento</span><span class="sxs-lookup"><span data-stu-id="a89a7-109">To stop a trace</span></span>  
  
1.  <span data-ttu-id="a89a7-110">Selecione um rastreamento que esteja sendo executado.</span><span class="sxs-lookup"><span data-stu-id="a89a7-110">Select a trace that is running.</span></span>  
  
2.  <span data-ttu-id="a89a7-111">No menu **Arquivo** , clique em **Parar Rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="a89a7-111">On the **File** menu, click **Stop Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a89a7-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a89a7-112">See Also</span></span>  
 [<span data-ttu-id="a89a7-113">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="a89a7-113">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
