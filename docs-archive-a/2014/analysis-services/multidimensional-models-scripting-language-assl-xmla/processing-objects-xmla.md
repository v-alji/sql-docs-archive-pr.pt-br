---
title: Objetos de processamento (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- objects [XML for Analysis]
- XML for Analysis, objects
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
- writeback [Analysis Services], XML for Analysis
- out-of-line bindings
- processing objects [XML for Analysis]
- XMLA, objects
ms.assetid: a65b3249-303d-49c6-98af-6ac6eed11a03
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e59c7953ae8fc7d3cfceafa7b0e9d8c7186daf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684399"
---
# <a name="processing-objects-xmla"></a><span data-ttu-id="a04fa-102">Processando objetos (XMLA)</span><span class="sxs-lookup"><span data-stu-id="a04fa-102">Processing Objects (XMLA)</span></span>
  <span data-ttu-id="a04fa-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , o processamento é a etapa ou série de etapas que transforma dados em informações para análise de negócios.</span><span class="sxs-lookup"><span data-stu-id="a04fa-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], processing is the step or series of steps that turn data into information for business analysis.</span></span> <span data-ttu-id="a04fa-104">O processamento será diferente dependendo do tipo de objeto, mas sempre fará parte da transformação de dados em informações.</span><span class="sxs-lookup"><span data-stu-id="a04fa-104">Processing is different depending on the type of object, but processing is always part of turning data into information.</span></span>  
  
 <span data-ttu-id="a04fa-105">Para processar um [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objeto, você pode usar o comando [process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="a04fa-105">To process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object, you can use the [Process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) command.</span></span> <span data-ttu-id="a04fa-106">O comando `Process` pode processar os seguintes objetos de uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a04fa-106">The `Process` command can process the following objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance:</span></span>  
  
-   <span data-ttu-id="a04fa-107">Cubes</span><span class="sxs-lookup"><span data-stu-id="a04fa-107">Cubes</span></span>  
  
-   <span data-ttu-id="a04fa-108">Bancos de dados</span><span class="sxs-lookup"><span data-stu-id="a04fa-108">Databases</span></span>  
  
-   <span data-ttu-id="a04fa-109">Dimensões</span><span class="sxs-lookup"><span data-stu-id="a04fa-109">Dimensions</span></span>  
  
-   <span data-ttu-id="a04fa-110">Grupos de medidas</span><span class="sxs-lookup"><span data-stu-id="a04fa-110">Measure groups</span></span>  
  
-   <span data-ttu-id="a04fa-111">Modelos de mineração</span><span class="sxs-lookup"><span data-stu-id="a04fa-111">Mining models</span></span>  
  
-   <span data-ttu-id="a04fa-112">Estruturas de mineração</span><span class="sxs-lookup"><span data-stu-id="a04fa-112">Mining structures</span></span>  
  
-   <span data-ttu-id="a04fa-113">Partições</span><span class="sxs-lookup"><span data-stu-id="a04fa-113">Partitions</span></span>  
  
 <span data-ttu-id="a04fa-114">Para controlar o processamento de objetos, o comando `Process` tem várias propriedades que podem ser definidas.</span><span class="sxs-lookup"><span data-stu-id="a04fa-114">To control the processing of objects, the `Process` command has various properties that can be set.</span></span> <span data-ttu-id="a04fa-115">O comando `Process` tem propriedades que controlam: quanto processamento será feito, que objetos serão processados, se as associações fora de linha serão usadas, como manipular erros e como gerenciar tabelas de write-back.</span><span class="sxs-lookup"><span data-stu-id="a04fa-115">The `Process` command has properties that control: how much processing will be done, which objects will be processed, whether to use out-of-line bindings, how to handle errors, and how to manage writeback tables.</span></span>  
  
## <a name="specifying-processing-options"></a><span data-ttu-id="a04fa-116">Especificando opções de processamento</span><span class="sxs-lookup"><span data-stu-id="a04fa-116">Specifying Processing Options</span></span>  
 <span data-ttu-id="a04fa-117">A propriedade [Type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) do `Process` comando especifica a opção de processamento a ser usada ao processar o objeto.</span><span class="sxs-lookup"><span data-stu-id="a04fa-117">The [Type](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) property of the `Process` command specifies the processing option to use when processing the object.</span></span> <span data-ttu-id="a04fa-118">Para obter mais informações sobre as opções de processamento, consulte [Opções e configurações de processamento &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="a04fa-118">For more information about processing options, see [Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md).</span></span>  
  
 <span data-ttu-id="a04fa-119">A tabela a seguir lista as constantes para a propriedade `Type` e os vários objetos que podem ser processados usando cada constante.</span><span class="sxs-lookup"><span data-stu-id="a04fa-119">The following table lists the constants for the `Type` property and the various objects that can be processed using each constant.</span></span>  
  
|<span data-ttu-id="a04fa-120">`Type` valor</span><span class="sxs-lookup"><span data-stu-id="a04fa-120">`Type` value</span></span>|<span data-ttu-id="a04fa-121">Objetos aplicáveis</span><span class="sxs-lookup"><span data-stu-id="a04fa-121">Applicable objects</span></span>|  
|--------------------|------------------------|  
|<span data-ttu-id="a04fa-122">*ProcessFull*</span><span class="sxs-lookup"><span data-stu-id="a04fa-122">*ProcessFull*</span></span>|<span data-ttu-id="a04fa-123">Cubo, banco de dados, dimensão, grupo de medidas, modelo de mineração, estrutura de mineração, partição</span><span class="sxs-lookup"><span data-stu-id="a04fa-123">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="a04fa-124">*ProcessAdd*</span><span class="sxs-lookup"><span data-stu-id="a04fa-124">*ProcessAdd*</span></span>|<span data-ttu-id="a04fa-125">Dimensão, partição</span><span class="sxs-lookup"><span data-stu-id="a04fa-125">Dimension, partition</span></span>|  
|<span data-ttu-id="a04fa-126">*ProcessUpdate*</span><span class="sxs-lookup"><span data-stu-id="a04fa-126">*ProcessUpdate*</span></span>|<span data-ttu-id="a04fa-127">Dimensão</span><span class="sxs-lookup"><span data-stu-id="a04fa-127">Dimension</span></span>|  
|<span data-ttu-id="a04fa-128">*ProcessIndexes*</span><span class="sxs-lookup"><span data-stu-id="a04fa-128">*ProcessIndexes*</span></span>|<span data-ttu-id="a04fa-129">Dimensão, cubo, grupo de medidas, partição</span><span class="sxs-lookup"><span data-stu-id="a04fa-129">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="a04fa-130">*ProcessData*</span><span class="sxs-lookup"><span data-stu-id="a04fa-130">*ProcessData*</span></span>|<span data-ttu-id="a04fa-131">Dimensão, cubo, grupo de medidas, partição</span><span class="sxs-lookup"><span data-stu-id="a04fa-131">Dimension, cube, measure group, partition</span></span>|  
|<span data-ttu-id="a04fa-132">*ProcessDefault*</span><span class="sxs-lookup"><span data-stu-id="a04fa-132">*ProcessDefault*</span></span>|<span data-ttu-id="a04fa-133">Cubo, banco de dados, dimensão, grupo de medidas, modelo de mineração, estrutura de mineração, partição</span><span class="sxs-lookup"><span data-stu-id="a04fa-133">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="a04fa-134">*ProcessClear*</span><span class="sxs-lookup"><span data-stu-id="a04fa-134">*ProcessClear*</span></span>|<span data-ttu-id="a04fa-135">Cubo, banco de dados, dimensão, grupo de medidas, modelo de mineração, estrutura de mineração, partição</span><span class="sxs-lookup"><span data-stu-id="a04fa-135">Cube, database, dimension, measure group, mining model, mining structure, partition</span></span>|  
|<span data-ttu-id="a04fa-136">*ProcessStructure*</span><span class="sxs-lookup"><span data-stu-id="a04fa-136">*ProcessStructure*</span></span>|<span data-ttu-id="a04fa-137">Cubo, estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="a04fa-137">Cube, mining structure</span></span>|  
|<span data-ttu-id="a04fa-138">*ProcessClearStructureOnly*</span><span class="sxs-lookup"><span data-stu-id="a04fa-138">*ProcessClearStructureOnly*</span></span>|<span data-ttu-id="a04fa-139">Estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="a04fa-139">Mining structure</span></span>|  
|<span data-ttu-id="a04fa-140">*ProcessScriptCache*</span><span class="sxs-lookup"><span data-stu-id="a04fa-140">*ProcessScriptCache*</span></span>|<span data-ttu-id="a04fa-141">Cubo</span><span class="sxs-lookup"><span data-stu-id="a04fa-141">Cube</span></span>|  
  
 <span data-ttu-id="a04fa-142">Para obter mais informações sobre o processamento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objetos, consulte [processamento de objeto de modelo multidimensional](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="a04fa-142">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
## <a name="specifying-objects-to-be-processed"></a><span data-ttu-id="a04fa-143">Especificando objetos a serem processados</span><span class="sxs-lookup"><span data-stu-id="a04fa-143">Specifying Objects to be Processed</span></span>  
 <span data-ttu-id="a04fa-144">A propriedade [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) do `Process` comando contém o identificador de objeto do objeto a ser processado.</span><span class="sxs-lookup"><span data-stu-id="a04fa-144">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Process` command contains the object identifier of the object to be processed.</span></span> <span data-ttu-id="a04fa-145">Somente um objeto pode ser especificado em um comando `Process`, mas processar um objeto também processará qualquer objeto filho.</span><span class="sxs-lookup"><span data-stu-id="a04fa-145">Only one object can be specified in a `Process` command, but processing an object also processes any child objects.</span></span> <span data-ttu-id="a04fa-146">Por exemplo, o processamento de um grupo de medidas em um cubo processará todas as partições desse grupo de medidas, enquanto que o processamento de um banco de dados processará todos os objetos, incluindo cubos, dimensões e estruturas de mineração, contidos nele.</span><span class="sxs-lookup"><span data-stu-id="a04fa-146">For example, processing a measure group in a cube processes all the partitions for that measure group, while processing a database processes all the objects, including cubes, dimensions, and mining structures, that are contained by the database.</span></span>  
  
 <span data-ttu-id="a04fa-147">Se você definir o atributo `ProcessAffectedObjects` do comando `Process` como verdadeiro, qualquer objeto relacionado afetado pelo processamento do objeto especificado também será processado.</span><span class="sxs-lookup"><span data-stu-id="a04fa-147">If you set the `ProcessAffectedObjects` attribute of the `Process` command to true, any related object affected by processing the specified object is also processed.</span></span> <span data-ttu-id="a04fa-148">Por exemplo, se uma dimensão é atualizada incrementalmente usando a opção de processamento *ProcessUpdate* no `Process` comando, qualquer partição cujas agregações são invalidadas devido aos membros sendo adicionados ou excluídos também são processados pelo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] If `ProcessAffectedObjects` é definido como true.</span><span class="sxs-lookup"><span data-stu-id="a04fa-148">For example, if a dimension is incrementally updated by using the *ProcessUpdate* processing option in the `Process` command, any partition whose aggregations are invalidated because of members being added or deleted is also processed by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] if `ProcessAffectedObjects` is set to true.</span></span> <span data-ttu-id="a04fa-149">Nesse caso, um único comando `Process` pode processar vários objetos de uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], mas o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] determinará que objetos, além do objeto único especificado no comando `Process`, também serão processados.</span><span class="sxs-lookup"><span data-stu-id="a04fa-149">In this case, a single `Process` command can process multiple objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, but [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] determines which objects besides the single object specified in the `Process` command must also be processed.</span></span>  
  
 <span data-ttu-id="a04fa-150">Porém, você pode processar vários objetos, como as dimensões, ao mesmo tempo usando vários comandos `Process` dentro de um comando `Batch`.</span><span class="sxs-lookup"><span data-stu-id="a04fa-150">However, you can process multiple objects, such as dimensions, at the same time by using multiple `Process` commands within a `Batch` command.</span></span> <span data-ttu-id="a04fa-151">As operações em lotes oferece um nível mais refinado de controle para o processamento em série ou em paralelo de objetos em uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do que a utilização do atributo `ProcessAffectedObjects`, além de permitir que você ajuste a sua abordagem de processamento para bancos de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] maiores.</span><span class="sxs-lookup"><span data-stu-id="a04fa-151">Batch operations provide a finer level of control for serial or parallel processing of objects on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance than using the `ProcessAffectedObjects` attribute, and let you to tune your processing approach for larger [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases.</span></span> <span data-ttu-id="a04fa-152">Para obter mais informações sobre como executar operações em lote, consulte [executando operações em lote &#40;XMLA&#41;](performing-batch-operations-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="a04fa-152">For more information about performing batch operations, see [Performing Batch Operations &#40;XMLA&#41;](performing-batch-operations-xmla.md).</span></span>  
  
## <a name="specifying-out-of-line-bindings"></a><span data-ttu-id="a04fa-153">Especificando associações fora de linha</span><span class="sxs-lookup"><span data-stu-id="a04fa-153">Specifying Out-of-Line Bindings</span></span>  
 <span data-ttu-id="a04fa-154">Se o `Process` comando não estiver contido em um `Batch` comando, você pode opcionalmente especificar associações fora de linha nas propriedades [bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla)e [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) do `Process` comando para os objetos a serem processados.</span><span class="sxs-lookup"><span data-stu-id="a04fa-154">If the `Process` command is not contained by a `Batch` command, you can optionally specify out-of-line bindings in the [Bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla), [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla), and [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) properties of the `Process` command for the objects to be processed.</span></span> <span data-ttu-id="a04fa-155">As associações fora de linha são referências a fontes de dados, exibições de fonte de dados e outros objetos nos quais a associação só existe durante a execução do comando `Process` e que substitui qualquer associação associada aos objetos processados.</span><span class="sxs-lookup"><span data-stu-id="a04fa-155">Out-of-line bindings are references to data sources, data source views, and other objects in which the binding exists only during the execution of the `Process` command, and which override any existing bindings associated with the objects being processed.</span></span> <span data-ttu-id="a04fa-156">Se associações fora de linha não forem especificadas, serão usadas as associações atualmente associadas aos objetos a serem processados.</span><span class="sxs-lookup"><span data-stu-id="a04fa-156">If out-of-line bindings are not specified, the bindings currently associated with the objects to be processed are used.</span></span>  
  
 <span data-ttu-id="a04fa-157">As associações fora de linha são usadas nas seguintes circunstâncias:</span><span class="sxs-lookup"><span data-stu-id="a04fa-157">Out-of-line bindings are used in the following circumstances:</span></span>  
  
-   <span data-ttu-id="a04fa-158">No processamento incremental de uma partição, no qual uma tabela de fatos alternativa ou um filtro da tabela de fatos existente deve ser especificado para garantir que as linhas não sejam contadas duas vezes.</span><span class="sxs-lookup"><span data-stu-id="a04fa-158">Incrementally processing a partition, in which an alternative fact table or a filter on the existing fact table must be specified to make sure that rows are not counted twice.</span></span>  
  
-   <span data-ttu-id="a04fa-159">Usar uma tarefa de fluxo de dados no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para fornecer dados durante o processamento de uma dimensão, um modelo de mineração ou uma partição.</span><span class="sxs-lookup"><span data-stu-id="a04fa-159">Using a data flow task in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to provide data while processing a dimension, mining model, or partition.</span></span>  
  
 <span data-ttu-id="a04fa-160">As associações fora de linha são descritas como parte da ASSL (Analysis Services Scripting Language).</span><span class="sxs-lookup"><span data-stu-id="a04fa-160">Out-of-line bindings are described as part of the Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="a04fa-161">Para obter mais informações sobre associações fora de linha no ASSL, consulte [fontes de dados e associações &#40;&#41;multidimensional do SSAS ](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="a04fa-161">For more information about out-of-line bindings in ASSL, see [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).</span></span>  
  
### <a name="incrementally-updating-partitions"></a><span data-ttu-id="a04fa-162">Atualizando partições incrementalmente</span><span class="sxs-lookup"><span data-stu-id="a04fa-162">Incrementally Updating Partitions</span></span>  
 <span data-ttu-id="a04fa-163">Atualizar incrementalmente uma partição já processada normalmente exige uma associação fora de linha, já que a associação especificada para a partição faz referência aos dados da tabela de fatos já agregados na partição.</span><span class="sxs-lookup"><span data-stu-id="a04fa-163">Incrementally updating an already processed partition typically requires an out-of-line binding because the binding specified for the partition references fact table data already aggregated within the partition.</span></span> <span data-ttu-id="a04fa-164">Ao atualizar incrementalmente uma partição já processada por meio do comando `Process`, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] executa as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="a04fa-164">When incrementally updating an already processed partition by using the `Process` command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] performs the following actions:</span></span>  
  
-   <span data-ttu-id="a04fa-165">Cria uma partição temporária com uma estrutura idêntica à da partição a ser atualizada incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="a04fa-165">Creates a temporary partition with a structure identical to that of the partition to be incrementally updated.</span></span>  
  
-   <span data-ttu-id="a04fa-166">Processa a partição temporária, usando a associação fora de linha especificada no comando `Process`.</span><span class="sxs-lookup"><span data-stu-id="a04fa-166">Processes the temporary partition, using the out-of-line binding specified in the `Process` command.</span></span>  
  
-   <span data-ttu-id="a04fa-167">Mescla a partição temporária com a partição selecionada existente.</span><span class="sxs-lookup"><span data-stu-id="a04fa-167">Merges the temporary partition with the existing selected partition.</span></span>  
  
 <span data-ttu-id="a04fa-168">Para obter mais informações sobre como mesclar partições usando XML for Analysis (XMLA), consulte [mesclando partições &#40;xmla&#41;](merging-partitions-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="a04fa-168">For more information about merging partitions using XML for Analysis (XMLA), see [Merging Partitions &#40;XMLA&#41;](merging-partitions-xmla.md).</span></span>  
  
## <a name="handling-processing-errors"></a><span data-ttu-id="a04fa-169">Manipulando erros de processamento</span><span class="sxs-lookup"><span data-stu-id="a04fa-169">Handling Processing Errors</span></span>  
 <span data-ttu-id="a04fa-170">A propriedade [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) do `Process` comando permite que você especifique como tratar os erros encontrados durante o processamento de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a04fa-170">The [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) property of the `Process` command lets you specify how to handle errors encountered while processing an object.</span></span> <span data-ttu-id="a04fa-171">Por exemplo, durante o processamento de uma dimensão, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encontra um valor duplicado na coluna de chave do atributo de chave.</span><span class="sxs-lookup"><span data-stu-id="a04fa-171">For example, while processing a dimension, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encounters a duplicate value in the key column of the key attribute.</span></span> <span data-ttu-id="a04fa-172">Como as chaves de atributo devem ser exclusivas, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] descarta os registros duplicados.</span><span class="sxs-lookup"><span data-stu-id="a04fa-172">Because attribute keys must be unique, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] discards the duplicate records.</span></span> <span data-ttu-id="a04fa-173">Com base na propriedade [KeyDuplicate](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) do `ErrorConfiguration` , o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] poderia:</span><span class="sxs-lookup"><span data-stu-id="a04fa-173">Based on the [KeyDuplicate](https://docs.microsoft.com/bi-reference/assl/properties/keyduplicate-element-assl) property of `ErrorConfiguration`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] could:</span></span>  
  
-   <span data-ttu-id="a04fa-174">Ignorar o erro e continuar o processamento da dimensão.</span><span class="sxs-lookup"><span data-stu-id="a04fa-174">Ignore the error and continue processing the dimension.</span></span>  
  
-   <span data-ttu-id="a04fa-175">Retornar uma mensagem declarando que o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encontrou uma chave duplicada e continuar o processamento.</span><span class="sxs-lookup"><span data-stu-id="a04fa-175">Return a message that states [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] encountered a duplicate key and continue processing.</span></span>  
  
 <span data-ttu-id="a04fa-176">Existem muitas condições semelhantes para as quais `ErrorConfiguration` oferece opções durante um comando `Process`.</span><span class="sxs-lookup"><span data-stu-id="a04fa-176">There are many similar conditions for which `ErrorConfiguration` provides options during a `Process` command.</span></span>  
  
## <a name="managing-writeback-tables"></a><span data-ttu-id="a04fa-177">Gerenciando tabelas de write-back</span><span class="sxs-lookup"><span data-stu-id="a04fa-177">Managing Writeback Tables</span></span>  
 <span data-ttu-id="a04fa-178">Se o comando `Process` encontrar uma partição de write-back, ou um cubo ou um grupo de medidas para essa partição, ela não será totalmente processada, pois pode ainda não haver uma tabela de write-back para ela.</span><span class="sxs-lookup"><span data-stu-id="a04fa-178">If the `Process` command encounters a write-enabled partition, or a cube or measure group for such a partition, that is not already fully processed, a writeback table may not already exist for that partition.</span></span> <span data-ttu-id="a04fa-179">A propriedade [WriteBackTableCreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) do `Process` comando determina se o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deve criar uma tabela de write-back.</span><span class="sxs-lookup"><span data-stu-id="a04fa-179">The [WritebackTableCreation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/writebacktablecreation-element-xmla) property of the `Process` command determines whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should create a writeback table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a04fa-180">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a04fa-180">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="a04fa-181">Descrição</span><span class="sxs-lookup"><span data-stu-id="a04fa-181">Description</span></span>  
 <span data-ttu-id="a04fa-182">O exemplo a seguir processa totalmente o banco de dados [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] de exemplo do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a04fa-182">The following example fully processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a04fa-183">Código</span><span class="sxs-lookup"><span data-stu-id="a04fa-183">Code</span></span>  
  
```  
<Process xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
  </Object>  
  <Type>ProcessFull</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
### <a name="description"></a><span data-ttu-id="a04fa-184">Descrição</span><span class="sxs-lookup"><span data-stu-id="a04fa-184">Description</span></span>  
 <span data-ttu-id="a04fa-185">O exemplo a seguir processa incrementalmente a partição de **Internet_Sales_2004** no grupo de medidas **vendas pela Internet** do cubo do **Adventure Works DW** no [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] banco de dados de exemplo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a04fa-185">The following example incrementally processes the **Internet_Sales_2004** partition in the **Internet Sales** measure group of the **Adventure Works DW** cube in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="a04fa-186">O `Process` comando está adicionando agregações para datas de pedido posteriores a 31 de dezembro de 2006 para a partição usando uma associação de consulta fora de linha na `Bindings` Propriedade do `Process` comando para recuperar as linhas da tabela de fatos das quais gerar agregações para adicionar à partição.</span><span class="sxs-lookup"><span data-stu-id="a04fa-186">The `Process` command is adding aggregations for order dates later than December 31, 2006 to the partition by using an out-of-line query binding in the `Bindings` property of the `Process` command to retrieve the fact table rows from which to generate aggregations to add to the partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a04fa-187">Código</span><span class="sxs-lookup"><span data-stu-id="a04fa-187">Code</span></span>  
  
```  
<Process ProcessAffectedObjects="true" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Object>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2006</PartitionID>  
  </Object>  
  <Bindings>  
    <Binding>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2006</PartitionID>  
      <Source xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="QueryBinding">  
        <DataSourceID>Adventure Works DW</DataSourceID>  
        <QueryDefinition>  
          SELECT  
            [dbo].[FactInternetSales].[ProductKey],  
            [dbo].[FactInternetSales].[OrderDateKey],  
            [dbo].[FactInternetSales].[DueDateKey],  
            [dbo].[FactInternetSales].[ShipDateKey],   
            [dbo].[FactInternetSales].[CustomerKey],   
            [dbo].[FactInternetSales].[PromotionKey],  
            [dbo].[FactInternetSales].[CurrencyKey],  
            [dbo].[FactInternetSales].[SalesTerritoryKey],  
            [dbo].[FactInternetSales].[SalesOrderNumber],  
            [dbo].[FactInternetSales].[SalesOrderLineNumber],  
            [dbo].[FactInternetSales].[RevisionNumber],  
            [dbo].[FactInternetSales].[OrderQuantity],  
            [dbo].[FactInternetSales].[UnitPrice],  
            [dbo].[FactInternetSales].[ExtendedAmount],  
            [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
            [dbo].[FactInternetSales].[DiscountAmount],  
            [dbo].[FactInternetSales].[ProductStandardCost],  
            [dbo].[FactInternetSales].[TotalProductCost],  
            [dbo].[FactInternetSales].[SalesAmount],  
            [dbo].[FactInternetSales].[TaxAmt],  
            [dbo].[FactInternetSales].[Freight],  
            [dbo].[FactInternetSales].[CarrierTrackingNumber],  
            [dbo].[FactInternetSales].[CustomerPONumber]  
          FROM [dbo].[FactInternetSales]  
          WHERE OrderDateKey > '1280'  
        </QueryDefinition>  
      </Source>  
    </Binding>  
  </Bindings>  
  <Type>ProcessAdd</Type>  
  <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
</Process>  
```  
  
  
