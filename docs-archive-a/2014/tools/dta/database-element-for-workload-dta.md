---
title: Elemento de banco de dados para carga de trabalho (DTA) | Microsoft Docs
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
ms.assetid: 112fca2a-37e5-4162-b2e7-b56eb8ab0c6f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2774bc7ed981c84c966a394c95347208cbc6d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678444"
---
# <a name="database-element-for-workload-dta"></a><span data-ttu-id="c6633-102">Elemento de banco de dados para carga de trabalho (DTA)</span><span class="sxs-lookup"><span data-stu-id="c6633-102">Database Element for Workload (DTA)</span></span>
  <span data-ttu-id="c6633-103">Especifica o banco de dados em que se encontra a tabela de rastreamento da carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c6633-103">Specifies the database where the workload trace table is located.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6633-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c6633-104">Syntax</span></span>  
  
```  
  
<Workload>  
  <Database>  
   ...code removed here...  
  </Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="c6633-105">Características do elemento</span><span class="sxs-lookup"><span data-stu-id="c6633-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="c6633-106">Característica</span><span class="sxs-lookup"><span data-stu-id="c6633-106">Characteristic</span></span>|<span data-ttu-id="c6633-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="c6633-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c6633-108">**Comprimento e tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c6633-108">**Data type and length**</span></span>|<span data-ttu-id="c6633-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c6633-109">None.</span></span>|  
|<span data-ttu-id="c6633-110">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="c6633-110">**Default value**</span></span>|<span data-ttu-id="c6633-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c6633-111">None.</span></span>|  
|<span data-ttu-id="c6633-112">**Ocorrência**</span><span class="sxs-lookup"><span data-stu-id="c6633-112">**Occurrence**</span></span>|<span data-ttu-id="c6633-113">Exigido uma vez se não houver outro tipo de carga de trabalho especificada.</span><span class="sxs-lookup"><span data-stu-id="c6633-113">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="c6633-114">É preciso especificar um elemento filho `EventString`, `File` ou  `Database` para o pai `Workload`, mas só pode ser usado um tipo.</span><span class="sxs-lookup"><span data-stu-id="c6633-114">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="c6633-115">Por exemplo, se uma carga de trabalho com o elemento `Database` for especificada, não será possível especificar uma carga de trabalho com o elemento `File` no mesmo arquivo XML de entrada.</span><span class="sxs-lookup"><span data-stu-id="c6633-115">For example, if you specify a workload with the `Database` element, you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="c6633-116">Relações do elemento</span><span class="sxs-lookup"><span data-stu-id="c6633-116">Element Relationships</span></span>  
  
|<span data-ttu-id="c6633-117">Relação</span><span class="sxs-lookup"><span data-stu-id="c6633-117">Relationship</span></span>|<span data-ttu-id="c6633-118">Elementos</span><span class="sxs-lookup"><span data-stu-id="c6633-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="c6633-119">**Elemento pai**</span><span class="sxs-lookup"><span data-stu-id="c6633-119">**Parent element**</span></span>|[<span data-ttu-id="c6633-120">Elemento Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c6633-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="c6633-121">**Elementos filho**</span><span class="sxs-lookup"><span data-stu-id="c6633-121">**Child elements**</span></span>|[<span data-ttu-id="c6633-122">Elemento Name para Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c6633-122">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="c6633-123">Elemento Schema para Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c6633-123">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="c6633-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="c6633-124">Remarks</span></span>  
 <span data-ttu-id="c6633-125">Esse elemento tem o nome **DatabaseDetailsTypecomplexType** no Esquema XML do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="c6633-125">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="c6633-126">Não confunda este elemento do `Database` com aquele cujo pai raiz é o elemento `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="c6633-126">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="c6633-127">(Consulte [Elemento Database para Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).)</span><span class="sxs-lookup"><span data-stu-id="c6633-127">(See [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).)</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6633-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c6633-128">Example</span></span>  
 <span data-ttu-id="c6633-129">Para obter um exemplo de uso desse `Database` elemento, consulte o exemplo de código no [elemento de carga de trabalho &#40;DTA&#41;](workload-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="c6633-129">For a usage example of this `Database` element, see the code example in [Workload Element &#40;DTA&#41;](workload-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6633-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6633-130">See Also</span></span>  
 [<span data-ttu-id="c6633-131">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="c6633-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
