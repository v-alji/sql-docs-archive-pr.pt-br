---
title: Utilitário sqlps | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- sqlps utility
- PowerShell [SQL Server], sqlps utility
ms.assetid: 4b2515a6-12c3-44fb-b263-1c567681cd2b
author: stevestein
ms.author: sstein
ms.openlocfilehash: b445366b3fb99ad4beebdf7b203ada77afe90c8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678382"
---
# <a name="sqlps-utility"></a><span data-ttu-id="2cdbb-102">Utilitário sqlps</span><span class="sxs-lookup"><span data-stu-id="2cdbb-102">sqlps Utility</span></span>
  <span data-ttu-id="2cdbb-103">O utilitário `sqlps` inicia uma sessão do Windows PowerShell 2.0 com os cmdlets e o provedor do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell carregados e registrados.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-103">The `sqlps` utility starts a Windows PowerShell 2.0 session with the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and cmdlets loaded and registered.</span></span> <span data-ttu-id="2cdbb-104">Você pode inserir comandos ou scripts do PowerShell que usam os componentes do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell para trabalhar com instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e seus objetos.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-104">You can enter PowerShell commands or scripts that use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components to work with instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and their objects.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="2cdbb-105">Use o módulo `sqlps` do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-105">Use the `sqlps` PowerShell module instead.</span></span> <span data-ttu-id="2cdbb-106">Para obter mais informações sobre o `sqlps` módulo, consulte [importar o módulo sqlps](../database-engine/import-the-sqlps-module.md).</span><span class="sxs-lookup"><span data-stu-id="2cdbb-106">For more information about the `sqlps` module, see [Import the SQLPS Module](../database-engine/import-the-sqlps-module.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cdbb-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2cdbb-107">Syntax</span></span>  
  
