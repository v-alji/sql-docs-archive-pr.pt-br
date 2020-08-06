---
title: Usar uma expressão em uma restrição de precedência | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- precedence constraints [Integration Services], adding expressions
- expressions [Integration Services], adding
ms.assetid: 601038bb-3b17-42ac-b09d-5b3a82fb6564
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a997efa448a8381cc8251cd4cbf69dc59f8968e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680982"
---
# <a name="use-an-expression-in-a-precedence-constraint"></a><span data-ttu-id="d623e-102">Usar uma expressão em uma restrição de precedência</span><span class="sxs-lookup"><span data-stu-id="d623e-102">Use an Expression in a Precedence Constraint</span></span>
  <span data-ttu-id="d623e-103">Este procedimento descreve como adicionar uma expressão a uma restrição de precedência usando a caixa de diálogo **Editor de Restrição de Precedência** .</span><span class="sxs-lookup"><span data-stu-id="d623e-103">This procedure describes how to add an expression to a precedence constraint by using the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="d623e-104">Antes de você poder adicionar uma expressão a uma restrição de precedência, o pacote deve incluir pelo menos dois executáveis, tarefas ou contêineres, e eles devem ser conectados por uma restrição de precedência.</span><span class="sxs-lookup"><span data-stu-id="d623e-104">Before you can add an expression to a precedence constraint, the package must include at least two executables, either tasks or containers, and they must be connected by a precedence constraint.</span></span>  
  
### <a name="to-add-an-expression-to-a-precedence-constraint"></a><span data-ttu-id="d623e-105">Como adicionar uma expressão a uma restrição de precedência</span><span class="sxs-lookup"><span data-stu-id="d623e-105">To add an expression to a precedence constraint</span></span>  
  
1.  <span data-ttu-id="d623e-106">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="d623e-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="d623e-107">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="d623e-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="d623e-108">Clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="d623e-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="d623e-109">Na superfície de design da guia **Fluxo de Controle** , clique duas vezes na restrição de precedência.</span><span class="sxs-lookup"><span data-stu-id="d623e-109">On the design surface of the **Control Flow** tab, double-click the precedence constraint.</span></span> <span data-ttu-id="d623e-110">O **Editor de Restrição de Precedência** será aberto.</span><span class="sxs-lookup"><span data-stu-id="d623e-110">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="d623e-111">Selecione **Expressão**, **Expressão e Restrição**ou **Expressão ou Restrição** na lista **Operação de avaliação** .</span><span class="sxs-lookup"><span data-stu-id="d623e-111">Select **Expression**, **Expression and Constraint**, or **Expression or Constraint** in the **Evaluation operation** list.</span></span>  
  
6.  <span data-ttu-id="d623e-112">Digite uma expressão na caixa de texto **Expressão** ou inicie o Construtor de Expressões para criar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="d623e-112">Type an expression in the **Expression** text box or launch the Expression Builder to create an expression.</span></span>  
  
7.  <span data-ttu-id="d623e-113">Para validar a sintaxe da expressão, clique em **Testar**.</span><span class="sxs-lookup"><span data-stu-id="d623e-113">To validate the expression syntax, click **Test**.</span></span>  
  
8.  <span data-ttu-id="d623e-114">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="d623e-114">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d623e-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d623e-115">See Also</span></span>  
 <span data-ttu-id="d623e-116">[Restrições de precedência](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="d623e-116">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="d623e-117">[Conectar tarefas e contêineres usando uma restrição de precedência padrão](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="d623e-117">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="d623e-118">[Definir o valor de uma restrição de precedência usando o menu de atalho](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="d623e-118">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="d623e-119">[Definir as propriedades de uma restrição de precedência](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="d623e-119">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="d623e-120">Expressões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d623e-120">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
