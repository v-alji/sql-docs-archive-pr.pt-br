---
title: Criando uma estrutura de modelo de mineração de clustering de sequências (tutorial de mineração de dados intermediário) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9339227-6c2e-4c4b-8be2-8c1960bc4a8d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 37d0a1738a758a9d8c4fd6b80310037937a9803f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572296"
---
# <a name="creating-a-sequence-clustering-mining-model-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="8f0b0-102">Criando uma estrutura de modelo de mineração de clustering de sequências (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="8f0b0-102">Creating a Sequence Clustering Mining Model Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="8f0b0-103">A primeira etapa da criação de um modelo de mineração de clustering de sequências é usar o Assistente de Mineração de Dados para criar uma nova estrutura de mineração e um modelo de mineração baseado no algoritmo Clustering de Sequências da [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f0b0-103">The first step in creating a sequence clustering mining model is to use the Data Mining Wizard to create a new mining structure and a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm.</span></span>  
  
 <span data-ttu-id="8f0b0-104">Você usará a mesma exibição da fonte de dados utilizada para a análise da cesta de compras, mas adicionará uma coluna com o identificador `sequence`.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-104">You will use the same data source view that you used for the market basket analysis, but you will add a column that contains the `sequence` identifier.</span></span> <span data-ttu-id="8f0b0-105">Neste cenário, a sequência significa a ordem em que o cliente adicionou itens à cesta de compras.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-105">In this scenario, the sequence means the order in which the customer added items to the shopping basket.</span></span>  
  
 <span data-ttu-id="8f0b0-106">Você também adicionará algumas colunas usadas em um dos modelos para agrupar clientes por dados demográficos.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-106">You will also add some columns that are used in one of the models to group customers by demographics.</span></span>  
  
### <a name="to-create-a-sequence-clustering-structure-and-model"></a><span data-ttu-id="8f0b0-107">Para criar uma estrutura e um modelo de de clustering de sequências</span><span class="sxs-lookup"><span data-stu-id="8f0b0-107">To create a sequence clustering structure and model</span></span>  
  
1.  <span data-ttu-id="8f0b0-108">Em Gerenciador de Soluções no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , clique com o botão direito do mouse em **estruturas de mineração** e selecione **nova estrutura de mineração**.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-108">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="8f0b0-109">Na página **Bem-vindo ao Assistente de Mineração de Dados** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-109">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="8f0b0-110">Na página **selecionar o método de definição** , verifique se a **partir de banco de dados relacional existente ou data warehouse** está selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-110">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="8f0b0-111">Na página **criar a estrutura de mineração de dados** , verifique se a opção **criar estrutura de mineração com um modelo de mineração** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-111">On the **Create the Data Mining Structure** page, verify that the option **Create mining structure with a mining model** is selected.</span></span> <span data-ttu-id="8f0b0-112">Em seguida, clique na lista suspensa da opção, **que data mining técnica deseja usar?** e selecione **clustering de sequências da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-112">Next, click the dropdown list for the option, **Which data mining technique do you want to use?**, and select **Microsoft Sequence Clustering**.</span></span> <span data-ttu-id="8f0b0-113">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-113">Click **Next**.</span></span>  
  
     <span data-ttu-id="8f0b0-114">A página **selecionar exibição da fonte de dados** é exibida.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-114">The **Select Data Source View** page appears.</span></span> <span data-ttu-id="8f0b0-115">Em **exibições da fonte de dados disponíveis**, selecione `Orders` .</span><span class="sxs-lookup"><span data-stu-id="8f0b0-115">Under **Available data source views**, select `Orders`.</span></span>  
  
     <span data-ttu-id="8f0b0-116">Pedidos é a mesma exibição da fonte de dados utilizada para a análise do cenário de cesta de compras.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-116">Orders is the same data source view that you used for the market basket scenario.</span></span> <span data-ttu-id="8f0b0-117">Se você não tiver criado essa exibição da fonte de dados, consulte [o tutorial adicionar uma exibição da fonte de dados com tabelas aninhadas &#40;&#41;de mineração de dados intermediários ](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="8f0b0-117">If you have not created this data source view, see [Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="8f0b0-118">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-118">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="8f0b0-119">Na página **especificar tipos de tabela** , marque a caixa de seleção **caso** ao lado da tabela **vAssocSeqOrders** e marque a caixa de seleção **aninhada** ao lado da tabela **vAssocSeqLineItems** .</span><span class="sxs-lookup"><span data-stu-id="8f0b0-119">On the **Specify Table Types** page, select the **Case** check box next to the **vAssocSeqOrders** table, and select the **Nested** check box next to the **vAssocSeqLineItems** table.</span></span> <span data-ttu-id="8f0b0-120">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-120">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f0b0-121">Se ocorrer um erro quando você marcar as caixas de seleção **caso** ou **aninhado** , pode ser que a junção na exibição da fonte de dados não esteja correta.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-121">If an error occurs when you select the **Case** or **Nested** check boxes, it may be that the join in the data source view is not correct.</span></span> <span data-ttu-id="8f0b0-122">A tabela aninhada, **vAssocSeqLineItems**, deve estar conectada à tabela de casos, **vAssocSeqOrders,** por uma junção de muitos para um.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-122">The nested table, **vAssocSeqLineItems**, must be connected to the case table, **vAssocSeqOrders,** by a many-to-one join.</span></span> <span data-ttu-id="8f0b0-123">Você pode editar a relação clicando com o botão direito do mouse na linha de junção e invertendo a direção da junção.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-123">You can edit the relationship by right-clicking on the join line and then reversing the direction of the join.</span></span> <span data-ttu-id="8f0b0-124">Para obter mais informações, consulte [a caixa de diálogo criar ou editar relação &#40;Analysis Services-&#41;de dados multidimensionais ](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="8f0b0-124">For more information, see [Create or Edit Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
