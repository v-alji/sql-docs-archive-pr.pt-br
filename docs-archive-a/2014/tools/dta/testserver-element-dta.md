---
title: Elemento TestServer (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TestServer element
ms.assetid: caa3547a-2cd5-47ad-ace2-a36752835cfe
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d1f1fadf76a43caca262652254e8a778602183c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683255"
---
# <a name="testserver-element-dta"></a><span data-ttu-id="5be57-102">Elemento TestServer (DTA)</span><span class="sxs-lookup"><span data-stu-id="5be57-102">TestServer Element (DTA)</span></span>
  <span data-ttu-id="5be57-103">Especifica o servidor de teste para ser usado ao ajustar um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="5be57-103">Specifies the test server to use when tuning a production server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be57-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5be57-104">Syntax</span></span>  
  
```  
  
<TuningOptions>  
  <TestServer>...</TestServer>  
   ...code removed here...  
</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="5be57-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="5be57-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="5be57-106">Característica</span><span class="sxs-lookup"><span data-stu-id="5be57-106">Characteristic</span></span>|<span data-ttu-id="5be57-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="5be57-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5be57-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5be57-108">**Data type and length**</span></span>|<span data-ttu-id="5be57-109">**string**, comprimento ilimitado.</span><span class="sxs-lookup"><span data-stu-id="5be57-109">**string**, unlimited length.</span></span>|  
|<span data-ttu-id="5be57-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="5be57-110">**Default value**</span></span>|<span data-ttu-id="5be57-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5be57-111">None.</span></span>|  
|<span data-ttu-id="5be57-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="5be57-112">**Occurrence**</span></span>|<span data-ttu-id="5be57-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5be57-113">Optional.</span></span> <span data-ttu-id="5be57-114">Pode ser usado uma vez para cada elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="5be57-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="5be57-115">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="5be57-115">Element Relationships</span></span>  
  
|<span data-ttu-id="5be57-116">Relação</span><span class="sxs-lookup"><span data-stu-id="5be57-116">Relationship</span></span>|<span data-ttu-id="5be57-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="5be57-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="5be57-118">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="5be57-118">**Parent element**</span></span>|[<span data-ttu-id="5be57-119">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="5be57-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="5be57-120">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="5be57-120">**Child elements**</span></span>|<span data-ttu-id="5be57-121">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5be57-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5be57-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5be57-122">Example</span></span>  
 <span data-ttu-id="5be57-123">Para obter um exemplo de uso desse elemento, veja [Reduzir a carga de ajuste do servidor de produção](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span><span class="sxs-lookup"><span data-stu-id="5be57-123">For a usage example of this element, see [Reduce the Production Server Tuning Load](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5be57-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5be57-124">See Also</span></span>  
 [<span data-ttu-id="5be57-125">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="5be57-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
