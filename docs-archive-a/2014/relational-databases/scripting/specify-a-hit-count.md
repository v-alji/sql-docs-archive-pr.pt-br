---
title: Especificar uma contagem de ocorrências
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.breakpt.hitcount
helpviewer_keywords:
- Transact-SQL debugger, breakpoint hit count
ms.assetid: 24836939-94ed-4e57-aa85-5d6938d859e4
author: rothja
ms.author: jroth
ms.openlocfilehash: 34c75e990bce1ea5e64c0b45f7acbcaa52fc3c40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576271"
---
# <a name="specify-a-hit-count"></a><span data-ttu-id="65157-102">Especificar uma contagem de ocorrências</span><span class="sxs-lookup"><span data-stu-id="65157-102">Specify a Hit Count</span></span>
  <span data-ttu-id="65157-103">Uma contagem de ocorrências de ponto de interrupção é um contador incrementado pelo depurador do [!INCLUDE[tsql](../../includes/tsql-md.md)] a cada vez que o ponto de interrupção é atingido.</span><span class="sxs-lookup"><span data-stu-id="65157-103">A breakpoint hit count is a counter that is incremented by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger each time the breakpoint is reached.</span></span> <span data-ttu-id="65157-104">Se a contagem de ocorrências especificada for atingida, e qualquer condição de ponto de interrupção especificada for atendida, o depurador executará a ação especificada para o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="65157-104">If the specified hit count is reached and any specified breakpoint condition is satisfied, the debugger performs the action specified for the breakpoint.</span></span>  
  
## <a name="hit-count-considerations"></a><span data-ttu-id="65157-105">Considerações sobre a contagem de ocorrências</span><span class="sxs-lookup"><span data-stu-id="65157-105">Hit Count Considerations</span></span>  
 <span data-ttu-id="65157-106">Por padrão, a execução é interrompida sempre que um ponto de interrupção é atingido.</span><span class="sxs-lookup"><span data-stu-id="65157-106">By default, execution breaks every time a breakpoint is hit.</span></span> <span data-ttu-id="65157-107">Você pode escolher uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="65157-107">You can choose between the following options:</span></span>  
  
-   <span data-ttu-id="65157-108">Interromper sempre (o padrão).</span><span class="sxs-lookup"><span data-stu-id="65157-108">Break always (the default).</span></span>  
  
-   <span data-ttu-id="65157-109">Interromper quando a contagem de ocorrências for igual a um valor especificado.</span><span class="sxs-lookup"><span data-stu-id="65157-109">Break when the hit count equals a specified value.</span></span>  
  
-   <span data-ttu-id="65157-110">Interromper quando a contagem de ocorrências for igual a um múltiplo do valor especificado.</span><span class="sxs-lookup"><span data-stu-id="65157-110">Break when the hit count equals a multiple of a specified value.</span></span>  
  
-   <span data-ttu-id="65157-111">Interromper quando a contagem de ocorrências for maior ou igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="65157-111">Break when the hit count is greater than or equal to a specified value.</span></span>  
  
 <span data-ttu-id="65157-112">As contagens de ocorrências de ponto de interrupção são incrementadas dentro do escopo de uma sessão de depuração.</span><span class="sxs-lookup"><span data-stu-id="65157-112">Breakpoint hit counts are incremented within the scope of a debugging session.</span></span> <span data-ttu-id="65157-113">Todas as contagens de ocorrências são definidas como zero no início de cada sessão de depuração.</span><span class="sxs-lookup"><span data-stu-id="65157-113">All hit counts are set to zero at the start of each debugging session.</span></span>  
  
 <span data-ttu-id="65157-114">Se você desejar controlar quantas vezes um ponto de interrupção é atingido sem ter a execução do ponto de interrupção, especifique uma contagem de ocorrências com um valor muito alto para que o ponto de interrupção nunca interrompa.</span><span class="sxs-lookup"><span data-stu-id="65157-114">If you want to track how many times a breakpoint is hit without having the breakpoint break execution, specify a hit count with a very high value so the breakpoint never breaks.</span></span>  
  
 <span data-ttu-id="65157-115">A ação padrão de um ponto de interrupção é interromper a execução quando a contagem de ocorrências e a condição de ponto de interrupção são atendidas.</span><span class="sxs-lookup"><span data-stu-id="65157-115">The default action for a breakpoint is to break execution when both the hit count and breakpoint condition have been satisfied.</span></span> <span data-ttu-id="65157-116">Para obter mais informações sobre como especificar outra ações, consulte [Especificar uma ação de ponto de interrupção](specify-a-breakpoint-action.md).</span><span class="sxs-lookup"><span data-stu-id="65157-116">For information about specifying other actions, see [Specify a Breakpoint Action](specify-a-breakpoint-action.md).</span></span>  
  
