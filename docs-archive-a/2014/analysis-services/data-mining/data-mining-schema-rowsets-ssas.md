---
title: Consultando os conjuntos de linhas do esquema de mineração de dados (Analysis Services-Mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- schema rowsets [Analysis Services], data mining
- data mining [Analysis Services], queries
- mining model content
- data mining [Analysis Services], schema rowsets
- schema rowsets [Analysis Services], retrieving
- data mining [Analysis Services], troubleshooting
ms.assetid: 442d8c29-07c7-45de-9a15-d556059f68d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60c802256454ee68d04392e685fa4acabf6c12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581624"
---
# <a name="querying-the-data-mining-schema-rowsets-analysis-services---data-mining"></a><span data-ttu-id="89422-102">Consultando os conjuntos de linhas de esquema de mineração de dados (Analysis Services - Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="89422-102">Querying the Data Mining Schema Rowsets (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="89422-103">No [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], muitos dos conjuntos de linhas de esquema de mineração de dados OLE DB existentes foram expostos como um conjunto de tabelas do sistema que pode ser consultado usando as instruções DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="89422-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], many of the existing OLE DB data mining schema rowsets are exposed as a set of system tables that you can query by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="89422-104">Ao criar consultas no conjunto de linhas de esquema de mineração de dados, é possível identificar os serviços disponíveis, obter atualizações sobre o status de seus modelos e estruturas e localizar detalhes sobre o conteúdo ou os parâmetros do modelo.</span><span class="sxs-lookup"><span data-stu-id="89422-104">By creating queries against the data mining schema rowset, you can identify the services that are available, get updates on the status of your models and structures, and find out details about the model content or parameters.</span></span> <span data-ttu-id="89422-105">Para obter uma descrição dos conjuntos de linhas de esquema de mineração de dados, consulte [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="89422-105">For a description of the data mining schema rowsets, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89422-106">Você também pode consultar os conjuntos de linhas de esquema de mineração de dados usando o XMLA.</span><span class="sxs-lookup"><span data-stu-id="89422-106">You can also query the data mining schema rowsets by using XMLA.</span></span> <span data-ttu-id="89422-107">Para obter mais informações sobre como fazer isso no SQL Server Management Studio, consulte [Criar uma consulta de mineração de dados usando o XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="89422-107">For more information about how to do this in SQL Server Management Studio, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="list-of-data-mining-schema-rowsets"></a><span data-ttu-id="89422-108">Lista de conjuntos de linhas de esquema de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="89422-108">List of Data Mining Schema Rowsets</span></span>  
 <span data-ttu-id="89422-109">A tabela a seguir lista os conjuntos de linhas de esquema de mineração de dados que podem ser úteis para consultas e monitoramentos.</span><span class="sxs-lookup"><span data-stu-id="89422-109">The following table lists the data mining schema rowsets that may be useful for querying and monitoring.</span></span>  
  
|<span data-ttu-id="89422-110">Nome do conjunto de linhas</span><span class="sxs-lookup"><span data-stu-id="89422-110">Rowset name</span></span>|<span data-ttu-id="89422-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="89422-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="89422-112">DMSCHEMA_MINING_MODELS</span><span class="sxs-lookup"><span data-stu-id="89422-112">DMSCHEMA_MINING_MODELS</span></span>|<span data-ttu-id="89422-113">Lista todos os modelos de mineração no contexto atual.</span><span class="sxs-lookup"><span data-stu-id="89422-113">Lists all mining models in the current context.</span></span><br /><br /> <span data-ttu-id="89422-114">As informações incluem a data de criação, os parâmetros usados para criar o modelo e o tamanho do treinamento definido.</span><span class="sxs-lookup"><span data-stu-id="89422-114">Includes such information as the date created, parameters used to create the model, and the size of the training set.</span></span>|  
|<span data-ttu-id="89422-115">DMSCHEMA_MINING_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="89422-115">DMSCHEMA_MINING_COLUMNS</span></span>|<span data-ttu-id="89422-116">Lista todas as colunas usadas nos modelos de mineração no contexto atual.</span><span class="sxs-lookup"><span data-stu-id="89422-116">Lists all columns used in mining models in the current context.</span></span><br /><br /> <span data-ttu-id="89422-117">As informações incluem o mapeamento para a coluna de origem de estrutura de mineração, o tipo de dados, a precisão e as funções de previsão que podem ser usadas com a coluna.</span><span class="sxs-lookup"><span data-stu-id="89422-117">Information includes mapping to mining structure source column, data type, precision, and prediction functions that can be used with the column.</span></span>|  
|<span data-ttu-id="89422-118">DMSCHEMA_MINING_STRUCTURES</span><span class="sxs-lookup"><span data-stu-id="89422-118">DMSCHEMA_MINING_STRUCTURES</span></span>|<span data-ttu-id="89422-119">Lista toda a estrutura de mineração no contexto atual.</span><span class="sxs-lookup"><span data-stu-id="89422-119">Lists all mining structure in the current context.</span></span><br /><br /> <span data-ttu-id="89422-120">As informações incluem se a estrutura é populada, a data em que a estrutura foi processada e a definição do conjunto de dados validado para a estrutura, se houver.</span><span class="sxs-lookup"><span data-stu-id="89422-120">Information includes whether the structure is populated, the date the structure was last processed, and the definition of the holdout data set for the structure, if any.</span></span>|  
|<span data-ttu-id="89422-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="89422-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span></span>|<span data-ttu-id="89422-122">Lista todas as colunas usadas nas estruturas de mineração no contexto atual.</span><span class="sxs-lookup"><span data-stu-id="89422-122">Lists all columns used in mining structures in the current context.</span></span><br /><br /> <span data-ttu-id="89422-123">As informações incluem o tipo de conteúdo e de dados, a nulidade e se a coluna contém dados de tabela aninhados.</span><span class="sxs-lookup"><span data-stu-id="89422-123">Information includes content type and data type, nullability, and whether the column contains nested table data.</span></span>|  
|<span data-ttu-id="89422-124">DMSCHEMA_MINING_SERVICES</span><span class="sxs-lookup"><span data-stu-id="89422-124">DMSCHEMA_MINING_SERVICES</span></span>|<span data-ttu-id="89422-125">Lista todos os serviços de mineração, ou algoritmos, disponíveis no servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="89422-125">Lists all mining services, or algorithms, that are available on the specified server.</span></span><br /><br /> <span data-ttu-id="89422-126">As informações incluem os sinalizadores de modelagem com suporte, os tipos de entrada e os tipos de fonte de dados com suporte.</span><span class="sxs-lookup"><span data-stu-id="89422-126">Information includes supported modeling flags, input types, and supported data source types.</span></span>|  
|<span data-ttu-id="89422-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89422-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span></span>|<span data-ttu-id="89422-128">Lista todos os parâmetros para os serviços de mineração disponíveis na instância atual.</span><span class="sxs-lookup"><span data-stu-id="89422-128">Lists all parameters for the mining services that are available on the current instance.</span></span><br /><br /> <span data-ttu-id="89422-129">As informações incluem o tipo de dados para cada parâmetro, os valores padrão e os limites superiores e inferiores.</span><span class="sxs-lookup"><span data-stu-id="89422-129">Information includes the data type for each parameter, the default values, and the upper and lower limits.</span></span>|  
|<span data-ttu-id="89422-130">DMSCHEMA_MODEL_CONTENT</span><span class="sxs-lookup"><span data-stu-id="89422-130">DMSCHEMA_MODEL_CONTENT</span></span>|<span data-ttu-id="89422-131">Retorna o conteúdo do modelo, caso o modelo tenha sido processado.</span><span class="sxs-lookup"><span data-stu-id="89422-131">Returns the content of the model if the model has been processed.</span></span><br /><br /> <span data-ttu-id="89422-132">Para obter mais informações, consulte [Conteúdo do modelo de mineração &#40;Analysis Services – Mineração de dados&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="89422-132">For more information, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>|  
|<span data-ttu-id="89422-133">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="89422-133">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="89422-134">Lista todos os bancos de dados (catálogos) na instância atual do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="89422-134">Lists all databases (catalogs) in the current instance of Analysis Services.</span></span>|  
|<span data-ttu-id="89422-135">MDSCHEMA_INPUT_DATASOURCES</span><span class="sxs-lookup"><span data-stu-id="89422-135">MDSCHEMA_INPUT_DATASOURCES</span></span>|<span data-ttu-id="89422-136">Lista todas as fontes de dados na instância atual do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="89422-136">Lists all data sources in the current instance of Analysis Services.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="89422-137">A lista na tabela não é abrangente; ela mostra apenas os conjuntos de linhas que podem ser interessantes para solucionar os problemas.</span><span class="sxs-lookup"><span data-stu-id="89422-137">The list in the table is not comprehensive; it shows only those rowsets that may be of most interest for troubleshooting.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="89422-138">Exemplos</span><span class="sxs-lookup"><span data-stu-id="89422-138">Examples</span></span>  
 <span data-ttu-id="89422-139">A seção a seguir fornece alguns exemplos de consultas nos conjuntos de linhas de esquema de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="89422-139">The following section provides some examples of queries against the data mining schema rowsets.</span></span>  
  
### <a name="example-1-list-data-mining-services"></a><span data-ttu-id="89422-140">Exemplo 1: lista de serviços de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="89422-140">Example 1: List Data Mining Services</span></span>  
 <span data-ttu-id="89422-141">A consulta a seguir retorna uma lista dos serviços de mineração disponíveis no servidor atual, indicando que os algoritmos estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="89422-141">The following query returns a list of the mining services that are available on the current server, meaning the algorithms that are enabled.</span></span> <span data-ttu-id="89422-142">As colunas fornecidas para cada serviço de mineração incluem os sinalizadores de modelagem e os tipos de conteúdo que podem ser usados em cada algoritmo, o GUID para cada serviço e todos os limites de previsão que podem ter sido adicionados a cada serviço.</span><span class="sxs-lookup"><span data-stu-id="89422-142">The columns provided for each mining service include the modeling flags and content types that can be used by each algorithm, the GUID for each service, and any prediction limits that may have been added for each service.</span></span>  
  
```  
SELECT *  
FROM $system.DMSCHEMA_MINING_SERVICES  
```  
  
### <a name="example-2-list-mining-model-parameters"></a><span data-ttu-id="89422-143">Exemplo 2: lista de parâmetros de modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="89422-143">Example 2: List Mining Model Parameters</span></span>  
 <span data-ttu-id="89422-144">O exemplo a seguir retorna os parâmetros usados para criar um modelo de mineração específico:</span><span class="sxs-lookup"><span data-stu-id="89422-144">The following example returns the parameters that were used to create a specific mining model:</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
### <a name="example-3-list-all-rowsets"></a><span data-ttu-id="89422-145">Exemplo 3: lista de todos os conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="89422-145">Example 3: List All Rowsets</span></span>  
 <span data-ttu-id="89422-146">O exemplo a seguir retorna uma lista abrangente dos conjuntos de linhas disponíveis no servidor atual:</span><span class="sxs-lookup"><span data-stu-id="89422-146">The following example returns a comprehensive list of the rowsets that are available on the current server:</span></span>  
  
```  
SELECT *   
FROM $system.DBSCHEMA_TABLES  
```  
  
## <a name="see-also"></a><span data-ttu-id="89422-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="89422-147">See Also</span></span>  
 [<span data-ttu-id="89422-148">Conceitos da solução de problemas (Analysis Services - Mineração de Dados)</span><span class="sxs-lookup"><span data-stu-id="89422-148">Troubleshooting Concepts (Analysis Services - Data Mining)</span></span>](https://msdn.microsoft.com/library/cc645881.aspx)  
  
  
