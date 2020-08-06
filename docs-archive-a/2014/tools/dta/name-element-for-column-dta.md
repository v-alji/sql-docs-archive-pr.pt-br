---
title: Elemento de nome para coluna (DTA) | Microsoft Docs
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
ms.assetid: f93b61de-01fe-4237-ada4-f1e481550564
author: stevestein
ms.author: sstein
ms.openlocfilehash: fad3d9a86a7c5db6b6a7503dc90b5a1540e3618b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678431"
---
# <a name="name-element-for-column-dta"></a><span data-ttu-id="65f86-102">Elemento de nome para coluna (DTA)</span><span class="sxs-lookup"><span data-stu-id="65f86-102">Name Element for Column (DTA)</span></span>
  <span data-ttu-id="65f86-103">Especifica o nome para uma coluna de índice em uma configuração especificada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="65f86-103">Specifies the name for an index column in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65f86-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="65f86-104">Syntax</span></span>  
  
```  
  
<Index>  
    <Column>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="65f86-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="65f86-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="65f86-106">Característica</span><span class="sxs-lookup"><span data-stu-id="65f86-106">Characteristic</span></span>|<span data-ttu-id="65f86-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="65f86-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="65f86-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="65f86-108">**Data type and length**</span></span>|<span data-ttu-id="65f86-109">`string`, comprimento ilimitado.</span><span class="sxs-lookup"><span data-stu-id="65f86-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="65f86-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="65f86-110">**Default value**</span></span>|<span data-ttu-id="65f86-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="65f86-111">None.</span></span>|  
|<span data-ttu-id="65f86-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="65f86-112">**Occurrence**</span></span>|<span data-ttu-id="65f86-113">Necessário uma vez para cada elemento `Column`.</span><span class="sxs-lookup"><span data-stu-id="65f86-113">Required once for each `Column` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="65f86-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="65f86-114">Element Relationships</span></span>  
  
|<span data-ttu-id="65f86-115">Relação</span><span class="sxs-lookup"><span data-stu-id="65f86-115">Relationship</span></span>|<span data-ttu-id="65f86-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="65f86-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="65f86-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="65f86-117">**Parent element**</span></span>|[<span data-ttu-id="65f86-118">Elemento Column para Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="65f86-118">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)|  
|<span data-ttu-id="65f86-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="65f86-119">**Child elements**</span></span>|<span data-ttu-id="65f86-120">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="65f86-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="65f86-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="65f86-121">Example</span></span>  
 <span data-ttu-id="65f86-122">Para obter um exemplo de uso desse elemento, veja [Amostra de arquivo de entrada XML com a configuração especificada pelo usuário &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="65f86-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f86-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="65f86-123">See Also</span></span>  
 [<span data-ttu-id="65f86-124">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="65f86-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