```  
  
      sqlps   
[ [ [ -NoLogo ][ -NoExit ][ -NoProfile ]  
    [ -OutPutFormat { Text | XML } ] [ -InPutFormat { Text | XML } ]  
  ]  
  [ -Command { -  
             | script_block [ -argsargument_array ]  
             | string [ command_parameters ]  
             }  
  ]  
]  
[ -? | -Help ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2cdbb-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2cdbb-108">Arguments</span></span>  
 <span data-ttu-id="2cdbb-109">**-NoLogo**</span><span class="sxs-lookup"><span data-stu-id="2cdbb-109">**-NoLogo**</span></span>  
 <span data-ttu-id="2cdbb-110">Especifica que o utilitário `sqlps` oculta a faixa de direitos autorais quando é iniciado.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-110">Specifies that the `sqlps` utility hide the copyright banner when it starts.</span></span>  
  
 <span data-ttu-id="2cdbb-111">**-NoExit**</span><span class="sxs-lookup"><span data-stu-id="2cdbb-111">**-NoExit**</span></span>  
 <span data-ttu-id="2cdbb-112">Especifica que o utilitário `sqlps` continua em execução após a conclusão dos comandos de inicialização.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-112">Specifies that the `sqlps` utility continue running after the startup commands have completed.</span></span>  
  
 <span data-ttu-id="2cdbb-113">**-NoProfile**</span><span class="sxs-lookup"><span data-stu-id="2cdbb-113">**-NoProfile**</span></span>  
 <span data-ttu-id="2cdbb-114">Especifica que o utilitário `sqlps` não carrega um perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-114">Specifies that the `sqlps` utility not load a user profile.</span></span> <span data-ttu-id="2cdbb-115">Os perfis de usuário registram alias, funções e variáveis usados com frequência para uso em sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-115">User profiles record commonly used aliases, functions, and variables for use across PowerShell sessions.</span></span>  
  
 <span data-ttu-id="2cdbb-116">**-OutPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="2cdbb-116">**-OutPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="2cdbb-117">Especifica que a `sqlps` saída do utilitário seja formatada como cadeias de caracteres de texto (**texto**) ou em um formato CLIXML serializado (**XML**).</span><span class="sxs-lookup"><span data-stu-id="2cdbb-117">Specifies that the `sqlps` utility output be formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="2cdbb-118">**-InPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="2cdbb-118">**-InPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="2cdbb-119">Especifica que a entrada para o `sqlps` utilitário é formatada como cadeias de caracteres de texto (**texto**) ou em um formato CLIXML serializado (**XML**).</span><span class="sxs-lookup"><span data-stu-id="2cdbb-119">Specifies that input to the `sqlps` utility is formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="2cdbb-120">**-Command**</span><span class="sxs-lookup"><span data-stu-id="2cdbb-120">**-Command**</span></span>  
 <span data-ttu-id="2cdbb-121">Especifica o comando para a execução do utilitário `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-121">Specifies the command for the `sqlps` utility to run.</span></span> <span data-ttu-id="2cdbb-122">O `sqlps` utilitário executa o comando e, em seguida, sai, a menos que **-NoExit** também seja especificado.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-122">The `sqlps` utility runs the command and then exits, unless **-NoExit** is also specified.</span></span> <span data-ttu-id="2cdbb-123">Não especifique outras opções depois de **-Command**, pois elas serão lidas como parâmetros de comando.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-123">Do not specify any other switches after **-Command**, they will be read as command parameters.</span></span>  
  
 **-**  
 <span data-ttu-id="2cdbb-124">**-Command-** especifica que o `sqlps` utilitário leu a entrada da entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-124">**-Command-** specifies that the `sqlps` utility read the input from the standard input.</span></span>  
  
 <span data-ttu-id="2cdbb-125">*Script_block* [ **-args**_argument_array_ ]</span><span class="sxs-lookup"><span data-stu-id="2cdbb-125">*script_block* [ **-args**_argument_array_ ]</span></span>  
 <span data-ttu-id="2cdbb-126">Especifica um bloco de comandos de PowerShell para executar. O bloco deve ficar entre chaves: {}.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-126">Specifies a block of PowerShell commands to run, the block must be enclosed in braces: {}.</span></span> <span data-ttu-id="2cdbb-127">*Script_block* só pode ser especificado quando o `sqlps` utilitário é chamado do **PowerShell** ou de outra `sqlps` sessão do utilitário.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-127">*Script_block* can only be specified when the `sqlps` utility is called from either **PowerShell** or another `sqlps` utility session.</span></span> <span data-ttu-id="2cdbb-128">O *argument_array* é uma matriz de variáveis do PowerShell que contêm os argumentos para os comandos do PowerShell em *script_block*.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-128">The *argument_array* is an array of PowerShell variables containing the arguments for the PowerShell commands in the *script_block*.</span></span>  
  
 <span data-ttu-id="2cdbb-129">*string* [ *command_parameters* ]</span><span class="sxs-lookup"><span data-stu-id="2cdbb-129">*string* [ *command_parameters* ]</span></span>  
 <span data-ttu-id="2cdbb-130">Especifica que uma cadeia de caracteres contendo os comandos do PowerShell seja executada.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-130">Specifies a string that contains the PowerShell commands to be run.</span></span> <span data-ttu-id="2cdbb-131">Use o formato **"& { *`command`* }"**.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-131">Use the format **"&{*`command`*}"**.</span></span> <span data-ttu-id="2cdbb-132">As aspas indicam uma cadeia de caracteres e o operador Invoke (&) faz com que o `sqlps` utilitário execute o comando.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-132">The quotation marks indicate a string, and the invoke operator (&) causes the `sqlps` utility to run the command.</span></span>  
  
 <span data-ttu-id="2cdbb-133">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="2cdbb-133">[ **-?**</span></span><span data-ttu-id="2cdbb-134"> |  **-Help** ]</span><span class="sxs-lookup"><span data-stu-id="2cdbb-134"> | **-Help** ]</span></span>  
 <span data-ttu-id="2cdbb-135">Mostra o resumo da sintaxe de opções do utilitário `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-135">Shows the syntax summary of the `sqlps` utility options.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cdbb-136">Comentários</span><span class="sxs-lookup"><span data-stu-id="2cdbb-136">Remarks</span></span>  
 <span data-ttu-id="2cdbb-137">O `sqlps` utilitário inicia o ambiente do PowerShell (PowerShell.exe) e carrega o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] módulo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-137">The `sqlps` utility starts the PowerShell environment (PowerShell.exe) and loads the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell module.</span></span> <span data-ttu-id="2cdbb-138">O módulo, também chamado `sqlps` , carrega e registra esses [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2cdbb-138">The module, also named `sqlps`, loads and registers these [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins:</span></span>  
  
-   <span data-ttu-id="2cdbb-139">Microsoft.SqlServer.Management.PSProvider.dll</span><span class="sxs-lookup"><span data-stu-id="2cdbb-139">Microsoft.SqlServer.Management.PSProvider.dll</span></span>  
  
     <span data-ttu-id="2cdbb-140">Implementa o provedor do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell e os cmdlets associados, como **Encode-SqlName** e **Decode-SqlName**.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-140">Implements the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and associated cmdlets such as **Encode-SqlName** and **Decode-SqlName**.</span></span>  
  
-   <span data-ttu-id="2cdbb-141">Microsoft.SqlServer.Management.PSSnapin.dll</span><span class="sxs-lookup"><span data-stu-id="2cdbb-141">Microsoft.SqlServer.Management.PSSnapin.dll</span></span>  
  
     <span data-ttu-id="2cdbb-142">Implementa os cmdlets **Invoke-Sqlcmd** e **Invoke-PolicyEvaluation** .</span><span class="sxs-lookup"><span data-stu-id="2cdbb-142">Implements the **Invoke-Sqlcmd** and **Invoke-PolicyEvaluation** cmdlets.</span></span>  
  
 <span data-ttu-id="2cdbb-143">É possível usar o utilitário `sqlps` para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2cdbb-143">You can use the `sqlps` utility to do the following:</span></span>  
  
-   <span data-ttu-id="2cdbb-144">Executar comandos do PowerShell de forma interativa.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-144">Interactively run PowerShell commands.</span></span>  
  
-   <span data-ttu-id="2cdbb-145">Executar arquivos de script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-145">Run PowerShell script files.</span></span>  
  
-   <span data-ttu-id="2cdbb-146">Executar cmdlets do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cdbb-146">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="2cdbb-147">Usar os caminhos de provedor do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para navegar pela hierarquia dos objetos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cdbb-147">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="2cdbb-148">Por padrão, o `sqlps` utilitário é executado com a política de execução de script definida como **restrita**.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-148">By default, the `sqlps` utility runs with the scripting execution policy set to **Restricted**.</span></span> <span data-ttu-id="2cdbb-149">Isso impede a execução de quaisquer scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-149">This prevents running any PowerShell scripts.</span></span> <span data-ttu-id="2cdbb-150">Você pode usar o cmdlet **Set-ExecutionPolicy** a fim de habilitar a execução de scripts assinados ou de qualquer script.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-150">You can use the **Set-ExecutionPolicy** cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="2cdbb-151">Execute apenas scripts de fontes confiáveis e proteja todos os arquivos de entrada e saída usando as permissões NTFS adequadas.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-151">Only run scripts from trusted sources, and secure all input and output files by using the appropriate NTFS permissions.</span></span> <span data-ttu-id="2cdbb-152">Para obter mais informações sobre como habilitar scripts do PowerShell, consulte [Running Windows PowerShell Scripts](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/)(a página pode estar em inglês).</span><span class="sxs-lookup"><span data-stu-id="2cdbb-152">For more information about enabling PowerShell scripts, see [Running Windows PowerShell Scripts](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/).</span></span>  
  
 <span data-ttu-id="2cdbb-153">A versão do utilitário `sqlps` no [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] e no [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] foi implementada como um minishell do Windows PowerShell 1.0.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-153">The version of the `sqlps` utility in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] and [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] was implemented as a Windows PowerShell 1.0 mini-shell.</span></span> <span data-ttu-id="2cdbb-154">Os minishells têm determinadas restrições, como não permitir que os usuários carreguem snap-ins diferentes dos carregados pelo minishell.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-154">Mini-shells have certain restrictions, such as not allowing users to load snap-ins other than those loaded by the mini-shell.</span></span> <span data-ttu-id="2cdbb-155">Essas restrições não se aplicam à versão [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] e superiores do utilitário, que foi alterado para usar o módulo `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-155">These restrictions do not apply to the [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] and higher versions of the utility, which have been changed to use the `sqlps` module.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2cdbb-156">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2cdbb-156">Examples</span></span>  

