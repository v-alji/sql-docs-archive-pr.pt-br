---
title: Elemento de nome para o índice (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Name element
ms.assetid: 2300e9cf-f0a8-49e6-b1f5-45ffe03ccb5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: a878923a3d483fae5ad6b55421a2b286f15ceb29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684957"
---
# <a name="name-element-for-index-dta"></a><span data-ttu-id="95513-102">Elemento de nome para índice (DTA)</span><span class="sxs-lookup"><span data-stu-id="95513-102">Name Element for Index (DTA)</span></span>
  <span data-ttu-id="95513-103">Especifica um nome para um índice na configuração especificada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="95513-103">Specifies a name for an index in the user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95513-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="95513-104">Syntax</span></span>  
  
```  
  
<Create>  
    <Index>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="95513-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="95513-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="95513-106">Característica</span><span class="sxs-lookup"><span data-stu-id="95513-106">Characteristic</span></span>|<span data-ttu-id="95513-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="95513-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="95513-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="95513-108">**Data type and length**</span></span>|<span data-ttu-id="95513-109">`string`, comprimento ilimitado.</span><span class="sxs-lookup"><span data-stu-id="95513-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="95513-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="95513-110">**Default value**</span></span>|<span data-ttu-id="95513-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="95513-111">None.</span></span>|  
|<span data-ttu-id="95513-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="95513-112">**Occurrence**</span></span>|<span data-ttu-id="95513-113">Necessário uma vez para cada elemento `Index`.</span><span class="sxs-lookup"><span data-stu-id="95513-113">Required once for each `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="95513-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="95513-114">Element Relationships</span></span>  
  
|<span data-ttu-id="95513-115">Relação</span><span class="sxs-lookup"><span data-stu-id="95513-115">Relationship</span></span>|<span data-ttu-id="95513-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="95513-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="95513-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="95513-117">**Parent element**</span></span>|[<span data-ttu-id="95513-118">Elemento Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="95513-118">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="95513-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="95513-119">**Child elements**</span></span>|<span data-ttu-id="95513-120">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="95513-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="95513-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="95513-121">Example</span></span>  
 <span data-ttu-id="95513-122">Para obter um exemplo de uso desse elemento, veja [Amostra de arquivo de entrada XML com a configuração especificada pelo usuário &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="95513-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95513-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="95513-123">See Also</span></span>  
 [<span data-ttu-id="95513-124">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="95513-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
