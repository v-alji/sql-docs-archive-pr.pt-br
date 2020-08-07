---
title: Janela Pontos de Interrupção
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Breakpoints Window [Transact-SQL]
ms.assetid: bad88d10-fdd5-4d3d-b5ea-a4f063847485
author: rothja
ms.author: jroth
ms.openlocfilehash: 077d501e581ed5baaac45cc6bbbb34e0040730e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581740"
---
# <a name="breakpoints-window"></a><span data-ttu-id="eec70-102">Janela Pontos de Interrupção</span><span class="sxs-lookup"><span data-stu-id="eec70-102">Breakpoints Window</span></span>
  <span data-ttu-id="eec70-103">A janela **Pontos de Interrupção** lista todos os pontos de interrupção definidos no atual Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eec70-103">The **Breakpoints** window lists all the breakpoints that are set in the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="eec70-104">Para gerenciar os pontos de interrupção, use a barra de ferramentas da janela **Pontos de Interrupção** .</span><span class="sxs-lookup"><span data-stu-id="eec70-104">To manage the breakpoints, use the toolbar in the **Breakpoints** window.</span></span> <span data-ttu-id="eec70-105">Pontos de interrupção são locais no código onde a execução pausa no modo de depuração de forma que é possível exibir os dados de depuração.</span><span class="sxs-lookup"><span data-stu-id="eec70-105">Breakpoints are locations in the code where execution pauses in debug mode so that you can view debugging data.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="eec70-106">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="eec70-106">Task List</span></span>  
 <span data-ttu-id="eec70-107">**Para acessar a janela Pontos de Interrupção**</span><span class="sxs-lookup"><span data-stu-id="eec70-107">**To access the Breakpoints window**</span></span>  
  
