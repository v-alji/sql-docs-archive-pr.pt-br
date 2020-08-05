---
title: Especificar eventos e colunas de dados para um arquivo de rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- adding events
- traces [SQL Server], data columns
- deleting events
- removing events
- traces [SQL Server], events
ms.assetid: 7da715a3-2f03-4063-b6a4-20fd7b44e675
author: stevestein
ms.author: sstein
ms.openlocfilehash: ffb8639a187f1e7e091e382031886659bd47d7d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568270"
---
# <a name="specify-events-and-data-columns-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="678cf-102">Especificar eventos e colunas de dados para um arquivo de rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="678cf-102">Specify Events and Data Columns for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="678cf-103">Este tópico descreve como especificar classes de evento e colunas de dados para rastreamentos usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="678cf-103">This topic describes how to specify event classes and data columns for traces by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-specify-events-and-data-columns-for-a-trace"></a><span data-ttu-id="678cf-104">Para especificar eventos e colunas de dados para um rastreamento</span><span class="sxs-lookup"><span data-stu-id="678cf-104">To specify events and data columns for a trace</span></span>  
  
1.  <span data-ttu-id="678cf-105">Na caixa de diálogo **Propriedades do Rastreamento** ou **Propriedades do Modelo de Rastreamento** , clique na guia **Seleção de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="678cf-105">On the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="678cf-106">A guia **Seleção de Eventos** contém um controle de grade.</span><span class="sxs-lookup"><span data-stu-id="678cf-106">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="678cf-107">O controle de grade é uma tabela que contém cada uma das classes de evento rastreáveis.</span><span class="sxs-lookup"><span data-stu-id="678cf-107">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="678cf-108">A tabela contém uma linha para cada classe de evento.</span><span class="sxs-lookup"><span data-stu-id="678cf-108">The table contains one row for each event class.</span></span> <span data-ttu-id="678cf-109">As classes de evento podem diferir ligeiramente, dependendo do tipo e versão de servidor com o qual você está conectado.</span><span class="sxs-lookup"><span data-stu-id="678cf-109">The event classes can differ slightly depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="678cf-110">As classes de evento são identificadas na coluna **Events**da grade e são agrupadas por categoria de evento.</span><span class="sxs-lookup"><span data-stu-id="678cf-110">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="678cf-111">As colunas restantes listam as colunas de dados que podem ser retornadas para cada classe de evento.</span><span class="sxs-lookup"><span data-stu-id="678cf-111">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="678cf-112">Na guia **Seleção de Eventos**, use o controle da grade para adicionar ou remover eventos e colunas de dados do arquivo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="678cf-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file.</span></span>  
  
3.  <span data-ttu-id="678cf-113">Para remover eventos do rastreamento, desmarque a caixa de seleção na coluna **Eventos** para cada classe de evento.</span><span class="sxs-lookup"><span data-stu-id="678cf-113">To remove events from the trace, clear the check box in the **Events** column for each event class.</span></span>  
  
4.  <span data-ttu-id="678cf-114">Para incluir eventos em um rastreamento, marque a caixa de seleção na coluna **Eventos** para cada classe de evento ou marque uma coluna de dados que corresponda a um evento.</span><span class="sxs-lookup"><span data-stu-id="678cf-114">To include events in a trace, check the box in the **Events** column for each event class, or check a data column that corresponds to an event.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="678cf-115">Se o rastreamento precisar ser correlacionado com os dados do Monitor do Sistema ou do Monitor de Desempenho, as colunas **Start Time** e **End Time** devem ser incluídas no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="678cf-115">If the trace is going be correlated with System Monitor or Performance Monitor data, both **Start Time** and **End Time** data columns must be included in the trace.</span></span>  
  
 <span data-ttu-id="678cf-116">Quando uma classe de evento é incluída, todas as colunas de dados associadas a ela também serão incluídas no rastreamento, se você tiver marcado a caixa correspondente a um evento.</span><span class="sxs-lookup"><span data-stu-id="678cf-116">When you include an event class, every associated data column is also included to the trace, if you have checked the box corresponding to an event.</span></span> <span data-ttu-id="678cf-117">Caso tenha marcado a caixa para uma coluna em particular, somente essa coluna será incluída no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="678cf-117">If you checked the box for a particular column, only that column is included in the trace.</span></span>  
  
1.  <span data-ttu-id="678cf-118">Para remover colunas de dados de uma classe de evento, desmarque as caixas de seleção da coluna de dados na linha de classe de evento ou clique com o botão direito do mouse no cabeçalho de coluna e selecione a opção **Desmarcar seleção de coluna** .</span><span class="sxs-lookup"><span data-stu-id="678cf-118">To remove data columns from an event class, clear the check boxes from the data column in the event class row, or right-click on the column header and select the **Deselect column** option.</span></span>  
  
2.  <span data-ttu-id="678cf-119">Outra alternativa é aplicar filtros ao rastreamento.</span><span class="sxs-lookup"><span data-stu-id="678cf-119">Optionally, apply filters to the trace.</span></span> <span data-ttu-id="678cf-120">Para obter mais informações, veja [Filtrar eventos em um rastreamento &#40;SQL Server Profiler&#41;](filter-events-in-a-trace-sql-server-profiler.md)</span><span class="sxs-lookup"><span data-stu-id="678cf-120">For more information, see [Filter Events in a Trace &#40;SQL Server Profiler&#41;](filter-events-in-a-trace-sql-server-profiler.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="678cf-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="678cf-121">See Also</span></span>  
 [<span data-ttu-id="678cf-122">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="678cf-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
