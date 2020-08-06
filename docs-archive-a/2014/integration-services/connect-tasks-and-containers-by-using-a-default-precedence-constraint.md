---
title: Conectar tarefas e contêineres usando uma restrição de precedência padrão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- default precedence constraints
- containers [Integration Services], precedence constraints
ms.assetid: 8f31f15f-98ff-4c35-b41f-8b8cfd148d75
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 00207172babdb41b1030e77e71a2c8bc3b99799d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684291"
---
# <a name="connect-tasks-and-containers-by-using-a-default-precedence-constraint"></a><span data-ttu-id="066de-102">Como conectar tarefas e contêineres por meio de uma restrição de precedência padrão</span><span class="sxs-lookup"><span data-stu-id="066de-102">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>
  <span data-ttu-id="066de-103">Restrições de precedência conectam dois executáveis.</span><span class="sxs-lookup"><span data-stu-id="066de-103">Precedence constraints connect two executables.</span></span> <span data-ttu-id="066de-104">Um executável pode ser qualquer tarefa ou um contêiner Loop For, Loop Foreach ou Sequência.</span><span class="sxs-lookup"><span data-stu-id="066de-104">An executable can be any task or a For Loop, Foreach Loop, or Sequence container.</span></span> <span data-ttu-id="066de-105">Este procedimento descreve como definir o comportamento padrão de restrições de precedência e como conectar executáveis usando as restrições de precedência padrão.</span><span class="sxs-lookup"><span data-stu-id="066de-105">This procedure describes how to set the default behavior for precedence constraints, and how to connect executables using the default precedence constraints.</span></span>  
  
## <a name="creating-default-precedence-constraints"></a><span data-ttu-id="066de-106">Criando restrições de precedência padrão</span><span class="sxs-lookup"><span data-stu-id="066de-106">Creating Default Precedence Constraints</span></span>  
 <span data-ttu-id="066de-107">Quando você usa o [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer pela primeira vez, o valor padrão de uma restrição de precedência é `Success`.</span><span class="sxs-lookup"><span data-stu-id="066de-107">When you first use [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the default value of a precedence constraint is `Success`.</span></span> <span data-ttu-id="066de-108">Siga estas etapas para configurar o [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer para usar um valor padrão diferente para restrições de precedência.</span><span class="sxs-lookup"><span data-stu-id="066de-108">Follow these steps to configure [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to use a different default value for precedence constraints.</span></span>  
  
#### <a name="to-set-the-default-value-for-precedence-constraints"></a><span data-ttu-id="066de-109">Para definir o valor padrão de restrições de precedência</span><span class="sxs-lookup"><span data-stu-id="066de-109">To set the default value for precedence constraints</span></span>  
  
1.  <span data-ttu-id="066de-110">Abra o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="066de-110">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="066de-111">No menu **Ferramentas** , clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="066de-111">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="066de-112">Na caixa de diálogo **Opções** , expanda **Designers do Business Intelligence** e então expanda **Designers do Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="066de-112">In the **Options** dialog box, expand **Business Intelligence Designers,** and then expand **Integration Services Designers**.</span></span>  
  
4.  <span data-ttu-id="066de-113">Clique em **Conexão Automática do Fluxo de Controle** e selecione **Conectar uma nova forma à forma selecionada por padrão**.</span><span class="sxs-lookup"><span data-stu-id="066de-113">Click **Control Flow Auto Connect** and select **Connect a new shape to the selected shape by default**.</span></span>  
  
5.  <span data-ttu-id="066de-114">Na lista suspensa, escolha **Usar uma restrição de Falha para a nova forma** ou **Usar uma restrição de Conclusão para a nova forma**.</span><span class="sxs-lookup"><span data-stu-id="066de-114">In the drop-down list, choose either **Use a Failure constraint for the new shape** or **Use a Completion constraint for the new shape**.</span></span>  
  
6.  <span data-ttu-id="066de-115">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="066de-115">Click **OK**.</span></span>  
  
#### <a name="to-create-a-default-precedence-constraint"></a><span data-ttu-id="066de-116">Para criar uma restrição de precedência padrão</span><span class="sxs-lookup"><span data-stu-id="066de-116">To create a default precedence constraint</span></span>  
  
1.  <span data-ttu-id="066de-117">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="066de-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="066de-118">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="066de-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="066de-119">Clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="066de-119">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="066de-120">Na superfície de design da guia **Fluxo de Controle** , clique na tarefa ou no contêiner e arraste seu conector para o executável em que você deseja aplicar a restrição de precedência.</span><span class="sxs-lookup"><span data-stu-id="066de-120">On the design surface of the **Control Flow** tab, click the task or container and drag its connector to the executable to which you want the precedence constraint to apply.</span></span>  
  
5.  <span data-ttu-id="066de-121">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="066de-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="066de-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="066de-122">See Also</span></span>  
 <span data-ttu-id="066de-123">[Restrições de precedência](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="066de-123">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="066de-124">[Definir o valor de uma restrição de precedência usando o menu de atalho](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="066de-124">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="066de-125">[Definir as propriedades de uma restrição de precedência](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="066de-125">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="066de-126">Usar uma expressão em uma restrição de precedência</span><span class="sxs-lookup"><span data-stu-id="066de-126">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
