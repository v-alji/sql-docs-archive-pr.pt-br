---
title: Consultar os parâmetros usados para criar um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: ce7719e0-6127-4d9c-a753-0e0a3db065e1
author: minewiskan
ms.author: owend
ms.openlocfilehash: a3802a0d70579f613accbe6abd310da909751b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681279"
---
# <a name="query-the-parameters-used-to-create-a-mining-model"></a><span data-ttu-id="d7672-102">Consultar os parâmetros usados para criar um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="d7672-102">Query the Parameters Used to Create a Mining Model</span></span>
  <span data-ttu-id="d7672-103">A composição de um modelo de mineração é afetada não apenas pelos casos de treinamento, mas também pelos parâmetros que foram definidos quando o modelo foi criado.</span><span class="sxs-lookup"><span data-stu-id="d7672-103">The composition of a mining model is affected not only by the training cases, but by the parameters that were set when the model was created.</span></span> <span data-ttu-id="d7672-104">Portanto, talvez seja útil recuperar as configurações de parâmetro de um modelo existente para compreender melhor o comportamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="d7672-104">Therefore, you might find it useful to retrieve the parameter settings of an existing model to better understand the behavior of the model.</span></span> <span data-ttu-id="d7672-105">A recuperação de parâmetros também é útil na documentação de uma versão específica desse modelo.</span><span class="sxs-lookup"><span data-stu-id="d7672-105">Retrieving parameters is also useful when documenting a particular version of that model.</span></span>  
  
 <span data-ttu-id="d7672-106">Para localizar parâmetros que foram usados quando o modelo foi criado, você cria uma consulta em um dos conjuntos de linhas do esquema do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="d7672-106">To find the parameters that were used when the model was created, you create a query against one of the mining model schema rowsets.</span></span> <span data-ttu-id="d7672-107">No [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)], esses conjuntos de linhas de esquema são expostos como um conjunto de exibições do sistema que pode ser consultado facilmente com a sintaxe Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="d7672-107">In [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)], these schema rowsets are exposed as a set of system views that you can query easily by using Transact-SQL syntax.</span></span> <span data-ttu-id="d7672-108">Este procedimento descreve como criar uma consulta que retorna os parâmetros usados para criar o modelo de mineração especificado.</span><span class="sxs-lookup"><span data-stu-id="d7672-108">This procedure describes how to create a query that returns the parameters that were used to create the specified mining model.</span></span>  
  
### <a name="to-open-a-query-window-for-a-schema-rowset-query"></a><span data-ttu-id="d7672-109">Para abrir uma janela Consulta para uma consulta de conjunto de linhas de esquema</span><span class="sxs-lookup"><span data-stu-id="d7672-109">To open a Query window for a schema rowset query</span></span>  
  
1.  <span data-ttu-id="d7672-110">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra a instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém o modelo que deseja consultar.</span><span class="sxs-lookup"><span data-stu-id="d7672-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the model you want to query.</span></span>  
  
2.  <span data-ttu-id="d7672-111">Clique com o botão direito do mouse no nome da instância, selecione **Nova Consulta**e selecione **DMX**.</span><span class="sxs-lookup"><span data-stu-id="d7672-111">Right-click the instance name, select **New Query**, and then select **DMX**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d7672-112"> Você também pode criar uma consulta para um modelo de mineração de dados usando o modelo **MDX** .</span><span class="sxs-lookup"><span data-stu-id="d7672-112">You can also create a query against a data mining model by using the **MDX** template.</span></span>  
  
3.  <span data-ttu-id="d7672-113">Se a instância tiver vários bancos de dados, selecione o banco de dados que contém o modelo que deseja consultar na lista **Banco de Dados Disponíveis** da barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="d7672-113">If the instance contains multiple databases, select the database that contains the model you want to query from the **Available Databases** list in the toolbar.</span></span>  
  
### <a name="to-return-model-parameters-for-an-existing-mining-model"></a><span data-ttu-id="d7672-114">Para retornar parâmetros de modelo para um modelo de mineração existente</span><span class="sxs-lookup"><span data-stu-id="d7672-114">To return model parameters for an existing mining model</span></span>  
  
1.  <span data-ttu-id="d7672-115">No painel de consulta DMX, digite ou cole o seguinte texto:</span><span class="sxs-lookup"><span data-stu-id="d7672-115">In the DMX query pane, type or paste the following text:</span></span>  
  
    ```  
    SELECT MINING_PARAMETERS  
    FROM $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = ''  
    ```  
  
2.  <span data-ttu-id="d7672-116">No Pesquisador de Objetos, selecione o modelo de mineração desejado e arraste-o no painel de consulta DMX, entre as aspas simples.</span><span class="sxs-lookup"><span data-stu-id="d7672-116">In Object Explorer, select the mining model you want, and then drag it into the DMX Query pane, between the single quotation marks.</span></span>  
  
3.  <span data-ttu-id="d7672-117">Pressione F5 ou clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="d7672-117">Press F5, or click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7672-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d7672-118">Example</span></span>  
 <span data-ttu-id="d7672-119">O código a seguir retorna uma lista dos parâmetros usados para criar o modelo de mineração que você criou no [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d7672-119">The following code returns a list of the parameters that were used to create the mining model that you build in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="d7672-120">Esses parâmetros incluem os valores explícitos de todos os padrões usados pelos serviços de mineração disponíveis dos provedores no servidor.</span><span class="sxs-lookup"><span data-stu-id="d7672-120">These parameters include the explicit values for any defaults used by the mining services available from providers on the server.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
 <span data-ttu-id="d7672-121">O exemplo de código retorna os seguintes parâmetros para o modelo de clustering:</span><span class="sxs-lookup"><span data-stu-id="d7672-121">The code example returns the following parameters for the clustering model:</span></span>  
  
 <span data-ttu-id="d7672-122">Resultados de eExample:</span><span class="sxs-lookup"><span data-stu-id="d7672-122">eExample Results:</span></span>  
  
 <span data-ttu-id="d7672-123">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d7672-123">MINING_PARAMETERS</span></span>  
  
 <span data-ttu-id="d7672-124">CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10</span><span class="sxs-lookup"><span data-stu-id="d7672-124">CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7672-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d7672-125">See Also</span></span>  
 <span data-ttu-id="d7672-126">[Tarefas e instruções de consulta de mineração de dados](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="d7672-126">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="d7672-127">Consultas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="d7672-127">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
