---
title: Criar uma consulta de mineração de dados usando XMLA | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: 8f6b6008-006c-4792-9bd1-64c30dc3fd41
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0e85b17db0781671fab0874706f12fdac95b30b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582696"
---
# <a name="create-a-data-mining-query-by-using-xmla"></a><span data-ttu-id="a70a8-102">Criar uma consulta de mineração de dados usando XMLA</span><span class="sxs-lookup"><span data-stu-id="a70a8-102">Create a Data Mining Query by Using XMLA</span></span>
  <span data-ttu-id="a70a8-103">Você pode criar várias consultas referentes a objetos de mineração de dados usando AMO, DMX ou XML/A.</span><span class="sxs-lookup"><span data-stu-id="a70a8-103">You can create a variety of queries against data mining objects by using AMO, DMX, or XML/A.</span></span>  
  
 <span data-ttu-id="a70a8-104">O XML é usado para comunicação entre o servidor Analysis Services e todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="a70a8-104">XML is used for communication between the Analysis Services server and all clients.</span></span> <span data-ttu-id="a70a8-105">Assim, embora geralmente seja muito mais fácil criar consultas de conteúdo usando DMX, você pode escrever consultas usando as instruções DISCOVER e COMMAND em XML/A, com um cliente que dê suporte a protocolo SOAP ou criando uma consulta XML/A no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a70a8-105">Therefore, although it is generally much easier to create content queries by using DMX, you can write queries by using the DISCOVER and COMMAND statements in XML/A, either by using a client that supports the SOAP protocol, or by creating an XML/A query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a70a8-106">Este tópico explica como usar os modelos XML/A disponíveis no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para criar uma consulta de conteúdo de modelo referente a um modelo de mineração armazenado no servidor atual.</span><span class="sxs-lookup"><span data-stu-id="a70a8-106">This topic explains how to use the XML/A templates that are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a model content query against a mining model stored on the current server.</span></span>  
  
## <a name="querying-data-mining-schema-rowsets-by-using-xmla"></a><span data-ttu-id="a70a8-107">Consultando conjuntos de linhas de esquema de mineração de dados usando XML/A</span><span class="sxs-lookup"><span data-stu-id="a70a8-107">Querying Data Mining Schema Rowsets by Using XML/A</span></span>  
  
#### <a name="to-open-an-xmla-template"></a><span data-ttu-id="a70a8-108">Para abrir um modelo XML/A</span><span class="sxs-lookup"><span data-stu-id="a70a8-108">To open an XML/A template</span></span>  
  
1.  <span data-ttu-id="a70a8-109">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Exibir** , clique em **Gerenciador de Modelos**.</span><span class="sxs-lookup"><span data-stu-id="a70a8-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="a70a8-110">Clique no ícone de cubo para abrir a lista de modelos do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a70a8-110">Click the cube icon to open the list of Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="a70a8-111">Na lista de categorias de modelo, expanda **XMLA**, **Conjuntos de Linhas do Esquema**e clique duas vezes em **Descobrir Conjuntos de Linhas do Esquema** para abrir o modelo no editor de código apropriado.</span><span class="sxs-lookup"><span data-stu-id="a70a8-111">In the list of template categories, expand **XMLA**, expand **Schema Rowsets**, and double-click **Discover Schema Rowsets** to open the template in the appropriate code editor.</span></span>  
  
4.  <span data-ttu-id="a70a8-112">Na caixa de diálogo **Conectar ao Analysis Services** , preencha as informações de conexão e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="a70a8-112">In the **Connect to Analysis Services** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="a70a8-113">Uma nova janela do editor de consulta é aberta, populada com o modelo **Descobrir Conjuntos de Linhas do Esquema** .</span><span class="sxs-lookup"><span data-stu-id="a70a8-113">A new query editor window opens, populated with the **Discover Schema Rowsets** template.</span></span>  
  
#### <a name="to-discover-column-names-from-the-mining-model-content-schema-rowset"></a><span data-ttu-id="a70a8-114">Para descobrir nomes de coluna do conjunto de linhas de esquema MINING MODEL CONTENT</span><span class="sxs-lookup"><span data-stu-id="a70a8-114">To discover column names from the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="a70a8-115">Com o modelo **Descobrir Conjuntos de Linhas do Esquema** aberto, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a70a8-115">With the **Discover Schema Rowsets** template open, click **Execute**.</span></span>  
  
     <span data-ttu-id="a70a8-116">Uma lista dos conjuntos de linha de esquema é retornada no painel **Resultados** que contém os nomes de todos os conjuntos de linhas disponíveis na instância atual.</span><span class="sxs-lookup"><span data-stu-id="a70a8-116">A list of schema rowsets is returned in the **Results** pane that contains the rowset names and rowset columns for all rowsets available on the current instance.</span></span>  
  
