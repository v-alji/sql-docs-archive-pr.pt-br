---
title: Várias restrições de precedência | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- multiple precedence constraints
- precedence executables [Integration Services]
- precedence constraints [Integration Services], multiple
- constrained executables [Integration Services]
ms.assetid: 71c53ead-3d19-4bc1-aafd-e5b32595b420
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16fefbbf886818989131710876564fc9e147a56a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574100"
---
# <a name="multiple-precedence-constraints"></a><span data-ttu-id="9a208-102">Várias restrições de precedência</span><span class="sxs-lookup"><span data-stu-id="9a208-102">Multiple Precedence Constraints</span></span>
  <span data-ttu-id="9a208-103">Uma restrição de precedência conecta dois executáveis: duas tarefas, dois contêineres, ou um de cada.</span><span class="sxs-lookup"><span data-stu-id="9a208-103">A precedence constraint connects two executables: two tasks, two containers, or one of each.</span></span> <span data-ttu-id="9a208-104">Eles são conhecidos como o executável de precedência e o executável restrito.</span><span class="sxs-lookup"><span data-stu-id="9a208-104">They are known as the precedence executable and the constrained executable.</span></span> <span data-ttu-id="9a208-105">Um executável restrito pode ter múltiplas restrições de precedência.</span><span class="sxs-lookup"><span data-stu-id="9a208-105">A constrained executable can have multiple precedence constraints.</span></span> <span data-ttu-id="9a208-106">Para obter informações, consulte [Restrições de precedência](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="9a208-106">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="9a208-107">Reunir cenários de restrição complexos por agrupamento de restrições permite que você implemente o fluxo de controle complexo em pacotes.</span><span class="sxs-lookup"><span data-stu-id="9a208-107">Assembling complex constraint scenarios by grouping constraints enables you to implement complex control flow in packages.</span></span> <span data-ttu-id="9a208-108">Por exemplo, na ilustração a seguir, a Tarefa D está vinculada à Tarefa A por uma restrição `Success`, a Tarefa D está vinculada à Tarefa B por uma restrição `Failure` e a Tarefa D está vinculada à Tarefa C por uma restrição `Success`.</span><span class="sxs-lookup"><span data-stu-id="9a208-108">For example, in the following illustration, Task D is linked to Task A by a `Success` constraint, Task D is linked to Task B by a `Failure` constraint, and Task D is linked to Task C by a `Success` constraint.</span></span> <span data-ttu-id="9a208-109">As restrições de precedência entre as Tarefas D e A, entre as Tarefas D e B e entre as Tarefas D e C participam de uma relação lógica *and* .</span><span class="sxs-lookup"><span data-stu-id="9a208-109">The precedence constraints between Task D and Task A, between Task D and Task B, and between Task D and Task C participate in a logical *and* relationship.</span></span> <span data-ttu-id="9a208-110">Portanto, para que a Tarefa D seja executada, a Tarefa A deve ser executada com êxito, a Tarefa B deve falhar e a Tarefa C deve ser executada com êxito.</span><span class="sxs-lookup"><span data-stu-id="9a208-110">Therefore, for Task D to run, Task A must run successfully, Task B must fail, and Task C must run successfully.</span></span>  
  
 <span data-ttu-id="9a208-111">![Tarefas vinculadas por restrições de precedência](media/precedenceconstraints.gif "Tarefas vinculadas por restrições de precedência")</span><span class="sxs-lookup"><span data-stu-id="9a208-111">![Tasks linked by precedence constraints](media/precedenceconstraints.gif "Tasks linked by precedence constraints")</span></span>  
  
## <a name="logicaland-property"></a><span data-ttu-id="9a208-112">Propriedade LogicalAnd</span><span class="sxs-lookup"><span data-stu-id="9a208-112">LogicalAnd Property</span></span>  
 <span data-ttu-id="9a208-113">Se uma tarefa ou contêiner tiver múltiplas restrições, a propriedade `LogicalAnd` especificará se uma restrição de precedência é avaliada isoladamente ou junto com outras restrições.</span><span class="sxs-lookup"><span data-stu-id="9a208-113">If a task or a container has multiple constraints, the `LogicalAnd` property specifies whether a precedence constraint is evaluated singly or in concert with other constraints.</span></span>  
  
 <span data-ttu-id="9a208-114">Você pode definir a `LogicalAnd` propriedade usando o **Editor de restrição de precedência** no [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer ou na janela Propriedades que o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] fornece.</span><span class="sxs-lookup"><span data-stu-id="9a208-114">You can set the `LogicalAnd` property using the **Precedence Constraint Editor** in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, or in the Properties window that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] provides.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="9a208-115">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="9a208-115">Related Tasks</span></span>  
 [<span data-ttu-id="9a208-116">Definir as propriedades de uma restrição de precedência</span><span class="sxs-lookup"><span data-stu-id="9a208-116">Set the Properties of a Precedence Constraint</span></span>](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md)  
  
  
