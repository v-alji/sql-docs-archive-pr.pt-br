---
title: Modificando e processando o modelo de cesta de mercado (tutorial de mineração de dados intermediário) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b6019413-aebd-4ff7-831a-644572ad88b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 369de98e944c5ccf5d06ef61eaa16c06bb864e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568967"
---
# <a name="modifying-and-processing-the-market-basket-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="914f0-102">Modificando e processando o modelo de cesta de compras (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="914f0-102">Modifying and Processing the Market Basket Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="914f0-103">Antes de processar o modelo de mineração de associação que você criou, você deve alterar os valores padrão de dois dos parâmetros: *suporte* e *probabilidade*.</span><span class="sxs-lookup"><span data-stu-id="914f0-103">Before you process the association mining model that you created, you must change the default values of two of the parameters: *Support* and *Probability*.</span></span>  
  
-   <span data-ttu-id="914f0-104">O *suporte* define a porcentagem de casos em que uma regra deve existir antes de ser considerada válida.</span><span class="sxs-lookup"><span data-stu-id="914f0-104">*Support* defines the percentage of cases in which a rule must exist before it is considered valid.</span></span> <span data-ttu-id="914f0-105">Você especificará que uma regra deve ser encontrada em pelo menos 1 por cento dos casos.</span><span class="sxs-lookup"><span data-stu-id="914f0-105">You will specify that a rule must be found in at least 1 percent of cases.</span></span>  
  
-   <span data-ttu-id="914f0-106">*Probabilidade* define a probabilidade de que uma associação deve ser antes de ser considerada válida.</span><span class="sxs-lookup"><span data-stu-id="914f0-106">*Probability* defines how likely an association must be before it is considered valid.</span></span> <span data-ttu-id="914f0-107">Você vai considerar qualquer associação com a probabilidade de pelo menos 10 por cento.</span><span class="sxs-lookup"><span data-stu-id="914f0-107">You will consider any association with a probability of at least 10 percent.</span></span>  
  
 <span data-ttu-id="914f0-108">Para obter mais informações sobre os efeitos de aumentar ou diminuir o suporte e a probabilidade, consulte [referência técnica do algoritmo de associação da Microsoft](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="914f0-108">For more information about the effects of increasing or decreasing support and probability, see [Microsoft Association Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="914f0-109">Depois de definir a estrutura e os parâmetros para o modelo de mineração de **Associação** , você processará o modelo.</span><span class="sxs-lookup"><span data-stu-id="914f0-109">After you have defined the structure and parameters for the **Association** mining model, you will process the model.</span></span>  
  
### <a name="to-adjust-the-parameters-of-the-association-model"></a><span data-ttu-id="914f0-110">Para ajustar os parâmetros do modelo de Associação</span><span class="sxs-lookup"><span data-stu-id="914f0-110">To adjust the parameters of the Association model</span></span>  
  
1.  <span data-ttu-id="914f0-111">Abra a guia **modelos de mineração** do designer de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="914f0-111">Open the **Mining Models** tab of Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="914f0-112">Clique com o botão direito do mouse na coluna **Associação** na grade no designer e selecione **definir parâmetros de algoritmo para abrir a caixa de diálogo parâmetros de algoritmo** .</span><span class="sxs-lookup"><span data-stu-id="914f0-112">Right-click the **Association** column in the grid in the designer and select **Set Algorithm Parameters to open the Algorithm Parameters** dialog box.</span></span>  
  
3.  <span data-ttu-id="914f0-113">Na coluna **valor** da caixa de diálogo **parâmetros do algoritmo** , defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="914f0-113">In the **Value** column of the **Algorithm Parameters** dialog box, set the following parameters:</span></span>  
  
     <span data-ttu-id="914f0-114">MINIMUM_PROBABILITY = 0.1</span><span class="sxs-lookup"><span data-stu-id="914f0-114">MINIMUM_PROBABILITY = 0.1</span></span>  
  
     <span data-ttu-id="914f0-115">MINIMUM_SUPPORT = 0.01</span><span class="sxs-lookup"><span data-stu-id="914f0-115">MINIMUM_SUPPORT = 0.01</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-process-the-mining-model"></a><span data-ttu-id="914f0-116">Para processar o modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="914f0-116">To process the mining model</span></span>  
  
1.  <span data-ttu-id="914f0-117">No menu **modelo de mineração** do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , selecione **estrutura de mineração de processo e todos os modelos.**</span><span class="sxs-lookup"><span data-stu-id="914f0-117">On the **Mining Model** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select **Process Mining Structure and All Models.**</span></span>  
  
2.  <span data-ttu-id="914f0-118">No aviso que pergunta se você deseja construir e implantar o projeto, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="914f0-118">At the warning asking whether you want to build and deploy the project, click **Yes**.</span></span>  
  
     <span data-ttu-id="914f0-119">A caixa de diálogo **processar estrutura de mineração-Associação** é aberta.</span><span class="sxs-lookup"><span data-stu-id="914f0-119">The **Process Mining Structure - Association** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="914f0-120">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="914f0-120">Click **Run**.</span></span>  
  
     <span data-ttu-id="914f0-121">A caixa de diálogo **Andamento do Processo** é aberta para exibir informações sobre o processamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="914f0-121">The **Process Progress** dialog box opens to display information about model processing.</span></span> <span data-ttu-id="914f0-122">O processamento da estrutura e do modelo novos pode demorar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="914f0-122">Processing of the new structure and model might take some time.</span></span>  
  
4.  <span data-ttu-id="914f0-123">Depois que o processamento estiver completo, clique em **Fechar** para sair da caixa de diálogo **Progresso do Processo** .</span><span class="sxs-lookup"><span data-stu-id="914f0-123">After processing is complete, click **Close** to exit the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="914f0-124">Clique em **fechar** novamente para sair da caixa de diálogo **processar estrutura de mineração-Associação** .</span><span class="sxs-lookup"><span data-stu-id="914f0-124">Click **Close** again to exit the **Process Mining Structure - Association** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="914f0-125">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="914f0-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="914f0-126">Explorando os modelos de cesta de mercado &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="914f0-126">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="914f0-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="914f0-127">See Also</span></span>  
 [<span data-ttu-id="914f0-128">Requisitos e considerações de processamento &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="914f0-128">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
