---
title: Processando o modelo de clustering de sequência | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4a7545fd-37a3-4766-ad59-0946f1bd3524
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 9975105fb6779e150e3a498bc87654d21292a1b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683190"
---
# <a name="processing-the-sequence-clustering-model"></a><span data-ttu-id="cb670-102">Processando o modelo de clustering de sequências</span><span class="sxs-lookup"><span data-stu-id="cb670-102">Processing the Sequence Clustering Model</span></span>
  <span data-ttu-id="cb670-103">Depois de criar uma nova estrutura de mineração, você deverá implantar as alterações feitas na solução de mineração de dados e processar a estrutura.</span><span class="sxs-lookup"><span data-stu-id="cb670-103">After you create a new mining structure, you must deploy the changes that you made to the data mining solution, and then process the structure.</span></span> <span data-ttu-id="cb670-104">Depois de processar a nova estrutura e quando o modelo de mineração estiver completo, você poderá navegar pelo  modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="cb670-104">After processing of both the new structure and the mining model is complete, you can browse the mining model.</span></span>  
  
 <span data-ttu-id="cb670-105">O processamento sempre será necessário na criação de uma nova estrutura de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="cb670-105">Processing is always required when you create a new data mining structure.</span></span> <span data-ttu-id="cb670-106">No entanto, se você adicionar um novo modelo de mineração a uma estrutura existente, poderá processar somente o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="cb670-106">However, if you add a new mining model to an existing structure, you can process just the mining model.</span></span> <span data-ttu-id="cb670-107">Neste cenário, como você criou uma nova estrutura de mineração e um novo modelo de mineração, será necessário processar ambos.</span><span class="sxs-lookup"><span data-stu-id="cb670-107">In this scenario, because you have created a new mining structure and a new mining model, you must process both.</span></span>  
  
### <a name="to-process-the-mining-structure-and-model"></a><span data-ttu-id="cb670-108">Para processar a estrutura de mineração e o modelo</span><span class="sxs-lookup"><span data-stu-id="cb670-108">To process the mining structure and model</span></span>  
  
1.  <span data-ttu-id="cb670-109">No menu **Modelo de Mineração** do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], selecione **Estrutura de Mineração do Processo e Todos os Modelos**.</span><span class="sxs-lookup"><span data-stu-id="cb670-109">On the **Mining Model** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select **Process Mining Structure and All Models**.</span></span>  
  
2.  <span data-ttu-id="cb670-110">No aviso que pergunta se você deseja construir e implantar o projeto, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="cb670-110">At the warning asking whether you want to build and deploy the project, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="cb670-111">Na caixa de diálogo **Processar Estrutura de Mineração – Clustering de Sequências com Região** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="cb670-111">In the **Process Mining Structure - Sequence Clustering with Region** dialog box, click **Run**.</span></span>  
  
     <span data-ttu-id="cb670-112">A caixa de diálogo **Andamento do Processo** é aberta para exibir informações sobre o processamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="cb670-112">The **Process Progress** dialog box opens to display information about model processing.</span></span> <span data-ttu-id="cb670-113">O processamento da estrutura e do modelo novos pode demorar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="cb670-113">Processing of the new structure and model might take some time.</span></span>  
  
4.  <span data-ttu-id="cb670-114">Depois que o processamento estiver completo, clique em **Fechar** para sair da caixa de diálogo **Progresso do Processo** .</span><span class="sxs-lookup"><span data-stu-id="cb670-114">After processing is complete, click **Close** to exit the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="cb670-115">Clique em **Fechar** novamente para sair da caixa de diálogo **Processar Estrutura de Mineração – Clustering de Sequências com Região** .</span><span class="sxs-lookup"><span data-stu-id="cb670-115">Click **Close** again to exit the **Process Mining Structure - Sequence Clustering with Region** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="cb670-116">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="cb670-116">Next Task in Lesson</span></span>  
 [<span data-ttu-id="cb670-117">Explorando o modelo de clustering de sequência &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="cb670-117">Exploring the Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="cb670-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cb670-118">See Also</span></span>  
 <span data-ttu-id="cb670-119">[Designer de mineração de dados](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="cb670-119">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 <span data-ttu-id="cb670-120">[Algoritmo de clustering de sequência da Microsoft](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="cb670-120">[Microsoft Sequence Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md) </span></span>  
 [<span data-ttu-id="cb670-121">Requisitos e considerações de processamento &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="cb670-121">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
