---
title: 'Lição 3: processando a estrutura de mineração de cesta de mercado | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 095a043f-cf6f-45bb-a021-ae4e1b535c65
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ce2c2e6944d524a38edc331d2cd128ca7cf7d419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678375"
---
# <a name="lesson-3-processing-the-market-basket-mining-structure"></a><span data-ttu-id="f2149-102">Lição 3: Processando a estrutura de mineração do Market Basket</span><span class="sxs-lookup"><span data-stu-id="f2149-102">Lesson 3: Processing the Market Basket Mining Structure</span></span>
  <span data-ttu-id="f2149-103">Nesta lição, você usará a instrução [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) e o vAssocSeqLineItems e o vAssocSeqOrders do [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] banco de dados de exemplo para processar as estruturas de mineração e os modelos de mineração criados na [lição 1: criando a estrutura de mineração da cesta de compras](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) e a [lição 2: adicionando modelos de mineração à estrutura de mineração da cesta de compras](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="f2149-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement and the vAssocSeqLineItems and vAssocSeqOrders from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) and [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span>  
  
 <span data-ttu-id="f2149-104">Ao processar uma estrutura de mineração, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] lê os dados de origem e compila as estruturas que dão suporte a modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="f2149-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="f2149-105">Quando você processa um modelo de mineração, os dados definidos pela estrutura de mineração são passados pelo algoritmo de Data Mining que você escolheu.</span><span class="sxs-lookup"><span data-stu-id="f2149-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you chose.</span></span> <span data-ttu-id="f2149-106">O algoritmo procura tendências e padrões e, depois, armazena as informações no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="f2149-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="f2149-107">Portanto, o modelo de mineração na verdade não contém os dados de origem, e sim as informações que foram descobertas pelo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="f2149-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="f2149-108">Para obter mais informações sobre o processamento de modelos de mineração, consulte [requisitos e considerações de processamento &#40;&#41;de mineração de dados ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f2149-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="f2149-109">Só será necessário reprocessar uma estrutura de mineração se houver alteração em uma coluna de estrutura ou nos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="f2149-109">You only have to reprocess a mining structure if you change a structure column or change the source data.</span></span> <span data-ttu-id="f2149-110">Se você adicionar um modelo de mineração a uma estrutura de mineração que já foi processada, será possível usar a instrução `INSERT INTO MINING MODEL` para treinar o novo modelo de mineração nos dados existentes.</span><span class="sxs-lookup"><span data-stu-id="f2149-110">If you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to train the new mining model on the existing data.</span></span>  
  
 <span data-ttu-id="f2149-111">Como a estrutura de mineração da cesta básica contém uma tabela aninhada, você terá que definir as colunas de mineração a serem treinadas, utilizando a estrutura de tabelas aninhadas, e utilizar o comando `SHAPE` para definir as consultas que recebem dados de treinamento das tabelas de origem.</span><span class="sxs-lookup"><span data-stu-id="f2149-111">Because the Market Basket mining structure contains a nested table, you will have to define the mining columns to be trained using the nested table structure, and use the `SHAPE` command to define the queries that pull the training data from the source tables.</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="f2149-112">Instrução INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="f2149-112">INSERT INTO Statement</span></span>  
 <span data-ttu-id="f2149-113">Para treinar a estrutura de mineração de cesta de compras e seus modelos de mineração associados, use a instrução [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="f2149-113">In order to train the Market Basket mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="f2149-114">O código na instrução pode ser dividido nas seguintes partes.</span><span class="sxs-lookup"><span data-stu-id="f2149-114">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="f2149-115">Identificando a estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="f2149-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="f2149-116">Listando as colunas na estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="f2149-116">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="f2149-117">Definindo os dados de treinamento usando `SHAPE`</span><span class="sxs-lookup"><span data-stu-id="f2149-117">Defining the training data using `SHAPE`</span></span>  
  
 <span data-ttu-id="f2149-118">A seguir, um exemplo genérico da instrução `INSERT INTO`:</span><span class="sxs-lookup"><span data-stu-id="f2149-118">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],'<nested SELECT statement>')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="f2149-119">A primeira linha do código identifica a estrutura de mineração a ser treinada:</span><span class="sxs-lookup"><span data-stu-id="f2149-119">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="f2149-120">As linhas seguintes do código especificam as colunas definidas pela estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="f2149-120">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="f2149-121">É preciso listar cada coluna na estrutura de mineração, e cada coluna deve mapear para uma coluna contida nos dados da consulta de origem.</span><span class="sxs-lookup"><span data-stu-id="f2149-121">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span> <span data-ttu-id="f2149-122">Você pode utilizar `SKIP` para ignorar colunas que existem nos dados de origem, mas não existem na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="f2149-122">You can use `SKIP` to ignore columns that exist in the source data but do not exist in the mining structure.</span></span> <span data-ttu-id="f2149-123">Para obter mais informações sobre como usar o `SKIP` , consulte [inserir em &#40;DMX&#41;](/sql/dmx/insert-into-dmx).</span><span class="sxs-lookup"><span data-stu-id="f2149-123">For more information about how to use `SKIP`, see [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx).</span></span>  
  
```  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
```  
  
 <span data-ttu-id="f2149-124">As linhas finais do código definem os dados que serão usados para treinar a estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="f2149-124">The final lines of the code define the data that will be used to train the mining structure.</span></span> <span data-ttu-id="f2149-125">Como os dados de origem estão contidos dentro de duas tabelas, você usará `SHAPE` para relacionar as tabelas.</span><span class="sxs-lookup"><span data-stu-id="f2149-125">Because the source data is contained within two tables, you will use `SHAPE` to relate the tables.</span></span>  
  
```  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],''<nested SELECT statement>'')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="f2149-126">Nesta lição, use `OPENQUERY` para definir os dados de origem.</span><span class="sxs-lookup"><span data-stu-id="f2149-126">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="f2149-127">Para obter informações sobre outros métodos de definição de uma consulta nos dados de origem, consulte [&#60;&#62;de consulta de dados de origem ](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="f2149-127">For information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="f2149-128">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="f2149-128">Lesson Tasks</span></span>  
 <span data-ttu-id="f2149-129">Você executará a seguinte tarefa nesta lição:</span><span class="sxs-lookup"><span data-stu-id="f2149-129">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="f2149-130">Processe a estrutura de mineração da cesta básica</span><span class="sxs-lookup"><span data-stu-id="f2149-130">Process the Market Basket mining structure</span></span>  
  
## <a name="processing-the-market-basket-mining-structure"></a><span data-ttu-id="f2149-131">Processando a estrutura de mineração da cesta básica</span><span class="sxs-lookup"><span data-stu-id="f2149-131">Processing the Market Basket Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="f2149-132">Para processar a estrutura de mineração utilizando INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="f2149-132">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="f2149-133">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="f2149-133">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="f2149-134">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="f2149-134">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="f2149-135">Copie o exemplo genérico da instrução INSERT INTO no campo em branco da consulta.</span><span class="sxs-lookup"><span data-stu-id="f2149-135">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="f2149-136">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f2149-136">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="f2149-137">por:</span><span class="sxs-lookup"><span data-stu-id="f2149-137">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="f2149-138">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f2149-138">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    [<nested table>]  
    ( SKIP, <skipped column> )  
    ```  
  
     <span data-ttu-id="f2149-139">por:</span><span class="sxs-lookup"><span data-stu-id="f2149-139">with:</span></span>  
  
    ```  
    [OrderNumber],  
    [Products]   
    (SKIP, [Model])  
    ```  
  
     <span data-ttu-id="f2149-140">Na instrução, `Products` se refere à tabela Produtos definida pela instrução SHAPE.</span><span class="sxs-lookup"><span data-stu-id="f2149-140">In the statement, `Products` refers to the Products table defined by the SHAPE statement.</span></span> <span data-ttu-id="f2149-141">`SKIP` é usado para ignorar a coluna Modelo, que existe nos dados de origem como uma chave, mas não é usada pela estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="f2149-141">`SKIP` is used to ignore the Model column, which exists in the source data as a key, but is not used by the mining structure.</span></span>  
  
5.  <span data-ttu-id="f2149-142">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f2149-142">Replace the following:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([<datasource>],'<SELECT statement>') }  
    APPEND  
    (   
      {OPENQUERY([<datasource>],'<nested SELECT statement>')  
    }  
    RELATE [<case key>] TO [<foreign key>]  
    ) AS [<nested table>]  
    ```  
  
     <span data-ttu-id="f2149-143">por:</span><span class="sxs-lookup"><span data-stu-id="f2149-143">with:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
     <span data-ttu-id="f2149-144">A consulta de origem faz referência à [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] fonte de dados definida no [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] projeto de exemplo.</span><span class="sxs-lookup"><span data-stu-id="f2149-144">The source query references the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample project.</span></span> <span data-ttu-id="f2149-145">Ela usa esta fonte de dados para acessar as exibições vAssocSeqLineItems e vAssocSeqOrders.</span><span class="sxs-lookup"><span data-stu-id="f2149-145">It uses this data source to access the vAssocSeqLineItems and vAssocSeqOrders views.</span></span> <span data-ttu-id="f2149-146">Essas exibições contêm os dados de origem que serão usados para treinar o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="f2149-146">These views contain the source data that will be used to train the mining model.</span></span> <span data-ttu-id="f2149-147">Se você não criou este projeto ou esses modos de exibição, consulte o [tutorial de mineração de dados básico](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="f2149-147">If you have not created this project or these views, see [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="f2149-148">Dentro do comando `SHAPE`, você usará `OPENQUERY` para definir duas consultas.</span><span class="sxs-lookup"><span data-stu-id="f2149-148">Within the `SHAPE` command, you will use `OPENQUERY` to define two queries.</span></span> <span data-ttu-id="f2149-149">A primeira consulta define a tabela pai, e a segunda consulta define a tabela aninhada.</span><span class="sxs-lookup"><span data-stu-id="f2149-149">The first query defines the parent table, and the second query defines the nested table.</span></span> <span data-ttu-id="f2149-150">As duas tabelas estão relacionadas usando a coluna OrderNumber que existe em ambas as tabelas.</span><span class="sxs-lookup"><span data-stu-id="f2149-150">The two tables are related using the OrderNumber column, which exists in both tables.</span></span>  
  
     <span data-ttu-id="f2149-151">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="f2149-151">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Market Basket]  
    (  
       [OrderNumber],[Products] (SKIP, [Model])  
    )  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
6.  <span data-ttu-id="f2149-152">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="f2149-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="f2149-153">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Process Market Basket.dmx` .</span><span class="sxs-lookup"><span data-stu-id="f2149-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Market Basket.dmx`.</span></span>  
  
8.  <span data-ttu-id="f2149-154">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="f2149-154">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="f2149-155">Após a conclusão da execução da consulta, você pode visualizar os padrões e os conjuntos de itens que foram encontrados, exibir associações ou filtrar por conjunto de itens, probabilidade ou importância.</span><span class="sxs-lookup"><span data-stu-id="f2149-155">After the query has finished running, you can view the patterns and itemsets that were found, view associations, or filter by itemset, probability, or importance.</span></span> <span data-ttu-id="f2149-156">Para exibir essas informações, no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , clique com o botão direito do mouse no nome do modelo de dados e clique em **procurar**.</span><span class="sxs-lookup"><span data-stu-id="f2149-156">To view this information, in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click the name of the data model, and then click **Browse**.</span></span>  
  
 <span data-ttu-id="f2149-157">Na próxima lição, você criará várias previsões com base nos modelos de mineração que adicionou à estrutura da cesta básica.</span><span class="sxs-lookup"><span data-stu-id="f2149-157">In the next lesson, you will create several predictions based on the mining models that you added to the Market Basket structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="f2149-158">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="f2149-158">Next Lesson</span></span>  
 [<span data-ttu-id="f2149-159">Lição 4: Executando previsões de Market Basket</span><span class="sxs-lookup"><span data-stu-id="f2149-159">Lesson 4: Executing Market Basket Predictions</span></span>](../../2014/tutorials/lesson-4-executing-market-basket-predictions.md)  
  
  
