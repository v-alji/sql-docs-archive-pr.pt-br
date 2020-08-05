---
title: 'Lição 4: navegando pelos modelos de mineração de compradores de bicicletas | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8de3c500-f881-42da-a096-b6c03300d58d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 709df371d840d4b24e420b4fcd08750fd31e8075
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572883"
---
# <a name="lesson-4-browsing-the-bike-buyer-mining-models"></a><span data-ttu-id="4dca2-102">Lição 4: Explorando modelos de mineração Comprador de Bicicleta</span><span class="sxs-lookup"><span data-stu-id="4dca2-102">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>
  <span data-ttu-id="4dca2-103">Nesta lição, você usará a instrução [Select (DMX)](/sql/dmx/select-dmx) para explorar o conteúdo na árvore de decisão e os modelos de mineração de cluster que você criou na [lição 2: adicionando modelos de mineração à estrutura de mineração preditiva](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="4dca2-103">In this lesson, you will use the [SELECT (DMX)](/sql/dmx/select-dmx) statement to explore the content in the decision tree and clustering mining models that you created in [Lesson 2: Adding Mining Models to the Predictive Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="4dca2-104">As colunas contidas em um modelo de mineração não são as colunas definidas pela estrutura de mineração. Ao contrário, constituem um conjunto específico de colunas que descrevem as tendências e os padrões encontrados pelo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="4dca2-104">The columns contained in a mining model are not the columns defined by the mining structure, but instead are a specific set of columns that describe the trends and patterns that are found by the algorithm.</span></span> <span data-ttu-id="4dca2-105">Essas colunas de modelo de mineração são descritas no conjunto de linhas de esquema [DMSCHEMA_MINING_MODEL_CONTENT conjunto de linhas](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) .</span><span class="sxs-lookup"><span data-stu-id="4dca2-105">These mining model columns are described in the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) schema rowset.</span></span> <span data-ttu-id="4dca2-106">Por exemplo, a coluna de MODEL_NAME no conjunto de linhas de esquema de conteúdo traz o nome do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="4dca2-106">For example, the MODEL_NAME column in the content schema rowset contains the name of the mining model.</span></span> <span data-ttu-id="4dca2-107">Para um modelo de mineração de clustering, a coluna de NODE_CAPTION contém o nome de cada cluster e a coluna NODE_DESCRIPTION contém a descrição das características de cada cluster.</span><span class="sxs-lookup"><span data-stu-id="4dca2-107">For a clustering mining model, the NODE_CAPTION column contains the name of each cluster, and the NODE_DESCRIPTION column contains a description of the characteristics of each cluster.</span></span> <span data-ttu-id="4dca2-108">Você pode navegar por essas colunas usando a seleção selecionar de \<model> . Demonstrativo de conteúdo no DMX.</span><span class="sxs-lookup"><span data-stu-id="4dca2-108">You can browse these columns by using the SELECT FROM \<model>.CONTENT statement in DMX.</span></span> <span data-ttu-id="4dca2-109">Também pode usar essa instrução para explorar os dados usados para criar o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="4dca2-109">You can also use this statement to explore the data that was used to create the mining model.</span></span> <span data-ttu-id="4dca2-110">O uso dessa instrução requer que as análises sejam habilitadas na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="4dca2-110">Drillthrough must be enabled on the mining structure in order to use this statement.</span></span> <span data-ttu-id="4dca2-111">Para obter mais informações sobre a instrução, consulte [selecionar do modelo de &#60;&#62;. CASOS &#40;&#41;DMX ](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="4dca2-111">For more information about the statement, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
 <span data-ttu-id="4dca2-112">Você também pode retornar todos os estados de uma coluna discreta usando a instrução SELECT DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="4dca2-112">You can also return all the states of a discrete column by using the SELECT DISTINCT statement.</span></span> <span data-ttu-id="4dca2-113">Por exemplo, se você executar esta operação na coluna gênero, a consulta retornará `male` e `female`.</span><span class="sxs-lookup"><span data-stu-id="4dca2-113">For example, if you perform this operation on a gender column, the query will return `male` and `female`.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="4dca2-114">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="4dca2-114">Lesson Tasks</span></span>  
 <span data-ttu-id="4dca2-115">Você executará as seguintes tarefas nesta lição:</span><span class="sxs-lookup"><span data-stu-id="4dca2-115">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="4dca2-116">Explore o conteúdo inserido nos modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="4dca2-116">Explore the content contained within the mining models</span></span>  
  
-   <span data-ttu-id="4dca2-117">Retorne as ocorrências dos dados de origem usadas para fazer um treinamento com os modelos de mineração</span><span class="sxs-lookup"><span data-stu-id="4dca2-117">Return the cases from the source data that was used to train the mining models</span></span>  
  
-   <span data-ttu-id="4dca2-118">Explore os diferentes estados disponíveis de uma coluna discreta específica</span><span class="sxs-lookup"><span data-stu-id="4dca2-118">Explore the different states available for a specific discrete column</span></span>  
  
## <a name="returning-the-content-of-a-mining-model"></a><span data-ttu-id="4dca2-119">Retornando o conteúdo de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="4dca2-119">Returning the Content of a Mining Model</span></span>  
 <span data-ttu-id="4dca2-120">Nesta lição, você usará a [&#62; de modelo selecionar de &#60;. CONTENT &#40;instrução&#41;DMX](/sql/dmx/select-from-model-dimension-content-dmx) para retornar o conteúdo do modelo de clustering.</span><span class="sxs-lookup"><span data-stu-id="4dca2-120">In this lesson, you use the [SELECT FROM &#60;model&#62;.CONTENT &#40;DMX&#41;](/sql/dmx/select-from-model-dimension-content-dmx) statement to return the contents of the clustering model.</span></span>  
  
 <span data-ttu-id="4dca2-121">Veja a seguir um exemplo genérico de SELECT de \<model> . Instrução de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="4dca2-121">The following is a generic example of the SELECT FROM \<model>.CONTENT statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CONTENT  
WHERE <where clause>  
```  
  
 <span data-ttu-id="4dca2-122">A primeira linha do código define que as colunas retornem do conteúdo do modelo de mineração e do modelo de mineração com as quais estão associadas:</span><span class="sxs-lookup"><span data-stu-id="4dca2-122">The first line of the code defines the columns to return from the mining model content, and the mining model they are associated with:</span></span>  
  
```  
SELECT <select list> FROM [<mining model].CONTENT  
```  
  
 <span data-ttu-id="4dca2-123">A cláusula .CONTENT, próxima ao nome do modelo de mineração, determina que você está retornando conteúdo do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="4dca2-123">The .CONTENT clause next to the name of the mining model specifies that you are returning content from the mining model.</span></span> <span data-ttu-id="4dca2-124">Para obter mais informações sobre as colunas contidas no modelo de mineração, consulte [DMSCHEMA_MINING_MODEL_CONTENT conjunto de linhas](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="4dca2-124">For more information about the columns contained in the mining model, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
 <span data-ttu-id="4dca2-125">Você pode optar por usar a linha final do código para filtrar os resultados retornados pela instrução:</span><span class="sxs-lookup"><span data-stu-id="4dca2-125">You can optionally use the final line of the code to filter the results returned by the statement:</span></span>  
  
```  
WHERE <where clause>  
```  
  
 <span data-ttu-id="4dca2-126">Por exemplo, se você quiser restringir os resultados da consulta apenas aos clusters que contêm um número elevado de ocorrências, você poderá adicionar a cláusula WHERE à instrução SELECT:</span><span class="sxs-lookup"><span data-stu-id="4dca2-126">For example, if you want to restrict the results of the query to only the clusters that contain a high number of cases, you can add the following WHERE clause to the SELECT statement:</span></span>  
  
```  
WHERE NODE_SUPPORT > 100  
```  
  
 <span data-ttu-id="4dca2-127">Para obter mais informações sobre como usar a instrução WHERE, consulte [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="4dca2-127">For more information about using the WHERE statement, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-content-of-the-clustering-mining-model"></a><span data-ttu-id="4dca2-128">Para retornar o conteúdo do modelo de mineração de clustering</span><span class="sxs-lookup"><span data-stu-id="4dca2-128">To return the content of the clustering mining model</span></span>  
  
1.  <span data-ttu-id="4dca2-129">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="4dca2-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="4dca2-130">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="4dca2-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="4dca2-131">Copie o exemplo genérico de SELECT de \<model> . Instrução de conteúdo na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="4dca2-131">Copy the generic example of the SELECT FROM \<model>.CONTENT statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="4dca2-132">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4dca2-132">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="4dca2-133">por:</span><span class="sxs-lookup"><span data-stu-id="4dca2-133">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="4dca2-134">Você também pode substituir \* por uma lista de qualquer uma das colunas contidas no [conjunto de linhas DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="4dca2-134">You can also replace \* with a list of any of the columns contained within the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
4.  <span data-ttu-id="4dca2-135">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4dca2-135">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="4dca2-136">por:</span><span class="sxs-lookup"><span data-stu-id="4dca2-136">with:</span></span>  
  
    ```  
    [Clustering]  
    ```  
  
     <span data-ttu-id="4dca2-137">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="4dca2-137">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT * FROM [Clustering].CONTENT  
    ```  
  
5.  <span data-ttu-id="4dca2-138">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="4dca2-138">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="4dca2-139">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `SELECT_CONTENT.dmx` .</span><span class="sxs-lookup"><span data-stu-id="4dca2-139">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_CONTENT.dmx`.</span></span>  
  
7.  <span data-ttu-id="4dca2-140">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="4dca2-140">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="4dca2-141">A consulta retorna o conteúdo de um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="4dca2-141">The query returns the content of the mining model.</span></span>  
  
## <a name="use-drillthrough"></a><span data-ttu-id="4dca2-142">Use a análise</span><span class="sxs-lookup"><span data-stu-id="4dca2-142">Use Drillthrough</span></span>  
 <span data-ttu-id="4dca2-143">O próximo passo é usar a instrução de análise para retornar uma amostragem dos casos usados para treinar o modelo de mineração de árvore de decisão.</span><span class="sxs-lookup"><span data-stu-id="4dca2-143">The next step is to use the drillthrough statement to return a sampling of the cases that were used to train the decision tree mining model.</span></span> <span data-ttu-id="4dca2-144">Nesta lição, você usará a [&#62; de modelo selecionar de &#60;. CASOS &#40;instrução&#41;DMX](/sql/dmx/select-from-model-content-dmx) para retornar o conteúdo do modelo de árvore de decisão.</span><span class="sxs-lookup"><span data-stu-id="4dca2-144">In this lesson, you use the [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) statement to return the contents of the decision tree model.</span></span>  
  
 <span data-ttu-id="4dca2-145">Veja a seguir um exemplo genérico de SELECT de \<model> . Instrução CASEs:</span><span class="sxs-lookup"><span data-stu-id="4dca2-145">The following is a generic example of the SELECT FROM \<model>.CASES statement:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model>].CASES  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="4dca2-146">A primeira linha do código define que as colunas retornem dos dados de origem, e do modelo de mineração a que pertencem:</span><span class="sxs-lookup"><span data-stu-id="4dca2-146">The first line of the code defines the columns to return from the source data, and the mining model they are contained within:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CASES  
```  
  
 <span data-ttu-id="4dca2-147">A cláusula .CASES especifica que você está executando uma consulta para análise.</span><span class="sxs-lookup"><span data-stu-id="4dca2-147">The .CASES clause specifies that you are performing a drillthrough query.</span></span> <span data-ttu-id="4dca2-148">Para usar o detalhamento, você deve habilitá-lo durante a criação do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="4dca2-148">In order to use drillthrough you must enable drillthrough when you create the mining model.</span></span>  
  
 <span data-ttu-id="4dca2-149">A linha final do código é opcional e especifica o nó no modelo de mineração do qual você está solicitando os casos:</span><span class="sxs-lookup"><span data-stu-id="4dca2-149">The final line of the code is optional and specifies the node in the mining model that you are requesting cases from:</span></span>  
  
```  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="4dca2-150">Para obter mais informações sobre como usar a instrução WHERE com IsInNode, consulte [selecionar do modelo de &#60;&#62;. CASOS &#40;&#41;DMX ](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="4dca2-150">For more information about using the WHERE statement with IsInNode, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
#### <a name="to-return-the-cases-that-were-used-to-train-the-mining-model"></a><span data-ttu-id="4dca2-151">Para retornar os casos usados para treinar o modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="4dca2-151">To return the cases that were used to train the mining model</span></span>  
  
1.  <span data-ttu-id="4dca2-152">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="4dca2-152">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="4dca2-153">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="4dca2-153">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="4dca2-154">Copie o exemplo genérico de SELECT de \<model> . Instrução CASEs na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="4dca2-154">Copy the generic example of the SELECT FROM \<model>.CASES statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="4dca2-155">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4dca2-155">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="4dca2-156">por:</span><span class="sxs-lookup"><span data-stu-id="4dca2-156">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="4dca2-157">Você também pode substituir \* por qualquer lista de colunas presente nos dados de origem (como [Comprador de Bicicleta]).</span><span class="sxs-lookup"><span data-stu-id="4dca2-157">You can also replace \* with a list of any of the columns contained within the source data (such as [Bike Buyer]).</span></span>  
  
4.  <span data-ttu-id="4dca2-158">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4dca2-158">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="4dca2-159">por:</span><span class="sxs-lookup"><span data-stu-id="4dca2-159">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="4dca2-160">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="4dca2-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT *   
    FROM [Decision Tree].CASES  
    ```  
  
5.  <span data-ttu-id="4dca2-161">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="4dca2-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="4dca2-162">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `SELECT_DRILLTHROUGH.dmx` .</span><span class="sxs-lookup"><span data-stu-id="4dca2-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DRILLTHROUGH.dmx`.</span></span>  
  
7.  <span data-ttu-id="4dca2-163">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="4dca2-163">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="4dca2-164">A consulta retorna os dados de origem que foram usados para treinar os modelos de mineração da árvore de decisão.</span><span class="sxs-lookup"><span data-stu-id="4dca2-164">The query returns the source data that was used to train the decision tree mining model.</span></span>  
  
## <a name="return-the-states-of-a-discrete-mining-model-column"></a><span data-ttu-id="4dca2-165">Retorne os estados de uma coluna discreta do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="4dca2-165">Return the States of a Discrete Mining Model Column</span></span>  
 <span data-ttu-id="4dca2-166">O próximo passo é usar a instrução SELECT DISTINCT para retornar possíveis estados diferentes na coluna de modelo de mineração especificada.</span><span class="sxs-lookup"><span data-stu-id="4dca2-166">The next step is to use the SELECT DISTINCT statement to return the different possible states in the specified mining model column.</span></span>  
  
 <span data-ttu-id="4dca2-167">Segue um exemplo genérico da instrução SELECT DISTINCT:</span><span class="sxs-lookup"><span data-stu-id="4dca2-167">The following is a generic example of the SELECT DISTINCT statement:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
FROM [<mining model>]  
```  
  
 <span data-ttu-id="4dca2-168">A primeira linha do código define as colunas do modelo de mineração para as quais os estados retornam:</span><span class="sxs-lookup"><span data-stu-id="4dca2-168">The first line of the code defines the mining model columns for which the states are returned:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
```  
  
 <span data-ttu-id="4dca2-169">Você deve incluir DISTINCT para retornar todos os estados da coluna.</span><span class="sxs-lookup"><span data-stu-id="4dca2-169">You must include DISTINCT in order to return all of the states of the column.</span></span> <span data-ttu-id="4dca2-170">Se você excluir DISTINCT, então a instrução toda se tornará um atalho para uma previsão e retornará o estado mais provável da coluna especificada.</span><span class="sxs-lookup"><span data-stu-id="4dca2-170">If you exclude DISTINCT, then the full statement becomes a shortcut for a prediction and returns the most likely state of the specified column.</span></span> <span data-ttu-id="4dca2-171">Para obter mais informações, consulte [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="4dca2-171">For more information, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-states-of-a-discrete-column"></a><span data-ttu-id="4dca2-172">Para retornar os estados de uma coluna discreta</span><span class="sxs-lookup"><span data-stu-id="4dca2-172">To return the states of a discrete column</span></span>  
  
1.  <span data-ttu-id="4dca2-173">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="4dca2-173">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="4dca2-174">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="4dca2-174">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="4dca2-175">Copie o exemplo genérico da instrução SELECT Distinct, no campo em branco da consulta.</span><span class="sxs-lookup"><span data-stu-id="4dca2-175">Copy the generic example of the SELECT Distinct statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="4dca2-176">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4dca2-176">Replace the following:</span></span>  
  
    ```  
    [<column,name>   
    ```  
  
     <span data-ttu-id="4dca2-177">por:</span><span class="sxs-lookup"><span data-stu-id="4dca2-177">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="4dca2-178">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4dca2-178">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="4dca2-179">por:</span><span class="sxs-lookup"><span data-stu-id="4dca2-179">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="4dca2-180">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="4dca2-180">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT DISTINCT [Bike Buyer]   
    FROM [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="4dca2-181">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="4dca2-181">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="4dca2-182">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `SELECT_DISCRETE.dmx` .</span><span class="sxs-lookup"><span data-stu-id="4dca2-182">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DISCRETE.dmx`.</span></span>  
  
7.  <span data-ttu-id="4dca2-183">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="4dca2-183">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="4dca2-184">A consulta retorna os estados possíveis da coluna Comprador de Bicicleta.</span><span class="sxs-lookup"><span data-stu-id="4dca2-184">The query returns the possible states of the Bike Buyer column.</span></span>  
  
 <span data-ttu-id="4dca2-185">Na próxima lição, você poderá prever se os clientes potenciais serão os compradores de bicicleta usando o modelo de mineração da árvore de decisão.</span><span class="sxs-lookup"><span data-stu-id="4dca2-185">In the next lesson, you will predict whether potential customers will be bike buyers by using the decision tree mining model.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="4dca2-186">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="4dca2-186">Next Lesson</span></span>  
 [<span data-ttu-id="4dca2-187">Lição 5: Executando previsão de consultas</span><span class="sxs-lookup"><span data-stu-id="4dca2-187">Lesson 5: Executing Prediction Queries</span></span>](../../2014/tutorials/lesson-5-executing-prediction-queries.md)  
  
  
