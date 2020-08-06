---
title: Exemplos de expressões de grupo (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data [Reporting Services], grouping
- grouping data
- expressions [Reporting Services], adding
- groups [Reporting Services], expressions
ms.assetid: 34cd0249-fc74-4cf2-ba11-7b072992bfd2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128e3fa7aed189fd00072c2c3e961b80f8137c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678604"
---
# <a name="group-expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="c66fd-102">Exemplos de expressões de grupo (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c66fd-102">Group Expression Examples (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c66fd-103">Em uma região de dados, você pode agrupar dados por um único campo ou criar expressões mais complexas que identifiquem os dados nos quais deve ser feito o agrupamento.</span><span class="sxs-lookup"><span data-stu-id="c66fd-103">In a data region, you can group data by a single field, or create more complex expressions that identify the data on which to group.</span></span> <span data-ttu-id="c66fd-104">Expressões complexas incluem referências a vários campos ou parâmetros, instruções condicionais ou código personalizado.</span><span class="sxs-lookup"><span data-stu-id="c66fd-104">Complex expressions include references to multiple fields or parameters, conditional statements, or custom code.</span></span> <span data-ttu-id="c66fd-105">Quando você define um grupo para uma região de dados, você adiciona essas expressões às propriedades **Group** .</span><span class="sxs-lookup"><span data-stu-id="c66fd-105">When you define a group for a data region, you add these expressions to the **Group** properties.</span></span> <span data-ttu-id="c66fd-106">Para obter mais informações, consulte [Adicionar ou excluir um grupo em uma região de dados &#40;Construtor de Relatórios e SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c66fd-106">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="c66fd-107">Para mesclar dois ou mais grupos baseados em expressões de campo simples, adicione cada campo à lista de expressões de grupo na definição do grupo.</span><span class="sxs-lookup"><span data-stu-id="c66fd-107">To merge two or more groups that are based on simple field expressions, add each field to the group expressions list in the group definition.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="examples-of-group-expressions"></a><span data-ttu-id="c66fd-108">Exemplos de expressões de grupo</span><span class="sxs-lookup"><span data-stu-id="c66fd-108">Examples of Group Expressions</span></span>  
 <span data-ttu-id="c66fd-109">A tabela a seguir fornece exemplos de expressões de grupo que podem ser usadas para definir um grupo.</span><span class="sxs-lookup"><span data-stu-id="c66fd-109">The following table provides examples of group expressions that you can use to define a group.</span></span>  
  
|<span data-ttu-id="c66fd-110">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c66fd-110">Description</span></span>|<span data-ttu-id="c66fd-111">Expression</span><span class="sxs-lookup"><span data-stu-id="c66fd-111">Expression</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="c66fd-112">Agrupar pelo campo `Region` .</span><span class="sxs-lookup"><span data-stu-id="c66fd-112">Group by the `Region` field.</span></span>|`=Fields!Region.Value`|  
|<span data-ttu-id="c66fd-113">Agrupar por sobrenome e nome.</span><span class="sxs-lookup"><span data-stu-id="c66fd-113">Group by last name and first name.</span></span>|`=Fields!LastName.Value`<br /><br /> `=Fields!FirstName.Value`|  
|<span data-ttu-id="c66fd-114">Agrupar pela primeira letra do sobrenome.</span><span class="sxs-lookup"><span data-stu-id="c66fd-114">Group by the first letter of the last name.</span></span>|`=Fields!LastName.Value.Substring(0,1)`|  
|<span data-ttu-id="c66fd-115">Agrupar pelo parâmetro, baseado na seleção do usuário.</span><span class="sxs-lookup"><span data-stu-id="c66fd-115">Group by parameter, based on user selection.</span></span><br /><br /> <span data-ttu-id="c66fd-116">Neste exemplo, o parâmetro `GroupBy` deve ser baseado em uma lista de valores disponíveis que fornece uma opção válida na qual deve ser feito o agrupamento.</span><span class="sxs-lookup"><span data-stu-id="c66fd-116">In this example, the parameter `GroupBy` must be based on an available values list that provides a valid choice to group on.</span></span>|`=Fields(Parameters!GroupBy.Value).Value`|  
|<span data-ttu-id="c66fd-117">Agrupar por três faixas etárias separadas:</span><span class="sxs-lookup"><span data-stu-id="c66fd-117">Group by three separate age ranges:</span></span><br /><br /> <span data-ttu-id="c66fd-118">"Menos de 21", "Entre 21 e 50" e "Mais de 50".</span><span class="sxs-lookup"><span data-stu-id="c66fd-118">"Under 21", "Between 21 and 50", and "Over 50".</span></span>|`=IIF(First(Fields!Age.Value)<21,"Under 21",(IIF(First(Fields!Age.Value)>=21 AND First(Fields!Age.Value)<=50,"Between 21 and 50","Over 50")))`|  
|<span data-ttu-id="c66fd-119">Agrupar por muitas faixas etárias.</span><span class="sxs-lookup"><span data-stu-id="c66fd-119">Group by many age ranges.</span></span> <span data-ttu-id="c66fd-120">Este exemplo mostra o código personalizado, escrito em [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET, que retorna uma cadeia para as seguintes faixas:</span><span class="sxs-lookup"><span data-stu-id="c66fd-120">This example shows custom code, written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET, that returns a string for the following ranges:</span></span><br /><br /> <span data-ttu-id="c66fd-121">25 ou menos</span><span class="sxs-lookup"><span data-stu-id="c66fd-121">25 or Under</span></span><br /><br /> <span data-ttu-id="c66fd-122">26 a 50</span><span class="sxs-lookup"><span data-stu-id="c66fd-122">26 to 50</span></span><br /><br /> <span data-ttu-id="c66fd-123">51 a 75</span><span class="sxs-lookup"><span data-stu-id="c66fd-123">51 to 75</span></span><br /><br /> <span data-ttu-id="c66fd-124">Mais de 75</span><span class="sxs-lookup"><span data-stu-id="c66fd-124">Over 75</span></span>|`=Code.GetRangeValueByAge(Fields!Age.Value)`<br /><br /> <span data-ttu-id="c66fd-125">Código personalizado:</span><span class="sxs-lookup"><span data-stu-id="c66fd-125">Custom code:</span></span><br /><br /> `Function GetRangeValueByAge(ByVal age As Integer) As String`<br /><br /> `Select Case age`<br /><br /> `Case 0 To 25`<br /><br /> `GetRangeValueByByAge = "25 or Under"`<br /><br /> `Case 26 To 50`<br /><br /> `GetRangeValueByByAge = "26 to 50"`<br /><br /> `Case 51 to 75`<br /><br /> `GetRangeValueByByAge = "51 to 75"`<br /><br /> `Case Else`<br /><br /> `GetRangeValueByByAge = "Over 75"`<br /><br /> `End Select`<br /><br /> `Return GetRangeValueByByAge`<br /><br /> `End Function`|  
  
## <a name="see-also"></a><span data-ttu-id="c66fd-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c66fd-126">See Also</span></span>  
 <span data-ttu-id="c66fd-127">[Filtrar, agrupar e classificar dados &#40;Construtor de Relatórios e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c66fd-127">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c66fd-128">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c66fd-128">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c66fd-129">Referências a código personalizado e assemblies em expressões no Designer de Relatórios &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c66fd-129">Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;</span></span>](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)  
  
  
