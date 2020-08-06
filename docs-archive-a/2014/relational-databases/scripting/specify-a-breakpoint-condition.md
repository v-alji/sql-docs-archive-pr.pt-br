---
title: Especificar uma condição de ponto de interrupção
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint conditions
ms.assetid: b43d8a2b-99a3-4fb7-8848-99c042ea7ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 659b6ca1149eb8f0412efbe2adbaf4c1ffce59d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681536"
---
# <a name="specify-a-breakpoint-condition"></a><span data-ttu-id="fd9b6-102">Especificar uma condição de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="fd9b6-102">Specify a Breakpoint Condition</span></span>
  <span data-ttu-id="fd9b6-103">Uma condição de ponto de interrupção é uma expressão [!INCLUDE[tsql](../../includes/tsql-md.md)] que é avaliada pelo depurador ao atingir o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-103">A breakpoint condition is a [!INCLUDE[tsql](../../includes/tsql-md.md)] expression that is evaluated by the debugger when the breakpoint is reached.</span></span> <span data-ttu-id="fd9b6-104">Se a condição for atendida e qualquer contagem de ocorrências especificada for atingida, o depurador será interrompido ou executará a ação especificada para o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-104">If the condition is satisfied and any specified hit count reached, the debugger either breaks or performs the action specified for the breakpoint.</span></span>  
  
## <a name="specifying-conditions"></a><span data-ttu-id="fd9b6-105">Especificando condições</span><span class="sxs-lookup"><span data-stu-id="fd9b6-105">Specifying Conditions</span></span>  
 <span data-ttu-id="fd9b6-106">A expressão especificada deve ser uma expressão Transact-SQL válida que seja avaliada como um valor Booliano.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-106">The expression specified must be a valid Transact-SQL expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="fd9b6-107">Para obter mais informações, veja [Expressões &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fd9b6-107">For more information, see [Expressions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql).</span></span>  
  
 <span data-ttu-id="fd9b6-108">Se você especificar uma condição de ponto de interrupção com sintaxe inválida, será exibida uma mensagem de aviso imediatamente.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-108">If you specify a breakpoint condition with invalid syntax, a warning message appears immediately.</span></span> <span data-ttu-id="fd9b6-109">Se você especificar uma condição com sintaxe válida, mas semântica inválidas, será exibida uma mensagem de aviso da primeira vez que o ponto de interrupção for atingido.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-109">If you specify a condition with valid syntax but invalid semantics, a warning message is displayed the first time the breakpoint is hit.</span></span> <span data-ttu-id="fd9b6-110">Em qualquer um dos casos, o depurador interromperá a execução quando o ponto de interrupção inválido for atingido.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-110">In either case, the debugger breaks execution when the invalid breakpoint is hit.</span></span>  
  
#### <a name="to-specify-a-condition"></a><span data-ttu-id="fd9b6-111">Para especificar uma condição</span><span class="sxs-lookup"><span data-stu-id="fd9b6-111">To Specify a Condition</span></span>  
  
1.  <span data-ttu-id="fd9b6-112">Na janela do editor, clique com o botão direito do mouse no glifo do ponto de interrupção e clique em **Condição** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-112">In the editor window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="fd9b6-113">-ou-</span><span class="sxs-lookup"><span data-stu-id="fd9b6-113">-or-</span></span>  
  
     <span data-ttu-id="fd9b6-114">Na janela **Pontos de Interrupção** , clique com o botão direito do mouse no glifo do ponto de interrupção e clique em **Condição** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-114">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="fd9b6-115">Na caixa de diálogo **Condição de Ponto de Interrupção** , insira uma expressão Booliana válida na caixa **Condição** .</span><span class="sxs-lookup"><span data-stu-id="fd9b6-115">In the **Breakpoint Condition** dialog box, enter a valid Boolean expression in the **Condition** box.</span></span>  
  
3.  <span data-ttu-id="fd9b6-116">Escolher **será verdadeiro** se você quiser interromper quando a expressão for avaliada `true` ou se escolher **tiver mudado** se desejar interromper quando o valor da expressão for alterado.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-116">Choose **Is true** if you want to break when the expression evaluates to `true`, or choose **Has changed** if you want to break when the value of the expression has changed.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fd9b6-117">O depurador não avalia a expressão Booliana até a primeira vez que o ponto de interrupção é atingido.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-117">The debugger does not evaluate the Boolean expression until the first time the breakpoint is reached.</span></span> <span data-ttu-id="fd9b6-118">Se você escolher **Has changed**, o depurador não considerará a primeira avaliação como uma alteração, então o depurador não interromperá na primeira avaliação.</span><span class="sxs-lookup"><span data-stu-id="fd9b6-118">If you choose **Has changed**, the debugger does not consider the first evaluation to be a change, so the debugger will not break on the first evaluation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd9b6-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd9b6-119">See Also</span></span>  
 <span data-ttu-id="fd9b6-120">[Especificar uma contagem de acesso](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="fd9b6-120">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="fd9b6-121">Especificar uma ação de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="fd9b6-121">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
