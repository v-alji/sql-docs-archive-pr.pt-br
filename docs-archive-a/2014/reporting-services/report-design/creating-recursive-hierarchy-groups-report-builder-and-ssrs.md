---
title: Criando grupos de hierarquias recursivas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 06eccab6-4089-46e8-a84f-5bf3bbe0c23b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: aeb99e725c5c61a6dc66c83e53afbc43b1224582
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572413"
---
# <a name="creating-recursive-hierarchy-groups-report-builder-and-ssrs"></a><span data-ttu-id="9895a-102">Criando grupos de hierarquias recursivas (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="9895a-102">Creating Recursive Hierarchy Groups (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9895a-103">Para exibir dados recursivos em que a relação entre pai e filho é representada por campos no conjunto de dados, você pode definir a expressão do grupo de região de dado com base no campo filho e definir a propriedade Parent com base no campo pai.</span><span class="sxs-lookup"><span data-stu-id="9895a-103">To display recursive data where the relationship between parent and child is represented by fields in the dataset, you can set the data region group expression based on the child field and set the Parent property based on the parent field.</span></span>  
  
 <span data-ttu-id="9895a-104">Exibir dados hierárquicos é um uso comum dos grupos de hierarquias recursivas (por exemplo, funcionários em um organograma).</span><span class="sxs-lookup"><span data-stu-id="9895a-104">Displaying hierarchical data is a common use for recursive hierarchy groups, for example, employees in an organizational chart.</span></span> <span data-ttu-id="9895a-105">O conjunto de dados inclui uma lista de funcionários e gerentes, em que os nomes de gerentes também aparecem na lista de funcionários.</span><span class="sxs-lookup"><span data-stu-id="9895a-105">The dataset includes a list of employees and the managers, where the manager names also appear in the list of employees.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="creating-recursive-hierarchies"></a><span data-ttu-id="9895a-106">Criando hierarquias recursivas</span><span class="sxs-lookup"><span data-stu-id="9895a-106">Creating Recursive Hierarchies</span></span>  
 <span data-ttu-id="9895a-107">Para criar uma hierarquia recursiva em uma região de dados tablix, você deve definir a expressão de grupo como o campo que especifica os dados filho e a propriedade Parent do grupo como o campo que especifica os dados pai.</span><span class="sxs-lookup"><span data-stu-id="9895a-107">To build a recursive hierarchy in a tablix data region, you must set the group expression to the field that specifies the child data and the Parent property of the group to the field that specifies the parent data.</span></span> <span data-ttu-id="9895a-108">Por exemplo, no caso de um conjunto de dados que inclui campos ID de funcionário e ID de gerente em que os funcionários estão subordinados aos gerentes, defina a expressão de grupo como ID de funcionário e a propriedade Parent como ID de gerente.</span><span class="sxs-lookup"><span data-stu-id="9895a-108">For example, for a dataset that includes fields for employee ID and manager ID where employees report to managers, set the group expression to employee ID and the Parent property to manager ID.</span></span>  
  
 <span data-ttu-id="9895a-109">Um grupo definido como hierarquia recursiva (isto é, um grupo que usa a propriedade Parent) só pode ter uma expressão de grupo.</span><span class="sxs-lookup"><span data-stu-id="9895a-109">A group that is defined as a recursive hierarchy (that is, a group that uses the Parent property) can have only one group expression.</span></span> <span data-ttu-id="9895a-110">É possível usar a função `Level` no preenchimento da caixa de texto para recuar os nomes de funcionários conforme seu nível na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="9895a-110">You can use the `Level` function in text box padding to indent employee names based on their level in the hierarchy.</span></span>  
  
 <span data-ttu-id="9895a-111">Para obter mais informações, consulte [Adicionar ou excluir um grupo em uma região de dados &#40;Construtor de Relatórios e SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) e [Criar um grupo de hierarquias recursivas &#40;Construtor de Relatórios e SSRS&#41;](create-a-recursive-hierarchy-group-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9895a-111">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) and  [Create a Recursive Hierarchy Group &#40;Report Builder and SSRS&#41;](create-a-recursive-hierarchy-group-report-builder-and-ssrs.md).</span></span>  
  
### <a name="aggregate-functions-that-support-recursion"></a><span data-ttu-id="9895a-112">Funções de agregação compatíveis com recursão</span><span class="sxs-lookup"><span data-stu-id="9895a-112">Aggregate Functions that support Recursion</span></span>  
 <span data-ttu-id="9895a-113">Você pode usar as funções de agregação do Reporting Services que aceitam o parâmetro *Recursive* para calcular dados resumidos de uma hierarquia recursiva.</span><span class="sxs-lookup"><span data-stu-id="9895a-113">You can use Reporting Services aggregate functions that accept the parameter *Recursive* to calculate summary data for a recursive hierarchy.</span></span> <span data-ttu-id="9895a-114">As funções a seguir aceitam `Recursive` como um parâmetro: [sum](report-builder-functions-sum-function.md), [AVG](report-builder-functions-avg-function.md), [Count](report-builder-functions-count-function.md), [CountDistinct](report-builder-functions-countdistinct-function.md), [COUNTROWS](report-builder-functions-countrows-function.md), [Max](report-builder-functions-max-function.md), [min](report-builder-functions-min-function.md), [Desv](report-builder-functions-stdev-function.md), [DESVPADP](report-builder-functions-stdevp-function.md), [sum](report-builder-functions-sum-function.md), [var](report-builder-functions-var-function.md)e [VARP](report-builder-functions-varp-function.md).</span><span class="sxs-lookup"><span data-stu-id="9895a-114">The following functions accept `Recursive` as a parameter: [Sum](report-builder-functions-sum-function.md), [Avg](report-builder-functions-avg-function.md), [Count](report-builder-functions-count-function.md), [CountDistinct](report-builder-functions-countdistinct-function.md), [CountRows](report-builder-functions-countrows-function.md), [Max](report-builder-functions-max-function.md), [Min](report-builder-functions-min-function.md), [StDev](report-builder-functions-stdev-function.md), [StDevP](report-builder-functions-stdevp-function.md), [Sum](report-builder-functions-sum-function.md), [Var](report-builder-functions-var-function.md), and [VarP](report-builder-functions-varp-function.md).</span></span> <span data-ttu-id="9895a-115">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="9895a-115">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9895a-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9895a-116">See Also</span></span>  
 <span data-ttu-id="9895a-117">[Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9895a-117">[Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9895a-118">[Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9895a-118">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9895a-119">[Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9895a-119">[Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) </span></span>  
 <span data-ttu-id="9895a-120">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9895a-120">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9895a-121">[Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9895a-121">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9895a-122">[Listas &#40;Construtor de Relatórios e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9895a-122">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9895a-123">Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9895a-123">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  