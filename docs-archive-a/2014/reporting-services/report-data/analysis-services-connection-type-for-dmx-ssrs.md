---
title: Tipo de conexão do Analysis Services para DMX (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- parameters [Reporting Services], DMX
- Data Mining Prediction [Reporting Services]
- query view [Reporting Services]
- DMX [Reporting Services]
- design view [Reporting Services]
- data mining [Reporting Services]
- passing parameters [Reporting Services]
ms.assetid: 2de825e9-6d8a-4128-add0-da15dc6cea3e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c6d2c689689cde5c6c5ef4ffa8ab5c0e8737078
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569139"
---
# <a name="analysis-services-connection-type-for-dmx-ssrs"></a><span data-ttu-id="77557-102">Tipo de conexão Analysis Services para DMX (SSRS)</span><span class="sxs-lookup"><span data-stu-id="77557-102">Analysis Services Connection Type for DMX (SSRS)</span></span>
  <span data-ttu-id="77557-103">Ao criar um conjunto de dados usando uma fonte de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], o Designer de Relatórios exibirá o designer de consultas MDX (Multidimensional Expression) se ele detectar um cubo válido.</span><span class="sxs-lookup"><span data-stu-id="77557-103">When you create a dataset using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data source, Report Designer displays the Multidimensional Expression (MDX) query designer if it detects a valid cube.</span></span> <span data-ttu-id="77557-104">Se nenhum cubo for detectado, mas um modelo de mineração de dados estiver disponível, o Designer de Relatórios exibirá o designer de consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="77557-104">If no cube is detected, but a data mining model is available, Report Designer displays the Data Mining Extensions (DMX) query designer.</span></span> <span data-ttu-id="77557-105">Para alternar entre os designers MDX e DMX, clique no botão **Tipo de Comando DMX** (![Alterar para a exibição de linguagem de consulta DMX](../media/rsqdicon-commandtypedmx.gif "Alterar para o modo de exibição de linguagem de consulta DMX")) na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="77557-105">To switch between the MDX and DMX designers, click the **Command Type DMX** (![Change to DMX query language view](../media/rsqdicon-commandtypedmx.gif "Change to DMX query language view")) button on the toolbar.</span></span> <span data-ttu-id="77557-106">Use o Designer de Consulta DMX para criar de maneira interativa uma consulta DMX usando elementos gráficos.</span><span class="sxs-lookup"><span data-stu-id="77557-106">Use the DMX Query Designer to interactively build a DMX query using graphical elements.</span></span> <span data-ttu-id="77557-107">Para usar o Designer de Consulta DMX, a fonte de dados especificada já deve ter um modelo de mineração de dados que forneça os dados.</span><span class="sxs-lookup"><span data-stu-id="77557-107">To use DMX Query Designer, the data source that you specify must already have a data mining model that provides the data.</span></span> <span data-ttu-id="77557-108">Os resultados da consulta são convertidos em um conjunto de linhas bidimensional para ser usado no relatório.</span><span class="sxs-lookup"><span data-stu-id="77557-108">Query results are converted to a flattened rowset for use in the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77557-109">Você deve treinar seu modelo antes de criar seu relatório.</span><span class="sxs-lookup"><span data-stu-id="77557-109">You must train your model before designing your report.</span></span> <span data-ttu-id="77557-110">Para obter mais informações, consulte [Soluções de mineração de dados](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="77557-110">For more information, see [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="design-mode"></a><span data-ttu-id="77557-111">Modo Design</span><span class="sxs-lookup"><span data-stu-id="77557-111">Design Mode</span></span>  
 <span data-ttu-id="77557-112">O designer de consulta DMX é aberto no modo Design.</span><span class="sxs-lookup"><span data-stu-id="77557-112">The DMX query designer opens in Design mode.</span></span> <span data-ttu-id="77557-113">O modo Design inclui uma superfície de design gráfico usada para selecionar um único modelo de mineração de dados e tabela de entrada e uma grade usada para especificara a consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="77557-113">Design mode includes a graphical design surface used for selecting a single data mining model and input table, and a grid used for specifying the prediction query.</span></span> <span data-ttu-id="77557-114">Há dois outros modos no designer de consulta DMX: modo Consulta e Resultado.</span><span class="sxs-lookup"><span data-stu-id="77557-114">There are two other modes in DMX query designer: Query mode and Result mode.</span></span> <span data-ttu-id="77557-115">No modo Consulta, a grade do modo Design é substituída por um painel Consulta, no qual você pode usar para consultas do tipo DMX.</span><span class="sxs-lookup"><span data-stu-id="77557-115">In Query mode, the grid from Design mode is replaced with a Query pane, which you can use to type DMX queries.</span></span> <span data-ttu-id="77557-116">No modo Resultado, o conjunto de resultados retornado pela consulta é exibido em uma grade de dados.</span><span class="sxs-lookup"><span data-stu-id="77557-116">In Result mode, the result set returned by the query appears in a data grid.</span></span>  
  
 <span data-ttu-id="77557-117">Para alterar os modos do designer de consulta DMX, clique com o botão direito do mouse na superfície do design de consulta e selecione **Design**, **Consulta**ou **Resultado**.</span><span class="sxs-lookup"><span data-stu-id="77557-117">To change modes for the DMX query designer, right-click on the query design surface and select **Design**, **Query**, or **Result**.</span></span> <span data-ttu-id="77557-118">Para obter mais informações, consulte [Interface do usuário do Designer de Consultas DMX do Analysis Services](analysis-services-dmx-query-designer-user-interface.md) e [Recuperar dados de um modelo de mineração de dados &#40;DMX&#41; &#40;SSRS&#41;](retrieve-data-from-a-data-mining-model-dmx-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="77557-118">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md) and [Retrieve Data from a Data Mining Model &#40;DMX&#41; &#40;SSRS&#41;](retrieve-data-from-a-data-mining-model-dmx-ssrs.md).</span></span>  
  
## <a name="designing-a-prediction-query"></a><span data-ttu-id="77557-119">Criando uma consulta de previsão</span><span class="sxs-lookup"><span data-stu-id="77557-119">Designing a Prediction Query</span></span>  
 <span data-ttu-id="77557-120">O painel Design de Consulta do modo Design contém duas janelas: **Modelo de Mineração** e **Selecionar Tabela de Entrada**.</span><span class="sxs-lookup"><span data-stu-id="77557-120">The Query Design pane of the Design mode contains two windows: **Mining Model** and **Select Input Table**.</span></span> <span data-ttu-id="77557-121">Use a janela **Modelo de Mineração** para selecionar o modelo de mineração a ser usado na consulta.</span><span class="sxs-lookup"><span data-stu-id="77557-121">Use the **Mining Model** window to select the mining model to use in your query.</span></span> <span data-ttu-id="77557-122">Use a janela **Selecionar Tabela de Entrada** para selecionar a tabela na qual suas previsões devem se basear.</span><span class="sxs-lookup"><span data-stu-id="77557-122">Use the **Select Input Table** window to select the table on which to base your predictions.</span></span> <span data-ttu-id="77557-123">Se quiser usar uma consulta singleton em vez de uma tabela de entrada, clique com o botão direito do mouse no painel Design de Consulta e selecione **Consulta Singleton**.</span><span class="sxs-lookup"><span data-stu-id="77557-123">If you want to use a singleton query instead of an input table, right-click in the Query Design pane and select **Singleton Query**.</span></span> <span data-ttu-id="77557-124">A janela **Selecionar Tabela de Entrada** é substituída por uma janela **Entrada de Consulta Singleton** .</span><span class="sxs-lookup"><span data-stu-id="77557-124">The **Select Input Table** window is replaced with a **Singleton Query Input** window.</span></span>  
  
 <span data-ttu-id="77557-125">No modo Design, arraste os campos das janelas **Modelo de Mineração** e **Selecionar Tabela de Entrada** para a coluna **Campo** no painel Grade.</span><span class="sxs-lookup"><span data-stu-id="77557-125">In Design mode, drag fields from the **Mining Model** and **Select Input Table** windows to the **Field** column in the Grid pane.</span></span> <span data-ttu-id="77557-126">Você também pode preencher as colunas restantes para especificar um alias, mostrar o campo nos resultados, agrupar os campos e especificar um operador para restringir o valor do campo para um determinado critério ou argumento.</span><span class="sxs-lookup"><span data-stu-id="77557-126">You can also fill in the remaining columns to specify an alias, to show the field in the results, to group fields together, and to specify an operator to restrict the field value to a given criteria or argument.</span></span> <span data-ttu-id="77557-127">Se você estiver no modo Consulta, crie a consulta DMX arrastando os campos para o painel Consulta.</span><span class="sxs-lookup"><span data-stu-id="77557-127">If you are in Query mode, build the DMX query by dragging fields to the Query pane.</span></span>  
  
## <a name="using-parameters"></a><span data-ttu-id="77557-128">Usando parâmetros</span><span class="sxs-lookup"><span data-stu-id="77557-128">Using Parameters</span></span>  
 <span data-ttu-id="77557-129">Você pode passar parâmetros de relatórios para um parâmetro de consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="77557-129">You can pass report parameters to a DMX query parameter.</span></span> <span data-ttu-id="77557-130">Para fazer isso, você deve adicionar um parâmetro à sua consulta DMX, definir os parâmetros de consulta na caixa de diálogo **Parâmetros de Consulta** e modificar os parâmetros de relatório associados.</span><span class="sxs-lookup"><span data-stu-id="77557-130">To do this, you must add a parameter to your DMX query, define the query parameters in the **Query Parameters** dialog box, and then modify the associated report parameters.</span></span> <span data-ttu-id="77557-131">Para definir um parâmetro de consulta, clique no botão **Parâmetros de Consulta** (![Ícone da caixa de diálogo Parâmetros de Consulta](../media/iconqueryparameter.gif "Ícone da caixa de diálogo Parâmetros de Consulta")) na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="77557-131">To define a query parameter, click the **Query Parameters** (![Icon for the Query Parameters dialog box](../media/iconqueryparameter.gif "Icon for the Query Parameters dialog box")) button on the toolbar.</span></span> <span data-ttu-id="77557-132">Para exibir instruções sobre como definir parâmetros em uma consulta DMX, consulte [Definir parâmetros no Designer de Consulta MDX do Analysis Services &#40;Construtor de Relatórios e SSRS&#41;](define-parameters-in-the-mdx-query-designer-for-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="77557-132">To view instructions about defining parameters in a DMX query, see [Define Parameters in the MDX Query Designer for Analysis Services &#40;Report Builder and SSRS&#41;](define-parameters-in-the-mdx-query-designer-for-analysis-services.md).</span></span>  
  
 <span data-ttu-id="77557-133">Para obter mais informações sobre como gerenciar a relação entre os parâmetros de relatório e de consulta, consulte [Associar um parâmetro de consulta a um parâmetro de relatório &#40;Construtor de Relatórios e SSRS&#41;](associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="77557-133">For more information about how to manage the relationship between report parameters and query parameters, see [Associate a Query Parameter with a Report Parameter &#40;Report Builder and SSRS&#41;](associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="77557-134">Para obter mais informações sobre parâmetros, consulte [Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="77557-134">For more information about parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77557-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="77557-135">See Also</span></span>  
 <span data-ttu-id="77557-136">[Soluções de mineração de dados](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions) </span><span class="sxs-lookup"><span data-stu-id="77557-136">[Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions) </span></span>  
 <span data-ttu-id="77557-137">[Ferramentas de design de consulta no Report Designer SQL Server Data Tools &#40;SSRS&#41;](query-design-tools-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="77557-137">[Query Design Tools in Report Designer SQL Server Data Tools &#40;SSRS&#41;](query-design-tools-ssrs.md) </span></span>  
 [<span data-ttu-id="77557-138">Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="77557-138">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  