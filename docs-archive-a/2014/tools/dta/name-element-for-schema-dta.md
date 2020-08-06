---
title: Elemento de nome para o esquema (DTA) | Microsoft Docs
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
ms.assetid: 014e4854-fed2-454b-8557-5f7c5bb6b17a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 678a6d58b35b25be2aed6d91fcae7ceb2640bdcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681999"
---
# <a name="name-element-for-schema-dta"></a><span data-ttu-id="32b9e-102">Elemento nome para esquema (DTA)</span><span class="sxs-lookup"><span data-stu-id="32b9e-102">Name Element for Schema (DTA)</span></span>
  <span data-ttu-id="32b9e-103">Contém o nome do esquema.</span><span class="sxs-lookup"><span data-stu-id="32b9e-103">Contains name of the schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32b9e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="32b9e-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here  
    <Schema>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="32b9e-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="32b9e-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="32b9e-106">Característica</span><span class="sxs-lookup"><span data-stu-id="32b9e-106">Characteristic</span></span>|<span data-ttu-id="32b9e-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="32b9e-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="32b9e-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="32b9e-108">**Data type and length**</span></span>|<span data-ttu-id="32b9e-109">`string`, entre 1 e 255 caracteres</span><span class="sxs-lookup"><span data-stu-id="32b9e-109">`string`, between 1 and 255 characters</span></span>|  
|<span data-ttu-id="32b9e-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="32b9e-110">**Default value**</span></span>|<span data-ttu-id="32b9e-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="32b9e-111">None.</span></span>|  
|<span data-ttu-id="32b9e-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="32b9e-112">**Occurrence**</span></span>|<span data-ttu-id="32b9e-113">Necessário uma vez por elemento de **Esquema** .</span><span class="sxs-lookup"><span data-stu-id="32b9e-113">Required once per **Schema** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="32b9e-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="32b9e-114">Element Relationships</span></span>  
  
|<span data-ttu-id="32b9e-115">Relação</span><span class="sxs-lookup"><span data-stu-id="32b9e-115">Relationship</span></span>|<span data-ttu-id="32b9e-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="32b9e-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="32b9e-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="32b9e-117">**Parent element**</span></span>|[<span data-ttu-id="32b9e-118">Elemento Schema para Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="32b9e-118">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="32b9e-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="32b9e-119">**Child elements**</span></span>|<span data-ttu-id="32b9e-120">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="32b9e-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="32b9e-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="32b9e-121">Example</span></span>  
 <span data-ttu-id="32b9e-122">Para obter um exemplo de uso desse elemento, consulte [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="32b9e-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b9e-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32b9e-123">See Also</span></span>  
 [<span data-ttu-id="32b9e-124">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="32b9e-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
