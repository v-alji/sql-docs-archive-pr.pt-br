---
title: Criar um modelo de rastreamento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- saving trace template
ms.assetid: 025868b0-3790-4cda-8757-5a58327bfba0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 355f97c7fecd8a9e31f10de881d1ae6df3b8f122
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678405"
---
# <a name="create-a-trace-template-sql-server-profiler"></a><span data-ttu-id="f43a3-102">Criar um modelo de rastreamento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f43a3-102">Create a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="f43a3-103">Este tópico descreve como criar um novo modelo de rastreamento usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f43a3-103">This topic describes how to create a new trace template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-create-a-trace-template"></a><span data-ttu-id="f43a3-104">Para criar um modelo de rastreamento</span><span class="sxs-lookup"><span data-stu-id="f43a3-104">To create a trace template</span></span>  
  
1.  <span data-ttu-id="f43a3-105">No menu **Arquivo** , aponte para **Modelos**e clique em **Novo Modelo**.</span><span class="sxs-lookup"><span data-stu-id="f43a3-105">On the **File** menu, point to **Templates**, and then click **New Template**.</span></span>  
  
2.  <span data-ttu-id="f43a3-106">Na caixa de diálogo **Propriedades do Modelo de Rastreamento** , selecione um tipo de servidor na lista **Selecionar tipo de servidor**.</span><span class="sxs-lookup"><span data-stu-id="f43a3-106">In the **Trace Template Properties** dialog box, select a server type from the **Select server type**list.</span></span>  
  
3.  <span data-ttu-id="f43a3-107">Na caixa **Nome do novo modelo** , insira um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="f43a3-107">In the **New template name** box, enter a template name.</span></span>  
  
4.  <span data-ttu-id="f43a3-108">Opcionalmente, clique em **Basear novo modelo no existente**e selecione um modelo na lista.</span><span class="sxs-lookup"><span data-stu-id="f43a3-108">Optionally, click **Base new template on existing one**, and then select a template from the list.</span></span>  
  
     <span data-ttu-id="f43a3-109">Todos os eventos, colunas de dados e filtros são inicialmente definidos como especificado no modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="f43a3-109">All events, data columns, and filters are initially set as specified in the selected template.</span></span>  
  
5.  <span data-ttu-id="f43a3-110">Opcionalmente, clique em **Usar como modelo padrão para o tipo de servidor selecionado**.</span><span class="sxs-lookup"><span data-stu-id="f43a3-110">Optionally, click **Use as a default template for selected server type**.</span></span>  
  
6.  <span data-ttu-id="f43a3-111">Na guia **Seleção de Eventos** , adicione, remova ou modifique eventos, colunas de dados ou filtros.</span><span class="sxs-lookup"><span data-stu-id="f43a3-111">On the **Events Selection** tab, add, remove, or modify events, data columns, or filters.</span></span>  
  
7.  <span data-ttu-id="f43a3-112">No menu **Seleção de Eventos**, use o controle da grade para adicionar ou remover eventos e colunas de dados do arquivo de rastreamento, da maneira abaixo:</span><span class="sxs-lookup"><span data-stu-id="f43a3-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows:</span></span>  
  
    -   <span data-ttu-id="f43a3-113">Para adicionar um evento, expanda a categoria de evento apropriada na coluna **Eventos** e selecione o nome do evento.</span><span class="sxs-lookup"><span data-stu-id="f43a3-113">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="f43a3-114">Quando um evento é adicionado, todas as colunas de dados relevantes são incluídas, por padrão.</span><span class="sxs-lookup"><span data-stu-id="f43a3-114">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="f43a3-115">Para remover uma coluna de dados de um evento do rastreamento, desmarque a caixa de seleção correspondente ao evento na coluna de dados.</span><span class="sxs-lookup"><span data-stu-id="f43a3-115">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="f43a3-116">Para adicionar filtros, clique no nome de coluna de dados e especifique os critérios de filtro na caixa de diálogo **Editar Filtro** .</span><span class="sxs-lookup"><span data-stu-id="f43a3-116">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="f43a3-117">Você também pode clicar com o botão direito do mouse no nome da coluna de dados e em **Editar Filtro de Coluna** para iniciar a caixa de diálogo **Editar Filtro** .</span><span class="sxs-lookup"><span data-stu-id="f43a3-117">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="f43a3-118">Para adicionar o filtro, clique em **OK** .</span><span class="sxs-lookup"><span data-stu-id="f43a3-118">Click **OK** to add the filter.</span></span>  
  
8.  <span data-ttu-id="f43a3-119">Clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="f43a3-119">Click **Save.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43a3-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f43a3-120">See Also</span></span>  
 <span data-ttu-id="f43a3-121">[Especificar eventos e colunas de dados para um arquivo de rastreamento &#40;SQL Server Profiler&#41;](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f43a3-121">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f43a3-122">[Derivar um modelo de um rastreamento em execução &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f43a3-122">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f43a3-123">[Derivar um modelo de um arquivo ou de uma tabela de rastreamento &#40;SQL Server Profiler&#41;](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f43a3-123">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f43a3-124">[Modelos e permissões do SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="f43a3-124">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="f43a3-125">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f43a3-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