7.  <span data-ttu-id="8f0b0-125">Na página **especificar os dados de treinamento** , escolha as colunas a serem usadas no modelo marcando uma caixa de seleção da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="8f0b0-125">On the **Specify the Training Data** page, choose the columns for use in the model by selecting a check box as follows:</span></span>  
  
    -   <span data-ttu-id="8f0b0-126">**Invir** Marque a caixa de seleção **entrada** .</span><span class="sxs-lookup"><span data-stu-id="8f0b0-126">**IncomeGroup** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="8f0b0-127">Essa coluna contém informações interessantes sobre os clientes que poderão ser usadas para clustering.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-127">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="8f0b0-128">Você a usará no primeiro modelo e vai ignorá-la no segundo.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-128">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="8f0b0-129">**OrderNumber** Marque a `Key` caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-129">**OrderNumber** Select the `Key` check box.</span></span>  
  
         <span data-ttu-id="8f0b0-130">Esse campo será usado como o identificador da tabela de casos, ou `Key`.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-130">This field will be used as the identifier for the case table, or `Key`.</span></span> <span data-ttu-id="8f0b0-131">Em geral, você nunca deve usar o campo de chave da tabela de casos como uma entrada, já que a chave contém valores exclusivos que não são úteis para clustering.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-131">In general, you should never use the key field of the case table as an input, because the key contains unique values that are not useful for clustering.</span></span>  
  
    -   <span data-ttu-id="8f0b0-132">**Região** do Marque a caixa de seleção **entrada** .</span><span class="sxs-lookup"><span data-stu-id="8f0b0-132">**Region** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="8f0b0-133">Essa coluna contém informações interessantes sobre os clientes que poderão ser usadas para clustering.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-133">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="8f0b0-134">Você a usará no primeiro modelo e vai ignorá-la no segundo.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-134">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="8f0b0-135">**LineNumber** Marque as `Key` caixas de seleção e de **entrada** .</span><span class="sxs-lookup"><span data-stu-id="8f0b0-135">**LineNumber** Select the `Key` and **Input** check boxes.</span></span>  
  
         <span data-ttu-id="8f0b0-136">O campo **LineNumber** será usado como o identificador para a tabela aninhada ou `Sequence Key` .</span><span class="sxs-lookup"><span data-stu-id="8f0b0-136">The **LineNumber** field will be used as the identifier for the nested table, or `Sequence Key`.</span></span> <span data-ttu-id="8f0b0-137">A chave para uma tabela aninhada sempre deve ser usada como entrada.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-137">The key for a nested table must always be used for input.</span></span>  
  
    -   <span data-ttu-id="8f0b0-138">**Modelo** Marque as caixas de seleção **entrada** e **previsível** .</span><span class="sxs-lookup"><span data-stu-id="8f0b0-138">**Model** Select the **Input** and **Predictable** check boxes.</span></span>  
  
     <span data-ttu-id="8f0b0-139">Verifique se as seleções estão corretas e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-139">Verify that the selections are correct, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="8f0b0-140">Na página **especificar conteúdo e tipo de dados das colunas** , verifique se a grade contém as colunas, os tipos de conteúdo e os tipos de dados mostrados na tabela a seguir e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-140">On the **Specify Columns' Content and Data Type** page, verify that the grid contains the columns, content types, and data types shown in the following table, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="8f0b0-141">Tabelas/Colunas</span><span class="sxs-lookup"><span data-stu-id="8f0b0-141">Tables/Columns</span></span>|<span data-ttu-id="8f0b0-142">Tipo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="8f0b0-142">Content Type</span></span>|<span data-ttu-id="8f0b0-143">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="8f0b0-143">Data Type</span></span>|  
    |---------------------|------------------|---------------|  
    |<span data-ttu-id="8f0b0-144">IncomeGroup</span><span class="sxs-lookup"><span data-stu-id="8f0b0-144">IncomeGroup</span></span>|<span data-ttu-id="8f0b0-145">Discreto</span><span class="sxs-lookup"><span data-stu-id="8f0b0-145">Discrete</span></span>|<span data-ttu-id="8f0b0-146">Texto</span><span class="sxs-lookup"><span data-stu-id="8f0b0-146">Text</span></span>|  
    |<span data-ttu-id="8f0b0-147">OrderNumber</span><span class="sxs-lookup"><span data-stu-id="8f0b0-147">OrderNumber</span></span>|<span data-ttu-id="8f0b0-148">Chave</span><span class="sxs-lookup"><span data-stu-id="8f0b0-148">Key</span></span>|<span data-ttu-id="8f0b0-149">Texto</span><span class="sxs-lookup"><span data-stu-id="8f0b0-149">Text</span></span>|  
    |<span data-ttu-id="8f0b0-150">Região</span><span class="sxs-lookup"><span data-stu-id="8f0b0-150">Region</span></span>|<span data-ttu-id="8f0b0-151">Discreto</span><span class="sxs-lookup"><span data-stu-id="8f0b0-151">Discrete</span></span>|<span data-ttu-id="8f0b0-152">Texto</span><span class="sxs-lookup"><span data-stu-id="8f0b0-152">Text</span></span>|  
    |<span data-ttu-id="8f0b0-153">vAssocSeqLineItems</span><span class="sxs-lookup"><span data-stu-id="8f0b0-153">vAssocSeqLineItems</span></span>|||  
    |<span data-ttu-id="8f0b0-154">Número da Linha</span><span class="sxs-lookup"><span data-stu-id="8f0b0-154">Line Number</span></span>|<span data-ttu-id="8f0b0-155">Key Sequence</span><span class="sxs-lookup"><span data-stu-id="8f0b0-155">Key Sequence</span></span>|<span data-ttu-id="8f0b0-156">long</span><span class="sxs-lookup"><span data-stu-id="8f0b0-156">Long</span></span>|  
    |<span data-ttu-id="8f0b0-157">Modelo</span><span class="sxs-lookup"><span data-stu-id="8f0b0-157">Model</span></span>|<span data-ttu-id="8f0b0-158">Discreto</span><span class="sxs-lookup"><span data-stu-id="8f0b0-158">Discrete</span></span>|<span data-ttu-id="8f0b0-159">Texto</span><span class="sxs-lookup"><span data-stu-id="8f0b0-159">Text</span></span>|  
  
