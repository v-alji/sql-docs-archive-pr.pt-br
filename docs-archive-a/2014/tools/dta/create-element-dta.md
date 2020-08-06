---
title: Elemento Create (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Create element (DTA)
ms.assetid: 9d076c90-f933-45f4-b6d9-447793f6528b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 407f16c3898e56cd393e36c39ed799b83e0092ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678445"
---
# <a name="create-element-dta"></a><span data-ttu-id="29d35-102">Criar elemento (DTA)</span><span class="sxs-lookup"><span data-stu-id="29d35-102">Create Element (DTA)</span></span>
  <span data-ttu-id="29d35-103">Contém informações sobre estruturas de índices, estatísticas e de heap em uma configuração especificada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="29d35-103">Contains information about the indexes, statistics, or heap structures in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29d35-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="29d35-104">Syntax</span></span>  
  
```  
  
<Recommendation>  
    <Create>  
    ...code removed here...  
    </Create>  
</Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="29d35-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="29d35-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="29d35-106">Característica</span><span class="sxs-lookup"><span data-stu-id="29d35-106">Characteristic</span></span>|<span data-ttu-id="29d35-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="29d35-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="29d35-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="29d35-108">**Data type and length**</span></span>|<span data-ttu-id="29d35-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="29d35-109">None.</span></span>|  
|<span data-ttu-id="29d35-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="29d35-110">**Default value**</span></span>|<span data-ttu-id="29d35-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="29d35-111">None.</span></span>|  
|<span data-ttu-id="29d35-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="29d35-112">**Occurrence**</span></span>|<span data-ttu-id="29d35-113">Necessária uma vez para cada tipo de estrutura física de design (estruturas de índices, estatísticas ou de heap).</span><span class="sxs-lookup"><span data-stu-id="29d35-113">Required once for each physical design structure type (indexes, statistics, or heap structures).</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="29d35-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="29d35-114">Element Relationships</span></span>  
  
|<span data-ttu-id="29d35-115">Relação</span><span class="sxs-lookup"><span data-stu-id="29d35-115">Relationship</span></span>|<span data-ttu-id="29d35-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="29d35-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="29d35-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="29d35-117">**Parent element**</span></span>|[<span data-ttu-id="29d35-118">Elemento Recommendation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="29d35-118">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
|<span data-ttu-id="29d35-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="29d35-119">**Child elements**</span></span>|[<span data-ttu-id="29d35-120">Elemento Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="29d35-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)<br /><br /> <span data-ttu-id="29d35-121">`Statistics`Elemento (consulte [Orientador de otimização do mecanismo de banco de dados esquema XML](https://schemas.microsoft.com/sqlserver/) para obter informações)</span><span class="sxs-lookup"><span data-stu-id="29d35-121">`Statistics` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span><br /><br /> <span data-ttu-id="29d35-122">`Heap`Elemento (consulte [Orientador de otimização do mecanismo de banco de dados esquema XML](https://schemas.microsoft.com/sqlserver/) para obter informações)</span><span class="sxs-lookup"><span data-stu-id="29d35-122">`Heap` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29d35-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="29d35-123">Remarks</span></span>  
 <span data-ttu-id="29d35-124">Esse elemento tem o nome **CreateTypecomplexType** no esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="29d35-124">This element is of the **CreateTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="29d35-125">É usado criar estruturas de índices, estatísticas e de heap em uma configuração especificada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="29d35-125">It is used to create indexes, statistics, and heap structures for a user-specified configuration.</span></span> <span data-ttu-id="29d35-126">Não confunda esse elemento `Create` com os outros tipos que podem ser usados para criar exibições (`CreateViewType`) ou particionamento (`CreatePType`).</span><span class="sxs-lookup"><span data-stu-id="29d35-126">Do not confuse this `Create` element with the other types that can be used to create views (`CreateViewType`) or partitioning (`CreatePType`).</span></span> <span data-ttu-id="29d35-127">Consulte o [Orientador de otimização do mecanismo de banco de dados esquema XML](https://schemas.microsoft.com/sqlserver/) para obter informações sobre esses outros `Create` tipos de elemento.</span><span class="sxs-lookup"><span data-stu-id="29d35-127">Refer to the [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information about these other `Create` element types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29d35-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="29d35-128">Example</span></span>  
 <span data-ttu-id="29d35-129">Para obter um exemplo de uso desse elemento, veja [Exemplo de arquivo de entrada XML com configuração especificada pelo usuário (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="29d35-129">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d35-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29d35-130">See Also</span></span>  
 [<span data-ttu-id="29d35-131">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="29d35-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
