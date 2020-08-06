---
title: Adicionando uma exibição da fonte de dados com tabelas aninhadas (tutorial de mineração de dados intermediário) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a14cd7f1-7a10-4ec6-af6a-f5f0676a0308
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: da1a9bff093e0b59e9d1166554d95bcf61aded08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683219"
---
# <a name="adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial"></a><span data-ttu-id="95fe6-102">Adicionando uma exibição da fonte de dados com tabelas aninhadas (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="95fe6-102">Adding a Data Source View with Nested Tables (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="95fe6-103">Para criar um modelo de cesta de compras, você deve usar uma exibição da fonte de dados que dá suporte a dados associativos.</span><span class="sxs-lookup"><span data-stu-id="95fe6-103">To create a market basket model, you must use a data source view that supports associative data.</span></span> <span data-ttu-id="95fe6-104">Essa fonte de dados também será usada para o cenário de clustering de sequências.</span><span class="sxs-lookup"><span data-stu-id="95fe6-104">This data source view will also be used for the sequence clustering scenario.</span></span>  
  
 <span data-ttu-id="95fe6-105">Essa exibição da fonte de dados é diferente de outras com as quais você pode ter trabalhado porque contém uma *tabela aninhada*.</span><span class="sxs-lookup"><span data-stu-id="95fe6-105">This data source view is different from others that you may have worked with because it contains a *nested table*.</span></span> <span data-ttu-id="95fe6-106">Uma *tabela aninhada* é uma tabela que contém várias linhas de informações sobre uma única linha na tabela de casos.</span><span class="sxs-lookup"><span data-stu-id="95fe6-106">A *nested table* is a table that contains multiple rows of information about a single row in the case table.</span></span> <span data-ttu-id="95fe6-107">Por exemplo, se o seu modelo analisasse o comportamento de compra de clientes, normalmente você usaria uma tabela com uma linha exclusiva para cada cliente como a tabela de casos.</span><span class="sxs-lookup"><span data-stu-id="95fe6-107">For example, if your model analyzes the purchasing behavior of customers, you would typically use a table that has a unique row for each customer as the case table.</span></span> <span data-ttu-id="95fe6-108">No entanto, cada cliente pode fazer várias compras e talvez você queira analisar a sequência de compras ou os produtos comprados juntos com frequência.</span><span class="sxs-lookup"><span data-stu-id="95fe6-108">However, each customer might make multiple purchases, and you might want to analyze the sequence of purchases, or products that are frequently purchased together.</span></span> <span data-ttu-id="95fe6-109">Para representar logicamente essas compras no modelo, adicione outra tabela à exibição da fonte de dados que lista as compras para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="95fe6-109">To logically represent these purchases in your model, you add another table to the data source view that lists the purchases for each customer.</span></span>  
  
 <span data-ttu-id="95fe6-110">Essa tabela de compras aninhada está relacionada à tabela de clientes uma relação muitos para um.</span><span class="sxs-lookup"><span data-stu-id="95fe6-110">This nested purchases table is related to the customer table by a many-to-one relationship.</span></span> <span data-ttu-id="95fe6-111">A tabela aninhada pode conter várias linhas para cada cliente, cada linha com um único produto comprado, talvez com informações adicionais sobre o pedido em que as compras foram feitas, o preço no momento do pedido ou qualquer promoção aplicável.</span><span class="sxs-lookup"><span data-stu-id="95fe6-111">The nested table might contain many rows for each customer, each row containing a single product that was purchased, perhaps with additional information about the order that the purchases were made, the price at the time of the order, or any promotions that applied.</span></span> <span data-ttu-id="95fe6-112">É possível usar as informações da tabela aninhada como entradas para o modelo ou como o atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="95fe6-112">You can use the information in the nested table as inputs to the model, or as the predictable attribute.</span></span>  
  
 <span data-ttu-id="95fe6-113">Nesta lição, você executa as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="95fe6-113">In this lesson, you do the following tasks:</span></span>  
  
