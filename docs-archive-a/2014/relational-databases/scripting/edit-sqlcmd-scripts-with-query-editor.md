---
title: Editar scripts SQLCMD com o Editor de Consultas
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], SQLCMD scripts
- SQLCMD scripts
- modifying scripts
- Query Editor [Database Engine], SQLCMD scripts
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: f77b866d-c330-47c9-9e74-0b8d8dff4b31
author: rothja
ms.author: jroth
ms.openlocfilehash: a3466cfc15ea2f4f0c8de5da42f4a1c24c28a575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574628"
---
# <a name="edit-sqlcmd-scripts-with-query-editor"></a><span data-ttu-id="240a5-102">Editar scripts SQLCMD com o Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="240a5-102">Edit SQLCMD Scripts with Query Editor</span></span>
  <span data-ttu-id="240a5-103">Com o Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , você pode gravar e editar consultas como scripts SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="240a5-103">By using the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] you can write and edit queries as SQLCMD scripts.</span></span> <span data-ttu-id="240a5-104">Você usa scripts SQLCMD quando precisa processar comandos de Sistema do Windows e instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] no mesmo script.</span><span class="sxs-lookup"><span data-stu-id="240a5-104">You use SQLCMD scripts when you have to process Windows System commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the same script.</span></span>  
  
