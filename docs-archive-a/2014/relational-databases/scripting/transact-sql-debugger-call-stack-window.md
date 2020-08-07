---
title: Janela Pilha de Chamadas
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Call Stack Window [Transact-SQL]
ms.assetid: ddb0b19c-87cd-4883-bcb8-ec09ffb30369
author: rothja
ms.author: jroth
ms.openlocfilehash: b4b72e484ade696be81ebac8ea4eed9be295edf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582401"
---
# <a name="call-stack-window"></a><span data-ttu-id="d869c-102">Janela Pilha de Chamadas</span><span class="sxs-lookup"><span data-stu-id="d869c-102">Call Stack Window</span></span>
  <span data-ttu-id="d869c-103">A janela **Pilha de Chamadas** exibe os módulos da pilha de chamadas e os valores e tipos de dados de quaisquer parâmetros que passaram para os módulos.</span><span class="sxs-lookup"><span data-stu-id="d869c-103">The **Call Stack** window displays the modules on the call stack, and the data types and values of any parameters that are passed to the modules.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="d869c-104">os módulos incluem procedimentos armazenados, funções e gatilhos.</span><span class="sxs-lookup"><span data-stu-id="d869c-104">modules include stored procedures, functions, and triggers.</span></span> <span data-ttu-id="d869c-105">Para exibir a pilha de chamadas, você deve estar no modo de depuração.</span><span class="sxs-lookup"><span data-stu-id="d869c-105">To display the call stack, you must be in debug mode.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="d869c-106">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="d869c-106">Task List</span></span>  
 <span data-ttu-id="d869c-107">**Para acessar a janela Pilha de Chamadas**</span><span class="sxs-lookup"><span data-stu-id="d869c-107">**To access the Call Stack window**</span></span>  
  
-   <span data-ttu-id="d869c-108">No menu **Depurar** , clique em **Janelas**e em **Pilha de Chamadas**.</span><span class="sxs-lookup"><span data-stu-id="d869c-108">On the **Debug** menu, click **Windows**, and then click **Call Stack**.</span></span>  
  
 <span data-ttu-id="d869c-109">**Para alterar o quadro atual da Pilha de Chamadas**</span><span class="sxs-lookup"><span data-stu-id="d869c-109">**To change the current Call Stack frame**</span></span>  
  
 <span data-ttu-id="d869c-110">Você pode usar qualquer um dos seguintes procedimentos para montar o quadro atual do quadro de pilhas:</span><span class="sxs-lookup"><span data-stu-id="d869c-110">You can use either of the following procedures to make a stack frame the current frame:</span></span>  
  
-   <span data-ttu-id="d869c-111">Clique com o botão direito do mouse no registro de ativação e depois clique em **Alternar para Quadro**.</span><span class="sxs-lookup"><span data-stu-id="d869c-111">Right-click the stack frame, and then click **Switch To Frame**.</span></span>  
  
-   <span data-ttu-id="d869c-112">Clique duas vezes no quadro de pilhas.</span><span class="sxs-lookup"><span data-stu-id="d869c-112">Double-click the stack frame.</span></span>  
  
 <span data-ttu-id="d869c-113">**Para exibir a origem de um quadro diferente do quadro atual**</span><span class="sxs-lookup"><span data-stu-id="d869c-113">**To view the source of a frame other than the current frame**</span></span>  
  
-   <span data-ttu-id="d869c-114">Clique com o botão direito do mouse no registro de ativação e depois clique em **Ir para Código-Fonte**.</span><span class="sxs-lookup"><span data-stu-id="d869c-114">Right-click the stack frame, and then click **Go To Source Code**.</span></span>  
  
