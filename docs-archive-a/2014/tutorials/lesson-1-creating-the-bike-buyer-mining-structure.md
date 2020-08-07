---
title: 'Lição 1: criando a estrutura de mineração de compradores de bicicletas | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a73ac60b-660f-458a-bd2f-993fbeba7226
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d6384910858d87a80aa3c8f897bc88e45f4504fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681969"
---
# <a name="lesson-1-creating-the-bike-buyer-mining-structure"></a><span data-ttu-id="cbf9d-102">Lição 1: Criando a estrutura de mineração de Comprador de Bicicleta</span><span class="sxs-lookup"><span data-stu-id="cbf9d-102">Lesson 1: Creating the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="cbf9d-103">Nesta lição, você criará uma estrutura de mineração que permite prever se um cliente potencial da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] irá adquirir uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-103">In this lesson, you will create a mining structure that allows you to predict whether a potential customer of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] will purchase a bicycle.</span></span> <span data-ttu-id="cbf9d-104">Se você não estiver familiarizado com as estruturas de mineração e sua função no Data Mining, consulte [estruturas de mineração &#40;Analysis Services-&#41;de mineração de dados ](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="cbf9d-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="cbf9d-105">A estrutura de mineração de compradores de bicicletas que você criará nesta lição dá suporte à adição de modelos de mineração com base no algoritmo [Microsoft Clustering](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)de[árvores de decisão da Microsoft](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="cbf9d-105">The Bike Buyer mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)[Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="cbf9d-106">Em lições posteriores, você usará os modelos de mineração de clustering para explorar as várias maneiras nas quais os clientes podem ser agrupados e usará os modelos de mineração da árvore de decisão para prever se um cliente potencial comprará ou não uma bicicleta.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-106">In later lessons, you will use the clustering mining models to explore the different ways in which customers can be grouped, and will use decision tree mining models to predict whether or not a potential customer will purchase a bicycle.</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="cbf9d-107">Instrução CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="cbf9d-107">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="cbf9d-108">Para criar uma estrutura de mineração, use a instrução [criar estrutura de mineração &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="cbf9d-108">To create a mining structure, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="cbf9d-109">O código na instrução pode ser dividido nas seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="cbf9d-110">Nomeando a estrutura.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-110">Naming the structure.</span></span>  
  
-   <span data-ttu-id="cbf9d-111">Definindo a coluna de chave.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-111">Defining the key column.</span></span>  
  
-   <span data-ttu-id="cbf9d-112">Definindo as colunas de mineração.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-112">Defining the mining columns.</span></span>  
  
-   <span data-ttu-id="cbf9d-113">Definindo um conjunto de dados de teste opcional.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-113">Defining an optional testing data set.</span></span>  
  
 <span data-ttu-id="cbf9d-114">A seguir, veja um exemplo genérico da instrução CREATE MINING STRUCTURE:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-114">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
