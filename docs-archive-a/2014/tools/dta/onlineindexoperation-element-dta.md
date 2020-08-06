---
title: Elemento OnlineIndexOperation (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- OnlineIndexOperation element
ms.assetid: 7c5614cd-09aa-4a59-9591-347aa7d36473
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48943c1b31d7a0a24ae939050d44494476e50034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576101"
---
# <a name="onlineindexoperation-element-dta"></a><span data-ttu-id="307f5-102">Elemento OnlineIndexOperation (DTA)</span><span class="sxs-lookup"><span data-stu-id="307f5-102">OnlineIndexOperation Element (DTA)</span></span>
  <span data-ttu-id="307f5-103">Especifica se os índices, as exibições indexadas ou as partições que o Database Engine Tuning Advisor recomenda podem ser criados online.</span><span class="sxs-lookup"><span data-stu-id="307f5-103">Specifies whether the indexes, indexed views, or partitions that Database Engine Tuning Advisor recommends can be created online.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="307f5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="307f5-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <OnlineIndexOperation>...</OnlineIndexOperation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="307f5-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="307f5-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="307f5-106">Característica</span><span class="sxs-lookup"><span data-stu-id="307f5-106">Characteristic</span></span>|<span data-ttu-id="307f5-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="307f5-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="307f5-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="307f5-108">**Data type and length**</span></span>|<span data-ttu-id="307f5-109">`string`, nenhum tamanho máximo.</span><span class="sxs-lookup"><span data-stu-id="307f5-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="307f5-110">**Valores permitidos**</span><span class="sxs-lookup"><span data-stu-id="307f5-110">**Allowed values**</span></span>|<span data-ttu-id="307f5-111">**OFF**</span><span class="sxs-lookup"><span data-stu-id="307f5-111">**OFF**</span></span><br /> <span data-ttu-id="307f5-112">Nenhuma estrutura de design físico recomendada pode ser criada online.</span><span class="sxs-lookup"><span data-stu-id="307f5-112">No recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="307f5-113">**ON**</span><span class="sxs-lookup"><span data-stu-id="307f5-113">**ON**</span></span><br /> <span data-ttu-id="307f5-114">Todas as estruturas de design físico recomendadas podem ser criadas online.</span><span class="sxs-lookup"><span data-stu-id="307f5-114">All recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="307f5-115">**MIXED**</span><span class="sxs-lookup"><span data-stu-id="307f5-115">**MIXED**</span></span><br /> <span data-ttu-id="307f5-116">O Orientador de Otimização do Mecanismo de Banco de Dados tenta recomendar estruturas de design físico que podem ser criadas online quando possível.</span><span class="sxs-lookup"><span data-stu-id="307f5-116">Database Engine Tuning Advisor attempts to recommend physical design structures that can be created online when possible.</span></span><br /><br /> <span data-ttu-id="307f5-117">Use um desses valores com esse elemento.</span><span class="sxs-lookup"><span data-stu-id="307f5-117">Use one of these values with this element.</span></span> <span data-ttu-id="307f5-118">Se os índices são criados online, a palavra-chave **ONLINE = ON** será acrescentada à definição de seus objetos.</span><span class="sxs-lookup"><span data-stu-id="307f5-118">If indexes are created online, the keyword **ONLINE = ON** is appended to its object definition.</span></span>|  
|<span data-ttu-id="307f5-119">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="307f5-119">**Default value**</span></span>|<span data-ttu-id="307f5-120">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="307f5-120">None.</span></span>|  
|<span data-ttu-id="307f5-121">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="307f5-121">**Occurrence**</span></span>|<span data-ttu-id="307f5-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="307f5-122">Optional.</span></span> <span data-ttu-id="307f5-123">Se usado, só pode ser utilizado uma vez para o elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="307f5-123">If used, can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="307f5-124">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="307f5-124">Element Relationships</span></span>  
  
|<span data-ttu-id="307f5-125">Relação</span><span class="sxs-lookup"><span data-stu-id="307f5-125">Relationship</span></span>|<span data-ttu-id="307f5-126">Elementos</span><span class="sxs-lookup"><span data-stu-id="307f5-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="307f5-127">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="307f5-127">**Parent element**</span></span>|[<span data-ttu-id="307f5-128">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="307f5-128">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="307f5-129">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="307f5-129">**Child elements**</span></span>|<span data-ttu-id="307f5-130">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="307f5-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="307f5-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="307f5-131">Example</span></span>  
 <span data-ttu-id="307f5-132">Para obter um exemplo de uso desse elemento, veja [Exemplo de arquivos de entrada XML simples &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="307f5-132">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="307f5-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="307f5-133">See Also</span></span>  
 [<span data-ttu-id="307f5-134">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="307f5-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
