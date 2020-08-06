---
title: Elemento de tabela para esquema (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Table element [DTA]
ms.assetid: a59e8319-05d1-47f3-af39-7d970ab8e7dc
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd444b1da99b22e0259dc1f50818c1763b7052ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683254"
---
# <a name="table-element-for-schema-dta"></a><span data-ttu-id="ff25b-102">Elemento de tabela para esquema (DTA)</span><span class="sxs-lookup"><span data-stu-id="ff25b-102">Table Element for Schema (DTA)</span></span>
  <span data-ttu-id="ff25b-103">Especifica a tabela para ajuste.</span><span class="sxs-lookup"><span data-stu-id="ff25b-103">Specifies the table for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff25b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ff25b-104">Syntax</span></span>  
  
```  
  
<Schema>  
...code removed here...  
    <Table>...</Table>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="ff25b-105">Atributos do elemento</span><span class="sxs-lookup"><span data-stu-id="ff25b-105">Element Attributes</span></span>  
  
|<span data-ttu-id="ff25b-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="ff25b-106">Attribute</span></span>|<span data-ttu-id="ff25b-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="ff25b-107">Description</span></span>|  
|---------------|-----------------|  
|`NumberOfRows`|<span data-ttu-id="ff25b-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ff25b-108">Optional.</span></span> <span data-ttu-id="ff25b-109">Inteiro que permite simular tabelas de tamanhos diferentes.</span><span class="sxs-lookup"><span data-stu-id="ff25b-109">Integer that allows you to simulate tables of different sizes.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="ff25b-110">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="ff25b-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="ff25b-111">Característica</span><span class="sxs-lookup"><span data-stu-id="ff25b-111">Characteristic</span></span>|<span data-ttu-id="ff25b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="ff25b-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="ff25b-113">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ff25b-113">**Data type and length**</span></span>|<span data-ttu-id="ff25b-114">**string**, entre 1 e 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="ff25b-114">**string**, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="ff25b-115">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="ff25b-115">**Default value**</span></span>|<span data-ttu-id="ff25b-116">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ff25b-116">None.</span></span>|  
|<span data-ttu-id="ff25b-117">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="ff25b-117">**Occurrence**</span></span>|<span data-ttu-id="ff25b-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ff25b-118">Optional.</span></span> <span data-ttu-id="ff25b-119">Lista tantas tabelas quanto for apropriado para sua carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ff25b-119">List as many tables as appropriate for your workload.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="ff25b-120">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="ff25b-120">Element Relationships</span></span>  
  
|<span data-ttu-id="ff25b-121">Relação</span><span class="sxs-lookup"><span data-stu-id="ff25b-121">Relationship</span></span>|<span data-ttu-id="ff25b-122">Elementos</span><span class="sxs-lookup"><span data-stu-id="ff25b-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="ff25b-123">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="ff25b-123">**Parent element**</span></span>|[<span data-ttu-id="ff25b-124">Elemento Schema para Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="ff25b-124">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="ff25b-125">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="ff25b-125">**Child elements**</span></span>|[<span data-ttu-id="ff25b-126">Elemento Name para Table &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="ff25b-126">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="ff25b-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="ff25b-127">Remarks</span></span>  
 <span data-ttu-id="ff25b-128">Se você não especificar um elemento `Table`, o Orientador de Otimização do Mecanismo de Banco de Dados assumirá que todas as tabelas no banco de dados especificado podem ser ajustadas.</span><span class="sxs-lookup"><span data-stu-id="ff25b-128">If you do not specify a `Table` element, Database Engine Tuning Advisor will assume all tables on the specified database can be tuned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff25b-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ff25b-129">Example</span></span>  
 <span data-ttu-id="ff25b-130">Para obter um exemplo de uso, veja [Elemento Server&#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="ff25b-130">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff25b-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ff25b-131">See Also</span></span>  
 [<span data-ttu-id="ff25b-132">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="ff25b-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
