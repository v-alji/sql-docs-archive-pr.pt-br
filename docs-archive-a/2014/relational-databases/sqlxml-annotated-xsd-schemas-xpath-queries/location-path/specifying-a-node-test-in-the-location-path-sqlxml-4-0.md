---
title: Especificando um teste de nó no caminho do local (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], location paths
- principal node types [SQLXML]
- node tests [SQLXML]
- location path for XPath query
ms.assetid: f46c30bf-1e24-4435-9ac2-f8ba43a8ff94
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d8535154f4b481c8a47bfdb8b801e3136a1ef0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574590"
---
# <a name="specifying-a-node-test-in-the-location-path-sqlxml-40"></a><span data-ttu-id="7005b-102">Especificando um teste de nó no caminho do local (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7005b-102">Specifying a Node Test in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="7005b-103">Um teste de nó especifica o tipo de nó selecionado pela etapa de local.</span><span class="sxs-lookup"><span data-stu-id="7005b-103">A node test specifies the node type selected by the location step.</span></span> <span data-ttu-id="7005b-104">Todo eixo (`child`, `parent`, `attribute` ou `self`) tem um tipo de nó principal.</span><span class="sxs-lookup"><span data-stu-id="7005b-104">Every axis (`child`, `parent`, `attribute`, or `self`) has a principal node type.</span></span> <span data-ttu-id="7005b-105">Para o `attribute` eixo, o tipo de nó principal é **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="7005b-105">For the `attribute` axis, the principal node type is **\<attribute>**.</span></span> <span data-ttu-id="7005b-106">Para os `parent` `child` eixos,, e `self` , o tipo de nó principal é **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="7005b-106">For the `parent`, `child`, and `self` axes, the principal node type is **\<element>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7005b-107">O teste de nó de curinga \* (por exemplo, `child::*`) não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="7005b-107">The wildcard node test \* (for example, `child::*`) is not supported.</span></span>  
  
## <a name="node-test-example-1"></a><span data-ttu-id="7005b-108">Teste de nó: exemplo 1</span><span class="sxs-lookup"><span data-stu-id="7005b-108">Node Test: Example 1</span></span>  
 <span data-ttu-id="7005b-109">O caminho do local `child::Customer` seleciona os **\<Customer>** filhos do elemento do nó de contexto.</span><span class="sxs-lookup"><span data-stu-id="7005b-109">The location path `child::Customer` selects **\<Customer>** element children of the context node.</span></span>  
  
 <span data-ttu-id="7005b-110">Neste exemplo, `child` é o eixo e `Customer` é o teste de nó.</span><span class="sxs-lookup"><span data-stu-id="7005b-110">In this example, `child` is the axis and `Customer` is the node test.</span></span> <span data-ttu-id="7005b-111">O tipo de nó de entidade para o `child` eixo é **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="7005b-111">The principal node type for the `child` axis is **\<element>**.</span></span> <span data-ttu-id="7005b-112">Portanto, o teste de nó será TRUE se o **\<Customer>** nó for um **\<element>** nó.</span><span class="sxs-lookup"><span data-stu-id="7005b-112">Therefore, the node test is TRUE if the **\<Customer>** node is an **\<element>** node.</span></span> <span data-ttu-id="7005b-113">Se o nó de contexto não tiver **\<Customer>** filhos, um conjunto de nós vazio será retornado.</span><span class="sxs-lookup"><span data-stu-id="7005b-113">If the context node has no **\<Customer>** children, an empty set of nodes is returned.</span></span>  
  
