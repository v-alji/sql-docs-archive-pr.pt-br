---
title: Criar uma consulta de conteúdo em um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: a0ce837a-89ed-46cf-9ce1-801ccb75fa04
author: minewiskan
ms.author: owend
ms.openlocfilehash: 26af1100d6ba80185c1cc4de18548df0e387824c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678356"
---
# <a name="create-a-content-query-on-a-mining-model"></a><span data-ttu-id="483d9-102">Criar uma consulta de conteúdo em um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="483d9-102">Create a Content Query on a Mining Model</span></span>
  <span data-ttu-id="483d9-103">Você pode consultar o conteúdo do modelo de mineração via programação usando AMO ou XML/A, mas é mais fácil criar consultas usando DMX.</span><span class="sxs-lookup"><span data-stu-id="483d9-103">You can query the mining model content programmatically by using AMO or XML/A, but it is easier to create queries by using DMX.</span></span> <span data-ttu-id="483d9-104">Também é possível criar consultas nos conjuntos de linhas de esquema de mineração de dados estabelecendo uma conexão com a instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e criando uma consulta usando os DMVs fornecidos pelo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="483d9-104">You can also create queries against the data mining schema rowsets by establishing a connection to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and creating a query using the DMVs provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="483d9-105">Os procedimentos a seguir demonstram como criar consultas em um modelo de mineração usando DMX e como consultar os conjuntos de linhas de esquema de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="483d9-105">The following procedures demonstrate how to create queries against a mining model by using DMX, and how to query the data mining schema rowsets.</span></span>  
  
 <span data-ttu-id="483d9-106">Para obter um exemplo de como criar uma consulta semelhante usando XML/A, consulte [Criar uma consulta de mineração de dados usando XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="483d9-106">For an example of how to create a similar query by using XML/A, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="querying-data-mining-model-content-by-using-dmx"></a><span data-ttu-id="483d9-107">Consultando o conteúdo do modelo de mineração de dados usando DMX</span><span class="sxs-lookup"><span data-stu-id="483d9-107">Querying Data Mining Model Content by Using DMX</span></span>  
  
#### <a name="to-create-a-dmx-model-content-query"></a><span data-ttu-id="483d9-108">Para criar uma consulta ao conteúdo do modelo DMX</span><span class="sxs-lookup"><span data-stu-id="483d9-108">To create a DMX model content query</span></span>  
  
1.  <span data-ttu-id="483d9-109">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Exibir** , clique em **Gerenciador de Modelos**.</span><span class="sxs-lookup"><span data-stu-id="483d9-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="483d9-110">No painel **Gerenciador de Modelos** , clique no ícone de cubo para alterar a lista e exibir modelos do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="483d9-110">In the **Template Explorer** pane, click the cube icon to change the list and display Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="483d9-111">Na lista de categorias de modelo, expanda **DMX**, expanda **Conteúdo do Modelo**e clique duas vezes em **Consulta de Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="483d9-111">In the list of template categories, expand **DMX**, expand **Model Content**, and double-click **Content Query**.</span></span>  
  
4.  <span data-ttu-id="483d9-112">Na caixa de diálogo **Conectar ao Analysis Services** , selecione a instância que contém o modelo de mineração que você deseja consultar e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="483d9-112">In the **Connect to Analysis Services** dialog box, select the instance that contains the mining model you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="483d9-113">O modelo **Consulta de Conteúdo** é aberto no editor de códigos apropriado.</span><span class="sxs-lookup"><span data-stu-id="483d9-113">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="483d9-114">O painel de metadados lista os modelos que estão disponíveis no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="483d9-114">The metadata pane lists the models that are available in the current database.</span></span> <span data-ttu-id="483d9-115">Para alterar o banco de dados, selecione outro banco de dados na lista **Bancos de Dados Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="483d9-115">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
5.  <span data-ttu-id="483d9-116">Insira o nome de um modelo de mineração na linha `FROM` [ *\<mining model, name, MyModel>* ] `.CONTENT` .</span><span class="sxs-lookup"><span data-stu-id="483d9-116">Enter the name of a mining model in the line, `FROM` [*\<mining model, name, MyModel>*]`.CONTENT`.</span></span> <span data-ttu-id="483d9-117">Se o nome do modelo de mineração contiver espaços, coloque o nome entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="483d9-117">If the mining model name contains spaces, you must enclose the name in brackets.</span></span>  
  
     <span data-ttu-id="483d9-118">Se não quiser digitar o nome, você poderá selecionar um modelo de mineração no **Pesquisador de Objetos** e arrastá-lo para o modelo.</span><span class="sxs-lookup"><span data-stu-id="483d9-118">If you don't want to type the name, you can select a mining model in **Object Explorer** and drag it into the template.</span></span>  
  
6.  <span data-ttu-id="483d9-119">Na linha, `SELECT` *\<select list, expr list, \*>* , digite os nomes das colunas no conjunto de linhas do esquema de conteúdo do modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="483d9-119">In the line, `SELECT`*\<select list, expr list, \*>*, type the names of columns in the mining model content schema rowset.</span></span>  
  
     <span data-ttu-id="483d9-120">Para ver uma lista das colunas que podem ser retornadas em consultas ao conteúdo do modelo de mineração, consulte [Conteúdo do modelo de mineração &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="483d9-120">To view a list of columns that you can return in mining model content queries, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
7.  <span data-ttu-id="483d9-121">Se preferir, digite uma condição na cláusula WHERE do modelo para restringir as linhas retornadas a nós ou valores específicos.</span><span class="sxs-lookup"><span data-stu-id="483d9-121">Optionally, type a condition in the WHERE clause of the template to restrict the rows returned to specific nodes or values.</span></span>  
  
8.  <span data-ttu-id="483d9-122">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="483d9-122">Click **Execute**.</span></span>  
  
## <a name="querying-the-data-mining-schema-rowsets"></a><span data-ttu-id="483d9-123">Consultando os conjuntos de linhas de esquema de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="483d9-123">Querying the Data Mining Schema Rowsets</span></span>  
  
#### <a name="to-create-a-query-against-the-data-mining-schema-rowset"></a><span data-ttu-id="483d9-124">Para criar uma consulta no conjunto de linhas do esquema de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="483d9-124">To create a query against the data mining schema rowset</span></span>  
  
1.  <span data-ttu-id="483d9-125">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], na barra de ferramentas **Nova Consulta** , clique em **Consulta DMX do Analysis Services**ou em **Consulta MDX do Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="483d9-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **New Query** toolbar, click **Analysis Services DMX Query**, or **Analysis Services MDX query**.</span></span>  
  
2.  <span data-ttu-id="483d9-126">Na caixa de diálogo **Conectar ao Analysis Services** , selecione a instância que contém os objetos que você deseja consultar e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="483d9-126">In the **Connect to Analysis Services** dialog box, select the instance that contains the objects you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="483d9-127">O modelo **Consulta de Conteúdo** é aberto no editor de códigos apropriado.</span><span class="sxs-lookup"><span data-stu-id="483d9-127">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="483d9-128">O painel de metadados lista os objetos que estão disponíveis no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="483d9-128">The metadata pane lists the objects that are available in the current database.</span></span> <span data-ttu-id="483d9-129">Para alterar o banco de dados, selecione outro banco de dados na lista **Bancos de Dados Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="483d9-129">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
3.  <span data-ttu-id="483d9-130">No editor de consultas, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="483d9-130">In the query editor, type the following:</span></span>  
  
     `SELECT *`  
  
     `FROM $system.DMSCHEMA_MINING_MODEL_CONTENT`  
  
     `WHERE MODEL_NAME = '<model name>'`  
  
4.  <span data-ttu-id="483d9-131">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="483d9-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="483d9-132">O painel Resultados exibe o conteúdo do modelo.</span><span class="sxs-lookup"><span data-stu-id="483d9-132">The Results pane displays the contents of the model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="483d9-133">Para ver uma lista de todos os conjuntos de linhas de esquema que você pode consultar na instância atual, use esta consulta: `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span><span class="sxs-lookup"><span data-stu-id="483d9-133">To view a list of all the schema rowsets that you can query on the current instance, use this query: `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span></span> <span data-ttu-id="483d9-134">Para ver uma lista de conjuntos de linhas de esquema específicos de mineração de dados, consulte [Conjuntos de linhas de esquema de mineração de dados](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="483d9-134">Or, for a list of schema rowsets specific to data mining, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="483d9-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="483d9-135">See Also</span></span>  
 <span data-ttu-id="483d9-136">[Conteúdo do modelo de mineração &#40;Analysis Services Mineração de dados&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="483d9-136">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="483d9-137">Conjuntos de linhas de esquema de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="483d9-137">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
