---
title: Elemento TuningOptions (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningOptions element
ms.assetid: 58a22ba1-8e03-411f-bd46-85e4540f217a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fab1c55c9d036424142b2692e8335ea65c22340
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683244"
---
# <a name="tuningoptions-element-dta"></a><span data-ttu-id="c0b8f-102">Elemento TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="c0b8f-102">TuningOptions Element (DTA)</span></span>
  <span data-ttu-id="c0b8f-103">Contém as opções de ajuste de uma sessão de ajuste específica.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-103">Contains the tuning options for a specific tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0b8f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c0b8f-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="c0b8f-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="c0b8f-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="c0b8f-106">Característica</span><span class="sxs-lookup"><span data-stu-id="c0b8f-106">Characteristic</span></span>|<span data-ttu-id="c0b8f-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="c0b8f-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c0b8f-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c0b8f-108">**Data type and length**</span></span>|<span data-ttu-id="c0b8f-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-109">None.</span></span>|  
|<span data-ttu-id="c0b8f-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="c0b8f-110">**Default value**</span></span>|<span data-ttu-id="c0b8f-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-111">None.</span></span>|  
|<span data-ttu-id="c0b8f-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="c0b8f-112">**Occurrence**</span></span>|<span data-ttu-id="c0b8f-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-113">Optional.</span></span> <span data-ttu-id="c0b8f-114">Se usado, só poderá ser usado uma vez para cada elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-114">If used, can only be used once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="c0b8f-115">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="c0b8f-115">Element Relationships</span></span>  
  
|<span data-ttu-id="c0b8f-116">Relação</span><span class="sxs-lookup"><span data-stu-id="c0b8f-116">Relationship</span></span>|<span data-ttu-id="c0b8f-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="c0b8f-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="c0b8f-118">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="c0b8f-118">**Parent element**</span></span>|[<span data-ttu-id="c0b8f-119">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b8f-119">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="c0b8f-120">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="c0b8f-120">**Child elements**</span></span>|<span data-ttu-id="c0b8f-121">Elemento `ReportSet`.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-121">`ReportSet` element.</span></span> <span data-ttu-id="c0b8f-122">Para obter mais informações, consulte o esquema XML do [Orientador de Otimização do Mecanismo de Banco de Dados](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="c0b8f-122">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="c0b8f-123">Elemento `TuningLogTable`.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-123">`TuningLogTable` element.</span></span> <span data-ttu-id="c0b8f-124">Para obter mais informações, consulte o esquema XML do [Orientador de Otimização do Mecanismo de Banco de Dados](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="c0b8f-124">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="c0b8f-125">Elemento `NumberOfEvents`.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-125">`NumberOfEvents` element.</span></span> <span data-ttu-id="c0b8f-126">Para obter mais informações, consulte o esquema XML do [Orientador de Otimização do Mecanismo de Banco de Dados](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="c0b8f-126">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> [<span data-ttu-id="c0b8f-127">Elemento TuningTimeInMin &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b8f-127">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)<br /><br /> [<span data-ttu-id="c0b8f-128">Elemento StorageBoundInMB &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b8f-128">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)<br /><br /> <span data-ttu-id="c0b8f-129">Elemento `MaxKeyColumnsInIndex`.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-129">`MaxKeyColumnsInIndex` element.</span></span> <span data-ttu-id="c0b8f-130">Para obter mais informações, consulte o esquema XML do [Orientador de Otimização do Mecanismo de Banco de Dados](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="c0b8f-130">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="c0b8f-131">Elemento `MaxColumnsInIndex`.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-131">`MaxColumnsInIndex` element.</span></span> <span data-ttu-id="c0b8f-132">Para obter mais informações, consulte o esquema XML do [Orientador de Otimização do Mecanismo de Banco de Dados](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="c0b8f-132">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="c0b8f-133">Elemento `MinPercentageImprovement`.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-133">`MinPercentageImprovement` element.</span></span> <span data-ttu-id="c0b8f-134">Para obter mais informações, consulte o esquema XML do [Orientador de Otimização do Mecanismo de Banco de Dados](https://go.microsoft.com/fwlink/?linkid=43100)</span><span class="sxs-lookup"><span data-stu-id="c0b8f-134">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100)</span></span><br /><br /> [<span data-ttu-id="c0b8f-135">Elemento TestServer &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b8f-135">TestServer Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="c0b8f-136">Elemento FeatureSet &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b8f-136">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="c0b8f-137">Elemento Partitioning &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b8f-137">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> [<span data-ttu-id="c0b8f-138">Elemento DropOnlyMode &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b8f-138">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)<br /><br /> [<span data-ttu-id="c0b8f-139">Elemento KeepExisting &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b8f-139">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)<br /><br /> [<span data-ttu-id="c0b8f-140">Elemento OnlineIndexOperation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b8f-140">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)<br /><br /> [<span data-ttu-id="c0b8f-141">Elemento DatabaseToConnect &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b8f-141">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)<br /><br /> <span data-ttu-id="c0b8f-142">Elemento `IgnoreConstantsInWorkload`.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-142">`IgnoreConstantsInWorkload` element.</span></span> <span data-ttu-id="c0b8f-143">Para obter mais informações, consulte o esquema XML do [Orientador de Otimização do Mecanismo de Banco de Dados](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="c0b8f-143">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="c0b8f-144">Elemento `RetainShellDB`.</span><span class="sxs-lookup"><span data-stu-id="c0b8f-144">`RetainShellDB` element.</span></span> <span data-ttu-id="c0b8f-145">Para obter mais informações, consulte o esquema XML do [Orientador de Otimização do Mecanismo de Banco de Dados](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="c0b8f-145">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c0b8f-146">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c0b8f-146">Example</span></span>  
 <span data-ttu-id="c0b8f-147">Para obter exemplos do `TuningOptions` elemento, consulte os [exemplos de arquivo de entrada XML &#40;DTA&#41;](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="c0b8f-147">For examples of the `TuningOptions` element, see the [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b8f-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0b8f-148">See Also</span></span>  
 [<span data-ttu-id="c0b8f-149">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b8f-149">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
