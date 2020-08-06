---
title: 'Lição 3: adicionando e processando modelos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: cc29927a-c368-4b8a-bbd0-af89a9f54dc9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 5da034089d8bbe7f1a967258d195a56ddbf13c03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569751"
---
# <a name="lesson-3-adding-and-processing-models"></a><span data-ttu-id="ff86f-102">Lição 3: Adicionando e processando modelos</span><span class="sxs-lookup"><span data-stu-id="ff86f-102">Lesson 3: Adding and Processing Models</span></span>
  <span data-ttu-id="ff86f-103">A estrutura de mineração inicial que você criou na lição anterior contém um único modelo de mineração que se baseia no algoritmo Árvores de Decisão da [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff86f-103">The mining structure that you created in the previous lesson contains a single mining model that is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="ff86f-104">Você pode usar este modelo para identificar clientes para a campanha de envio de destino.</span><span class="sxs-lookup"><span data-stu-id="ff86f-104">You can use this model to identify customers for the targeted mailing campaign.</span></span> <span data-ttu-id="ff86f-105">Porém, para assegurar que sua análise seja completa, é uma prática comum criar modelos relacionados usando algoritmos diferentes e comparar seus resultados.</span><span class="sxs-lookup"><span data-stu-id="ff86f-105">However, to ensure that your analysis is thorough, it is a common practice to create related models using different algorithms and compare their results.</span></span> <span data-ttu-id="ff86f-106">Assim, você também pode obter diferentes visões.</span><span class="sxs-lookup"><span data-stu-id="ff86f-106">That way you can get different insights as well.</span></span> <span data-ttu-id="ff86f-107">Portanto, você criará dois modelos adicionais e, depois, processará e implantará os modelos.</span><span class="sxs-lookup"><span data-stu-id="ff86f-107">Therefore, you will create two additional models, then process and deploy the models.</span></span>  
  
 <span data-ttu-id="ff86f-108">Nesta lição, você criará um conjunto de modelos de mineração com sugestões dos clientes mais prováveis a partir de uma lista de clientes potenciais.</span><span class="sxs-lookup"><span data-stu-id="ff86f-108">In this lesson, you will create a set of mining models that will suggest the most likely customers from a list of potential customers.</span></span>  
  
 <span data-ttu-id="ff86f-109">Para concluir as tarefas nesta lição, você usará o [algoritmo Microsoft Clustering](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) e o [algoritmo Microsoft Naive Bayes](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="ff86f-109">To complete the tasks in this lesson, you will use the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and the [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="ff86f-110">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="ff86f-110">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="ff86f-111">Adicionando novos modelos à estrutura de mala direta direcionada &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="ff86f-111">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="ff86f-112">Processando modelos na estrutura de mala direta direcionada &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="ff86f-112">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="ff86f-113">Primeira tarefa na lição</span><span class="sxs-lookup"><span data-stu-id="ff86f-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="ff86f-114">Adicionando novos modelos à estrutura de mala direta direcionada &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="ff86f-114">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="ff86f-115">Lição anterior</span><span class="sxs-lookup"><span data-stu-id="ff86f-115">Previous Lesson</span></span>  
 [<span data-ttu-id="ff86f-116">Lição 2: criando uma estrutura de endereçamento direcionada &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="ff86f-116">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="ff86f-117">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="ff86f-117">Next Lesson</span></span>  
 [<span data-ttu-id="ff86f-118">Lição 4: explorando os modelos de mala direta direcionados &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="ff86f-118">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff86f-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ff86f-119">See Also</span></span>  
 [<span data-ttu-id="ff86f-120">Adicionar Modelos de Mineração a uma estrutura &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ff86f-120">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md)  
  
  
