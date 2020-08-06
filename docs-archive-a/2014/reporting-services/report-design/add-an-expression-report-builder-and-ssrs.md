---
title: Adicionar uma expressão (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a60ee091-b4ed-41e1-9b6a-032c316cd03f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 16f414bfad47ae92681de50eb576a6ac2cb3f5fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679143"
---
# <a name="add-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="a3a0c-102">Adicionar uma expressão (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a3a0c-102">Add an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a3a0c-103">As expressões são usadas em um relatório inteiro para definir as propriedades de itens de relatório, os filtros, os grupos, a ordem de classificação, as cadeias de conexão e os valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-103">Expressions are used throughout a report for defining report item properties, filters, groups, sort order, connection strings, and parameter values.</span></span> <span data-ttu-id="a3a0c-104">As expressões começam com o sinal de igual (=) e são gravadas no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3a0c-104">Expressions begin with an equal sign (=) and are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="a3a0c-105">Elas são avaliadas durante a execução pelo processador de relatório, que combina o resultado da avaliação com os elementos de layout do relatório.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-105">They are evaluated at run time by the report processor, which combines the evaluation result with report layout elements.</span></span>  
  
 <span data-ttu-id="a3a0c-106">As expressões podem ser simples ou complexas.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-106">Expressions can be simple or complex.</span></span> <span data-ttu-id="a3a0c-107">Uma expressão simples faz referência a um único item de uma coleção interna.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-107">Simple expression refer to a single item in a built-in collection.</span></span> <span data-ttu-id="a3a0c-108">As expressões complexas podem conter constantes, operadores, itens de coleção global e chamadas de função.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-108">Complex expressions can contain constants, operators, global collection items, and function calls.</span></span> <span data-ttu-id="a3a0c-109">Para obter mais informações, consulte [Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a3a0c-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-expression-to-a-text-box"></a><span data-ttu-id="a3a0c-110">Para adicionar uma expressão a uma caixa de texto</span><span class="sxs-lookup"><span data-stu-id="a3a0c-110">To add an expression to a text box</span></span>  
  
-   <span data-ttu-id="a3a0c-111">No modo **Design** , clique na caixa de texto na superfície de design à qual você deseja adicionar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-111">In **Design** view, click the text box on the design surface to which you want to add an expression.</span></span>  
  
    -   <span data-ttu-id="a3a0c-112">No caso de uma expressão simples, digite na caixa de texto o texto para exibição da expressão.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-112">For a simple expression, type the display text for the expression in the text box.</span></span> <span data-ttu-id="a3a0c-113">Por exemplo, para o campo de conjunto de dados Vendas, digite `[Sales]`.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-113">For example, for the dataset field Sales, type `[Sales]`.</span></span>  
  
    -   <span data-ttu-id="a3a0c-114">No caso de uma expressão complexa, clique com o botão direito do mouse na caixa de texto e selecione **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-114">For a complex expression, right-click the text box, and select **Expression**.</span></span> <span data-ttu-id="a3a0c-115">A caixa de diálogo **Expressão** é aberta.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-115">The **Expression** dialog box opens.</span></span> <span data-ttu-id="a3a0c-116">Digite ou crie a expressão interativamente após o sinal '=' no painel Expressão e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-116">Type or interactively create your expression after the '=' in the expression pane, and then click OK.</span></span>  
  
         <span data-ttu-id="a3a0c-117">A expressão aparece na superfície de design como `<<Expr>>`.</span><span class="sxs-lookup"><span data-stu-id="a3a0c-117">The expression appears on the design surface as `<<Expr>>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a0c-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a3a0c-118">See Also</span></span>  
 <span data-ttu-id="a3a0c-119">[Formatando texto e espaços reservados &#40;Construtor de Relatórios e SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a3a0c-119">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a3a0c-120">[Caixas de texto &#40;Construtor de Relatórios e SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a3a0c-120">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a3a0c-121">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a3a0c-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a3a0c-122">[Exemplos de equações de filtro &#40;Construtor de Relatórios e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a3a0c-122">[Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a3a0c-123">[Exemplos de expressões de grupo &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a3a0c-123">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a3a0c-124">[Caixa de diálogo Expressão &#40;Construtor de Relatórios&#41;](../expression-dialog-box-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="a3a0c-124">[Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md) </span></span>  
 <span data-ttu-id="a3a0c-125">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a3a0c-125">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a3a0c-126">Adicionar um código a um relatório &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a3a0c-126">Add Code to a Report &#40;SSRS&#41;</span></span>](add-code-to-a-report-ssrs.md)  
  
  
