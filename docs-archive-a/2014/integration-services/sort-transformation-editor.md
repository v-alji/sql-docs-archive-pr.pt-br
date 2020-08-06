---
title: Editor de transformação Classificação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttransformation.f1
helpviewer_keywords:
- Sort Transformation Editor
ms.assetid: 8ae23970-49a9-4d6d-9f15-c7074783347c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f48c366f4337af29b03877f6bb20b804457a293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685821"
---
# <a name="sort-transformation-editor"></a><span data-ttu-id="8162c-102">Editor de Transformação Classificação</span><span class="sxs-lookup"><span data-stu-id="8162c-102">Sort Transformation Editor</span></span>
  <span data-ttu-id="8162c-103">Use a caixa de diálogo **Editor de Transformação Classificação** para selecionar as colunas a classificar, definir a ordem de classificação e especificar se as duplicatas devem ser removidas.</span><span class="sxs-lookup"><span data-stu-id="8162c-103">Use the **Sort Transformation Editor** dialog box to select the columns to sort, set the sort order, and specify whether duplicates are removed.</span></span>  
  
 <span data-ttu-id="8162c-104">Para saber mais sobre a transformação Classificação, consulte [Sort Transformation](data-flow/transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8162c-104">To learn more about the Sort transformation, see [Sort Transformation](data-flow/transformations/sort-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8162c-105">Opções</span><span class="sxs-lookup"><span data-stu-id="8162c-105">Options</span></span>  
 <span data-ttu-id="8162c-106">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="8162c-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="8162c-107">Usando as caixas de seleção, especifique as colunas a classificar.</span><span class="sxs-lookup"><span data-stu-id="8162c-107">Using the check boxes, specify the columns to sort.</span></span>  
  
 <span data-ttu-id="8162c-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8162c-108">**Name**</span></span>  
 <span data-ttu-id="8162c-109">Visualize o nome de cada coluna de entrada disponível.</span><span class="sxs-lookup"><span data-stu-id="8162c-109">View the name of each available input column.</span></span>  
  
 <span data-ttu-id="8162c-110">**Passagem**</span><span class="sxs-lookup"><span data-stu-id="8162c-110">**Passthrough**</span></span>  
 <span data-ttu-id="8162c-111">Indique se a coluna deve ser incluída na saída classificada.</span><span class="sxs-lookup"><span data-stu-id="8162c-111">Indicate whether to include the column in the sorted output.</span></span>  
  
 <span data-ttu-id="8162c-112">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="8162c-112">**Input Column**</span></span>  
 <span data-ttu-id="8162c-113">Selecione colunas para cada linha na lista de colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8162c-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="8162c-114">As seleções se refletem naquelas da caixa de seleção da tabela **Colunas de Entrada Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="8162c-114">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="8162c-115">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="8162c-115">**Output Alias**</span></span>  
 <span data-ttu-id="8162c-116">Digite um alias para cada coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="8162c-116">Type an alias for each output column.</span></span> <span data-ttu-id="8162c-117">O padrão é o nome da coluna de entrada; no entanto, é possível escolher qualquer nome descritivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="8162c-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="8162c-118">**Tipo de Classificação**</span><span class="sxs-lookup"><span data-stu-id="8162c-118">**Sort Type**</span></span>  
 <span data-ttu-id="8162c-119">Indique se a classificação deve ser feita em ordem ascendente ou descendente.</span><span class="sxs-lookup"><span data-stu-id="8162c-119">Indicate whether to sort in ascending or descending order.</span></span>  
  
 <span data-ttu-id="8162c-120">**Sort Order**</span><span class="sxs-lookup"><span data-stu-id="8162c-120">**Sort Order**</span></span>  
 <span data-ttu-id="8162c-121">Indique a ordem na qual classificar as colunas.</span><span class="sxs-lookup"><span data-stu-id="8162c-121">Indicate the order in which to sort columns.</span></span> <span data-ttu-id="8162c-122">Deve ser definido manualmente para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="8162c-122">This must be set manually for each column.</span></span>  
  
 <span data-ttu-id="8162c-123">**Sinalizadores de Comparação**</span><span class="sxs-lookup"><span data-stu-id="8162c-123">**Comparison Flags**</span></span>  
 <span data-ttu-id="8162c-124">Para obter mais informações sobre as opções de comparação de cadeias de caracteres, consulte [Comparando dados de cadeia de caracteres](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="8162c-124">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="8162c-125">**Remover linhas com valores de classificação duplicados**</span><span class="sxs-lookup"><span data-stu-id="8162c-125">**Remove rows with duplicate sort values**</span></span>  
 <span data-ttu-id="8162c-126">Indique se a transformação deve copiar as linhas duplicadas para a saída ou criar uma única entrada para todas as duplicatas, seguindo as opções de comparação de cadeia de caracteres especificadas.</span><span class="sxs-lookup"><span data-stu-id="8162c-126">Indicate whether the transformation copies duplicate rows to the transformation output, or creates a single entry for all duplicates, based on the specified string comparison options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8162c-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8162c-127">See Also</span></span>  
 [<span data-ttu-id="8162c-128">Referência de mensagens e erros do Integration Services</span><span class="sxs-lookup"><span data-stu-id="8162c-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