(  
    <key column>,  
    <mining structure columns>  
)   
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="cbf9d-115">A primeira linha do código define o nome da estrutura:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-115">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="cbf9d-116">Para obter informações sobre como nomear um objeto em DMX (extensões de mineração de dados), consulte [identificadores &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="cbf9d-116">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="cbf9d-117">A próxima linha do código define a coluna de chave da estrutura de mineração, que identifica exclusivamente uma entidade nos dados de origem:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-117">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>,  
```  
  
 <span data-ttu-id="cbf9d-118">Na estrutura de mineração que você criará, o identificador do cliente, `CustomerKey`, define uma entidade nos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-118">In the mining structure you will create, the customer identifier, `CustomerKey`, defines an entity in the source data.</span></span>  
  
 <span data-ttu-id="cbf9d-119">A próxima linha do código define as colunas de mineração que serão usadas pelos modelos de mineração associados à estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-119">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="cbf9d-120">Você pode usar a função DISCRETIZAR no \<mining structure columns> para discretizar colunas contínuas usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-120">You can use the DISCRETIZE function within \<mining structure columns> to discretize continuous columns by using the following syntax:</span></span>  
  
 `DISCRETIZE(<method>,<number of buckets>)`  
  
 <span data-ttu-id="cbf9d-121">Para obter mais informações sobre colunas discretização, consulte [métodos de discretização &#40;mineração de dados&#41;](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="cbf9d-121">For more information about discretizing columns, see [Discretization Methods &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span></span> <span data-ttu-id="cbf9d-122">Para obter mais informações sobre os tipos de colunas de estrutura de mineração que você pode definir, consulte [colunas da estrutura de mineração](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="cbf9d-122">For more information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
 <span data-ttu-id="cbf9d-123">A última linha do código define uma partição opcional na estrutura de mineração:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-123">The final line of the code defines an optional partition in the mining structure:</span></span>  
  
```  
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="cbf9d-124">Você especifica parte dos dados a serem usados no teste dos modelos de mineração relacionados com a estrutura, e os demais dados serão usados para treinamento dos modelos.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-124">You specify some portion of the data to use for testing mining models that are related to the structure, and the remaining data is used for training the models.</span></span> <span data-ttu-id="cbf9d-125">Por padrão, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cria um conjunto de dados de teste que contém 30% de todos os dados dos casos.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-125">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates a test data set that contains 30 percent of all case data.</span></span> <span data-ttu-id="cbf9d-126">Você adicionará a especificação de que o conjunto de dados de teste deve conter 30% dos casos até o máximo de 1000 casos.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-126">You will add the specification that the test data set should contain 30 percent of the cases up to a maximum of 1000 cases.</span></span> <span data-ttu-id="cbf9d-127">Se 30% dos casos for inferior a 1000, o conjunto de dados de teste terá uma quantidade menor.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-127">If 30 percent of the cases is less than 1000, the test data set will contain the smaller amount.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="cbf9d-128">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="cbf9d-128">Lesson Tasks</span></span>  
 <span data-ttu-id="cbf9d-129">Você executará as seguintes tarefas nesta lição:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-129">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="cbf9d-130">Criar uma nova consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-130">Create a new blank query.</span></span>  
  
-   <span data-ttu-id="cbf9d-131">Alterar a consulta para criar a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-131">Alter the query to create the mining structure.</span></span>  
  
-   <span data-ttu-id="cbf9d-132">Executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-132">Execute the query.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="cbf9d-133">Criando a consulta</span><span class="sxs-lookup"><span data-stu-id="cbf9d-133">Creating the Query</span></span>  
 <span data-ttu-id="cbf9d-134">A primeira etapa é se conectar a uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e criar uma nova consulta DMX no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbf9d-134">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="cbf9d-135">Para criar uma nova consulta DMX no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cbf9d-135">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="cbf9d-136">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbf9d-136">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="cbf9d-137">Na caixa de diálogo **conectar ao servidor** , para **tipo de servidor**, selecione **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-137">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="cbf9d-138">Em **nome do servidor**, digite `LocalHost` ou digite o nome da instância do à qual [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] você deseja se conectar para esta lição.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-138">In **Server name**, type `LocalHost`, or type the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="cbf9d-139">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-139">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="cbf9d-140">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX** para abrir o **Editor de consultas** e uma nova consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the **Query Editor** and a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="cbf9d-141">Alterando a consulta</span><span class="sxs-lookup"><span data-stu-id="cbf9d-141">Altering the Query</span></span>  
 <span data-ttu-id="cbf9d-142">A próxima etapa é modificar a instrução CREATE MINING STRUCTURE descrita acima para criar a estrutura de mineração de Comprador de Bicicleta.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-142">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Bike Buyer mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="cbf9d-143">Para personalizar a instrução CREATE MINING STRUCTURE.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-143">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="cbf9d-144">No Editor de Consultas, copie o exemplo genérico da instrução CREATE MINING STRUCTURE na consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-144">In the Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="cbf9d-145">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-145">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]   
    ```  
  
     <span data-ttu-id="cbf9d-146">por:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-146">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
3.  <span data-ttu-id="cbf9d-147">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-147">Replace the following:</span></span>  
  
    ```  
    <key column>   
    ```  
  
     <span data-ttu-id="cbf9d-148">por:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-148">with:</span></span>  
  
    ```  
    CustomerKey LONG KEY  
    ```  
  
4.  <span data-ttu-id="cbf9d-149">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-149">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>   
    ```  
  
     <span data-ttu-id="cbf9d-150">por:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-150">with:</span></span>  
  
    ```  
    [Age] LONG DISCRETIZED(Automatic,10),  
    [Bike Buyer] LONG DISCRETE,  
    [Commute Distance] TEXT DISCRETE,  
    [Education] TEXT DISCRETE,  
    [Gender] TEXT DISCRETE,  
    [House Owner Flag] TEXT DISCRETE,  
    [Marital Status] TEXT DISCRETE,  
    [Number Cars Owned] LONG DISCRETE,  
    [Number Children At Home] LONG DISCRETE,  
    [Occupation] TEXT DISCRETE,  
    [Region] TEXT DISCRETE,  
    [Total Children]LONG DISCRETE,  
    [Yearly Income] DOUBLE CONTINUOUS  
    ```  
  
