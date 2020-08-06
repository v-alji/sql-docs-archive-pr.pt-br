---
title: Elemento KeepExisting (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- KeepExisting element
ms.assetid: e67aae61-d06d-4a03-85ba-6516c3502dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: cde9b3091b75f55e4b9c79137853fbd7d4e0daf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682014"
---
# <a name="keepexisting-element-dta"></a><span data-ttu-id="7b20e-102">Elemento KeepExisting (DTA)</span><span class="sxs-lookup"><span data-stu-id="7b20e-102">KeepExisting Element (DTA)</span></span>
  <span data-ttu-id="7b20e-103">Especifica as estruturas físicas de design (índices, exibições indexadas ou particionamento) que o Orientador de Otimização do Mecanismo de Banco de Dados deve reter ao gerar sua recomendação.</span><span class="sxs-lookup"><span data-stu-id="7b20e-103">Specifies the physical design structures (indexes, indexed views, or partitioning) that Database Engine Tuning Advisor must retain when generating its recommendation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b20e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7b20e-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <KeepExisting>...</KeepExisting>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="7b20e-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="7b20e-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="7b20e-106">Característica</span><span class="sxs-lookup"><span data-stu-id="7b20e-106">Characteristic</span></span>|<span data-ttu-id="7b20e-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="7b20e-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7b20e-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="7b20e-108">**Data type and length**</span></span>|<span data-ttu-id="7b20e-109">`string`O limite de tamanho é aplicado pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="7b20e-109">`string`, length limit enforced by the server.</span></span>|  
|<span data-ttu-id="7b20e-110">**Valores permitidos**</span><span class="sxs-lookup"><span data-stu-id="7b20e-110">**Allowed values**</span></span>|<span data-ttu-id="7b20e-111">**NONE**</span><span class="sxs-lookup"><span data-stu-id="7b20e-111">**NONE**</span></span><br /> <span data-ttu-id="7b20e-112">Não existe nenhuma estrutura.</span><span class="sxs-lookup"><span data-stu-id="7b20e-112">No existing structures.</span></span><br /><br /> <span data-ttu-id="7b20e-113">**ALL**</span><span class="sxs-lookup"><span data-stu-id="7b20e-113">**ALL**</span></span><br /> <span data-ttu-id="7b20e-114">Todas as estruturas existentes.</span><span class="sxs-lookup"><span data-stu-id="7b20e-114">All existing structures.</span></span><br /><br /> <span data-ttu-id="7b20e-115">**ALIGNED**</span><span class="sxs-lookup"><span data-stu-id="7b20e-115">**ALIGNED**</span></span><br /> <span data-ttu-id="7b20e-116">Todas as estruturas alinhadas por partição.</span><span class="sxs-lookup"><span data-stu-id="7b20e-116">All partition-aligned structures.</span></span><br /><br /> <span data-ttu-id="7b20e-117">**CL_IDX**</span><span class="sxs-lookup"><span data-stu-id="7b20e-117">**CL_IDX**</span></span><br /> <span data-ttu-id="7b20e-118">Todos os índices clusterizados em tabelas</span><span class="sxs-lookup"><span data-stu-id="7b20e-118">All clustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="7b20e-119">**IDX**</span><span class="sxs-lookup"><span data-stu-id="7b20e-119">**IDX**</span></span><br /> <span data-ttu-id="7b20e-120">Todos os índices clusterizados e não cluster em tabelas</span><span class="sxs-lookup"><span data-stu-id="7b20e-120">All clustered and nonclustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="7b20e-121">Use apenas um desses valores com este elemento.</span><span class="sxs-lookup"><span data-stu-id="7b20e-121">Use only one of these values with this element.</span></span>|  
|<span data-ttu-id="7b20e-122">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="7b20e-122">**Default value**</span></span>|<span data-ttu-id="7b20e-123">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7b20e-123">None.</span></span>|  
|<span data-ttu-id="7b20e-124">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="7b20e-124">**Occurrence**</span></span>|<span data-ttu-id="7b20e-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7b20e-125">Optional.</span></span> <span data-ttu-id="7b20e-126">Pode-se usar apenas uma vez para cada elemento de `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="7b20e-126">Can use only once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="7b20e-127">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="7b20e-127">Element Relationships</span></span>  
  
|<span data-ttu-id="7b20e-128">Relação</span><span class="sxs-lookup"><span data-stu-id="7b20e-128">Relationship</span></span>|<span data-ttu-id="7b20e-129">Elementos</span><span class="sxs-lookup"><span data-stu-id="7b20e-129">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="7b20e-130">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="7b20e-130">**Parent element**</span></span>|[<span data-ttu-id="7b20e-131">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="7b20e-131">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="7b20e-132">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="7b20e-132">**Child elements**</span></span>|<span data-ttu-id="7b20e-133">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7b20e-133">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7b20e-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7b20e-134">Example</span></span>  
 <span data-ttu-id="7b20e-135">Para obter um exemplo de uso desse elemento, veja [Exemplo de arquivos de entrada XML simples &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="7b20e-135">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b20e-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7b20e-136">See Also</span></span>  
 [<span data-ttu-id="7b20e-137">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="7b20e-137">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