-   <span data-ttu-id="95fe6-114">Você adiciona uma exibição da fonte de dados à [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="95fe6-114">You add a data source view to the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source.</span></span>  
  
-   <span data-ttu-id="95fe6-115">Você adiciona as tabelas de casos e aninhada a essa exibição.</span><span class="sxs-lookup"><span data-stu-id="95fe6-115">You add the case and nested tables to this view.</span></span>  
  
-   <span data-ttu-id="95fe6-116">Você especifica a relação muitos para um entre as tabelas de casos e aninhada.</span><span class="sxs-lookup"><span data-stu-id="95fe6-116">You specify the many-to-one relationship between the case and nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95fe6-117">.</span><span class="sxs-lookup"><span data-stu-id="95fe6-117">.</span></span> <span data-ttu-id="95fe6-118">É importante seguir o procedimento descrito com exatidão para especificar corretamente a relação entre a tabela de casos e a tabela aninhada e evitar erros durante o processamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="95fe6-118">It is important that you follow the described procedure exactly, to correctly specify the relationship between the case table and the nested table and to avoid errors when you process the model.</span></span>  
  
-   <span data-ttu-id="95fe6-119">Você define como as colunas de dados são usadas no modelo.</span><span class="sxs-lookup"><span data-stu-id="95fe6-119">You define how the columns of data are used in the model.</span></span>  
  
 <span data-ttu-id="95fe6-120">Para obter mais informações sobre como trabalhar com tabelas de casos e aninhadas e como escolher uma chave de tabela aninhada, consulte [tabelas aninhadas &#40;Analysis Services&#41;de mineração de dados ](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="95fe6-120">For more information about working with case and nested tables, and how to choose a nested table key, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="95fe6-121">Para adicionar uma exibição da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="95fe6-121">To add a data source view</span></span>  
  
1.  <span data-ttu-id="95fe6-122">Em Gerenciador de Soluções, clique com o botão direito do mouse em **exibições da fonte de dados**e selecione **nova exibição da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="95fe6-122">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
     <span data-ttu-id="95fe6-123">O Assistente de Exibição da Fonte de Dados é exibido.</span><span class="sxs-lookup"><span data-stu-id="95fe6-123">The Data Source View Wizard opens.</span></span>  
  
2.  <span data-ttu-id="95fe6-124">Na página **Bem-vindo ao Assistente de Exibição da Fonte de Dados** , clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="95fe6-124">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="95fe6-125">Na página **selecionar uma fonte de dados** , em **fontes de dados relacionais**, selecione a [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] fonte de dados que você criou no tutorial de mineração de dados básico.</span><span class="sxs-lookup"><span data-stu-id="95fe6-125">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source that you created in the Basic Data Mining Tutorial.</span></span> <span data-ttu-id="95fe6-126">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="95fe6-126">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="95fe6-127">Na página **selecionar tabelas e exibições** , selecione as tabelas a seguir e clique na seta para a direita para incluí-las na nova exibição da fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="95fe6-127">On the **Select Tables and Views** page, select the following tables, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   `vAssocSeqOrders`  
  
    -   `vAssocSeqLineItems`  
  
5.  <span data-ttu-id="95fe6-128">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="95fe6-128">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="95fe6-129">Na página **concluindo o assistente** , por padrão, a exibição da fonte de dados é denominada [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95fe6-129">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="95fe6-130">Altere o nome para `Orders` e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="95fe6-130">Change the name to `Orders`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="95fe6-131">O designer de exibição da fonte de dados é aberto e a `Orders` exibição da fonte de dados é exibida.</span><span class="sxs-lookup"><span data-stu-id="95fe6-131">Data Source View Designer opens and the `Orders` data source view appears.</span></span>  
  
### <a name="to-create-a-relationship-between-tables"></a><span data-ttu-id="95fe6-132">Para criar uma relação entre tabelas</span><span class="sxs-lookup"><span data-stu-id="95fe6-132">To create a relationship between tables</span></span>  
  
1.  <span data-ttu-id="95fe6-133">No Designer da Exibição da Fonte de Dados, posicione as duas tabelas para que elas se alinhem horizontalmente, com a tabela vAssocSeqLineItems no lado esquerdo e a tabela vAssocSeqOrders no lado direito.</span><span class="sxs-lookup"><span data-stu-id="95fe6-133">In Data Source View Designer, position the two tables so that the tables are aligned horizontally, with the vAssocSeqLineItems table on the left side and the vAssocSeqOrders table on the right side.</span></span>  
  
2.  <span data-ttu-id="95fe6-134">Selecione a coluna **OrderNumber** na tabela vAssocSeqLineItems.</span><span class="sxs-lookup"><span data-stu-id="95fe6-134">Select the **OrderNumber** column in the vAssocSeqLineItems table.</span></span>  
  
3.  <span data-ttu-id="95fe6-135">Arraste a coluna para a tabela vAssocSeqOrders e coloque-a na coluna **OrderNumber** .</span><span class="sxs-lookup"><span data-stu-id="95fe6-135">Drag the column to the vAssocSeqOrders table, and put it on the **OrderNumber** column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="95fe6-136">Certifique-se de arrastar a coluna **OrderNumber** da tabela aninhada vAssocSeqLineItems, que representa o lado muitos da junção, para a tabela de casos vAssocSeqOrders, que representa o lado um da junção.</span><span class="sxs-lookup"><span data-stu-id="95fe6-136">Make sure to drag the **OrderNumber** column from the vAssocSeqLineItems nested table, which represents the many side of the join, to the vAssocSeqOrders case table, which represents the one side of the join.</span></span>  
  
     <span data-ttu-id="95fe6-137">Uma nova *relação muitos para um* agora existe entre as tabelas VAssocSeqLineItems e vAssocSeqOrders.</span><span class="sxs-lookup"><span data-stu-id="95fe6-137">A new *many-to-one relationship* now exists between the vAssocSeqLineItems and vAssocSeqOrders tables.</span></span> <span data-ttu-id="95fe6-138">Se você uniu as tabelas corretamente, a exibição da fonte de dados deverá ser parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="95fe6-138">If you have joined the tables correctly, the data source view should appear as follows:</span></span>  
  
     <span data-ttu-id="95fe6-139">![esperada junção muitos-para-um em tabelas aninhadas e de caso](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "esperada junção muitos-para-um em tabelas aninhadas e de caso")</span><span class="sxs-lookup"><span data-stu-id="95fe6-139">![expected many-to-one join on nested and case table](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "expected many-to-one join on nested and case table")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="95fe6-140">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="95fe6-140">Next Task in Lesson</span></span>  
 [<span data-ttu-id="95fe6-141">Criando uma estrutura de cesta de mercado e um modelo &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="95fe6-141">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="95fe6-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="95fe6-142">See Also</span></span>  
 <span data-ttu-id="95fe6-143">[Tutorial de mineração de dados intermediário &#40;Analysis Services de mineração de dados&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="95fe6-143">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="95fe6-144">[Estruturas de mineração &#40;Analysis Services de mineração de dados&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="95fe6-144">[Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="95fe6-145">Modelos de mineração &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="95fe6-145">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-models-analysis-services-data-mining.md)  
  
  
