---
title: Usar uma expressão em um componente de fluxo de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], data flow
- expressions [Integration Services], data flow components
ms.assetid: 9181b998-d24a-41fb-bb3c-14eee34f910d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 653bf468d0af6d44c5abe7344fcc13f93f86b430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681746"
---
# <a name="use-an-expression-in-a-data-flow-component"></a><span data-ttu-id="aefc9-102">Usar uma expressão em um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="aefc9-102">Use an Expression in a Data Flow Component</span></span>
  <span data-ttu-id="aefc9-103">Este procedimento descreve como adicionar uma expressão à transformação Divisão Condicional ou à transformação Coluna derivada.</span><span class="sxs-lookup"><span data-stu-id="aefc9-103">This procedure describes how to add an expression to the Conditional Split transformation or to the Derived Column transformation.</span></span> <span data-ttu-id="aefc9-104">A transformação Divisão Condicional usa expressões para definir as condições que direcionam linhas de dados a uma saída de transformação e a transformação Coluna Derivada usa expressões para definir valores atribuídos a colunas.</span><span class="sxs-lookup"><span data-stu-id="aefc9-104">The Conditional Split transformation uses expressions to define the conditions that direct data rows to a transformation output, and the Derived Column transformation uses expressions to define values assigned to columns.</span></span>  
  
 <span data-ttu-id="aefc9-105">Para implementar uma expressão em uma transformação, o pacote já deve incluir pelo menos uma tarefa Fluxo de Dados e uma fonte.</span><span class="sxs-lookup"><span data-stu-id="aefc9-105">To implement an expression in a transformation, the package must already include at least one Data Flow task and a source.</span></span> <span data-ttu-id="aefc9-106">Para obter informações sobre como adicionar itens a pacotes, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="aefc9-106">For information about adding items to packages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="aefc9-107">Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="aefc9-107">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
    
  
-   [<span data-ttu-id="aefc9-108">Adicionar ou excluir um componente em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="aefc9-108">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
-   [<span data-ttu-id="aefc9-109">Conectar componentes em um fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="aefc9-109">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)  
  
### <a name="to-create-an-expression"></a><span data-ttu-id="aefc9-110">Para criar uma expressão</span><span class="sxs-lookup"><span data-stu-id="aefc9-110">To create an expression</span></span>  
  
1.  <span data-ttu-id="aefc9-111">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="aefc9-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="aefc9-112">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="aefc9-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="aefc9-113">No Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] , clique na guia **Fluxo de Controle** e clique na tarefa Fluxo de Dados que contém o fluxo de dados no qual você deseja implementar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="aefc9-113">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow** tab, and then click the Data Flow task that contains the data flow in which you want to implement an expression.</span></span>  
  
4.  <span data-ttu-id="aefc9-114">Clique na guia **Fluxo de Dados** e arraste uma transformação Divisão Condicional ou Coluna Derivada da **Caixa de Ferramentas** para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="aefc9-114">Click the **Data Flow** tab, and drag either a Conditional Split or Derived Column transformation from the **Toolbox** to the design surface.</span></span>  
  
5.  <span data-ttu-id="aefc9-115">Arraste o conector verde da fonte ou uma transformação para a transformação Divisão Condicional ou Coluna Derivada.</span><span class="sxs-lookup"><span data-stu-id="aefc9-115">Drag the green connector from the source or a transformation to the Conditional Split or Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="aefc9-116">Clique duas vezes na transformação para abrir sua caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aefc9-116">Double-click the transformation to open its dialog box.</span></span>  
  
7.  <span data-ttu-id="aefc9-117">No painel à esquerda, expanda **Variáveis** para exibir variáveis definidas pelo sistema e pelo usuário e expanda **Colunas** para exibir as colunas de entrada de transformação.</span><span class="sxs-lookup"><span data-stu-id="aefc9-117">In the left pane, expand **Variables** to display system and user-defined variables, and expand **Columns** to display the transformation input columns.</span></span>  
  
8.  <span data-ttu-id="aefc9-118">No painel à direita, expanda **Funções Matemáticas**, **Funções de Cadeia de Caracteres**, **Funções de Data/Hora**, **Funções NULL**, **Conversões de Tipo**e **Operadores** para acessar as funções, as conversões e os operadores fornecidos pela gramática de expressão.</span><span class="sxs-lookup"><span data-stu-id="aefc9-118">In the right pane, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators** to access the functions, the casts, and the operators that the expression grammar provides.</span></span>  
  
9. <span data-ttu-id="aefc9-119">Dependendo da transformação, execute uma das seguintes ações para criar uma expressão:</span><span class="sxs-lookup"><span data-stu-id="aefc9-119">Depending on the transformation, do one of the following to build an expression:</span></span>  
  
    -   <span data-ttu-id="aefc9-120">Na caixa de diálogo **Editor de Transformação Divisão Condicional** , arraste variáveis, colunas, funções, operadores e conversões até a coluna **Condição** .</span><span class="sxs-lookup"><span data-stu-id="aefc9-120">In the **Conditional Split Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Condition** column.</span></span> <span data-ttu-id="aefc9-121">Se preferir, digite uma expressão diretamente na coluna **Condição** .</span><span class="sxs-lookup"><span data-stu-id="aefc9-121">Alternatively, you can type an expression directly in the **Condition** column.</span></span>  
  
    -   <span data-ttu-id="aefc9-122">Na caixa de diálogo **Editor de Transformação Coluna Derivada** , arraste variáveis, colunas, funções, operadores e conversões até a coluna **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="aefc9-122">In the **Derived Column Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Expression** column.</span></span> <span data-ttu-id="aefc9-123">Como alternativa, é possível digitar uma expressão diretamente na coluna **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="aefc9-123">Alternatively, you can type an expression directly in the **Expression** column.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="aefc9-124">Ao remover o foco da coluna **Condição** ou da coluna **Expressão** , o texto da expressão pode ser realçado para indicar que a sintaxe da expressão está incorreta.</span><span class="sxs-lookup"><span data-stu-id="aefc9-124">When you remove the focus from the **Condition** column or the **Expression** column, the expression text might be highlighted to indicate that the expression syntax is incorrect.</span></span>  
  
10. <span data-ttu-id="aefc9-125">Clique em **OK** para sair da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aefc9-125">Click **OK** to exit the dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aefc9-126">Se a expressão não for válida, um alerta aparecerá descrevendo os erros de sintaxe na expressão.</span><span class="sxs-lookup"><span data-stu-id="aefc9-126">If the expression is not valid, an alert appears describing the syntax errors in the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aefc9-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aefc9-127">See Also</span></span>  
 <span data-ttu-id="aefc9-128">[Integration Services &#40;expressões&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="aefc9-128">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="aefc9-129">[Transformação Divisão condicional](data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="aefc9-129">[Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="aefc9-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="aefc9-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span></span>  
 <span data-ttu-id="aefc9-131">[Tarefa de Fluxo de Dados](control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="aefc9-131">[Data Flow Task](control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="aefc9-132">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="aefc9-132">Data Flow</span></span>](data-flow/data-flow.md)  
  
  