9. <span data-ttu-id="8f0b0-160">Na página **criar conjunto de testes** , altere a **porcentagem de dados para teste** para 20 e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-160">On the **Create Testing Set** page, change the **Percentage of data for testing** to 20, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="8f0b0-161">Na página **concluindo o assistente** , para o **nome da estrutura de mineração**, digite `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="8f0b0-161">On the **Completing the Wizard** page, for the **Mining structure name**, type `Sequence Clustering with Region`.</span></span>  
  
11. <span data-ttu-id="8f0b0-162">Para o **nome do modelo de mineração**, digite `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="8f0b0-162">For the **Mining model name**, type `Sequence Clustering with Region`.</span></span>  
  
12. <span data-ttu-id="8f0b0-163">Marque a caixa **permitir Drill-through** e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="8f0b0-163">Check the **Allow drill through** box, and then click **Finish**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8f0b0-164">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="8f0b0-164">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8f0b0-165">Processando o modelo de clustering de sequências</span><span class="sxs-lookup"><span data-stu-id="8f0b0-165">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="8f0b0-166">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f0b0-166">See Also</span></span>  
 <span data-ttu-id="8f0b0-167">[Designer de mineração de dados](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="8f0b0-167">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="8f0b0-168">Microsoft Sequence Clustering Algorithm</span><span class="sxs-lookup"><span data-stu-id="8f0b0-168">Microsoft Sequence Clustering Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md)  
  
  
