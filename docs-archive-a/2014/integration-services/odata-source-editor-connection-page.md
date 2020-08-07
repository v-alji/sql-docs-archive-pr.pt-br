---
title: Editor de origem OData (página conexão) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- Sql12.dts.designer.odatasource.connection.f1
ms.assetid: 20bcd347-4547-4fad-b182-9571030101df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ecd0d060ea2197ae7174325b654645fefa23505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575205"
---
# <a name="odata-source-editor-connection-page"></a><span data-ttu-id="daeda-102">Editor de Origem do OData (página Conexão)</span><span class="sxs-lookup"><span data-stu-id="daeda-102">OData Source Editor (Connection Page)</span></span>
  <span data-ttu-id="daeda-103">Use a página **Conexão** da caixa de diálogo **Editor de Origem do OData** para selecionar o gerenciador de conexões do OData para a origem do OData.</span><span class="sxs-lookup"><span data-stu-id="daeda-103">Use the **Connection** page of the **OData Source Editor** dialog box to select the OData connection manager for the OData source.</span></span> <span data-ttu-id="daeda-104">Essa página também permite que você especifique uma coleção ou um caminho de recurso e qualquer opção de consulta para indicar quais dados precisam ser recuperados da origem do OData.</span><span class="sxs-lookup"><span data-stu-id="daeda-104">This page also lets you specify a collection or a resource path and any query options to indicate what data needs to be retrieved from the OData source.</span></span> <span data-ttu-id="daeda-105">Para obter mais informações sobre origem do OData, consulte [OData Source](data-flow/odata-source.md).</span><span class="sxs-lookup"><span data-stu-id="daeda-105">To learn more about the OData source, see [OData Source](data-flow/odata-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="daeda-106">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="daeda-106">Static Options</span></span>  
 <span data-ttu-id="daeda-107">**Gerenciador de conexões OData**</span><span class="sxs-lookup"><span data-stu-id="daeda-107">**OData connection manager**</span></span>  
 <span data-ttu-id="daeda-108">Selecione um gerenciador de conexões existente na lista ou crie uma nova conexão clicando em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="daeda-108">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="daeda-109">**Novo**</span><span class="sxs-lookup"><span data-stu-id="daeda-109">**New**</span></span>  
 <span data-ttu-id="daeda-110">Crie um novo gerenciador de conexões usando a caixa de diálogo **Editor do Gerenciador de Conexões do OData** .</span><span class="sxs-lookup"><span data-stu-id="daeda-110">Create a new connection manager by using the **OData Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="daeda-111">**Use o caminho de coleção ou de recurso**</span><span class="sxs-lookup"><span data-stu-id="daeda-111">**Use collection or resource path**</span></span>  
 <span data-ttu-id="daeda-112">Especifique o método para selecionar os dados da origem.</span><span class="sxs-lookup"><span data-stu-id="daeda-112">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="daeda-113">Opção</span><span class="sxs-lookup"><span data-stu-id="daeda-113">Option</span></span>|<span data-ttu-id="daeda-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="daeda-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="daeda-115">Coleção</span><span class="sxs-lookup"><span data-stu-id="daeda-115">Collection</span></span>|<span data-ttu-id="daeda-116">Recupere os dados da origem do OData usando um nome de coleção.</span><span class="sxs-lookup"><span data-stu-id="daeda-116">Retrieve data from the OData source by using a collection name.</span></span>|  
|<span data-ttu-id="daeda-117">Caminho do recurso</span><span class="sxs-lookup"><span data-stu-id="daeda-117">Resource Path</span></span>|<span data-ttu-id="daeda-118">Recupere os dados da origem do OData usando um caminho de recurso.</span><span class="sxs-lookup"><span data-stu-id="daeda-118">Retrieve data from the OData source by using a resource path.</span></span>|  
  
 <span data-ttu-id="daeda-119">**Opções de consulta**</span><span class="sxs-lookup"><span data-stu-id="daeda-119">**Query options**</span></span>  
 <span data-ttu-id="daeda-120">Especifique as opções para a consulta.</span><span class="sxs-lookup"><span data-stu-id="daeda-120">Specify options for the query.</span></span>  <span data-ttu-id="daeda-121">Por exemplo: $top=5</span><span class="sxs-lookup"><span data-stu-id="daeda-121">For example: $top=5</span></span>  
  
 <span data-ttu-id="daeda-122">**Url do feed**</span><span class="sxs-lookup"><span data-stu-id="daeda-122">**Feed url**</span></span>  
 <span data-ttu-id="daeda-123">Exibe o URL do feed somente leitura com base nas opções que você selecionou nesta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="daeda-123">Displays the read-only Feed URL based on options you selected on this dialog box.</span></span>  
  
 <span data-ttu-id="daeda-124">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="daeda-124">**Preview**</span></span>  
 <span data-ttu-id="daeda-125">Visualize os resultados usando a caixa de diálogo **Visualização** .</span><span class="sxs-lookup"><span data-stu-id="daeda-125">Preview results by using the **Preview** dialog box.</span></span> <span data-ttu-id="daeda-126">A**Visualização** pode exibir até 20 linhas.</span><span class="sxs-lookup"><span data-stu-id="daeda-126">**Preview** can display up to 20 rows.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="daeda-127">Opções dinâmicas</span><span class="sxs-lookup"><span data-stu-id="daeda-127">Dynamic Options</span></span>  
  
### <a name="use-collection-or-resource-path--collection"></a><span data-ttu-id="daeda-128">Use o caminho de coleção ou de recurso = Coleção</span><span class="sxs-lookup"><span data-stu-id="daeda-128">Use collection or resource path = Collection</span></span>  
 <span data-ttu-id="daeda-129">**Coleção**</span><span class="sxs-lookup"><span data-stu-id="daeda-129">**Collection**</span></span>  
 <span data-ttu-id="daeda-130">Selecione uma coleção na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="daeda-130">Select a collection from the drop-down list.</span></span>  
  
### <a name="use-collection-or-resource-path--resource-path"></a><span data-ttu-id="daeda-131">Use o caminho da coleção ou do recurso = Caminho do recurso</span><span class="sxs-lookup"><span data-stu-id="daeda-131">Use collection or resource path = Resource Path</span></span>  
 <span data-ttu-id="daeda-132">**Resource path**</span><span class="sxs-lookup"><span data-stu-id="daeda-132">**Resource path**</span></span>  
 <span data-ttu-id="daeda-133">Digite um caminho de recurso.</span><span class="sxs-lookup"><span data-stu-id="daeda-133">Type a resource path.</span></span> <span data-ttu-id="daeda-134">Por exemplo: Funcionários</span><span class="sxs-lookup"><span data-stu-id="daeda-134">For example: Employees</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daeda-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="daeda-135">See Also</span></span>  
 <span data-ttu-id="daeda-136">[Editor de origem OData &#40;página colunas&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="daeda-136">[OData Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="daeda-137">[Editor de origem OData &#40;página saída de erro&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="daeda-137">[OData Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="daeda-138">Gerenciador de conexões do OData</span><span class="sxs-lookup"><span data-stu-id="daeda-138">OData Connection Manager</span></span>](connection-manager/odata-connection-manager.md)  
  
  
