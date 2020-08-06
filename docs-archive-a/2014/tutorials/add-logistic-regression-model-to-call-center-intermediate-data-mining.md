---
title: Adicionando um modelo de regressão logística à estrutura do Call Center (tutorial de mineração de dados intermediário) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 97abb77a-346c-44fa-8959-688dee1af6a8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7d0100313d1ea5a1af5f729249bc2d743a730222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683223"
---
# <a name="adding-a-logistic-regression-model-to-the-call-center-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="6aab5-102">Adicionando um modelo de regressão logística à estrutura do call center (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="6aab5-102">Adding a Logistic Regression Model to the Call Center Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="6aab5-103">Além de analisar os fatores que podem afetar as operações do call center, você também recebeu uma solicitação para fornecer algumas recomendações específicas sobre como melhorar a qualidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="6aab5-103">In addition to analyzing the factors that might affect call center operations, you were also asked to provide some specific recommendations on how the staff can improve service quality.</span></span> <span data-ttu-id="6aab5-104">Nesta tarefa, você usará a mesma estrutura de mineração que usou para criar o modelo exploratório e adicionar um modelo de mineração que será usado para criar previsões.</span><span class="sxs-lookup"><span data-stu-id="6aab5-104">In this task, you will use the same mining structure that you used to build the exploratory model and add a mining model that will be used for creating predictions.</span></span>  
  
 <span data-ttu-id="6aab5-105">No [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], um modelo de regressão logística se baseia no algoritmo de redes neurais e, portanto, fornece a mesma flexibilidade e capacidade que um modelo de rede neural.</span><span class="sxs-lookup"><span data-stu-id="6aab5-105">In [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], a logistic regression model is based on the neural networks algorithm, and therefore provides the same flexibility and power as a neural network model.</span></span> <span data-ttu-id="6aab5-106">No entanto, a regressão logística é particularmente bem-apropriada para prever resultados binários.</span><span class="sxs-lookup"><span data-stu-id="6aab5-106">However, logistic regression is particularly well-suited for predicting binary outcomes.</span></span>  
  
 <span data-ttu-id="6aab5-107">Para este cenário, você poderá usar a mesma estrutura de mineração usada no modelo de rede neural.</span><span class="sxs-lookup"><span data-stu-id="6aab5-107">For this scenario, you will use the same mining structure that you used for the neural network model.</span></span> <span data-ttu-id="6aab5-108">No entanto, você personalizará o novo modelo para direcionar suas questões comerciais.</span><span class="sxs-lookup"><span data-stu-id="6aab5-108">However, you will customize the new model to target your business questions.</span></span> <span data-ttu-id="6aab5-109">Você está interessado em melhorar a qualidade de serviço e saber quantos operadores experientes você precisa. Então, você configurará seu modelo para prever esses valores.</span><span class="sxs-lookup"><span data-stu-id="6aab5-109">You are interested in improving service quality and determining how many experienced operators you need, so you will set up your model to predict those values.</span></span>  
  
 <span data-ttu-id="6aab5-110">Para assegurar que todos os modelos baseados nos dados do call center sejam o mais semelhantes possível, você usará o mesmo valor de semente de antes.</span><span class="sxs-lookup"><span data-stu-id="6aab5-110">To ensure that all the models based on the call center data are as similar as possible, you will use the same seed value as before.</span></span> <span data-ttu-id="6aab5-111">Definir o parâmetro de semente assegura que o modelo processa os dados do mesmo ponto de partida, e minimiza variações causadas por artefatos nos dados.</span><span class="sxs-lookup"><span data-stu-id="6aab5-111">Setting the seed parameter ensures that the model processes the data from the same starting point, and minimizes variations caused by artifacts in the data.</span></span>  
  
### <a name="to-add-a-new-mining-model-to-the-call-center-mining-structure"></a><span data-ttu-id="6aab5-112">Para adicionar um novo modelo de mineração à estrutura de mineração do call center</span><span class="sxs-lookup"><span data-stu-id="6aab5-112">To add a new mining model to the call center mining structure</span></span>  
  
1.  <span data-ttu-id="6aab5-113">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , em Gerenciador de soluções, clique com o botão direito do mouse na estrutura de mineração, **compartimentalizados do Call Center**e selecione **Abrir Designer**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, right-click the mining structure, **Call Center Binned**, and select **Open Designer**.</span></span>  
  
2.  <span data-ttu-id="6aab5-114">No designer de mineração de dados, clique na guia **modelos de mineração** .</span><span class="sxs-lookup"><span data-stu-id="6aab5-114">In Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="6aab5-115">Clique em **criar um modelo de mineração relacionado**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-115">Click **Create a related mining model**.</span></span>  
  
