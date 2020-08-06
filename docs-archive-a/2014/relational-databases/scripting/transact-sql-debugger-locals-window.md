---
title: Janela Locais
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Locals Window [Transact-SQL]
ms.assetid: 59bea640-7823-4b4d-832c-f384d83cca2f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f8f62eb69a50d7543af41dddb9c62c842d17151
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582949"
---
# <a name="locals-window"></a><span data-ttu-id="511ff-102">Janela Locais</span><span class="sxs-lookup"><span data-stu-id="511ff-102">Locals Window</span></span>
  <span data-ttu-id="511ff-103">A janela **Locais** exibe informações sobre as expressões locais no escopo atual do depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="511ff-103">The **Locals** window displays information about the local expressions in the current scope of the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="511ff-104">O escopo é definido como o quadro atual da pilha de chamadas selecionada na janela **Pilha de Chamadas** .</span><span class="sxs-lookup"><span data-stu-id="511ff-104">The scope is set to the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="511ff-105">Você deve estar no modo de depuração para exibir as expressões locais.</span><span class="sxs-lookup"><span data-stu-id="511ff-105">You must be in debug mode to display the local expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="511ff-106">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="511ff-106">Task List</span></span>  
 <span data-ttu-id="511ff-107">**Para acessar a janela Locais**</span><span class="sxs-lookup"><span data-stu-id="511ff-107">**To access the Locals window**</span></span>  
  
-   <span data-ttu-id="511ff-108">No menu **Depurar** , clique em **Janelas**e em **Locais**.</span><span class="sxs-lookup"><span data-stu-id="511ff-108">On the **Debug** menu, click **Windows**, and then click **Locals**.</span></span>  
  
 <span data-ttu-id="511ff-109">**Para alterar o valor de uma expressão**</span><span class="sxs-lookup"><span data-stu-id="511ff-109">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="511ff-110">Clique com o botão direito do mouse na expressão e selecione **Editar Valor**.</span><span class="sxs-lookup"><span data-stu-id="511ff-110">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="511ff-111">Colunas</span><span class="sxs-lookup"><span data-stu-id="511ff-111">Columns</span></span>  
 <span data-ttu-id="511ff-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="511ff-112">**Name**</span></span>  
 <span data-ttu-id="511ff-113">É o nome da expressão local.</span><span class="sxs-lookup"><span data-stu-id="511ff-113">Is the name of the local expression.</span></span> <span data-ttu-id="511ff-114">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] lista variáveis, parâmetros e funções de sistema com nomes que iniciam com @@.</span><span class="sxs-lookup"><span data-stu-id="511ff-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger lists variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="511ff-115">**Valor**</span><span class="sxs-lookup"><span data-stu-id="511ff-115">**Value**</span></span>  
 <span data-ttu-id="511ff-116">Exibe o valor atribuído atualmente à expressão local.</span><span class="sxs-lookup"><span data-stu-id="511ff-116">Displays the value that is currently assigned to the local expression.</span></span> <span data-ttu-id="511ff-117">Esta coluna fica em branco quando nenhum valor é atribuído à expressão.</span><span class="sxs-lookup"><span data-stu-id="511ff-117">This column is blank when no value has been assigned to the expression.</span></span>  
  
 <span data-ttu-id="511ff-118">Se o comprimento de uma expressão for maior do que a largura da coluna **Valor** , uma dica de ferramenta exibe o valor total quando o ponteiro passa sobre a célula **Valor** daquela expressão.</span><span class="sxs-lookup"><span data-stu-id="511ff-118">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="511ff-119">Um ícone de lupa em uma célula **Valor** indica que o visualizador de depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] está disponível.</span><span class="sxs-lookup"><span data-stu-id="511ff-119">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="511ff-120">Na lista, você pode especificar **Visualizador de Texto**, **Visualizador de XML**ou **Visualizador de HTML**.</span><span class="sxs-lookup"><span data-stu-id="511ff-120">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="511ff-121">Para iniciar um visualizador de depurador, clique no ícone de lupa.</span><span class="sxs-lookup"><span data-stu-id="511ff-121">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="511ff-122">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] abre uma caixa de diálogo que exibe os dados em um formato apropriado para o tipo dos dados.</span><span class="sxs-lookup"><span data-stu-id="511ff-122">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="511ff-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="511ff-123">**Type**</span></span>  
 <span data-ttu-id="511ff-124">Exibe o tipo de dados da expressão.</span><span class="sxs-lookup"><span data-stu-id="511ff-124">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="511ff-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="511ff-125">See Also</span></span>  
 <span data-ttu-id="511ff-126">[Depurador do Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="511ff-126">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="511ff-127">[Informações do depurador Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="511ff-127">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="511ff-128">[Janela de Observação](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="511ff-128">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="511ff-129">[Janela Pilha de Chamadas](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="511ff-129">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="511ff-130">[Caixa de diálogo QuickWatch](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="511ff-130">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="511ff-131">Expressões &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="511ff-131">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
