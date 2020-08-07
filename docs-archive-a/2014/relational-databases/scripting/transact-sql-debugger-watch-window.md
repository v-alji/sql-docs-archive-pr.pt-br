---
title: Janela de Observação
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Watch Window [Transact-SQL]
ms.assetid: 23f3baa4-14c2-4262-92f7-3f43fcfa0436
author: rothja
ms.author: jroth
ms.openlocfilehash: c2a3db9b095902fcb5620af91fb86d80f773d606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576264"
---
# <a name="watch-window"></a><span data-ttu-id="3ff08-102">Janela de Observação</span><span class="sxs-lookup"><span data-stu-id="3ff08-102">Watch Window</span></span>
  <span data-ttu-id="3ff08-103">A janela **Inspecionar** exibe informações sobre as expressões que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="3ff08-103">The **Watch** window displays information about the expressions that you have selected.</span></span> <span data-ttu-id="3ff08-104">Pode haver até quatro janelas Inspecionar: **Inspecionar 1**, **Inspecionar 2, Inspecionar 3**e **Inspecionar 4**.</span><span class="sxs-lookup"><span data-stu-id="3ff08-104">There can be up to four watch windows: **Watch 1**, **Watch 2, Watch 3**, and **Watch 4**.</span></span> <span data-ttu-id="3ff08-105">As expressões são avaliadas dentro do escopo do quadro de pilha de chamadas atual selecionada na janela **Pilha de Chamadas** .</span><span class="sxs-lookup"><span data-stu-id="3ff08-105">The expressions are evaluated within the scope of the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="3ff08-106">Você deve estar no modo de depuração para inspecionar variáveis e expressões.</span><span class="sxs-lookup"><span data-stu-id="3ff08-106">You must be in debug mode to watch variables and expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="3ff08-107">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="3ff08-107">Task List</span></span>  
 <span data-ttu-id="3ff08-108">**Para acessar as janelas Inspecionar**</span><span class="sxs-lookup"><span data-stu-id="3ff08-108">**To access the Watch windows**</span></span>  
  
-   <span data-ttu-id="3ff08-109">No menu **Depurar** , clique em **Janelas**, clique em **Inspecionar**e depois em **Inspecionar 1**, **Inspecionar 2, Inspecionar 3**ou **Inspecionar 4**.</span><span class="sxs-lookup"><span data-stu-id="3ff08-109">On the **Debug** menu, click **Windows**, click **Watch**, and then click **Watch 1**, **Watch 2, Watch 3**, or **Watch 4**.</span></span>  
  
 <span data-ttu-id="3ff08-110">**Para alterar o valor de uma expressão**</span><span class="sxs-lookup"><span data-stu-id="3ff08-110">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="3ff08-111">Clique com o botão direito do mouse na expressão e selecione **Editar Valor**.</span><span class="sxs-lookup"><span data-stu-id="3ff08-111">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="3ff08-112">Colunas</span><span class="sxs-lookup"><span data-stu-id="3ff08-112">Columns</span></span>  
 <span data-ttu-id="3ff08-113">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3ff08-113">**Name**</span></span>  
 <span data-ttu-id="3ff08-114">São as expressões listadas pelo depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ff08-114">Are the expressions that are listed by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="3ff08-115">Há suporte para as seguintes expressões:</span><span class="sxs-lookup"><span data-stu-id="3ff08-115">The following expressions are supported:</span></span>  
  
-   <span data-ttu-id="3ff08-116">Variáveis.</span><span class="sxs-lookup"><span data-stu-id="3ff08-116">Variables.</span></span>  
  
-   <span data-ttu-id="3ff08-117">Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="3ff08-117">Parameters.</span></span>  
  
-   <span data-ttu-id="3ff08-118">Funções do sistema cujo nome começa com @@.</span><span class="sxs-lookup"><span data-stu-id="3ff08-118">System functions whose name starts with @@.</span></span>  
  
-   <span data-ttu-id="3ff08-119">Expressões criadas pela aplicação de operadores a uma ou mais variáveis, parâmetros ou funções do sistema, como @IntegerCounter + 1 ou FirstName + LastName.</span><span class="sxs-lookup"><span data-stu-id="3ff08-119">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
-   <span data-ttu-id="3ff08-120">Instruções Transact-SQL que retornam um único valor, como: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span><span class="sxs-lookup"><span data-stu-id="3ff08-120">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
 <span data-ttu-id="3ff08-121">**Valor**</span><span class="sxs-lookup"><span data-stu-id="3ff08-121">**Value**</span></span>  
 <span data-ttu-id="3ff08-122">Exibe o valor retornado depois que o depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] avalia a expressão especificada em **Nome**.</span><span class="sxs-lookup"><span data-stu-id="3ff08-122">Displays the value that is returned after the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger evaluates the expression specified in **Name**.</span></span>  
  
 <span data-ttu-id="3ff08-123">Se o comprimento de uma expressão for maior do que a largura da coluna **Valor** , uma dica de ferramenta exibe o valor total quando o ponteiro passa sobre a célula **Valor** daquela expressão.</span><span class="sxs-lookup"><span data-stu-id="3ff08-123">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="3ff08-124">Um ícone de lupa em uma célula **Valor** indica que o visualizador de depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] está disponível.</span><span class="sxs-lookup"><span data-stu-id="3ff08-124">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="3ff08-125">Na lista, você pode especificar **Visualizador de Texto**, **Visualizador de XML**ou **Visualizador de HTML**.</span><span class="sxs-lookup"><span data-stu-id="3ff08-125">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="3ff08-126">Para iniciar um visualizador de depurador, clique no ícone de lupa.</span><span class="sxs-lookup"><span data-stu-id="3ff08-126">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="3ff08-127">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] abre uma caixa de diálogo que exibe os dados em um formato apropriado para o tipo dos dados.</span><span class="sxs-lookup"><span data-stu-id="3ff08-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="3ff08-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3ff08-128">**Type**</span></span>  
 <span data-ttu-id="3ff08-129">Exibe o tipo de dados da expressão.</span><span class="sxs-lookup"><span data-stu-id="3ff08-129">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff08-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ff08-130">See Also</span></span>  
 <span data-ttu-id="3ff08-131">[Depurador do Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="3ff08-131">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="3ff08-132">[Informações do depurador Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="3ff08-132">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="3ff08-133">[Janela Locais](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="3ff08-133">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="3ff08-134">[Janela Pilha de Chamadas](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="3ff08-134">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="3ff08-135">[Caixa de diálogo QuickWatch](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="3ff08-135">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="3ff08-136">Expressões &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3ff08-136">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
