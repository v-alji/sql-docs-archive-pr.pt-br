---
title: Elemento de esquema para banco de dados (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Schema element
ms.assetid: d932e59c-953f-4ab4-934d-b6baf344835c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7653177878f3a832abd2d1ca266bc5feb17b9a29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570416"
---
# <a name="schema-element-for-database-dta"></a><span data-ttu-id="a688a-102">Elemento de esquema para banco de dados (DTA)</span><span class="sxs-lookup"><span data-stu-id="a688a-102">Schema Element for Database (DTA)</span></span>
  <span data-ttu-id="a688a-103">Especifica o esquema do banco de dados que você deseja ajustar.</span><span class="sxs-lookup"><span data-stu-id="a688a-103">Specifies the schema of the database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a688a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a688a-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here...  
    <Schema>...</Schema>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="a688a-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="a688a-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="a688a-106">Característica</span><span class="sxs-lookup"><span data-stu-id="a688a-106">Characteristic</span></span>|<span data-ttu-id="a688a-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="a688a-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a688a-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a688a-108">**Data type and length**</span></span>|<span data-ttu-id="a688a-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a688a-109">None.</span></span>|  
|<span data-ttu-id="a688a-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="a688a-110">**Default value**</span></span>|<span data-ttu-id="a688a-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a688a-111">None.</span></span>|  
|<span data-ttu-id="a688a-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="a688a-112">**Occurrence**</span></span>|<span data-ttu-id="a688a-113">Exigido uma vez para o elemento do **Banco de Dados** especificado no elemento **Servidor** .</span><span class="sxs-lookup"><span data-stu-id="a688a-113">Required once for the **Database** element that is specified under the **Server** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="a688a-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="a688a-114">Element Relationships</span></span>  
  
|<span data-ttu-id="a688a-115">Relação</span><span class="sxs-lookup"><span data-stu-id="a688a-115">Relationship</span></span>|<span data-ttu-id="a688a-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="a688a-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="a688a-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="a688a-117">**Parent element**</span></span>|[<span data-ttu-id="a688a-118">Elemento Database para Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a688a-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="a688a-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="a688a-119">**Child elements**</span></span>|[<span data-ttu-id="a688a-120">Elemento Name para Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a688a-120">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)<br /><br /> [<span data-ttu-id="a688a-121">Elemento Table para Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a688a-121">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="a688a-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a688a-122">Example</span></span>  
 <span data-ttu-id="a688a-123">Para obter um exemplo de uso desse elemento, consulte [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="a688a-123">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a688a-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a688a-124">See Also</span></span>  
 [<span data-ttu-id="a688a-125">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="a688a-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
