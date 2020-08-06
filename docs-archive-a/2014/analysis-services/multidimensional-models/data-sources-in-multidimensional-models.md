---
title: Fontes de dados em modelos multidimensionais | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- metadata [Analysis Services]
- Analysis Services objects, data sources
- storing data [Analysis Services], data sources
- data sources [Analysis Services], about data sources
- security [Analysis Services], data sources
- data sources [Analysis Services]
- storage [Analysis Services], data sources
ms.assetid: a16469d9-9d53-4e35-9982-fc06327a9d33
author: minewiskan
ms.author: owend
ms.openlocfilehash: 41386c1c7abb0324aa17df24b3c427ca8cbb5615
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582174"
---
# <a name="data-sources-in-multidimensional-models"></a><span data-ttu-id="c43ac-102">Fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="c43ac-102">Data Sources in Multidimensional Models</span></span>
  <span data-ttu-id="c43ac-103">Todos os dados que você importa ou carrega em um modelo multidimensional são originados de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="c43ac-103">All data that you import or load into a multidimensional model originates from an external data source.</span></span> <span data-ttu-id="c43ac-104">Normalmente, os dados de origem são de um data warehouse criado para fins de geração de relatórios, mas poderiam vir de qualquer banco de dados relacional que seja acessado diretamente ou indiretamente por um intermediário, como um pacote do [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c43ac-104">Typically, source data is from a data warehouse designed for reporting purposes, but it could come from any relational database that is accessed directly or indirectly through an intermediary, such as an [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span>  
  
 <span data-ttu-id="c43ac-105">Um objeto de **fonte de dados** no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] especifica uma conexão direta com uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="c43ac-105">A **data source** object in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] specifies a direct connection to an external data source.</span></span> <span data-ttu-id="c43ac-106">Além do local físico, um objeto de fonte de dados especifica a cadeia de conexão, o provedor de dados, as credenciais e outras propriedades que controlam o comportamento da conexão.</span><span class="sxs-lookup"><span data-stu-id="c43ac-106">In addition to physical location, a data source object specifies the connection string, data provider, credentials, and other properties that control connection behavior.</span></span>  
  
 <span data-ttu-id="c43ac-107">As informações fornecidas pelo objeto de fonte de dados são usadas durante as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="c43ac-107">Information provided by the data source object is used during the following operations:</span></span>  
  
-   <span data-ttu-id="c43ac-108">Obter informações de esquema e outros metadados usados para gerar exibições de fontes de dados em um modelo.</span><span class="sxs-lookup"><span data-stu-id="c43ac-108">Get schema information and other metadata used to generate data source views into a model.</span></span>  
  
-   <span data-ttu-id="c43ac-109">Consultar ou carregar dados em um modelo durante o processamento.</span><span class="sxs-lookup"><span data-stu-id="c43ac-109">Query or load data into a model during processing.</span></span>  
  
-   <span data-ttu-id="c43ac-110">Executar as consultas em modelos multidimensionais ou de mineração de dados que usam o modo de armazenamento ROLAP</span><span class="sxs-lookup"><span data-stu-id="c43ac-110">Run queries against multidimensional or data mining models that use ROLAP storage mode.</span></span>  
  
-   <span data-ttu-id="c43ac-111">Ler ou gravar em partições remotas.</span><span class="sxs-lookup"><span data-stu-id="c43ac-111">Read or write to remote partitions.</span></span>  
  
-   <span data-ttu-id="c43ac-112">Conectar a objetos vinculados, assim como sincronizar do destino para a origem.</span><span class="sxs-lookup"><span data-stu-id="c43ac-112">Connect to linked objects, as well as synchronize from target to source.</span></span>  
  
