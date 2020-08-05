---
title: Constantes em expressões (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b8ae650b-0f46-4848-b62b-15f8a40751b8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d95005a04482cb03d3bb3860aea695c7e7969255
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572449"
---
# <a name="constants-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="dd13b-102">Constantes em expressões (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="dd13b-102">Constants in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dd13b-103">Uma constante consiste em texto literal ou texto predefinido.</span><span class="sxs-lookup"><span data-stu-id="dd13b-103">A constant consists of literal text or predefined text.</span></span> <span data-ttu-id="dd13b-104">O processador de relatório tem acesso às constantes predefinidas; portanto, quando elas são incluídas em uma expressão, os valores que elas representam são substituídos na expressão antes de ela ser avaliada.</span><span class="sxs-lookup"><span data-stu-id="dd13b-104">The report processor has access to predefined constants so that when you include them in an expression, the values they represent are substituted in the expression before it is evaluated.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="literal-text"></a><span data-ttu-id="dd13b-105">Texto literal</span><span class="sxs-lookup"><span data-stu-id="dd13b-105">Literal Text</span></span>  
 <span data-ttu-id="dd13b-106">Em uma expressão, texto literal é o texto que está entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="dd13b-106">In an expression, literal text is text that is in double quotation marks.</span></span> <span data-ttu-id="dd13b-107">Você também poderá digitar o texto diretamente em uma caixa de texto sem aspas duplas, se ele não fizer parte de uma expressão.</span><span class="sxs-lookup"><span data-stu-id="dd13b-107">You can also type text directly into a text box without double quotation marks if it is not part of an expression.</span></span> <span data-ttu-id="dd13b-108">Se o valor da caixa de texto não começar com um sinal de igual (=), o texto será tratado como texto literal.</span><span class="sxs-lookup"><span data-stu-id="dd13b-108">If the text box value does not begin with an equal sign (=), the text is treated as literal text.</span></span> <span data-ttu-id="dd13b-109">A tabela a seguir mostra vários exemplos de texto literal em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="dd13b-109">The following table shows several examples of literal text in an expression.</span></span>  
  
|<span data-ttu-id="dd13b-110">Constante</span><span class="sxs-lookup"><span data-stu-id="dd13b-110">Constant</span></span>|<span data-ttu-id="dd13b-111">Exibir texto</span><span class="sxs-lookup"><span data-stu-id="dd13b-111">Display text</span></span>|<span data-ttu-id="dd13b-112">Texto de expressão</span><span class="sxs-lookup"><span data-stu-id="dd13b-112">Expression text</span></span>|  
|--------------|------------------|---------------------|  
|<span data-ttu-id="dd13b-113">Execução do relatório em:</span><span class="sxs-lookup"><span data-stu-id="dd13b-113">Report run at:</span></span>|<\<Expr>>|`="Report run at: " & Globals!ExecutionTime`|  
|<span data-ttu-id="dd13b-114">Ciclos da Adventure Works</span><span class="sxs-lookup"><span data-stu-id="dd13b-114">Adventure Works Cycles</span></span>|<span data-ttu-id="dd13b-115">Ciclos da Adventure Works</span><span class="sxs-lookup"><span data-stu-id="dd13b-115">Adventure Works Cycles</span></span>|<span data-ttu-id="dd13b-116">Ciclos da Adventure Works</span><span class="sxs-lookup"><span data-stu-id="dd13b-116">Adventure Works Cycles</span></span>|  
|<span data-ttu-id="dd13b-117">[Texto de exibição entre colchetes]</span><span class="sxs-lookup"><span data-stu-id="dd13b-117">[Bracketed display text]</span></span>|<span data-ttu-id="dd13b-118">\\[Texto de exibição entre colchetes\\]</span><span class="sxs-lookup"><span data-stu-id="dd13b-118">\\[Bracketed display text\\]</span></span>|<span data-ttu-id="dd13b-119">[Texto de exibição entre colchetes]</span><span class="sxs-lookup"><span data-stu-id="dd13b-119">[Bracketed display text]</span></span>|  
  
## <a name="rdl-constants"></a><span data-ttu-id="dd13b-120">Constantes RDL</span><span class="sxs-lookup"><span data-stu-id="dd13b-120">RDL Constants</span></span>  
 <span data-ttu-id="dd13b-121">É possível usar constantes definidas em linguagem RDL (Report Definition Language) em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="dd13b-121">You can use constants defined in Report Definition Language (RDL) in an expression.</span></span> <span data-ttu-id="dd13b-122">Na caixa de diálogo **Expressão** , as constantes são exibidas quando você cria uma expressão para uma propriedade de relatório que aceita apenas determinados valores válidos, também conhecidos como tipos enumerados.</span><span class="sxs-lookup"><span data-stu-id="dd13b-122">In the **Expression** dialog box, constants appear when you create an expression for a report property that only accepts certain valid values, also known as enumerated types.</span></span> <span data-ttu-id="dd13b-123">A tabela a seguir mostra dois exemplos.</span><span class="sxs-lookup"><span data-stu-id="dd13b-123">The following table shows two examples.</span></span>  
  
|<span data-ttu-id="dd13b-124">Propriedade</span><span class="sxs-lookup"><span data-stu-id="dd13b-124">Property</span></span>|<span data-ttu-id="dd13b-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd13b-125">Description</span></span>|<span data-ttu-id="dd13b-126">Valores</span><span class="sxs-lookup"><span data-stu-id="dd13b-126">Values</span></span>|  
|--------------|-----------------|------------|  
|<span data-ttu-id="dd13b-127">TextAlign</span><span class="sxs-lookup"><span data-stu-id="dd13b-127">TextAlign</span></span>|<span data-ttu-id="dd13b-128">Valores válidos para alinhamento de texto em uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="dd13b-128">Valid values for aligning text in a text box.</span></span>|<span data-ttu-id="dd13b-129">Geral, À Esquerda, Centralizado, À Direita</span><span class="sxs-lookup"><span data-stu-id="dd13b-129">General, Left, Center, Right</span></span>|  
|<span data-ttu-id="dd13b-130">BorderStyle</span><span class="sxs-lookup"><span data-stu-id="dd13b-130">BorderStyle</span></span>|<span data-ttu-id="dd13b-131">Valores válidos para uma linha adicionada a um relatório.</span><span class="sxs-lookup"><span data-stu-id="dd13b-131">Valid values for a line added to a report.</span></span>|<span data-ttu-id="dd13b-132">Padrão, Nenhum, Pontilhado, Tracejado, Sólido, Duplo, TraçoPonto, TraçoPontoPonto</span><span class="sxs-lookup"><span data-stu-id="dd13b-132">Default, None, Dotted, Dashed, Solid, Double, DashDot, DashDotdot</span></span>|  
  
## <a name="visual-basic-constants"></a><span data-ttu-id="dd13b-133">Constantes do Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd13b-133">Visual Basic Constants</span></span>  
 <span data-ttu-id="dd13b-134">É possível usar constantes definidas na biblioteca de tempo de execução [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="dd13b-134">You can use constants defined in the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library in an expression.</span></span> <span data-ttu-id="dd13b-135">Por exemplo, você pode usar a constante `DateInterval.Day`.</span><span class="sxs-lookup"><span data-stu-id="dd13b-135">For example, you can use the constant `DateInterval.Day`.</span></span> <span data-ttu-id="dd13b-136">A seguinte expressão para a data de 10 de janeiro de 2008 retorna o número 10:</span><span class="sxs-lookup"><span data-stu-id="dd13b-136">The following expression for the date January 10, 2008 returns the number 10:</span></span>  
  
 `=DatePart("d",Globals!ExecutionTime)`  
  
## <a name="clr-constants"></a><span data-ttu-id="dd13b-137">Constantes CLR</span><span class="sxs-lookup"><span data-stu-id="dd13b-137">CLR Constants</span></span>  
 <span data-ttu-id="dd13b-138">É possível usar constantes definidas nas classes CLR (Common Language Runtime) [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="dd13b-138">You can use constants defined in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language run-time (CLR) classes in an expression.</span></span> <span data-ttu-id="dd13b-139">A tabela a seguir mostra um exemplo de uma cor definida pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="dd13b-139">The following table shows an example of a system-defined color.</span></span>  
  
|<span data-ttu-id="dd13b-140">Constante</span><span class="sxs-lookup"><span data-stu-id="dd13b-140">Constant</span></span>|<span data-ttu-id="dd13b-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd13b-141">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="dd13b-142">MistyRose</span><span class="sxs-lookup"><span data-stu-id="dd13b-142">MistyRose</span></span>|<span data-ttu-id="dd13b-143">Ao criar uma expressão para uma propriedade do relatório baseada na cor do plano de fundo, é possível especificar uma cor pelo nome.</span><span class="sxs-lookup"><span data-stu-id="dd13b-143">When you create an expression for a report property that is based on background color, you can specify a color by name.</span></span> <span data-ttu-id="dd13b-144">Os nomes válidos são listados na caixa de diálogo **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="dd13b-144">Valid names are listed in the **Expression** dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd13b-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dd13b-145">See Also</span></span>  
 <span data-ttu-id="dd13b-146">[Caixa de diálogo expressão](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="dd13b-146">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="dd13b-147">[Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd13b-147">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd13b-148">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd13b-148">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd13b-149">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd13b-149">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="dd13b-150">Caixa de diálogo Expressão &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="dd13b-150">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