5.  <span data-ttu-id="cbf9d-151">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-151">Replace the following:</span></span>  
  
    ```  
    WITH HOLDOUT (holdout specifier>)  
    ```  
  
     <span data-ttu-id="cbf9d-152">por:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-152">with:</span></span>  
  
    ```  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
    ```  
  
     <span data-ttu-id="cbf9d-153">A instrução completa da estrutura de mineração agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-153">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key] LONG KEY,  
       [Age]LONG DISCRETIZED(Automatic,10),  
       [Bike Buyer] LONG DISCRETE,  
       [Commute Distance] TEXT DISCRETE,  
       [Education] TEXT DISCRETE,  
       [Gender] TEXT DISCRETE,  
       [House Owner Flag] TEXT DISCRETE,  
       [Marital Status] TEXT DISCRETE,  
       [Number Cars Owned]LONG DISCRETE,  
       [Number Children At Home]LONG DISCRETE,  
       [Occupation] TEXT DISCRETE,  
       [Region] TEXT DISCRETE,  
       [Total Children]LONG DISCRETE,  
       [Yearly Income] DOUBLE CONTINUOUS  
    )  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
  
    ```  
  
6.  <span data-ttu-id="cbf9d-154">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-154">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="cbf9d-155">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="cbf9d-155">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Bike Buyer Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="cbf9d-156">Executando a consulta</span><span class="sxs-lookup"><span data-stu-id="cbf9d-156">Executing the Query</span></span>  
 <span data-ttu-id="cbf9d-157">A última etapa é executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-157">The final step is to execute the query.</span></span> <span data-ttu-id="cbf9d-158">Depois que uma consulta é criada e salva, ela precisa ser executada.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-158">After a query is created and saved, it needs to be executed.</span></span> <span data-ttu-id="cbf9d-159">Ou seja, a instrução precisa ser executada para criar a estrutura de mineração no servidor.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-159">That is, the statement needs to be run in order to create the mining structure on the server.</span></span> <span data-ttu-id="cbf9d-160">Para obter mais informações sobre a execução de consultas no editor de consultas, consulte [mecanismo de banco de dados editor de consultas &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="cbf9d-160">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="cbf9d-161">Para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-161">To execute the query</span></span>  
  
1.  <span data-ttu-id="cbf9d-162">No editor de consultas, na barra de ferramentas, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-162">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="cbf9d-163">O status da consulta é exibido na guia **mensagens** na parte inferior do editor de consultas após a conclusão da execução da instrução.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-163">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="cbf9d-164">As mensagens devem exibir:</span><span class="sxs-lookup"><span data-stu-id="cbf9d-164">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="cbf9d-165">Uma nova estrutura chamada **comprador de bicicletas** agora existe no servidor.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-165">A new structure named **Bike Buyer** now exists on the server.</span></span>  
  
 <span data-ttu-id="cbf9d-166">Na próxima lição, você adicionará modelos de mineração à estrutura que acaba de criar.</span><span class="sxs-lookup"><span data-stu-id="cbf9d-166">In the next lesson, you will add mining models to the structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="cbf9d-167">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="cbf9d-167">Next Lesson</span></span>  
 [<span data-ttu-id="cbf9d-168">Lição 2: Adicionando modelos de mineração à estrutura de mineração de Comprador de Bicicleta</span><span class="sxs-lookup"><span data-stu-id="cbf9d-168">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md)  
  
  
