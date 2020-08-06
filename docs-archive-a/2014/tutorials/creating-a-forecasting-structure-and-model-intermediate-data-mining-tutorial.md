---
title: Criando uma estrutura e um modelo de previsão (tutorial de mineração de dados intermediário) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5f55cbf6-0db4-4cb4-a0f5-e27441873d4f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d77b15a9a8efe9a9c6faec49a2274ee182706992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678380"
---
# <a name="creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="144e3-102">Criando uma estrutura e um modelo de previsão (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="144e3-102">Creating a Forecasting Structure and Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="144e3-103">Em seguida, você usará o Assistente de Mineração de Dados para criar uma nova estrutura e um novo modelo de mineração baseados na exibição da fonte de dados recém-criada.</span><span class="sxs-lookup"><span data-stu-id="144e3-103">Next, you will use the Data Mining Wizard to create a new mining structure and mining model based on the data source view that you just created.</span></span> <span data-ttu-id="144e3-104">Nesta tarefa, você especificará que o modelo de mineração deverá usar o algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series.</span><span class="sxs-lookup"><span data-stu-id="144e3-104">In this task you will specify that the mining model should use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm.</span></span>  
  
### <a name="to-create-a-forecasting-mining-structure"></a><span data-ttu-id="144e3-105">Para criar uma estrutura de mineração de previsão</span><span class="sxs-lookup"><span data-stu-id="144e3-105">To create a forecasting mining structure</span></span>  
  
1.  <span data-ttu-id="144e3-106">Em Gerenciador de Soluções no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , clique com o botão direito do mouse em **estruturas de mineração** e selecione **nova estrutura de mineração**.</span><span class="sxs-lookup"><span data-stu-id="144e3-106">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="144e3-107">Na página **Bem-vindo ao Assistente de Mineração de Dados** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="144e3-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="144e3-108">Na página **selecionar o método de definição** , verifique se a **partir de banco de dados relacional existente ou data warehouse** está selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="144e3-108">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="144e3-109">Na página **criar a estrutura de mineração de dados** , sob a **qual data mining técnica você deseja usar?**, selecione **série temporal da Microsoft**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="144e3-109">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Time Series**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="144e3-110">Na página **selecionar exibição da fonte de dados** , em **exibições da fonte de dados disponíveis**, selecione **SalesByRegion**.</span><span class="sxs-lookup"><span data-stu-id="144e3-110">On the **Select Data Source View** page, under **Available data source views**, select **SalesByRegion**.</span></span>  
  
6.  <span data-ttu-id="144e3-111">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="144e3-111">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="144e3-112">Na página **especificar tipos de tabela** , verifique se a caixa de seleção na coluna **caso** da tabela vTimeSeries está selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="144e3-112">On the **Specify Table Types** page, ensure that the check box in the **Case** column for the vTimeSeries table is selected, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="144e3-113">Na página **especificar os dados de treinamento** , marque as caixas de seleção na coluna **chave** para as colunas ModelRegion e ReportingDate.</span><span class="sxs-lookup"><span data-stu-id="144e3-113">On the **Specify the Training Data** page, select the check boxes in the **Key** column for the ModelRegion and ReportingDate columns.</span></span>  
  
     <span data-ttu-id="144e3-114">ReportingDate deve estar marcada por padrão, já que você especificou essa coluna como a chave primária lógica quando criou a exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="144e3-114">ReportingDate should be selected by default, because you specified this column as the logical primary key when you created the data source view.</span></span> <span data-ttu-id="144e3-115">Ao adicionar ModelRegion como uma segunda chave, você está dizendo ao algoritmo para criar uma série de tempo separada para cada combinação de modelo e região listada nesse campo.</span><span class="sxs-lookup"><span data-stu-id="144e3-115">By adding ModelRegion as a second key, you are telling the algorithm to create a separate time series for each combination of model and region listed in this field.</span></span>  
  
9. <span data-ttu-id="144e3-116">Marque as caixas de seleção nas colunas **entrada** e **previsível** para a quantidade, coluna e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="144e3-116">Select the check boxes in the **Input** and **Predictable** columns for the Quantity, column, and then click **Next**.</span></span>  
  
     <span data-ttu-id="144e3-117">Ao selecionar **previsível**, você indica que deseja criar previsões nos dados nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="144e3-117">By selecting **Predictable**, you indicate that you want to create forecasts on the data in this column.</span></span> <span data-ttu-id="144e3-118">No entanto, como você deseja basear as previsões em dados passados, deverá adicionar também a coluna como uma entrada.</span><span class="sxs-lookup"><span data-stu-id="144e3-118">However, because you want to base the forecasts on past data, you must also add the column as an input.</span></span>  
  
10. <span data-ttu-id="144e3-119">Na página **especificar conteúdo e tipo de dados das colunas**, examine as seleções.</span><span class="sxs-lookup"><span data-stu-id="144e3-119">On the page **Specify Columns' Content and Data Type**, review the selections.</span></span>  
  
     <span data-ttu-id="144e3-120">A coluna ModelRegion é designada como uma coluna de **chave** e a coluna ReportingDate é designada automaticamente como uma coluna **Key Time** .</span><span class="sxs-lookup"><span data-stu-id="144e3-120">The ModelRegion column is designated as a **Key** column and the ReportingDate column is automatically designated as a **Key Time** column.</span></span> <span data-ttu-id="144e3-121">Só é possível ter um de cada tipo de chave.</span><span class="sxs-lookup"><span data-stu-id="144e3-121">You can have only one of each type of key.</span></span>  
  
11. <span data-ttu-id="144e3-122">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="144e3-122">Click **Next**.</span></span>  
  
12. <span data-ttu-id="144e3-123">Na página **concluindo o assistente** , para **nome da estrutura de mineração**, digite `Forecasting` .</span><span class="sxs-lookup"><span data-stu-id="144e3-123">On the **Completing the Wizard** page, for **Mining structure name**, type `Forecasting`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="144e3-124">A opção para habilitar o detalhamento não estará disponível para modelos de série temporal.</span><span class="sxs-lookup"><span data-stu-id="144e3-124">The option to enable drillthrough is not available for time series models.</span></span>  
  
13. <span data-ttu-id="144e3-125">Em **nome do modelo de mineração**, digite `Forecasting` e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="144e3-125">In **Mining model name**, type `Forecasting`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="144e3-126">O designer de mineração de dados é aberto para exibir a `Forecasting` estrutura de mineração que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="144e3-126">Data Mining Designer opens to display the `Forecasting` mining structure that you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="144e3-127">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="144e3-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="144e3-128">Modificando a estrutura de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="144e3-128">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="144e3-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="144e3-129">See Also</span></span>  
 <span data-ttu-id="144e3-130">[Designer de mineração de dados](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="144e3-130">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="144e3-131">Algoritmo MTS</span><span class="sxs-lookup"><span data-stu-id="144e3-131">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
