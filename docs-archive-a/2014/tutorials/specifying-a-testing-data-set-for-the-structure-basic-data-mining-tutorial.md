---
title: Especificando um conjunto de dados de teste para a estrutura (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75cd508f-b126-418b-848d-3c4c3e6c303f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c1430706a0ec2cd3ddc0eaee18d7001d05fefae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568958"
---
# <a name="specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial"></a><span data-ttu-id="e2bcb-102">Especificando um conjunto de dados de teste para a estrutura (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="e2bcb-102">Specifying a Testing Data Set for the Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="e2bcb-103">Nas últimas telas do Assistente de Mineração de Dados, você dividirá seus dados entre um conjunto de teste e um conjunto de treinamento.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-103">In the final few screens of the Data Mining Wizard you will split your data into a testing set and a training set.</span></span> <span data-ttu-id="e2bcb-104">Em seguida, dará um nome à sua estrutura e habilitará o detalhamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-104">You will then name your structure and enable drillthrough on the model.</span></span>  
  
## <a name="specifying-a-testing-set"></a><span data-ttu-id="e2bcb-105">Especificando um conjunto de teste</span><span class="sxs-lookup"><span data-stu-id="e2bcb-105">Specifying a Testing Set</span></span>  
 <span data-ttu-id="e2bcb-106">A separação dos dados em conjuntos de treinamento e de teste na criação de uma estrutura de mineração possibilita a avaliação fácil da precisão dos modelos de mineração criados posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-106">Separating data into training and testing sets when you create a mining structure makes it possible to easily assess the accuracy of the mining models that you create later.</span></span> <span data-ttu-id="e2bcb-107">Para obter mais informações sobre conjuntos de testes, consulte [conjuntos de dados de treinamento e teste](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="e2bcb-107">For more information on testing sets, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-specify-the-testing-set"></a><span data-ttu-id="e2bcb-108">Para especificar o conjunto de teste</span><span class="sxs-lookup"><span data-stu-id="e2bcb-108">To specify the testing set</span></span>  
  
1.  <span data-ttu-id="e2bcb-109">Na página **criar conjunto de testes** , para **percentual de dados para teste**, deixe o valor padrão de `30` .</span><span class="sxs-lookup"><span data-stu-id="e2bcb-109">On the **Create Testing Set** page, for **Percentage of data for testing**, leave the default value of `30`.</span></span>  
  
2.  <span data-ttu-id="e2bcb-110">Para o **número máximo de casos no conjunto de dados de teste**, digite `1000` .</span><span class="sxs-lookup"><span data-stu-id="e2bcb-110">For **Maximum number of cases in testing data set**, type `1000`.</span></span>  
  
3.  <span data-ttu-id="e2bcb-111">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-111">Click **Next**.</span></span>  
  
## <a name="specifying-drillthrough"></a><span data-ttu-id="e2bcb-112">Especificando o detalhamento</span><span class="sxs-lookup"><span data-stu-id="e2bcb-112">Specifying Drillthrough</span></span>  
 <span data-ttu-id="e2bcb-113">O detalhamento pode ser habilitado em modelos e em estruturas.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-113">Drillthrough can be enabled on models and on structures.</span></span> <span data-ttu-id="e2bcb-114">A caixa de seleção nesta caixa de diálogo permite o detalhamento no modelo nomeado.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-114">The checkbox in this dialog box enables drillthrough on the named model.</span></span> <span data-ttu-id="e2bcb-115">Depois que o modelo tiver sido processado, você poderá recuperar as informações detalhadas dos dados de treinamento que foram usados para criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-115">After the model has been processed,  you will be able to retrieve detailed information from the training data that were used to create the model.</span></span>  
  
 <span data-ttu-id="e2bcb-116">Se a estrutura de mineração subjacente também estiver configurada para permitir o detalhamento, você poderá recuperar informações detalhadas dos casos de modelo e da estrutura de mineração, inclusive colunas que não foram incluídas no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-116">If the underlying mining structure has also been configured to allow drillthrough, you can retrieve detailed information from both the model cases and the mining structure, including columns that were not included in the mining model.</span></span> <span data-ttu-id="e2bcb-117">Para obter mais informações, consulte [Consultas de detalhamento &#40;Mineração de dados&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="e2bcb-117">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span></span>  
  
#### <a name="to-name-the-model-and-structure-and-specify-drillthrough"></a><span data-ttu-id="e2bcb-118">Para nomear o modelo e a estrutura e especificar o detalhamento</span><span class="sxs-lookup"><span data-stu-id="e2bcb-118">To name the model and structure and specify drillthrough</span></span>  
  
1.  <span data-ttu-id="e2bcb-119">Na página **concluindo o assistente** , em **nome da estrutura de mineração**, digite `Targeted Mailing` .</span><span class="sxs-lookup"><span data-stu-id="e2bcb-119">On the **Completing the Wizard** page, in **Mining structure name**, type `Targeted Mailing`.</span></span>  
  
2.  <span data-ttu-id="e2bcb-120">Em **nome do modelo de mineração**, digite `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="e2bcb-120">In **Mining model name**, type `TM_Decision_Tree`.</span></span>  
  
3.  <span data-ttu-id="e2bcb-121">Marque a caixa de seleção **permitir Drill-through** .</span><span class="sxs-lookup"><span data-stu-id="e2bcb-121">Select the **Allow drill through** check box.</span></span>  
  
4.  <span data-ttu-id="e2bcb-122">Examine o painel de **Visualização** .</span><span class="sxs-lookup"><span data-stu-id="e2bcb-122">Review the **Preview** pane.</span></span> <span data-ttu-id="e2bcb-123">Observe que somente as colunas selecionadas como **chave**, **entrada** ou **previsível** são mostradas.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-123">Notice that only those columns selected as **Key**, **Input** or **Predictable** are shown.</span></span> <span data-ttu-id="e2bcb-124">As outras colunas selecionadas (como AddressLine1, por exemplo) não são usadas para a criação do modelo, mas estarão disponíveis na estrutura subjacente e podem ser consultadas após o processamento e a implantação do modelo.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-124">The other columns you selected (e.g., AddressLine1) are not used for building the model but will be available in the underlying structure, and can be queried after the model is processed and deployed.</span></span>  
  
5.  <span data-ttu-id="e2bcb-125">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="e2bcb-125">Click **Finish**.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="e2bcb-126">Tarefa anterior da lição</span><span class="sxs-lookup"><span data-stu-id="e2bcb-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="e2bcb-127">Especificando o tipo de dados e o tipo de conteúdo &#40;tutorial de mineração de dados básico&#41;</span><span class="sxs-lookup"><span data-stu-id="e2bcb-127">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="e2bcb-128">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="e2bcb-128">Next Lesson</span></span>  
 [<span data-ttu-id="e2bcb-129">Lição 3: Adicionando e processando modelos</span><span class="sxs-lookup"><span data-stu-id="e2bcb-129">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2bcb-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e2bcb-130">See Also</span></span>  
 <span data-ttu-id="e2bcb-131">[Habilitar detalhamento para um modelo de mineração](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="e2bcb-131">[Enable Drillthrough for a Mining Model](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span></span>  
 <span data-ttu-id="e2bcb-132">[Consultas de detalhamento &#40;mineração de dados&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e2bcb-132">[Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="e2bcb-133">Especifique os dados de treinamento &#40;assistente de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="e2bcb-133">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](../../2014/analysis-services/specify-the-training-data-data-mining-wizard.md)  
  
  
