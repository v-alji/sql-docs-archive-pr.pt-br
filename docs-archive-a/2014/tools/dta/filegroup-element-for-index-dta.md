---
title: Elemento de grupo de arquivos para índice (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Filegroup element [DTA]
ms.assetid: 7078d2fb-fa77-44fc-beb3-c095088fcb85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ed8ea723d6c0798b93e16411ee47d6e956c6c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683256"
---
# <a name="filegroup-element-for-index-dta"></a><span data-ttu-id="97057-102">Elemento de grupo de arquivos para índice (DTA)</span><span class="sxs-lookup"><span data-stu-id="97057-102">Filegroup Element for Index (DTA)</span></span>
  <span data-ttu-id="97057-103">Especifica o grupo de arquivos no qual o índice será criado para uma configuração especificada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="97057-103">Specifies the filegroup on which the index is to be created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97057-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="97057-104">Syntax</span></span>  
  
```  
  
<Index>  
  <Name>...</Name>  
  <Column>  
    <Name>...</Name>  
  <Filegroup>...</Filegroup>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="97057-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="97057-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="97057-106">Característica</span><span class="sxs-lookup"><span data-stu-id="97057-106">Characteristic</span></span>|<span data-ttu-id="97057-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="97057-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="97057-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="97057-108">**Data type and length**</span></span>|<span data-ttu-id="97057-109">`string`, comprimento ilimitado.</span><span class="sxs-lookup"><span data-stu-id="97057-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="97057-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="97057-110">**Default value**</span></span>|<span data-ttu-id="97057-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="97057-111">None.</span></span>|  
|<span data-ttu-id="97057-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="97057-112">**Occurrence**</span></span>|<span data-ttu-id="97057-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="97057-113">Optional.</span></span> <span data-ttu-id="97057-114">Pode ser usado uma vez para cada elemento `Index`.</span><span class="sxs-lookup"><span data-stu-id="97057-114">Can use once for each `Index` element.</span></span> <span data-ttu-id="97057-115">Esse elemento não poderá ser usado se os elementos `PartitionScheme` e `PartitionColumn` forem especificados para o elemento `Index`.</span><span class="sxs-lookup"><span data-stu-id="97057-115">This element cannot be used if the `PartitionScheme` and `PartitionColumn` elements are specified for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="97057-116">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="97057-116">Element Relationships</span></span>  
  
|<span data-ttu-id="97057-117">Relação</span><span class="sxs-lookup"><span data-stu-id="97057-117">Relationship</span></span>|<span data-ttu-id="97057-118">Elementos</span><span class="sxs-lookup"><span data-stu-id="97057-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="97057-119">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="97057-119">**Parent element**</span></span>|[<span data-ttu-id="97057-120">Elemento Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="97057-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="97057-121">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="97057-121">**Child elements**</span></span>|<span data-ttu-id="97057-122">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="97057-122">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="97057-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="97057-123">Example</span></span>  
 <span data-ttu-id="97057-124">Para obter um exemplo de uso desse elemento, veja [Amostra de arquivo de entrada XML com a configuração especificada pelo usuário &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="97057-124">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97057-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="97057-125">See Also</span></span>  
 [<span data-ttu-id="97057-126">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="97057-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
