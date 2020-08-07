---
title: 'Lição 3: processando a estrutura de mineração do comprador de bicicletas | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e748c2cd-339d-4e82-82f1-be2d0fc41b61
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2e3f85016b32884b9a6b809e28d20d9985f97cd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681963"
---
# <a name="lesson-3-processing-the-bike-buyer-mining-structure"></a><span data-ttu-id="9dcfd-102">Lição 3: Processando a estrutura de mineração Comprador de Bicicleta</span><span class="sxs-lookup"><span data-stu-id="9dcfd-102">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="9dcfd-103">Nesta lição, você usará a instrução INSERT INTO e a exibição vTargetMail do banco de [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] dados de exemplo para processar as estruturas de mineração e os modelos de mineração criados na [lição 1: criando a estrutura de mineração de compradores de bicicletas](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) e a [lição 2: adicionando modelos de mineração à estrutura de mineração de compradores de bicicletas](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="9dcfd-103">In this lesson, you will use the INSERT INTO statement and the vTargetMail view from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) and [Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="9dcfd-104">Ao processar uma estrutura de mineração, o [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] lê os dados de origem e compila as estruturas que dão suporte a modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="9dcfd-105">Ao processar um modelo de mineração, os dados definidos pela estrutura de mineração são passados pelo algoritmo de mineração de dados escolhido.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you choose.</span></span> <span data-ttu-id="9dcfd-106">O algoritmo procura tendências e padrões e, depois, armazena as informações no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="9dcfd-107">Portanto, o modelo de mineração na verdade não contém os dados de origem, e sim as informações que foram descobertas pelo algoritmo.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="9dcfd-108">Para obter mais informações sobre o processamento de modelos de mineração, consulte [requisitos e considerações de processamento &#40;&#41;de mineração de dados ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9dcfd-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="9dcfd-109">Você precisará reprocessar uma estrutura de mineração somente se alterar uma coluna de estrutura ou alterar os dados de origem.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-109">You need to reprocess a mining structure only if you change a structure column or change the source data.</span></span> <span data-ttu-id="9dcfd-110">Adicionando-se um modelo de mineração a uma estrutura de mineração que já foi processada, é possível usar a instrução INSERT INTO MINING MODEL para treinar o novo modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-110">If you add a mining model to a mining structure that has already been processed, you can use the INSERT INTO MINING MODEL statement to train the new mining model.</span></span>  
  