2.  <span data-ttu-id="a70a8-117">No painel de **consulta** , coloque o cursor depois **\<Restriction List>** e pressione ENTER para adicionar uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="a70a8-117">In the **Query** pane, place the cursor after **\<Restriction List>** and press ENTER to add a new line.</span></span>  
  
3.  <span data-ttu-id="a70a8-118">Coloque o cursor na linha em branco e digite \*\* \<SchemaName> DMSCHEMA_MINING_MODEL_CONTENT \</SchemaName> \*\*</span><span class="sxs-lookup"><span data-stu-id="a70a8-118">Place the cursor on the blank line and type **\<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT\</SchemaName>**</span></span>  
  
     <span data-ttu-id="a70a8-119">A seção completa de restrições deverá ser parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="a70a8-119">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT</SchemaName>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
4.  <span data-ttu-id="a70a8-120">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a70a8-120">Click **Execute**.</span></span>  
  
     <span data-ttu-id="a70a8-121">O painel **Resultados** mostra uma lista de nomes de colunas do conjunto de linhas do esquema especificado.</span><span class="sxs-lookup"><span data-stu-id="a70a8-121">The **Results** pane shows a list of column names for the specified schema rowset.</span></span>  
  
#### <a name="to-create-a-content-query-using-the-mining-model-content-schema-rowset"></a><span data-ttu-id="a70a8-122">Para criar uma consulta de conteúdo usando o conjunto de linhas do esquema de MINING MODEL CONTENT</span><span class="sxs-lookup"><span data-stu-id="a70a8-122">To create a content query using the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="a70a8-123">No modelo **Descobrir Conjuntos de Linhas do Esquema** , altere o tipo de solicitação substituindo o texto dentro das marcas de tipo de solicitação.</span><span class="sxs-lookup"><span data-stu-id="a70a8-123">In the **Discover Schema Rowsets** template, change the request type by replacing the text inside the request type tags.</span></span>  
  
     <span data-ttu-id="a70a8-124">Substitua esta linha:</span><span class="sxs-lookup"><span data-stu-id="a70a8-124">Replace this line:</span></span>  
  
     `<RequestType>DISCOVER_SCHEMA_ROWSETS</RequestType>`  
  
     <span data-ttu-id="a70a8-125">pela seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="a70a8-125">with the following line:</span></span>  
  
     <span data-ttu-id="a70a8-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span><span class="sxs-lookup"><span data-stu-id="a70a8-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span></span>  
  
2.  <span data-ttu-id="a70a8-127">Altere a lista de restrições para especificar um modelo de mineração pelo nome, adicionando uma nova condição às listas de restrições.</span><span class="sxs-lookup"><span data-stu-id="a70a8-127">Change the restriction list to specify a mining model by name, by adding a new condition to the restriction lists.</span></span>  
  
3.  <span data-ttu-id="a70a8-128">No modelo, coloque o cursor depois de `<Restriction List>` e pressione a ENTER para adicionar uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="a70a8-128">In the template, place the cursor after `<Restriction List>` and press ENTER to add a new line.</span></span>  
  
4.  <span data-ttu-id="a70a8-129">Coloque o cursor na linha em branco e digite **<MODEL_NAME>Nome do meu domínio</MODEL_NAME>**</span><span class="sxs-lookup"><span data-stu-id="a70a8-129">Place the cursor on the blank line and type **<MODEL_NAME>My model name</MODEL_NAME>**</span></span>  
  
     <span data-ttu-id="a70a8-130">A seção completa de restrições deverá ser parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="a70a8-130">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<MODEL_NAME>My model name</MODEL_NAME>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
5.  <span data-ttu-id="a70a8-131">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a70a8-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="a70a8-132">O painel Resultados exibe a definição de esquema, junto com os valores para o modelo especificado.</span><span class="sxs-lookup"><span data-stu-id="a70a8-132">The Results pane displays the schema definition, together with the values for the specified model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a70a8-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a70a8-133">See Also</span></span>  
 <span data-ttu-id="a70a8-134">[Conteúdo do modelo de mineração &#40;Analysis Services Mineração de dados&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a70a8-134">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="a70a8-135">Conjuntos de linhas de esquema de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="a70a8-135">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