-   <span data-ttu-id="c43ac-113">Executar operações de write-back que atualizam dados de tabela de fatos armazenadas em um banco de dados relacional.</span><span class="sxs-lookup"><span data-stu-id="c43ac-113">Perform write back operations that update fact table data stored in a relational database.</span></span>  
  
 <span data-ttu-id="c43ac-114">Ao construir um modelo multidimensional debaixo pra cima, você inicia criando o objeto de fonte de dados e, em seguida, usa-o para gerar o próximo objeto, uma **exibição da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="c43ac-114">When building a multidimensional model from the bottom up, you start by creating the data source object, and then use it to generate the next object, a **data source view**.</span></span> <span data-ttu-id="c43ac-115">Uma exibição da fonte de dados é a camada de abstração de dados no modelo.</span><span class="sxs-lookup"><span data-stu-id="c43ac-115">A data source view is the data abstraction layer in the model.</span></span> <span data-ttu-id="c43ac-116">Ela é criada normalmente depois do objeto de fonte de dados, usando o esquema do banco de dados de origem como a base.</span><span class="sxs-lookup"><span data-stu-id="c43ac-116">It is typically created after the data source object, using the schema of the source database as the basis.</span></span> <span data-ttu-id="c43ac-117">No entanto, você pode escolher outros modos de criar um modelo, inclusive iniciar com cubos e dimensões, e gerando o esquema que melhor dê suporte ao seu design.</span><span class="sxs-lookup"><span data-stu-id="c43ac-117">However, you can choose other ways to build a model, including starting with cubes and dimensions, and generating the schema that best supports your design.</span></span>  
  
 <span data-ttu-id="c43ac-118">Independentemente de como você crie isto, cada modelo exige pelo menos um objeto de fonte de dados que especifica uma conexão com os dados de origem.</span><span class="sxs-lookup"><span data-stu-id="c43ac-118">Regardless of how you build it, each model requires at least one data source object that specifies a connection to source data.</span></span> <span data-ttu-id="c43ac-119">Você pode criar vários objetos de fonte de dados em um único modelo para usar dados de origens diferentes ou variar as propriedades de conexão para objetos específicos.</span><span class="sxs-lookup"><span data-stu-id="c43ac-119">You can create multiple data source objects in a single model to use data from different sources or vary connection properties for specific objects.</span></span>  
  
 <span data-ttu-id="c43ac-120">Os objetos de fonte de dados podem ser gerenciados independentemente de outros objetos em seu modelo.</span><span class="sxs-lookup"><span data-stu-id="c43ac-120">Data source objects can be managed independently of other objects in your model.</span></span> <span data-ttu-id="c43ac-121">Depois que você criar uma fonte de dados, pode alterar suas propriedades posteriormente e, em seguida, pré-processar o modelo para assegurar que os dados sejam recuperados corretamente.</span><span class="sxs-lookup"><span data-stu-id="c43ac-121">After you create a data source, you can change its properties later, and then preprocess the model to ensure the data is retrieved correctly.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="c43ac-122">Tópicos relacionados e tarefas</span><span class="sxs-lookup"><span data-stu-id="c43ac-122">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="c43ac-123">Tópico</span><span class="sxs-lookup"><span data-stu-id="c43ac-123">Topic</span></span>|<span data-ttu-id="c43ac-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="c43ac-124">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c43ac-125">Fontes de dados com suporte &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="c43ac-125">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)|<span data-ttu-id="c43ac-126">Descreve os tipos de fonte de dados que podem ser usados em um modelo multidimensional.</span><span class="sxs-lookup"><span data-stu-id="c43ac-126">Describes the types of data sources that can be used in a multidimensional model.</span></span>|  
|[<span data-ttu-id="c43ac-127">Criar uma fonte de dados &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="c43ac-127">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](create-a-data-source-ssas-multidimensional.md)|<span data-ttu-id="c43ac-128">Explica como adicionar um objeto de fonte de dados a um modelo multidimensional.</span><span class="sxs-lookup"><span data-stu-id="c43ac-128">Explains how to add a data source object to a multidimensional model.</span></span>|  
|[<span data-ttu-id="c43ac-129">Excluir uma exibição da fonte de dados no gerenciador de soluções &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="c43ac-129">Delete a Data Source in Solution Explorer &#40;SSAS Multidimensional&#41;</span></span>](delete-a-data-source-in-solution-explorer-ssas-multidimensional.md)|<span data-ttu-id="c43ac-130">Use este procedimento para excluir um objeto de fonte de dados de um modelo multidimensional.</span><span class="sxs-lookup"><span data-stu-id="c43ac-130">Use this procedure to delete a data source object from a multidimensional model.</span></span>|  
|[<span data-ttu-id="c43ac-131">Definir propriedades da fonte de dados &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="c43ac-131">Set Data Source Properties &#40;SSAS Multidimensional&#41;</span></span>](set-data-source-properties-ssas-multidimensional.md)|<span data-ttu-id="c43ac-132">Descreve cada propriedade e explica como definir cada uma.</span><span class="sxs-lookup"><span data-stu-id="c43ac-132">Describes each property and explains how to set each one.</span></span>|  
|[<span data-ttu-id="c43ac-133">Definir opções de representação &#40;SSAS – Multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="c43ac-133">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](set-impersonation-options-ssas-multidimensional.md)|<span data-ttu-id="c43ac-134">Explica como configurar as opções na caixa de diálogo de Informações sobre Representação.</span><span class="sxs-lookup"><span data-stu-id="c43ac-134">Explains how to configure options in the Impersonation Information dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c43ac-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c43ac-135">See Also</span></span>  
 <span data-ttu-id="c43ac-136">[Objetos de banco de dados &#40;Analysis Services-&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="c43ac-136">[Database Objects &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="c43ac-137">[Arquitetura lógica &#40;Analysis Services de dados multidimensionais&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="c43ac-137">[Logical Architecture &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span></span>  
 <span data-ttu-id="c43ac-138">[Exibições da fonte de dados em modelos multidimensionais](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="c43ac-138">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="c43ac-139">Fontes de dados e associações &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="c43ac-139">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](data-sources-and-bindings-ssas-multidimensional.md)  
  
  
