---
title: 'Lição 2: adicionando modelos de mineração à estrutura de mineração da cesta de mercado | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d96a7a7d-35d7-4b34-abb5-f0822c256253
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b9573d9359983e33cf23533787c26039572710ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681303"
---
# <a name="lesson-2-adding-mining-models-to-the-market-basket-mining-structure"></a><span data-ttu-id="6de1e-102">Lição 2: Adicionando modelos de mineração à estrutura de mineração do Market Basket </span><span class="sxs-lookup"><span data-stu-id="6de1e-102">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>
  <span data-ttu-id="6de1e-103">Nesta lição, você adicionará dois modelos de mineração à estrutura de mineração de cesta de mercado criada na [lição 1: criando a estrutura de mineração de cesta de compras](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="6de1e-103">In this lesson, you will add two mining models to the Market Basket mining structure that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="6de1e-104">Estes modelos de mineração permitirão criar previsões.</span><span class="sxs-lookup"><span data-stu-id="6de1e-104">These mining models will allow you to create predictions.</span></span>  
  
 <span data-ttu-id="6de1e-105">Para prever os tipos de produtos que os clientes tendem a comprar ao mesmo tempo, você criará dois modelos de mineração usando o [algoritmo de associação da Microsoft](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) e dois valores diferentes para o parâmetro *MINIMUM_PROBABILTY* .</span><span class="sxs-lookup"><span data-stu-id="6de1e-105">To predict the types of products that customers tend to purchase at the same time, you will create two mining models using the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) and two different values for the *MINIMUM_PROBABILTY* parameter.</span></span>  
  
 <span data-ttu-id="6de1e-106">*MINIMUM_PROBABILTY* é um [!INCLUDE[msCoName](../includes/msconame-md.md)] parâmetro de algoritmo de associação que ajuda a determinar o número de regras que um modelo de mineração conterá, especificando a probabilidade mínima que uma regra deve ter.</span><span class="sxs-lookup"><span data-stu-id="6de1e-106">*MINIMUM_PROBABILTY* is a [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm parameter that helps to determine the number of rules that a mining model will contain by specifying the minimum probability that a rule must have.</span></span> <span data-ttu-id="6de1e-107">Por exemplo, definindo-se esse valor como 0,4, uma regra é especificada, a qual só poderá ser gerada se a combinação de produtos que a regra descreve tiver, pelo menos, 40% de probabilidade de ocorrência.</span><span class="sxs-lookup"><span data-stu-id="6de1e-107">For example, setting this value to 0.4 specifies that a rule can be generated only if the combination of products that the rule describes has at least a forty percent probability of occurring.</span></span>  
  
 <span data-ttu-id="6de1e-108">Você exibirá o efeito de alterar o parâmetro *MINIMUM_PROBABILTY* em uma lição posterior.</span><span class="sxs-lookup"><span data-stu-id="6de1e-108">You will view the effect of changing the *MINIMUM_PROBABILTY* parameter in a later lesson.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="6de1e-109">Instrução ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="6de1e-109">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="6de1e-110">Para adicionar um modelo de mineração que contém uma tabela aninhada a uma estrutura de mineração, use a instrução [ALTER MINING structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="6de1e-110">To add a mining model that contains a nested table to a mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="6de1e-111">O código na instrução pode ser dividido nas seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="6de1e-111">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="6de1e-112">Identificando a estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="6de1e-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="6de1e-113">Nomeando o modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="6de1e-113">Naming the mining model</span></span>  
  
-   <span data-ttu-id="6de1e-114">Definindo a coluna de chave</span><span class="sxs-lookup"><span data-stu-id="6de1e-114">Defining the key column</span></span>  
  
-   <span data-ttu-id="6de1e-115">Definindo as colunas de entrada e as previsíveis</span><span class="sxs-lookup"><span data-stu-id="6de1e-115">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="6de1e-116">Definindo as colunas de tabelas aninhadas</span><span class="sxs-lookup"><span data-stu-id="6de1e-116">Defining the nested table columns</span></span>  
  
-   <span data-ttu-id="6de1e-117">Identificando as alterações de algoritmo e de parâmetro</span><span class="sxs-lookup"><span data-stu-id="6de1e-117">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="6de1e-118">A seguir, está um exemplo genérico da instrução `ALTER MINING STRUCTURE` que adiciona um modelo de mineração a uma estrutura que inclui colunas de tabelas aninhadas:</span><span class="sxs-lookup"><span data-stu-id="6de1e-118">The following is a generic example of the `ALTER MINING STRUCTURE` statement that adds a mining model to a structure that includes nested table columns:</span></span>  
  
```  
ALTER MINING STRUCTURE [<Mining Structure Name>]  
ADD MINING MODEL [<Mining Model Name>]  
(  
    [<key column>],  
    <mining model column> <usage>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
) USING <algorithm>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="6de1e-119">A primeira linha do código identifica a estrutura de mineração existente à qual o modelo de mineração será adicionada:</span><span class="sxs-lookup"><span data-stu-id="6de1e-119">The first line of the code identifies the existing mining structure to which the mining model will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="6de1e-120">A linha seguinte do código nomeia o modelo de mineração que será adicionado à estrutura de mineração:</span><span class="sxs-lookup"><span data-stu-id="6de1e-120">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="6de1e-121">Para obter informações sobre como nomear um objeto em DMX (extensões de mineração de dados), consulte [identificadores &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="6de1e-121">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="6de1e-122">As linhas seguintes do código definem as colunas da estrutura de mineração que será usada pelo modelo de mineração:</span><span class="sxs-lookup"><span data-stu-id="6de1e-122">The next lines of the code define the columns in the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns> <usage>,  
```  
  
 <span data-ttu-id="6de1e-123">Você só pode usar colunas que já existam na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="6de1e-123">You can only use columns that already exist in the mining structure.</span></span>  
  
 <span data-ttu-id="6de1e-124">A primeira coluna na lista de colunas do modelo de mineração deve ser a coluna de chave na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="6de1e-124">The first column in the list of mining model columns must be the key column in the mining structure.</span></span> <span data-ttu-id="6de1e-125">No entanto, você não precisa digitar `KEY` após a coluna de chave para especificar o uso.</span><span class="sxs-lookup"><span data-stu-id="6de1e-125">However, you do not have to type `KEY` after the key column to specify usage.</span></span> <span data-ttu-id="6de1e-126">Isso é porque você já definiu a coluna como uma chave quando criou a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="6de1e-126">That is because you have already defined the column as a key when you created the mining structure.</span></span>  
  
 <span data-ttu-id="6de1e-127">As linhas restantes especificam o uso das colunas no novo modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="6de1e-127">The remaining lines specify the usage of the columns in the new mining model.</span></span> <span data-ttu-id="6de1e-128">Você pode especificar que uma coluna no modelo de mineração será utilizada para previsão usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="6de1e-128">You can specify that a column in the mining model will be used for prediction by using the following syntax:</span></span>  
  
```  
<column name> PREDICT,  
```  
  
 <span data-ttu-id="6de1e-129">Se você não especificar o uso, não terá que incluir uma coluna de estrutura de mineração de dados na lista.</span><span class="sxs-lookup"><span data-stu-id="6de1e-129">If you do not specify usage, you do not have to include a data mining structure column in the list.</span></span> <span data-ttu-id="6de1e-130">Todas as colunas usadas pela estrutura de mineração de dados referenciada estão automaticamente disponíveis para uso pelos modelos de mineração que se baseiam nessa estrutura.</span><span class="sxs-lookup"><span data-stu-id="6de1e-130">All columns that are used by the referenced data mining structure are automatically available for use by the mining models that are based on that structure.</span></span> <span data-ttu-id="6de1e-131">Porém, o modelo não usará as colunas para treinamento, a menos que você especifique o uso.</span><span class="sxs-lookup"><span data-stu-id="6de1e-131">However, the model will not use the columns for training unless you specify the usage.</span></span>  
  
 <span data-ttu-id="6de1e-132">A última linha do código define o algoritmo e os parâmetros de algoritmo que serão usados para gerar o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="6de1e-132">The last line in the code defines the algorithm and algorithm parameters that will be used to generate the mining model.</span></span>  
  
```  
) USING <algorithm>( <algorithm parameters> )  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="6de1e-133">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="6de1e-133">Lesson Tasks</span></span>  
 <span data-ttu-id="6de1e-134">Você executará as seguintes tarefas nesta lição:</span><span class="sxs-lookup"><span data-stu-id="6de1e-134">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="6de1e-135">Adicione um modelo de mineração de associação à estrutura, usando a probabilidade padrão</span><span class="sxs-lookup"><span data-stu-id="6de1e-135">Add an association mining model to the structure using the default probability</span></span>  
  
-   <span data-ttu-id="6de1e-136">Adicione um modelo de mineração de associação à estrutura, usando uma probabilidade modificada</span><span class="sxs-lookup"><span data-stu-id="6de1e-136">Add an association mining model to the structure using a modified probability</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-using-the-default-minimum_probability"></a><span data-ttu-id="6de1e-137">Acrescentando um Modelo de Mineração de Associação à estrutura usando MINIMUM_PROBABILITY padrão</span><span class="sxs-lookup"><span data-stu-id="6de1e-137">Adding an Association Mining Model to the Structure Using the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="6de1e-138">A primeira tarefa é adicionar um novo modelo de mineração à estrutura de mineração de cesta de mercado com base no [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo de associação usando o valor padrão para *MINIMUM_PROBABILITY*.</span><span class="sxs-lookup"><span data-stu-id="6de1e-138">The first task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm using the default value for *MINIMUM_PROBABILITY*.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="6de1e-139">Para adicionar um modelo de mineração de Associação</span><span class="sxs-lookup"><span data-stu-id="6de1e-139">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="6de1e-140">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="6de1e-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="6de1e-141">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="6de1e-141">Query Editor opens and contains a new, blank query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6de1e-142">Para criar uma consulta DMX para um banco de dados [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] específico, clique com o botão direito do mouse no banco de dados em vez da instância.</span><span class="sxs-lookup"><span data-stu-id="6de1e-142">To create a DMX query against a specific [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, right-click the database instead of the instance.</span></span>  
  
2.  <span data-ttu-id="6de1e-143">Copie o exemplo genérico da instrução `ALTER MINING STRUCTURE` na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="6de1e-143">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="6de1e-144">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6de1e-144">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="6de1e-145">por:</span><span class="sxs-lookup"><span data-stu-id="6de1e-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
4.  <span data-ttu-id="6de1e-146">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6de1e-146">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="6de1e-147">por:</span><span class="sxs-lookup"><span data-stu-id="6de1e-147">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="6de1e-148">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6de1e-148">Replace the following:</span></span>  
  
    ```  
    [<key column>],  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="6de1e-149">por:</span><span class="sxs-lookup"><span data-stu-id="6de1e-149">with:</span></span>  
  
    ```  
    OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="6de1e-150">Nesse caso, a tabela `[Products]` foi designada como a coluna previsível`.` Além disso, a coluna `[Model]` é incluída na lista de colunas de tabelas aninhadas, porque ela é a coluna de chave da tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="6de1e-150">In this case, the `[Products]` table has been designated as the predictable column`.` Also, the `[Model]` column is included in the list of nested table columns because it is the key column of the nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6de1e-151">Lembre-se de que uma chave aninhada é diferente de uma chave de caso.</span><span class="sxs-lookup"><span data-stu-id="6de1e-151">Remember that a nested key is different from a case key.</span></span> <span data-ttu-id="6de1e-152">Uma chave de caso é um identificador exclusivo do caso, enquanto a chave aninhada é um atributo que você quer modelar.</span><span class="sxs-lookup"><span data-stu-id="6de1e-152">A case key is a unique identifier of the case, whereas the nested key is an attribute that you want to model.</span></span>  
  
6.  <span data-ttu-id="6de1e-153">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6de1e-153">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="6de1e-154">por:</span><span class="sxs-lookup"><span data-stu-id="6de1e-154">with:</span></span>  
  
    ```  
    Using Microsoft_Association_Rules  
    ```  
  
     <span data-ttu-id="6de1e-155">A instrução resultante deverá ser agora:</span><span class="sxs-lookup"><span data-stu-id="6de1e-155">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Default Association]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    Using Microsoft_Association_Rules  
    ```  
  
7.  <span data-ttu-id="6de1e-156">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="6de1e-156">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="6de1e-157">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Default_Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="6de1e-157">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Default_Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="6de1e-158">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="6de1e-158">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-changing-the-default-minimum_probability"></a><span data-ttu-id="6de1e-159">Acrescentando um Modelo de Mineração de Associação à estrutura alterando MINIMUM_PROBABILITY padrão</span><span class="sxs-lookup"><span data-stu-id="6de1e-159">Adding an Association Mining Model to the Structure Changing the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="6de1e-160">A próxima tarefa é adicionar um novo modelo de mineração à estrutura de mineração da cesta de compras, com base no algoritmo Associação da [!INCLUDE[msCoName](../includes/msconame-md.md)] e alterar o valor padrão de MINIMUM_PROBABILITY para 0,01.</span><span class="sxs-lookup"><span data-stu-id="6de1e-160">The next task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm, and change the default value for MINIMUM_PROBABILITY to 0.01.</span></span> <span data-ttu-id="6de1e-161">A alteração do parâmetro fará com que o algoritmo de Associação [!INCLUDE[msCoName](../includes/msconame-md.md)] crie mais regras.</span><span class="sxs-lookup"><span data-stu-id="6de1e-161">Changing the parameter will cause the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm to create more rules.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="6de1e-162">Para adicionar um modelo de mineração de Associação</span><span class="sxs-lookup"><span data-stu-id="6de1e-162">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="6de1e-163">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="6de1e-163">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="6de1e-164">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="6de1e-164">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="6de1e-165">Copie o exemplo genérico da instrução `ALTER MINING STRUCTURE` na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="6de1e-165">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="6de1e-166">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6de1e-166">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="6de1e-167">por:</span><span class="sxs-lookup"><span data-stu-id="6de1e-167">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="6de1e-168">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6de1e-168">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="6de1e-169">por:</span><span class="sxs-lookup"><span data-stu-id="6de1e-169">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="6de1e-170">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6de1e-170">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="6de1e-171">por:</span><span class="sxs-lookup"><span data-stu-id="6de1e-171">with:</span></span>  
  
    ```  
    OrderNumber,  
    [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="6de1e-172">Neste caso, a tabela `[Products]` foi designada como a coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="6de1e-172">In this case, the `[Products]` table has been designated as the predictable column.</span></span> <span data-ttu-id="6de1e-173">Também, a coluna `[MODEL]` é incluída na lista, porque é a coluna de chave na tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="6de1e-173">Also, the `[MODEL]` column is included in the list because it is the key column in the nested table.</span></span>  
  
6.  <span data-ttu-id="6de1e-174">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6de1e-174">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="6de1e-175">por:</span><span class="sxs-lookup"><span data-stu-id="6de1e-175">with:</span></span>  
  
    ```  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
     <span data-ttu-id="6de1e-176">A instrução resultante deverá ser agora:</span><span class="sxs-lookup"><span data-stu-id="6de1e-176">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Modified Assocation]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
7.  <span data-ttu-id="6de1e-177">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="6de1e-177">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="6de1e-178">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Modified Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="6de1e-178">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="6de1e-179">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="6de1e-179">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="6de1e-180">Nesta próxima lição você processará a estrutura de mineração da cesta básica junto com seus modelos de mineração associados.</span><span class="sxs-lookup"><span data-stu-id="6de1e-180">In this next lesson you will process the Market Basket mining structure together with its associated mining models.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="6de1e-181">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="6de1e-181">Next Lesson</span></span>  
 [<span data-ttu-id="6de1e-182">Lição 3: Processando a estrutura de mineração do Market Basket</span><span class="sxs-lookup"><span data-stu-id="6de1e-182">Lesson 3: Processing the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-market-basket-mining-structure.md)  
  
  
