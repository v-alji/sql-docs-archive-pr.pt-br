---
title: Elemento de nome para banco de dados (DTA) | Microsoft Docs
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
ms.assetid: e871c4fa-3b57-46cf-b4f8-e3be86f92dc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: c692e31b9175bf05dcfb0504ea79e98cbb82f36b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678425"
---
# <a name="name-element-for-database-dta"></a><span data-ttu-id="b0cb2-102">Elemento de nome para o banco de dados (DTA)</span><span class="sxs-lookup"><span data-stu-id="b0cb2-102">Name Element for Database (DTA)</span></span>
  <span data-ttu-id="b0cb2-103">Especifica o nome de um banco de dados que você deseja ajustar.</span><span class="sxs-lookup"><span data-stu-id="b0cb2-103">Specifies the name of a database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0cb2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b0cb2-104">Syntax</span></span>  
  
```  
  
<Server>  
    <Database>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="b0cb2-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="b0cb2-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="b0cb2-106">Característica</span><span class="sxs-lookup"><span data-stu-id="b0cb2-106">Characteristic</span></span>|<span data-ttu-id="b0cb2-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="b0cb2-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b0cb2-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b0cb2-108">**Data type and length**</span></span>|<span data-ttu-id="b0cb2-109">`string`, comprimento ilimitado.</span><span class="sxs-lookup"><span data-stu-id="b0cb2-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="b0cb2-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="b0cb2-110">**Default value**</span></span>|<span data-ttu-id="b0cb2-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b0cb2-111">None.</span></span>|  
|<span data-ttu-id="b0cb2-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="b0cb2-112">**Occurrence**</span></span>|<span data-ttu-id="b0cb2-113">Obrigatório uma vez por elemento `Database`.</span><span class="sxs-lookup"><span data-stu-id="b0cb2-113">Required once per `Database` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="b0cb2-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="b0cb2-114">Element Relationships</span></span>  
  
|<span data-ttu-id="b0cb2-115">Relação</span><span class="sxs-lookup"><span data-stu-id="b0cb2-115">Relationship</span></span>|<span data-ttu-id="b0cb2-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="b0cb2-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="b0cb2-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="b0cb2-117">**Parent element**</span></span>|[<span data-ttu-id="b0cb2-118">Elemento Database para Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b0cb2-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="b0cb2-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="b0cb2-119">**Child elements**</span></span>|<span data-ttu-id="b0cb2-120">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b0cb2-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b0cb2-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b0cb2-121">Example</span></span>  
 <span data-ttu-id="b0cb2-122">Para obter um exemplo de uso desse elemento, consulte [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="b0cb2-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0cb2-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b0cb2-123">See Also</span></span>  
 [<span data-ttu-id="b0cb2-124">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="b0cb2-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
