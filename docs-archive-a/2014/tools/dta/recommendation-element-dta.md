---
title: Elemento de recomendação (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Recommendation element
ms.assetid: 679ea535-865a-4633-a4d3-5b3090515158
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4eb54a106d67f0217a2604b2d08754d0d2c0765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570417"
---
# <a name="recommendation-element-dta"></a><span data-ttu-id="3c0f2-102">Elemento de recomendação (DTA)</span><span class="sxs-lookup"><span data-stu-id="3c0f2-102">Recommendation Element (DTA)</span></span>
  <span data-ttu-id="3c0f2-103">Contém informações sobre os índices hipotéticos que integram a configuração especificada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="3c0f2-103">Contains information about the hypothetical indexes that are part of a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c0f2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3c0f2-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    ...code removed here...  
    <Table>  
      <Name>...</Name>  
      <Recommendation>  
      ...code removed here...  
      </Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="3c0f2-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="3c0f2-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="3c0f2-106">Característica</span><span class="sxs-lookup"><span data-stu-id="3c0f2-106">Characteristic</span></span>|<span data-ttu-id="3c0f2-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c0f2-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3c0f2-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="3c0f2-108">**Data type and length**</span></span>|<span data-ttu-id="3c0f2-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3c0f2-109">None.</span></span>|  
|<span data-ttu-id="3c0f2-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="3c0f2-110">**Default value**</span></span>|<span data-ttu-id="3c0f2-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3c0f2-111">None.</span></span>|  
|<span data-ttu-id="3c0f2-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="3c0f2-112">**Occurrence**</span></span>|<span data-ttu-id="3c0f2-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3c0f2-113">Optional.</span></span> <span data-ttu-id="3c0f2-114">Pode ser usado uma vez para cada elemento `Table`.</span><span class="sxs-lookup"><span data-stu-id="3c0f2-114">Can use once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="3c0f2-115">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="3c0f2-115">Element Relationships</span></span>  
  
|<span data-ttu-id="3c0f2-116">Relação</span><span class="sxs-lookup"><span data-stu-id="3c0f2-116">Relationship</span></span>|<span data-ttu-id="3c0f2-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="3c0f2-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="3c0f2-118">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="3c0f2-118">**Parent element**</span></span>|[<span data-ttu-id="3c0f2-119">Elemento Table para Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3c0f2-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="3c0f2-120">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="3c0f2-120">**Child elements**</span></span>|[<span data-ttu-id="3c0f2-121">Elemento Create &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3c0f2-121">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)<br /><br /> <span data-ttu-id="3c0f2-122">Elemento `Drop`.</span><span class="sxs-lookup"><span data-stu-id="3c0f2-122">`Drop` element.</span></span> <span data-ttu-id="3c0f2-123">Para obter mais informações, consulte o esquema XML do [Orientador de Otimização do Mecanismo de Banco de Dados](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="3c0f2-123">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c0f2-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="3c0f2-124">Remarks</span></span>  
 <span data-ttu-id="3c0f2-125">Esse elemento tem o nome **RecommendationTypecomplexType** no esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="3c0f2-125">This element is of the **RecommendationTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="3c0f2-126">É usado para especificar os índices de uma configuração hipotética.</span><span class="sxs-lookup"><span data-stu-id="3c0f2-126">It is used to specify indexes for a hypothetical configuration.</span></span> <span data-ttu-id="3c0f2-127">Não confunda esse elemento `Recommendation` com os outros tipos que podem ser usados para especificar particionamento (`RecommendationPType`) ou exibições (`RecommendationViewType`).</span><span class="sxs-lookup"><span data-stu-id="3c0f2-127">Do not confuse this `Recommendation` element with the other types that can be used to specify partitioning (`RecommendationPType`) or views (`RecommendationViewType`).</span></span> <span data-ttu-id="3c0f2-128">Para obter informações sobre esses outros `Recommendation` tipos de elemento, consulte o [Orientador de otimização do mecanismo de banco de dados esquema XML](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="3c0f2-128">For information about these other `Recommendation` element types, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c0f2-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3c0f2-129">Example</span></span>  
 <span data-ttu-id="3c0f2-130">Para obter um exemplo de uso desse elemento, veja [Exemplo de arquivo de entrada XML com configuração especificada pelo usuário (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3c0f2-130">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0f2-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3c0f2-131">See Also</span></span>  
 [<span data-ttu-id="3c0f2-132">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="3c0f2-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
