---
title: Exibir dados de sessão de evento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ac742a01-2a95-42c7-b65e-ad565020dc49
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: eaeb5fd22b95b8f1056b8dce9e3c7d683b52602f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685248"
---
# <a name="view-event-session-data"></a><span data-ttu-id="815ca-102">Exibir dados de sessão de evento</span><span class="sxs-lookup"><span data-stu-id="815ca-102">View Event Session Data</span></span>
  <span data-ttu-id="815ca-103">Este tópico descreve o uso da interface do usuário de exibição para ver e analisar dados de evento estendidos:</span><span class="sxs-lookup"><span data-stu-id="815ca-103">This topic describes using the display user interface to see and analyze extended event data:</span></span>  
  
-   <span data-ttu-id="815ca-104">Exibir Dados de Destino</span><span class="sxs-lookup"><span data-stu-id="815ca-104">View Target Data</span></span>  
  
-   <span data-ttu-id="815ca-105">Trabalhando com dados</span><span class="sxs-lookup"><span data-stu-id="815ca-105">Working With Data</span></span>  
  
## <a name="view-target-data"></a><span data-ttu-id="815ca-106">Exibir Dados de Destino</span><span class="sxs-lookup"><span data-stu-id="815ca-106">View Target Data</span></span>  
 <span data-ttu-id="815ca-107">Você pode exibir os dados coletados no destino especificado dentro do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="815ca-107">You can display the data collected into the specified target within [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="view-target-data"></a><span data-ttu-id="815ca-108">Exibir Dados de Destino</span><span class="sxs-lookup"><span data-stu-id="815ca-108">View Target Data</span></span>  
 <span data-ttu-id="815ca-109">Para exibir dados de destino:</span><span class="sxs-lookup"><span data-stu-id="815ca-109">To view target data:</span></span>  
  
1.  <span data-ttu-id="815ca-110">No Pesquisador de Objetos, expanda **Gerenciamento**, **Eventos Estendidos**, **Sessões**e, em seguida, uma sessão.</span><span class="sxs-lookup"><span data-stu-id="815ca-110">In Object Explorer, expand **Management**, **Extended Events**, **Sessions**, and then a session.</span></span>  
  
2.  <span data-ttu-id="815ca-111">Clique com o botão direito do mouse no nome do destino e clique em **Exibir Dados de Destino** para exibir os dados de destino.</span><span class="sxs-lookup"><span data-stu-id="815ca-111">Right-click the target name, and then click **View Target Data** to display the target data.</span></span>  
  
     <span data-ttu-id="815ca-112">A janela de dados de destino aparece na exibição padrão e mostra os dados de destino.</span><span class="sxs-lookup"><span data-stu-id="815ca-112">The target data window appears in default view and displays the target data.</span></span>  
  
 <span data-ttu-id="815ca-113">Observações sobre como exibir dados de destino:</span><span class="sxs-lookup"><span data-stu-id="815ca-113">Notes on viewing target data:</span></span>  
  
-   <span data-ttu-id="815ca-114">Os dados de destino não estão disponíveis para o destino ETW.</span><span class="sxs-lookup"><span data-stu-id="815ca-114">Target data is not available for the ETW target.</span></span>  
  
-   <span data-ttu-id="815ca-115">Para exibir os dados de ring_buffer no formato xml, na janela de dados de destino, clique no link **dados de destino de ring_buffer** .</span><span class="sxs-lookup"><span data-stu-id="815ca-115">To view the ring_buffer data in xml format, in the target data window click the **ring_buffer target data** link.</span></span> <span data-ttu-id="815ca-116">O arquivo ring_buffer.xml aparece no editor de xml.</span><span class="sxs-lookup"><span data-stu-id="815ca-116">The ring_buffer.xml file appears in the xml editor.</span></span>  
  
-   <span data-ttu-id="815ca-117">Para um destino de event_file, exiba os dados de destino de arquivo (arquivo .XEL) usando um dos métodos a seguir:</span><span class="sxs-lookup"><span data-stu-id="815ca-117">For an event_file target, view the file target data (.XEL file) using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="815ca-118">Use o arquivo-> abrir no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="815ca-118">Use File -> Open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>
    
    -   <span data-ttu-id="815ca-119">Arraste e solte o arquivo no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="815ca-119">Drag and drop the file into [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> 
    
    -   <span data-ttu-id="815ca-120">Clique duas vezes no arquivo .XEL.</span><span class="sxs-lookup"><span data-stu-id="815ca-120">Double click the .XEL file.</span></span>  
    
    -   <span data-ttu-id="815ca-121">No [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], clique com o botão direito em uma sessão de Eventos Estendidos em execução e selecione Exibir Dados de Destino.</span><span class="sxs-lookup"><span data-stu-id="815ca-121">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right click on a running Extended Events session and select View Target Data.</span></span> 
    
    -   <span data-ttu-id="815ca-122">[fn_xe_file_target_read_file](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="815ca-122">[fn_xe_file_target_read_file](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>
    
    -   <span data-ttu-id="815ca-123">Use o PowerShell Read-SQLXevent no [módulo SqlServer. XEvent](https://www.powershellgallery.com/packages/SqlServer.XEvent).</span><span class="sxs-lookup"><span data-stu-id="815ca-123">Use Powershell Read-SQLXevent in [SQLServer.XEvent module](https://www.powershellgallery.com/packages/SqlServer.XEvent).</span></span>
    
    -   <span data-ttu-id="815ca-124">Consumir programaticamente XEvents usando o [NuGet do XELite](https://www.nuget.org/packages/Microsoft.SqlServer.XEvent.XELite).</span><span class="sxs-lookup"><span data-stu-id="815ca-124">Programmatically consume XEvents by using the [XELite NuGet](https://www.nuget.org/packages/Microsoft.SqlServer.XEvent.XELite).</span></span>
    
    -   <span data-ttu-id="815ca-125">Você pode exibir mais de um. XEL arquivo selecionando **mesclar arquivos de eventos estendidos** no menu arquivo-> abrir.</span><span class="sxs-lookup"><span data-stu-id="815ca-125">You can view more than one .XEL file by selecting **Merge Extended Event Files** from the File -> Open menu.</span></span>

### <a name="watching-live-data"></a><span data-ttu-id="815ca-126">Assistindo dados ao vivo</span><span class="sxs-lookup"><span data-stu-id="815ca-126">Watching Live Data</span></span>  
 <span data-ttu-id="815ca-127">Você pode assistir dados ao vivo à medida que estão sendo capturados.</span><span class="sxs-lookup"><span data-stu-id="815ca-127">You can watch live data as it is being captured.</span></span>  
  
-   <span data-ttu-id="815ca-128">No Pesquisador de objetos, expanda os nós **Gerenciamento**, **eventos estendidos**e **sessões** .</span><span class="sxs-lookup"><span data-stu-id="815ca-128">In Object Explorer, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  

-   <span data-ttu-id="815ca-129">Clique com o botão direito do mouse no nome da sessão e clique em **Observar Dados Dinâmicos** para começar a exibir dados de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="815ca-129">Right-click the session name and then click **Watch Live Data** to start displaying the tracing data.</span></span>  
  
     <span data-ttu-id="815ca-130">As colunas de exibição padrão são **Nome do Evento** e **TimeStamp**.</span><span class="sxs-lookup"><span data-stu-id="815ca-130">The default display columns are **Event Name** and **TimeStamp**.</span></span>  
  
     <span data-ttu-id="815ca-131">Para adicionar mais colunas à janela de rastreamento, clique no botão **Escolher Colunas** na barra de ferramentas Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="815ca-131">To add additional columns to the trace window, click the **Choose Columns** button on the Extended Events toolbar.</span></span> <span data-ttu-id="815ca-132">A guia **Detalhes** mostra todos os detalhes de evento do evento selecionado.</span><span class="sxs-lookup"><span data-stu-id="815ca-132">The **Details** tab shows all of the event details for the selected event.</span></span>  
  
     <span data-ttu-id="815ca-133">Em geral, os eventos são exibidos em aproximadamente 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="815ca-133">Events are usually displayed in approximately 30 seconds.</span></span> <span data-ttu-id="815ca-134">Se você quiser alterar o período de latência, poderá alterar a **Latência máxima de expedição** na página **Avançado** da caixa de diálogo **Nova Sessão** .</span><span class="sxs-lookup"><span data-stu-id="815ca-134">If you want to change the latency period, you can change the **Maximum dispatch latency** on the **Advanced** page of the of the **New Session** dialog.</span></span>  
     
-    <span data-ttu-id="815ca-135">Os dados dinâmicos podem ser transmitidos pelo [módulo SqlServer. XEvent do PowerShell](https://www.powershellgallery.com/packages/SqlServer.XEvent).</span><span class="sxs-lookup"><span data-stu-id="815ca-135">Live data can be streamed by the [SqlServer.XEvent PowerShell module](https://www.powershellgallery.com/packages/SqlServer.XEvent).</span></span>
     
### <a name="to-refresh-target-data"></a><span data-ttu-id="815ca-136">Para atualizar dados de destino</span><span class="sxs-lookup"><span data-stu-id="815ca-136">To Refresh Target Data</span></span>  
 <span data-ttu-id="815ca-137">Atualizar dados de destino não tem suporte para destinos de event_files:</span><span class="sxs-lookup"><span data-stu-id="815ca-137">Refreshing target data is not supported for event_files targets:</span></span>  
  
1.  <span data-ttu-id="815ca-138">Para atualizar os dados de destino automaticamente, clique com o botão direito do mouse nesses dados, selecione **Intervalo de Atualização**e selecione o intervalo de atualização na lista de intervalos.</span><span class="sxs-lookup"><span data-stu-id="815ca-138">To refresh the target data automatically, right click the target data, select **Refresh Interval**, and then select the refresh interval from the interval list.</span></span>  
  
2.  <span data-ttu-id="815ca-139">Para pausar e continuar a atualização automática, clique com o botão direito do mouse nos dados de destino e selecione **Pausar** ou **Retomar**.</span><span class="sxs-lookup"><span data-stu-id="815ca-139">To pause and resume the automatic refresh, right-click the target data and then select **Pause** or **Resume**.</span></span>  
  
3.  <span data-ttu-id="815ca-140">Para exibir os dados de destino manualmente, clique com o botão direito do mouse nos dados de destino e selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="815ca-140">To refresh the target data manually, right click the target data, and then select **Refresh**.</span></span>  
  
## <a name="working-with-data"></a><span data-ttu-id="815ca-141">Trabalhando com dados</span><span class="sxs-lookup"><span data-stu-id="815ca-141">Working With Data</span></span>  
 <span data-ttu-id="815ca-142">Você pode usar os recursos de análise da interface de usuário de Eventos Estendidos para identificar problemas.</span><span class="sxs-lookup"><span data-stu-id="815ca-142">You can use the analysis capabilities of the Extended Events user interface to identify problems.</span></span>  
  
### <a name="details-pane"></a><span data-ttu-id="815ca-143">Painel Detalhes</span><span class="sxs-lookup"><span data-stu-id="815ca-143">Details Pane</span></span>  
 <span data-ttu-id="815ca-144">O painel de **Detalhes** mostra todas as colunas para o evento selecionado, incluindo campos e ações.</span><span class="sxs-lookup"><span data-stu-id="815ca-144">The **Details** pane shows all the columns for the selected event, including fields and actions.</span></span> <span data-ttu-id="815ca-145">Você pode adicionar uma coluna à tabela de dados de destino clicando com o botão direito em uma linha no painel de **Detalhes** e selecionando **Mostrar Coluna na Tabela**.</span><span class="sxs-lookup"><span data-stu-id="815ca-145">You can add a column to the target data table by right-clicking a row in the **Details** pane and selecting **Show Column in Table**.</span></span>  
  
### <a name="create-modify-or-delete-merged-columns"></a><span data-ttu-id="815ca-146">Criar, modificar ou excluir colunas mescladas</span><span class="sxs-lookup"><span data-stu-id="815ca-146">Create, Modify, or Delete Merged Columns</span></span>  
 <span data-ttu-id="815ca-147">Uma coluna mesclada permite que você combine um conjunto de campos a ser exibido em uma única coluna.</span><span class="sxs-lookup"><span data-stu-id="815ca-147">A merged column allows you to combine a set of fields to be displayed in a single column.</span></span> <span data-ttu-id="815ca-148">A coluna mesclada mostrará os dados do primeiro campo não NULL baseado na ordem que eles são adicionados à lista de campos.</span><span class="sxs-lookup"><span data-stu-id="815ca-148">The merged column will show the data from the first non-NULL field based on the order they are added to the field list.</span></span> <span data-ttu-id="815ca-149">Isto é semelhante ao que você vê no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Profiler, onde uma coluna específica pode mostrar dados diferentes dependendo do evento (o exemplo mais comum disto é o campo TextData no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Profiler).</span><span class="sxs-lookup"><span data-stu-id="815ca-149">This is similar to what you see in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Profiler, where a specific column may show different data depending on the event (the most common example of this is the TextData field in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Profiler).</span></span> <span data-ttu-id="815ca-150">Para um exemplo, você pode mesclar os campos instrução e batch_text dos eventos sql_statement_completed e sql_batch_completed, respectivamente, em um campo nomeado myStatement.</span><span class="sxs-lookup"><span data-stu-id="815ca-150">For an example, you could merge the statement and batch_text fields from the sql_statement_completed and sql_batch_completed events, respectively, into a field named myStatement.</span></span> <span data-ttu-id="815ca-151">Quando você exibe a coluna myStatement na tabela, ela mostrará os dados apropriados para o evento associado.</span><span class="sxs-lookup"><span data-stu-id="815ca-151">When you display the myStatement column in the table it will show the appropriate data for the associated event.</span></span>  
  
 <span data-ttu-id="815ca-152">Você pode criar, modificar ou excluir colunas mescladas:</span><span class="sxs-lookup"><span data-stu-id="815ca-152">You can create, modify, or delete merged columns:</span></span>  
  
1.  <span data-ttu-id="815ca-153">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="815ca-153">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="815ca-154">(Você também pode clicar com o botão direito do mouse no nome da sessão e selecionar **Observar Dados Dinâmicos**.)</span><span class="sxs-lookup"><span data-stu-id="815ca-154">(You can also right click the session name, and then select **Watch Live Data**.)</span></span>  
  
2.  <span data-ttu-id="815ca-155">Na janela de resultados de rastreamento, clique com o botão direito no cabeçalho de coluna e clique em **Escolher Colunas**.</span><span class="sxs-lookup"><span data-stu-id="815ca-155">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
 <span data-ttu-id="815ca-156">Para criar uma coluna mesclada, clique em **Novo** na caixa de diálogo **Escolher Colunas** .</span><span class="sxs-lookup"><span data-stu-id="815ca-156">To create a merged column, click **New** in the **Choose Columns** dialog box.</span></span>  <span data-ttu-id="815ca-157">Na caixa de diálogo **Nova Coluna Mesclada** , nomeie a coluna mesclada e selecione as colunas originais a serem incluídas na coluna mesclada.</span><span class="sxs-lookup"><span data-stu-id="815ca-157">In the **New Merged Column** dialog, name the merged column and select the original columns to be included in the merged column.</span></span>  
  
 <span data-ttu-id="815ca-158">Para editar uma coluna mesclada, selecione uma coluna mesclada na caixa de diálogo **Escolher Colunas** e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="815ca-158">To edit a merged column, select a merged column in the **Choose Columns** dialog and click **Edit**.</span></span> <span data-ttu-id="815ca-159">Na caixa de diálogo **Editar Coluna Mesclada** , renomeie a coluna mesclada ou modifique as colunas originais a serem incluídas na coluna mesclada.</span><span class="sxs-lookup"><span data-stu-id="815ca-159">In the **Edit Merged Column** dialog, rename the merged column or modify the original columns to be included in the merged column.</span></span>  
  
 <span data-ttu-id="815ca-160">Para excluir uma coluna mesclada, selecione uma coluna mesclada na caixa de diálogo **Escolher Colunas** e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="815ca-160">To delete a merged column, select a merged column in the **Choose Columns** dialog and click **Delete**.</span></span>  
  
### <a name="filter-results"></a><span data-ttu-id="815ca-161">Filtrar resultados</span><span class="sxs-lookup"><span data-stu-id="815ca-161">Filter Results</span></span>  
 <span data-ttu-id="815ca-162">Você pode exibir resultados de rastreamento e aplicar filtros para reduzir os resultados do rastreamento que são exibidos na janela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="815ca-162">You can view trace results, and then apply filters to narrow down the trace results that are displayed in the trace window.</span></span> <span data-ttu-id="815ca-163">O filtro de exibição inclui um filtro de hora e um filtro avançado.</span><span class="sxs-lookup"><span data-stu-id="815ca-163">The display filter includes a time filter and an advanced filter.</span></span> <span data-ttu-id="815ca-164">Use o filtro de hora para filtrar os resultados de rastreamento por carimbo de data/hora de evento e use o filtro avançado para construir condições de filtro usando os campos de eventos e ações.</span><span class="sxs-lookup"><span data-stu-id="815ca-164">You use the time filter to filter the trace results by event timestamp, and you use the advanced filter to construct filter conditions using the event fields and actions.</span></span> <span data-ttu-id="815ca-165">Há um relacionamento "e" entre os filtros de hora e avançado.</span><span class="sxs-lookup"><span data-stu-id="815ca-165">There is an "and" relationship between the time and advanced filters.</span></span>  
  
 <span data-ttu-id="815ca-166">Para criar um filtro:</span><span class="sxs-lookup"><span data-stu-id="815ca-166">To create a filter:</span></span>  
  
1.  <span data-ttu-id="815ca-167">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="815ca-167">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="815ca-168">(Você também pode clicar com o botão direito do mouse no nome da sessão e selecionar **Observar Dados Dinâmicos**.)</span><span class="sxs-lookup"><span data-stu-id="815ca-168">(You can also right click the session name, and then select **Watch Live Data**.)</span></span>  
  
2.  <span data-ttu-id="815ca-169">Na janela de resultados de rastreamento, selecione os resultados que você deseja filtrar e, na barra de ferramentas **Eventos Estendidos** , clique no botão **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="815ca-169">In the trace results window, select the results you want to filter, and then on the **Extended Events** toolbar, click **Filters**.</span></span>  
  
3.  <span data-ttu-id="815ca-170">Na caixa de diálogo **Filtros** , selecione **Definir filtro de hora** para definir o filtro de hora arrastando o controle deslizante ou modificando a hora na caixa de edição.</span><span class="sxs-lookup"><span data-stu-id="815ca-170">In the **Filters** dialog box, select **Set time filter** to set the time filter by dragging the slider bars or modifying the time in the edit box.</span></span>  
  
4.  <span data-ttu-id="815ca-171">Na seção **Filtros adicionais** , aplique seus critérios de filtro e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="815ca-171">In the **Additional filters** section, apply your filter criteria, and then click **Apply**.</span></span>  
  
### <a name="sort-results"></a><span data-ttu-id="815ca-172">Classificar Resultados</span><span class="sxs-lookup"><span data-stu-id="815ca-172">Sort Results</span></span>  
 <span data-ttu-id="815ca-173">Para classificar os resultados em ordem crescente ou decrescente:</span><span class="sxs-lookup"><span data-stu-id="815ca-173">To sort results either in ascending or descending order:</span></span>  
  
1.  <span data-ttu-id="815ca-174">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="815ca-174">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="815ca-175">(Você também pode clicar com o botão direito no nome da sessão, **Observar Dados Dinâmicos**e em seguida clicar no botão **Parar Feed de Dados** na barra de ferramentas.)</span><span class="sxs-lookup"><span data-stu-id="815ca-175">(You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.)</span></span>  
  
2.  <span data-ttu-id="815ca-176">Na janela de resultados de rastreamento, clique com o botão direito do mouse no cabeçalho da coluna que você quer classificar e clique em **Classificação Crescente** ou **Classificação Decrescente**.</span><span class="sxs-lookup"><span data-stu-id="815ca-176">In the trace results window, right-click the column heading you want to sort and click **Sort Ascending** or **Sort Descending**.</span></span>  
  
 <span data-ttu-id="815ca-177">Você também pode clicar no cabeçalho da coluna para reverter a ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="815ca-177">You can also click the column header to reverse the sort order.</span></span>  
  
 <span data-ttu-id="815ca-178">Se você agrupou colunas, classificar a coluna só classificará os dados dentro do grupo.</span><span class="sxs-lookup"><span data-stu-id="815ca-178">If you have grouped columns, sorting the column will only sort data within the group.</span></span>  
  
### <a name="group-results"></a><span data-ttu-id="815ca-179">Agrupar resultados</span><span class="sxs-lookup"><span data-stu-id="815ca-179">Group Results</span></span>  
 <span data-ttu-id="815ca-180">Os resultados agrupados são equivalentes à funcionalidade da cláusula `GROUP BY` no [!INCLUDE[tsql](../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="815ca-180">Grouped results are equivalent to the functionality of the `GROUP BY` clause in [!INCLUDE[tsql](../includes/tsql-md.md)].</span></span> <span data-ttu-id="815ca-181">A tabela de dados de destino mostrará os dados agrupados, permitindo expandir e recolher os dados.</span><span class="sxs-lookup"><span data-stu-id="815ca-181">The target data table will show the data grouped together, allowing you to expand and collapse the data.</span></span>  
  
 <span data-ttu-id="815ca-182">Você deve agrupar dados antes de poder agregá-lo.</span><span class="sxs-lookup"><span data-stu-id="815ca-182">You must group data before you can aggregate it.</span></span> <span data-ttu-id="815ca-183">Por exemplo, você pode agrupar no valor query_hash, classificar em ordem decrescente por duração, obter a duração média para cada grupo e classificar em ordem decrescente na agregação.</span><span class="sxs-lookup"><span data-stu-id="815ca-183">For example, you can group on the query_hash value, sort descending by duration, get the average duration for each group, and then sort descending on the aggregation.</span></span>  <span data-ttu-id="815ca-184">Isto produzirá uma lista que mostra a lista de instruções exclusivas da duração média mais longa para a mais curta.</span><span class="sxs-lookup"><span data-stu-id="815ca-184">This will produce a list that shows the list of unique statements from longest to shortest average duration.</span></span> <span data-ttu-id="815ca-185">Quando você expande o grupo de nível superior, você verá as execuções individuais daquela consulta específica classificada da mais longa para a mais curta.</span><span class="sxs-lookup"><span data-stu-id="815ca-185">When you expand the top group you will see the individual executions of that specific query sorted from longest to shortest.</span></span>  
  
 <span data-ttu-id="815ca-186">Você pode agrupar os resultados por uma única coluna ou por várias colunas.</span><span class="sxs-lookup"><span data-stu-id="815ca-186">You can group results by a single column or by multiple columns.</span></span>  
  
 <span data-ttu-id="815ca-187">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="815ca-187">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="815ca-188">(Você também pode clicar com o botão direito no nome da sessão, **Observar Dados Dinâmicos**e em seguida clicar no botão **Parar Feed de Dados** na barra de ferramentas.)</span><span class="sxs-lookup"><span data-stu-id="815ca-188">(You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.)</span></span>  
  
 <span data-ttu-id="815ca-189">Para agrupar resultados por uma única coluna, clique com o botão direito do mouse no cabeçalho da coluna na janela de resultados de rastreamento e clique em **Agrupar por Esta Coluna**.</span><span class="sxs-lookup"><span data-stu-id="815ca-189">To group results by a single column, right-click the column heading in the trace results window, and click **Group by this Column**.</span></span> <span data-ttu-id="815ca-190">Para desfazer o agrupamento, selecione uma das linhas e clique em **Remover Todo o Agrupamento**.</span><span class="sxs-lookup"><span data-stu-id="815ca-190">To undo the grouping, select one of the rows and click **Remove All Groupings**.</span></span>  
  
 <span data-ttu-id="815ca-191">Para agrupar resultados por várias colunas, clique no botão **Agrupamento** na barra de ferramentas **Eventos Estendidos** .</span><span class="sxs-lookup"><span data-stu-id="815ca-191">To group results by a multiple columns, click the **Grouping** button on the **Extended Events** toolbar.</span></span> <span data-ttu-id="815ca-192">Na caixa de diálogo **Colunas disponíveis** da caixa de diálogo **Agrupamento** , selecione as colunas que você quer agrupar e mova-as na caixa **Colunas agrupadas em** .</span><span class="sxs-lookup"><span data-stu-id="815ca-192">In the **Available columns** box of the **Grouping** dialog, select the columns you want to group, and move them into the **Columns grouped on** box.</span></span> <span data-ttu-id="815ca-193">Para alterar a ordem, na caixa **Colunas agrupadas em** , clique nas setas para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="815ca-193">To change the order in the **Columns grouped on** box, click the up or down arrows.</span></span>  
  
### <a name="aggregate-results"></a><span data-ttu-id="815ca-194">Agregar resultados</span><span class="sxs-lookup"><span data-stu-id="815ca-194">Aggregate Results</span></span>  
 <span data-ttu-id="815ca-195">Você pode exibir os resultados de rastreamento e analisar mais profundamente os dados de seu evento agregando colunas em seus resultados.</span><span class="sxs-lookup"><span data-stu-id="815ca-195">You can view the trace results, and then further analyze your event data by aggregating columns in your results.</span></span> <span data-ttu-id="815ca-196">Eventos Estendidos dão suporte a cinco funções de agregação:</span><span class="sxs-lookup"><span data-stu-id="815ca-196">Extended Events supports five aggregation functions:</span></span>  
  
-   <span data-ttu-id="815ca-197">Sum</span><span class="sxs-lookup"><span data-stu-id="815ca-197">sum</span></span>  
  
-   <span data-ttu-id="815ca-198">Min</span><span class="sxs-lookup"><span data-stu-id="815ca-198">min</span></span>  
  
-   <span data-ttu-id="815ca-199">max</span><span class="sxs-lookup"><span data-stu-id="815ca-199">max</span></span>  
  
-   <span data-ttu-id="815ca-200">média</span><span class="sxs-lookup"><span data-stu-id="815ca-200">average</span></span>  
  
-   <span data-ttu-id="815ca-201">contagem</span><span class="sxs-lookup"><span data-stu-id="815ca-201">count</span></span>  
  
 <span data-ttu-id="815ca-202">Sum, Min, Max e Average podem ser usados somente com as colunas numéricas.</span><span class="sxs-lookup"><span data-stu-id="815ca-202">Sum, min, max, and average can only be used with numeric columns.</span></span> <span data-ttu-id="815ca-203">Count é o número de valores não nulos que existem para a coluna selecionada no grupo.</span><span class="sxs-lookup"><span data-stu-id="815ca-203">Count is the number of non-null values that exist for the selected column in the group.</span></span>  
  
 <span data-ttu-id="815ca-204">A agregação é realizada em um grupo; portanto, você deve agrupar os resultados antes de você executar a agregação.</span><span class="sxs-lookup"><span data-stu-id="815ca-204">Aggregation is performed on a group, so you must group the results before you can perform the aggregation.</span></span> <span data-ttu-id="815ca-205">Para agregar resultados:</span><span class="sxs-lookup"><span data-stu-id="815ca-205">To aggregate results:</span></span>  
  
1.  <span data-ttu-id="815ca-206">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="815ca-206">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="815ca-207">(Você também pode clicar com o botão direito no nome da sessão, **Observar Dados Dinâmicos**e em seguida clicar no botão **Parar Feed de Dados** na barra de ferramentas.)</span><span class="sxs-lookup"><span data-stu-id="815ca-207">(You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.)</span></span>  
  
2.  <span data-ttu-id="815ca-208">Na barra de ferramentas **Eventos Estendidos** , clique no botão **Agregação** .</span><span class="sxs-lookup"><span data-stu-id="815ca-208">On the **Extended Events** toolbar, click the **Aggregation** button.</span></span> <span data-ttu-id="815ca-209">A caixa de diálogo Agregação exibirá as colunas disponíveis para agregação.</span><span class="sxs-lookup"><span data-stu-id="815ca-209">The Aggregation dialog box will display the columns available for aggregation.</span></span>  
  
3.  <span data-ttu-id="815ca-210">Na coluna **Tipo de Agregação** , selecione o tipo de agregação.</span><span class="sxs-lookup"><span data-stu-id="815ca-210">In the **Aggregation Type** column, select the aggregation type.</span></span>  
  
4.  <span data-ttu-id="815ca-211">Na caixa **Classificar agregação por** , selecione a coluna de classificação.</span><span class="sxs-lookup"><span data-stu-id="815ca-211">In the **Sort aggregation by** box, select the sort column.</span></span> <span data-ttu-id="815ca-212">Em seguida, selecione em ordem crescente ou decrescente.</span><span class="sxs-lookup"><span data-stu-id="815ca-212">Then select ascending or descending order.</span></span>  
  
### <a name="search-for-text-in-columns"></a><span data-ttu-id="815ca-213">Pesquisar texto nas colunas</span><span class="sxs-lookup"><span data-stu-id="815ca-213">Search for Text in Columns</span></span>  
 <span data-ttu-id="815ca-214">Você pode pesquisar texto nas colunas:</span><span class="sxs-lookup"><span data-stu-id="815ca-214">You can search for text in columns:</span></span>  
  
1.  <span data-ttu-id="815ca-215">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="815ca-215">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="815ca-216">(Você também pode clicar com o botão direito do mouse no nome da sessão e selecionar **Observar Dados Dinâmicos**.)</span><span class="sxs-lookup"><span data-stu-id="815ca-216">(You can also right click the session name, select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="815ca-217">Clique em **Localizar** na barra de ferramentas **Eventos Estendidos** .</span><span class="sxs-lookup"><span data-stu-id="815ca-217">Click **Find** on the **Extended Events** toolbar.</span></span>  
  
3.  <span data-ttu-id="815ca-218">Na caixa de diálogo **Localizar** da caixa de diálogo **Localizar nos Eventos Estendidos** , insira o texto de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="815ca-218">In the **Find what** box of the **Find in Extended Events** dialog box, enter the search text.</span></span> <span data-ttu-id="815ca-219">Você pode selecionar uma das suas últimas 20 cadeias de caracteres pesquisadas na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="815ca-219">You can select one of your last 20 search strings from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="815ca-220">Na caixa **Examinar** , selecione o local para pesquisar o texto especificado.</span><span class="sxs-lookup"><span data-stu-id="815ca-220">In the **Look in** box, select the location to search for the specified text.</span></span> <span data-ttu-id="815ca-221">Use as seguintes opções para procurar:</span><span class="sxs-lookup"><span data-stu-id="815ca-221">Use the following options for searching:</span></span>  
  
    -   <span data-ttu-id="815ca-222">Colunas da tabela.</span><span class="sxs-lookup"><span data-stu-id="815ca-222">Table Columns.</span></span> <span data-ttu-id="815ca-223">Use esta opção para procurar todas as colunas visíveis na janela de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="815ca-223">Use this option to search all visible columns in the trace window.</span></span>  
  
    -   <span data-ttu-id="815ca-224">Detalhes.</span><span class="sxs-lookup"><span data-stu-id="815ca-224">Details.</span></span> <span data-ttu-id="815ca-225">Use esta opção para pesquisar todas as colunas (promovidas e não promovidas) na janela de rastreamento que foram selecionadas antes de abrir a caixa de diálogo **Localizar em eventos estendidos** .</span><span class="sxs-lookup"><span data-stu-id="815ca-225">Use this option to search all columns (promoted and non-promoted) in the trace window that were selected before opening the **Find in Extended Events** dialog box.</span></span>  
  
    -   <span data-ttu-id="815ca-226">*Event_column_name*.</span><span class="sxs-lookup"><span data-stu-id="815ca-226">*Event_column_name*.</span></span> <span data-ttu-id="815ca-227">Use esta opção para procurar uma coluna de evento específica na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="815ca-227">Use this option to search in a specific event column from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="815ca-228">Use as opções a seguir para especificar como você quer definir a pesquisa:</span><span class="sxs-lookup"><span data-stu-id="815ca-228">Use the following options to specify how you want to define the search:</span></span>  
  
    -   <span data-ttu-id="815ca-229">Diferenciar maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="815ca-229">Match case.</span></span> <span data-ttu-id="815ca-230">Use esta opção para exibir os resultados da pesquisa para o texto que você inseriu na caixa Localizar que corresponde conteúdo e caso.</span><span class="sxs-lookup"><span data-stu-id="815ca-230">Use this option to display the search results for the text you entered in the Find what box that are matched both by content and by case.</span></span>  
  
    -   <span data-ttu-id="815ca-231">Coincidir palavra inteira.</span><span class="sxs-lookup"><span data-stu-id="815ca-231">Match whole word.</span></span> <span data-ttu-id="815ca-232">Use esta opção para exibir somente os resultados da pesquisa para o texto que você inseriu que corresponde palavras completas.</span><span class="sxs-lookup"><span data-stu-id="815ca-232">Use this option to display only the search results for the text you entered that match complete words.</span></span>  
  
    -   <span data-ttu-id="815ca-233">Pesquisar para cima.</span><span class="sxs-lookup"><span data-stu-id="815ca-233">Search up.</span></span> <span data-ttu-id="815ca-234">Use esta opção para pesquisar do local do seu cursor para o início dos resultados.</span><span class="sxs-lookup"><span data-stu-id="815ca-234">Use this option to search from your cursor location to the beginning of the results.</span></span>  
  
    -   <span data-ttu-id="815ca-235">Usar.</span><span class="sxs-lookup"><span data-stu-id="815ca-235">Use.</span></span> <span data-ttu-id="815ca-236">Use esta opção para interpretar os caracteres especiais e as expressões regulares que você inseriu na caixa Localizar.</span><span class="sxs-lookup"><span data-stu-id="815ca-236">Use this option to interpret the special characters and the regular expressions you entered in the Find what box.</span></span> <span data-ttu-id="815ca-237">Caracteres especiais incluem os caracteres curinga (\*) e (?) para representar um ou mais caracteres.</span><span class="sxs-lookup"><span data-stu-id="815ca-237">Special characters include the wildcard characters (\*) and (?) to represent one or more characters.</span></span> <span data-ttu-id="815ca-238">Expressões regulares são notações especiais usadas para definir padrões de texto de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="815ca-238">Regular expressions are special notations used to define patterns of search text.</span></span>  
  
    -   <span data-ttu-id="815ca-239">Clique em **Localizar Próximo** para procurar o próximo texto que você inseriu na caixa **Localizar** .</span><span class="sxs-lookup"><span data-stu-id="815ca-239">Click **Find Next** to search for the next text that you entered in the **Find what** box.</span></span>  
  
### <a name="bookmarks"></a><span data-ttu-id="815ca-240">Indicadores</span><span class="sxs-lookup"><span data-stu-id="815ca-240">Bookmarks</span></span>  
 <span data-ttu-id="815ca-241">Para facilitar o retorno a uma linha, você poderá marcar uma ou mais linhas nos dados de destino.</span><span class="sxs-lookup"><span data-stu-id="815ca-241">To make it easier to return to a row, you can bookmark one or more row(s) in the target data.</span></span> <span data-ttu-id="815ca-242">Clique com o botão direito do mouse para alterar o indicador.</span><span class="sxs-lookup"><span data-stu-id="815ca-242">Right click on a row to change the bookmark.</span></span> <span data-ttu-id="815ca-243">Use os botões anterior e próximo na barra de ferramentas **Eventos Estendidos** para navegar para linhas marcadas.</span><span class="sxs-lookup"><span data-stu-id="815ca-243">Use the previous and next buttons on the **Extended Events** toolbar to navigate to bookmarked rows.</span></span>  
  
### <a name="change-display-settings"></a><span data-ttu-id="815ca-244">Alterar as configurações de exibição</span><span class="sxs-lookup"><span data-stu-id="815ca-244">Change Display Settings</span></span>  
 <span data-ttu-id="815ca-245">Você pode salvar informações de coluna (ordem de coluna, coluna de mesclagem e largura de coluna) e informações de filtro de um resultado de rastreamento em um arquivo de configuração de exibição de Eventos Estendidos (arquivo .viewsetting).</span><span class="sxs-lookup"><span data-stu-id="815ca-245">You can save column information (column order, merge column, and column width) and filter information of a trace result into an Extended Events display setting file (.viewsetting file).</span></span> <span data-ttu-id="815ca-246">Após salvar o arquivo, você pode aplicá-lo aos seus resultados de rastreamento para alterar a exibição.</span><span class="sxs-lookup"><span data-stu-id="815ca-246">After saving the file, you can apply it to your trace results to change the view.</span></span>  
  
 <span data-ttu-id="815ca-247">Para alterar as configurações de exibição:</span><span class="sxs-lookup"><span data-stu-id="815ca-247">To change the display settings:</span></span>  
  
1.  <span data-ttu-id="815ca-248">Abra um arquivo .XEL para exibir os resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="815ca-248">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="815ca-249">(Você também pode clicar com o botão direito do mouse no nome da sessão e selecionar **Observar Dados Dinâmicos**.)</span><span class="sxs-lookup"><span data-stu-id="815ca-249">(You can also right click the session name, select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="815ca-250">Na barra de ferramentas **Eventos Estendidos** , selecione **Configurações de Vídeo**.</span><span class="sxs-lookup"><span data-stu-id="815ca-250">On the **Extended Events** toolbar, select **Display Settings**.</span></span> <span data-ttu-id="815ca-251">Na lista suspensa, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="815ca-251">From the drop-down list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="815ca-252">Salvar como.</span><span class="sxs-lookup"><span data-stu-id="815ca-252">Save as.</span></span> <span data-ttu-id="815ca-253">Salve as colunas e informações de filtro de um resultado de rastreamento em um arquivo .viewsetting.</span><span class="sxs-lookup"><span data-stu-id="815ca-253">Save the columns and filter information of a trace result to a .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="815ca-254">Abrir.</span><span class="sxs-lookup"><span data-stu-id="815ca-254">Open.</span></span> <span data-ttu-id="815ca-255">Abra um arquivo .viewsetting existente.</span><span class="sxs-lookup"><span data-stu-id="815ca-255">Open an existing .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="815ca-256">Abrir recente.</span><span class="sxs-lookup"><span data-stu-id="815ca-256">Open recent.</span></span> <span data-ttu-id="815ca-257">Abra um arquivo .viewsetting salvo recentemente.</span><span class="sxs-lookup"><span data-stu-id="815ca-257">Open a recently saved .viewsetting file.</span></span>  
  
### <a name="copy-or-export-trace-results"></a><span data-ttu-id="815ca-258">Copiar ou exportar resultados de rastreamento</span><span class="sxs-lookup"><span data-stu-id="815ca-258">Copy or Export Trace Results</span></span>  
 <span data-ttu-id="815ca-259">Você pode copiar células, linhas e detalhes para linhas selecionadas de seus resultados do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="815ca-259">You can copy cells, rows, and details to selected rows from your trace results.</span></span> <span data-ttu-id="815ca-260">Você também pode exportar seus resultados do rastreamento para os itens a seguir:</span><span class="sxs-lookup"><span data-stu-id="815ca-260">You can also export your trace results to the following:</span></span>  
  
-   <span data-ttu-id="815ca-261">Arquivo .XEL</span><span class="sxs-lookup"><span data-stu-id="815ca-261">.XEL file</span></span>  
  
-   <span data-ttu-id="815ca-262">tabela</span><span class="sxs-lookup"><span data-stu-id="815ca-262">table</span></span>  
  
-   <span data-ttu-id="815ca-263">Arquivo .CSV</span><span class="sxs-lookup"><span data-stu-id="815ca-263">.CSV file</span></span>  
  
 <span data-ttu-id="815ca-264">Para copiar resultados de rastreamento, selecione uma célula, linha ou linhas, clique com o botão direito, selecione **Cópia** e em **Célula**, **Linha**ou **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="815ca-264">To copy trace results, select a cell, row, or rows, right click, select **Copy** and then **Cell**, **Row**, or **Details**.</span></span> <span data-ttu-id="815ca-265">A opção Eventos Estendidos oferece suporte à cópia de um máximo de 1.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="815ca-265">Extended Events supports copying up to a maximum of 1000 rows.</span></span>  
  
 <span data-ttu-id="815ca-266">Você pode exportar resultados de rastreamento para um arquivo .XEL, tabela ou arquivo .CSV selecionando **Exportar para** da opção de menu **Eventos Estendidos** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="815ca-266">You can export trace results to a .XEL file, table, or .CSV file by selecting **Export to** from the **Extended Events** menu option in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="view-a-deadlock-graph-and-query-plans"></a><span data-ttu-id="815ca-267">Exibir um gráfico de Deadlock e planos de consulta</span><span class="sxs-lookup"><span data-stu-id="815ca-267">View a Deadlock Graph and Query Plans</span></span>  
 <span data-ttu-id="815ca-268">Você pode exibir o deadlock graph para **xml_deadlock_report** no painel Detalhes para ajudar a solucionar problemas de deadlocks.</span><span class="sxs-lookup"><span data-stu-id="815ca-268">You can view the deadlock graph for **xml_deadlock_report** in the Details pane to help you troubleshoot deadlocks.</span></span> <span data-ttu-id="815ca-269">Você também pode exibir gráficos de plano de consulta para os seguintes eventos:</span><span class="sxs-lookup"><span data-stu-id="815ca-269">You can also view query plan graphs for the following events:</span></span>  
  
-   <span data-ttu-id="815ca-270">query_post_compilation_showplan</span><span class="sxs-lookup"><span data-stu-id="815ca-270">query_post_compilation_showplan</span></span>  
  
-   <span data-ttu-id="815ca-271">query_pre_execution_showplan</span><span class="sxs-lookup"><span data-stu-id="815ca-271">query_pre_execution_showplan</span></span>  
  
-   <span data-ttu-id="815ca-272">query_post_execution_showplan</span><span class="sxs-lookup"><span data-stu-id="815ca-272">query_post_execution_showplan</span></span>  
  
 <span data-ttu-id="815ca-273">Para exibir o deadlock graph:</span><span class="sxs-lookup"><span data-stu-id="815ca-273">To view the deadlock graph:</span></span>  
  
-   <span data-ttu-id="815ca-274">No Pesquisador de objetos, expanda os nós **Gerenciamento**, **eventos estendidos**e **sessões** .</span><span class="sxs-lookup"><span data-stu-id="815ca-274">In Object Explorer, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
-   <span data-ttu-id="815ca-275">Clique com o botão direito do mouse na sessão que contém o evento de deadlock configurado que você deseja exibir e selecione **Observar Dados Dinâmicos**.</span><span class="sxs-lookup"><span data-stu-id="815ca-275">Right-click the session that contains the configured deadlock event that you want to view, and select **Watch Live Data**.</span></span>  
  
-   <span data-ttu-id="815ca-276">Selecione o evento de deadlock e exiba o gráfico na guia **Deadlock** no painel Detalhes.</span><span class="sxs-lookup"><span data-stu-id="815ca-276">Select the deadlock event and view the graph on the **Deadlock** tab in the Details pane.</span></span>  
  
 <span data-ttu-id="815ca-277">Para exibir gráficos de plano de consulta:</span><span class="sxs-lookup"><span data-stu-id="815ca-277">To view query plan graphs:</span></span>  
  
1.  <span data-ttu-id="815ca-278">No Pesquisador de objetos, expanda os nós **Gerenciamento**, **eventos estendidos**e **sessões** .</span><span class="sxs-lookup"><span data-stu-id="815ca-278">In Object Explorer, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="815ca-279">Clique com o botão direito do mouse na sessão que contém o gráfico de plano de consulta que você deseja exibir (por exemplo, query_post_compilation_showplan) e selecione **Observar Dados Dinâmicos**.</span><span class="sxs-lookup"><span data-stu-id="815ca-279">Right-click the session that contains the query plan graph that you want to view (for example, query_post_compilation_showplan), and then select **Watch Live Data**.</span></span>  
  
3.  <span data-ttu-id="815ca-280">Selecione o evento de gráfico de plano de consulta (por exemplo, query_post_compilation_showplan) e exiba o gráfico na guia **Plano de consulta** no painel Detalhes.</span><span class="sxs-lookup"><span data-stu-id="815ca-280">Select the query plan graph event (for example, query_post_compilation_showplan) and view the graph on the **Query plan** tab in the Details pane.</span></span>  
  
  
