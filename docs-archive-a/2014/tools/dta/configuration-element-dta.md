---
title: Elemento de configuração (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Configuration element
ms.assetid: 1478e56f-57c4-4441-bac9-1ac91453839b
author: stevestein
ms.author: sstein
ms.openlocfilehash: d11938d9a9a694f994a3ea977022a393cbae23d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678455"
---
# <a name="configuration-element-dta"></a><span data-ttu-id="803c9-102">Elemento de configuração (DTA)</span><span class="sxs-lookup"><span data-stu-id="803c9-102">Configuration Element (DTA)</span></span>
  <span data-ttu-id="803c9-103">Determina uma configuração especificada pelo usuário, que consiste em estruturas existentes e hipotéticas de design físico do Orientador de Otimização do Mecanismo de Banco de Dados, para análise, quando uma carga de trabalho é analisada.</span><span class="sxs-lookup"><span data-stu-id="803c9-103">Specifies a user-specified configuration consisting of existing and hypothetical physical design structures for the Database Engine Tuning Advisor to analyze when tuning a workload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="803c9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="803c9-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>...</Server>  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions  
    <Configuration [SpecificationMode="Relative" | "Absolute"]>  
    ...code removed here...  
    </Configuration>  
</DTAInput>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="803c9-105">Atributos do elemento</span><span class="sxs-lookup"><span data-stu-id="803c9-105">Element Attributes</span></span>  
  
|<span data-ttu-id="803c9-106">Atributo de configuração</span><span class="sxs-lookup"><span data-stu-id="803c9-106">Configuration Attribute</span></span>|<span data-ttu-id="803c9-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="803c9-107">Description</span></span>|  
|-----------------------------|-----------------|  
|`SpecificationMode`|<span data-ttu-id="803c9-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="803c9-108">Optional.</span></span> <span data-ttu-id="803c9-109">Especifica se o Orientador de Otimização do Mecanismo de Banco de Dados deve analisar a configuração especificada em relação à configuração existente atual ou como configuração totalmente nova e autônoma.</span><span class="sxs-lookup"><span data-stu-id="803c9-109">Specifies whether Database Engine Tuning Advisor should analyze the specified configuration in relation to the current existing configuration, or as a completely new, standalone one.</span></span> <span data-ttu-id="803c9-110">Use um tipo de dados de **cadeia de caracteres** para especificar esse atributo com um dos seguintes valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="803c9-110">Use a **string** data type to specify this attribute with one of the following allowed values:</span></span><br /><br /> <span data-ttu-id="803c9-111">`Relative`:</span><span class="sxs-lookup"><span data-stu-id="803c9-111">`Relative`:</span></span> <br />                  <span data-ttu-id="803c9-112">Avalia a configuração especificada em relação à configuração existente atual das estruturas de design físicas (índices, exibições indexadas, particionamento) do banco de dados que está sendo ajustado.</span><span class="sxs-lookup"><span data-stu-id="803c9-112">Evaluates the specified configuration in relation to the current existing configuration of physical design structures (indexes, indexed views, partitioning) in the database that is being tuned.</span></span> <span data-ttu-id="803c9-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="803c9-113">For example:</span></span> <br />`<Configuration SpecificationMode="Relative">`<br /><br /> <span data-ttu-id="803c9-114">`Absolute`:</span><span class="sxs-lookup"><span data-stu-id="803c9-114">`Absolute`:</span></span> <br />                  <span data-ttu-id="803c9-115">Avalia a configuração especificada como uma configuração autônoma.</span><span class="sxs-lookup"><span data-stu-id="803c9-115">Evaluates the specified configuration as a standalone configuration.</span></span> <span data-ttu-id="803c9-116">Quando Absolute é especificado, o Orientador de Otimização do Mecanismo de Banco de Dados não considera a configuração existente.</span><span class="sxs-lookup"><span data-stu-id="803c9-116">When Absolute is specified, Database Engine Tuning Advisor does not consider the existing configuration.</span></span> <span data-ttu-id="803c9-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="803c9-117">For example:</span></span><br />`<Configuration SpecificationMode="Absolute">`|  
  
## <a name="element-characteristics"></a><span data-ttu-id="803c9-118">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="803c9-118">Element Characteristics</span></span>  
  
|<span data-ttu-id="803c9-119">Característica</span><span class="sxs-lookup"><span data-stu-id="803c9-119">Characteristic</span></span>|<span data-ttu-id="803c9-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="803c9-120">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="803c9-121">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="803c9-121">**Data type and length**</span></span>|<span data-ttu-id="803c9-122">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="803c9-122">None.</span></span>|  
|<span data-ttu-id="803c9-123">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="803c9-123">**Default value**</span></span>|<span data-ttu-id="803c9-124">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="803c9-124">None.</span></span>|  
|<span data-ttu-id="803c9-125">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="803c9-125">**Occurrence**</span></span>|<span data-ttu-id="803c9-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="803c9-126">Optional.</span></span> <span data-ttu-id="803c9-127">Pode ser usado uma vez para cada elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="803c9-127">Can use once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="803c9-128">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="803c9-128">Element Relationships</span></span>  
  
|<span data-ttu-id="803c9-129">Relação</span><span class="sxs-lookup"><span data-stu-id="803c9-129">Relationship</span></span>|<span data-ttu-id="803c9-130">Elementos</span><span class="sxs-lookup"><span data-stu-id="803c9-130">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="803c9-131">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="803c9-131">**Parent element**</span></span>|[<span data-ttu-id="803c9-132">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="803c9-132">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="803c9-133">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="803c9-133">**Child elements**</span></span>|[<span data-ttu-id="803c9-134">Elemento Server para Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="803c9-134">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="803c9-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="803c9-135">Example</span></span>  
 <span data-ttu-id="803c9-136">Para obter um exemplo de uso desse elemento, veja [Exemplo de arquivo de entrada XML com configuração especificada pelo usuário (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="803c9-136">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="803c9-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="803c9-137">See Also</span></span>  
 [<span data-ttu-id="803c9-138">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="803c9-138">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
