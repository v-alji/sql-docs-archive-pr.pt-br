---
title: 'Lição 1: criando a estrutura de mineração de cesta de mercado | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a817c8d1-aff4-42b4-b194-ad9cc1c60f35
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a6a6e123e525512a72d70bcc8ca2eba549d1347e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681970"
---
# <a name="lesson-1-creating-the-market-basket-mining-structure"></a><span data-ttu-id="9c385-102">Lição 1: Criando a estrutura de mineração do Market Basket </span><span class="sxs-lookup"><span data-stu-id="9c385-102">Lesson 1: Creating the Market Basket Mining Structure</span></span>
  <span data-ttu-id="9c385-103">Nesta lição, você criará uma estrutura de mineração que permite prever quais produtos [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] um cliente tende a adquirir ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="9c385-103">In this lesson, you will create a mining structure that allows you to predict what [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] products a customer tends to purchase at the same time.</span></span> <span data-ttu-id="9c385-104">Se você não estiver familiarizado com as estruturas de mineração e sua função no Data Mining, consulte [estruturas de mineração &#40;Analysis Services-&#41;de mineração de dados ](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9c385-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="9c385-105">A estrutura de mineração de associação que você criará nesta lição oferece suporte à adição de modelos de mineração com base no [algoritmo de associação da Microsoft](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="9c385-105">The association mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md).</span></span> <span data-ttu-id="9c385-106">Em lições posteriores, você usará os modelos de mineração para prever o tipo de produtos que um cliente tente a comprar ao mesmo tempo, que é chamado de análise de cesta básica.</span><span class="sxs-lookup"><span data-stu-id="9c385-106">In later lessons, you will use the mining models to predict the type of products a customer tends to purchase at the same time, which is called a market basket analysis.</span></span> <span data-ttu-id="9c385-107">Por exemplo, você pode achar que os clientes tendem a comprar mountain bikes, pneus de bicicleta e capacetes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="9c385-107">For example, you may find that customers tend to buy mountain bikes, bike tires, and helmets at the same time.</span></span>  
  
 <span data-ttu-id="9c385-108">Nesta lição, a estrutura de mineração é definida usando as tabelas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="9c385-108">In this lesson, the mining structure is defined by using nested tables.</span></span> <span data-ttu-id="9c385-109">As tabelas aninhadas são usadas porque o domínio de dados que será definido pela estrutura está em duas tabelas de origem diferentes.</span><span class="sxs-lookup"><span data-stu-id="9c385-109">Nested tables are used because the data domain that will be defined by the structure is contained within two different source tables.</span></span> <span data-ttu-id="9c385-110">Para obter mais informações sobre tabelas aninhadas, consulte [tabelas aninhadas &#40;Analysis Services&#41;de mineração de dados ](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9c385-110">For more information on nested tables, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="9c385-111">Instrução CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="9c385-111">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="9c385-112">Para criar uma estrutura de mineração contendo uma tabela aninhada, use a instrução [criar estrutura de mineração &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="9c385-112">In order to create a mining structure containing a nested table, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="9c385-113">O código na instrução pode ser dividido nas seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="9c385-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="9c385-114">Nomeando a estrutura</span><span class="sxs-lookup"><span data-stu-id="9c385-114">Naming the structure</span></span>  
  
-   <span data-ttu-id="9c385-115">Definindo a coluna de chave</span><span class="sxs-lookup"><span data-stu-id="9c385-115">Defining the key column</span></span>  
  
-   <span data-ttu-id="9c385-116">Definindo as colunas de mineração</span><span class="sxs-lookup"><span data-stu-id="9c385-116">Defining the mining columns</span></span>  
  
-   <span data-ttu-id="9c385-117">Definindo as colunas de tabelas aninhadas</span><span class="sxs-lookup"><span data-stu-id="9c385-117">Defining the nested table columns</span></span>  
  
 <span data-ttu-id="9c385-118">A seguir, veja um exemplo genérico da instrução CREATE MINING STRUCTURE:</span><span class="sxs-lookup"><span data-stu-id="9c385-118">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<Mining Structure Name>]  
(  
   <key column>,  
   <mining structure columns>,  
   <table columns>  
   (  <nested key column>,  
      <nested mining structure columns> )  
)  
  
```  
  
 <span data-ttu-id="9c385-119">A primeira linha do código define o nome da estrutura:</span><span class="sxs-lookup"><span data-stu-id="9c385-119">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [Mining Structure Name]  
```  
  
 <span data-ttu-id="9c385-120">Para obter informações sobre como nomear um objeto no DMX, consulte [identificadores &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="9c385-120">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="9c385-121">A próxima linha do código define a coluna de chave da estrutura de mineração, que identifica exclusivamente uma entidade nos dados de origem:</span><span class="sxs-lookup"><span data-stu-id="9c385-121">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>  
```  
  
 <span data-ttu-id="9c385-122">A próxima linha do código define as colunas de mineração que serão usadas pelos modelos de mineração associados à estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="9c385-122">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="9c385-123">As próximas linhas do código definem as colunas de tabela aninhadas:</span><span class="sxs-lookup"><span data-stu-id="9c385-123">The next lines of the code define the nested table columns:</span></span>  
  
```  
<table columns>  
(  <nested key column>,  
   <nested mining structure columns> )  
```  
  
 <span data-ttu-id="9c385-124">Para obter informações sobre os tipos de colunas de estrutura de mineração que você pode definir, consulte [colunas da estrutura de mineração](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="9c385-124">For information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c385-125">Por padrão, o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] cria um conjunto de dados de validação de 30 por cento para cada estrutura de mineração; no entanto, ao usar DMX para criar uma estrutura de mineração, você deverá adicionar manualmente o conjunto de dados de validação, se desejado.</span><span class="sxs-lookup"><span data-stu-id="9c385-125">By default, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates a 30 percent holdout data set for each mining structure; however, when you use DMX to create a mining structure, you must manually add the holdout data set, if desired.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="9c385-126">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="9c385-126">Lesson Tasks</span></span>  
 <span data-ttu-id="9c385-127">Você executará as seguintes tarefas nesta lição:</span><span class="sxs-lookup"><span data-stu-id="9c385-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="9c385-128">Criar uma nova consulta em branco</span><span class="sxs-lookup"><span data-stu-id="9c385-128">Create a new blank query</span></span>  
  
-   <span data-ttu-id="9c385-129">Alterar a consulta para criar a estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="9c385-129">Alter the query to create the mining structure</span></span>  
  
-   <span data-ttu-id="9c385-130">Executar a consulta</span><span class="sxs-lookup"><span data-stu-id="9c385-130">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="9c385-131">Criando a consulta</span><span class="sxs-lookup"><span data-stu-id="9c385-131">Creating the Query</span></span>  
 <span data-ttu-id="9c385-132">A primeira etapa é se conectar a uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e criar uma nova consulta DMX no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c385-132">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="9c385-133">Para criar uma nova consulta DMX no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9c385-133">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="9c385-134">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c385-134">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="9c385-135">Na caixa de diálogo **conectar ao servidor** , para **tipo de servidor**, selecione **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="9c385-135">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="9c385-136">Em **nome do servidor**, digite `LocalHost` ou o nome da instância do à [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qual você deseja se conectar para esta lição.</span><span class="sxs-lookup"><span data-stu-id="9c385-136">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="9c385-137">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="9c385-137">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="9c385-138">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="9c385-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="9c385-139">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="9c385-139">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="9c385-140">Alterando a consulta</span><span class="sxs-lookup"><span data-stu-id="9c385-140">Altering the Query</span></span>  
 <span data-ttu-id="9c385-141">A próxima etapa é modificar a instrução CREATE MINING STRUCTURE descrita acima para criar a estrutura de mineração de Cesta Básica.</span><span class="sxs-lookup"><span data-stu-id="9c385-141">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Market Basket mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="9c385-142">Para personalizar a instrução CREATE MINING STRUCTURE.</span><span class="sxs-lookup"><span data-stu-id="9c385-142">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="9c385-143">No editor de consultas, copie o exemplo genérico da instrução criar estrutura de mineração para a consulta em branco.</span><span class="sxs-lookup"><span data-stu-id="9c385-143">In Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="9c385-144">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c385-144">Replace the following:</span></span>  
  
    ```  
    [mining structure name]   
    ```  
  
     <span data-ttu-id="9c385-145">por:</span><span class="sxs-lookup"><span data-stu-id="9c385-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
3.  <span data-ttu-id="9c385-146">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c385-146">Replace the following:</span></span>  
  
    ```  
    <key column>  
    ```  
  
     <span data-ttu-id="9c385-147">por:</span><span class="sxs-lookup"><span data-stu-id="9c385-147">with:</span></span>  
  
    ```  
    OrderNumber TEXT KEY  
    ```  
  
4.  <span data-ttu-id="9c385-148">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c385-148">Replace the following:</span></span>  
  
    ```  
    <table columns>  
    (  <nested key column>,  
       <nested mining structure columns> )  
    ```  
  
     <span data-ttu-id="9c385-149">por:</span><span class="sxs-lookup"><span data-stu-id="9c385-149">with:</span></span>  
  
    ```  
    [Products] TABLE (  
        [Model] TEXT KEY  
    )  
    ```  
  
     <span data-ttu-id="9c385-150">A linguagem TEXT KEY especifica que a coluna Modelo é a coluna de chave para a tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="9c385-150">The TEXT KEY language specifies that the Model column is the key column for the nested table.</span></span>  
  
     <span data-ttu-id="9c385-151">A instrução completa da estrutura de mineração agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="9c385-151">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Market Basket] (  
        OrderNumber TEXT KEY,  
        [Products] TABLE (  
            [Model] TEXT KEY  
        )  
    )  
    ```  
  
5.  <span data-ttu-id="9c385-152">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="9c385-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="9c385-153">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Market Basket Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="9c385-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Market Basket Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="9c385-154">Executando a consulta</span><span class="sxs-lookup"><span data-stu-id="9c385-154">Executing the Query</span></span>  
 <span data-ttu-id="9c385-155">A última etapa é executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="9c385-155">The final step is to execute the query.</span></span> <span data-ttu-id="9c385-156">Depois que você cria e salva a consulta, ela deve ser executada (isto é, a instrução deve ser executada) para criar a estrutura de mineração no servidor.</span><span class="sxs-lookup"><span data-stu-id="9c385-156">After a query is created and saved, it needs to be executed (that is, the statement needs to be run) in order to create the mining structure on the server.</span></span> <span data-ttu-id="9c385-157">Para obter mais informações sobre a execução de consultas no editor de consultas, consulte [mecanismo de banco de dados editor de consultas &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="9c385-157">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="9c385-158">Para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="9c385-158">To execute the query</span></span>  
  
-   <span data-ttu-id="9c385-159">No editor de consultas, na barra de ferramentas, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="9c385-159">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="9c385-160">O status da consulta é exibido na guia **mensagens** na parte inferior do editor de consultas após a conclusão da execução da instrução.</span><span class="sxs-lookup"><span data-stu-id="9c385-160">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="9c385-161">As mensagens devem exibir:</span><span class="sxs-lookup"><span data-stu-id="9c385-161">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="9c385-162">Uma nova estrutura denominada **cesta de mercado** agora existe no servidor.</span><span class="sxs-lookup"><span data-stu-id="9c385-162">A new structure named **Market Basket** now exists on the server.</span></span>  
  
 <span data-ttu-id="9c385-163">Na próxima lição, você adicionará dois modelos de mineração à estrutura de mineração Cesta Básica recém-criada.</span><span class="sxs-lookup"><span data-stu-id="9c385-163">In the next lesson, you will add mining models to the Market Basket mining structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="9c385-164">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="9c385-164">Next Lesson</span></span>  
 [<span data-ttu-id="9c385-165">Lição 2: Adicionando modelos de mineração à estrutura de mineração do Market Basket</span><span class="sxs-lookup"><span data-stu-id="9c385-165">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md)  
  
  
