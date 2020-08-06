---
title: Editor de restrição de precedência | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.precedenceconstraint.f1
helpviewer_keywords:
- Precedence Constraint Editor dialog box
ms.assetid: b10d4330-6e35-4037-b309-ef56efcd60c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6853d1974f4276361d60e1d73b34c72a366a7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571429"
---
# <a name="precedence-constraint-editor"></a><span data-ttu-id="97e2b-102">Editor de Restrição de Precedência</span><span class="sxs-lookup"><span data-stu-id="97e2b-102">Precedence Constraint Editor</span></span>
  <span data-ttu-id="97e2b-103">Use a caixa de diálogo **Editor de Restrição de Precedência** para configurar as restrições de precedência.</span><span class="sxs-lookup"><span data-stu-id="97e2b-103">Use the **Precedence Constraint Editor** dialog box to configure precedence constraints.</span></span>  
  
## <a name="options"></a><span data-ttu-id="97e2b-104">Opções</span><span class="sxs-lookup"><span data-stu-id="97e2b-104">Options</span></span>  
 <span data-ttu-id="97e2b-105">**Operação de avaliação**</span><span class="sxs-lookup"><span data-stu-id="97e2b-105">**Evaluation operation**</span></span>  
 <span data-ttu-id="97e2b-106">Especifica a operação de avaliação usada pela restrição de precedência.</span><span class="sxs-lookup"><span data-stu-id="97e2b-106">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="97e2b-107">As operações são: **Constraint**, **Expression**, **Expression and Constraint** e **Expression or Constraint**.</span><span class="sxs-lookup"><span data-stu-id="97e2b-107">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
 <span data-ttu-id="97e2b-108">**Valor**</span><span class="sxs-lookup"><span data-stu-id="97e2b-108">**Value**</span></span>  
 <span data-ttu-id="97e2b-109">Especifique o valor de restrição: **Success**, **Failure** ou **Completion**.</span><span class="sxs-lookup"><span data-stu-id="97e2b-109">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97e2b-110"> A linha de restrição de precedência é verde para **Success**, realçado para **Failure**e azul para **Completion**.</span><span class="sxs-lookup"><span data-stu-id="97e2b-110">The precedence constraint line is green for **Success**, highlighted for **Failure**, and blue for **Completion**.</span></span>  
  
 <span data-ttu-id="97e2b-111">**Expression**</span><span class="sxs-lookup"><span data-stu-id="97e2b-111">**Expression**</span></span>  
 <span data-ttu-id="97e2b-112">Se usar as operações **Expressão**, **Expressão e Restrição**ou **Expressão ou Restrição**, digite uma expressão ou inicie o Construtor de Expressões para criar a expressão.</span><span class="sxs-lookup"><span data-stu-id="97e2b-112">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression or launch the Expression Builder to create the expression.</span></span> <span data-ttu-id="97e2b-113">A expressão deve ser avaliada como um booliano.</span><span class="sxs-lookup"><span data-stu-id="97e2b-113">The expression must evaluate to a Boolean.</span></span>  
  
 <span data-ttu-id="97e2b-114">**Test**</span><span class="sxs-lookup"><span data-stu-id="97e2b-114">**Test**</span></span>  
 <span data-ttu-id="97e2b-115">Valide a expressão.</span><span class="sxs-lookup"><span data-stu-id="97e2b-115">Validate the expression.</span></span>  
  
 <span data-ttu-id="97e2b-116">**AND lógico**</span><span class="sxs-lookup"><span data-stu-id="97e2b-116">**Logical AND**</span></span>  
 <span data-ttu-id="97e2b-117">Selecione para especificar que várias restrições de precedência no mesmo executável devem ser avaliadas juntas.</span><span class="sxs-lookup"><span data-stu-id="97e2b-117">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="97e2b-118">Todas as restrições devem ser avaliadas como `True`.</span><span class="sxs-lookup"><span data-stu-id="97e2b-118">All constraints must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97e2b-119">Este tipo de restrição de precedência aparece como uma linha sólida nas cores verde, realçado ou azul.</span><span class="sxs-lookup"><span data-stu-id="97e2b-119">This type of precedence constraint appears as a solid green, highlighted or blue line.</span></span>  
  
 <span data-ttu-id="97e2b-120">**OR lógico**</span><span class="sxs-lookup"><span data-stu-id="97e2b-120">**Logical OR**</span></span>  
 <span data-ttu-id="97e2b-121">Selecione para especificar que várias restrições de precedência no mesmo executável devem ser avaliadas juntas.</span><span class="sxs-lookup"><span data-stu-id="97e2b-121">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="97e2b-122">Pelo menos uma restrição deve ser avaliada como `True`.</span><span class="sxs-lookup"><span data-stu-id="97e2b-122">At least one constraint must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97e2b-123">Este tipo de restrição de precedência aparece como uma linha pontilhada nas cores verde, realçado ou azul.</span><span class="sxs-lookup"><span data-stu-id="97e2b-123">This type of precedence constraint appears as a dotted green, highlighted, or blue line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97e2b-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="97e2b-124">See Also</span></span>  
 <span data-ttu-id="97e2b-125">[Restrições de precedência](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="97e2b-125">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="97e2b-126">[Tarefas do Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="97e2b-126">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="97e2b-127">[Contêineres de Integration Services](control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="97e2b-127">[Integration Services Containers](control-flow/integration-services-containers.md) </span></span>  
 [<span data-ttu-id="97e2b-128">Expressões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="97e2b-128">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