## <a name="stack-frames"></a><span data-ttu-id="d869c-115">Quadros de pilhas</span><span class="sxs-lookup"><span data-stu-id="d869c-115">Stack Frames</span></span>  
 <span data-ttu-id="d869c-116">Cada linha na janela **Pilha de Chamadas** é chamada de um registro de ativação e representa a chamada de um módulo de um arquivo de script [!INCLUDE[tsql](../../includes/tsql-md.md)] ou uma chamada de um módulo a outro.</span><span class="sxs-lookup"><span data-stu-id="d869c-116">Each row in the **Call Stack** window is called a stack frame and represents either a call from a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file to a module or a call from one module to another.</span></span> <span data-ttu-id="d869c-117">O registro de ativação inferior no vídeo indica a linha da janela do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] que fez a primeira chamada na pilha.</span><span class="sxs-lookup"><span data-stu-id="d869c-117">The bottom stack frame in the display indicates the line in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window that made the first call into the stack.</span></span> <span data-ttu-id="d869c-118">A linha superior indica em qual linha o depurador pausou a depuração e é identificada por uma seta amarela na margem esquerda da janela.</span><span class="sxs-lookup"><span data-stu-id="d869c-118">The top row indicates the line on which the debugger paused execution, and is identified by a yellow arrow in the left margin of the window.</span></span> <span data-ttu-id="d869c-119">Cada linha intermediária indica o módulo e o número de linha do código fonte que chamou o próximo quadro de pilha mais alto.</span><span class="sxs-lookup"><span data-stu-id="d869c-119">Each intermediate row indicates the module and the line number of the source code that called the next higher stack frame.</span></span>  
  
 <span data-ttu-id="d869c-120">Todas as expressões nas janelas **Locais**, **Inspecionar**e **QuickWatch** são avaliadas com base no registro de ativação atual.</span><span class="sxs-lookup"><span data-stu-id="d869c-120">All expressions in the **Locals**, **Watch**, and **QuickWatch** windows are evaluated based on the current stack frame.</span></span> <span data-ttu-id="d869c-121">A janela Editor de Consultas exibe o código para o quadro atual.</span><span class="sxs-lookup"><span data-stu-id="d869c-121">The Query Editor window displays the code for the current frame.</span></span> <span data-ttu-id="d869c-122">Por padrão, o registro de ativação atual é o quadro no qual o depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] pausou a execução.</span><span class="sxs-lookup"><span data-stu-id="d869c-122">By default, the current stack frame is the frame in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger paused execution.</span></span> <span data-ttu-id="d869c-123">Quando você altera o registro de ativação atual para outro quadro, as expressão das janelas **Locais**, **Inspecionar**e **QuickWatch** são reavaliadas no contexto do novo quadro de pilhas e o código-fonte do novo quadro é exibido na janela Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="d869c-123">When you change the current stack frame to another frame, the expressions in the **Locals**, **Watch**, and **QuickWatch** windows are reevaluated in the context of the new frame, and the source code of the new frame is displayed in the Query Editor window.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="d869c-124">Colunas</span><span class="sxs-lookup"><span data-stu-id="d869c-124">Columns</span></span>  
 <span data-ttu-id="d869c-125">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d869c-125">**Name**</span></span>  
 <span data-ttu-id="d869c-126">Exibe informações sobre um módulo na pilha de chamadas.</span><span class="sxs-lookup"><span data-stu-id="d869c-126">Displays information about a module on the call stack.</span></span>  
  
 <span data-ttu-id="d869c-127">Na linha inferior da pilha de chamadas, **Nome** relaciona a janela de fonte do Editor de Consultas e o número de linha que fez a primeira chamada na pilha.</span><span class="sxs-lookup"><span data-stu-id="d869c-127">For the bottom row in the call stack, **Name** lists the Query Editor source window and line number of the first call into the stack.</span></span> <span data-ttu-id="d869c-128">Para as outras linhas, **Nome** apresenta o formato **Module(Instance.Database)(ParmList) LineNumber**.</span><span class="sxs-lookup"><span data-stu-id="d869c-128">For the other rows, **Name** has the format **Module(Instance.Database)(ParmList) LineNumber**.</span></span>  
  
 <span data-ttu-id="d869c-129">**Módulo**</span><span class="sxs-lookup"><span data-stu-id="d869c-129">**Module**</span></span>  
 <span data-ttu-id="d869c-130">É o nome do procedimento armazenado, função ou procedimento armazenado que chamou o próximo quadro.</span><span class="sxs-lookup"><span data-stu-id="d869c-130">Is the name of the stored procedure, function, or stored procedure that called to the next frame.</span></span>  
  
 <span data-ttu-id="d869c-131">**Instance.Database**</span><span class="sxs-lookup"><span data-stu-id="d869c-131">**Instance.Database**</span></span>  
 <span data-ttu-id="d869c-132">É a instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e do banco de dados que está segurando o módulo.</span><span class="sxs-lookup"><span data-stu-id="d869c-132">Is the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the database that is holding the module.</span></span>  
  
 <span data-ttu-id="d869c-133">**ParmList**</span><span class="sxs-lookup"><span data-stu-id="d869c-133">**ParmList**</span></span>  
 <span data-ttu-id="d869c-134">Indica o tipo de dados, o nome e o valor de cada parâmetro transmitido dentro durante a chamada para o módulo.</span><span class="sxs-lookup"><span data-stu-id="d869c-134">Indicates the data type, name, and value for each parameter that is passed in during the call to the module.</span></span>  
  
 <span data-ttu-id="d869c-135">**LineNumber**</span><span class="sxs-lookup"><span data-stu-id="d869c-135">**LineNumber**</span></span>  
 <span data-ttu-id="d869c-136">Para todas as linhas excluindo a linha de parte superior, **LineNumber** indica qual linha no módulo chamou o quadro.</span><span class="sxs-lookup"><span data-stu-id="d869c-136">For all rows except the top row, **LineNumber** indicates which line in the module called to the frame.</span></span> <span data-ttu-id="d869c-137">Para a linha de parte superior, **LineNumber** indica a linha na qual o depurador está atualmente focalizado.</span><span class="sxs-lookup"><span data-stu-id="d869c-137">For the top row, **LineNumber** indicates the line on which the debugger is currently focused.</span></span>  
  
 <span data-ttu-id="d869c-138">**Idioma**</span><span class="sxs-lookup"><span data-stu-id="d869c-138">**Language**</span></span>  
 <span data-ttu-id="d869c-139">Exibe **Transact-SQL** para [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d869c-139">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d869c-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d869c-140">See Also</span></span>  
 <span data-ttu-id="d869c-141">[Depurador do Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="d869c-141">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="d869c-142">[Informações do depurador Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="d869c-142">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 [<span data-ttu-id="d869c-143">Percorrer o código do Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d869c-143">Step Through Transact-SQL Code</span></span>](step-through-transact-sql-code.md)  
