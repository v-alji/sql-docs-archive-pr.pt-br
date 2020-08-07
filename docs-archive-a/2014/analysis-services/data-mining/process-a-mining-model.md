---
title: Processar um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], processing
ms.assetid: c2204472-c500-47a5-9afa-7ce2ca78b233
author: minewiskan
ms.author: owend
ms.openlocfilehash: c2fed5d72c677dc175f4c9681096d1859b30d829
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681920"
---
# <a name="process-a-mining-model"></a><span data-ttu-id="c527b-102">Processar um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="c527b-102">Process a Mining Model</span></span>
  <span data-ttu-id="c527b-103">Na guia Modelos de Mineração do Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], você pode processar um modelo de mineração específico que está associado a uma estrutura de mineração ou processar todos os modelos que estão associados com a estrutura.</span><span class="sxs-lookup"><span data-stu-id="c527b-103">In the Mining Models tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can either process a specific mining model that is associated with a mining structure or you can process all the models that are associated with the structure.</span></span>  
  
 <span data-ttu-id="c527b-104">É possível processar um modelo de mineração usando as seguintes ferramentas:</span><span class="sxs-lookup"><span data-stu-id="c527b-104">You can process a mining model by using the following tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
 <span data-ttu-id="c527b-105">Você também pode usar um comando do processo XMLA.</span><span class="sxs-lookup"><span data-stu-id="c527b-105">You can also use an XMLA Process command.</span></span> <span data-ttu-id="c527b-106">Para obter mais informações, consulte [ferramentas e abordagens para processar &#40;Analysis Services&#41;](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="c527b-106">For more information, see  [Tools and Approaches for Processing &#40;Analysis Services&#41;](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span></span>  
  
### <a name="process-a-single-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="c527b-107">Processar um único modelo de mineração usando as Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="c527b-107">Process a single mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="c527b-108">Na guia **Modelos de Mineração** do Designer de Mineração de Dados, selecione um modelo de mineração de uma ou mais colunas de modelos na grade.</span><span class="sxs-lookup"><span data-stu-id="c527b-108">On the **Mining Models** tab of Data Mining Designer, select a mining model from the one or more columns of models in the grid.</span></span>  
  
2.  <span data-ttu-id="c527b-109">No menu **Modelo de Mineração** , selecione **Processar Modelo**.</span><span class="sxs-lookup"><span data-stu-id="c527b-109">On the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="c527b-110">Caso faça uma alteração na estrutura de mineração, você receberá uma solicitação para implantar a estrutura novamente antes de processar o modelo.</span><span class="sxs-lookup"><span data-stu-id="c527b-110">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the model.</span></span> <span data-ttu-id="c527b-111">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c527b-111">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="c527b-112">Na caixa de diálogo **processando \<model> modelo de mineração –** , clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="c527b-112">In the **Processing Mining Model - \<model>** dialog box, click **Run**.</span></span>  
  
     <span data-ttu-id="c527b-113">A caixa de diálogo **Andamento do Processo** é aberta e exibe os detalhes sobre o processamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="c527b-113">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
4.  <span data-ttu-id="c527b-114">Clique em **Fechar** na caixa de diálogo **Andamento do Processo** , após o modelo completar seu processamento.</span><span class="sxs-lookup"><span data-stu-id="c527b-114">After the model has successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="c527b-115">Clique em **fechar** na caixa de diálogo **processando \<model> modelo de mineração** .</span><span class="sxs-lookup"><span data-stu-id="c527b-115">Click **Close** in the **Processing Mining Model - \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="c527b-116">Só foram processados a estrutura de mineração e o modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="c527b-116">Only the mining structure and the selected mining model have been processed.</span></span>  
  
### <a name="process-all-mining-models-that-are-associated-with-a-mining-structure"></a><span data-ttu-id="c527b-117">Processar todos os modelos de mineração que estão associados com uma estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="c527b-117">Process all mining models that are associated with a mining structure</span></span>  
  
1.  <span data-ttu-id="c527b-118">Na guia **Modelos de Mineração** do Designer de Mineração de Dados, selecione **Processar Estrutura de Mineração e Todos os Modelos** a partir do menu **Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="c527b-118">On the **Mining Models** tab of Data Mining Designer, select **Process Mining Structure and All Models** from the **Mining Model** menu.</span></span>  
  
2.  <span data-ttu-id="c527b-119">Caso faça alterações na estrutura de mineração, você receberá uma solicitação para implantar a estrutura novamente antes de processar os modelos.</span><span class="sxs-lookup"><span data-stu-id="c527b-119">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="c527b-120">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c527b-120">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="c527b-121">Na caixa de diálogo **processando \<structure> estrutura de mineração –** , clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="c527b-121">In the **Processing Mining Structure - \<structure>** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="c527b-122">A caixa de diálogo **Andamento do Processo** é aberta e exibe os detalhes sobre o processamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="c527b-122">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
5.  <span data-ttu-id="c527b-123">Clique em **Fechar** na caixa de diálogo **Andamento do Processo** , após os modelos completarem seu processamento.</span><span class="sxs-lookup"><span data-stu-id="c527b-123">After the models have successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
6.  <span data-ttu-id="c527b-124">Clique em **fechar** na caixa de diálogo \*\*processamento \<model> \*\* .</span><span class="sxs-lookup"><span data-stu-id="c527b-124">Click **Close** in the **Processing \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="c527b-125">A estrutura de mineração e todos os modelos de mineração associados foram processados.</span><span class="sxs-lookup"><span data-stu-id="c527b-125">The mining structure and all the associated mining models have been processed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c527b-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c527b-126">See Also</span></span>  
 [<span data-ttu-id="c527b-127">Tarefas e instruções do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="c527b-127">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
