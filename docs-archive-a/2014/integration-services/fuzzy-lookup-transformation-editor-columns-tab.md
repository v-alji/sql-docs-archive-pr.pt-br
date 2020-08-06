---
title: Editor de transformação pesquisa difusa (guia colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.columns.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: aaf45327-79e9-4760-9b4d-546ace91b5b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9294022b52536940916a381d7b811437eaa5814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679429"
---
# <a name="fuzzy-lookup-transformation-editor-columns-tab"></a><span data-ttu-id="97980-102">Editor de Transformação Pesquisa Difusa (guia Colunas)</span><span class="sxs-lookup"><span data-stu-id="97980-102">Fuzzy Lookup Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="97980-103">Use a guia **Colunas** da caixa de diálogo **Editor de Transformação Pesquisa Difusa** para definir propriedades das colunas de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="97980-103">Use the **Columns** tab of the **Fuzzy Lookup Transformation Editor** dialog box to set properties for input and output columns.</span></span>  
  
 <span data-ttu-id="97980-104">Para saber mais sobre a transformação Pesquisa Difusa, consulte [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="97980-104">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="97980-105">Opções</span><span class="sxs-lookup"><span data-stu-id="97980-105">Options</span></span>  
 <span data-ttu-id="97980-106">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="97980-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="97980-107">Arraste colunas de entrada para conectá-las com colunas de pesquisa disponíveis.</span><span class="sxs-lookup"><span data-stu-id="97980-107">Drag input columns to connect them to available lookup columns.</span></span> <span data-ttu-id="97980-108">Essas colunas devem ter tipos de dados correspondentes com suporte.</span><span class="sxs-lookup"><span data-stu-id="97980-108">These columns must have matching, supported data types.</span></span> <span data-ttu-id="97980-109">Selecione uma linha de mapeamento e clique com o botão direito do mouse para editar os mapeamentos na caixa de diálogo [Criar Relações](data-flow/transformations/create-relationships.md) .</span><span class="sxs-lookup"><span data-stu-id="97980-109">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="97980-110">**Nome**</span><span class="sxs-lookup"><span data-stu-id="97980-110">**Name**</span></span>  
 <span data-ttu-id="97980-111">Exiba os nomes das colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="97980-111">View the names of the available input columns.</span></span>  
  
 <span data-ttu-id="97980-112">**Passagem**</span><span class="sxs-lookup"><span data-stu-id="97980-112">**Pass Through**</span></span>  
 <span data-ttu-id="97980-113">Especifique se as colunas de entrada devem ser incluídas na saída da transformação.</span><span class="sxs-lookup"><span data-stu-id="97980-113">Specify whether to include the input columns in the output of the transformation.</span></span>  
  
 <span data-ttu-id="97980-114">**Colunas de Pesquisa Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="97980-114">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="97980-115">Use as caixas de seleção para selecionar colunas nas quais executar operações de pesquisa difusa.</span><span class="sxs-lookup"><span data-stu-id="97980-115">Use the check boxes to select columns on which to perform fuzzy lookup operations.</span></span>  
  
 <span data-ttu-id="97980-116">**coluna de pesquisa**</span><span class="sxs-lookup"><span data-stu-id="97980-116">**Lookup Column**</span></span>  
 <span data-ttu-id="97980-117">Selecione colunas de pesquisa na lista de colunas da tabela de referência disponíveis.</span><span class="sxs-lookup"><span data-stu-id="97980-117">Select lookup columns from the list of available reference table columns.</span></span> <span data-ttu-id="97980-118">Suas seleções se refletem nas da caixa de seleção da tabela **Colunas de Pesquisa Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="97980-118">Your selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span> <span data-ttu-id="97980-119">Selecionar uma coluna na tabela **Colunas de Pesquisa Disponíveis** cria uma coluna de saída que contém o valor da coluna da tabela de referência para cada linha correspondente retornada.</span><span class="sxs-lookup"><span data-stu-id="97980-119">Selecting a column in the **Available Lookup Columns** table creates an output column that contains the reference table column value for each matching row returned.</span></span>  
  
 <span data-ttu-id="97980-120">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="97980-120">**Output Alias**</span></span>  
 <span data-ttu-id="97980-121">Digite um alias para a saída de cada coluna de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="97980-121">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="97980-122">O padrão é o nome da coluna de pesquisa com um valor de índice numérico anexado; contudo, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="97980-122">The default is the name of the lookup column with a numeric index value appended; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97980-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="97980-123">See Also</span></span>  
 <span data-ttu-id="97980-124">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="97980-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="97980-125">[Editor de transformação pesquisa difusa &#40;guia tabela de referência&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="97980-125">[Fuzzy Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 [<span data-ttu-id="97980-126">Editor de Transformação Pesquisa Difusa &#40;Guia Avançado&#41;</span><span class="sxs-lookup"><span data-stu-id="97980-126">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
