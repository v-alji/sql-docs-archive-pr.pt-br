---
title: Filtrar eventos em um rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 0fd63573-3b35-4f67-9e1e-ed9aabee11a8
author: stevestein
ms.author: sstein
ms.openlocfilehash: fef9dd6956d407011261c54f796a751a0bf94941
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684430"
---
# <a name="filter-events-in-a-trace-sql-server-profiler"></a><span data-ttu-id="c0a57-102">Filtrar eventos em um rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="c0a57-102">Filter Events in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="c0a57-103">Os filtros limitam os eventos coletados em um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c0a57-103">Filters limit the events collected in a trace.</span></span> <span data-ttu-id="c0a57-104">Se não houver um filtro definido, serão retornados todos os eventos das classes de evento selecionadas na saída do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c0a57-104">If a filter is not set, all events of the selected event classes are returned in the trace output.</span></span> <span data-ttu-id="c0a57-105">Não é obrigatório definir um filtro para um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c0a57-105">It is not mandatory to set a filter for a trace.</span></span> <span data-ttu-id="c0a57-106">Porém, um filtro minimiza a sobrecarga incorrida durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c0a57-106">However, a filter minimizes the overhead that is incurred during tracing.</span></span>  
  
 <span data-ttu-id="c0a57-107">Os filtros são adicionados às definições de rastreamento por meio da guia **Seleção de Eventos** da caixa de diálogo **Propriedades do Rastreamento** ou **Propriedades do Modelo de Rastreamento** .</span><span class="sxs-lookup"><span data-stu-id="c0a57-107">You add filters to trace definitions by using the **Events Selection** tab of the **Trace Properties** or **Trace Template Properties** dialog box.</span></span>  
  
### <a name="to-filter-events-in-a-trace"></a><span data-ttu-id="c0a57-108">Para filtrar eventos em um rastreamento</span><span class="sxs-lookup"><span data-stu-id="c0a57-108">To filter events in a trace</span></span>  
  
1.  <span data-ttu-id="c0a57-109">Na caixa de diálogo **Propriedades do Rastreamento** ou **Propriedades do Modelo de Rastreamento** , clique na guia **Seleção de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="c0a57-109">In the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="c0a57-110">A guia **Seleção de Eventos** contém um controle de grade.</span><span class="sxs-lookup"><span data-stu-id="c0a57-110">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="c0a57-111">O controle de grade é uma tabela que contém cada uma das classes de evento rastreáveis.</span><span class="sxs-lookup"><span data-stu-id="c0a57-111">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="c0a57-112">A tabela contém uma linha para cada classe de evento.</span><span class="sxs-lookup"><span data-stu-id="c0a57-112">The table contains one row for each event class.</span></span> <span data-ttu-id="c0a57-113">As classes de evento podem diferir ligeiramente, dependendo do tipo e versão de servidor com o qual você está conectado.</span><span class="sxs-lookup"><span data-stu-id="c0a57-113">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="c0a57-114">As classes de evento são identificadas na coluna **Events**da grade e são agrupadas por categoria de evento.</span><span class="sxs-lookup"><span data-stu-id="c0a57-114">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="c0a57-115">As colunas restantes listam as colunas de dados que podem ser retornadas para cada classe de evento.</span><span class="sxs-lookup"><span data-stu-id="c0a57-115">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="c0a57-116">Clique em **Filtros de Coluna.**</span><span class="sxs-lookup"><span data-stu-id="c0a57-116">Click **Column Filters.**</span></span>  
  
     <span data-ttu-id="c0a57-117">A caixa de diálogo **Editar Filtro**é exibida.</span><span class="sxs-lookup"><span data-stu-id="c0a57-117">The **Edit Filter**dialog box appears.</span></span> <span data-ttu-id="c0a57-118">A caixa de diálogo **Editar Filtro**contém uma lista de operadores de comparação que podem ser usados para filtrar eventos em um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="c0a57-118">The **Edit Filter**dialog box contains a list of comparison operators that you can use to filter events in a trace.</span></span>  
  
3.  <span data-ttu-id="c0a57-119">Para aplicar um filtro, clique no operador de comparação e digite um valor a usar para o filtro.</span><span class="sxs-lookup"><span data-stu-id="c0a57-119">To apply a filter, click the comparison operator, and type a value to use for the filter.</span></span>  
  
4.  <span data-ttu-id="c0a57-120">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0a57-120">Click **OK**.</span></span>  
  
 <span data-ttu-id="c0a57-121">**Considerações:**</span><span class="sxs-lookup"><span data-stu-id="c0a57-121">**Considerations:**</span></span>  
  
-   <span data-ttu-id="c0a57-122">Se definir condições de filtro nas colunas de dados **StartTime** e **EndTime** da guia Seleção de Eventos, verifique se:</span><span class="sxs-lookup"><span data-stu-id="c0a57-122">If you set filter conditions on the **StartTime** and **EndTime** data columns of the Events Selection tab, then make sure that:</span></span>  
  
    -   <span data-ttu-id="c0a57-123">A data inserida corresponda a este formato: `YYYY/MM/DD HH:mm:sec`.</span><span class="sxs-lookup"><span data-stu-id="c0a57-123">The date you enter matches this format: `YYYY/MM/DD HH:mm:sec`.</span></span>  
  
         <span data-ttu-id="c0a57-124">-OU-</span><span class="sxs-lookup"><span data-stu-id="c0a57-124">-OR-</span></span>  
  
    -   <span data-ttu-id="c0a57-125">**Usar configurações regionais para exibir valores de data e hora** está marcado na caixa de diálogo **Opções Gerais** .</span><span class="sxs-lookup"><span data-stu-id="c0a57-125">**Use regional settings to display date and time values** is checked in the **General Options** dialog box.</span></span> <span data-ttu-id="c0a57-126">Para exibir a caixa de diálogo **Opções Gerais**, no menu [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Ferramentas**, clique em **Opção**.</span><span class="sxs-lookup"><span data-stu-id="c0a57-126">To view the **General Options** dialog box, on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Tools** menu, click **Option**.</span></span>  
  
         <span data-ttu-id="c0a57-127">-E-</span><span class="sxs-lookup"><span data-stu-id="c0a57-127">-AND-</span></span>  
  
    -   <span data-ttu-id="c0a57-128">A data inserida esteja entre 1° de janeiro de 1753 e 31 de dezembro de 9999.</span><span class="sxs-lookup"><span data-stu-id="c0a57-128">The date you enter is between January 1, 1753 and December 31, 9999.</span></span>  
  
-   <span data-ttu-id="c0a57-129">Se rastrear eventos do utilitário **osql** ou do utilitário **sqlcmd** , sempre acrescente **%** aos filtros na coluna de dados **TextData** .</span><span class="sxs-lookup"><span data-stu-id="c0a57-129">If tracing events from the **osql** utility or from the **sqlcmd** utility, always append **%** to filters on the **TextData** data column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0a57-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0a57-130">See Also</span></span>  
 [<span data-ttu-id="c0a57-131">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c0a57-131">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
