---
title: Função RowNumber (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d718ba8-d323-49fb-aac8-e7013a117b75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f3d16188138c2f268305fddb092d56be870a3f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573701"
---
# <a name="rownumber-function-report-builder-and-ssrs"></a><span data-ttu-id="2fe6e-102">Função RowNumber (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="2fe6e-102">RowNumber Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2fe6e-103">Retorna uma contagem contínua do número de linhas para o escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-103">Returns a running count of the number of rows for the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="2fe6e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2fe6e-104">Syntax</span></span>  
  
```  
  
RowNumber(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2fe6e-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="2fe6e-105">Parameters</span></span>  
 <span data-ttu-id="2fe6e-106">*escopo*</span><span class="sxs-lookup"><span data-stu-id="2fe6e-106">*scope*</span></span>  
 <span data-ttu-id="2fe6e-107">(`String`) O nome de um conjunto de dados, região de dados ou grupo ou nulo (`Nothing` no [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), que especifica o contexto no qual avaliar o número de linhas.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-107">(`String`) The name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the number of rows.</span></span> <span data-ttu-id="2fe6e-108">`Nothing` especifica o contexto mais externo, geralmente o conjunto de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-108">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fe6e-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="2fe6e-109">Remarks</span></span>  
 <span data-ttu-id="2fe6e-110">`RowNumber`Retorna um valor em execução da contagem de linhas dentro do escopo especificado, assim como [RunningValue](report-builder-functions-runningvalue-function.md) retorna o valor em execução de uma função de agregação.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-110">`RowNumber` returns a running value of the count of rows within the specified scope, just as [RunningValue](report-builder-functions-runningvalue-function.md) returns the running value of an aggregate function.</span></span> <span data-ttu-id="2fe6e-111">Ao especificar um escopo, você especifica quando redefinir a contagem de linhas como 1.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-111">When you specify a scope, you specify when to reset the row count to 1.</span></span>  
  
 <span data-ttu-id="2fe6e-112">O*scope* não pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-112">*scope* cannot be an expression.</span></span> <span data-ttu-id="2fe6e-113">*scope* deve ser um escopo contentor.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-113">*scope* must be a containing scope.</span></span> <span data-ttu-id="2fe6e-114">Escopos típicos, do confinamento mais externo ao mais interno, são conjuntos de dados de relatório, região de dados, grupos de linhas ou grupos de colunas.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-114">Typical scopes, from the outermost to the innermost containment, are report dataset, data region, row groups or column groups.</span></span>  
  
 <span data-ttu-id="2fe6e-115">Para incrementar valores entre colunas, especifique um escopo que seja o nome de um grupo de colunas.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-115">To increment values across columns, specify a scope that is the name of a column group.</span></span> <span data-ttu-id="2fe6e-116">Para incrementar números em baixo das linhas, especifique um escopo que seja o nome de um grupo de linhas.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-116">To increment numbers down rows, specify a scope that is the name of a row group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2fe6e-117">Não há suporte para a inclusão de agregações que especificam um grupo de linhas e um grupo de colunas em uma única expressão.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-117">Including aggregates that specify both a row group and a column group in a single expression is not supported.</span></span>  
  
 <span data-ttu-id="2fe6e-118">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="2fe6e-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="code-example"></a><span data-ttu-id="2fe6e-119">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="2fe6e-119">Code Example</span></span>  
 <span data-ttu-id="2fe6e-120">A expressão a seguir pode ser usada para a propriedade `BackgroundColor` de uma linha de detalhes da região de dados Tablix para alternar a cor das linhas de detalhes de cada grupo, sempre começando com Branco.</span><span class="sxs-lookup"><span data-stu-id="2fe6e-120">The following is an expression that you can use for the `BackgroundColor` property of a Tablix data region detail row to alternate the color of detail rows for each group, always beginning with White.</span></span>  
  
```  
=IIF(RowNumber("GroupbyCategory") Mod 2, "White", "PaleGreen")  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fe6e-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2fe6e-121">See Also</span></span>  
 <span data-ttu-id="2fe6e-122">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fe6e-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2fe6e-123">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fe6e-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2fe6e-124">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2fe6e-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2fe6e-125">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2fe6e-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