## <a name="node-test-example-2"></a><span data-ttu-id="7005b-114">Teste de nó: exemplo 2</span><span class="sxs-lookup"><span data-stu-id="7005b-114">Node Test: Example 2</span></span>  
 <span data-ttu-id="7005b-115">O caminho do local `attribute::CustomerID` seleciona o atributo **CustomerID** do nó de contexto.</span><span class="sxs-lookup"><span data-stu-id="7005b-115">The location path `attribute::CustomerID` selects the **CustomerID** attribute of the context node.</span></span>  
  
 <span data-ttu-id="7005b-116">No exemplo, `attribute` é o eixo e `CustomerID` é o teste de nó.</span><span class="sxs-lookup"><span data-stu-id="7005b-116">In the example, `attribute` is the axis and `CustomerID` is the node test.</span></span> <span data-ttu-id="7005b-117">O tipo de nó principal do `attribute` eixo é **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="7005b-117">The principal node type of the `attribute` axis is **\<attribute>**.</span></span> <span data-ttu-id="7005b-118">Portanto, o teste de nó será TRUE se **CustomerID** for um **\<attribute>** nó.</span><span class="sxs-lookup"><span data-stu-id="7005b-118">Therefore, the node test is TRUE if **CustomerID** is an **\<attribute>** node.</span></span> <span data-ttu-id="7005b-119">Se o nó de contexto não tiver nenhum **CustomerID**, um conjunto de nós vazio será retornado.</span><span class="sxs-lookup"><span data-stu-id="7005b-119">If the context node has no **CustomerID**, an empty set of nodes is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7005b-120">Nessa implementação do XPath, se uma etapa de local se refere a um **\<element>** ou um **\<attribute>** tipo que não está declarado no esquema, um erro é gerado.</span><span class="sxs-lookup"><span data-stu-id="7005b-120">In this implementation of XPath, if a location step refers to an **\<element>** or an **\<attribute>** type that is not declared in the schema, an error is generated.</span></span> <span data-ttu-id="7005b-121">Isto é diferente da implementação de XPath em MSXML, que retorna um conjunto de nós vazio.</span><span class="sxs-lookup"><span data-stu-id="7005b-121">This is different from the implementation of XPath in MSXML, which returns an empty node set.</span></span>  
  
## <a name="abbreviated-syntax-for-the-axes"></a><span data-ttu-id="7005b-122">Sintaxe abreviada para os eixos</span><span class="sxs-lookup"><span data-stu-id="7005b-122">Abbreviated Syntax for the Axes</span></span>  
 <span data-ttu-id="7005b-123">A sintaxe abreviada a seguir para o caminho de local tem suporte:</span><span class="sxs-lookup"><span data-stu-id="7005b-123">The following abbreviated syntax for the location path is supported:</span></span>  
  
-   <span data-ttu-id="7005b-124">`attribute::` pode ser abreviado para `@`.</span><span class="sxs-lookup"><span data-stu-id="7005b-124">`attribute::` can be abbreviated to `@`.</span></span>  
  
     <span data-ttu-id="7005b-125">O caminho do local `Customer[@CustomerID="ALFKI"]` é o mesmo que `child::Customer[attribute::CustomerID="ALFKI"]`.</span><span class="sxs-lookup"><span data-stu-id="7005b-125">The location path `Customer[@CustomerID="ALFKI"]` is the same as `child::Customer[attribute::CustomerID="ALFKI"]`.</span></span>  
  
-   <span data-ttu-id="7005b-126">`child::` pode ser omitido de uma etapa de local.</span><span class="sxs-lookup"><span data-stu-id="7005b-126">`child::` can be omitted from a location step.</span></span>  
  
     <span data-ttu-id="7005b-127">Assim, `child` é o eixo padrão.</span><span class="sxs-lookup"><span data-stu-id="7005b-127">Thus, `child` is the default axis.</span></span> <span data-ttu-id="7005b-128">O caminho do local `Customer/Order` é o mesmo que `child::Customer/child::Order`.</span><span class="sxs-lookup"><span data-stu-id="7005b-128">The location path `Customer/Order` is the same as `child::Customer/child::Order`.</span></span>  
  
-   <span data-ttu-id="7005b-129">`self::node()` pode ser abreviado como um ponto (.) e `parent::node()` pode ser abreviado como dois pontos (..).</span><span class="sxs-lookup"><span data-stu-id="7005b-129">`self::node()` can be abbreviated to one period (.), and `parent::node()` can be abbreviated to two periods (..).</span></span>  
  
  
