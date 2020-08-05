---
title: Escolher um tipo de gráfico de precisão e definir opções de gráfico | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services]
- mining models [Analysis Services], validating
- classification accuracy [data mining]
- accuracy testing [data mining]
ms.assetid: bd24dd4a-624f-478a-9c94-b1361e857680
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33c2b5e8a1e228a86328ef6df1b636742d3614ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572856"
---
# <a name="choose-an-accuracy-chart-type-and-set-chart-options"></a><span data-ttu-id="f82a9-102">Escolher um tipo de gráfico de precisão e definir opções de gráfico</span><span class="sxs-lookup"><span data-stu-id="f82a9-102">Choose an Accuracy Chart Type and Set Chart Options</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="f82a9-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]fornece vários métodos para determinar a validade de seus modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="f82a9-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides multiple methods for determining the validity of your mining models.</span></span> <span data-ttu-id="f82a9-104">O tipo de gráfico de precisão que você pode criar para cada modelo ou estrutura depende destes fatores:</span><span class="sxs-lookup"><span data-stu-id="f82a9-104">The type of accuracy chart that you can create for each model or structure depends on these factors:</span></span>  
  
-   <span data-ttu-id="f82a9-105">O tipo de algoritmo que foi usado na criação do modelo</span><span class="sxs-lookup"><span data-stu-id="f82a9-105">The type of algorithm that was used to create the model</span></span>  
  
-   <span data-ttu-id="f82a9-106">O tipo de dados do atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="f82a9-106">The data type of the predictable attribute</span></span>  
  
-   <span data-ttu-id="f82a9-107">O número de atributos previsíveis para medir</span><span class="sxs-lookup"><span data-stu-id="f82a9-107">The number of predictable attributes to measure</span></span>  
  
 <span data-ttu-id="f82a9-108">Este tópico fornece uma visão geral dos diferentes gráficos de precisão.</span><span class="sxs-lookup"><span data-stu-id="f82a9-108">This topic provides an overview of the different accuracy charts.</span></span>  
  
 <span data-ttu-id="f82a9-109">**Observação** os gráficos e suas definição não são salvos.</span><span class="sxs-lookup"><span data-stu-id="f82a9-109">**Note** Charts and their definitions are not saved.</span></span> <span data-ttu-id="f82a9-110">Se você fechar a janela que contém um gráfico, terá que criá-lo novamente.</span><span class="sxs-lookup"><span data-stu-id="f82a9-110">If you close the window that contains a chart, you must create the chart again.</span></span>  
  
## <a name="accuracy-chart-types"></a><span data-ttu-id="f82a9-111">Tipos de gráfico de precisão</span><span class="sxs-lookup"><span data-stu-id="f82a9-111">Accuracy Chart Types</span></span>  
 <span data-ttu-id="f82a9-112">Dependendo do tipo de gráfico escolhido, você tem a possibilidade de configurar mais as opções, navegar pelo gráfico, copiar o gráfico na área de transferência e trabalhar com os dados no Excel.</span><span class="sxs-lookup"><span data-stu-id="f82a9-112">Depending on the chart type that you choose, you have the ability to further configure options, to browse the chart, or copy the chart to the Clipboard and work with the data in Excel.</span></span>  
  
#### <a name="lift-chart"></a><span data-ttu-id="f82a9-113">Gráfico de comparação de precisão</span><span class="sxs-lookup"><span data-stu-id="f82a9-113">Lift chart</span></span>  
 <span data-ttu-id="f82a9-114">Depois de configurar as opções para os modelos e os dados de teste, clique na guia **Gráfico de Comparação de Precisão** para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="f82a9-114">After you have configured the options for the models and the testing data, click the **Lift Chart** tab to view the results.</span></span> <span data-ttu-id="f82a9-115">Você também pode copiar o gráfico na área de transferência ou exibir os detalhes das linhas de tendência individuais ou pontos de dados na Legenda de Mineração.</span><span class="sxs-lookup"><span data-stu-id="f82a9-115">You can also copy the chart to the Clipboard, or view details of individual trend lines or data points in the Mining Legend.</span></span>  
  
#### <a name="profit-chart"></a><span data-ttu-id="f82a9-116">Gráfico de ganho</span><span class="sxs-lookup"><span data-stu-id="f82a9-116">Profit Chart</span></span>  
 <span data-ttu-id="f82a9-117">Depois de configurar as opções para os modelos e os dados de teste, clique na guia **Gráfico de Comparação de Precisão** , selecione **Gráfico de Ganho** na lista **Tipo de Gráfico** para definir as opções do gráfico de ganho e, em seguida, clique em **OK** para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="f82a9-117">After you have configured the options for the models and the testing data, click the **Lift Chart** tab, select **Profit Chart** from the **Chart Type** list to set profit chart options, and then click **OK** to view the results.</span></span>  
  
 <span data-ttu-id="f82a9-118">Você pode usar a caixa de diálogo **Configurações do Gráfico de Ganho** quantas vezes desejar para testar diferentes opções de custo e exibir novamente o gráfico.</span><span class="sxs-lookup"><span data-stu-id="f82a9-118">You can use the **Profit Chart Settings** dialog box as many times as you want to try different cost options and redisplay the chart.</span></span> <span data-ttu-id="f82a9-119">O Legenda de Mineração contém informações detalhadas sobre o ganho estimado para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="f82a9-119">The Mining Legend contains detailed information about the estimated profit for each model.</span></span> <span data-ttu-id="f82a9-120">Você também pode copiar o gráfico e seus conteúdo da Legenda de Mineração para a área de transferência para trabalhar com eles no Excel.</span><span class="sxs-lookup"><span data-stu-id="f82a9-120">You can also copy the chart and the contents of the Mining Legend to the Clipboard to work with it in Excel.</span></span>  
  