### <a name="a-run-the-sqlps-utility-in-default-interactive-mode-without-the-copyright-banner"></a><span data-ttu-id="2cdbb-157">a.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-157">A.</span></span> <span data-ttu-id="2cdbb-158">Executar o utilitário sqlps no modo interativo padrão, sem a faixa de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="2cdbb-158">Run the sqlps utility in default, interactive mode without the copyright banner</span></span>
  
```cmd
sqlps -NoLogo  
```  
  
### <a name="b-run-a-sql-server-powershell-script-from-the-command-prompt"></a><span data-ttu-id="2cdbb-159">B.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-159">B.</span></span> <span data-ttu-id="2cdbb-160">Executar um script do SQL Server PowerShell no prompt de comando</span><span class="sxs-lookup"><span data-stu-id="2cdbb-160">Run a SQL Server PowerShell script from the command prompt</span></span>
  
```cmd
sqlps -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
### <a name="c-run-a-sql-server-powershell-script-from-the-command-prompt-and-keep-running-after-the-script-completes"></a><span data-ttu-id="2cdbb-161">C.</span><span class="sxs-lookup"><span data-stu-id="2cdbb-161">C.</span></span> <span data-ttu-id="2cdbb-162">Executar um script do SQL Server PowerShell a partir do prompt de comando, e manter a execução após a conclusão do script</span><span class="sxs-lookup"><span data-stu-id="2cdbb-162">Run a SQL Server PowerShell script from the command prompt, and keep running after the script completes</span></span>
  
```cmd
sqlps -NoExit -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cdbb-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2cdbb-163">See Also</span></span>  
 <span data-ttu-id="2cdbb-164">[Habilitar ou desabilitar um protocolo de rede de servidor](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="2cdbb-164">[Enable or Disable a Server Network Protocol](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 [<span data-ttu-id="2cdbb-165">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cdbb-165">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
