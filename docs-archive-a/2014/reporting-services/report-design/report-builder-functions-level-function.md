---
title: Função Level (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 41235402-bb9e-4cb7-b91e-431e77db19cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dedbf00ce8330242c95e9592f649d95171f0987a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573717"
---
# <a name="level-function-report-builder-and-ssrs"></a><span data-ttu-id="f86ca-102">Função Level (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f86ca-102">Level Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f86ca-103">Retorna o nível atual de profundidade em uma hierarquia recursiva.</span><span class="sxs-lookup"><span data-stu-id="f86ca-103">Returns the current level of depth in a recursive hierarchy.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="f86ca-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f86ca-104">Syntax</span></span>  
  
```  
  
Level(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f86ca-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="f86ca-105">Parameters</span></span>  
 <span data-ttu-id="f86ca-106">*escopo*</span><span class="sxs-lookup"><span data-stu-id="f86ca-106">*scope*</span></span>  
 <span data-ttu-id="f86ca-107">(`String`) (Opcional).</span><span class="sxs-lookup"><span data-stu-id="f86ca-107">(`String`) (Optional).</span></span> <span data-ttu-id="f86ca-108">O nome de um conjunto de dados, um grupo ou uma região de dados que contém os itens de relatório aos quais a função de agregação deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="f86ca-108">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="f86ca-109">Se *scope* não estiver especificado, será usado o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="f86ca-109">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="f86ca-110">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="f86ca-110">Return Type</span></span>  
 <span data-ttu-id="f86ca-111">Retorna um `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f86ca-111">Returns an `Integer`.</span></span> <span data-ttu-id="f86ca-112">Se *Scope* especifica um DataSet ou uma região de dados, ou especifica um agrupamento nonrecursive (ou seja, um agrupamento sem `Parent` elemento), `Level` retorna 0.</span><span class="sxs-lookup"><span data-stu-id="f86ca-112">If *scope* specifies a dataset or data region, or specifies a nonrecursive grouping (that is, a grouping with no `Parent` element), `Level` returns 0.</span></span> <span data-ttu-id="f86ca-113">Se o *scope* for omitido, ele retornará o nível do escopo atual.</span><span class="sxs-lookup"><span data-stu-id="f86ca-113">If *scope* is omitted, it returns the level of the current scope.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f86ca-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="f86ca-114">Remarks</span></span>  
 <span data-ttu-id="f86ca-115">O valor retornado pela função `Level` é baseado em zero; isto é, o primeiro nível em uma hierarquia é 0.</span><span class="sxs-lookup"><span data-stu-id="f86ca-115">The value returned by the `Level` function is zero based; that is, the first level in a hierarchy is 0.</span></span>  
  
 <span data-ttu-id="f86ca-116">A função `Level` pode ser usada para fornecer recuo em uma hierarquia recursiva, como uma lista de funcionários.</span><span class="sxs-lookup"><span data-stu-id="f86ca-116">The `Level` function can be used to provide indentation in a recursive hierarchy, such as an employee list.</span></span>  
  
 <span data-ttu-id="f86ca-117">Para obter mais informações sobre hierarquias recursivas, consulte [Criando grupos de hierarquias recursivas &#40;Construtor de Relatórios e SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f86ca-117">For more information about recursive hierarchies, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f86ca-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f86ca-118">Example</span></span>  
 <span data-ttu-id="f86ca-119">O exemplo de código a seguir fornece o nível de linha no grupo de Funcionários:</span><span class="sxs-lookup"><span data-stu-id="f86ca-119">The following code example provides the level of row in the Employees group:</span></span>  
  
```  
=Level("Employees")  
```  
  
## <a name="see-also"></a><span data-ttu-id="f86ca-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f86ca-120">See Also</span></span>  
 <span data-ttu-id="f86ca-121">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f86ca-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f86ca-122">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f86ca-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f86ca-123">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f86ca-123">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f86ca-124">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f86ca-124">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
