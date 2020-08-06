---
title: Definir as propriedades de uma restrição de precedência | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Precedence Constraint Editor dialog box
- precedence constraints [Integration Services], properties
ms.assetid: d990f600-5c09-4cd5-8528-0a58d79dc9f2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 55b95bdb79d801156bef6198bc0f57accb5d9517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582519"
---
# <a name="set-the-properties-of-a-precedence-constraint"></a><span data-ttu-id="f10dd-102">Definir as propriedades de uma restrição de precedência</span><span class="sxs-lookup"><span data-stu-id="f10dd-102">Set the Properties of a Precedence Constraint</span></span>
  <span data-ttu-id="f10dd-103">Para definir propriedades em restrições de precedência, você pode usar uma destas ferramentas:</span><span class="sxs-lookup"><span data-stu-id="f10dd-103">To set properties on precedence constraints, you can use one of these tools:</span></span>  
  
-   <span data-ttu-id="f10dd-104">Você pode usar a caixa de diálogo **Editor de Restrição de Precedência** .</span><span class="sxs-lookup"><span data-stu-id="f10dd-104">You can use the **Precedence Constraint Editor** dialog box.</span></span>  
  
-   <span data-ttu-id="f10dd-105">Você pode usar a janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="f10dd-105">You can use the Properties window.</span></span> <span data-ttu-id="f10dd-106">A janela Propriedades lista as propriedades para configurar restrições de precedência que não estão disponíveis na caixa de diálogo **Editor de Restrição de Precedência** .</span><span class="sxs-lookup"><span data-stu-id="f10dd-106">The Properties window lists properties for configuring precedence constraints that are not available in the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="f10dd-107">Na janela Propriedades, você pode fornecer uma descrição e um nome da restrição de precedência e configurar a anotação para exibir a restrição de precedência na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="f10dd-107">In the Properties window, you can provide a description and name of the precedence constraint, and configure the annotation to display for the precedence constraint on the design surface.</span></span>  
  
 <span data-ttu-id="f10dd-108">Os procedimentos a seguir descrevem como definir propriedades em restrições de precedência usando cada dessas ferramentas.</span><span class="sxs-lookup"><span data-stu-id="f10dd-108">The following procedures describe how to set properties on precedence constraints by using each of these tools.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-precedence-constraint-editor"></a><span data-ttu-id="f10dd-109">Para definir as propriedades de uma restrição de precedência utilizando o Editor de Restrição de Precedência</span><span class="sxs-lookup"><span data-stu-id="f10dd-109">To set the properties of a precedence constraint by using the Precedence Constraint Editor</span></span>  
  
1.  <span data-ttu-id="f10dd-110">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="f10dd-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="f10dd-111">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="f10dd-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="f10dd-112">Clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="f10dd-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="f10dd-113">Clique duas vezes na restrição de precedência.</span><span class="sxs-lookup"><span data-stu-id="f10dd-113">Double-click the precedence constraint.</span></span>  
  
     <span data-ttu-id="f10dd-114">O **Editor de Restrição de Precedência** será aberto.</span><span class="sxs-lookup"><span data-stu-id="f10dd-114">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="f10dd-115">Na lista suspensa **Operação de avaliação** , selecione uma operação de avaliação.</span><span class="sxs-lookup"><span data-stu-id="f10dd-115">In the **Evaluation operation** drop-down list, select an evaluation operation.</span></span>  
  
6.  <span data-ttu-id="f10dd-116">Na `Value` lista suspensa, selecione o resultado da execução do executável de precedência.</span><span class="sxs-lookup"><span data-stu-id="f10dd-116">In the `Value` drop-down list, select the execution result of the precedence executable.</span></span>  
  
7.  <span data-ttu-id="f10dd-117">Se a operação de avaliação usar uma expressão, na `Expression` caixa, digite uma expressão e clique em **testar** para avaliar a expressão.</span><span class="sxs-lookup"><span data-stu-id="f10dd-117">If the evaluation operation uses an expression, in the `Expression` box, type an expression, and click **Test** to evaluate the expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f10dd-118">Nomes de variáveis diferenciam maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f10dd-118">Variable names are case-sensitive.</span></span>  
  