4.  <span data-ttu-id="6aab5-116">Na caixa de diálogo **novo modelo de mineração** , para **nome do modelo**, digite `Call Center - LR` .</span><span class="sxs-lookup"><span data-stu-id="6aab5-116">In the **New Mining Model** dialog box, for **Model name**, type `Call Center - LR`.</span></span>  <span data-ttu-id="6aab5-117">Para **nome do algoritmo**, selecione **regressão logística da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-117">For **Algorithm name**, select **Microsoft Logistic Regression**.</span></span>  
  
5.  <span data-ttu-id="6aab5-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="6aab5-119">O novo modelo de mineração é exibido na guia **modelos de mineração** .</span><span class="sxs-lookup"><span data-stu-id="6aab5-119">The new mining model is displayed in the **Mining Models** tab.</span></span>  
  
### <a name="to-customize-the-logistic-regression-model"></a><span data-ttu-id="6aab5-120">Para personalizar o modelo de regressão logística</span><span class="sxs-lookup"><span data-stu-id="6aab5-120">To customize the logistic regression model</span></span>  
  
1.  <span data-ttu-id="6aab5-121">Na coluna para o novo modelo de mineração, `Call Center - LR` deixe a ID callcenter do fato como a chave.</span><span class="sxs-lookup"><span data-stu-id="6aab5-121">In the column for the new mining model, `Call Center - LR`, leave Fact CallCenter ID as the key.</span></span>  
  
2.  <span data-ttu-id="6aab5-122">Altere o valor dos operadores ServiceGrade e Level dois para **prever**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-122">Change the value of ServiceGrade and Level Two Operators to **Predict**.</span></span>  
  
     <span data-ttu-id="6aab5-123">Essas colunas serão usadas como entrada e para previsão.</span><span class="sxs-lookup"><span data-stu-id="6aab5-123">These columns will be used both as input and for prediction.</span></span> <span data-ttu-id="6aab5-124">Em essência, você está criando dois modelos separados com os mesmos dados: um que prevê o número de operadores e outro que prevê a classificação de serviço.</span><span class="sxs-lookup"><span data-stu-id="6aab5-124">In essence, you are creating two separate models on the same data: one that predicts the number of operators, and one that predicts the service grade.</span></span>  
  
3.  <span data-ttu-id="6aab5-125">Altere todas as outras colunas para **entrada**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-125">Change all other columns to **Input**.</span></span>  
  
### <a name="to-specify-the-seed-and-process-the-models"></a><span data-ttu-id="6aab5-126">Para especificar a semente e processar os modelos</span><span class="sxs-lookup"><span data-stu-id="6aab5-126">To specify the seed and process the models</span></span>  
  
1.  <span data-ttu-id="6aab5-127">Na guia **modelo de mineração** , clique com o botão direito do mouse na coluna do modelo chamado Call Center-LR e selecione **definir parâmetros de algoritmo**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-127">In the **Mining Model** tab, right-click the column for the model named Call Center - LR, and select **Set Algorithm Parameters**.</span></span>  
  
2.  <span data-ttu-id="6aab5-128">Na linha do parâmetro HOLDOUT_SEED, clique na célula vazia em **valor**e digite `1` .</span><span class="sxs-lookup"><span data-stu-id="6aab5-128">In the row for the HOLDOUT_SEED parameter, click the empty cell under **Value**, and type `1`.</span></span> <span data-ttu-id="6aab5-129">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-129">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6aab5-130">O valor escolhido como semente não importa, desde que você use a mesma semente para todos os modelos relacionados.</span><span class="sxs-lookup"><span data-stu-id="6aab5-130">The value that you choose as the seed does not matter, as long as you use the same seed for all related models.</span></span>  
  
3.  <span data-ttu-id="6aab5-131">No menu **modelos de mineração** , selecione **processar estrutura de mineração e todos os modelos**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-131">In the **Mining Models** menu, select **Process Mining Structure and All Models**.</span></span> <span data-ttu-id="6aab5-132">Clique em **Sim** para implantar o projeto de Data Mining atualizado no servidor.</span><span class="sxs-lookup"><span data-stu-id="6aab5-132">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
4.  <span data-ttu-id="6aab5-133">Na caixa de diálogo **modelo de mineração de processo** , clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-133">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
5.  <span data-ttu-id="6aab5-134">Clique em **fechar** para fechar a caixa de diálogo **progresso do processo** e clique em **fechar** novamente na caixa de diálogo **processar modelo de mineração** .</span><span class="sxs-lookup"><span data-stu-id="6aab5-134">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="6aab5-135">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="6aab5-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="6aab5-136">Criando previsões para os modelos do Call Center &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="6aab5-136">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="6aab5-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6aab5-137">See Also</span></span>  
 [<span data-ttu-id="6aab5-138">Requisitos e considerações de processamento &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="6aab5-138">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