-   <span data-ttu-id="eec70-108">No menu **Depurar** , clique em **Janelas**e em **Pontos de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="eec70-108">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
## <a name="breakpoints-window-columns"></a><span data-ttu-id="eec70-109">Colunas da Janela Pontos de Interrupção</span><span class="sxs-lookup"><span data-stu-id="eec70-109">Breakpoints Window Columns</span></span>  
 <span data-ttu-id="eec70-110">Por padrão, a janela **Pontos de interrupção** lista as colunas a seguir.</span><span class="sxs-lookup"><span data-stu-id="eec70-110">By default, the **Breakpoints** window lists the following columns.</span></span>  
  
 <span data-ttu-id="eec70-111">**Nome**</span><span class="sxs-lookup"><span data-stu-id="eec70-111">**Name**</span></span>  
 <span data-ttu-id="eec70-112">Exibe o nome do ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="eec70-112">Displays the name of the breakpoint.</span></span> <span data-ttu-id="eec70-113">Os nomes dos pontos de interrupção são fornecidos pelo depurador.</span><span class="sxs-lookup"><span data-stu-id="eec70-113">Breakpoint names are provided by the debugger.</span></span> <span data-ttu-id="eec70-114">Esse nome inclui o nome da janela do Editor de Consultas do Mecanismo do Banco de Dados que contém o ponto de interrupção e o número da linha do Editor de Consultas onde o ponto de interrupção foi configurado.</span><span class="sxs-lookup"><span data-stu-id="eec70-114">This name includes the name of Database Engine Query Editor window that contains the breakpoint, and the line number in the Query Editor on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="eec70-115">**Condição**</span><span class="sxs-lookup"><span data-stu-id="eec70-115">**Condition**</span></span>  
 <span data-ttu-id="eec70-116">Exibe **(nenhuma condição)** .</span><span class="sxs-lookup"><span data-stu-id="eec70-116">Displays **(no condition)**.</span></span> <span data-ttu-id="eec70-117">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] não dá suporte a condições de ponto de interrupção de configuração.</span><span class="sxs-lookup"><span data-stu-id="eec70-117">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint conditions.</span></span>  
  
 <span data-ttu-id="eec70-118">**Contagem de Ocorrências**</span><span class="sxs-lookup"><span data-stu-id="eec70-118">**Hit Count**</span></span>  
 <span data-ttu-id="eec70-119">Exibe**sempre é interrompido**.</span><span class="sxs-lookup"><span data-stu-id="eec70-119">Displays**breaks always**.</span></span>  
  
 <span data-ttu-id="eec70-120">Você pode adicionar e remover as seguintes colunas selecionando-as na lista **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="eec70-120">You can add and remove the following columns by selecting them on the **Columns** list.</span></span>  
  
 <span data-ttu-id="eec70-121">**Filter**</span><span class="sxs-lookup"><span data-stu-id="eec70-121">**Filter**</span></span>  
 <span data-ttu-id="eec70-122">Exibe **(nenhum)** .</span><span class="sxs-lookup"><span data-stu-id="eec70-122">Displays **(none)**.</span></span> <span data-ttu-id="eec70-123">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] não dá suporte a filtros de ponto de interrupção de configuração.</span><span class="sxs-lookup"><span data-stu-id="eec70-123">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint filters.</span></span>  
  
 <span data-ttu-id="eec70-124">**Quando Visitado**</span><span class="sxs-lookup"><span data-stu-id="eec70-124">**When Hit**</span></span>  
 <span data-ttu-id="eec70-125">Exibe **Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="eec70-125">Displays **Break**.</span></span>  
  
 <span data-ttu-id="eec70-126">**Idioma**</span><span class="sxs-lookup"><span data-stu-id="eec70-126">**Language**</span></span>  
 <span data-ttu-id="eec70-127">Exibe **Transact-SQL** para [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eec70-127">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="eec70-128">**Função**</span><span class="sxs-lookup"><span data-stu-id="eec70-128">**Function**</span></span>  
 <span data-ttu-id="eec70-129">Exibe o número da linha onde o ponto de interrupção está definido.</span><span class="sxs-lookup"><span data-stu-id="eec70-129">Displays the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="eec70-130">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="eec70-130">**File**</span></span>  
 <span data-ttu-id="eec70-131">Exibe o nome do arquivo de origem que contém o ponto de interrupção e o número da linha na qual o ponto de interrupção está definido.</span><span class="sxs-lookup"><span data-stu-id="eec70-131">Displays the name of the source file that contains the breakpoint, and the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="eec70-132">**Endereço**</span><span class="sxs-lookup"><span data-stu-id="eec70-132">**Address**</span></span>  
 <span data-ttu-id="eec70-133">O depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] não dá suporte a este recurso.</span><span class="sxs-lookup"><span data-stu-id="eec70-133">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="eec70-134">**Processo**</span><span class="sxs-lookup"><span data-stu-id="eec70-134">**Process**</span></span>  
 <span data-ttu-id="eec70-135">Exibe **[SQL]** para indicar que este é um processo do [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eec70-135">Displays **[SQL]** to indicate that this is a [!INCLUDE[ssDE](../../includes/ssde-md.md)] process.</span></span> <span data-ttu-id="eec70-136">Em seguida apresenta o nome da instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] na qual o código é executado.</span><span class="sxs-lookup"><span data-stu-id="eec70-136">This is followed by the name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the code executes.</span></span>  
  
## <a name="breakpoints-window-toolbar"></a><span data-ttu-id="eec70-137">Barra de ferramentas da janela Pontos de Interrupção</span><span class="sxs-lookup"><span data-stu-id="eec70-137">Breakpoints Window Toolbar</span></span>  
 <span data-ttu-id="eec70-138">Quando a janela atual do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] tem pontos de interrupção ativos, a janela **Pontos de Interrupção** exibe uma barra de ferramentas que pode ser usada para gerenciar os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="eec70-138">When the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window has active breakpoints, the **Breakpoints** window displays a toolbar that can be used to manage the breakpoints.</span></span>  
  
 <span data-ttu-id="eec70-139">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="eec70-139">**Delete**</span></span>  
 <span data-ttu-id="eec70-140">Exclui o ponto de interrupção selecionado.</span><span class="sxs-lookup"><span data-stu-id="eec70-140">Deletes the selected breakpoint.</span></span>  
  
 <span data-ttu-id="eec70-141">**Excluir Todos os Pontos de Interrupção**</span><span class="sxs-lookup"><span data-stu-id="eec70-141">**Delete All Breakpoints**</span></span>  
 <span data-ttu-id="eec70-142">Exclui todos os pontos de interrupção exibidos na janela **Pontos de Interrupção** .</span><span class="sxs-lookup"><span data-stu-id="eec70-142">Deletes all breakpoints that are displayed in the **Breakpoints** window.</span></span>  
  
 <span data-ttu-id="eec70-143">**Desabilitar Todos os Pontos de Interrupção**</span><span class="sxs-lookup"><span data-stu-id="eec70-143">**Disable All Breakpoints**</span></span>  
 <span data-ttu-id="eec70-144">Desabilita todos os pontos de interrupção de forma que eles não interrompam a execução de código; porém, os pontos de interrupção permanecem.</span><span class="sxs-lookup"><span data-stu-id="eec70-144">Disables all breakpoints so that they no longer stop code execution; however, the breakpoints remain.</span></span> <span data-ttu-id="eec70-145">Quando todos os pontos de interrupção estão desabilitados, este botão se transforma em **Habilitar Todos os Pontos de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="eec70-145">When all the breakpoints are disabled, this button becomes **Enable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="eec70-146">**Habilitar Todos os Pontos de Interrupção**</span><span class="sxs-lookup"><span data-stu-id="eec70-146">**Enable All Breakpoints**</span></span>  
 <span data-ttu-id="eec70-147">Habilita todos os pontos de interrupção de forma que eles interrompam a execução de código.</span><span class="sxs-lookup"><span data-stu-id="eec70-147">Enables all breakpoints so that they stop code execution.</span></span> <span data-ttu-id="eec70-148">Quando todos os pontos de interrupção estão habilitados, este botão se transforma em **Desabilitar Todos os Pontos de Interrupção**.</span><span class="sxs-lookup"><span data-stu-id="eec70-148">When all breakpoints are enabled, this button becomes **Disable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="eec70-149">**Ir para Código Fonte**</span><span class="sxs-lookup"><span data-stu-id="eec70-149">**Go To Source Code**</span></span>  
 <span data-ttu-id="eec70-150">Posiciona o cursor na linha do Editor de Consultas que contém o ponto de interrupção selecionado.</span><span class="sxs-lookup"><span data-stu-id="eec70-150">Positions the cursor on the line in the Query Editor that contains the selected breakpoint.</span></span>  
  
 <span data-ttu-id="eec70-151">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="eec70-151">**Columns**</span></span>  
 <span data-ttu-id="eec70-152">Lista todas as colunas que podem ser exibidas na janela **Pontos de Interrupção** .</span><span class="sxs-lookup"><span data-stu-id="eec70-152">Lists all the columns that can be displayed in the **Breakpoints** window.</span></span> <span data-ttu-id="eec70-153">Uma caixa de seleção indica as colunas em exibição.</span><span class="sxs-lookup"><span data-stu-id="eec70-153">A check box indicates the columns that are displayed.</span></span> <span data-ttu-id="eec70-154">Para adicionar ou remover uma coluna na janela **Pontos de Interrupção** , selecione a coluna na lista.</span><span class="sxs-lookup"><span data-stu-id="eec70-154">To add or remove a column in the **Breakpoints** window, select the column on the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec70-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eec70-155">See Also</span></span>  
 [<span data-ttu-id="eec70-156">Depurador do Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eec70-156">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
