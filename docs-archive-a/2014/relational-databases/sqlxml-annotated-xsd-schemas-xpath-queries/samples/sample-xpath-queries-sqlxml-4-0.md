---
title: Consultas XPath de exemplo (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- examples [SQLXML], XPath
- sample applications [SQLXML]
- sample XPath queries [SQLXML]
- mapping schema [SQLXML], queries
- XPath queries [SQLXML], samples
ms.assetid: 1595c2d4-0e9c-4969-84c8-a793a32df57d
author: rothja
ms.author: jroth
ms.openlocfilehash: 08ed32433e9bed4cc1542d6700ad73dc96f3c2dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569296"
---
# <a name="sample-xpath-queries-sqlxml-40"></a><span data-ttu-id="8847d-102">Consultas XPath de exemplo (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="8847d-102">Sample XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="8847d-103">Esta seção apresenta exemplos de consultas XPath para SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="8847d-103">This section provides examples of XPath queries for SQLXML 4.0.</span></span> <span data-ttu-id="8847d-104">Para fins de ilustração, essas consultas XPath de exemplo são especificadas em um modelo executado usando o ADO.</span><span class="sxs-lookup"><span data-stu-id="8847d-104">For illustration purposes, these example XPath queries are specified in a template executed using ADO.</span></span> <span data-ttu-id="8847d-105">Por isso, você deve usar um arquivo de esquema de mapeamento, SampleSchema1.xml, também fornecido nesta seção.</span><span class="sxs-lookup"><span data-stu-id="8847d-105">Therefore, you must use a mapping schema file, SampleSchema1.xml, which is also provided in this section.</span></span> <span data-ttu-id="8847d-106">Salve este arquivo no diretório onde seus modelos estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="8847d-106">Save this file in the directory where your templates are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8847d-107">As consultas de exemplo desta seção são agrupadas pelo tipo de operação XPath é executada pela consulta.</span><span class="sxs-lookup"><span data-stu-id="8847d-107">The sample queries in this section are grouped by the type of XPath operation that is performed by the query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8847d-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8847d-108">In This Section</span></span>  
 [<span data-ttu-id="8847d-109">Exemplo de esquema XSD anotado para exemplos de XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="8847d-109">Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;</span></span>](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md)  
 <span data-ttu-id="8847d-110">Use este arquivo com os exemplos de consulta XPath fornecidos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="8847d-110">Use this file with the XPath query examples provided in this section.</span></span>  
  
 [<span data-ttu-id="8847d-111">Especificando eixos em consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="8847d-111">Specifying Axes in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-axes-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="8847d-112">Ilustra como eixos são especificados em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="8847d-112">Illustrates how axes are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="8847d-113">Especificando predicados com valor booliano em consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="8847d-113">Specifying Boolean-Valued Predicates in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-valued-predicates-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="8847d-114">Ilustra como predicados com valor booliano são especificados em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="8847d-114">Illustrates how Boolean-valued predicates are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="8847d-115">Especificando operadores relacionais em consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="8847d-115">Specifying Relational Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-relational-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="8847d-116">Ilustra como operadores relacionais são especificados em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="8847d-116">Illustrates how relational operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="8847d-117">Especificando operadores aritméticos em consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="8847d-117">Specifying Arithmetic Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-arithmetic-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="8847d-118">Ilustra como operadores aritméticos são especificados em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="8847d-118">Illustrates how arithmetic operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="8847d-119">Especificando funções de conversão explícitas em consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="8847d-119">Specifying Explicit Conversion Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="8847d-120">Ilustra como funções de conversão explícitas são especificadas em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="8847d-120">Illustrates how explicit conversion functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="8847d-121">Especificando operadores boolianos em consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="8847d-121">Specifying Boolean Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="8847d-122">Ilustra como operadores boolianos são especificados em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="8847d-122">Illustrates how Boolean operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="8847d-123">Especificando funções booleanas em consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="8847d-123">Specifying Boolean Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="8847d-124">Ilustra como funções boolianas são especificadas em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="8847d-124">Illustrates how Boolean functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="8847d-125">Especificando variáveis XPath em consultas XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="8847d-125">Specifying XPath Variables in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-xpath-variables-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="8847d-126">Ilustra como variáveis XPath são especificadas em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="8847d-126">Illustrates how XPath variables are specified in XPath queries.</span></span>  
  
  
