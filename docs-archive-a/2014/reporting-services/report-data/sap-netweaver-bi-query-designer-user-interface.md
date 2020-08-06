---
title: Interface do usuário do Designer de Consultas do SAP NetWeaver BI | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10014"
- sql12.rtp.rptdesigner.dataview.sapbwquerydesigner.f1
helpviewer_keywords:
- data sources [Reporting Services], SAP NetWeaver Business Intelligence
- SAP NetWeaver Business Intelligence [Reporting Services], query designer
- query designers [Reporting Services]
ms.assetid: 102da66e-ca31-41aa-ab4b-c9b5ab752a72
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c1bd7293021a1a755c8189f354af7a54f7e4737
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571311"
---
# <a name="sap-netweaver-bi-query-designer-user-interface"></a><span data-ttu-id="fc52e-102">Interface do usuário do Designer de Consulta do SAP NetWeaver BI</span><span class="sxs-lookup"><span data-stu-id="fc52e-102">SAP NetWeaver BI Query Designer User Interface</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="fc52e-103">fornece um designer de consultas gráficas para criar consultas MDX para uma fonte de dados do SAP NetWeaver® Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="fc52e-103">provides a graphical query designer for building Multidimensional Expression (MDX) queries for a SAP NetWeaver® Business Intelligence data source.</span></span> <span data-ttu-id="fc52e-104">O designer de consultas gráficas MDX tem dois modos: Design e Consulta.</span><span class="sxs-lookup"><span data-stu-id="fc52e-104">The MDX graphical query designer has two modes: Design mode and Query mode.</span></span> <span data-ttu-id="fc52e-105">Cada modo contém um painel Metadados, do qual é possível arrastar membros de um InfoCube, MultiProvider ou consulta habilitada para Web definida na fonte de dados para criar uma consulta MDX que recupere dados quando o relatório for processado.</span><span class="sxs-lookup"><span data-stu-id="fc52e-105">Each mode provides a Metadata pane from which you can drag members from an InfoCube, MultiProvider, or Web-enabled query defined on the data source to build an MDX query that retrieves data when the report is processed.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="fc52e-106">Os usuários acessam fontes de dados quando criam e executam consultas.</span><span class="sxs-lookup"><span data-stu-id="fc52e-106">Users access data sources when they create and run queries.</span></span> <span data-ttu-id="fc52e-107">Você deve conceder permissões mínimas nas fontes de dados, como permissões somente leitura.</span><span class="sxs-lookup"><span data-stu-id="fc52e-107">You should grant minimal permissions on the data sources, such as read-only permissions.</span></span>

 <span data-ttu-id="fc52e-108">Para obter mais informações sobre como trabalhar com uma fonte de dados multidimensionais do SAP, consulte [Tipo de conexão do SAP NetWeaver BI &#40;SSRS&#41;](sap-netweaver-bi-connection-type-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fc52e-108">For more information about working with a SAP multidimensional data source, see [SAP NetWeaver BI Connection Type &#40;SSRS&#41;](sap-netweaver-bi-connection-type-ssrs.md).</span></span>

 <span data-ttu-id="fc52e-109">Esta seção descreve os botões da barra de ferramentas e os painéis do designer de consulta para cada modo do designer de consultas gráficas.</span><span class="sxs-lookup"><span data-stu-id="fc52e-109">This section describes the toolbar buttons and query designer panes for each mode of the graphical query designer.</span></span>

## <a name="graphical-query-designer-in-design-mode"></a><span data-ttu-id="fc52e-110">Designer de Consultas Gráficas no modo Design</span><span class="sxs-lookup"><span data-stu-id="fc52e-110">Graphical Query Designer in Design Mode</span></span>
 <span data-ttu-id="fc52e-111">Quando você edita uma consulta de um conjunto de dados que usa uma fonte de dados do [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] , o designer de consultas gráficas é aberto no modo Design.</span><span class="sxs-lookup"><span data-stu-id="fc52e-111">When you edit a dataset query that uses a [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] data source, the graphical query designer opens in the Design mode.</span></span> <span data-ttu-id="fc52e-112">A figura a seguir mostra os painéis do modo Design.</span><span class="sxs-lookup"><span data-stu-id="fc52e-112">The following figure labels the panes for Design mode.</span></span>

 <span data-ttu-id="fc52e-113">![Designer de consultas usando MDX no Modo Design](../media/rsqd-dssapbw-mdx-designmode.gif "Designer de consultas usando MDX no Modo Design")</span><span class="sxs-lookup"><span data-stu-id="fc52e-113">![Query Designer using MDX in Design Mode](../media/rsqd-dssapbw-mdx-designmode.gif "Query Designer using MDX in Design Mode")</span></span>

 <span data-ttu-id="fc52e-114">A tabela a seguir lista os painéis neste modo.</span><span class="sxs-lookup"><span data-stu-id="fc52e-114">The following table lists the panes in this mode.</span></span>

|<span data-ttu-id="fc52e-115">Painel</span><span class="sxs-lookup"><span data-stu-id="fc52e-115">Pane</span></span>|<span data-ttu-id="fc52e-116">Função</span><span class="sxs-lookup"><span data-stu-id="fc52e-116">Function</span></span>|
|----------|--------------|
|<span data-ttu-id="fc52e-117">Botão Selecionar Cubo</span><span class="sxs-lookup"><span data-stu-id="fc52e-117">Select Cube button</span></span>|<span data-ttu-id="fc52e-118">Exibe o InfoCube, MultiProvider ou consulta habilitada para Web selecionada no momento.</span><span class="sxs-lookup"><span data-stu-id="fc52e-118">Displays the currently selected InfoCube, MultiProvider, or Web-enabled query.</span></span>|
|<span data-ttu-id="fc52e-119">Painel Metadados</span><span class="sxs-lookup"><span data-stu-id="fc52e-119">Metadata pane</span></span>|<span data-ttu-id="fc52e-120">Exibe uma lista hierárquica de InfoCubes, MultiProviders e consultas.</span><span class="sxs-lookup"><span data-stu-id="fc52e-120">Displays a hierarchical list of InfoCubes, MultiProviders, and queries.</span></span> <span data-ttu-id="fc52e-121">As consultas criadas na fonte de dados podem ser exibidas no cubo correspondente.</span><span class="sxs-lookup"><span data-stu-id="fc52e-121">Queries created at the data source may appear under the corresponding cube.</span></span>|
|<span data-ttu-id="fc52e-122">Painel Membros Calculados</span><span class="sxs-lookup"><span data-stu-id="fc52e-122">Calculated Members pane</span></span>|<span data-ttu-id="fc52e-123">Exibe os membros calculados definidos no momento disponíveis para serem usados na consulta.</span><span class="sxs-lookup"><span data-stu-id="fc52e-123">Displays the currently defined calculated members available for use in the query.</span></span>|
|<span data-ttu-id="fc52e-124">Painel Dados</span><span class="sxs-lookup"><span data-stu-id="fc52e-124">Data pane</span></span>|<span data-ttu-id="fc52e-125">Exibe os resultados da execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="fc52e-125">Displays the results of running the query.</span></span>|

 <span data-ttu-id="fc52e-126">Você pode arrastar dimensões e imagens chave do painel Metadados e membros calculados do painel Membro Calculado para o painel Dados.</span><span class="sxs-lookup"><span data-stu-id="fc52e-126">You can drag dimensions and key figures from the Metadata pane, and calculated members from the Calculated Member pane onto the Data pane.</span></span> <span data-ttu-id="fc52e-127">Se o botão de alternância **Executar Automaticamente** na barra de ferramentas estiver ativo, o designer de consulta executará a consulta toda vez que você soltar um objeto no painel Dados.</span><span class="sxs-lookup"><span data-stu-id="fc52e-127">If the **AutoExecute** toggle button on the toolbar is on, the query designer runs the query every time you drop an object onto the Data pane.</span></span> <span data-ttu-id="fc52e-128">Se **Executar Automaticamente** estiver desativado, o designer de consulta não executará a consulta quando forem feitas alterações no painel Dados.</span><span class="sxs-lookup"><span data-stu-id="fc52e-128">If **AutoExecute** is off, the query designer does not run the query as you make changes to the Data pane.</span></span> <span data-ttu-id="fc52e-129">Você pode executar manualmente a consulta usando o botão **Executar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="fc52e-129">You can manually run the query using the **Run** button on the toolbar.</span></span>

### <a name="toolbar-for-the-graphical-query-designer-in-design-mode-toolbar"></a><span data-ttu-id="fc52e-130">Barra de ferramentas do Designer de Consultas Gráficas na barra de ferramentas do modo Design</span><span class="sxs-lookup"><span data-stu-id="fc52e-130">Toolbar for the Graphical Query Designer in Design Mode Toolbar</span></span>
 <span data-ttu-id="fc52e-131">A barra de ferramentas do designer de consulta fornece botões para ajudá-lo a criar consultas MDX por meio da interface gráfica.</span><span class="sxs-lookup"><span data-stu-id="fc52e-131">The query designer toolbar provides buttons to help you design MDX queries using the graphical interface.</span></span> <span data-ttu-id="fc52e-132">A tabela a seguir descreve os botões e as respectivas funções.</span><span class="sxs-lookup"><span data-stu-id="fc52e-132">The following table describes the buttons and their functions.</span></span>

|<span data-ttu-id="fc52e-133">Botão</span><span class="sxs-lookup"><span data-stu-id="fc52e-133">Button</span></span>|<span data-ttu-id="fc52e-134">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="fc52e-134">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="fc52e-135">**Editar como Texto**</span><span class="sxs-lookup"><span data-stu-id="fc52e-135">**Edit As Text**</span></span>|<span data-ttu-id="fc52e-136">Alterna entre o designer de consulta baseado em texto e o designer de consultas gráficas.</span><span class="sxs-lookup"><span data-stu-id="fc52e-136">Toggle between the text-based query designer and the graphical query designer.</span></span> <span data-ttu-id="fc52e-137">Não disponível para esse tipo de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fc52e-137">Not available for this data source type.</span></span>|
|<span data-ttu-id="fc52e-138">**Importaçãoação**</span><span class="sxs-lookup"><span data-stu-id="fc52e-138">**Import**</span></span>|<span data-ttu-id="fc52e-139">Importa uma consulta existente de um arquivo de definição de relatório (.rdl) no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fc52e-139">Import an existing query from a report definition (.rdl) file on the file system.</span></span> <span data-ttu-id="fc52e-140">Para obter mais informações, consulte [Conjuntos de dados inseridos e compartilhados de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fc52e-140">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>|
|<span data-ttu-id="fc52e-141">![Atualizar campos de conjunto de dados](../media/rsqdicon-refreshfields.gif "Atualizar campos de conjunto de dados")</span><span class="sxs-lookup"><span data-stu-id="fc52e-141">![Refresh dataset fields](../media/rsqdicon-refreshfields.gif "Refresh dataset fields")</span></span>|<span data-ttu-id="fc52e-142">Atualiza metadados na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fc52e-142">Refresh metadata from the data source.</span></span>|
|<span data-ttu-id="fc52e-143">![Adicionar membro calculado](../../analysis-services/media/rsqdicon-addcalculatedmember.gif "Adicionar Membro Calculado")</span><span class="sxs-lookup"><span data-stu-id="fc52e-143">![Add calculated member](../../analysis-services/media/rsqdicon-addcalculatedmember.gif "Add calculated member")</span></span>|<span data-ttu-id="fc52e-144">Exibe a caixa de diálogo **Construtor de Membro Calculado** .</span><span class="sxs-lookup"><span data-stu-id="fc52e-144">Display the **Calculated Member Builder** dialog box.</span></span>|
|<span data-ttu-id="fc52e-145">![Alternar para mostrar células vazias](../../analysis-services/media/rsqdicon-showemptycells.gif "Alternar para mostrar células vazias")</span><span class="sxs-lookup"><span data-stu-id="fc52e-145">![Toggle for show empty cells](../../analysis-services/media/rsqdicon-showemptycells.gif "Toggle for show empty cells")</span></span>|<span data-ttu-id="fc52e-146">Alterna entre mostrar ou não células vazias no painel Dados.</span><span class="sxs-lookup"><span data-stu-id="fc52e-146">Switch between showing and not showing empty cells in the Data pane.</span></span> <span data-ttu-id="fc52e-147">(Equivale a usar a cláusula NON EMPTY em MDX).</span><span class="sxs-lookup"><span data-stu-id="fc52e-147">(This is the equivalent to using the NON EMPTY clause in MDX).</span></span>|
|<span data-ttu-id="fc52e-148">![Executar a consulta automaticamente](../../analysis-services/media/rsqdicon-autoexecute.gif "Executar a consulta automaticamente")</span><span class="sxs-lookup"><span data-stu-id="fc52e-148">![AutoExecute the query](../../analysis-services/media/rsqdicon-autoexecute.gif "AutoExecute the query")</span></span>|<span data-ttu-id="fc52e-149">Executa automaticamente a consulta e mostra o resultado toda vez que é feita uma alteração, por exemplo, excluindo uma coluna no painel Dados.</span><span class="sxs-lookup"><span data-stu-id="fc52e-149">Automatically run the query and show the result every time a change is made, for example, deleting a column in the Data pane.</span></span> <span data-ttu-id="fc52e-150">Os resultados são mostrados no painel Dados.</span><span class="sxs-lookup"><span data-stu-id="fc52e-150">Results are shown in the Data pane.</span></span>|
|<span data-ttu-id="fc52e-151">![Delete (excluir)](../../analysis-services/media/rsqdicon-delete.gif "Excluir")</span><span class="sxs-lookup"><span data-stu-id="fc52e-151">![Delete](../../analysis-services/media/rsqdicon-delete.gif "Delete")</span></span>|<span data-ttu-id="fc52e-152">Exclui da consulta a coluna selecionada no painel Dados.</span><span class="sxs-lookup"><span data-stu-id="fc52e-152">Delete the selected column in the Data pane from the query.</span></span>|
|<span data-ttu-id="fc52e-153">![Ícone da caixa de diálogo Parâmetros de Consulta](../../analysis-services/media/iconqueryparameter.gif "Ícone da caixa de diálogo Parâmetros de Consulta")</span><span class="sxs-lookup"><span data-stu-id="fc52e-153">![Icon for the Query Parameters dialog box](../../analysis-services/media/iconqueryparameter.gif "Icon for the Query Parameters dialog box")</span></span>|<span data-ttu-id="fc52e-154">Exiba a caixa de diálogo **Variáveis** .</span><span class="sxs-lookup"><span data-stu-id="fc52e-154">Display the **Variables** dialog box.</span></span> <span data-ttu-id="fc52e-155">Esse botão é habilitado somente quando o cubo selecionado é um cubo de Consulta (porque somente os cubos de consulta oferecem suporte a variáveis).</span><span class="sxs-lookup"><span data-stu-id="fc52e-155">This button is enabled only when the selected cube is a Query cube (because only query cubes support variables).</span></span> <span data-ttu-id="fc52e-156">Quando você atribui um valor padrão a uma variável, um parâmetro de relatório correspondente é criado.</span><span class="sxs-lookup"><span data-stu-id="fc52e-156">When you assign a default value to a variable, a corresponding report parameter is created.</span></span>|
|<span data-ttu-id="fc52e-157">![Executar a consulta](../../analysis-services/media/rsqdicon-run.gif "Executar a consulta")</span><span class="sxs-lookup"><span data-stu-id="fc52e-157">![Run the query](../../analysis-services/media/rsqdicon-run.gif "Run the query")</span></span>|<span data-ttu-id="fc52e-158">Executa a consulta e exibe os resultados no painel Dados.</span><span class="sxs-lookup"><span data-stu-id="fc52e-158">Run the query and display the results in the Data pane.</span></span>|
|<span data-ttu-id="fc52e-159">![Cancelar a consulta](../../analysis-services/media/rsqdicon-cancel.gif "Cancelar a consulta")</span><span class="sxs-lookup"><span data-stu-id="fc52e-159">![Cancel the query](../../analysis-services/media/rsqdicon-cancel.gif "Cancel the query")</span></span>|<span data-ttu-id="fc52e-160">Cancela a consulta.</span><span class="sxs-lookup"><span data-stu-id="fc52e-160">Cancel the query.</span></span>|
|<span data-ttu-id="fc52e-161">![Alternar para o modo Design](../../analysis-services/media/rsqdicon-designmode.gif "Alterna para o modo de design")</span><span class="sxs-lookup"><span data-stu-id="fc52e-161">![Switch to Design mode](../../analysis-services/media/rsqdicon-designmode.gif "Switch to Design mode")</span></span>|<span data-ttu-id="fc52e-162">Alterna entre o modo Design e o modo Consulta.</span><span class="sxs-lookup"><span data-stu-id="fc52e-162">Switch between Design mode and Query mode.</span></span>|

## <a name="graphical-query-designer-in-query-mode"></a><span data-ttu-id="fc52e-163">Designer de consultas gráficas no modo Consulta</span><span class="sxs-lookup"><span data-stu-id="fc52e-163">Graphical Query Designer in Query Mode</span></span>
 <span data-ttu-id="fc52e-164">Para alterar o designer de consultas gráficas para o modo Consulta, clique no botão de alternância **Modo Design** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="fc52e-164">To change the graphical query designer to Query mode, click the **Design Mode** toggle button on the toolbar.</span></span>

 <span data-ttu-id="fc52e-165">A figura a seguir indica as partes do designer de consulta no modo Consulta.</span><span class="sxs-lookup"><span data-stu-id="fc52e-165">The following figure indicates the parts of the query designer in Query mode.</span></span>

 <span data-ttu-id="fc52e-166">![Designer de consultas SAP BW MDX na Visualização da Consulta](../media/rsqd-dssapbw-mdx-querymode.gif "Designer de consultas SAP BW MDX na Visualização da Consulta")</span><span class="sxs-lookup"><span data-stu-id="fc52e-166">![SAP BW MDX query designer in query view](../media/rsqd-dssapbw-mdx-querymode.gif "SAP BW MDX query designer in query view")</span></span>

 <span data-ttu-id="fc52e-167">A tabela a seguir descreve a função de cada painel.</span><span class="sxs-lookup"><span data-stu-id="fc52e-167">The following table describes the function of each pane.</span></span>

|<span data-ttu-id="fc52e-168">Painel</span><span class="sxs-lookup"><span data-stu-id="fc52e-168">Pane</span></span>|<span data-ttu-id="fc52e-169">Função</span><span class="sxs-lookup"><span data-stu-id="fc52e-169">Function</span></span>|
|----------|--------------|
|<span data-ttu-id="fc52e-170">Botão Selecionar Cubo</span><span class="sxs-lookup"><span data-stu-id="fc52e-170">Select Cube button</span></span>|<span data-ttu-id="fc52e-171">Exibe o InfoCube, MultiProvider ou outro cubo selecionado no momento.</span><span class="sxs-lookup"><span data-stu-id="fc52e-171">Displays the currently selected InfoCube, MultiProvider, or other cube.</span></span>|
|<span data-ttu-id="fc52e-172">Painel Metadados/Funções</span><span class="sxs-lookup"><span data-stu-id="fc52e-172">Metadata/Functions pane</span></span>|<span data-ttu-id="fc52e-173">Exibe uma janela com guias que mostra uma lista de metadados ou funções disponíveis que pode ser usada para criar o texto de consulta.</span><span class="sxs-lookup"><span data-stu-id="fc52e-173">Displays a tabbed window that shows a list of available metadata or functions that can be used to build the query text.</span></span>|
|<span data-ttu-id="fc52e-174">Painel Variáveis</span><span class="sxs-lookup"><span data-stu-id="fc52e-174">Variables pane</span></span>|<span data-ttu-id="fc52e-175">Exibe as variáveis definidas no momento disponíveis para serem usadas na consulta.</span><span class="sxs-lookup"><span data-stu-id="fc52e-175">Displays the currently defined variables available for use in the query.</span></span>|
|<span data-ttu-id="fc52e-176">Painel Consulta</span><span class="sxs-lookup"><span data-stu-id="fc52e-176">Query pane</span></span>|<span data-ttu-id="fc52e-177">Exibe o texto da consulta atual.</span><span class="sxs-lookup"><span data-stu-id="fc52e-177">Displays the current query text.</span></span>|
|<span data-ttu-id="fc52e-178">Painel Resultado</span><span class="sxs-lookup"><span data-stu-id="fc52e-178">Result pane</span></span>|<span data-ttu-id="fc52e-179">Exibe os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="fc52e-179">Displays the results of the query.</span></span>|

 <span data-ttu-id="fc52e-180">No painel Metadados, você pode arrastar as principais figuras e dimensões da guia **Metadados** para o painel Consulta MDX; o nome técnico dos metadados é inserido no cursor.</span><span class="sxs-lookup"><span data-stu-id="fc52e-180">From the Metadata pane, you can drag key figures and dimensions from the **Metadata** tab onto the MDX Query pane; the technical name for the metadata is inserted at the cursor.</span></span> <span data-ttu-id="fc52e-181">Você pode arrastar as funções da guia **Funções** para o painel Consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="fc52e-181">You can drag functions from the **Functions** tab onto the MDX Query pane.</span></span> <span data-ttu-id="fc52e-182">Quando você executar a consulta, o painel Resultado exibirá os resultados da consulta MDX atual.</span><span class="sxs-lookup"><span data-stu-id="fc52e-182">When you execute the query, the Result pane displays the results for the current MDX query.</span></span>

 <span data-ttu-id="fc52e-183">Se seu cubo selecionado for uma consulta habilitada para Web; você será solicitado a definir valores padrão estáticos para as variáveis existentes.</span><span class="sxs-lookup"><span data-stu-id="fc52e-183">If your selected cube is a Web-enabled query, you will be prompted to set static default values for the existing variables.</span></span> <span data-ttu-id="fc52e-184">Em seguida, você pode arrastar as variáveis para o painel Consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="fc52e-184">You can then drag variables onto the MDX Query pane.</span></span>

 <span data-ttu-id="fc52e-185">Os painéis Metadados e Variável exibem nomes amigáveis.</span><span class="sxs-lookup"><span data-stu-id="fc52e-185">The Metadata and Variable panes display friendly names.</span></span> <span data-ttu-id="fc52e-186">Quando você solta os objetos no painel Consulta MDX, você verá os nomes técnicos necessários pela fonte de dados inseridos na consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="fc52e-186">When you drop the objects onto the MDX Query pane, you see the technical names needed by the data source entered into the MDX query.</span></span>

### <a name="toolbar-for-the-graphical-query-designer-in-query-mode"></a><span data-ttu-id="fc52e-187">Barra de ferramentas do Designer de Consultas Gráficas no modo Consulta</span><span class="sxs-lookup"><span data-stu-id="fc52e-187">Toolbar for the Graphical Query Designer in Query Mode</span></span>
 <span data-ttu-id="fc52e-188">A barra de ferramentas do designer de consulta fornece botões para ajudá-lo a criar consultas MDX por meio da interface gráfica.</span><span class="sxs-lookup"><span data-stu-id="fc52e-188">The query designer toolbar provides buttons to help you design MDX queries using the graphical interface.</span></span> <span data-ttu-id="fc52e-189">Os botões da barra de ferramentas são idênticos nos modos Design e Consulta, mas os botões a seguir não estão ativados no modo Consulta:</span><span class="sxs-lookup"><span data-stu-id="fc52e-189">The toolbar buttons are identical between Design mode and Query mode, but the following buttons are not enabled for Query mode:</span></span>

-   <span data-ttu-id="fc52e-190">**Editar como Texto**</span><span class="sxs-lookup"><span data-stu-id="fc52e-190">**Edit As Text**</span></span>

-   <span data-ttu-id="fc52e-191">**Adicionar membro calculado** (![Adicionar membro calculado](../../analysis-services/media/rsqdicon-addcalculatedmember.gif "Adicionar Membro Calculado"))</span><span class="sxs-lookup"><span data-stu-id="fc52e-191">**Add Calculated Member** (![Add calculated member](../../analysis-services/media/rsqdicon-addcalculatedmember.gif "Add calculated member"))</span></span>

-   <span data-ttu-id="fc52e-192">**Mostrar Células Vazias** (![Alternar para mostrar células vazias](../../analysis-services/media/rsqdicon-showemptycells.gif "Alternar para mostrar células vazias"))</span><span class="sxs-lookup"><span data-stu-id="fc52e-192">**Show Empty Cells** (![Toggle for show empty cells](../../analysis-services/media/rsqdicon-showemptycells.gif "Toggle for show empty cells"))</span></span>

-   <span data-ttu-id="fc52e-193">**Executar automaticamente** (![Executar a consulta automaticamente](../../analysis-services/media/rsqdicon-autoexecute.gif "Executar a consulta automaticamente"))</span><span class="sxs-lookup"><span data-stu-id="fc52e-193">**AutoExecute** (![AutoExecute the query](../../analysis-services/media/rsqdicon-autoexecute.gif "AutoExecute the query"))</span></span>

-   <span data-ttu-id="fc52e-194">**Excluir** (![Excluir](../../analysis-services/media/rsqdicon-delete.gif "Excluir"))</span><span class="sxs-lookup"><span data-stu-id="fc52e-194">**Delete** (![Delete](../../analysis-services/media/rsqdicon-delete.gif "Delete"))</span></span>

## <a name="see-also"></a><span data-ttu-id="fc52e-195">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fc52e-195">See Also</span></span>
 <span data-ttu-id="fc52e-196">[Criar um conjunto de um DataSet compartilhado ou um conjunto de &#40;inserido Construtor de relatórios e SSRS&#41;arquivo de](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) [configuração RSReportDesigner](../report-server/rsreportdesigner-configuration-file.md)</span><span class="sxs-lookup"><span data-stu-id="fc52e-196">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) [RSReportDesigner Configuration File](../report-server/rsreportdesigner-configuration-file.md)</span></span>

