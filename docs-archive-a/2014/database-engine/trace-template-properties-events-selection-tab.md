---
title: Propriedades do modelo de rastreamento (guia Seleção de eventos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.tracetemplateproperties.eventsselection.f1
helpviewer_keywords:
- Trace Template Properties dialog box
ms.assetid: 5b202457-ab42-4902-8012-7f3f40aa09f5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: da497db6e9373c63836753dc2be96deb3ce90244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684850"
---
# <a name="trace-template-properties-events-selection-tab"></a><span data-ttu-id="c0d14-102">Propriedades do Modelo de Rastreamento (guia Seleção de Eventos)</span><span class="sxs-lookup"><span data-stu-id="c0d14-102">Trace Template Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="c0d14-103">Use a guia **Seleção de Eventos** da caixa de diálogo **Propriedades do Modelo de Rastreamento** para exibir, editar ou especificar classes de evento e colunas de dados para incluir um modelo de rastreamento do [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0d14-103">Use the **Events Selection** tab of the **Trace Template Properties** dialog box to view, edit, or specify event classes and data columns to include in a [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace template.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0d14-104">Opções</span><span class="sxs-lookup"><span data-stu-id="c0d14-104">Options</span></span>  
 <span data-ttu-id="c0d14-105">Coluna**Eventos**</span><span class="sxs-lookup"><span data-stu-id="c0d14-105">**Events** column</span></span>  
 <span data-ttu-id="c0d14-106">Especifique os eventos que devem ser rastreados selecionando ou desmarcando a caixa de seleção na coluna Eventos.</span><span class="sxs-lookup"><span data-stu-id="c0d14-106">Specify events that should be traced by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="c0d14-107">Os eventos são organizados por categoria de evento.</span><span class="sxs-lookup"><span data-stu-id="c0d14-107">Events are organized by event category.</span></span>  
  
 <span data-ttu-id="c0d14-108">Se você selecionou **Basear novo modelo no existente** na guia **Geral** , os eventos serão selecionados automaticamente de acordo com o modelo especificado.</span><span class="sxs-lookup"><span data-stu-id="c0d14-108">If you selected **Base new template on existing one** on the **General** tab, events are automatically selected according to the specified template.</span></span> <span data-ttu-id="c0d14-109">Para obter mais informações sobre classes de evento, consulte [Referência de classe de evento do SQL Server](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c0d14-109">For more information about event classes, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="c0d14-110">Colunas de dados</span><span class="sxs-lookup"><span data-stu-id="c0d14-110">Data columns</span></span>  
 <span data-ttu-id="c0d14-111">Especifique as colunas de dados que devem ser rastreadas marcando a caixa que corresponde ao evento e a coluna de dados que você precisa.</span><span class="sxs-lookup"><span data-stu-id="c0d14-111">Specify data columns that should be traced by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="c0d14-112">Todas as colunas de evento pertinentes serão selecionadas por padrão para cada evento incluído no rastreamento, se a caixa de seleção correspondente ao evento estiver marcada.</span><span class="sxs-lookup"><span data-stu-id="c0d14-112">All relevant event columns are checked by default for each event included in the trace, if the checkbox corresponding to the event is checked.</span></span> <span data-ttu-id="c0d14-113">Se você selecionou **Basear novo modelo no existente** na guia **Geral** , as colunas de dados e os filtros serão selecionados automaticamente de acordo com o modelo especificado.</span><span class="sxs-lookup"><span data-stu-id="c0d14-113">If you checked **Base new template on existing one** on the **General** tab, data columns and filters are automatically selected according to the specified template.</span></span>  
  
 <span data-ttu-id="c0d14-114">Especifique os filtros clicando no cabeçalho da coluna de dados e digitando os critérios de filtro.</span><span class="sxs-lookup"><span data-stu-id="c0d14-114">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="c0d14-115">As colunas de dados filtrados são indicadas por um ícone de filtro à esquerda do rótulo da coluna na caixa de diálogo **Editar Filtro** .</span><span class="sxs-lookup"><span data-stu-id="c0d14-115">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span>  
  
 <span data-ttu-id="c0d14-116">**Mostrar todos os eventos**</span><span class="sxs-lookup"><span data-stu-id="c0d14-116">**Show all events**</span></span>  
 <span data-ttu-id="c0d14-117">Mostra todos os eventos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c0d14-117">Show all available events.</span></span> <span data-ttu-id="c0d14-118">Essa opção será selecionada por padrão se você estiver criando um novo modelo que não seja baseado em um modelo existente.</span><span class="sxs-lookup"><span data-stu-id="c0d14-118">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="c0d14-119">Desmarque para ocultar todos os eventos não selecionados na grade **Seleção de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="c0d14-119">Uncheck to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="c0d14-120">**Mostrar todas as colunas**</span><span class="sxs-lookup"><span data-stu-id="c0d14-120">**Show all columns**</span></span>  
 <span data-ttu-id="c0d14-121">Mostra todas as colunas de dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c0d14-121">Show all available data columns.</span></span> <span data-ttu-id="c0d14-122">Essa opção será selecionada por padrão se você estiver criando um novo modelo que não seja baseado em um modelo existente.</span><span class="sxs-lookup"><span data-stu-id="c0d14-122">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="c0d14-123">Desmarque para ocultar todas as colunas de dados não selecionadas na guia **Seleção de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="c0d14-123">Uncheck to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="c0d14-124">**Filtros de coluna**</span><span class="sxs-lookup"><span data-stu-id="c0d14-124">**Column Filters**</span></span>  
 <span data-ttu-id="c0d14-125">Inicia a caixa de diálogo **Editar Filtro**, que exibe um ícone de filtro à esquerda do rótulo da coluna de dados.</span><span class="sxs-lookup"><span data-stu-id="c0d14-125">Launches the **Edit Filter** dialog box, which displays a filter icon to the left of the data column label.</span></span> <span data-ttu-id="c0d14-126">Use a caixa de diálogo **Editar Filtro** para editar filtros de coluna de dados.</span><span class="sxs-lookup"><span data-stu-id="c0d14-126">Use the **Edit Filter** dialog box to edit data column filters.</span></span>  
  
 <span data-ttu-id="c0d14-127">**Organizar colunas**</span><span class="sxs-lookup"><span data-stu-id="c0d14-127">**Organize Columns**</span></span>  
 <span data-ttu-id="c0d14-128">Altera a ordem das colunas no rastreamento e agrupa os resultados em uma ou mais colunas.</span><span class="sxs-lookup"><span data-stu-id="c0d14-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d14-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0d14-129">See Also</span></span>  
 <span data-ttu-id="c0d14-130">[Especificar eventos e colunas de dados para um arquivo de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c0d14-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c0d14-131">[Organizar colunas exibidas em um &#40;de rastreamento SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c0d14-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c0d14-132">[Filtrar eventos em um &#40;de rastreamento SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c0d14-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c0d14-133">[Exibir informações de filtro &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c0d14-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c0d14-134">[Modificar um filtro &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c0d14-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c0d14-135">[Modelos e permissões do SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="c0d14-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="c0d14-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c0d14-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
