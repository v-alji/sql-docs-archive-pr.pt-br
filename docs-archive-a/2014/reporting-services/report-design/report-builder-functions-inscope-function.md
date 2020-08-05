---
title: Função InScope (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8cd209a-e5d3-4dce-ab2d-f271f6c54955
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62c4ad5de7af1ac0762df29deaa17953a8a378db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573719"
---
# <a name="inscope-function-report-builder-and-ssrs"></a><span data-ttu-id="48f94-102">Função InScope (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="48f94-102">InScope Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="48f94-103">Indica se a instância atual de um item está no escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="48f94-103">Indicates whether the current instance of an item is in the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="48f94-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="48f94-104">Syntax</span></span>  
  
```  
InScope(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48f94-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="48f94-105">Parameters</span></span>  
 <span data-ttu-id="48f94-106">*escopo*</span><span class="sxs-lookup"><span data-stu-id="48f94-106">*scope*</span></span>  
 <span data-ttu-id="48f94-107">(`String`) O nome de um conjunto de dados, região de dados ou grupo que especifica um escopo.</span><span class="sxs-lookup"><span data-stu-id="48f94-107">(`String`) The name of a dataset, data region, or group that specifies a scope.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="48f94-108">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="48f94-108">Return Type</span></span>  
 <span data-ttu-id="48f94-109">Retorna um `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="48f94-109">Returns a `Boolean`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48f94-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="48f94-110">Remarks</span></span>  
 <span data-ttu-id="48f94-111">A `InScope` função testa o escopo da instância atual de um item de relatório para associação no escopo especificado pelo parâmetro de *escopo*.</span><span class="sxs-lookup"><span data-stu-id="48f94-111">The `InScope` function tests the scope of the current instance of a report item for membership in the scope specified by the *scope*parameter.</span></span>  
  
 <span data-ttu-id="48f94-112">O*Scope* não pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="48f94-112">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="48f94-113">Um uso típico da função `InScope` é em regiões de dados que possuem escopo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="48f94-113">A typical use for the `InScope` function is in data regions that have dynamic scoping.</span></span> <span data-ttu-id="48f94-114">Por exemplo, `InScope` pode ser usada em um link de detalhamento em células de uma região de dados para fornecer um nome de relatório diferente e conjuntos de parâmetros diferentes, dependendo da célula clicada.</span><span class="sxs-lookup"><span data-stu-id="48f94-114">For example, `InScope` can be used in a drillthrough link in a data region cells to provide a different report name and different sets of parameters depending on which cell is clicked.</span></span> <span data-ttu-id="48f94-115">Um exemplo disso é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="48f94-115">An example of this is as follows:</span></span>  
  
-   <span data-ttu-id="48f94-116">A expressão a seguir, usada como o nome do relatório em um link de drillthrough, abrirá o relatório `ProductDetail` , se a célula clicada estiver no grupo `Month` , e o relatório `ProductSummary` se não estiver.</span><span class="sxs-lookup"><span data-stu-id="48f94-116">The following expression, used as the report name in a drillthrough link, opens the `ProductDetail` report if the clicked cell is in the `Month` group, and the `ProductSummary` report if it is not.</span></span>  
  
    ```  
    =Iif(InScope("Month"), "ProductDetail", "ProductSummary")  
    ```  
  
-   <span data-ttu-id="48f94-117">A expressão a seguir, usada na propriedade `Omit` de um parâmetro de relatório detalhado, passará o parâmetro para o relatório de destino somente se a célula clicada estiver no grupo `Product`.</span><span class="sxs-lookup"><span data-stu-id="48f94-117">The following expression, used in the `Omit` property of a drillthrough report parameter, will pass the parameter to the target report only if the clicked cell is in the `Product` group.</span></span>  
  
    ```  
    =Not(InScope("Product"))  
    ```  
  
 <span data-ttu-id="48f94-118">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="48f94-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="48f94-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="48f94-119">Example</span></span>  
 <span data-ttu-id="48f94-120">O exemplo de código a seguir indica se a instância atual do item está no conjunto de dados, região de dados ou escopo do grupo `Product` .</span><span class="sxs-lookup"><span data-stu-id="48f94-120">The following code example indicates whether the current instance of the item is in the `Product` dataset, data region, or group scope.</span></span>  
  
```  
=InScope("Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="48f94-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48f94-121">See Also</span></span>  
 <span data-ttu-id="48f94-122">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="48f94-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="48f94-123">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="48f94-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="48f94-124">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="48f94-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="48f94-125">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="48f94-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
