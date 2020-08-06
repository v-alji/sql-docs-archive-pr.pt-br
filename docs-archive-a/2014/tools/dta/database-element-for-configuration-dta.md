---
title: Elemento de banco de dados para configuração (DTA) | Microsoft Docs
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
ms.assetid: e91ba243-6cc9-457a-8f5a-134f3c71ae69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 69ce1a0ac9912907f6d22916dd6243621e0778db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678443"
---
# <a name="database-element-for-configuration-dta"></a><span data-ttu-id="a5aaa-102">Elemento de banco de dados para configuração (DTA)</span><span class="sxs-lookup"><span data-stu-id="a5aaa-102">Database Element for Configuration (DTA)</span></span>
  <span data-ttu-id="a5aaa-103">Especifica o banco de dados em relação ao qual você deseja que o Orientador de Otimização do Mecanismo de Banco de Dados avalie a configuração hipotética (especificada pelo elemento`Configuration` ).</span><span class="sxs-lookup"><span data-stu-id="a5aaa-103">Specifies the database against which you want the Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5aaa-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a5aaa-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="a5aaa-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="a5aaa-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="a5aaa-106">Característica</span><span class="sxs-lookup"><span data-stu-id="a5aaa-106">Characteristic</span></span>|<span data-ttu-id="a5aaa-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5aaa-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a5aaa-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a5aaa-108">**Data type and length**</span></span>|<span data-ttu-id="a5aaa-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a5aaa-109">None.</span></span>|  
|<span data-ttu-id="a5aaa-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="a5aaa-110">**Default value**</span></span>|<span data-ttu-id="a5aaa-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a5aaa-111">None.</span></span>|  
|<span data-ttu-id="a5aaa-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="a5aaa-112">**Occurrence**</span></span>|<span data-ttu-id="a5aaa-113">Exigido uma ou mais vezes por elemento `Server`.</span><span class="sxs-lookup"><span data-stu-id="a5aaa-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="a5aaa-114">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="a5aaa-114">Element Relationships</span></span>  
  
|<span data-ttu-id="a5aaa-115">Relação</span><span class="sxs-lookup"><span data-stu-id="a5aaa-115">Relationship</span></span>|<span data-ttu-id="a5aaa-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="a5aaa-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="a5aaa-117">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="a5aaa-117">**Parent element**</span></span>|[<span data-ttu-id="a5aaa-118">Elemento Server para Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a5aaa-118">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)|  
|<span data-ttu-id="a5aaa-119">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="a5aaa-119">**Child elements**</span></span>|[<span data-ttu-id="a5aaa-120">Elemento Name para Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a5aaa-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="a5aaa-121">Elemento Schema para Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a5aaa-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="a5aaa-122">Elemento Recommendation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a5aaa-122">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="a5aaa-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="a5aaa-123">Remarks</span></span>  
 <span data-ttu-id="a5aaa-124">Esse elemento tem o nome **DatabaseTypecomplexType** no esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="a5aaa-124">This element is of the **DatabaseTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="a5aaa-125">Não confunda esse elemento `Database` com o elemento cujo pai raiz é o elemento `Server` que ocorre no topo do arquivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="a5aaa-125">Do not confuse this `Database` element with the one whose root parent is the `Server` element, which occurs at the top of the XML input file.</span></span> <span data-ttu-id="a5aaa-126">Para obter mais informações, veja [Elemento Database para servidor &#40;DTA&#41;](database-element-for-server-dta.md).</span><span class="sxs-lookup"><span data-stu-id="a5aaa-126">For more information, see [Database Element for Server &#40;DTA&#41;](database-element-for-server-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5aaa-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a5aaa-127">Example</span></span>  
 <span data-ttu-id="a5aaa-128">Para obter um exemplo de uso desse `Database` elemento, consulte a [amostra do arquivo de entrada XML com a configuração especificada pelo usuário &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="a5aaa-128">For a usage example of this `Database` element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5aaa-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a5aaa-129">See Also</span></span>  
 [<span data-ttu-id="a5aaa-130">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="a5aaa-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