#### <a name="scatter-plot"></a><span data-ttu-id="f82a9-121">Dispersão</span><span class="sxs-lookup"><span data-stu-id="f82a9-121">Scatter Plot</span></span>  
 <span data-ttu-id="f82a9-122">Se tiver selecionado o tipo de modelo apropriado, ao clicar na guia **Gráfico de Comparação de Precisão** , o tipo do gráfico será definido automaticamente como **Dispersão** e uma dispersão será exibida.</span><span class="sxs-lookup"><span data-stu-id="f82a9-122">If you have selected the appropriate type of model, when you click the **Lift Chart** tab, the chart type is automatically set to **Scatter Plot** and a scatter plot is displayed.</span></span> <span data-ttu-id="f82a9-123">Não é possível fazer nenhuma configuração adicional.</span><span class="sxs-lookup"><span data-stu-id="f82a9-123">No further configuration is possible.</span></span> <span data-ttu-id="f82a9-124">Você também pode copiar o gráfico para a área de transferência e colar o gráfico no Excel ou em outro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f82a9-124">You can also copy the chart to the Clipboard and paste the chart as a graphic into Excel or another application.</span></span>  
  
#### <a name="classification-matrix"></a><span data-ttu-id="f82a9-125">Matriz de classificação</span><span class="sxs-lookup"><span data-stu-id="f82a9-125">Classification Matrix</span></span>  
 <span data-ttu-id="f82a9-126">Para obter uma matriz de classificação, use a guia **Seleção de Entrada** para selecionar os modelos e os dados de teste. Depois, clique na guia **Matriz de Classificação** para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="f82a9-126">For a classification matrix, use the **Input Selection** tab to choose the models and the testing data, and then click the **Classification Matrix** tab to view the results.</span></span>  
  
 <span data-ttu-id="f82a9-127">Os conteúdos de uma matriz de classificação são os mesmos para todos os tipos de modelo e não podem ser configurados.</span><span class="sxs-lookup"><span data-stu-id="f82a9-127">The contents of a classification matrix are the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="f82a9-128">Você pode copiar os dados no gráfico para a área de transferência e então trabalhar com eles no Excel.</span><span class="sxs-lookup"><span data-stu-id="f82a9-128">You can copy the data in the chart to the Clipboard and then work with it in Excel.</span></span>  
  
#### <a name="cross-validation-report"></a><span data-ttu-id="f82a9-129">Relatório de validação cruzada</span><span class="sxs-lookup"><span data-stu-id="f82a9-129">Cross-Validation Report</span></span>  
 <span data-ttu-id="f82a9-130">Para obter um relatório de validação cruzada, depois de selecionar uma estrutura ou um modelo de mineração no Gerenciador de Soluções, clique na guia **Validação Cruzada** , configure as opções relevantes e depois clique em **Obter Resultados** para gerar o relatório.</span><span class="sxs-lookup"><span data-stu-id="f82a9-130">For a cross-validation report, after you have selected a mining structure or mining model in Solution Explorer, click the **Cross Validation** tab, configure all relevant options, and then click **Get Results** to generate the report.</span></span> <span data-ttu-id="f82a9-131">Não é possível fazer nenhuma configuração adicional.</span><span class="sxs-lookup"><span data-stu-id="f82a9-131">No further configuration is possible.</span></span>  
  
 <span data-ttu-id="f82a9-132">O formato do relatório de validação cruzada é o mesmo para todos os tipos de modelo e não pode ser configurado.</span><span class="sxs-lookup"><span data-stu-id="f82a9-132">The format of the cross-validation report is the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="f82a9-133">Entretanto, o conteúdo do relatório difere dependendo do tipo de modelo que você está analisando e do tipo de dados do atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="f82a9-133">However, the content of the report differs depending on the type of model that you are analyzing, and the data type of the predictable attribute.</span></span> <span data-ttu-id="f82a9-134">Também é possível copiar os resultados do relatório para a área de transferência e trabalhar com os dados no Excel.</span><span class="sxs-lookup"><span data-stu-id="f82a9-134">You can also copy the results of the report to the Clipboard and work with the data in Excel.</span></span>  
  
  
