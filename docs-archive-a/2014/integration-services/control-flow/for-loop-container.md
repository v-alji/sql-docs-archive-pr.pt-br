---
title: Contêiner do Loop For | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.forloopcontainerdetails.f1
helpviewer_keywords:
- repeating control flow
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: 44cf7355-992b-4bbf-a28c-bfb012de06f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a6c864779237fdbf4dd249f87b7c06655293c047
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568749"
---
# <a name="for-loop-container"></a><span data-ttu-id="dbc6f-102">Contêiner Loop For</span><span class="sxs-lookup"><span data-stu-id="dbc6f-102">For Loop Container</span></span>
  <span data-ttu-id="dbc6f-103">O contêiner Loop For define um fluxo de controle repetitivo em um pacote.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-103">The For Loop container defines a repeating control flow in a package.</span></span> <span data-ttu-id="dbc6f-104">A implementação de loop é semelhante à estrutura de loop **For** em linguagens de programação.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-104">The loop implementation is similar to the **For** looping structure in programming languages.</span></span> <span data-ttu-id="dbc6f-105">Em cada repetição do loop, o contêiner Loop For avalia uma expressão e repete seu fluxo de trabalho até a expressão ser avaliada como `False`.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-105">In each repeat of the loop, the For Loop container evaluates an expression and repeats its workflow until the expression evaluates to `False`.</span></span>  
  
 <span data-ttu-id="dbc6f-106">O contêiner Loop For usa os seguintes elementos para definir o loop:</span><span class="sxs-lookup"><span data-stu-id="dbc6f-106">The For Loop container usesthe following elements to define the loop:</span></span>  
  
-   <span data-ttu-id="dbc6f-107">Uma expressão de inicialização opcional que atribui valores aos contadores de loop.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-107">An optional initialization expression that assigns values to the loop counters.</span></span>  
  
-   <span data-ttu-id="dbc6f-108">Uma expressão de avaliação que contém a expressão usada para testar se o loop deve parar ou continuar.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-108">An evaluation expression that contains the expression used to test whether the loop should stop or continue.</span></span>  
  
