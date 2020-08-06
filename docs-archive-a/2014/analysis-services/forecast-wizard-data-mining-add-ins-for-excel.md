---
title: Assistente de previsão (suplementos de mineração de dados para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- forecasting [data mining]
- time series [data mining]
ms.assetid: c5b33f75-42d4-4598-89e7-94815c142ce6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c3fae97bf1c36154d8ae378840014f2fb997afd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570976"
---
# <a name="forecast-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="65cf3-102">Assistente de Previsão (Suplementos de Mineração de Dados para Excel)</span><span class="sxs-lookup"><span data-stu-id="65cf3-102">Forecast Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="65cf3-103">![Assistente para Associação na faixa de opções Mineração de Dados](media/dmc-forecast.gif "Assistente para Associação na faixa de opções Mineração de Dados")</span><span class="sxs-lookup"><span data-stu-id="65cf3-103">![Associate wizard in Data Mining ribbon](media/dmc-forecast.gif "Associate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="65cf3-104">O assistente de Previsão o ajuda a prever valores em uma série temporal.</span><span class="sxs-lookup"><span data-stu-id="65cf3-104">The Forecast wizard helps you predict values in a time series.</span></span> <span data-ttu-id="65cf3-105">O assistente de previsão utiliza o algoritmo Série Temporal da [!INCLUDE[msCoName](../includes/msconame-md.md)] ou MTS, que é um algoritmo de regressão para uso na previsão de colunas contínuas, como vendas de produto.</span><span class="sxs-lookup"><span data-stu-id="65cf3-105">The Forecast wizard uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm, which is a regression algorithm for use in predicting continuous columns, such as product sales.</span></span>  
  
 <span data-ttu-id="65cf3-106">Cada modelo de previsão deve conter uma série de casos, que é a coluna que faz distinção entre os pontos em uma sequência.</span><span class="sxs-lookup"><span data-stu-id="65cf3-106">Each forecasting model must contain a case series, which is the column that distinguishes between points in a sequence.</span></span> <span data-ttu-id="65cf3-107">Por exemplo, se você estiver usando dados históricos para prever as vendas em um período de vários meses, usará uma coluna contendo uma série de datas como a série de casos.</span><span class="sxs-lookup"><span data-stu-id="65cf3-107">For example, if you are using historical data to forecast sales over a period of several months, you would use a column containing a series of dates as the case series.</span></span>  
  
 <span data-ttu-id="65cf3-108">Você pode criar previsões de um modelo de previsão sem fornecer novos dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="65cf3-108">You can create predictions from a forecasting model without providing new input data.</span></span>  
  
 <span data-ttu-id="65cf3-109">A [previsão &#40;ferramentas de análise de tabela para&#41;](forecast-table-analysis-tools-for-excel.md) ferramenta do Excel, na faixa de quadro **analisar** , também permite que você crie modelos de previsão, mas é menos personalizável e só pode usar dados em tabelas do Excel.</span><span class="sxs-lookup"><span data-stu-id="65cf3-109">The [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) tool, in the **Analyze** ribbon, also lets you create forecasting models, but it is less customizable and can only use data in Excel tables.</span></span>  
  
## <a name="using-the-forecast-wizard"></a><span data-ttu-id="65cf3-110">Usando o Assistente de Previsão</span><span class="sxs-lookup"><span data-stu-id="65cf3-110">Using the Forecast Wizard</span></span>  
  
1.  <span data-ttu-id="65cf3-111">Na faixa de faixas de **mineração de dados** , clique em **previsão**.</span><span class="sxs-lookup"><span data-stu-id="65cf3-111">In the **Data Mining** ribbon, click **Forecast**.</span></span>  
  
2.  <span data-ttu-id="65cf3-112">Em **selecionar dados de origem**, escolha a tabela do Excel, o intervalo ou a fonte de dados externa para usar como entradas.</span><span class="sxs-lookup"><span data-stu-id="65cf3-112">In the **Select Source Data**, choose the Excel table, range, or external data source to use as inputs.</span></span>  
  
     <span data-ttu-id="65cf3-113">Se você usar uma fonte de dados externa, poderá definir a exibição personalizada ou as consultas e salvá-la como uma fonte de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65cf3-113">If you use an external data source, you can define custom view or queries and save it as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="65cf3-114">Na página **previsão** , para carimbo de data/ **hora**, selecione uma coluna que contenha um valor numérico exclusivo (isso inclui valores de dados e de hora) que podem ser usados como a série de casos.</span><span class="sxs-lookup"><span data-stu-id="65cf3-114">On the **Forecasting** page, for **Time stamp**, select a column that contains unique numeric value (this includes date and time values) that can be used as the case series.</span></span> <span data-ttu-id="65cf3-115">A fonte de dados deve ser classificada em ordem crescente por essa coluna.</span><span class="sxs-lookup"><span data-stu-id="65cf3-115">The data source must be sorted in ascending order by this column.</span></span>  
  
     <span data-ttu-id="65cf3-116">Se os dados não tiverem essa coluna, você poderá usar a opção \<no time stamp> .</span><span class="sxs-lookup"><span data-stu-id="65cf3-116">If your data does not have such a column, you can use the option \<no time stamp>.</span></span> <span data-ttu-id="65cf3-117">O assistente adicionará uma coluna de ordem exclusiva para os dados de entrada; em virtude disso, você deverá assegurar que os dados sejam classificados da maneira desejada antes de executar o assistente e escolher essa opção.</span><span class="sxs-lookup"><span data-stu-id="65cf3-117">The wizard will add a unique order column for the input data; therefore, you must make sure that the data is sorted the way you want before running the wizard and choosing this option.</span></span>  
  
4.  <span data-ttu-id="65cf3-118">Opcionalmente, você pode clicar em **parâmetros** e personalizar o comportamento do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="65cf3-118">Optionally, you can click **Parameters** and customize the behavior of the mining model.</span></span>  
  
     <span data-ttu-id="65cf3-119">Modelos de previsão dão suporte a vários algoritmos diferentes:</span><span class="sxs-lookup"><span data-stu-id="65cf3-119">Forecasting models support several different algorithms:</span></span>  
  
    -   <span data-ttu-id="65cf3-120">ARIMA</span><span class="sxs-lookup"><span data-stu-id="65cf3-120">ARIMA</span></span>  
  
    -   <span data-ttu-id="65cf3-121">ARTXP (um tipo de modelo de regressão)</span><span class="sxs-lookup"><span data-stu-id="65cf3-121">ARTXP (a type of regression model)</span></span>  
  
    -   <span data-ttu-id="65cf3-122">ARTXP e ARIMA combinados</span><span class="sxs-lookup"><span data-stu-id="65cf3-122">ARTXP and ARIMA combined</span></span>  
  
     <span data-ttu-id="65cf3-123">Para obter informações sobre as diferenças, consulte [referência técnica do algoritmo do Microsoft Time Series](data-mining/microsoft-time-series-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="65cf3-123">For information about the differences, see [Microsoft Time Series Algorithm Technical Reference](data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
     <span data-ttu-id="65cf3-124">Você também pode adicionar dicas de periodicidade, especificar opções de atenuação e personalizar opções de regressão para o modelo.</span><span class="sxs-lookup"><span data-stu-id="65cf3-124">You can also add periodicity hints, specify smoothing options, and customize regression options for the model.</span></span>  
  
5.  <span data-ttu-id="65cf3-125">Na página **concluir** , forneça um nome descritivo para seu conjunto de dados e modelo e defina as seguintes opções que controlam como você trabalha com o modelo concluído:</span><span class="sxs-lookup"><span data-stu-id="65cf3-125">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="65cf3-126">**Procurar modelo**.</span><span class="sxs-lookup"><span data-stu-id="65cf3-126">**Browse model**.</span></span> <span data-ttu-id="65cf3-127">Quando essa opção é selecionada, assim que o assistente termina de processar o modelo, ele abre uma janela de **procura** para ajudá-lo a explorar os resultados.</span><span class="sxs-lookup"><span data-stu-id="65cf3-127">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="65cf3-128">O conteúdo do visualizador depende do tipo de modelo que você criou.</span><span class="sxs-lookup"><span data-stu-id="65cf3-128">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="65cf3-129">Para obter mais informações, consulte [navegando em um modelo de previsão](browsing-a-forecasting-model.md).</span><span class="sxs-lookup"><span data-stu-id="65cf3-129">For more information, see [Browsing a Forecasting Model](browsing-a-forecasting-model.md).</span></span>  
  
    -   <span data-ttu-id="65cf3-130">**Habilitar detalhamento**.</span><span class="sxs-lookup"><span data-stu-id="65cf3-130">**Enable drillthrough**.</span></span> <span data-ttu-id="65cf3-131">Selecione esta opção para visualizar os dados subjacentes do modelo finalizado.</span><span class="sxs-lookup"><span data-stu-id="65cf3-131">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="65cf3-132">Essa opção estará disponível somente se você criar um modelo de Árvore de Decisão.</span><span class="sxs-lookup"><span data-stu-id="65cf3-132">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="65cf3-133">**Use o modelo temporário**.</span><span class="sxs-lookup"><span data-stu-id="65cf3-133">**Use temporary model**.</span></span> <span data-ttu-id="65cf3-134">Se você selecionar esta opção, o modelo não será salvo no servidor.</span><span class="sxs-lookup"><span data-stu-id="65cf3-134">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="65cf3-135">Os modelos temporários serão excluídos quando você fechar o Excel.</span><span class="sxs-lookup"><span data-stu-id="65cf3-135">Temporary models are deleted when you close Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="65cf3-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65cf3-136">Requirements</span></span>  
 <span data-ttu-id="65cf3-137">Os dados devem incluir pelo menos uma coluna que possa ser usada como a série temporal.</span><span class="sxs-lookup"><span data-stu-id="65cf3-137">Your data should include at least one column that can be used as the time series.</span></span> <span data-ttu-id="65cf3-138">Os valores nesta coluna devem ser exclusivos e contínuos, ou seja, não deve haver intervalos.</span><span class="sxs-lookup"><span data-stu-id="65cf3-138">The values in this column should be unique and continuous - that is, there should be no gaps.</span></span> <span data-ttu-id="65cf3-139">Antes de executar o assistente, classifique os dados pela coluna da série temporal em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="65cf3-139">Before running the wizard, sort the data by the time series column in ascending order.</span></span>  
  
 <span data-ttu-id="65cf3-140">Se os dados não incluírem uma coluna de data ou hora, você poderá atribuir uma série numérica arbitrária ou deixar o assistente criar uma.</span><span class="sxs-lookup"><span data-stu-id="65cf3-140">If your data does not include a time or date column, you can assign an arbitrary numeric series, or let the wizard create one.</span></span> <span data-ttu-id="65cf3-141">Se você permitir que o assistente crie a coluna da ordem de série, verifique se as outras colunas são classificadas na ordem desejada antes de iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="65cf3-141">F you let the wizard create the series order column, make sure the other columns are sorted in the worder you want them before starting the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65cf3-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="65cf3-142">See Also</span></span>  
 <span data-ttu-id="65cf3-143">[Criando um modelo de mineração de dados](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="65cf3-143">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="65cf3-144">[Previsão de &#40;ferramentas de análise de tabela para Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="65cf3-144">[Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span></span>  
 [<span data-ttu-id="65cf3-145">Procurando um modelo de previsão</span><span class="sxs-lookup"><span data-stu-id="65cf3-145">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
  
