---
title: Editor de transformação Agregação (guia Avançado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.aggregationtransformation.advanced.f1
helpviewer_keywords:
- Aggregate Transformation Editor
ms.assetid: 186a9736-2554-40a0-9cb2-877a8db5fde8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb3742a83f363f74004a5aac0eefc589ee2a5be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571534"
---
# <a name="aggregate-transformation-editor-advanced-tab"></a><span data-ttu-id="ff54a-102">Editor de Transformação Agregação (guia Avançado)</span><span class="sxs-lookup"><span data-stu-id="ff54a-102">Aggregate Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="ff54a-103">Use a guia **Avançado** da caixa de diálogo **Editor de Transformação Agregação** para definir propriedades de componentes, especificar agregações e definir propriedades de colunas de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="ff54a-103">Use the **Advanced** tab of the **Aggregate Transformation Editor** dialog box to set component properties, specify aggregations, and set properties of input and output columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff54a-104">As opções de contagem de chaves, escala de chave, contagem de chaves distintas e escala de chave distinta são aplicadas em nível de componente quando especificado na guia **Avançado** , em nível de saída quando especificado na exibição avançada da guia **Agregações** e em nível de coluna quando especificado na lista de colunas na parte inferior da guia **Agregações** .</span><span class="sxs-lookup"><span data-stu-id="ff54a-104">The options for key count, key scale, distinct key count, and distinct key scale apply at the component level when specified on the **Advanced** tab, at the output level when specified in the advanced display of the **Aggregations** tab, and at the column level when specified in the column list at the bottom of the **Aggregations** tab.</span></span>  
>   
>  <span data-ttu-id="ff54a-105">Na transformação Agregação, **Chaves** e **Escala de Chave** fazem referência ao número de grupos que são esperados como resultado de uma operação **Agrupar porz** .</span><span class="sxs-lookup"><span data-stu-id="ff54a-105">In the Aggregate transformation, **Keys** and **Keys scale** refer to the number of groups that are expected to result from a **Group by** operation.</span></span> <span data-ttu-id="ff54a-106">**Chaves de distinção de contagem** e **Escala de distinção de contagem** fazem referência ao número de valores distintos que são esperados como resultado de uma operação de **Contagem de distinção** .</span><span class="sxs-lookup"><span data-stu-id="ff54a-106">**Count distinct keys** and **Count distinct scale** refer to the number of distinct values that are expected to result from a **Distinct count** operation.</span></span>  
  
 <span data-ttu-id="ff54a-107">Para obter mais informações sobre a transformação Agregação, consulte [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="ff54a-107">To learn more about the Aggregate transformation, see [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ff54a-108">Opções</span><span class="sxs-lookup"><span data-stu-id="ff54a-108">Options</span></span>  
 <span data-ttu-id="ff54a-109">**Escala de Chave**</span><span class="sxs-lookup"><span data-stu-id="ff54a-109">**Keys scale**</span></span>  
 <span data-ttu-id="ff54a-110">Especifique, opcionalmente, o número aproximado de chaves que a agregação espera.</span><span class="sxs-lookup"><span data-stu-id="ff54a-110">Optionally specify the approximate number of keys that the aggregation expects.</span></span> <span data-ttu-id="ff54a-111">A transformação usa estas informações para otimizar seu tamanho de cache inicial.</span><span class="sxs-lookup"><span data-stu-id="ff54a-111">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="ff54a-112">Por padrão, o valor desta opção é **Não Especificado**.</span><span class="sxs-lookup"><span data-stu-id="ff54a-112">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="ff54a-113">Se for especificada a **Escala de chave** e o **Número de chaves** , o **Número de chaves** terá precedência.</span><span class="sxs-lookup"><span data-stu-id="ff54a-113">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
|<span data-ttu-id="ff54a-114">Valor</span><span class="sxs-lookup"><span data-stu-id="ff54a-114">Value</span></span>|<span data-ttu-id="ff54a-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="ff54a-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ff54a-116">Não Especificado</span><span class="sxs-lookup"><span data-stu-id="ff54a-116">Unspecified</span></span>|<span data-ttu-id="ff54a-117">A propriedade **Escala de chave** não é usada.</span><span class="sxs-lookup"><span data-stu-id="ff54a-117">The **Keys scale** property is not used.</span></span>|  
|<span data-ttu-id="ff54a-118">Baixo</span><span class="sxs-lookup"><span data-stu-id="ff54a-118">Low</span></span>|<span data-ttu-id="ff54a-119">A agregação pode gravar aproximadamente 500.000 chaves.</span><span class="sxs-lookup"><span data-stu-id="ff54a-119">Aggregation can write approximately 500,000 keys.</span></span>|  
|<span data-ttu-id="ff54a-120">Médio</span><span class="sxs-lookup"><span data-stu-id="ff54a-120">Medium</span></span>|<span data-ttu-id="ff54a-121">A agregação pode gravar aproximadamente 5.000.000 de chaves.</span><span class="sxs-lookup"><span data-stu-id="ff54a-121">Aggregation can write approximately 5,000,000 keys.</span></span>|  
|<span data-ttu-id="ff54a-122">Alta</span><span class="sxs-lookup"><span data-stu-id="ff54a-122">High</span></span>|<span data-ttu-id="ff54a-123">A agregação pode gravar mais de 25.000.000 de chaves.</span><span class="sxs-lookup"><span data-stu-id="ff54a-123">Aggregation can write more than 25,000,000 keys.</span></span>|  
  
 <span data-ttu-id="ff54a-124">**Número de chaves**</span><span class="sxs-lookup"><span data-stu-id="ff54a-124">**Number of keys**</span></span>  
 <span data-ttu-id="ff54a-125">Especifique, opcionalmente, o número exato de chaves que a agregação espera.</span><span class="sxs-lookup"><span data-stu-id="ff54a-125">Optionally specify the exact number of keys that the aggregation expects.</span></span> <span data-ttu-id="ff54a-126">A transformação usa estas informações para otimizar seu tamanho de cache inicial.</span><span class="sxs-lookup"><span data-stu-id="ff54a-126">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="ff54a-127">Se for especificada a **Escala de chave** e o **Número de chaves** , o **Número de chaves** terá precedência.</span><span class="sxs-lookup"><span data-stu-id="ff54a-127">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
 <span data-ttu-id="ff54a-128">**Escala de distinção de contagem**</span><span class="sxs-lookup"><span data-stu-id="ff54a-128">**Count distinct scale**</span></span>  
 <span data-ttu-id="ff54a-129">Especifique, opcionalmente, o número aproximado de valores de distinção que a agregação pode gravar.</span><span class="sxs-lookup"><span data-stu-id="ff54a-129">Optionally specify the approximate number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="ff54a-130">Por padrão, o valor desta opção é **Não Especificado**.</span><span class="sxs-lookup"><span data-stu-id="ff54a-130">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="ff54a-131">Se for especificada a **Escala de Distinção de Contagem** e as **Chaves de Distinção de Contagem** , as **Chaves de Distinção de Contagem** terão precedência.</span><span class="sxs-lookup"><span data-stu-id="ff54a-131">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
|<span data-ttu-id="ff54a-132">Valor</span><span class="sxs-lookup"><span data-stu-id="ff54a-132">Value</span></span>|<span data-ttu-id="ff54a-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="ff54a-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ff54a-134">Não Especificado</span><span class="sxs-lookup"><span data-stu-id="ff54a-134">Unspecified</span></span>|<span data-ttu-id="ff54a-135">A propriedade Escala de Distinção de Contagem não é usada.</span><span class="sxs-lookup"><span data-stu-id="ff54a-135">The CountDistinctScale property is not used.</span></span>|  
|<span data-ttu-id="ff54a-136">Baixo</span><span class="sxs-lookup"><span data-stu-id="ff54a-136">Low</span></span>|<span data-ttu-id="ff54a-137">A agregação pode gravar aproximadamente 500.000 valores de distinção.</span><span class="sxs-lookup"><span data-stu-id="ff54a-137">Aggregation can write approximately 500,000 distinct values.</span></span>|  
|<span data-ttu-id="ff54a-138">Médio</span><span class="sxs-lookup"><span data-stu-id="ff54a-138">Medium</span></span>|<span data-ttu-id="ff54a-139">A agregação pode gravar aproximadamente 5.000.000 valores distintos.</span><span class="sxs-lookup"><span data-stu-id="ff54a-139">Aggregation can write approximately 5,000,000 distinct values.</span></span>|  
|<span data-ttu-id="ff54a-140">Alta</span><span class="sxs-lookup"><span data-stu-id="ff54a-140">High</span></span>|<span data-ttu-id="ff54a-141">A agregação pode gravar mais de 25.000.000 de valores de distinção.</span><span class="sxs-lookup"><span data-stu-id="ff54a-141">Aggregation can write more than 25,000,000 distinct values.</span></span>|  
  
 <span data-ttu-id="ff54a-142">**Chaves de distinção de contagem**</span><span class="sxs-lookup"><span data-stu-id="ff54a-142">**Count distinct keys**</span></span>  
 <span data-ttu-id="ff54a-143">Especifique, opcionalmente, o número exato de valores de distinção que a agregação pode gravar.</span><span class="sxs-lookup"><span data-stu-id="ff54a-143">Optionally specify the exact number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="ff54a-144">Se for especificada a **Escala de Distinção de Contagem** e as **Chaves de Distinção de Contagem** , as **Chaves de Distinção de Contagem** terão precedência.</span><span class="sxs-lookup"><span data-stu-id="ff54a-144">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
 <span data-ttu-id="ff54a-145">**Estender fator automaticamente**</span><span class="sxs-lookup"><span data-stu-id="ff54a-145">**Auto extend factor**</span></span>  
 <span data-ttu-id="ff54a-146">Use um valor entre 1 e 100 para especificar a porcentagem pela qual a memória pode ser estendida durante a agregação.</span><span class="sxs-lookup"><span data-stu-id="ff54a-146">Use a value between 1 and 100 to specify the percentage by which memory can be extended during the aggregation.</span></span> <span data-ttu-id="ff54a-147">Por padrão, o valor desta opção é **25%**.</span><span class="sxs-lookup"><span data-stu-id="ff54a-147">By default, the value of this option is **25%**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff54a-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ff54a-148">See Also</span></span>  
 <span data-ttu-id="ff54a-149">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ff54a-149">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ff54a-150">[Editor de transformação Agregação &#40;guia agregações&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span><span class="sxs-lookup"><span data-stu-id="ff54a-150">[Aggregate Transformation Editor &#40;Aggregations Tab&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span></span>  
 [<span data-ttu-id="ff54a-151">Agregar valores em um conjunto de dados por meio da transformação Agregação</span><span class="sxs-lookup"><span data-stu-id="ff54a-151">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>](data-flow/transformations/aggregate-values-in-a-dataset-by-using-the-aggregate-transformation.md)  
  
  
