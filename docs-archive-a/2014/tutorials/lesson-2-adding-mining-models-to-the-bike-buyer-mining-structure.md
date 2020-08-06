---
title: 'Lição 2: adicionando modelos de mineração à estrutura de mineração de compradores de bicicletas | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 03fe44c5-6452-4ed0-95f6-9682670c0f52
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: de65fb7a85154f607cd8f266faec4621cdc41476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681306"
---
# <a name="lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure"></a><span data-ttu-id="9ad70-102">Lição 2: Adicionando modelos de mineração à estrutura de mineração de Comprador de Bicicleta</span><span class="sxs-lookup"><span data-stu-id="9ad70-102">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="9ad70-103">Nesta lição, você adicionará dois modelos de mineração à estrutura de mineração de compradores de bicicletas que criou [a lição 1: criando a estrutura de mineração de compradores de bicicletas](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="9ad70-103">In this lesson, you will add two mining models to the Bike Buyer mining structure that you created [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md).</span></span> <span data-ttu-id="9ad70-104">Esses modelos de mineração lhe permitirão explorar os dados usando um modelo e criar previsões usando outro.</span><span class="sxs-lookup"><span data-stu-id="9ad70-104">These mining models will allow you to explore the data using one model, and to create predictions using another.</span></span>  
  
 <span data-ttu-id="9ad70-105">Para explorar como os clientes potenciais podem ser categorizados por suas características, você criará um modelo de mineração baseado no [algoritmo Microsoft Clustering](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="9ad70-105">To explore how potential customers can be categorized by their characteristics, you will create a mining model based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span> <span data-ttu-id="9ad70-106">Em uma lição posterior, você explorará como esse algoritmo localiza clusters de clientes que compartilham características semelhantes.</span><span class="sxs-lookup"><span data-stu-id="9ad70-106">In a later lesson, you will explore how this algorithm finds clusters of customers who share similar characteristics.</span></span> <span data-ttu-id="9ad70-107">Por exemplo, você pode identificar que alguns clientes tendem a viver perto de outros, andar de bicicleta e ter formação acadêmica similar.</span><span class="sxs-lookup"><span data-stu-id="9ad70-107">For example, you might find that certain customers tend to live close to each other, commute by bicycle, and have similar education backgrounds.</span></span> <span data-ttu-id="9ad70-108">É possível usar esses clusters para entender melhor como clientes diferentes estão relacionados e usar as informações para criar uma estratégia de marketing cujo alvo são clientes específicos.</span><span class="sxs-lookup"><span data-stu-id="9ad70-108">You can use these clusters to better understand how different customers are related, and to use the information to create a marketing strategy that targets specific customers.</span></span>  
  
 <span data-ttu-id="9ad70-109">Para prever se é provável que um cliente potencial compre uma bicicleta, você criará um modelo de mineração baseado no [algoritmo árvores de decisão da Microsoft](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="9ad70-109">To predict whether a potential customer is likely to buy a bicycle, you will create a mining model based on the [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="9ad70-110">Esse algoritmo verifica as informações associadas a cada cliente potencial e identifica características que são úteis para prever se eles comprarão uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="9ad70-110">This algorithm looks through the information that is associated with each potential customer, and finds characteristics that are useful in predicting if they will buy a bicycle.</span></span> <span data-ttu-id="9ad70-111">Em seguida, ele compara os valores das características dos compradores de bicicletas anteriores com as dos novos clientes potenciais para determinar se esses clientes novos têm probabilidade de comprar uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="9ad70-111">It then compares the values of the characteristics of previous bike buyers against new potential customers to determine whether the new potential customers are likely to buy a bicycle.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="9ad70-112">Instrução ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="9ad70-112">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="9ad70-113">Para adicionar um modelo de mineração à estrutura de mineração, use a instrução [ALTER MINING structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="9ad70-113">In order to add a mining model to the mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="9ad70-114">O código na instrução pode ser dividido nas seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="9ad70-114">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="9ad70-115">Identificando a estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="9ad70-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="9ad70-116">Nomeando o modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="9ad70-116">Naming the mining model</span></span>  
  
-   <span data-ttu-id="9ad70-117">Definindo a coluna de chave</span><span class="sxs-lookup"><span data-stu-id="9ad70-117">Defining the key column</span></span>  
  
-   <span data-ttu-id="9ad70-118">Definindo as colunas de entrada e as previsíveis</span><span class="sxs-lookup"><span data-stu-id="9ad70-118">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="9ad70-119">Identificando as alterações de algoritmo e de parâmetro</span><span class="sxs-lookup"><span data-stu-id="9ad70-119">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="9ad70-120">Veja a seguir um exemplo genérico da instrução ALTER MINING MODEL:</span><span class="sxs-lookup"><span data-stu-id="9ad70-120">The following is a generic example of the ALTER MINING MODEL statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
(  
    [<key column>],  
    <mining model columns>,  
) USING <algorithm name>( <algorithm parameters> )  
WITH FILTER (<expression>)  
```  
  
 <span data-ttu-id="9ad70-121">A primeira linha do código identifica a estrutura de mineração existente à qual os modelos de mineração serão adicionados:</span><span class="sxs-lookup"><span data-stu-id="9ad70-121">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="9ad70-122">A linha seguinte do código nomeia o modelo de mineração que será adicionado à estrutura de mineração:</span><span class="sxs-lookup"><span data-stu-id="9ad70-122">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="9ad70-123">Para obter informações sobre como nomear um objeto no DMX, consulte [identificadores &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="9ad70-123">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="9ad70-124">As linhas seguintes do código definem as colunas a partir da estrutura de mineração que será usada pelo modelo de mineração:</span><span class="sxs-lookup"><span data-stu-id="9ad70-124">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns>  
```  
  
 <span data-ttu-id="9ad70-125">Você só pode usar colunas que já existem na estrutura de mineração, e a primeira coluna na lista deve ser a coluna de chave da estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="9ad70-125">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="9ad70-126">A linha seguinte do código define o algoritmo de mineração que gera o modelo de mineração e os parâmetros que podem ser definidos no algoritmo:</span><span class="sxs-lookup"><span data-stu-id="9ad70-126">The next line of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm:</span></span>  
  
```  
) USING <algorithm name>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="9ad70-127">Para obter mais informações sobre os parâmetros de algoritmo que você pode ajustar, consulte [algoritmo de árvores de decisão da Microsoft](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) e algoritmo de [clustering da Microsoft](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="9ad70-127">For more information about the algorithm parameters that you can adjust, see [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) and [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span>  
  
 <span data-ttu-id="9ad70-128">Você pode especificar que uma coluna no modelo de mineração seja utilizada para previsão usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9ad70-128">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
 <span data-ttu-id="9ad70-129">A última linha do código, que é opcional, define o filtro que é aplicado para treinamento e teste do modelo.</span><span class="sxs-lookup"><span data-stu-id="9ad70-129">The final line of the code, which is optional, defines a filter that is applied when training and testing the model.</span></span> <span data-ttu-id="9ad70-130">Para obter mais informações sobre como aplicar filtros a modelos de mineração, consulte [filtros para modelos de mineração &#40;&#41;de mineração de dados de Analysis Services ](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9ad70-130">For more information about how to apply filters to mining models, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="9ad70-131">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="9ad70-131">Lesson Tasks</span></span>  
 <span data-ttu-id="9ad70-132">Você executará as seguintes tarefas nesta lição:</span><span class="sxs-lookup"><span data-stu-id="9ad70-132">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="9ad70-133">Adicionar um modelo de mineração de árvore de decisão à estrutura do Comprador de Bicicleta usando o algoritmo Árvores de Decisão da [!INCLUDE[msCoName](../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ad70-133">Add a decision tree mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm</span></span>  
  
-   <span data-ttu-id="9ad70-134">Adicionar um modelo de mineração de clustering à estrutura do Comprador de Bicicleta usando o algoritmo Clustering da [!INCLUDE[msCoName](../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ad70-134">Add a clustering mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm</span></span>  
  
-   <span data-ttu-id="9ad70-135">Como deseja ver os resultados de todos os casos, você ainda não adicionará um filtro a nenhum modelo.</span><span class="sxs-lookup"><span data-stu-id="9ad70-135">Because you want to see results for all cases, you will not yet add a filter to either model.</span></span>  
  
## <a name="adding-a-decision-tree-mining-model-to-the-structure"></a><span data-ttu-id="9ad70-136">Adicionando um modelo de mineração de árvore de decisão à estrutura</span><span class="sxs-lookup"><span data-stu-id="9ad70-136">Adding a Decision Tree Mining Model to the Structure</span></span>  
 <span data-ttu-id="9ad70-137">A primeira etapa é adicionar um modelo de mineração baseado no algoritmo Árvores de Decisão da [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ad70-137">The first step is to add a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
#### <a name="to-add-a-decision-tree-mining-model"></a><span data-ttu-id="9ad70-138">Para adicionar um modelo de mineração de árvore de decisão</span><span class="sxs-lookup"><span data-stu-id="9ad70-138">To add a decision tree mining model</span></span>  
  
1.  <span data-ttu-id="9ad70-139">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX** para abrir o editor de consultas e uma nova consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="9ad70-139">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="9ad70-140">Copie o exemplo genérico da instrução ALTER MINING STRUCTURE na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="9ad70-140">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="9ad70-141">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9ad70-141">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="9ad70-142">por:</span><span class="sxs-lookup"><span data-stu-id="9ad70-142">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="9ad70-143">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9ad70-143">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="9ad70-144">por:</span><span class="sxs-lookup"><span data-stu-id="9ad70-144">with:</span></span>  
  
    ```  
    Decision Tree  
    ```  
  
5.  <span data-ttu-id="9ad70-145">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9ad70-145">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    ```  
  
     <span data-ttu-id="9ad70-146">por:</span><span class="sxs-lookup"><span data-stu-id="9ad70-146">with:</span></span>  
  
    ```  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ```  
  
     <span data-ttu-id="9ad70-147">Nesse caso, a coluna `[Bike Buyer]` foi designada como a coluna PREDICT.</span><span class="sxs-lookup"><span data-stu-id="9ad70-147">In this case, the `[Bike Buyer]` column has been designated as the PREDICT column.</span></span>  
  
6.  <span data-ttu-id="9ad70-148">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9ad70-148">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )   
    ```  
  
     <span data-ttu-id="9ad70-149">por:</span><span class="sxs-lookup"><span data-stu-id="9ad70-149">with:</span></span>  
  
    ```  
    Using Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="9ad70-150">A instrução WITH DRILLTHROUGH permite explorar os casos que foram usados para criar o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="9ad70-150">The WITH DRILLTHROUGH statement allows you to explore the cases that were used to build the mining model.</span></span>  
  
     <span data-ttu-id="9ad70-151">A instrução resultante deverá ser agora:</span><span class="sxs-lookup"><span data-stu-id="9ad70-151">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Decision Tree]  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ) USING Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
7.  <span data-ttu-id="9ad70-152">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="9ad70-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="9ad70-153">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `DT_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="9ad70-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `DT_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="9ad70-154">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="9ad70-154">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-a-clustering-mining-model-to-the-structure"></a><span data-ttu-id="9ad70-155">Adicionando um modelo de mineração de clustering à estrutura</span><span class="sxs-lookup"><span data-stu-id="9ad70-155">Adding a Clustering Mining Model to the Structure</span></span>  
 <span data-ttu-id="9ad70-156">Agora você pode adicionar um modelo de estrutura de mineração do Comprador de Bicicleta com base no algoritmo Clustering da [!INCLUDE[msCoName](../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ad70-156">You can now add a mining model to the Bike Buyer mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span> <span data-ttu-id="9ad70-157">Como o modelo de mineração de clustering usará todas as colunas definidas na estrutura de mineração, você pode usar um atalho para adicionar o modelo à estrutura omitindo a definição das colunas de mineração.</span><span class="sxs-lookup"><span data-stu-id="9ad70-157">Because the clustering mining model will use all the columns defined in the mining structure, you can use a shortcut to add the model to the structure by omitting the definition of the mining columns.</span></span>  
  
#### <a name="to-add-a-clustering-mining-model"></a><span data-ttu-id="9ad70-158">Para adicionar um modelo de mineração de Clustering</span><span class="sxs-lookup"><span data-stu-id="9ad70-158">To add a Clustering mining model</span></span>  
  
1.  <span data-ttu-id="9ad70-159">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX** para abrir o editor de consultas abre e uma nova consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="9ad70-159">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor opens and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="9ad70-160">Copie o exemplo genérico da instrução ALTER MINING STRUCTURE na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="9ad70-160">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="9ad70-161">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9ad70-161">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="9ad70-162">por:</span><span class="sxs-lookup"><span data-stu-id="9ad70-162">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="9ad70-163">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9ad70-163">Replace the following:</span></span>  
  
    ```  
    <mining model>   
    ```  
  
     <span data-ttu-id="9ad70-164">por:</span><span class="sxs-lookup"><span data-stu-id="9ad70-164">with:</span></span>  
  
    ```  
    Clustering Model  
    ```  
  
5.  <span data-ttu-id="9ad70-165">Exclua:</span><span class="sxs-lookup"><span data-stu-id="9ad70-165">Delete the following:</span></span>  
  
    ```  
    (  
        [<key column>],  
        <mining model columns>,  
    )  
    ```  
  
6.  <span data-ttu-id="9ad70-166">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9ad70-166">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="9ad70-167">por:</span><span class="sxs-lookup"><span data-stu-id="9ad70-167">with:</span></span>  
  
    ```  
    USING Microsoft_Clustering  
    ```  
  
     <span data-ttu-id="9ad70-168">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="9ad70-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Clustering]  
    USING Microsoft_Clustering   
    ```  
  
7.  <span data-ttu-id="9ad70-169">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="9ad70-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="9ad70-170">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Clustering_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="9ad70-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Clustering_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="9ad70-171">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="9ad70-171">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="9ad70-172">Na próxima lição, você processará os modelos e a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="9ad70-172">In the next lesson, you will process the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="9ad70-173">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="9ad70-173">Next Lesson</span></span>  
 [<span data-ttu-id="9ad70-174">Lição 3: Processando a estrutura de mineração Comprador de Bicicleta</span><span class="sxs-lookup"><span data-stu-id="9ad70-174">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-bike-buyer-mining-structure.md)  
  
  
