---
title: Elemento StorageBoundInMB (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- StorageBoundInMB element
ms.assetid: a8374910-bf68-4edb-b464-53a3a705e7f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea49b0af981b8f8d96efb087033d8f1466364c76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683258"
---
# <a name="storageboundinmb-element-dta"></a><span data-ttu-id="b3fde-102">Elemento StorageBoundInMB (DTA)</span><span class="sxs-lookup"><span data-stu-id="b3fde-102">StorageBoundInMB Element (DTA)</span></span>
  <span data-ttu-id="b3fde-103">Especifica o espaço de máximo em megabytes que podem ser consumidos pela recomendação de ajuste do Orientador de Otimização do Mecanismo de Banco de Dados (índice e conjunto de particionamento).</span><span class="sxs-lookup"><span data-stu-id="b3fde-103">Specifies the maximum space in megabytes that can be consumed by the Database Engine Tuning Advisor tuning recommendation (index and partitioning set).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3fde-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b3fde-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <StorageBoundInMB>...</ StorageBoundInMB >  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="b3fde-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="b3fde-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="b3fde-106">Característica</span><span class="sxs-lookup"><span data-stu-id="b3fde-106">Characteristic</span></span>|<span data-ttu-id="b3fde-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="b3fde-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b3fde-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b3fde-108">**Data type and length**</span></span>|<span data-ttu-id="b3fde-109">`unsignedInt`, comprimento ilimitado.</span><span class="sxs-lookup"><span data-stu-id="b3fde-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="b3fde-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="b3fde-110">**Default value**</span></span>|<span data-ttu-id="b3fde-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b3fde-111">None.</span></span>|  
|<span data-ttu-id="b3fde-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="b3fde-112">**Occurrence**</span></span>|<span data-ttu-id="b3fde-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b3fde-113">Optional.</span></span> <span data-ttu-id="b3fde-114">Só pode ser usado uma vez para o elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="b3fde-114">Can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="b3fde-115">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="b3fde-115">Element Relationships</span></span>  
  
|<span data-ttu-id="b3fde-116">Relação</span><span class="sxs-lookup"><span data-stu-id="b3fde-116">Relationship</span></span>|<span data-ttu-id="b3fde-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="b3fde-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="b3fde-118">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="b3fde-118">**Parent element**</span></span>|[<span data-ttu-id="b3fde-119">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b3fde-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="b3fde-120">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="b3fde-120">**Child elements**</span></span>|<span data-ttu-id="b3fde-121">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b3fde-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3fde-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="b3fde-122">Remarks</span></span>  
 <span data-ttu-id="b3fde-123">Quando múltiplos bancos de dados são ajustados, as recomendações para todos os bancos de dados são consideradas no cálculo do espaço.</span><span class="sxs-lookup"><span data-stu-id="b3fde-123">When multiple databases are tuned, recommendations for all databases are considered for the space calculation.</span></span> <span data-ttu-id="b3fde-124">Por padrão, o Orientador de Otimização do Mecanismo de Banco de Dados assume o menor dos seguintes tamanhos de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="b3fde-124">By default, Database Engine Tuning Advisor assumes the smaller of the following storage sizes:</span></span>  
  
-   <span data-ttu-id="b3fde-125">Três vezes o tamanho de dados brutos atuais, o que inclui o tamanho total de heaps e índices clusterizados em tabelas.</span><span class="sxs-lookup"><span data-stu-id="b3fde-125">Three times the current raw data size, which includes the total size of heaps and clustered indexes on tables.</span></span>  
  
-   <span data-ttu-id="b3fde-126">Os espaços livres em todas as unidades de disco anexas mais o tamanho dos dados brutos.</span><span class="sxs-lookup"><span data-stu-id="b3fde-126">The free space on all attached disk drives plus the raw data size.</span></span>  
  
 <span data-ttu-id="b3fde-127">O tamanho de armazenamento padrão não inclui índices não clusterizados e exibições indexadas.</span><span class="sxs-lookup"><span data-stu-id="b3fde-127">The default storage size does not include nonclustered indexes and indexed views.</span></span>  
  
 <span data-ttu-id="b3fde-128">Se o valor especificado para o elemento `StorageBoundInMB` exceder o espaço de disco atual, o Orientador de Otimização do Mecanismo de Banco de Dados retorna um erro, mas continua o ajuste.</span><span class="sxs-lookup"><span data-stu-id="b3fde-128">If the value specified for the `StorageBoundInMB` element exceeds the actual disk space, Database Engine Tuning Advisor returns an error, but continues tuning.</span></span> <span data-ttu-id="b3fde-129">Depois que o ajuste estiver completo, você pode acrescentar espaço de disco caso decida implementar a recomendação.</span><span class="sxs-lookup"><span data-stu-id="b3fde-129">After tuning is complete, you can add disk space if you decide to implement the recommendation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3fde-130">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b3fde-130">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="b3fde-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="b3fde-131">Description</span></span>  
 <span data-ttu-id="b3fde-132">O seguinte exemplo de código mostra como definir um limite de 1500 megabytes como o espaço de disco de máximo que uma recomendação de ajuste pode consumir:</span><span class="sxs-lookup"><span data-stu-id="b3fde-132">The following code example shows how to set a limit of 1500 megabytes as the maximum disk space that a tuning recommendation can consume:</span></span>  
  
## <a name="code"></a><span data-ttu-id="b3fde-133">Código</span><span class="sxs-lookup"><span data-stu-id="b3fde-133">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <StorageBoundInMB>1500</StorageBoundInMB>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3fde-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b3fde-134">See Also</span></span>  
 [<span data-ttu-id="b3fde-135">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="b3fde-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
