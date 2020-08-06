---
title: Criando um modelo de clustering de sequência relacionado (tutorial de mineração de dados intermediário) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1fb4f5bc-1756-45ca-9cd7-411a8c5992a9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d015ed8a9887cb6164020806bf4136f58629ad11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681983"
---
# <a name="creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="1aefa-102">Criando um modelo de clustering de sequências relacionado (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="1aefa-102">Creating a Related Sequence Clustering Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="1aefa-103">Por meio da sua exploração do modelo de clustering de sequências, você aprendeu que outros atributos, como Região ou Rendimento, têm um efeito muito forte sobre os modelos e, portanto, para compreender melhor as sequências, será preciso criar um modelo de clustering de sequências relacionado e remover os atributos relacionados aos dados demográficos do cliente.</span><span class="sxs-lookup"><span data-stu-id="1aefa-103">Through your exploration of the sequence clustering model, you learned that other attributes such as Region or Income have a strong effect on the models; therefore, to understand the sequences better, you will create a related sequence clustering model and remove the attributes related to customer demographics.</span></span>  
  
 <span data-ttu-id="1aefa-104">Nesta tarefa, você criará uma cópia do modelo de clustering de sequências regional e removerá do modelo qualquer coluna que não esteja diretamente relacionada às sequências.</span><span class="sxs-lookup"><span data-stu-id="1aefa-104">In this task, you will create a copy of the regional sequence clustering model, and then remove from the model any columns that are not directly related to the sequences.</span></span>  
  
 <span data-ttu-id="1aefa-105">O novo modelo conterá todas as mesmas colunas do modelo de mineração em que foi baseado.</span><span class="sxs-lookup"><span data-stu-id="1aefa-105">The new model will contain all the same columns as the mining model on which it is based.</span></span> <span data-ttu-id="1aefa-106">No entanto, você não precisa remover as colunas da estrutura de mineração, somente especificar que o novo modelo de mineração deverá ignorar as colunas.</span><span class="sxs-lookup"><span data-stu-id="1aefa-106">However, you do not need to remove the columns from the mining structure, only specify that the new mining model ignore the columns.</span></span>  
  
### <a name="to-make-a-copy-of-the-sequence-clustering-model"></a><span data-ttu-id="1aefa-107">Para fazer uma cópia do modelo de clustering de sequências</span><span class="sxs-lookup"><span data-stu-id="1aefa-107">To make a copy of the sequence clustering model</span></span>  
  
1.  <span data-ttu-id="1aefa-108">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , no designer de mineração de dados, clique na guia **modelos de mineração** .</span><span class="sxs-lookup"><span data-stu-id="1aefa-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in the Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="1aefa-109">Clique com o botão direito do mouse no modelo que você deseja copiar e selecione **novo modelo de mineração**.</span><span class="sxs-lookup"><span data-stu-id="1aefa-109">Right-click the model you want to copy, and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="1aefa-110">Na caixa de diálogo **novo modelo de mineração** , digite um nome de modelo e selecione Microsoft `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="1aefa-110">In the **New Mining Model** dialog box, type a model name, and select Microsoft `Sequence Clustering`.</span></span>  
  
     <span data-ttu-id="1aefa-111">Para este tutorial, digite o nome `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="1aefa-111">For this tutorial, type the name `Sequence Clustering`.</span></span>  
  
4.  <span data-ttu-id="1aefa-112">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1aefa-112">Click **OK**.</span></span>  
  
### <a name="to-remove-columns-from-the-mining-model"></a><span data-ttu-id="1aefa-113">Para remover colunas do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="1aefa-113">To remove columns from the mining model</span></span>  
  
1.  <span data-ttu-id="1aefa-114">Na guia **modelo de mineração** , na coluna do novo modelo denominado clustering de sequência, clique na linha do atributo de **grupo renda** e selecione **ignorar**.</span><span class="sxs-lookup"><span data-stu-id="1aefa-114">In the **Mining Model** tab, in the column for the new model named Sequence Clustering, click the row for the **Income Group** attribute, and select **Ignore**.</span></span>  
  
2.  <span data-ttu-id="1aefa-115">Repita essa etapa para a **região**de atributo.</span><span class="sxs-lookup"><span data-stu-id="1aefa-115">Repeat this step for the attribute **Region**.</span></span>  
  
3.  <span data-ttu-id="1aefa-116">Clique no sinal de adição ao lado do nome da tabela, **v associações Seq itens de linha**, para expandir a tabela e exibir as colunas da tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="1aefa-116">Click the plus sign next to the table name, **v Assoc Seq Line Items**, to expand the table and view the columns from the nested table.</span></span>  
  
     <span data-ttu-id="1aefa-117">O novo modelo só deve conter as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="1aefa-117">The new model should have only the following columns:</span></span>  
  
     <span data-ttu-id="1aefa-118">**Solicitar NumberKey**</span><span class="sxs-lookup"><span data-stu-id="1aefa-118">**Order NumberKey**</span></span>  
  
     <span data-ttu-id="1aefa-119">**Chave de número de linha**</span><span class="sxs-lookup"><span data-stu-id="1aefa-119">**Line Number Key**</span></span>  
  
     <span data-ttu-id="1aefa-120">**Previsão de modelo**</span><span class="sxs-lookup"><span data-stu-id="1aefa-120">**Model Predict**</span></span>  
  
### <a name="to-process-the-new-sequence-clustering-model"></a><span data-ttu-id="1aefa-121">Para processar o novo modelo de clustering de sequências</span><span class="sxs-lookup"><span data-stu-id="1aefa-121">To process the new sequence clustering model</span></span>  
  
1.  <span data-ttu-id="1aefa-122">Na guia **modelo de mineração** , clique com o botão direito do mouse no novo modelo chamado `Sequence Clustering` e selecione **modelo de processo**.</span><span class="sxs-lookup"><span data-stu-id="1aefa-122">In the **Mining Model** tab, right-click the new model named `Sequence Clustering`, and select **Process Model**.</span></span>  
  
     <span data-ttu-id="1aefa-123">Como o novo modelo de mineração simplificado se baseia em uma estrutura que já foi processada, não será preciso reprocessá-la.</span><span class="sxs-lookup"><span data-stu-id="1aefa-123">Because the new simplified mining model is based on a structure that has already been processed, you do not need to reprocess the structure.</span></span> <span data-ttu-id="1aefa-124">É possível processar somente o novo modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="1aefa-124">You can process just the new mining model.</span></span>  
  
2.  <span data-ttu-id="1aefa-125">Clique em **Sim** para implantar o projeto de Data Mining atualizado no servidor.</span><span class="sxs-lookup"><span data-stu-id="1aefa-125">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
3.  <span data-ttu-id="1aefa-126">Na caixa de diálogo **modelo de mineração de processo** , clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="1aefa-126">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="1aefa-127">Clique em **fechar** para fechar a caixa de diálogo **progresso do processo** e clique em **fechar** novamente na caixa de diálogo **processar modelo de mineração** .</span><span class="sxs-lookup"><span data-stu-id="1aefa-127">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="1aefa-128">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="1aefa-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="1aefa-129">Criando previsões em um modelo de clustering de sequência &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="1aefa-129">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="1aefa-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1aefa-130">See Also</span></span>  
 [<span data-ttu-id="1aefa-131">Requisitos e considerações de processamento &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="1aefa-131">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