## <a name="sqlcmd-mode"></a><span data-ttu-id="240a5-105">Modo SQLCMD</span><span class="sxs-lookup"><span data-stu-id="240a5-105">SQLCMD Mode</span></span>  
 <span data-ttu-id="240a5-106">Para usar o Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] para gravar ou editar scripts SQLCMD, habilite o modo de script SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="240a5-106">To use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor to write or edit SQLCMD scripts, you must enable the SQLCMD scripting mode.</span></span> <span data-ttu-id="240a5-107">Por padrão, o modo SQLCMD não é habilitado no Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="240a5-107">By default, SQLCMD mode is not enabled in the Query Editor.</span></span> <span data-ttu-id="240a5-108">Você pode habilitar o modo de script clicando no ícone **Modo SQLCMD** na barra de ferramentas ou selecionando **Modo SQLCMD** no menu **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="240a5-108">You can enable scripting mode by clicking the **SQLCMD Mode** icon in the toolbar or by selecting **SQLCMD Mode** from the **Query** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="240a5-109">A habilitação do modo SQLCMD desativa o IntelliSense e o depurador [!INCLUDE[tsql](../../includes/tsql-md.md)] no Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="240a5-109">Enabling SQLCMD mode turns off IntelliSense and the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="240a5-110">No Editor de Consultas, os scripts SQLCMD podem usar os mesmos recursos disponíveis para todos os scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="240a5-110">SQLCMD scripts in the Query Editor can use the same features that all [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts use.</span></span> <span data-ttu-id="240a5-111">Entre esses recursos estão:</span><span class="sxs-lookup"><span data-stu-id="240a5-111">These features include the following:</span></span>  
  
-   <span data-ttu-id="240a5-112">Codificação por cores</span><span class="sxs-lookup"><span data-stu-id="240a5-112">Color Coding</span></span>  
  
-   <span data-ttu-id="240a5-113">Scripts de execução</span><span class="sxs-lookup"><span data-stu-id="240a5-113">Executing Scripts</span></span>  
  
-   <span data-ttu-id="240a5-114">Controle do código-fonte</span><span class="sxs-lookup"><span data-stu-id="240a5-114">Source Control</span></span>  
  
-   <span data-ttu-id="240a5-115">Scripts de análise</span><span class="sxs-lookup"><span data-stu-id="240a5-115">Parsing Scripts</span></span>  
  
-   <span data-ttu-id="240a5-116">Showplan</span><span class="sxs-lookup"><span data-stu-id="240a5-116">Showplan</span></span>  
  
## <a name="enable-sqlcmd-scripting-in-query-editor"></a><span data-ttu-id="240a5-117">Habilitar o script de SQLCMD no Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="240a5-117">Enable SQLCMD Scripting in Query Editor</span></span>  
 <span data-ttu-id="240a5-118">Para ativar o script SQLCMD em uma janela ativa do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] , use o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="240a5-118">To turn SQLCMD scripting on for an active [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window, use the following procedure.</span></span>  
  
#### <a name="to-switch-a-database-engine-query-editor-window-to-sqlcmd-mode"></a><span data-ttu-id="240a5-119">Para alternar uma janela do Editor de Consultas do Mecanismo de Banco de Dados para o modo SQLCMD</span><span class="sxs-lookup"><span data-stu-id="240a5-119">To switch a Database Engine Query Editor window to SQLCMD mode</span></span>  
  
1.  <span data-ttu-id="240a5-120">No Pesquisador de Objetos, clique com o botão direito do mouse no servidor e clique em **Nova Consulta**para abrir uma nova janela do Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="240a5-120">In Object Explorer, right-click the server, and then click **New Query**, to open a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span>  
  
2.  <span data-ttu-id="240a5-121">No menu **Consulta** , clique em **Modo SQLCMD**.</span><span class="sxs-lookup"><span data-stu-id="240a5-121">On the **Query** menu, click **SQLCMD Mode**.</span></span>  
  
     <span data-ttu-id="240a5-122">O Editor de Consultas executa instruções **sqlcmd** no contexto do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="240a5-122">The Query Editor executes **sqlcmd** statements in the context of the Query Editor.</span></span>  
  
3.  <span data-ttu-id="240a5-123">Na barra de ferramentas **Editor do SQL** , na lista **Bancos de Dados Disponíveis** , selecione [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="240a5-123">On the **SQL Editor** toolbar, in the **Available Databases** list, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
4.  <span data-ttu-id="240a5-124">Na janela do Editor de Consultas, digite as duas instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] a seguir e a instrução `!!DIR` **sqlcmd** :</span><span class="sxs-lookup"><span data-stu-id="240a5-124">In the Query Editor window, type the following two [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and the `!!DIR` **sqlcmd** statement:</span></span>  
  
    ```  
    SELECT DISTINCT Type FROM Sales.SpecialOffer;  
    GO  
    !!DIR  
    GO  
    SELECT ProductCategoryID, Name FROM Production.ProductCategory;  
    GO  
    ```  
  
5.  <span data-ttu-id="240a5-125">Pressione F5 para executar a seção inteira de instruções mistas [!INCLUDE[tsql](../../includes/tsql-md.md)] e MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="240a5-125">Press F5 to execute the whole section of mixed [!INCLUDE[tsql](../../includes/tsql-md.md)] and MS-DOS statements.</span></span>  
  
     <span data-ttu-id="240a5-126">Observe os dois painéis de resultados SQL da primeira e terceira instruções.</span><span class="sxs-lookup"><span data-stu-id="240a5-126">Notice the two SQL result panes from the first and third statements.</span></span>  
  
6.  <span data-ttu-id="240a5-127">No painel **Resultados** , clique na guia **Mensagens** para ver as mensagens das três instruções:</span><span class="sxs-lookup"><span data-stu-id="240a5-127">In the **Results** pane, click the **Messages** tab to see the messages from all three statements:</span></span>  
  
    -   <span data-ttu-id="240a5-128">(6 linha(s) afetada(s))</span><span class="sxs-lookup"><span data-stu-id="240a5-128">(6 row(s) affected)</span></span>  
  
    -   \<The directory information>  
  
    -   <span data-ttu-id="240a5-129">(4 linha(s) afetada(s))</span><span class="sxs-lookup"><span data-stu-id="240a5-129">(4 row(s) affected)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="240a5-130">Quando executado na linha de comando, o utilitário **sqlcmd** permite a interação total com o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="240a5-130">When executed from the command line, the **sqlcmd** utility permits full interaction with the operating system.</span></span> <span data-ttu-id="240a5-131">Ao usar o Editor de Consultas no **Modo SQLCMD**, tenha cuidado para não executar instruções interativas.</span><span class="sxs-lookup"><span data-stu-id="240a5-131">When you use the Query Editor in **SQLCMD Mode**, you must be careful not to execute interactive statements.</span></span> <span data-ttu-id="240a5-132">O Editor de Consultas não pode responder a prompts do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="240a5-132">The Query Editor cannot respond to operating system prompts.</span></span>  
  
 <span data-ttu-id="240a5-133">Para obter mais informações sobre como executar o SQLCMD, consulte [sqlcmd Utility](../../tools/sqlcmd-utility.md)ou consulte o tutorial do SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="240a5-133">For more information about how to run SQLCMD, see [sqlcmd Utility](../../tools/sqlcmd-utility.md), or take the SQLCMD tutorial.</span></span>  
  
## <a name="enable-sqlcmd-scripting-by-default"></a><span data-ttu-id="240a5-134">Habilitar o script SQLCMD por padrão</span><span class="sxs-lookup"><span data-stu-id="240a5-134">Enable SQLCMD Scripting by Default</span></span>  
 <span data-ttu-id="240a5-135">Para ativar o script de SQLCMD por padrão, no menu **Ferramentas** , selecione **Opções**, expanda **Execução de Consulta**e **SQL Server**, clique na página **Geral** e marque a caixa **Por padrão, abrir novas consultas no modo SQLCMD** .</span><span class="sxs-lookup"><span data-stu-id="240a5-135">To turn SQLCMD scripting on by default, on the **Tools** menu select **Options**, expand **Query Execution**, and **SQL Server**, click the **General** page, and then check the **By default open new queries in SQLCMD Mode** box.</span></span>  
  
## <a name="writing-and-editing-sqlcmd-scripts"></a><span data-ttu-id="240a5-136">Gravando e editando scripts SQLCMD</span><span class="sxs-lookup"><span data-stu-id="240a5-136">Writing and Editing SQLCMD Scripts</span></span>  
 <span data-ttu-id="240a5-137">Depois de habilitar o modo de script, você pode gravar comandos SQLCMD e instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="240a5-137">After enabling scripting mode you may write SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="240a5-138">As seguintes regras se aplicam:</span><span class="sxs-lookup"><span data-stu-id="240a5-138">The following rules apply:</span></span>  
  
-   <span data-ttu-id="240a5-139">Comandos SQLCMD devem ser a primeira instrução em uma linha.</span><span class="sxs-lookup"><span data-stu-id="240a5-139">SQLCMD commands must be the first statement on a line.</span></span>  
  
-   <span data-ttu-id="240a5-140">Somente um comando SQLCMD é permitido em cada linha.</span><span class="sxs-lookup"><span data-stu-id="240a5-140">Only one SQLCMD command is permitted on each line.</span></span>  
  
-   <span data-ttu-id="240a5-141">Comandos SQLCMD podem ser precedidos por comentários ou espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="240a5-141">SQLCMD commands can be preceded by comments or white space.</span></span>  
  
-   <span data-ttu-id="240a5-142">Comandos SQLCMD em caracteres de comentário não são executados.</span><span class="sxs-lookup"><span data-stu-id="240a5-142">SQLCMD commands within comment characters are not executed.</span></span>  
  
-   <span data-ttu-id="240a5-143">Caracteres de comentário de linha única são dois hífens (`--)` ) e devem aparecer no início de uma linha.</span><span class="sxs-lookup"><span data-stu-id="240a5-143">Single line comment characters are two hyphens (`--)` and must appear at the beginning of a line.</span></span>  
  
-   <span data-ttu-id="240a5-144">Comandos de sistema operacional devem ser precedidos por dois pontos de exclamação (`!!`).</span><span class="sxs-lookup"><span data-stu-id="240a5-144">Operating system commands must be preceded by two exclamation points (`!!`).</span></span> <span data-ttu-id="240a5-145">O comando com dois pontos de exclamação faz com que a instrução que vem depois desses pontos seja executada usando o processador de comando `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="240a5-145">The double-exclamation points command causes the statement that follows the exclamation points to be executed using the `cmd.exe` command processor.</span></span> <span data-ttu-id="240a5-146">Como o texto depois de `!!` é passado como um parâmetro para `cmd.exe`, a linha de comando final será executada como: `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.</span><span class="sxs-lookup"><span data-stu-id="240a5-146">The text after `!!` is passed in as a parameter to `cmd.exe`, so the final command line will execute as: `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.</span></span>  
  
-   <span data-ttu-id="240a5-147">Para fazer uma distinção clara entre comandos SQLCMD e comandos [!INCLUDE[tsql](../../includes/tsql-md.md)], todos os comandos SQLCMD precisam ser precedidos por dois-pontos (`:`).</span><span class="sxs-lookup"><span data-stu-id="240a5-147">To make a clear distinction between SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)], all SQLCMD commands, need to be prefixed with a colon (`:`).</span></span>  
  
-   <span data-ttu-id="240a5-148">O comando `GO` pode ser usado sem prefácio ou precedido por `!!:`</span><span class="sxs-lookup"><span data-stu-id="240a5-148">The `GO` command may be used without preface, or preceded by `!!:`</span></span>  
  
-   <span data-ttu-id="240a5-149">O Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] dá suporte para variáveis de ambiente e variáveis definidas como parte de um script SQLCMD, mas não dá suporte para variáveis SQLCMD internas ou **osql** .</span><span class="sxs-lookup"><span data-stu-id="240a5-149">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports environment variables and variables that are defined as part of a SQLCMD script, but does not support built-in SQLCMD or **osql** variables.</span></span> <span data-ttu-id="240a5-150">O processamento SQLCMD feito pelo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] diferencia maiúsculas de minúsculas para variáveis.</span><span class="sxs-lookup"><span data-stu-id="240a5-150">SQLCMD processing by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is case sensitive for variables.</span></span> <span data-ttu-id="240a5-151">Por exemplo, PRINT '$ (COMPUTERNAME)' produz o resultado correto, mas PRINT '$(ComputerName)' retorna um erro.</span><span class="sxs-lookup"><span data-stu-id="240a5-151">For example, PRINT '$(COMPUTERNAME)' produces the correct result, but PRINT '$(ComputerName)' returns an error.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="240a5-152">usa o [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient para a execução em modo regular e SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="240a5-152">uses [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient for execution in regular and SQLCMD mode.</span></span> <span data-ttu-id="240a5-153">Quando executado na linha de comando, o SQLCMD usa o provedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="240a5-153">When run from the command line, SQLCMD uses the OLE DB provider.</span></span> <span data-ttu-id="240a5-154">Devido às diferentes opções padrão que podem ser aplicadas, é possível observar um comportamento diferente ao executar a mesma consulta no Modo SQLCMD do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e no utilitário SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="240a5-154">Because different default options may apply, it is possible to get different behavior while executing the same query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] SQLCMD Mode, and in the SQLCMD utility.</span></span>  
  
## <a name="supported-sqlcmd-syntax"></a><span data-ttu-id="240a5-155">Sintaxe SQLCMD com suporte</span><span class="sxs-lookup"><span data-stu-id="240a5-155">Supported SQLCMD Syntax</span></span>  
 <span data-ttu-id="240a5-156">O Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] oferece suporte às seguintes palavras-chave do script SQLCMD:</span><span class="sxs-lookup"><span data-stu-id="240a5-156">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following SQLCMD script keywords:</span></span>  
  
 `[!!:]GO[count]`  
  
 `!! <command>`  
  
 `:exit(statement)`  
  
 `:Quit`  
  
 `:r <filename>`  
  
 `:setvar <var> <value>`  
  
 `:connect server[\instance] [-l login_timeout] [-U user [-P password]]`  
  
 `:on error [ignore|exit]`  
  
 `:error <filename>|stderr|stdout`  
  
 `:out <filename>|stderr|stdout`  
  
> [!NOTE]  
>  <span data-ttu-id="240a5-157">Para `:error` e `:out`, `stderr` e `stdout` envia a saída à guia de mensagens.</span><span class="sxs-lookup"><span data-stu-id="240a5-157">For both `:error` and `:out`, `stderr` and `stdout` send output to the messages tab.</span></span>  
  
 <span data-ttu-id="240a5-158">O Editor de Consultas não oferece suporte aos comandos SQLCMD não listados acima.</span><span class="sxs-lookup"><span data-stu-id="240a5-158">SQLCMD commands not listed above are not supported in Query Editor.</span></span> <span data-ttu-id="240a5-159">Quando um script que contém palavras-chave SQLCMD sem suporte é executado, o editor de consultas enviará uma mensagem "ignorando comando \* \<ignored command*> " para o destino para cada palavra-chave sem suporte.</span><span class="sxs-lookup"><span data-stu-id="240a5-159">When a script containing SQLCMD keywords that are not supported is executed, the Query Editor will send an "Ignoring command \*\<ignored command*>" message to the destination for each unsupported keyword.</span></span> <span data-ttu-id="240a5-160">O script será executado com êxito, mas os comandos sem suporte serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="240a5-160">The script will execute successfully, but the unsupported commands will be ignored.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="240a5-161">Como você não está iniciando o SQLCMD na linha de comando, existem algumas limitações na execução do Editor de Consultas no Modo SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="240a5-161">Because you are not starting SQLCMD from the command line, there are some limitations when running Query Editor in SQLCMD Mode.</span></span> <span data-ttu-id="240a5-162">Você não pode passar parâmetros de linha de comando como variáveis e, como o Editor de Consultas não tem a capacidade para responder a prompts do sistema operacional, tenha cuidado para não executar instruções interativas.</span><span class="sxs-lookup"><span data-stu-id="240a5-162">You cannot pass in command-line parameters such as variables, and, because the Query Editor does not have the ability to respond to operating system prompts, you must be careful not to execute interactive statements.</span></span>  
  
## <a name="color-coding-in-sqlcmd-scripts"></a><span data-ttu-id="240a5-163">Codificação por cores em scripts SQLCMD</span><span class="sxs-lookup"><span data-stu-id="240a5-163">Color Coding in SQLCMD Scripts</span></span>  
 <span data-ttu-id="240a5-164">Com o script SQLCMD habilitado, os scripts serão codificados por cores.</span><span class="sxs-lookup"><span data-stu-id="240a5-164">With SQLCMD scripting enabled, scripts will be color coded.</span></span> <span data-ttu-id="240a5-165">A codificação por cores para palavras-chave do [!INCLUDE[tsql](../../includes/tsql-md.md)] permanecerá a mesma.</span><span class="sxs-lookup"><span data-stu-id="240a5-165">The color coding for [!INCLUDE[tsql](../../includes/tsql-md.md)] keywords will remain the same.</span></span> <span data-ttu-id="240a5-166">Os comandos SQLCMD são apresentados com um plano de fundo sombreado.</span><span class="sxs-lookup"><span data-stu-id="240a5-166">SQLCMD commands are presented with a shaded background.</span></span>  
  
## <a name="example"></a><span data-ttu-id="240a5-167">Exemplo</span><span class="sxs-lookup"><span data-stu-id="240a5-167">Example</span></span>  
 <span data-ttu-id="240a5-168">O exemplo a seguir usa uma instrução **sqlcmd** para criar um arquivo de saída denominado testoutput.txt, executa duas instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT juntamente com um comando de sistema operacional (para imprimir o diretório atual).</span><span class="sxs-lookup"><span data-stu-id="240a5-168">The following example uses a **sqlcmd** statement to create an output file called testoutput.txt, executes two [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statements along with one operating system command (to print out the current directory).</span></span> <span data-ttu-id="240a5-169">O arquivo resultante contém a saída de mensagem da instrução `DIR` , seguida dos resultados produzidos pelas instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="240a5-169">The resultant file contains the message output from the `DIR` statement, followed by the results output from the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
:out C:\testoutput.txt  
SELECT @@VERSION As 'Server Version'  
!!DIR  
!!:GO  
SELECT @@SERVERNAME AS 'Server Name'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="240a5-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="240a5-170">See Also</span></span>  
 [<span data-ttu-id="240a5-171">Utilitário sqlcmd</span><span class="sxs-lookup"><span data-stu-id="240a5-171">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
