---
title: Modificar um filtro (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], modifying
- modifying filters, modifying
- filters [SQL Server], traces
ms.assetid: 8b317813-4918-4485-b930-77b1951aa00c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5a7bab18952820a3dc49c9479797a411521f8e71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572887"
---
# <a name="modify-a-filter-sql-server-profiler"></a><span data-ttu-id="5f0e6-102">Modificar um filtro (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="5f0e6-102">Modify a Filter (SQL Server Profiler)</span></span>
  <span data-ttu-id="5f0e6-103">Os filtros são adicionados aos modelos de rastreamento, que contêm as definições de rastreamento, para limitar o número de eventos coletados por um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-103">You add filters to trace templates, which contain the trace definitions, to limit the number of events that are gathered by a trace.</span></span> <span data-ttu-id="5f0e6-104">Limitar o número de eventos coletados pode reduzir os efeitos do desempenho do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-104">Limiting the number of events gathered can reduce the performance effects of tracing.</span></span> <span data-ttu-id="5f0e6-105">Se definir filtros para um modelo de rastreamento e achar que o rastreamento não está coletando o tipo de informações de que necessita, você poderá editar o filtro.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-105">If you set filters for a trace template and find that the trace is not gathering the kind of information that you need, you can edit the filter.</span></span>  
  
### <a name="to-modify-a-filter"></a><span data-ttu-id="5f0e6-106">Para modificar um filtro</span><span class="sxs-lookup"><span data-stu-id="5f0e6-106">To modify a filter</span></span>  
  
1.  <span data-ttu-id="5f0e6-107">No [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], abra o modelo referente ao filtro de rastreamento que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-107">In [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], open the template for the trace filter that you want to modify.</span></span> <span data-ttu-id="5f0e6-108">No menu **Arquivo** , clique em **Modelos**e escolha **Editar Modelo**.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-108">On the **File** menu, click **Templates**, and then choose **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="5f0e6-109">Na guia **Geral** da caixa de diálogo **Propriedades do Modelo de Rastreamento** , selecione um modelo na lista **Selecionar nome do modelo** .</span><span class="sxs-lookup"><span data-stu-id="5f0e6-109">In the **General** tab of the **Trace Template Properties** dialog, select a template from the **Select template name** list.</span></span>  
  
3.  <span data-ttu-id="5f0e6-110">Clique na guia **Seleção de Eventos** .</span><span class="sxs-lookup"><span data-stu-id="5f0e6-110">Click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="5f0e6-111">A guia **Seleção de Eventos** contém um controle de grade.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-111">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="5f0e6-112">O controle de grade é uma tabela que contém cada uma das classes de evento rastreáveis.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-112">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="5f0e6-113">A tabela contém uma linha para cada classe de evento.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-113">The table contains one row for each event class.</span></span> <span data-ttu-id="5f0e6-114">As classes de evento podem diferir ligeiramente, dependendo do tipo e versão de servidor com o qual você está conectado.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-114">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="5f0e6-115">As classes de evento são identificadas na coluna **Events**da grade e são agrupadas por categoria de evento.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-115">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="5f0e6-116">As colunas restantes listam as colunas de dados que podem ser retornadas para cada classe de evento.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-116">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
4.  <span data-ttu-id="5f0e6-117">Clique em **Filtros de Coluna**.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-117">Click **Column Filters**.</span></span>  
  
5.  <span data-ttu-id="5f0e6-118">Na caixa de diálogo **Editar Filtro** , clique no valor próximo ao operador de comparação que você deseja editar e exclua-o ou digite o novo valor.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-118">In the **Edit Filter** dialog box, click the value next to the comparison operator that you want to edit, and type the new value or delete a value.</span></span> <span data-ttu-id="5f0e6-119">Você também pode adicionar outros filtros.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-119">You can also add additional filters.</span></span>  
  
6.  <span data-ttu-id="5f0e6-120">Clique em **OK** e salve o modelo.</span><span class="sxs-lookup"><span data-stu-id="5f0e6-120">Click **OK** and save the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f0e6-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5f0e6-121">See Also</span></span>  
 [<span data-ttu-id="5f0e6-122">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="5f0e6-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
