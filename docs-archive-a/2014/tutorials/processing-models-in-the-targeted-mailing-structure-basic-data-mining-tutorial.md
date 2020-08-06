---
title: Processando modelos na estrutura de endereçamento de destino (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d8233bb-117e-4563-9302-8a5a8ad1fae2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b8fb7b9f601f351520c3f611cc3c520614ed8ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680238"
---
# <a name="processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="aa71c-102">Processando modelos na estrutura de mala direta (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="aa71c-102">Processing Models in the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="aa71c-103">Antes de navegar ou trabalhar nos modelos de mineração criados por você, implante o projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e processe a estrutura de mineração e os modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="aa71c-103">Before you can browse or work with the mining models that you have created, you must deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span>  
  
-   <span data-ttu-id="aa71c-104">A *implantação* do envia o projeto para um servidor e cria todos os objetos nesse projeto no servidor.</span><span class="sxs-lookup"><span data-stu-id="aa71c-104">*Deploying* sends the project to a server and creates any objects in that project on the server.</span></span>  
  
-   <span data-ttu-id="aa71c-105">O *processamento* popula [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objetos com dados de fontes de dados relacionais.</span><span class="sxs-lookup"><span data-stu-id="aa71c-105">*Processing* populates [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects with data from relational data sources.</span></span>  
  
 <span data-ttu-id="aa71c-106">Os modelos só poderão ser usados depois de serem implantados e processados.</span><span class="sxs-lookup"><span data-stu-id="aa71c-106">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="aa71c-107">Além disso, ao fazer uma mudança no modelo, tal como adicionar novos dados, você deverá implantar e processar os modelos novamente.</span><span class="sxs-lookup"><span data-stu-id="aa71c-107">Also, when you make any changes to the model, such as adding new data, you must redeploy and reprocess the models.</span></span>  
  
## <a name="ensuring-consistency-with-holdoutseed"></a><span data-ttu-id="aa71c-108">Garantindo a consistência com HoldoutSeed</span><span class="sxs-lookup"><span data-stu-id="aa71c-108">Ensuring Consistency with HoldoutSeed</span></span>  
 <span data-ttu-id="aa71c-109">Quando você implanta um projeto e processa a estrutura e os modelos, as linhas individuais da sua estrutura de dados são atribuídas ao conjunto de treinamento ou ao conjunto de teste com base em um valor numérico de semente aleatória.</span><span class="sxs-lookup"><span data-stu-id="aa71c-109">When you deploy a project and process the structure and models, individual rows in your data structure are assigned to either the training set or testing set based on a numerical seed value.</span></span> <span data-ttu-id="aa71c-110">Por padrão, o valor numérico da semente aleatória é calculado com base em atributos da estrutura de dados.</span><span class="sxs-lookup"><span data-stu-id="aa71c-110">By default, the numerical seed value is computed based on attributes of the data structure.</span></span> <span data-ttu-id="aa71c-111">No entanto, se você alterar alguns aspectos do seu modelo, o valor da semente aleatória poderia ser alterado, levando a resultados um pouco diferentes.</span><span class="sxs-lookup"><span data-stu-id="aa71c-111">However, if you ever change some aspects of your model, the seed value would change, leading to subtly different results.</span></span> <span data-ttu-id="aa71c-112">Portanto, para garantir que os resultados sejam os mesmos descritos aqui, vamos atribuir arbitrariamente uma *semente* de controle fixa de `12` .</span><span class="sxs-lookup"><span data-stu-id="aa71c-112">Therefore, in order to ensure that your results are the same as described here, we will arbitrarily assign a fixed *holdout seed* of `12`.</span></span> <span data-ttu-id="aa71c-113">A semente de controle é usada para inicializar o algoritmo de amostragem e garante que os dados sejam particionados aproximadamente da mesma forma para todas as estruturas de mineração e seus modelos.</span><span class="sxs-lookup"><span data-stu-id="aa71c-113">The holdout seed is used to initialize the sampling algorithm, and ensures that the data is partitioned in roughly the same way for all mining structures and their models.</span></span>  
  
 <span data-ttu-id="aa71c-114">Esse valor não afeta o número de casos no conjunto de treinamento; apenas garante que o mesmo método de particionamento seja usado sempre na criação do modelo.</span><span class="sxs-lookup"><span data-stu-id="aa71c-114">This value does not affect the number of cases in the training set; it simply ensures that the same partitioning method will be used each time you build the model.</span></span>  
  
 <span data-ttu-id="aa71c-115">Para obter mais informações sobre a semente de controle, consulte [conjuntos de dados de treinamento e teste](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="aa71c-115">For more information on holdout seed, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-set-the-holdout-seed"></a><span data-ttu-id="aa71c-116">Para definir Holdout Seed</span><span class="sxs-lookup"><span data-stu-id="aa71c-116">To set the Holdout Seed</span></span>  
  
1.  <span data-ttu-id="aa71c-117">Clique na guia **estrutura de mineração** ou na guia **modelos de mineração** no designer de mineração de dados no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aa71c-117">Click on the **Mining Structure** tab or the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="aa71c-118">O **direcionamento de mala MiningStructure** é exibido no painel **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="aa71c-118">**Targeted Mailing MiningStructure** displays in the **Properties** pane.</span></span>  
  
2.  <span data-ttu-id="aa71c-119">Verifique se o painel **Propriedades** está aberto pressionando **F4**.</span><span class="sxs-lookup"><span data-stu-id="aa71c-119">Ensure that the **Properties** pane is open by pressing **F4**.</span></span>  
  
3.  <span data-ttu-id="aa71c-120">Verifique se o **CacheMode** está definido como **KeepTrainingCases**.</span><span class="sxs-lookup"><span data-stu-id="aa71c-120">Ensure that **CacheMode** is set to **KeepTrainingCases**.</span></span>  
  
4.  <span data-ttu-id="aa71c-121">Insira `12` para **HoldoutSeed**.</span><span class="sxs-lookup"><span data-stu-id="aa71c-121">Enter `12` for **HoldoutSeed**.</span></span>  
  
## <a name="deploying-and-processing-the-models"></a><span data-ttu-id="aa71c-122">Implantando e processando os modelos</span><span class="sxs-lookup"><span data-stu-id="aa71c-122">Deploying and Processing the Models</span></span>  
 <span data-ttu-id="aa71c-123">No designer de mineração de dados, você pode decidir quais objetos processar, dependendo do escopo das alterações feitas em seu modelo ou nos dados subjacentes:</span><span class="sxs-lookup"><span data-stu-id="aa71c-123">In Data Mining Designer, you can decide which objects to process, depending on the scope of changes you've made to your model or the underlying data:</span></span>  
  
 <span data-ttu-id="aa71c-124">Para esta tarefa, como os dados e os modelos são novos, você processará a estrutura e todos os modelos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="aa71c-124">For this task, because the data and the models are new, you will process the structure and all the models at the same time.</span></span>  
  
#### <a name="to-deploy-the-project-and-process-all-the-mining-models"></a><span data-ttu-id="aa71c-125">Para implantar o projeto e processar todos os modelos de mineração</span><span class="sxs-lookup"><span data-stu-id="aa71c-125">To deploy the project and process all the mining models</span></span>  
  
1.  <span data-ttu-id="aa71c-126">No menu **modelo de mineração** , selecione **processar estrutura de mineração e todos os modelos**.</span><span class="sxs-lookup"><span data-stu-id="aa71c-126">In the **Mining Model** menu, select **Process Mining Structure and All Models**.</span></span>  
  
     <span data-ttu-id="aa71c-127">Caso tenha feito alterações na estrutura de mineração, será solicitado que você crie e implante o projeto antes de processar os modelos.</span><span class="sxs-lookup"><span data-stu-id="aa71c-127">If you made changes to the structure, you will be prompted to build and deploy the project before processing the models.</span></span> <span data-ttu-id="aa71c-128">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="aa71c-128">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="aa71c-129">Clique em **executar** na caixa de diálogo **processando a estrutura de mineração – endereçamento direcionado** .</span><span class="sxs-lookup"><span data-stu-id="aa71c-129">Click **Run** in the **Processing Mining Structure - Targeted Mailing** dialog box.</span></span>  
  
     <span data-ttu-id="aa71c-130">A caixa de diálogo **Andamento do Processo** é aberta para exibir os detalhes sobre o processamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="aa71c-130">The **Process Progress** dialog box opens to display the details of model processing.</span></span> <span data-ttu-id="aa71c-131">O processamento do modelo pode demorar um pouco, dependendo do computador.</span><span class="sxs-lookup"><span data-stu-id="aa71c-131">Model processing might take some time, depending on your computer.</span></span>  
  
3.  <span data-ttu-id="aa71c-132">Clique em **Fechar** na caixa de diálogo **Andamento do Processo** após os modelos completarem seu processamento.</span><span class="sxs-lookup"><span data-stu-id="aa71c-132">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="aa71c-133">Clique em **fechar** na caixa de diálogo \*\*processando estrutura de mineração- \<structure> \*\* .</span><span class="sxs-lookup"><span data-stu-id="aa71c-133">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="aa71c-134">Tarefa anterior da lição</span><span class="sxs-lookup"><span data-stu-id="aa71c-134">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="aa71c-135">Adicionando novos modelos à estrutura de mala direta direcionada &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="aa71c-135">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="aa71c-136">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="aa71c-136">Next Lesson</span></span>  
 [<span data-ttu-id="aa71c-137">Lição 4: explorando os modelos de mala direta direcionados &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="aa71c-137">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="aa71c-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa71c-138">See Also</span></span>  
 [<span data-ttu-id="aa71c-139">Requisitos e considerações de processamento &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="aa71c-139">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