-   <span data-ttu-id="dbc6f-109">Uma expressão de iteração opcional que incrementa ou diminui o contador de loop.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-109">An optional iteration expression that increments or decrements the loop counter.</span></span>  
  
 <span data-ttu-id="dbc6f-110">O diagrama a seguir mostra um contêiner Loop For com uma tarefa Enviar Email.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-110">The following diagram shows a For Loop container with a Send Mail task.</span></span> <span data-ttu-id="dbc6f-111">Se a expressão de inicialização é `@Counter = 0`, a expressão de avaliação é `@Counter < 4`e a expressão de iteração é `@Counter = @Counter + 1`, o loop é repetido quatro vezes e envia quatro mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-111">If the initialization expression is `@Counter = 0`, the evaluation expression is `@Counter < 4`, and the iteration expression is `@Counter = @Counter + 1`, the loop repeats four times and sends four e-mail messages.</span></span>  
  
 <span data-ttu-id="dbc6f-112">![Um contêiner Loop For repete uma tarefa quatro vezes](../media/ssis-forloop.gif "Um contêiner Loop For repete uma tarefa quatro vezes")</span><span class="sxs-lookup"><span data-stu-id="dbc6f-112">![A For Loop container repeats a task four times](../media/ssis-forloop.gif "A For Loop container repeats a task four times")</span></span>  
  
 <span data-ttu-id="dbc6f-113">As expressões devem ser expressões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] válidas.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-113">The expressions must be valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions.</span></span>  
  
 <span data-ttu-id="dbc6f-114">Para criar as expressões de inicialização e de atribuição, você pode usar o operador de atribuição (=).</span><span class="sxs-lookup"><span data-stu-id="dbc6f-114">To create the initialization and assignment expressions, you can use the assignment operator (=).</span></span> <span data-ttu-id="dbc6f-115">Não há suporte para esse operador pela gramática de expressão do Integration Services e só pode ser usado pelos tipos de expressão de inicialização e de atribuição no contêiner Loop For.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-115">This operator is not otherwise supported by the Integration Services expression grammar and can only be used by the initialization and assignment expression types in the For Loop container.</span></span> <span data-ttu-id="dbc6f-116">Qualquer expressão que usa o operador de atribuição deve ter a sintaxe `@Var = <expression>`, em que **Var** é uma variável de tempo de execução e \<expression> é uma expressão que segue as regras da sintaxe de expressão do [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbc6f-116">Any expression that uses the assignment operator must have the syntax `@Var = <expression>`, where **Var** is a run-time variable and \<expression> is an expression that follows the rules of the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="dbc6f-117">A expressão pode incluir as variáveis, literais e quaisquer operadores e funções que a gramática de expressão SSIS ofereça suporte.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-117">The expression can include the variables, literals, and any operators and functions that the SSIS expression grammar supports.</span></span> <span data-ttu-id="dbc6f-118">A expressão deve avaliar um tipo de dados que pode ser convertido em tipo de dados da variável.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-118">The expression must evaluate to a data type that can be cast to the data type of the variable.</span></span>  
  
 <span data-ttu-id="dbc6f-119">Um contêiner Loop For pode ter só uma expressão de avaliação.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-119">A For Loop container can have only one evaluation expression.</span></span> <span data-ttu-id="dbc6f-120">Isso significa que o contêiner Loop For executa todos os seus elementos de fluxo de controle o mesmo número de vezes.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-120">This means that the For Loop container runs all its control flow elements the same number of times.</span></span> <span data-ttu-id="dbc6f-121">Como o contêiner Loop For pode incluir outros contêineres Loop For, você pode construir loops aninhados e implementar loop complexo em pacotes.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-121">Because the For Loop container can include other For Loop containers, you can build nested loops and implement complex looping in packages.</span></span>  
  
 <span data-ttu-id="dbc6f-122">Você pode definir uma propriedade de transação no contêiner Loop For para estabelecer uma transação para um subconjunto do fluxo de controle de pacote.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-122">You can set a transaction property on the For Loop container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="dbc6f-123">Desse modo, é possível gerenciar as transações em um nível mais granular.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-123">In this way, you can manage transactions at a more granular level.</span></span> <span data-ttu-id="dbc6f-124">Por exemplo, se um contêiner Loop For repetir um fluxo de controle que atualiza dados em uma tabela várias vezes, você poderá configurar o Loop For e seu fluxo de controle para usar uma transação para garantir que, se todos os dados não forem atualizados com êxito, nenhum dado seja atualizado.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-124">For example, if a For Loop container repeats a control flow that updates data in a table multiple times, you can configure the For Loop and its control flow to use a transaction to ensure that if not all data is updated successfully, no data is updated.</span></span> <span data-ttu-id="dbc6f-125">Para obter mais informações, consulte [Transações do Integration Services](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="dbc6f-125">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-for-loop-container"></a><span data-ttu-id="dbc6f-126">Configuração do contêiner Loop For</span><span class="sxs-lookup"><span data-stu-id="dbc6f-126">Configuration of the For Loop Container</span></span>  
 <span data-ttu-id="dbc6f-127">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-127">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="dbc6f-128">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="dbc6f-128">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="dbc6f-129">Editor do Loop For</span><span class="sxs-lookup"><span data-stu-id="dbc6f-129">For Loop Editor</span></span>](../for-loop-editor.md)  
  
-   [<span data-ttu-id="dbc6f-130">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="dbc6f-130">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="dbc6f-131">Para obter mais informações sobre como definir essas propriedades programaticamente, consulte a documentação da classe **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** no Guia do Desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="dbc6f-131">For more information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="dbc6f-132">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="dbc6f-132">Related Tasks</span></span>  
 <span data-ttu-id="dbc6f-133">Para obter informações sobre como configurar um contêiner Loop For, consulte os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="dbc6f-133">For information about how to configure a For Loop Container, see the following topics.</span></span>  
  
-   [<span data-ttu-id="dbc6f-134">Configurar um contêiner Loop For</span><span class="sxs-lookup"><span data-stu-id="dbc6f-134">Configure a For Loop Container</span></span>](for-loop-container.md)  
  
-   [<span data-ttu-id="dbc6f-135">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="dbc6f-135">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="dbc6f-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dbc6f-136">See Also</span></span>  
 <span data-ttu-id="dbc6f-137">[Fluxo de Controle](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="dbc6f-137">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="dbc6f-138">Expressões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dbc6f-138">Integration Services &#40;SSIS&#41; Expressions</span></span>](../expressions/integration-services-ssis-expressions.md)  
  
  
