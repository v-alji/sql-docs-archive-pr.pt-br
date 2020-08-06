---
title: Propriedades de rastreamento (guia Seleção de eventos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.eventsselection.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: e1892f24-7272-4d5d-8926-6150cc82b2c3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11f4725865d39c21e36f5fd09eaf2afd4cde3017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681815"
---
# <a name="trace-properties-events-selection-tab"></a><span data-ttu-id="10efb-102">Propriedades do Rastreamento (guia Seleção de Eventos)</span><span class="sxs-lookup"><span data-stu-id="10efb-102">Trace Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="10efb-103">Use a guia **Seleção de Eventos** da caixa de diálogo **Propriedades do Rastreamento** para exibir ou especificar eventos do rastreamento e colunas de dados.</span><span class="sxs-lookup"><span data-stu-id="10efb-103">Use the **Events Selection** tab of the **Trace Properties** dialog box to view or specify traced events and data columns.</span></span>  
  
## <a name="options"></a><span data-ttu-id="10efb-104">Opções</span><span class="sxs-lookup"><span data-stu-id="10efb-104">Options</span></span>  
 <span data-ttu-id="10efb-105">Coluna**Eventos**</span><span class="sxs-lookup"><span data-stu-id="10efb-105">**Events** column</span></span>  
 <span data-ttu-id="10efb-106">Especifique os eventos do rastreamento marcando ou desmarcando a caixa de seleção na coluna de eventos.</span><span class="sxs-lookup"><span data-stu-id="10efb-106">Specify traced events by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="10efb-107">Os**Eventos** são organizados por categoria de evento.</span><span class="sxs-lookup"><span data-stu-id="10efb-107">**Events** are organized by event category.</span></span> <span data-ttu-id="10efb-108">As classes de evento especificadas no modelo são selecionadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="10efb-108">Event classes specified in the template are automatically selected.</span></span> <span data-ttu-id="10efb-109">Para obter mais informações, confira [Referência de classe de evento do SQL Server](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="10efb-109">For more information, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="10efb-110">Colunas de dados</span><span class="sxs-lookup"><span data-stu-id="10efb-110">Data columns</span></span>  
 <span data-ttu-id="10efb-111">Especifique as colunas de dados do rastreamento marcando a caixa correspondente ao evento e a coluna de dados necessária.</span><span class="sxs-lookup"><span data-stu-id="10efb-111">Specify traced data columns by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="10efb-112">Por padrão, todas as colunas de dados pertinentes são marcadas para cada evento incluído no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="10efb-112">All relevant event columns are checked by default for each event included in the trace.</span></span>  
  
 <span data-ttu-id="10efb-113">Especifique os filtros clicando no cabeçalho da coluna de dados e digitando os critérios de filtro.</span><span class="sxs-lookup"><span data-stu-id="10efb-113">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="10efb-114">As colunas de dados filtrados são indicadas por um ícone de filtro à esquerda do rótulo da coluna na caixa de diálogo **Editar Filtro** .</span><span class="sxs-lookup"><span data-stu-id="10efb-114">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="10efb-115">Para obter mais informações, consulte [SQL Server Profiler - Editar Filtro](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span><span class="sxs-lookup"><span data-stu-id="10efb-115">For more information, see [SQL Server Profiler - Edit Filter](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span></span>  
  
 <span data-ttu-id="10efb-116">**Mostrar todos os eventos**</span><span class="sxs-lookup"><span data-stu-id="10efb-116">**Show all events**</span></span>  
 <span data-ttu-id="10efb-117">Mostra todos os eventos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="10efb-117">Show all available events.</span></span> <span data-ttu-id="10efb-118">Por padrão, somente as linhas selecionadas na grade **Seleção de Eventos** são exibidas.</span><span class="sxs-lookup"><span data-stu-id="10efb-118">By default, only rows in the **Events Selection** grid that are selected display.</span></span> <span data-ttu-id="10efb-119">Desmarque essa caixa para ocultar todos os eventos não selecionados na grade **Seleção de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="10efb-119">Uncheck this box to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="10efb-120">**Mostrar todas as colunas**</span><span class="sxs-lookup"><span data-stu-id="10efb-120">**Show all columns**</span></span>  
 <span data-ttu-id="10efb-121">Mostra todas as colunas de dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="10efb-121">Show all available data columns.</span></span> <span data-ttu-id="10efb-122">Por padrão, somente colunas de dados selecionadas são exibidas.</span><span class="sxs-lookup"><span data-stu-id="10efb-122">By default, only data columns that are selected display.</span></span> <span data-ttu-id="10efb-123">Desmarque essa caixa para ocultar todas as colunas de dados não selecionadas na grade **Seleção de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="10efb-123">Uncheck this box to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="10efb-124">**Filtros de coluna**</span><span class="sxs-lookup"><span data-stu-id="10efb-124">**Column Filters**</span></span>  
 <span data-ttu-id="10efb-125">Abre a caixa de diálogo **Editar Filtro** .</span><span class="sxs-lookup"><span data-stu-id="10efb-125">Launches the **Edit Filter** dialog box.</span></span> <span data-ttu-id="10efb-126">Você pode usar essa caixa de diálogo para editar filtros de coluna de dados.</span><span class="sxs-lookup"><span data-stu-id="10efb-126">You can use this dialog to edit data column filters.</span></span>  
  
 <span data-ttu-id="10efb-127">**Organizar colunas**</span><span class="sxs-lookup"><span data-stu-id="10efb-127">**Organize Columns**</span></span>  
 <span data-ttu-id="10efb-128">Altera a ordem das colunas no rastreamento e agrupa os resultados em uma ou mais colunas.</span><span class="sxs-lookup"><span data-stu-id="10efb-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10efb-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="10efb-129">See Also</span></span>  
 <span data-ttu-id="10efb-130">[Especificar eventos e colunas de dados para um arquivo de rastreamento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="10efb-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="10efb-131">[Organizar colunas exibidas em um &#40;de rastreamento SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="10efb-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="10efb-132">[Filtrar eventos em um &#40;de rastreamento SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="10efb-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="10efb-133">[Exibir informações de filtro &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="10efb-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="10efb-134">[Modificar um filtro &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="10efb-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="10efb-135">[Modelos e permissões do SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="10efb-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="10efb-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="10efb-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
