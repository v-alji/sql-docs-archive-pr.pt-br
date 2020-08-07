---
title: Percorrer código Transact-SQL
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, debugging code
- Transact-SQL debugger, step over
- Transact-SQL debugger, step out
- Transact-SQL debugger, step into
ms.assetid: e09079b8-c4c9-42b4-821b-4ce81a98a086
author: rothja
ms.author: jroth
ms.openlocfilehash: 48cb307130c65729640864a26bdf1dfaf344b32b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581749"
---
# <a name="step-through-transact-sql-code"></a><span data-ttu-id="dc9ba-102">Percorrer código Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dc9ba-102">Step Through Transact-SQL Code</span></span>
  <span data-ttu-id="dc9ba-103">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] permite que você controle quais instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] são executadas em uma janela Editor de Consultas [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc9ba-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger enables you to control which [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are run in a [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span> <span data-ttu-id="dc9ba-104">Você pode pausar o depurador em instruções individuais e exibir o estado dos elementos de código nesse ponto.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-104">You can pause the debugger on individual statements and then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="dc9ba-105">Pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="dc9ba-105">Breakpoints</span></span>  
 <span data-ttu-id="dc9ba-106">Um ponto de interrupção sinaliza o depurador para pausar a execução em uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] específica.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-106">A breakpoint signals the debugger to pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="dc9ba-107">Para mais informações sobre pontos de interrupção, consulte Usando pontos de interrupção de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-107">For more information about breakpoints, see Using Transact-SQL Breakpoints.</span></span>  
  
## <a name="controlling-statement-execution"></a><span data-ttu-id="dc9ba-108">Controlando a execução de uma instrução</span><span class="sxs-lookup"><span data-stu-id="dc9ba-108">Controlling Statement Execution</span></span>  
 <span data-ttu-id="dc9ba-109">No depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] , você pode especificar as seguintes opções para executar a partir da instrução atual em código [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="dc9ba-109">In the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can specify the following options for executing from the current statement in [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
-   <span data-ttu-id="dc9ba-110">Executar até o próximo ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-110">Run to the next breakpoint.</span></span>  
  
-   <span data-ttu-id="dc9ba-111">Avançar para a próxima instrução.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-111">Step into the next statement.</span></span>  
  
     <span data-ttu-id="dc9ba-112">Se a próxima instrução chamar um procedimento armazenado, uma função ou um gatilho do [!INCLUDE[tsql](../../includes/tsql-md.md)] , o depurador exibirá uma nova janela do Editor de Consultas que contém o código do módulo.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-112">If the next statement invokes a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, function, or trigger, the debugger displays a new Query Editor window that contains the code of the module.</span></span> <span data-ttu-id="dc9ba-113">A janela está no modo de depuração e a execução pausa na primeira instrução do módulo.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-113">The window is in debug mode, and execution pauses on the first statement in the module.</span></span> <span data-ttu-id="dc9ba-114">Você pode mover-se pelo código do módulo, por exemplo, definindo pontos de interrupção ou percorrendo o código.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-114">You can then move through the module code, for example, by setting breakpoints or stepping through the code.</span></span>  
  
-   <span data-ttu-id="dc9ba-115">Passe pela próxima instrução.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-115">Step over the next statement.</span></span>  
  
     <span data-ttu-id="dc9ba-116">A próxima instrução é executada.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-116">The next statement is executed.</span></span> <span data-ttu-id="dc9ba-117">No entanto, se a próxima instrução chamar um procedimento armazenado, uma função ou um gatilho, o código do módulo será executado até o fim, e os resultados serão retornados ao código de chamada.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-117">However, if the statement invokes a stored procedure, function, or trigger, the module code runs until it finishes, and the results are returned to the calling code.</span></span> <span data-ttu-id="dc9ba-118">Se você tiver certeza de que não há erros em um procedimento armazenado, poderá passar por ele.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-118">If you are sure there are no errors in a stored procedure, you can step over it.</span></span> <span data-ttu-id="dc9ba-119">A execução pausa na instrução que segue a chamada do procedimento armazenado, da função ou do gatilho.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-119">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="dc9ba-120">Sair de um procedimento armazenado, uma função ou um gatilho.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-120">Step out of a stored procedure, function, or trigger.</span></span>  
  
     <span data-ttu-id="dc9ba-121">A execução pausa na instrução que segue a chamada do procedimento armazenado, da função ou do gatilho.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-121">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="dc9ba-122">Execute do local atual ao local atual do ponteiro e ignore todos os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-122">Run from the current location to the current location of the pointer, and ignore all breakpoints.</span></span>  
  
 <span data-ttu-id="dc9ba-123">A tabela a seguir lista os vários modos nos quais você pode controlar como as instruções são executadas  no depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc9ba-123">The following table lists the various ways in which you can control how statements execute in the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span>  
  
|<span data-ttu-id="dc9ba-124">Ação</span><span class="sxs-lookup"><span data-stu-id="dc9ba-124">Action</span></span>|<span data-ttu-id="dc9ba-125">Procedimento</span><span class="sxs-lookup"><span data-stu-id="dc9ba-125">Procedure</span></span>|  
|------------|---------------|  
|<span data-ttu-id="dc9ba-126">Executar todas as instruções da instrução atual para o próximo ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="dc9ba-126">Run all statements from the current statement to the next breakpoint</span></span>|<span data-ttu-id="dc9ba-127">No menu **Depurar**, clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-127">On the **Debug** menu, click **Continue**.</span></span><br /><br /> <span data-ttu-id="dc9ba-128">Na barra de ferramentas **depurar** , clique no botão **continuar** .</span><span class="sxs-lookup"><span data-stu-id="dc9ba-128">On the **Debug** toolbar, click the **Continue** button.</span></span>|  
|<span data-ttu-id="dc9ba-129">Avançar para a próxima instrução ou módulo</span><span class="sxs-lookup"><span data-stu-id="dc9ba-129">Step into the next statement or module</span></span>|<span data-ttu-id="dc9ba-130">No menu **depurar** , clique em **depuração em**.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-130">On the **Debug** menu, click **Step Into**.</span></span><br /><br /> <span data-ttu-id="dc9ba-131">Na barra de ferramentas **depurar** , clique no botão **entrar em** .</span><span class="sxs-lookup"><span data-stu-id="dc9ba-131">On the **Debug** toolbar, click the **Step Into** button.</span></span><br /><br /> <span data-ttu-id="dc9ba-132">Pressione F11.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-132">Press F11.</span></span>|  
|<span data-ttu-id="dc9ba-133">Passar pela próxima instrução ou módulo</span><span class="sxs-lookup"><span data-stu-id="dc9ba-133">Step over the next statement or module</span></span>|<span data-ttu-id="dc9ba-134">No menu **Depurar**, clique em **Percorrer**.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-134">On the **Debug** menu, click **Step Over**.</span></span><br /><br /> <span data-ttu-id="dc9ba-135">Na barra de ferramentas **depurar** , clique no botão **passar sobre** .</span><span class="sxs-lookup"><span data-stu-id="dc9ba-135">On the **Debug** toolbar, click the **Step Over** button.</span></span><br /><br /> <span data-ttu-id="dc9ba-136">Pressione F10.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-136">Press F10.</span></span>|  
|<span data-ttu-id="dc9ba-137">Sair de um módulo</span><span class="sxs-lookup"><span data-stu-id="dc9ba-137">Step out of a module</span></span>|<span data-ttu-id="dc9ba-138">No menu **depurar** , clique em **sair**.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-138">On the **Debug** menu, click **Step Out**.</span></span><br /><br /> <span data-ttu-id="dc9ba-139">Na barra de ferramentas **depurar** , clique no botão **sair** .</span><span class="sxs-lookup"><span data-stu-id="dc9ba-139">On the **Debug** toolbar, click the **Step Out** button.</span></span><br /><br /> <span data-ttu-id="dc9ba-140">Pressione SHIFT+F11.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-140">Press SHIFT+F11.</span></span>|  
|<span data-ttu-id="dc9ba-141">Executar para o local do cursor atual</span><span class="sxs-lookup"><span data-stu-id="dc9ba-141">Run to the current cursor location</span></span>|<span data-ttu-id="dc9ba-142">Clique com o botão direito do mouse na janela Editor de Consultas e então clique em **Executar até o Cursor**.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-142">Right-click in the Query Editor window, and then click **Run To Cursor**.</span></span><br /><br /> <span data-ttu-id="dc9ba-143">Pressione CTRL+F10.</span><span class="sxs-lookup"><span data-stu-id="dc9ba-143">Press CTRL+F10.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc9ba-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dc9ba-144">See Also</span></span>  
 [<span data-ttu-id="dc9ba-145">Informações do depurador Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dc9ba-145">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
