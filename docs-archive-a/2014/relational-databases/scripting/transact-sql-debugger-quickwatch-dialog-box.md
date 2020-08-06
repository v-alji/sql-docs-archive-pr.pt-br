---
title: Caixa de diálogo QuickWatch
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.quickwatch
helpviewer_keywords:
- QuickWatch Dialog [Transact-SQL]
ms.assetid: d6bbb373-1452-41f2-bdc5-86ae689c3dc0
author: rothja
ms.author: jroth
ms.openlocfilehash: 48e4bda558b75bec0c81815c90feff9d6500a803
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582947"
---
# <a name="quickwatch-dialog-box"></a><span data-ttu-id="c0ead-102">Caixa de diálogo QuickWatch</span><span class="sxs-lookup"><span data-stu-id="c0ead-102">QuickWatch Dialog Box</span></span>
  <span data-ttu-id="c0ead-103">Use a caixa de diálogo **QuickWatch** para exibir rapidamente o tipo e o valor de dados de uma expressão [!INCLUDE[tsql](../../includes/tsql-md.md)] , como uma variável ou parâmetro, quando você estiver depurando um código [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0ead-103">Use the **QuickWatch** dialog box to quickly view the data type and value of one [!INCLUDE[tsql](../../includes/tsql-md.md)] expression, such as a variable or parameter, when you are debugging [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="c0ead-104">Ao observar várias expressões, você também pode acrescentar a expressão à janela **Inspecionar** .</span><span class="sxs-lookup"><span data-stu-id="c0ead-104">To watch multiple expressions, you can also add the expression to a **Watch** window.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="c0ead-105">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="c0ead-105">Task List</span></span>  
 <span data-ttu-id="c0ead-106">**Para acessar a caixa de diálogo QuickWatch**</span><span class="sxs-lookup"><span data-stu-id="c0ead-106">**To access the QuickWatch dialog box**</span></span>  
  
-   <span data-ttu-id="c0ead-107">No menu **Depurar** , clique em **QuickWatch**.</span><span class="sxs-lookup"><span data-stu-id="c0ead-107">On the **Debug** menu, click **QuickWatch**.</span></span>  
  
 <span data-ttu-id="c0ead-108">**Para exibir a informações sobre uma expressão**</span><span class="sxs-lookup"><span data-stu-id="c0ead-108">**To view the information about an expression**</span></span>  
  
1.  <span data-ttu-id="c0ead-109">Na caixa de listagem **Expressão** , digite ou selecione a expressão desejada.</span><span class="sxs-lookup"><span data-stu-id="c0ead-109">In the **Expression** list box, type or select the expression that you want.</span></span> <span data-ttu-id="c0ead-110">Há suporte às seguintes expressões [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c0ead-110">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] expressions are supported:</span></span>  
  
    -   <span data-ttu-id="c0ead-111">Variáveis.</span><span class="sxs-lookup"><span data-stu-id="c0ead-111">Variables.</span></span>  
  
    -   <span data-ttu-id="c0ead-112">Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="c0ead-112">Parameters.</span></span>  
  
    -   <span data-ttu-id="c0ead-113">Funções do sistema cujo nome começa com @@.</span><span class="sxs-lookup"><span data-stu-id="c0ead-113">System functions whose name starts with @@.</span></span>  
  
    -   <span data-ttu-id="c0ead-114">Expressões criadas pela aplicação de operadores a uma ou mais variáveis, parâmetros ou funções do sistema, como @IntegerCounter + 1 ou FirstName + LastName.</span><span class="sxs-lookup"><span data-stu-id="c0ead-114">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
    -   <span data-ttu-id="c0ead-115">Instruções Transact-SQL que retornam um único valor, como: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span><span class="sxs-lookup"><span data-stu-id="c0ead-115">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
2.  <span data-ttu-id="c0ead-116">Clique em **Reavaliar**.</span><span class="sxs-lookup"><span data-stu-id="c0ead-116">Click **Reevaluate**.</span></span>  
  
 <span data-ttu-id="c0ead-117">**Para acrescentar a expressão QuickWatch a uma janela Inspecionar**</span><span class="sxs-lookup"><span data-stu-id="c0ead-117">**To add the QuickWatch expression to a Watch window**</span></span>  
  
-   <span data-ttu-id="c0ead-118">Clique em **Adicionar Inspeção**.</span><span class="sxs-lookup"><span data-stu-id="c0ead-118">Click **Add Watch**.</span></span>  
  
 <span data-ttu-id="c0ead-119">**Para alterar o valor da expressão QuickWatch**</span><span class="sxs-lookup"><span data-stu-id="c0ead-119">**To change the value of the QuickWatch expression**</span></span>  
  
-   <span data-ttu-id="c0ead-120">Clique com o botão direito do mouse na expressão e selecione **Editar Valor**.</span><span class="sxs-lookup"><span data-stu-id="c0ead-120">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0ead-121">Opções</span><span class="sxs-lookup"><span data-stu-id="c0ead-121">Options</span></span>  
 <span data-ttu-id="c0ead-122">**Lista de expressões**</span><span class="sxs-lookup"><span data-stu-id="c0ead-122">**Expression list**</span></span>  
 <span data-ttu-id="c0ead-123">Exibe a expressão atualmente selecionada.</span><span class="sxs-lookup"><span data-stu-id="c0ead-123">Displays the currently selected expression.</span></span> <span data-ttu-id="c0ead-124">A lista suspensa contém um conjunto de expressões que você pode selecionar para exibir.</span><span class="sxs-lookup"><span data-stu-id="c0ead-124">The drop-down list contains a set of expressions that you can select to display.</span></span> <span data-ttu-id="c0ead-125">As expressões da lista são as disponíveis no escopo do quadro de pilhas selecionado atualmente na janela **Pilha de Chamadas** .</span><span class="sxs-lookup"><span data-stu-id="c0ead-125">The expressions in the list are those available in the scope of the stack frame that is currently selected in the **Call Stack** window.</span></span> <span data-ttu-id="c0ead-126">Para exibir uma expressão diferente, digite a expressão ou selecione-a na lista.</span><span class="sxs-lookup"><span data-stu-id="c0ead-126">To display a different expression, either enter the expression or select it from list.</span></span> <span data-ttu-id="c0ead-127">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] dá suporte às seguintes expressões: variáveis, parâmetros e funções de sistema com nomes que iniciam com @@.</span><span class="sxs-lookup"><span data-stu-id="c0ead-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports the following expressions: variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="c0ead-128">**Grade de valor**</span><span class="sxs-lookup"><span data-stu-id="c0ead-128">**Value grid**</span></span>  
 <span data-ttu-id="c0ead-129">Exibe as propriedades da expressão atualmente em inspeção.</span><span class="sxs-lookup"><span data-stu-id="c0ead-129">Displays the properties of the expression that is currently being watched.</span></span>  
  
 <span data-ttu-id="c0ead-130">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c0ead-130">**Name**</span></span>  
 <span data-ttu-id="c0ead-131">É a expressão [!INCLUDE[tsql](../../includes/tsql-md.md)] que é inspecionada.</span><span class="sxs-lookup"><span data-stu-id="c0ead-131">Is the [!INCLUDE[tsql](../../includes/tsql-md.md)] expression being watched.</span></span>  
  
 <span data-ttu-id="c0ead-132">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c0ead-132">**Value**</span></span>  
 <span data-ttu-id="c0ead-133">Exibe o valor atribuído atualmente à expressão.</span><span class="sxs-lookup"><span data-stu-id="c0ead-133">Displays the value that is currently assigned to the expression.</span></span> <span data-ttu-id="c0ead-134">Um espaço em branco é exibido se atualmente a expressão não tiver nenhum valor.</span><span class="sxs-lookup"><span data-stu-id="c0ead-134">A blank is displayed when the expression currently has no value.</span></span>  
  
 <span data-ttu-id="c0ead-135">Se o comprimento de uma expressão for maior do que a largura da coluna **Valor** , uma dica de ferramenta exibe o valor total quando o ponteiro passa sobre a célula **Valor** daquela expressão.</span><span class="sxs-lookup"><span data-stu-id="c0ead-135">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="c0ead-136">Um ícone de lupa em uma célula **Valor** indica que o visualizador de depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] está disponível.</span><span class="sxs-lookup"><span data-stu-id="c0ead-136">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="c0ead-137">Na lista, você pode especificar **Visualizador de Texto**, **Visualizador de XML**ou **Visualizador de HTML**.</span><span class="sxs-lookup"><span data-stu-id="c0ead-137">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="c0ead-138">Para iniciar um visualizador de depurador, clique no ícone de lupa.</span><span class="sxs-lookup"><span data-stu-id="c0ead-138">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="c0ead-139">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] abre uma caixa de diálogo que exibe os dados em um formato apropriado para o tipo dos dados.</span><span class="sxs-lookup"><span data-stu-id="c0ead-139">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="c0ead-140">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c0ead-140">**Type**</span></span>  
 <span data-ttu-id="c0ead-141">Exibe o tipo de dados da expressão.</span><span class="sxs-lookup"><span data-stu-id="c0ead-141">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ead-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0ead-142">See Also</span></span>  
 <span data-ttu-id="c0ead-143">[Depurador do Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="c0ead-143">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="c0ead-144">[Informações do depurador Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="c0ead-144">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="c0ead-145">[Janela de Observação](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="c0ead-145">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="c0ead-146">[Janela Locais](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="c0ead-146">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="c0ead-147">[Janela Pilha de Chamadas](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="c0ead-147">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 [<span data-ttu-id="c0ead-148">Expressões &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c0ead-148">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
  
  
