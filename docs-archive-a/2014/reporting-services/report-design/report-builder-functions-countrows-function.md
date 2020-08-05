---
title: Função CountRows (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5b1c403d-6afd-44c8-b5f6-5ecff2a29a45
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d5311dfc5dfcb89449a4039fdac4100fc5a3b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573726"
---
# <a name="countrows-function-report-builder-and-ssrs"></a><span data-ttu-id="a76a4-102">Função CountRows (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a76a4-102">CountRows Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a76a4-103">Retorna o número de linhas no escopo especificado, inclusive as linhas com valores nulos.</span><span class="sxs-lookup"><span data-stu-id="a76a4-103">Returns the number of rows in the specified scope, including rows with null values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="a76a4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a76a4-104">Syntax</span></span>  
  
```  
  
CountRows(scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a76a4-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="a76a4-105">Parameters</span></span>  
 <span data-ttu-id="a76a4-106">*escopo*</span><span class="sxs-lookup"><span data-stu-id="a76a4-106">*scope*</span></span>  
 <span data-ttu-id="a76a4-107">(`String`) O nome de um conjunto de dados, região de dados ou grupo que contém os itens de relatório a serem contados.</span><span class="sxs-lookup"><span data-stu-id="a76a4-107">(`String`) The name of a dataset, data region, or group that contains the report items to count.</span></span>  
  
 <span data-ttu-id="a76a4-108">*recursivos*</span><span class="sxs-lookup"><span data-stu-id="a76a4-108">*recursive*</span></span>  
 <span data-ttu-id="a76a4-109">(**Enumerated Type**) Opcional.</span><span class="sxs-lookup"><span data-stu-id="a76a4-109">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="a76a4-110">`Simple` (padrão) ou `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="a76a4-110">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="a76a4-111">Especifica se a agregação deve ser executada recursivamente.</span><span class="sxs-lookup"><span data-stu-id="a76a4-111">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="a76a4-112">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="a76a4-112">Return Type</span></span>  
 <span data-ttu-id="a76a4-113">Retorna um `Integer`.</span><span class="sxs-lookup"><span data-stu-id="a76a4-113">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a76a4-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="a76a4-114">Remarks</span></span>  
 <span data-ttu-id="a76a4-115">A função `CountRows` conta todas as linhas no escopo especificado incluindo linhas que possuem valores nulos.</span><span class="sxs-lookup"><span data-stu-id="a76a4-115">`CountRows` counts all rows in the specified scope, including rows that have null values.</span></span>  
  
 <span data-ttu-id="a76a4-116">O valor do *scope* não pode ser uma expressão e deve fazer referência ao escopo atual ou a um escopo contentor.</span><span class="sxs-lookup"><span data-stu-id="a76a4-116">The value of *scope* cannot be an expression and must refer to the current scope or a containing scope.</span></span>  
  
 <span data-ttu-id="a76a4-117">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="a76a4-117">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="a76a4-118">Para obter mais informações sobre agregações recursivas, consulte [Criando grupos de hierarquias recursivas &#40;Construtor de Relatórios e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a76a4-118">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a76a4-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a76a4-119">Example</span></span>  
 <span data-ttu-id="a76a4-120">O exemplo de código a seguir mostra uma expressão que calcula o número de linhas em um grupo de linhas denominado `GroupbyCategory` (baseado na expressão `[Category]`).</span><span class="sxs-lookup"><span data-stu-id="a76a4-120">The following code example shows an expression that calculates the number of rows in a row group named `GroupbyCategory` (based on the expression `[Category]`).</span></span>  
  
```  
="Number of rows: " & CountRows("GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="a76a4-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a76a4-121">See Also</span></span>  
 <span data-ttu-id="a76a4-122">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a76a4-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a76a4-123">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a76a4-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a76a4-124">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a76a4-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a76a4-125">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a76a4-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
