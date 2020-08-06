---
title: Adicionando uma exibição da fonte de dados para previsão (tutorial de mineração de dados intermediários) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2665040a-1291-4064-ba01-f458637dda57
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 9424988efa6a9856f4ef0d558992fc90ac303861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683218"
---
# <a name="adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial"></a><span data-ttu-id="6f9ad-102">Adicionando uma exibição da fonte de dados para previsão (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="6f9ad-102">Adding a Data Source View for Forecasting (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="6f9ad-103">Nesta tarefa, você adiciona uma exibição da fonte de dados que será usada no cenário de previsão.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-103">In this task, you add a data source view that will be used for the forecasting scenario.</span></span> <span data-ttu-id="6f9ad-104">Um modelo de previsão exige que os dados contenham uma coluna que possa ser usada na identificação das etapas de uma série temporal.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-104">A forecasting model requires that the data contains a column that can be used to identify steps in a time series.</span></span> <span data-ttu-id="6f9ad-105">Se você planeja analisar várias séries de dados, todas elas deverão terminar na mesma data ou período.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-105">If you plan to analyze multiple series of data, all series must end on the same date or time step.</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="6f9ad-106">Para adicionar uma exibição da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="6f9ad-106">To add a data source view</span></span>  
  
1.  <span data-ttu-id="6f9ad-107">Em Gerenciador de Soluções, clique com o botão direito do mouse em **exibições da fonte de dados**e selecione **nova exibição da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-107">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="6f9ad-108">Na página **Bem-vindo ao Assistente de Exibição da Fonte de Dados** , clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-108">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="6f9ad-109">Na página **selecionar uma fonte de dados** , em **fontes de dados relacionais**, selecione a [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-109">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source.</span></span> <span data-ttu-id="6f9ad-110">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-110">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6f9ad-111">Se você não tiver essa fonte de dados, poderá encontrar as etapas para criar a fonte de dados no [tutorial de mineração de dados básico](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="6f9ad-111">If you do not have this data source, you can find the steps to create the data source in the [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
4.  <span data-ttu-id="6f9ad-112">Na página **selecionar tabelas e exibições** , selecione a tabela, vTimeSeries (dbo) e clique na seta para a direita para adicioná-la à exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-112">On the **Select Tables and Views** page, select the table, vTimeSeries (dbo), and then click the right arrow to add it to the data source view.</span></span>  
  
5.  <span data-ttu-id="6f9ad-113">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="6f9ad-114">Na página **concluindo o assistente** , por padrão, a exibição da fonte de dados é denominada [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f9ad-114">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="6f9ad-115">Altere o nome para **SalesByRegion**e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-115">Change the name to **SalesByRegion**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="6f9ad-116">O designer de exibição da fonte de dados é aberto e a exibição da fonte de dados **SalesByRegion** é exibida.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-116">Data Source View Designer opens and the **SalesByRegion** data source view appears.</span></span>  
  
## <a name="working-with-the-data-source-view"></a><span data-ttu-id="6f9ad-117">Trabalhando com a exibição da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="6f9ad-117">Working with the Data Source View</span></span>  
 <span data-ttu-id="6f9ad-118">Depois de criar a exibição da fonte de dados, será possível explorar os dados das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="6f9ad-118">After you have created the data source view, you can explore the data in the following ways:</span></span>  
  
-   <span data-ttu-id="6f9ad-119">Clique com o botão direito do mouse na tabela vTimeSeries no designer e selecione **explorar dados** para abrir a tabela selecionada em uma grade.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-119">Right-click the table vTimeSeries in the designer, and select **Explore Data** to open the selected table in a grid.</span></span>  
  
-   <span data-ttu-id="6f9ad-120">Clique em **Opções de amostragem** e use a caixa de diálogo opções de exploração de **dados** para alterar o método de amostragem.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-120">Click **Sampling options** and then use the **Data Exploration Options** dialog box to change the sampling method.</span></span> <span data-ttu-id="6f9ad-121">Clique em **Atualizar** para carregar os dados na tabela usando as novas configurações de opção.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-121">Click **Refresh** to load data in the table using the new option settings.</span></span> <span data-ttu-id="6f9ad-122">Por exemplo, você pode especificar o número de linhas a serem geradas no exemplo ou escolher as n linhas principais.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-122">For example, you could specify the number of rows to output in the sample, or choose the top n rows.</span></span>  
  
-   <span data-ttu-id="6f9ad-123">Clique com o botão direito do mouse na tabela vTimeSeries e selecione **Propriedades** para atribuir um novo nome à tabela.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-123">Right-click the table vTimeSeries and select **Properties** to assign a new name to the table.</span></span> <span data-ttu-id="6f9ad-124">Você também pode selecionar colunas individuais na exibição da fonte de dados e modificar as propriedades de coluna.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-124">You can also select individual columns from the data source view, and the modify the column properties.</span></span>  
  
-   <span data-ttu-id="6f9ad-125">Clique em qualquer ponto na área de design de exibição da fonte de dados para criar uma nova consulta e atribuir um nome a ela, para criar relações entre tabelas ou para alterar o layout da área de design.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-125">Click anywhere in the data source view design area to create a new query and assign a name to it, to create relationships between tables, or to change the layout of the design area.</span></span>  
  
-   <span data-ttu-id="6f9ad-126">Clique com o botão direito do mouse em uma tabela e selecione **novo cálculo nomeado** para criar colunas derivadas, incluindo agregações.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-126">Right-click a table and select **New Named Calculation** to create derived columns, including aggregations.</span></span> <span data-ttu-id="6f9ad-127">Você também pode adicionar novas tabelas e exibições da fonte de dados nesta exibição.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-127">You can also add new tables and views from the data source in this view.</span></span>  
  
 <span data-ttu-id="6f9ad-128">Na próxima tarefa, você irá explorar os dados da série temporal e determinar a melhor coluna a ser usada como o identificador de série temporal.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-128">In the next task, you will explore the time series data and determine the best column to use as the time series identifier.</span></span> <span data-ttu-id="6f9ad-129">Aprenderá também como tratar lacunas nos dados de série temporal.</span><span class="sxs-lookup"><span data-stu-id="6f9ad-129">You will also learn how to handle gaps in time series data.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="6f9ad-130">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="6f9ad-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="6f9ad-131">Noções básicas sobre os requisitos de um modelo de série temporal &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="6f9ad-131">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="6f9ad-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f9ad-132">See Also</span></span>  
 [<span data-ttu-id="6f9ad-133">Algoritmo MTS</span><span class="sxs-lookup"><span data-stu-id="6f9ad-133">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