## <a name="train-structure-template"></a><span data-ttu-id="9dcfd-111">Treinar modelo de estrutura</span><span class="sxs-lookup"><span data-stu-id="9dcfd-111">Train Structure Template</span></span>  
 <span data-ttu-id="9dcfd-112">Para treinar a estrutura de mineração e seus modelos de mineração associados, use a instrução [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="9dcfd-112">In order to train the mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="9dcfd-113">O código na instrução pode ser dividido nas seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="9dcfd-114">Identificando a estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="9dcfd-114">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="9dcfd-115">Listando as colunas na estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="9dcfd-115">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="9dcfd-116">Definindo os dados de treinamento</span><span class="sxs-lookup"><span data-stu-id="9dcfd-116">Defining the training data</span></span>  
  
 <span data-ttu-id="9dcfd-117">Segue um exemplo genérico da instrução INSERT INTO:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-117">The following is a generic example of the INSERT INTO statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="9dcfd-118">A primeira linha do código identifica a estrutura de mineração a ser treinada:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-118">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="9dcfd-119">A linha seguinte do código especifica as colunas definidas pela estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-119">The next line of the code specifies the columns that are defined by the mining structure.</span></span> <span data-ttu-id="9dcfd-120">É preciso listar cada coluna na estrutura de mineração, e cada coluna deve mapear para uma coluna contida nos dados da consulta de origem.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-120">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="9dcfd-121">A linha final do código define os dados que serão usados para treinar a estrutura de mineração:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-121">The final line of the code defines the data that will be used to train the mining structure:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="9dcfd-122">Nesta lição, use `OPENQUERY` para definir os dados de origem.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-122">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="9dcfd-123">Para obter informações sobre outros métodos de definição da consulta de origem, consulte [&#60;&#62;de consulta de dados de origem ](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="9dcfd-123">For information about other methods of defining the source query, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="9dcfd-124">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="9dcfd-124">Lesson Tasks</span></span>  
 <span data-ttu-id="9dcfd-125">Você executará a seguinte tarefa nesta lição:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-125">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="9dcfd-126">Processe a estrutura de mineração de Compradores de Bicicleta</span><span class="sxs-lookup"><span data-stu-id="9dcfd-126">Process the Bike Buyer mining structure</span></span>  
  
## <a name="processing-the-predictive-mining-structure"></a><span data-ttu-id="9dcfd-127">Processando a estrutura de mineração preditiva</span><span class="sxs-lookup"><span data-stu-id="9dcfd-127">Processing the Predictive Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="9dcfd-128">Para processar a estrutura de mineração utilizando INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="9dcfd-128">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="9dcfd-129">No Pesquisador de **objetos**, clique com o botão direito do mouse na instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , aponte para **nova consulta**e clique em **DMX**.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="9dcfd-130">O Editor de Consultas é exibido com uma consulta nova em branco.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="9dcfd-131">Copie o exemplo genérico da instrução INSERT INTO no campo em branco da consulta.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-131">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="9dcfd-132">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-132">Replace the following:</span></span>  
  
    ```  
    [<mining structure name>]   
    ```  
  
     <span data-ttu-id="9dcfd-133">por:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-133">with:</span></span>  
  
    ```  
    Bike Buyer  
    ```  
  
4.  <span data-ttu-id="9dcfd-134">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-134">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="9dcfd-135">por:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-135">with:</span></span>  
  
    ```  
    [Customer Key],  
    [Age],  
    [Bike Buyer],  
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
  
5.  <span data-ttu-id="9dcfd-136">Substitua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-136">Replace the following:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="9dcfd-137">por:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-137">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
     <span data-ttu-id="9dcfd-138">A instrução OPENQUERY referencia a fonte de dados [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] para acessar a exibição vTargetMail.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-138">The OPENQUERY statement references the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source to access the view vTargetMail.</span></span> <span data-ttu-id="9dcfd-139">A exibição contém os dados de origem que serão usados para treinar os modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-139">The view contains the source data that will be used to train the mining models.</span></span>  
  
     <span data-ttu-id="9dcfd-140">A instrução completa agora deve ser:</span><span class="sxs-lookup"><span data-stu-id="9dcfd-140">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key],  
       [Age],  
       [Bike Buyer],  
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
    )  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
6.  <span data-ttu-id="9dcfd-141">No menu **arquivo** , clique em **salvar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-141">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="9dcfd-142">Na caixa de diálogo **salvar como** , navegue até a pasta apropriada e nomeie o arquivo `Process Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="9dcfd-142">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Bike Buyer Structure.dmx`.</span></span>  
  
8.  <span data-ttu-id="9dcfd-143">Na barra de ferramentas, clique no botão **executar** .</span><span class="sxs-lookup"><span data-stu-id="9dcfd-143">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="9dcfd-144">Na próxima lição, você explorará o conteúdo dos modelos de mineração adicionados à estrutura de mineração nesta lição.</span><span class="sxs-lookup"><span data-stu-id="9dcfd-144">In the next lesson, you will explore content in the mining models you added to the mining structure in this lesson.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="9dcfd-145">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="9dcfd-145">Next Lesson</span></span>  
 [<span data-ttu-id="9dcfd-146">Lição 4: Explorando modelos de mineração Comprador de Bicicleta</span><span class="sxs-lookup"><span data-stu-id="9dcfd-146">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>](../../2014/tutorials/lesson-4-browsing-the-bike-buyer-mining-models.md)  
  
  