#### <a name="to-specify-a-hit-count"></a><span data-ttu-id="65157-117">Para especificar uma contagem de ocorrências</span><span class="sxs-lookup"><span data-stu-id="65157-117">To Specify a Hit Count</span></span>  
  
1.  <span data-ttu-id="65157-118">Na janela do editor, clique com o botão direito do mouse no glifo do ponto de interrupção e clique em **Contagem de Ocorrências** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="65157-118">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="65157-119">-ou-</span><span class="sxs-lookup"><span data-stu-id="65157-119">-or-</span></span>  
  
     <span data-ttu-id="65157-120">Na janela **Pontos de Interrupção** , clique com o botão direito do mouse no glifo de ponto de interrupção e clique em **Contagem de Ocorrências** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="65157-120">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="65157-121">Na caixa de diálogo **Contagem de Ocorrências de Ponto de interrupção** , selecione o comportamento desejado na caixa **Quando o ponto de interrupção for atingido** .</span><span class="sxs-lookup"><span data-stu-id="65157-121">In the **Breakpoint Hit Count** dialog box, select the behavior you want from the **When the breakpoint is hit** box.</span></span>  
  
     <span data-ttu-id="65157-122">Se você escolher qualquer configuração diferente de **Interromper Sempre**, uma caixa de texto será exibida à direita da lista.</span><span class="sxs-lookup"><span data-stu-id="65157-122">If you choose any setting other than **Break Always**, a text box appears to the right of the list.</span></span> <span data-ttu-id="65157-123">Digite um inteiro na caixa de texto para especificar a contagem de ocorrências desejada.</span><span class="sxs-lookup"><span data-stu-id="65157-123">Enter an integer in the text box to specify the hit count you want.</span></span>  
  
3.  <span data-ttu-id="65157-124">Clique em **OK** para implementar as alterações ou em **Cancelar** para sair sem aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="65157-124">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
#### <a name="to-view-or-reset-the-current-hit-count"></a><span data-ttu-id="65157-125">Para exibir ou redefinir a contagem de ocorrências atual</span><span class="sxs-lookup"><span data-stu-id="65157-125">To View or Reset the Current Hit Count</span></span>  
  
1.  <span data-ttu-id="65157-126">Na janela do editor, clique com o botão direito do mouse no glifo do ponto de interrupção e clique em **Contagem de Ocorrências** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="65157-126">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="65157-127">-ou-</span><span class="sxs-lookup"><span data-stu-id="65157-127">-or-</span></span>  
  
     <span data-ttu-id="65157-128">Na janela **Pontos de Interrupção** , clique com o botão direito do mouse no glifo de ponto de interrupção e clique em **Contagem de Ocorrências** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="65157-128">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="65157-129">Na caixa de diálogo **Contagem de Ocorrências de Ponto de interrupção** , **Contagem de ocorrências atual:** é exibido imediatamente acima do botão **Redefinir** .</span><span class="sxs-lookup"><span data-stu-id="65157-129">In the **Breakpoint Hit Count** dialog box, the **Current hit count:** is displayed just above the **Reset** button.</span></span>  
  
3.  <span data-ttu-id="65157-130">Clique em **Redefinir** se desejar definir a contagem de ocorrências atual como zero.</span><span class="sxs-lookup"><span data-stu-id="65157-130">Click **Reset** if you want to set the current hit count to zero.</span></span>  
  
4.  <span data-ttu-id="65157-131">Clique em **OK** ou em **Cancelar** para sair do diálogo.</span><span class="sxs-lookup"><span data-stu-id="65157-131">Click **OK** or **Cancel** to exit the dialog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65157-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="65157-132">See Also</span></span>  
 [<span data-ttu-id="65157-133">Especificar uma condição de ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="65157-133">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)  
  
  
