---
title: Elemento DropOnlyMode (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DropOnlyMode element
ms.assetid: 80960676-7581-4074-889b-80ee665963dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b274dc394a933308cf2161cc271d09b8391900c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678438"
---
# <a name="droponlymode-element-dta"></a><span data-ttu-id="27886-102">Elemento DropOnlyMode (DTA)</span><span class="sxs-lookup"><span data-stu-id="27886-102">DropOnlyMode Element (DTA)</span></span>
  <span data-ttu-id="27886-103">Especifica que o Orientador de Otimização do Mecanismo de Banco de Dados deve apenas considerar descartar índices, exibições indexadas ou partições existentes durante a sessão de ajuste.</span><span class="sxs-lookup"><span data-stu-id="27886-103">Specifies that Database Engine Tuning Advisor should only consider dropping existing indexes, indexed views, or partitions during the tuning session.</span></span> <span data-ttu-id="27886-104">Nenhuma nova estrutura de design físico é considerada quando esta opção de ajuste é especificada.</span><span class="sxs-lookup"><span data-stu-id="27886-104">No new physical design structures are considered when this tuning option is specified.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27886-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="27886-105">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <DropOnlyMode>...</DropOnlyMode>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="27886-106">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="27886-106">Element Characteristics</span></span>  
  
|<span data-ttu-id="27886-107">Característica</span><span class="sxs-lookup"><span data-stu-id="27886-107">Characteristic</span></span>|<span data-ttu-id="27886-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="27886-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="27886-109">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="27886-109">**Data type and length**</span></span>|<span data-ttu-id="27886-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="27886-110">None.</span></span>|  
|<span data-ttu-id="27886-111">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="27886-111">**Default value**</span></span>|<span data-ttu-id="27886-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="27886-112">None.</span></span>|  
|<span data-ttu-id="27886-113">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="27886-113">**Occurrence**</span></span>|<span data-ttu-id="27886-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="27886-114">Optional.</span></span> <span data-ttu-id="27886-115">Pode-se usar apenas uma vez para cada elemento de `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="27886-115">Can use only once for each `TuningOptions` element.</span></span> <span data-ttu-id="27886-116">Não poderá ser usado se os elementos seguintes forem especificados no elemento de `TuningOptions`:</span><span class="sxs-lookup"><span data-stu-id="27886-116">Cannot be used if the following elements are specified in the `TuningOptions` element:</span></span><br /><br /> [<span data-ttu-id="27886-117">Elemento FeatureSet &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="27886-117">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="27886-118">Elemento Partitioning &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="27886-118">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> <span data-ttu-id="27886-119">O [Elemento KeepExisting &#40;DTA&#41;](keepexisting-element-dta.md) é definido como **ALL**</span><span class="sxs-lookup"><span data-stu-id="27886-119">[KeepExisting Element &#40;DTA&#41;](keepexisting-element-dta.md) is set to **ALL**</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="27886-120">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="27886-120">Element Relationships</span></span>  
  
|<span data-ttu-id="27886-121">Relação</span><span class="sxs-lookup"><span data-stu-id="27886-121">Relationship</span></span>|<span data-ttu-id="27886-122">Elementos</span><span class="sxs-lookup"><span data-stu-id="27886-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="27886-123">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="27886-123">**Parent element**</span></span>|[<span data-ttu-id="27886-124">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="27886-124">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="27886-125">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="27886-125">**Child elements**</span></span>|<span data-ttu-id="27886-126">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="27886-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="27886-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="27886-127">Example</span></span>  
 <span data-ttu-id="27886-128">O exemplo seguinte mostra a seção `TuningOptions` de um arquivo de entrada do Orientador de Otimização do Mecanismo de Banco de Dados XML onde o `DropOnlyMode` é especificado.</span><span class="sxs-lookup"><span data-stu-id="27886-128">The following example shows the `TuningOptions` section of a Database Engine Tuning Advisor XML input file where the `DropOnlyMode` is specified.</span></span> <span data-ttu-id="27886-129">Nesse exemplo a hora de ajuste é limitada a 24 horas (1440 minutos) e todos os índices clusterizados e não clusterizados existentes serão considerados para o descarte:</span><span class="sxs-lookup"><span data-stu-id="27886-129">In this example the tuning time is limited to 24 hours (1440 minutes) and all existing clustered and nonclustered indexes will be considered for dropping:</span></span>  
  
```xml  
<TuningOptions  
  <TuningTimeInMin>1440</Name>  
  <KeepExisting>ALIGNED</KeepExisting>  
  <DropOnlyMode />  
</TuningOptions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="27886-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="27886-130">See Also</span></span>  
 [<span data-ttu-id="27886-131">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="27886-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
