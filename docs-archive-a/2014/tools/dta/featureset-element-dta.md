---
title: Elemento featureset (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- FeatureSet element
ms.assetid: f2070c53-4a5c-4c11-ac38-96ee200c84f0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d36c28b24a56ef2dcdf69578fb7e8c196306a416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683849"
---
# <a name="featureset-element-dta"></a><span data-ttu-id="b72bc-102">Elemento FeatureSet (DTA)</span><span class="sxs-lookup"><span data-stu-id="b72bc-102">FeatureSet Element (DTA)</span></span>
  <span data-ttu-id="b72bc-103">Contém as estruturas físicas de design (índices ou exibições indexadas) que você gostaria que o Orientador de Otimização do Mecanismo de Banco de Dados usasse durante análise.</span><span class="sxs-lookup"><span data-stu-id="b72bc-103">Contains the physical design structures (indexes or indexed views) that you would like Database Engine Tuning Advisor to use during analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b72bc-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b72bc-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <FeatureSet>...</FeatureSet>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="b72bc-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="b72bc-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="b72bc-106">Característica</span><span class="sxs-lookup"><span data-stu-id="b72bc-106">Characteristic</span></span>|<span data-ttu-id="b72bc-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="b72bc-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b72bc-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b72bc-108">**Data type and length**</span></span>|<span data-ttu-id="b72bc-109">`string`, nenhum tamanho máximo.</span><span class="sxs-lookup"><span data-stu-id="b72bc-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="b72bc-110">**Valores permitidos**</span><span class="sxs-lookup"><span data-stu-id="b72bc-110">**Allowed values**</span></span>|<span data-ttu-id="b72bc-111">**IDX_IV**</span><span class="sxs-lookup"><span data-stu-id="b72bc-111">**IDX_IV**</span></span><br /> <span data-ttu-id="b72bc-112">Índices e exibições indexadas.</span><span class="sxs-lookup"><span data-stu-id="b72bc-112">Indexes and indexed views.</span></span><br /><br /> <span data-ttu-id="b72bc-113">**IDX**</span><span class="sxs-lookup"><span data-stu-id="b72bc-113">**IDX**</span></span><br /> <span data-ttu-id="b72bc-114">Somente índices.</span><span class="sxs-lookup"><span data-stu-id="b72bc-114">Indexes only.</span></span><br /><br /> <span data-ttu-id="b72bc-115">**IV**</span><span class="sxs-lookup"><span data-stu-id="b72bc-115">**IV**</span></span><br /> <span data-ttu-id="b72bc-116">Somente exibições indexadas.</span><span class="sxs-lookup"><span data-stu-id="b72bc-116">Indexed views only.</span></span><br /><br /> <span data-ttu-id="b72bc-117">**NCL_IDX**</span><span class="sxs-lookup"><span data-stu-id="b72bc-117">**NCL_IDX**</span></span><br /> <span data-ttu-id="b72bc-118">Somente índices não clusterizados</span><span class="sxs-lookup"><span data-stu-id="b72bc-118">Nonclustered indexes only.</span></span><br /><br /> <span data-ttu-id="b72bc-119">Use um desses valores com esse elemento.</span><span class="sxs-lookup"><span data-stu-id="b72bc-119">Use one of these values with this element.</span></span>|  
|<span data-ttu-id="b72bc-120">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="b72bc-120">**Default value**</span></span>|<span data-ttu-id="b72bc-121">**IDX**</span><span class="sxs-lookup"><span data-stu-id="b72bc-121">**IDX**</span></span>|  
|<span data-ttu-id="b72bc-122">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="b72bc-122">**Occurrence**</span></span>|<span data-ttu-id="b72bc-123">Exigido uma vez para cada elemento `TuningOptions`, a menos que seja usado o elemento `DropOnlyMode`.</span><span class="sxs-lookup"><span data-stu-id="b72bc-123">Required once for each `TuningOptions` element, unless the `DropOnlyMode` element is used.</span></span> <span data-ttu-id="b72bc-124">Se `DropOnlyMode` for usado, você não poderá usar o `FeatureSet`.</span><span class="sxs-lookup"><span data-stu-id="b72bc-124">If `DropOnlyMode` is used, you cannot use `FeatureSet`.</span></span> <span data-ttu-id="b72bc-125">Estes elementos são mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="b72bc-125">These elements are mutually exclusive.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="b72bc-126">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="b72bc-126">Element Relationships</span></span>  
  
|<span data-ttu-id="b72bc-127">Relação</span><span class="sxs-lookup"><span data-stu-id="b72bc-127">Relationship</span></span>|<span data-ttu-id="b72bc-128">Elementos</span><span class="sxs-lookup"><span data-stu-id="b72bc-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="b72bc-129">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="b72bc-129">**Parent element**</span></span>|[<span data-ttu-id="b72bc-130">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b72bc-130">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="b72bc-131">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="b72bc-131">**Child elements**</span></span>|<span data-ttu-id="b72bc-132">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b72bc-132">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b72bc-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b72bc-133">Example</span></span>  
 <span data-ttu-id="b72bc-134">Para obter um exemplo de uso desse elemento, veja [Exemplo de arquivos de entrada XML simples &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="b72bc-134">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b72bc-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b72bc-135">See Also</span></span>  
 [<span data-ttu-id="b72bc-136">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="b72bc-136">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