8.  <span data-ttu-id="f10dd-119">Se várias tarefas ou contêineres estiverem conectados ao executável restrito, selecione **lógico e** para especificar que os resultados da execução de todos os executáveis anteriores devem ser avaliados como `true` .</span><span class="sxs-lookup"><span data-stu-id="f10dd-119">If multiple tasks or containers are connected to the constrained executable, select **Logical AND** to specify that the execution results of all preceding executables must evaluate to `true`.</span></span> <span data-ttu-id="f10dd-120">Selecione **lógico ou** para especificar que apenas um resultado de execução deve ser avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="f10dd-120">Select **Logical OR** to specify that only one execution result must evaluate to `true`.</span></span>  
  
9. <span data-ttu-id="f10dd-121">Clique em **OK** para fechar o **Editor de Restrição de Precedência**.</span><span class="sxs-lookup"><span data-stu-id="f10dd-121">Click **OK** to close the **Precedence Constraint Editor**.</span></span>  
  
10. <span data-ttu-id="f10dd-122">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="f10dd-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-properties-window"></a><span data-ttu-id="f10dd-123">Para definir as propriedades de uma restrição de precedência utilizando a janela Propriedades</span><span class="sxs-lookup"><span data-stu-id="f10dd-123">To set the properties of a precedence constraint by using the Properties window</span></span>  
  
1.  <span data-ttu-id="f10dd-124">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote a ser modificado.</span><span class="sxs-lookup"><span data-stu-id="f10dd-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to modify.</span></span>  
  
2.  <span data-ttu-id="f10dd-125">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="f10dd-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="f10dd-126">Clique na guia **fluxo de controle** . Na superfície de design da guia **fluxo de controle** , clique com o botão direito do mouse na restrição de precedência e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f10dd-126">Click the **Control Flow** tab. On the design surface of the **Control Flow** tab, right-click the precedence constraint, and then click **Properties**.</span></span> <span data-ttu-id="f10dd-127">Na janela Propriedades, modifique os valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="f10dd-127">In the Properties window, modify the property values.</span></span>  
  
