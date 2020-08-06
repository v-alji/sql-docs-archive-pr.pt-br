---
title: Elemento de banco de dados para servidor (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: 5cd9a87a-af4b-45f3-8c18-f7fd7e7d3064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9a48d255898eff6bd780f8edf2c8d2da7229b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678442"
---
# <a name="database-element-for-server-dta"></a><span data-ttu-id="27ef5-102">Elemento de banco de dados para servidor (DTA)</span><span class="sxs-lookup"><span data-stu-id="27ef5-102">Database Element for Server (DTA)</span></span>
  <span data-ttu-id="27ef5-103">Especifica o banco de dados que deseja ajustar em um servidor específico.</span><span class="sxs-lookup"><span data-stu-id="27ef5-103">Specifies the database you want to tune on a specific server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27ef5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="27ef5-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="27ef5-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="27ef5-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="27ef5-106">Característica</span><span class="sxs-lookup"><span data-stu-id="27ef5-106">Characteristic</span></span>|<span data-ttu-id="27ef5-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="27ef5-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="27ef5-108">Comprimento e tipo de dados</span><span class="sxs-lookup"><span data-stu-id="27ef5-108">Data type and length</span></span>|<span data-ttu-id="27ef5-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="27ef5-109">None.</span></span>|  
|<span data-ttu-id="27ef5-110">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="27ef5-110">Default value</span></span>|<span data-ttu-id="27ef5-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="27ef5-111">None.</span></span>|  
|<span data-ttu-id="27ef5-112">Ocorrência</span><span class="sxs-lookup"><span data-stu-id="27ef5-112">Occurrence</span></span>|<span data-ttu-id="27ef5-113">Exigido uma ou mais vezes por elemento `Server`.</span><span class="sxs-lookup"><span data-stu-id="27ef5-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="27ef5-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="27ef5-114">Element Relationships</span></span>  
  
|<span data-ttu-id="27ef5-115">Relação</span><span class="sxs-lookup"><span data-stu-id="27ef5-115">Relationship</span></span>|<span data-ttu-id="27ef5-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="27ef5-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="27ef5-117">Elemento pai</span><span class="sxs-lookup"><span data-stu-id="27ef5-117">Parent element</span></span>|[<span data-ttu-id="27ef5-118">Elemento Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="27ef5-118">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)|  
|<span data-ttu-id="27ef5-119">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="27ef5-119">Child elements</span></span>|[<span data-ttu-id="27ef5-120">Elemento Name para Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="27ef5-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="27ef5-121">Elemento Schema para Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="27ef5-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="27ef5-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="27ef5-122">Remarks</span></span>  
 <span data-ttu-id="27ef5-123">Esse elemento tem o nome **DatabaseDetailsTypecomplexType** no Esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="27ef5-123">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="27ef5-124">Não confunda este elemento do `Database` com aquele cujo pai raiz é o elemento `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="27ef5-124">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="27ef5-125">Para obter mais informações, veja [Elemento Database para configuração &#40;DTA&#41;](database-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="27ef5-125">For more information, see [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="27ef5-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="27ef5-126">Example</span></span>  
 <span data-ttu-id="27ef5-127">Para obter um exemplo de uso do `Database` elemento, consulte [elemento de servidor &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="27ef5-127">For a usage example of the `Database` element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ef5-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="27ef5-128">See Also</span></span>  
 [<span data-ttu-id="27ef5-129">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="27ef5-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
