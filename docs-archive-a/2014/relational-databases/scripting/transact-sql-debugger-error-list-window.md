---
title: Janela Lista de Erros
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- error list window
- SQL Server Management Studio [SQL Server], error list window
ms.assetid: fae6327d-e268-44ae-a474-4a8f8f843129
author: rothja
ms.author: jroth
ms.openlocfilehash: 00455c339344b7b38a48500c49d139aa52df6116
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582952"
---
# <a name="error-list-window-management-studio"></a><span data-ttu-id="05edb-102">Janela Lista de Erros (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="05edb-102">Error List Window (Management Studio)</span></span>
  <span data-ttu-id="05edb-103">A [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Lista de Erros**do** exibe os erros de sintaxe e semântica gerados no código IntelliSense do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05edb-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Error List** displays the syntax and semantic errors that are generated from the IntelliSense code in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
## <a name="features-of-the-error-list"></a><span data-ttu-id="05edb-104">Recursos da Lista de Erros</span><span class="sxs-lookup"><span data-stu-id="05edb-104">Features of the Error List</span></span>  
 <span data-ttu-id="05edb-105">A **Lista de Erros** fornece a seguinte funcionalidade:</span><span class="sxs-lookup"><span data-stu-id="05edb-105">The **Error List** provides the following functionality:</span></span>  
  
-   <span data-ttu-id="05edb-106">À medida que os scripts são editados, a **Lista de Erros** exibe os erros e avisos gerados pelo IntelliSense no Editor de Consultas [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05edb-106">As you edit scripts, the **Error List** displays the errors and warnings produced by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
-   <span data-ttu-id="05edb-107">Você pode clicar duas vezes em qualquer entrada de mensagem de erro para se concentrar na guia do arquivo de script que gerou o erro e mover-se até o local do erro.</span><span class="sxs-lookup"><span data-stu-id="05edb-107">You can double-click any error message entry to focus on the tab for the script file that generated the error, and move to the error location.</span></span>  
  
-   <span data-ttu-id="05edb-108">É possível filtrar quais entradas você quer exibir e quais colunas de informações quer que apareçam para cada entrada.</span><span class="sxs-lookup"><span data-stu-id="05edb-108">You can filter which entries you want to display, and which columns of information you want appear for each entry.</span></span>  
  
-   <span data-ttu-id="05edb-109">Depois que você corrigir um erro, a entrada com erro será removida da **Lista de Erros**.</span><span class="sxs-lookup"><span data-stu-id="05edb-109">After you fix an error, the error entry is removed from the **Error List**.</span></span>  
  
-   <span data-ttu-id="05edb-110">Quando você fecha a guia para um arquivo de script [!INCLUDE[tsql](../../includes/tsql-md.md)] , os erros desse arquivo são removidos da **Lista de Erros**.</span><span class="sxs-lookup"><span data-stu-id="05edb-110">When you close the tab for a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file, the errors for that file are removed from the **Error List**.</span></span>  
  
## <a name="working-with-the-error-list"></a><span data-ttu-id="05edb-111">Trabalhando com a Lista de Erros</span><span class="sxs-lookup"><span data-stu-id="05edb-111">Working with the Error List</span></span>  
 <span data-ttu-id="05edb-112">Para exibir a **Lista de Erros**, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="05edb-112">To display the **Error List**, do one of the following:</span></span>  
  
-   <span data-ttu-id="05edb-113">No menu **Exibir** , clique em **Lista de Erros**.</span><span class="sxs-lookup"><span data-stu-id="05edb-113">On the **View** menu, click **Error List**.</span></span>  
  
-   <span data-ttu-id="05edb-114">Insira o atalho de teclado CTRL+\\, CTRL+E.</span><span class="sxs-lookup"><span data-stu-id="05edb-114">Enter the keyboard shortcut CTRL+\\, CTRL+E.</span></span>  
  
 <span data-ttu-id="05edb-115">Depois de abrir a **Lista de Erros**, você poderá personalizar sua exibição executando as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="05edb-115">After you open the **Error List**, you can customize your view by performing the following actions:</span></span>  
  
-   <span data-ttu-id="05edb-116">Para classificar a lista, clique em qualquer cabeçalho de coluna.</span><span class="sxs-lookup"><span data-stu-id="05edb-116">To sort the list, click any column header.</span></span> <span data-ttu-id="05edb-117">Para classificar novamente por uma coluna adicional, pressione e segure a tecla SHIFT e clique em outro cabeçalho de coluna.</span><span class="sxs-lookup"><span data-stu-id="05edb-117">To sort again by an additional column, press and hold the SHIFT key, and then click another column header.</span></span>  
  
-   <span data-ttu-id="05edb-118">Para selecionar as colunas a serem exibidas e ocultadas, selecione **Mostrar Colunas** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="05edb-118">To select which columns are displayed and which are hidden, select **Show Columns** from the shortcut menu.</span></span>  
  
-   <span data-ttu-id="05edb-119">Para alterar a ordem na qual as colunas são exibidas, arraste qualquer cabeçalho de coluna para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="05edb-119">To change the order in which columns are displayed, drag any column header to the left or right.</span></span>  
  
 <span data-ttu-id="05edb-120">A **Lista de Erros** não está vinculada a informações adicionais sobre erros específicos.</span><span class="sxs-lookup"><span data-stu-id="05edb-120">The **Error List** does not link to additional information about specific errors.</span></span>  
  
## <a name="transact-sql-errors-in-management-studio"></a><span data-ttu-id="05edb-121">Erros de Transact-SQL no Management Studio</span><span class="sxs-lookup"><span data-stu-id="05edb-121">Transact-SQL Errors in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="05edb-122">exibe erros de scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] nos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="05edb-122">displays errors for [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in the following locations:</span></span>  
  
-   <span data-ttu-id="05edb-123">A **Lista de Erros** contém todos os erros de sintaxe e semântica encontrados pelo IntelliSense no Editor do [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05edb-123">The **Error List** contains all syntax and semantic errors found by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor.</span></span> <span data-ttu-id="05edb-124">Essa lista de erros é atualizada dinamicamente a medida que você edita scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05edb-124">This list of errors is dynamically updated as you edit [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="05edb-125">A lista inclui todos os erros que o editor encontrou em cada script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05edb-125">The list includes all errors that the editor has found in each [!INCLUDE[tsql](../../includes/tsql-md.md)] script.</span></span> <span data-ttu-id="05edb-126">O editor não interrompe a análise de um arquivo após encontrar erros em um script.</span><span class="sxs-lookup"><span data-stu-id="05edb-126">The editor does not stop parsing a file after encountering errors in a script.</span></span> <span data-ttu-id="05edb-127">No [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], o IntelliSense do Editor [!INCLUDE[ssDE](../../includes/ssde-md.md)] não dá suporte a todos os elementos de sintaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05edb-127">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="05edb-128">A **Lista de Erros** contém somente erros de sintaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] que tem suporte no IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="05edb-128">The **Error List** contains only errors from the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax that is supported by IntelliSense.</span></span>  
  
-   <span data-ttu-id="05edb-129">A guia **Mensagens** na parte inferior da janela do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] exibe todos os erros e mensagens retornados pelo [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] quando um script [!INCLUDE[tsql](../../includes/tsql-md.md)] é executado.</span><span class="sxs-lookup"><span data-stu-id="05edb-129">The **Messages** tab at the bottom of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window displays all errors and messages that are returned by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] when a [!INCLUDE[tsql](../../includes/tsql-md.md)] script is executed.</span></span> <span data-ttu-id="05edb-130">Essa lista não muda até que você execute o script novamente.</span><span class="sxs-lookup"><span data-stu-id="05edb-130">This list does not change until you execute the script again.</span></span> <span data-ttu-id="05edb-131">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] interrompe a análise de um lote após encontrar um ou dois erros de compilação; dessa forma, a guia **Mensagens** pode não listar todos os erros de um script.</span><span class="sxs-lookup"><span data-stu-id="05edb-131">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stops parsing a batch after it finds one or two compile errors; therefore, the **Messages** tab might not list all errors in a script.</span></span>  
  
 <span data-ttu-id="05edb-132">Às vezes são listados erros em ambos os locais.</span><span class="sxs-lookup"><span data-stu-id="05edb-132">Sometimes errors are listed in both locations.</span></span> <span data-ttu-id="05edb-133">Por exemplo, um arquivo de script poderia ter um erro de sintaxe exibido na **Lista de Erros**.</span><span class="sxs-lookup"><span data-stu-id="05edb-133">For example, a script file might have a syntax error that is listed in the **Error List**.</span></span> <span data-ttu-id="05edb-134">Se você executar o script antes de corrigir o erro, o analisador do [!INCLUDE[ssDE](../../includes/ssde-md.md)] poderá detectar a mesma condição e retornar outra cópia da mensagem de erro na guia **Mensagens** .</span><span class="sxs-lookup"><span data-stu-id="05edb-134">If you execute the script before you correct the error, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] parser can detect the same condition and return another copy of the error message in the **Messages** tab.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05edb-135">A **Lista de Erros** exibe somente os erros do Editor de Consulta do [!INCLUDE[ssDE](../../includes/ssde-md.md)] ; ela não exibe erros de editores MDX, DMX ou XML/A.</span><span class="sxs-lookup"><span data-stu-id="05edb-135">The **Error List** only displays errors from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor; it does not display errors from the MDX, DMX, or XML/A Editors.</span></span> <span data-ttu-id="05edb-136">Todos os erros de MDX, DMX e XML/A são exibidos na guia **Mensagens** desses editores.</span><span class="sxs-lookup"><span data-stu-id="05edb-136">All MDX, DMX, and XML/A errors are displayed in the **Messages** tab in those editors.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="05edb-137">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="05edb-137">UI element list</span></span>  
 <span data-ttu-id="05edb-138">Quando a **Lista de Erros** estiver aberta, as informações serão exibidas nas seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="05edb-138">When the **Error List** is open, the information is displayed in the following columns:</span></span>  
  
 <span data-ttu-id="05edb-139">**Ordem Padrão**</span><span class="sxs-lookup"><span data-stu-id="05edb-139">**Default Order**</span></span>  
 <span data-ttu-id="05edb-140">Exibe um inteiro que indica a ordem na qual uma entrada foi gerada.</span><span class="sxs-lookup"><span data-stu-id="05edb-140">Displays an integer that indicates the order in which an entry was generated.</span></span>  
  
 <span data-ttu-id="05edb-141">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="05edb-141">**Description**</span></span>  
 <span data-ttu-id="05edb-142">Exibe o texto da entrada de erro.</span><span class="sxs-lookup"><span data-stu-id="05edb-142">Displays the text of the error entry.</span></span> <span data-ttu-id="05edb-143">As descrições longas se acomodam em linhas adicionais.</span><span class="sxs-lookup"><span data-stu-id="05edb-143">Lengthy descriptions wrap onto additional lines.</span></span>  
  
 <span data-ttu-id="05edb-144">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="05edb-144">**File**</span></span>  
 <span data-ttu-id="05edb-145">Exibe o nome do arquivo de script que gerou o erro.</span><span class="sxs-lookup"><span data-stu-id="05edb-145">Displays the name of the script file that generated the error.</span></span>  
  
 <span data-ttu-id="05edb-146">**Linha**</span><span class="sxs-lookup"><span data-stu-id="05edb-146">**Line**</span></span>  
 <span data-ttu-id="05edb-147">Exibe um inteiro que indica qual linha do código inclui o erro.</span><span class="sxs-lookup"><span data-stu-id="05edb-147">Displays an integer that indicates which line of the code includes the error.</span></span>  
  
 <span data-ttu-id="05edb-148">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="05edb-148">**Column**</span></span>  
 <span data-ttu-id="05edb-149">Exibe um inteiro que indica a posição do erro linha na linha do código.</span><span class="sxs-lookup"><span data-stu-id="05edb-149">Displays an integer that indicates the position of the error in the line of code.</span></span>  
  
 <span data-ttu-id="05edb-150">**Projeto**</span><span class="sxs-lookup"><span data-stu-id="05edb-150">**Project**</span></span>  
 <span data-ttu-id="05edb-151">Exibe o nome do projeto que inclui o arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="05edb-151">Displays the name of the project that includes the script file.</span></span>  
