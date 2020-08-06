---
title: Elemento TuningTimeInMin (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningTimeInMin element
ms.assetid: 4973d9ac-20fd-4ac3-bc9f-5d60e39fdb7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4dae3fe4e9ac3126f43ec017c34d2bc548fda6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683243"
---
# <a name="tuningtimeinmin-element-dta"></a><span data-ttu-id="de28f-102">Elemento TuningTimeInMin (DTA)</span><span class="sxs-lookup"><span data-stu-id="de28f-102">TuningTimeInMin Element (DTA)</span></span>
  <span data-ttu-id="de28f-103">Especifica o comprimento máximo de uma sessão de ajuste em minutos.</span><span class="sxs-lookup"><span data-stu-id="de28f-103">Specifies the maximum length of a tuning session in minutes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de28f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="de28f-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <TuningTimeInMin>...</TuningTimeInMin>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="de28f-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="de28f-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="de28f-106">Característica</span><span class="sxs-lookup"><span data-stu-id="de28f-106">Characteristic</span></span>|<span data-ttu-id="de28f-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="de28f-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="de28f-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="de28f-108">**Data type and length**</span></span>|<span data-ttu-id="de28f-109">`unsignedInt`, comprimento ilimitado.</span><span class="sxs-lookup"><span data-stu-id="de28f-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="de28f-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="de28f-110">**Default value**</span></span>|<span data-ttu-id="de28f-111">480 minutos (8 horas).</span><span class="sxs-lookup"><span data-stu-id="de28f-111">480 minutes (8 hours).</span></span>|  
|<span data-ttu-id="de28f-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="de28f-112">**Occurrence**</span></span>|<span data-ttu-id="de28f-113">Exigido, exceto se houver valor especificado para o elemento `NumberOfEvents`.</span><span class="sxs-lookup"><span data-stu-id="de28f-113">Required unless a value has been specified for the `NumberOfEvents` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="de28f-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="de28f-114">Element Relationships</span></span>  
  
|<span data-ttu-id="de28f-115">Relação</span><span class="sxs-lookup"><span data-stu-id="de28f-115">Relationship</span></span>|<span data-ttu-id="de28f-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="de28f-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="de28f-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="de28f-117">**Parent element**</span></span>|[<span data-ttu-id="de28f-118">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="de28f-118">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="de28f-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="de28f-119">**Child elements**</span></span>|<span data-ttu-id="de28f-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="de28f-120">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="de28f-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="de28f-121">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="de28f-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="de28f-122">Description</span></span>  
 <span data-ttu-id="de28f-123">O exemplo de código a seguir mostra como definir 12 horas como tempo máximo de ajuste:</span><span class="sxs-lookup"><span data-stu-id="de28f-123">The following code example shows how to set 12 hours as the maximum tuning time:</span></span>  
  
## <a name="code"></a><span data-ttu-id="de28f-124">Código</span><span class="sxs-lookup"><span data-stu-id="de28f-124">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <TuningTimeInMin>720</TuningTimeInMin>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de28f-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de28f-125">See Also</span></span>  
 [<span data-ttu-id="de28f-126">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="de28f-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
