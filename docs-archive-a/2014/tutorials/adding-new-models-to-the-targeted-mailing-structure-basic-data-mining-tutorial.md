---
title: Adicionando novos modelos à estrutura de endereçamento de destino (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 512c6888-60f1-46e4-9639-bc448395b8d7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b83dfc6c9e218eecf3f2abe636b8c24d69d1b507
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683217"
---
# <a name="adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="ab516-102">Adicionando novos modelos à estrutura de mala direta (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="ab516-102">Adding New Models to the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="ab516-103">Nesta tarefa, você definirá dois modelos adicionais usando a guia **modelos de mineração** do designer de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="ab516-103">In this task, you will define two additional models by using the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="ab516-104">Você usará os algoritmos Microsoft Naive Bayes e Microsoft Clustering para criar os modelos.</span><span class="sxs-lookup"><span data-stu-id="ab516-104">You will use the Microsoft Clustering and Microsoft Naive Bayes algorithms to create the models.</span></span> <span data-ttu-id="ab516-105">Esses dois algoritmos foram selecionados por causa de sua capacidade de prever um valor discreto (por exemplo, compra de bicicletas).</span><span class="sxs-lookup"><span data-stu-id="ab516-105">These two algorithms are selected because of their ability to predict a discrete value (i.e., bike purchase).</span></span> <span data-ttu-id="ab516-106">Para obter mais informações sobre esses algoritmos, consulte [algoritmo de clustering da Microsoft](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) e [algoritmo do Microsoft Naive Bayes](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md)</span><span class="sxs-lookup"><span data-stu-id="ab516-106">For more information about these algorithms, see [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md)</span></span>  
  
### <a name="to-create-a-clustering-mining-model"></a><span data-ttu-id="ab516-107">Para criar um modelo de mineração de clustering</span><span class="sxs-lookup"><span data-stu-id="ab516-107">To create a clustering mining model</span></span>  
  
1.  <span data-ttu-id="ab516-108">Alterne para a guia **modelos de mineração** no designer de mineração de dados no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ab516-108">Switch to the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="ab516-109">Observe que o designer exibe duas colunas, uma para a estrutura de mineração e outra para o `TM_Decision_Tree` modelo de mineração que você criou na lição anterior.</span><span class="sxs-lookup"><span data-stu-id="ab516-109">Notice that the designer displays two columns, one for the mining structure and one for the `TM_Decision_Tree` mining model, which you created in the previous lesson.</span></span>  
  
2.  <span data-ttu-id="ab516-110">Clique com o botão direito do mouse na coluna **estrutura** e selecione **novo modelo de mineração**.</span><span class="sxs-lookup"><span data-stu-id="ab516-110">Right-click the **Structure** column and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="ab516-111">Na caixa de diálogo **novo modelo de mineração** , em **nome do modelo**, digite `TM_Clustering` .</span><span class="sxs-lookup"><span data-stu-id="ab516-111">In the **New Mining Model** dialog box, in **Model name**, type `TM_Clustering`.</span></span>  
  
4.  <span data-ttu-id="ab516-112">Em **nome do algoritmo**, selecione **clustering da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="ab516-112">In **Algorithm name**, select **Microsoft Clustering**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="ab516-113">O novo modelo agora aparece na guia **modelos de mineração** do designer de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="ab516-113">The new model now appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="ab516-114">Esse modelo, criado com o [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo clustering, agrupa clientes com características semelhantes em clusters e prevê a compra de bicicletas para cada cluster.</span><span class="sxs-lookup"><span data-stu-id="ab516-114">This model, built with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm, groups customers with similar characteristics into clusters and predicts bike buying for each cluster.</span></span> <span data-ttu-id="ab516-115">Embora você possa modificar o uso e as propriedades da coluna para o novo modelo, nenhuma alteração no `TM_Clustering` modelo é necessária para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="ab516-115">Although you can modify the column usage and properties for the new model, no changes to the `TM_Clustering` model are necessary for this tutorial.</span></span>  
  
### <a name="to-create-a-naive-bayes-mining-model"></a><span data-ttu-id="ab516-116">Criar um modelo de mineração Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="ab516-116">To create a Naive Bayes mining model</span></span>  
  
1.  <span data-ttu-id="ab516-117">Na guia **modelos de mineração** do designer de mineração de dados, na coluna de **estrutura** clickthe à direita e selecione **novo modelo de mineração**.</span><span class="sxs-lookup"><span data-stu-id="ab516-117">In the **Mining Models** tab of Data Mining Designer, right-clickthe **Structure** column, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="ab516-118">Na caixa de diálogo **novo modelo de mineração** , em **nome do modelo**, digite `TM_NaiveBayes` .</span><span class="sxs-lookup"><span data-stu-id="ab516-118">In the **New Mining Model** dialog box, under **Model name**, type `TM_NaiveBayes`.</span></span>  
  
3.  <span data-ttu-id="ab516-119">Em **nome do algoritmo**, selecione **Microsoft Naive Bayes**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab516-119">In **Algorithm name**, select **Microsoft Naive Bayes**, then click **OK**.</span></span>  
  
     <span data-ttu-id="ab516-120">Uma mensagem é exibida informando que o [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo Naive Bayes não dá suporte às colunas de **renda** e **idade** anual, que são contínuas.</span><span class="sxs-lookup"><span data-stu-id="ab516-120">A message appears stating that the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm does not support the **Age** and **Yearly Income** columns, which are continuous.</span></span>  
  
4.  <span data-ttu-id="ab516-121">Clique em **Sim** para confirmar a mensagem e continuar.</span><span class="sxs-lookup"><span data-stu-id="ab516-121">Click **Yes** to acknowledge the message and continue.</span></span>  
  
 <span data-ttu-id="ab516-122">Um novo modelo é exibido na guia **modelos de mineração** do designer de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="ab516-122">A new model appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="ab516-123">Embora você possa modificar o uso de coluna e as propriedades de todos os modelos nesta guia, nenhuma alteração no `TM_NaiveBayes` modelo é necessária para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="ab516-123">Although you can modify the column usage and properties for all the models in this tab, no changes to the `TM_NaiveBayes` model are necessary for this tutorial.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ab516-124">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="ab516-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ab516-125">Processando modelos na estrutura de mala direta direcionada &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="ab516-125">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ab516-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ab516-126">See Also</span></span>  
 <span data-ttu-id="ab516-127">[Adicionar modelos de mineração a uma estrutura &#40;mineração de dados Analysis Services&#41;](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ab516-127">[Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="ab516-128">[Designer de mineração de dados](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="ab516-128">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="ab516-129">Movendo objetos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="ab516-129">Moving Data Mining Objects</span></span>](../../2014/analysis-services/data-mining/moving-data-mining-objects.md)  
  
  