4.  <span data-ttu-id="f10dd-128">Na janela **Propriedades** , defina as seguintes propriedades de leitura/gravação de restrições de precedência:</span><span class="sxs-lookup"><span data-stu-id="f10dd-128">In the **Properties** window, set the following read/write properties of precedence constraints:</span></span>  
  
    |<span data-ttu-id="f10dd-129">Propriedade de leitura/gravação</span><span class="sxs-lookup"><span data-stu-id="f10dd-129">Read/write property</span></span>|<span data-ttu-id="f10dd-130">Ação de configuração</span><span class="sxs-lookup"><span data-stu-id="f10dd-130">Configuration action</span></span>|  
    |--------------------------|--------------------------|  
    |<span data-ttu-id="f10dd-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="f10dd-131">Description</span></span>|<span data-ttu-id="f10dd-132">Forneça uma descrição.</span><span class="sxs-lookup"><span data-stu-id="f10dd-132">Provide a description.</span></span>|  
    |<span data-ttu-id="f10dd-133">EvalOp</span><span class="sxs-lookup"><span data-stu-id="f10dd-133">EvalOp</span></span>|<span data-ttu-id="f10dd-134">Selecione uma operação de avaliação.</span><span class="sxs-lookup"><span data-stu-id="f10dd-134">Select an evaluation operation.</span></span> <span data-ttu-id="f10dd-135">Se a `Expression` operação, **ExpressionAndConstant**ou **ExpressionOrConstant** for selecionada, você poderá especificar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="f10dd-135">If the `Expression`, **ExpressionAndConstant**, or **ExpressionOrConstant** operation is selected, you can specify an expression.</span></span>|  
    |<span data-ttu-id="f10dd-136">Expression</span><span class="sxs-lookup"><span data-stu-id="f10dd-136">Expression</span></span>|<span data-ttu-id="f10dd-137">Se a operação de avaliação incluir uma expressão, forneça uma expressão.</span><span class="sxs-lookup"><span data-stu-id="f10dd-137">If the evaluation operation includes and expression, provide an expression.</span></span> <span data-ttu-id="f10dd-138">A expressão deve ser avaliada como um booliano.</span><span class="sxs-lookup"><span data-stu-id="f10dd-138">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="f10dd-139">Para obter mais informações sobre a linguagem de expressão, consulte [Expressões do Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f10dd-139">For more information about the expression language, see [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>|  
    |<span data-ttu-id="f10dd-140">LogicalAnd</span><span class="sxs-lookup"><span data-stu-id="f10dd-140">LogicalAnd</span></span>|<span data-ttu-id="f10dd-141">Defina `LogicalAnd` para especificar se a restrição de precedência é avaliada em conjunto com outras restrições de precedência, quando vários executáveis precedem e estão vinculados ao executável restrito</span><span class="sxs-lookup"><span data-stu-id="f10dd-141">Set `LogicalAnd` to specify whether the precedence constraint is evaluated in concert with other precedence constraints, when multiple executables precede and are linked to the constrained executable</span></span>|  
    |<span data-ttu-id="f10dd-142">Nome</span><span class="sxs-lookup"><span data-stu-id="f10dd-142">Name</span></span>|<span data-ttu-id="f10dd-143">Atualize o nome da restrição de precedência.</span><span class="sxs-lookup"><span data-stu-id="f10dd-143">Update the name of the precedence constraint.</span></span>|  
    |<span data-ttu-id="f10dd-144">ShowAnnotation</span><span class="sxs-lookup"><span data-stu-id="f10dd-144">ShowAnnotation</span></span>|<span data-ttu-id="f10dd-145">Especifique o tipo de anotação a ser usada.</span><span class="sxs-lookup"><span data-stu-id="f10dd-145">Specify the type of annotation to use.</span></span> <span data-ttu-id="f10dd-146">Selecione **Nunca** para desabilitar anotações, **AsNeeded** para habilitar a anotação sob demanda, **ConstraintName** para efetuar anotações automáticas usando o valor da propriedade Name, **ConstraintDescription** para efetuar anotações automaticamente usando o valor da propriedade Description e **ConstraintOptions** para efetuar anotações automáticas usando os valores das propriedades Value e Expression.</span><span class="sxs-lookup"><span data-stu-id="f10dd-146">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **ConstraintName** to automatically annotate using the value of the Name property, **ConstraintDescription** to automatically annotate using the value of the Description property, and **ConstraintOptions** to automatically annotate using the values of the Value and Expression properties.</span></span>|  
    |<span data-ttu-id="f10dd-147">Valor</span><span class="sxs-lookup"><span data-stu-id="f10dd-147">Value</span></span>|<span data-ttu-id="f10dd-148">Se a operação de avaliação especificada na propriedade EvalOP incluir uma restrição, selecione o resultado de execução do executável de restrição.</span><span class="sxs-lookup"><span data-stu-id="f10dd-148">If the evaluation operation specified in the EvalOP property includes a constraint, select the execution result of the constraining executable.</span></span>|  
  
5.  <span data-ttu-id="f10dd-149">Feche a janela Propriedades.</span><span class="sxs-lookup"><span data-stu-id="f10dd-149">Close the Properties window.</span></span>  
  
6.  <span data-ttu-id="f10dd-150">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="f10dd-150">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10dd-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f10dd-151">See Also</span></span>  
 <span data-ttu-id="f10dd-152">[Restrições de precedência](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="f10dd-152">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="f10dd-153">[Conectar tarefas e contêineres usando uma restrição de precedência padrão](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="f10dd-153">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="f10dd-154">[Definir o valor de uma restrição de precedência usando o menu de atalho](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="f10dd-154">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 [<span data-ttu-id="f10dd-155">Usar uma expressão em uma restrição de precedência</span><span class="sxs-lookup"><span data-stu-id="f10dd-155">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
