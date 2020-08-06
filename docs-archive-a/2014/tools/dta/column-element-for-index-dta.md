---
title: Elemento Column para index (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Column element
ms.assetid: ba9fac20-26bd-4333-940e-842c15241b46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67853dc7d1193d3a0f80e56023846bc55a20bdaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678457"
---
# <a name="column-element-for-index-dta"></a><span data-ttu-id="7434f-102">Elemento de coluna para índice (DTA)</span><span class="sxs-lookup"><span data-stu-id="7434f-102">Column Element for Index (DTA)</span></span>
  <span data-ttu-id="7434f-103">Especifica as colunas onde o índice é criado para uma configuração especificada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7434f-103">Specifies the columns on which the index is created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7434f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7434f-104">Syntax</span></span>  
  
```  
  
<Create>  
  <Index>  
    <Name>...</Name>  
    <Column [Type | SortOrder]>  
     ...code removed here...  
     </Column>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="7434f-105">Atributos do elemento</span><span class="sxs-lookup"><span data-stu-id="7434f-105">Element Attributes</span></span>  
  
|<span data-ttu-id="7434f-106">Atributo da coluna</span><span class="sxs-lookup"><span data-stu-id="7434f-106">Column Attribute</span></span>|<span data-ttu-id="7434f-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="7434f-107">Description</span></span>|  
|----------------------|-----------------|  
|`Type`|<span data-ttu-id="7434f-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7434f-108">Optional.</span></span> <span data-ttu-id="7434f-109">Especifica o tipo de coluna de índice.</span><span class="sxs-lookup"><span data-stu-id="7434f-109">Specifies the index column type.</span></span> <span data-ttu-id="7434f-110">Use um tipo de dados de **cadeia de caracteres** para especificar esse atributo com um dos seguintes valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="7434f-110">Use a **string** data type to specify this attribute with one of the following allowed values:</span></span><br /><br /> <span data-ttu-id="7434f-111">`KeyColumn`:</span><span class="sxs-lookup"><span data-stu-id="7434f-111">`KeyColumn`:</span></span><br />                  <span data-ttu-id="7434f-112">Especifica que a coluna é referenciada por uma chave de índice.</span><span class="sxs-lookup"><span data-stu-id="7434f-112">Specifies that the column is referenced by an index key.</span></span> <span data-ttu-id="7434f-113">Use a sintaxe a seguir para definir esse atributo:</span><span class="sxs-lookup"><span data-stu-id="7434f-113">Use the following syntax to set this attribute:</span></span><br />`<Column Type="KeyColumn">`<br /><span data-ttu-id="7434f-114">Para obter mais informações sobre colunas de chave, veja [Índices clusterizados e não clusterizados descritos](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="7434f-114">For more information about key columns, see [Clustered and Nonclustered Indexes Described](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span></span><br /><br /> <span data-ttu-id="7434f-115">`IncludedColumn`: Especifica que a coluna é uma coluna incluída (em vez de uma coluna de chave).</span><span class="sxs-lookup"><span data-stu-id="7434f-115">`IncludedColumn`: Specifies that the column is an included column (instead of a key column).</span></span> <span data-ttu-id="7434f-116">Use a sintaxe a seguir para definir esse atributo:</span><span class="sxs-lookup"><span data-stu-id="7434f-116">Use the following syntax to set this attribute:</span></span><br />`<Column Type="IncludedColumn">`<br /><span data-ttu-id="7434f-117">Para obter mais informações sobre colunas incluídas, veja [Criar índices com colunas incluídas](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="7434f-117">For more information about included columns, see [Create Indexes with Included Columns](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span></span>|  
|`SortOrder`|<span data-ttu-id="7434f-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7434f-118">Optional.</span></span> <span data-ttu-id="7434f-119">Especifica a ordem de escolha da coluna.</span><span class="sxs-lookup"><span data-stu-id="7434f-119">Specifies the sorting order of the column.</span></span> <span data-ttu-id="7434f-120">Use um tipo de dados **de cadeia de caracteres** para especificar uma ordem **"Crescente"** ou **"Decrescente"** como segue:</span><span class="sxs-lookup"><span data-stu-id="7434f-120">Use a **string** data type to specify either an **"Ascending"** or **"Descending"** sorting order as follows:</span></span><br /><br /> `<Column SortOrder="Ascending">`|  
  
## <a name="element-characteristics"></a><span data-ttu-id="7434f-121">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="7434f-121">Element Characteristics</span></span>  
  
|<span data-ttu-id="7434f-122">Característica</span><span class="sxs-lookup"><span data-stu-id="7434f-122">Characteristic</span></span>|<span data-ttu-id="7434f-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="7434f-123">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7434f-124">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="7434f-124">**Data type and length**</span></span>|<span data-ttu-id="7434f-125">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7434f-125">None.</span></span>|  
|<span data-ttu-id="7434f-126">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="7434f-126">**Default value**</span></span>|<span data-ttu-id="7434f-127">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7434f-127">None.</span></span>|  
|<span data-ttu-id="7434f-128">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="7434f-128">**Occurrence**</span></span>|<span data-ttu-id="7434f-129">Pode especificar até 1024 colunas para o elemento `Index`.</span><span class="sxs-lookup"><span data-stu-id="7434f-129">Can specify up to 1024 columns for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="7434f-130">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="7434f-130">Element Relationships</span></span>  
  
|<span data-ttu-id="7434f-131">Relação</span><span class="sxs-lookup"><span data-stu-id="7434f-131">Relationship</span></span>|<span data-ttu-id="7434f-132">Elementos</span><span class="sxs-lookup"><span data-stu-id="7434f-132">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="7434f-133">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="7434f-133">**Parent element**</span></span>|[<span data-ttu-id="7434f-134">Elemento Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="7434f-134">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="7434f-135">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="7434f-135">**Child elements**</span></span>|[<span data-ttu-id="7434f-136">Elemento Name para coluna &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="7434f-136">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="7434f-137">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7434f-137">Example</span></span>  
 <span data-ttu-id="7434f-138">Para obter um exemplo de uso desse elemento, veja [Exemplo de arquivo de entrada XML com configuração especificada pelo usuário (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="7434f-138">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7434f-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7434f-139">See Also</span></span>  
 [<span data-ttu-id="7434f-140">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="7434f-140">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
