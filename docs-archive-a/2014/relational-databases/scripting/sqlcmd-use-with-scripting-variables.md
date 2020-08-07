---
title: Usar sqlcmd com variáveis de script
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- scripts [SQL Server], sqlcmd utility
- variables [SQL Server], scripts
- scripting variables [SQL Server]
- sqlcmd utility, scripts
- setvar command
ms.assetid: 793495ca-cfc9-498d-8276-c44a5d09a92c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443cb400dc099726ba75bfcec2d38cee4ee2dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581755"
---
# <a name="use-sqlcmd-with-scripting-variables"></a><span data-ttu-id="41564-102">Usar sqlcmd com variáveis de script</span><span class="sxs-lookup"><span data-stu-id="41564-102">Use sqlcmd with Scripting Variables</span></span>
  <span data-ttu-id="41564-103">As variáveis usadas em scripts normalmente são chamadas de variáveis de script.</span><span class="sxs-lookup"><span data-stu-id="41564-103">Variables that are used in scripts are called scripting variables.</span></span> <span data-ttu-id="41564-104">As variáveis de script habilitam um script ser usado em vários cenários.</span><span class="sxs-lookup"><span data-stu-id="41564-104">Scripting variables enable one script to be used in multiple scenarios.</span></span> <span data-ttu-id="41564-105">Por exemplo, se você desejar executar um script em vários servidores, em vez de modificar o script para cada servidor, pode usar uma variável de script para o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="41564-105">For example, if you want to run one script against multiple servers, instead of modifying the script for each server, you can use a scripting variable for the server name.</span></span> <span data-ttu-id="41564-106">Alterando o nome do servidor fornecido para a variável de script, o mesmo script pode ser executado em diferentes servidores.</span><span class="sxs-lookup"><span data-stu-id="41564-106">By changing the server name supplied to the scripting variable, the same script can be executed on different servers.</span></span>  
  
 <span data-ttu-id="41564-107">As variáveis de script podem ser definidas explicitamente usando o comando **setvar** , ou implicitamente, usando a opção **sqlcmd-v** .</span><span class="sxs-lookup"><span data-stu-id="41564-107">Scripting variables can be defined explicitly by using the **setvar** command, or implicitly by using the **sqlcmd-v** option.</span></span>  
  
 <span data-ttu-id="41564-108">Este tópico também inclui exemplos que definem variáveis ambientais no prompt de comando Cmd.exe usando **SET**.</span><span class="sxs-lookup"><span data-stu-id="41564-108">This topic also includes examples defining environmental variables at the Cmd.exe command prompt by using **SET**.</span></span>  
  
## <a name="setting-scripting-variables-by-using-the-setvar-command"></a><span data-ttu-id="41564-109">Definindo variáveis de script usando o comando setvar</span><span class="sxs-lookup"><span data-stu-id="41564-109">Setting Scripting Variables by Using the setvar Command</span></span>  
 <span data-ttu-id="41564-110">O comando **setvar** é usado para definir variáveis de script.</span><span class="sxs-lookup"><span data-stu-id="41564-110">The **setvar** command is used to define scripting variables.</span></span> <span data-ttu-id="41564-111">Variáveis definidas usando o comando **setvar** são armazenadas internamente.</span><span class="sxs-lookup"><span data-stu-id="41564-111">Variables that are defined by using the **setvar** command are stored internally.</span></span> <span data-ttu-id="41564-112">Variáveis de script não devem ser confundidas com variáveis de ambiente, que são definidas no prompt de comando usando **SET**.</span><span class="sxs-lookup"><span data-stu-id="41564-112">Scripting variables should not be confused with environment variables that are defined at the command prompt by using **SET**.</span></span> <span data-ttu-id="41564-113">Se um script fizer referência a uma variável que não é uma variável de ambiente ou não foi definida usando **setvar**, uma mensagem de erro será retornada e a execução do script será interrompida.</span><span class="sxs-lookup"><span data-stu-id="41564-113">If a script references a variable that is not an environment variable or is not defined by using **setvar**, an error message is returned and the execution of the script will stop.</span></span> <span data-ttu-id="41564-114">Para obter mais informações, veja a opção **-b** em [Utilitário sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="41564-114">For more information, see the **-b** option in [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span>  
  
## <a name="variable-precedence-low-to-high"></a><span data-ttu-id="41564-115">Precedência de variável (baixa para alta)</span><span class="sxs-lookup"><span data-stu-id="41564-115">Variable Precedence (Low to High)</span></span>  
 <span data-ttu-id="41564-116">Se mais de um tipo de variável tiver o mesmo nome, a variável com precedência mais alta será usada.</span><span class="sxs-lookup"><span data-stu-id="41564-116">If more than one type of variable has the same name, the variable with the highest precedence is used.</span></span>  
  
1.  <span data-ttu-id="41564-117">Variáveis ambientais do nível de sistema</span><span class="sxs-lookup"><span data-stu-id="41564-117">System level environmental variables</span></span>  
  
2.  <span data-ttu-id="41564-118">Variáveis ambientais do nível de usuário</span><span class="sxs-lookup"><span data-stu-id="41564-118">User level environmental variables</span></span>  
  
3.  <span data-ttu-id="41564-119">Shell de comando (**SET X=Y**) definido no prompt de comando antes de iniciar o **sqlcmd**</span><span class="sxs-lookup"><span data-stu-id="41564-119">Command shell (**SET X=Y**) set at command prompt before starting **sqlcmd**</span></span>  
  
4.  <span data-ttu-id="41564-120">**sqlcmd-v** X=Y</span><span class="sxs-lookup"><span data-stu-id="41564-120">**sqlcmd-v** X=Y</span></span>  
  
5.  <span data-ttu-id="41564-121">**:Setvar** X Y</span><span class="sxs-lookup"><span data-stu-id="41564-121">**:Setvar** X Y</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41564-122">Para exibir as variáveis ambientais, no **Painel de Controle**, abra **Sistema**e clique na guia **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="41564-122">To view the environmental variables, in **Control Panel**, open **System**, and then click the **Advanced** tab.</span></span>  
  
## <a name="implicitly-setting-scripting-variables"></a><span data-ttu-id="41564-123">Definindo implicitamente variáveis de script</span><span class="sxs-lookup"><span data-stu-id="41564-123">Implicitly Setting Scripting Variables</span></span>  
 <span data-ttu-id="41564-124">Ao iniciar o **sqlcmd** com uma opção que contém uma variável **sqlcmd** relacionada, a variável **sqlcmd** será implicitamente definida com o valor especificado com a opção.</span><span class="sxs-lookup"><span data-stu-id="41564-124">When you start **sqlcmd** with an option that has a related **sqlcmd** variable, the **sqlcmd** variable is set implicitly to the value that is specified by using the option.</span></span> <span data-ttu-id="41564-125">No exemplo a seguir, o `sqlcmd` é iniciado com a opção `-l` .</span><span class="sxs-lookup"><span data-stu-id="41564-125">In the following example, `sqlcmd` is started with the `-l` option.</span></span> <span data-ttu-id="41564-126">Isto define implicitamente a variável SQLLOGINTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="41564-126">This implicitly sets the SQLLOGINTIMEOUT variable.</span></span>  
  
 `c:\> sqlcmd -l 60`  
  
 <span data-ttu-id="41564-127">Também é possível usar a opção **-v** para definir uma variável de script existente em um script.</span><span class="sxs-lookup"><span data-stu-id="41564-127">You can also use the **-v** option to set a scripting variable that exists in a script.</span></span> <span data-ttu-id="41564-128">O script a seguir (o nome de arquivo é `testscript.sql`), `ColumnName` é uma variável de script.</span><span class="sxs-lookup"><span data-stu-id="41564-128">In the following script (the file name is `testscript.sql`), `ColumnName` is a scripting variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `SELECT x.$(ColumnName)`  
  
 `FROM Person.Person x`  
  
 <span data-ttu-id="41564-129">`WHERE c.`BusinessEntityID`< 5;`</span><span class="sxs-lookup"><span data-stu-id="41564-129">`WHERE c.`BusinessEntityID `< 5;`</span></span>  
  
 <span data-ttu-id="41564-130">Assim você pode especificar o nome da coluna que deseja que retorne usando a opção `-v` :</span><span class="sxs-lookup"><span data-stu-id="41564-130">You can then specify the name of the column that you want returned by using the `-v` option:</span></span>  
  
 `sqlcmd -v ColumnName ="FirstName" -i c:\testscript.sql`  
  
 <span data-ttu-id="41564-131">Para retornar uma coluna diferente usando o mesmo script, altere o valor da variável de script `ColumnName` .</span><span class="sxs-lookup"><span data-stu-id="41564-131">To return a different column by using the same script, change the value of the `ColumnName` scripting variable.</span></span>  
  
 `sqlcmd -v ColumnName ="LastName" -i c:\testscript.sql`  
  
## <a name="guidelines-for-scripting-variable-names-and-values"></a><span data-ttu-id="41564-132">Diretrizes para nomes e valores de variáveis de script</span><span class="sxs-lookup"><span data-stu-id="41564-132">Guidelines for Scripting Variable Names and Values</span></span>  
 <span data-ttu-id="41564-133">Considere as seguintes diretrizes ao nomear variáveis de script:</span><span class="sxs-lookup"><span data-stu-id="41564-133">Consider the following guidelines when you name scripting variables:</span></span>  
  
-   <span data-ttu-id="41564-134">Os nomes das variáveis não devem conter caracteres de espaços em brancos ou aspas.</span><span class="sxs-lookup"><span data-stu-id="41564-134">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="41564-135">Os nomes das variáveis não devem ter a mesma forma que uma expressão variável, como *$(var)*.</span><span class="sxs-lookup"><span data-stu-id="41564-135">Variable names must not have the same form as a variable expression, such as *$(var)*.</span></span>  
  
-   <span data-ttu-id="41564-136">Variáveis de script não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="41564-136">Scripting variables are case-insensitive</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="41564-137">Se nenhum valor for atribuído a uma variável de ambiente **sqlcmd** , a variável será removida.</span><span class="sxs-lookup"><span data-stu-id="41564-137">If no value is assigned to a **sqlcmd** environment variable, the variable is removed.</span></span> <span data-ttu-id="41564-138">Usar **:setvar VarName** sem um valor limpa a variável.</span><span class="sxs-lookup"><span data-stu-id="41564-138">Using **:setvar VarName** without a value clears the variable.</span></span>  
  
 <span data-ttu-id="41564-139">Considere as seguintes diretrizes ao especificar valores para variáveis de script:</span><span class="sxs-lookup"><span data-stu-id="41564-139">Consider the following guidelines when you specify values for scripting variables:</span></span>  
  
-   <span data-ttu-id="41564-140">Valores de variáveis definidos usando **setvar** ou a opção **-v** deverão ser mantidos entre aspas se o valor da cadeia contiver espaços.</span><span class="sxs-lookup"><span data-stu-id="41564-140">Variable values that are defined by using **setvar** or the **-v** option must be enclosed by quotation marks if the string value contains spaces.</span></span>  
  
-   <span data-ttu-id="41564-141">Se houver aspas no valor da variável, elas devem ser substituídas.</span><span class="sxs-lookup"><span data-stu-id="41564-141">If quotation marks are part of the variable value, they must be escaped.</span></span> <span data-ttu-id="41564-142">Por exemplo:`setvar MyVar "spac""e"`.</span><span class="sxs-lookup"><span data-stu-id="41564-142">For example: :`setvar MyVar "spac""e"`.</span></span>  
  
## <a name="guidelines-for-cmdexe-set-variable-values-and-names"></a><span data-ttu-id="41564-143">Diretrizes para nomes e valores da variável SET de Cmd.exe</span><span class="sxs-lookup"><span data-stu-id="41564-143">Guidelines for Cmd.exe SET Variable Values and Names</span></span>  
 <span data-ttu-id="41564-144">Variáveis definidas usando SET fazem parte do ambiente de Cmd.exe e podem ser referenciadas por **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="41564-144">Variables that are defined by using SET are part of the Cmd.exe environment and can be referenced by **sqlcmd**.</span></span> <span data-ttu-id="41564-145">Considere as seguintes diretrizes:</span><span class="sxs-lookup"><span data-stu-id="41564-145">Consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="41564-146">Os nomes das variáveis não devem conter caracteres de espaços em brancos ou aspas.</span><span class="sxs-lookup"><span data-stu-id="41564-146">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="41564-147">Valores de variáveis podem conter espaços ou aspas.</span><span class="sxs-lookup"><span data-stu-id="41564-147">Variable values may contain spaces or quotation marks.</span></span>  
  
## <a name="sqlcmd-scripting-variables"></a><span data-ttu-id="41564-148">Variáveis de script do sqlcmd</span><span class="sxs-lookup"><span data-stu-id="41564-148">sqlcmd Scripting Variables</span></span>  
 <span data-ttu-id="41564-149">Variáveis definidas por **sqlcmd** são conhecidas como variáveis de script.</span><span class="sxs-lookup"><span data-stu-id="41564-149">Variables that are defined by **sqlcmd** are known as scripting variables.</span></span> <span data-ttu-id="41564-150">A tabela a seguir lista variáveis de script do **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="41564-150">The following table lists **sqlcmd** scripting variables.</span></span>  
  
|<span data-ttu-id="41564-151">Variável</span><span class="sxs-lookup"><span data-stu-id="41564-151">Variable</span></span>|<span data-ttu-id="41564-152">Opção relacionada</span><span class="sxs-lookup"><span data-stu-id="41564-152">Related option</span></span>|<span data-ttu-id="41564-153">R/W</span><span class="sxs-lookup"><span data-stu-id="41564-153">R/W</span></span>|<span data-ttu-id="41564-154">Padrão</span><span class="sxs-lookup"><span data-stu-id="41564-154">Default</span></span>|  
|--------------|--------------------|----------|-------------|  
|<span data-ttu-id="41564-155">SQLCMDUSER\*</span><span class="sxs-lookup"><span data-stu-id="41564-155">SQLCMDUSER\*</span></span>|<span data-ttu-id="41564-156">-U</span><span class="sxs-lookup"><span data-stu-id="41564-156">-U</span></span>|<span data-ttu-id="41564-157">R</span><span class="sxs-lookup"><span data-stu-id="41564-157">R</span></span>|<span data-ttu-id="41564-158">""</span><span class="sxs-lookup"><span data-stu-id="41564-158">""</span></span>|  
|<span data-ttu-id="41564-159">SQLCMDPASSWORD\*</span><span class="sxs-lookup"><span data-stu-id="41564-159">SQLCMDPASSWORD\*</span></span>|<span data-ttu-id="41564-160">-P</span><span class="sxs-lookup"><span data-stu-id="41564-160">-P</span></span>|--|<span data-ttu-id="41564-161">""</span><span class="sxs-lookup"><span data-stu-id="41564-161">""</span></span>|  
|<span data-ttu-id="41564-162">SQLCMDSERVER\*</span><span class="sxs-lookup"><span data-stu-id="41564-162">SQLCMDSERVER\*</span></span>|<span data-ttu-id="41564-163">-S</span><span class="sxs-lookup"><span data-stu-id="41564-163">-S</span></span>|<span data-ttu-id="41564-164">R</span><span class="sxs-lookup"><span data-stu-id="41564-164">R</span></span>|<span data-ttu-id="41564-165">"DefaultLocalInstance"</span><span class="sxs-lookup"><span data-stu-id="41564-165">"DefaultLocalInstance"</span></span>|  
|<span data-ttu-id="41564-166">SQLCMDWORKSTATION</span><span class="sxs-lookup"><span data-stu-id="41564-166">SQLCMDWORKSTATION</span></span>|<span data-ttu-id="41564-167">-H</span><span class="sxs-lookup"><span data-stu-id="41564-167">-H</span></span>|<span data-ttu-id="41564-168">R</span><span class="sxs-lookup"><span data-stu-id="41564-168">R</span></span>|<span data-ttu-id="41564-169">"ComputerName"</span><span class="sxs-lookup"><span data-stu-id="41564-169">"ComputerName"</span></span>|  
|<span data-ttu-id="41564-170">SQLCMDDBNAME</span><span class="sxs-lookup"><span data-stu-id="41564-170">SQLCMDDBNAME</span></span>|<span data-ttu-id="41564-171">-d</span><span class="sxs-lookup"><span data-stu-id="41564-171">-d</span></span>|<span data-ttu-id="41564-172">R</span><span class="sxs-lookup"><span data-stu-id="41564-172">R</span></span>|<span data-ttu-id="41564-173">""</span><span class="sxs-lookup"><span data-stu-id="41564-173">""</span></span>|  
|<span data-ttu-id="41564-174">SQLCMDLOGINTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="41564-174">SQLCMDLOGINTIMEOUT</span></span>|<span data-ttu-id="41564-175">-l</span><span class="sxs-lookup"><span data-stu-id="41564-175">-l</span></span>|<span data-ttu-id="41564-176">R/W</span><span class="sxs-lookup"><span data-stu-id="41564-176">R/W</span></span>|<span data-ttu-id="41564-177">"8" (segundos)</span><span class="sxs-lookup"><span data-stu-id="41564-177">"8" (seconds)</span></span>|  
|<span data-ttu-id="41564-178">SQLCMDSTATTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="41564-178">SQLCMDSTATTIMEOUT</span></span>|<span data-ttu-id="41564-179">-T</span><span class="sxs-lookup"><span data-stu-id="41564-179">-t</span></span>|<span data-ttu-id="41564-180">R/W</span><span class="sxs-lookup"><span data-stu-id="41564-180">R/W</span></span>|<span data-ttu-id="41564-181">"0" = espere indefinidamente</span><span class="sxs-lookup"><span data-stu-id="41564-181">"0" = wait indefinitely</span></span>|  
|<span data-ttu-id="41564-182">SQLCMDHEADERS</span><span class="sxs-lookup"><span data-stu-id="41564-182">SQLCMDHEADERS</span></span>|<span data-ttu-id="41564-183">-H</span><span class="sxs-lookup"><span data-stu-id="41564-183">-h</span></span>|<span data-ttu-id="41564-184">R/W</span><span class="sxs-lookup"><span data-stu-id="41564-184">R/W</span></span>|<span data-ttu-id="41564-185">"0"</span><span class="sxs-lookup"><span data-stu-id="41564-185">"0"</span></span>|  
|<span data-ttu-id="41564-186">SQLCMDCOLSEP</span><span class="sxs-lookup"><span data-stu-id="41564-186">SQLCMDCOLSEP</span></span>|<span data-ttu-id="41564-187">-S</span><span class="sxs-lookup"><span data-stu-id="41564-187">-s</span></span>|<span data-ttu-id="41564-188">R/W</span><span class="sxs-lookup"><span data-stu-id="41564-188">R/W</span></span>|<span data-ttu-id="41564-189">" "</span><span class="sxs-lookup"><span data-stu-id="41564-189">" "</span></span>|  
|<span data-ttu-id="41564-190">SQLCMDCOLWIDTH</span><span class="sxs-lookup"><span data-stu-id="41564-190">SQLCMDCOLWIDTH</span></span>|<span data-ttu-id="41564-191">-w</span><span class="sxs-lookup"><span data-stu-id="41564-191">-w</span></span>|<span data-ttu-id="41564-192">R/W</span><span class="sxs-lookup"><span data-stu-id="41564-192">R/W</span></span>|<span data-ttu-id="41564-193">"0"</span><span class="sxs-lookup"><span data-stu-id="41564-193">"0"</span></span>|  
|<span data-ttu-id="41564-194">SQLCMDPACKETSIZE</span><span class="sxs-lookup"><span data-stu-id="41564-194">SQLCMDPACKETSIZE</span></span>|<span data-ttu-id="41564-195">-a</span><span class="sxs-lookup"><span data-stu-id="41564-195">-a</span></span>|<span data-ttu-id="41564-196">R</span><span class="sxs-lookup"><span data-stu-id="41564-196">R</span></span>|<span data-ttu-id="41564-197">"4096"</span><span class="sxs-lookup"><span data-stu-id="41564-197">"4096"</span></span>|  
|<span data-ttu-id="41564-198">SQLCMDERRORLEVEL</span><span class="sxs-lookup"><span data-stu-id="41564-198">SQLCMDERRORLEVEL</span></span>|<span data-ttu-id="41564-199">-M</span><span class="sxs-lookup"><span data-stu-id="41564-199">-m</span></span>|<span data-ttu-id="41564-200">R/W</span><span class="sxs-lookup"><span data-stu-id="41564-200">R/W</span></span>|<span data-ttu-id="41564-201">"0"</span><span class="sxs-lookup"><span data-stu-id="41564-201">"0"</span></span>|  
|<span data-ttu-id="41564-202">SQLCMDMAXVARTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="41564-202">SQLCMDMAXVARTYPEWIDTH</span></span>|<span data-ttu-id="41564-203">-y</span><span class="sxs-lookup"><span data-stu-id="41564-203">-y</span></span>|<span data-ttu-id="41564-204">R/W</span><span class="sxs-lookup"><span data-stu-id="41564-204">R/W</span></span>|<span data-ttu-id="41564-205">"256"</span><span class="sxs-lookup"><span data-stu-id="41564-205">"256"</span></span>|  
|<span data-ttu-id="41564-206">SQLCMDMAXFIXEDTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="41564-206">SQLCMDMAXFIXEDTYPEWIDTH</span></span>|<span data-ttu-id="41564-207">-y</span><span class="sxs-lookup"><span data-stu-id="41564-207">-Y</span></span>|<span data-ttu-id="41564-208">R/W</span><span class="sxs-lookup"><span data-stu-id="41564-208">R/W</span></span>|<span data-ttu-id="41564-209">"0" = ilimitado</span><span class="sxs-lookup"><span data-stu-id="41564-209">"0" = unlimited</span></span>|  
|<span data-ttu-id="41564-210">SQLCMDEDITOR</span><span class="sxs-lookup"><span data-stu-id="41564-210">SQLCMDEDITOR</span></span>||<span data-ttu-id="41564-211">R/W</span><span class="sxs-lookup"><span data-stu-id="41564-211">R/W</span></span>|<span data-ttu-id="41564-212">"edit.com"</span><span class="sxs-lookup"><span data-stu-id="41564-212">"edit.com"</span></span>|  
|<span data-ttu-id="41564-213">SQLCMDINI</span><span class="sxs-lookup"><span data-stu-id="41564-213">SQLCMDINI</span></span>||<span data-ttu-id="41564-214">R</span><span class="sxs-lookup"><span data-stu-id="41564-214">R</span></span>|<span data-ttu-id="41564-215">""</span><span class="sxs-lookup"><span data-stu-id="41564-215">""</span></span>|  
  
 <span data-ttu-id="41564-216">\*SQLCMDUSER, SQLCMDPASSWORD e SQLCMDSERVER são definidos quando **: Connect** é usado.</span><span class="sxs-lookup"><span data-stu-id="41564-216">\* SQLCMDUSER, SQLCMDPASSWORD and SQLCMDSERVER are set when **:Connect** is used.</span></span>  
  
 <span data-ttu-id="41564-217">R indica que o valor pode ser definido apenas uma vez durante a inicialização do programa.</span><span class="sxs-lookup"><span data-stu-id="41564-217">R indicates the value can only be set one time during program initialization.</span></span>  
  
 <span data-ttu-id="41564-218">R/W indica que o valor pode ser redefinido usando o comando **setvar** e que comandos subsequentes usarão o novo valor.</span><span class="sxs-lookup"><span data-stu-id="41564-218">R/W indicates that the value can be reset by using the **setvar** command and subsequent commands will use the new value.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="41564-219">Exemplos</span><span class="sxs-lookup"><span data-stu-id="41564-219">Examples</span></span>  
  
### <a name="a-using-the-setvar-command-in-a-script"></a><span data-ttu-id="41564-220">a.</span><span class="sxs-lookup"><span data-stu-id="41564-220">A.</span></span> <span data-ttu-id="41564-221">Usando o comando setvar em um script</span><span class="sxs-lookup"><span data-stu-id="41564-221">Using the setvar command in a script</span></span>  
 <span data-ttu-id="41564-222">Muitas opções do **sqlcmd** podem ser controladas em um script usando o comando **setvar** .</span><span class="sxs-lookup"><span data-stu-id="41564-222">Many **sqlcmd** options can be controlled in a script by using the **setvar** command.</span></span> <span data-ttu-id="41564-223">No exemplo a seguir, o script `test.sql` é criado e nele a variável `SQLCMDLOGINTIMEOUT` é definida como `60` segundos e outra variável de script, `server`, é definida como `testserver`.</span><span class="sxs-lookup"><span data-stu-id="41564-223">In the following example, the script `test.sql` is created in which the `SQLCMDLOGINTIMEOUT` variable is set to `60` seconds and another scripting variable, `server`, is set to `testserver`.</span></span> <span data-ttu-id="41564-224">O código a seguir está em `test.sql`.</span><span class="sxs-lookup"><span data-stu-id="41564-224">The following code is in `test.sql`.</span></span>  
  
 `:setvar SQLCMDLOGINTIMEOUT 60`  
  
 `:setvar server "testserver"`  
  
 `:connect $(server) -l $(SQLCMDLOGINTIMEOUT)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `The script is then called by using sqlcmd:`  
  
 `sqlcmd -i c:\test.sql`  
  
### <a name="b-using-the-setvar-command-interactively"></a><span data-ttu-id="41564-225">B.</span><span class="sxs-lookup"><span data-stu-id="41564-225">B.</span></span> <span data-ttu-id="41564-226">Usando interativamente o comando setvar</span><span class="sxs-lookup"><span data-stu-id="41564-226">Using the setvar command interactively</span></span>  
 <span data-ttu-id="41564-227">O exemplo a seguir mostra como definir interativamente uma variável de script usando o comando `setvar` .</span><span class="sxs-lookup"><span data-stu-id="41564-227">The following example shows how to set a scripting variable interactively by using the `setvar` command.</span></span>  
  
 `sqlcmd`  
  
 `:setvar  MYDATABASE AdventureWorks2012`  
  
 `USE $(MYDATABASE);`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Changed database context to 'AdventureWorks2012'`  
  
 `1>`  
  
### <a name="c-using-command-prompt-environment-variables-within-sqlcmd"></a><span data-ttu-id="41564-228">C.</span><span class="sxs-lookup"><span data-stu-id="41564-228">C.</span></span> <span data-ttu-id="41564-229">Usando variáveis de ambiente de prompt de comando no sqlcmd</span><span class="sxs-lookup"><span data-stu-id="41564-229">Using command prompt environment variables within sqlcmd</span></span>  
 <span data-ttu-id="41564-230">No exemplo a seguir, quatro variáveis de ambiente `are` são definidas e depois chamadas a partir do `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="41564-230">In the following example, four environment variables `are` set and then called from `sqlcmd`.</span></span>  
  
 `C:\>SET tablename=Person.Person`  
  
 `C:\>SET col1=FirstName`  
  
 `C:\>SET col2=LastName`  
  
 `C:\>SET title=Ms.`  
  
 `C:\>sqlcmd -d AdventureWorks2012`  
  
 `1> SELECT TOP 5 $(col1) + ' ' + $(col2) AS Name`  
  
 `2> FROM $(tablename)`  
  
 `3> WHERE Title ='$(title)'`  
  
 `4> GO`  
  
### <a name="d-using-user-level-environment-variables-within-sqlcmd"></a><span data-ttu-id="41564-231">D.</span><span class="sxs-lookup"><span data-stu-id="41564-231">D.</span></span> <span data-ttu-id="41564-232">Usando variáveis de ambiente em nível de usuário no sqlcmd</span><span class="sxs-lookup"><span data-stu-id="41564-232">Using user-level environment variables within sqlcmd</span></span>  
 <span data-ttu-id="41564-233">No exemplo a seguir, a variável de ambiente de nível de usuário `%Temp%` está definida no prompt de comando e foi passada para o arquivo de entrada do `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="41564-233">In the following example the user-level environmental variable `%Temp%` is set at the command prompt and passed to the `sqlcmd` input file.</span></span> <span data-ttu-id="41564-234">Para obter a variável de ambiente de nível de usuário: em **Painel de Controle**, clique duas vezes em **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="41564-234">To obtain the user-level environment variable, in **Control Panel**, double-click **System**.</span></span> <span data-ttu-id="41564-235">Clique na guia **Avançado** e em **Variáveis de Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="41564-235">Click the **Advance** tab, and then click **Environment Variables**.</span></span>  
  
 <span data-ttu-id="41564-236">O código a seguir está no arquivo de entrada `c:\testscript.txt`:</span><span class="sxs-lookup"><span data-stu-id="41564-236">The following code is in the input file `c:\testscript.txt`:</span></span>  
  
 `:OUT $(MyTempDirectory)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName`  
  
 `FROM AdventureWorks2012.Person.Person`  
  
 <span data-ttu-id="41564-237">`WHERE BusinessEntityID` `< 5;`</span><span class="sxs-lookup"><span data-stu-id="41564-237">`WHERE BusinessEntityID` `< 5;`</span></span>  
  
 <span data-ttu-id="41564-238">O código a seguir é inserido no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="41564-238">This following code is entered at the command prompt:</span></span>  
  
 `C:\ >SET MyTempDirectory=%Temp%\output.txt`  
  
 `C:\ >sqlcmd -i C:\testscript.txt`  
  
 <span data-ttu-id="41564-239">O resultado a seguir é enviado ao arquivo de saída C:\Documents and Settings\\<user\>\Local Settings\Temp\output.txt.</span><span class="sxs-lookup"><span data-stu-id="41564-239">The following result is sent to the output file C:\Documents and Settings\\<user\>\Local Settings\Temp\output.txt.</span></span>  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `FirstName`  
  
 `--------------------------------------------------`  
  
 `Gustavo`  
  
 `Catherine`  
  
 `Kim`  
  
 `Humberto`  
  
 `(4 rows affected)`  
  
### <a name="e-using-a-startup-script"></a><span data-ttu-id="41564-240">E.</span><span class="sxs-lookup"><span data-stu-id="41564-240">E.</span></span> <span data-ttu-id="41564-241">Usando um script de inicialização</span><span class="sxs-lookup"><span data-stu-id="41564-241">Using a startup script</span></span>  
 <span data-ttu-id="41564-242">Um script de inicialização **sqlcmd** é executado quando **sqlcmd** é iniciado.</span><span class="sxs-lookup"><span data-stu-id="41564-242">A **sqlcmd** startup script is executed when **sqlcmd** is started.</span></span> <span data-ttu-id="41564-243">O exemplo a seguir define a variável de ambiente de `SQLCMDINI`.</span><span class="sxs-lookup"><span data-stu-id="41564-243">The following example sets the environment variable `SQLCMDINI`.</span></span> <span data-ttu-id="41564-244">Este é o conteúdo de `init.sql.`</span><span class="sxs-lookup"><span data-stu-id="41564-244">This is the contents of `init.sql.`</span></span>  
  
 `SET NOCOUNT ON`  
  
 `GO`  
  
 `DECLARE @nt_username nvarchar(128)`  
  
 `SET @nt_username = (SELECT rtrim(convert(nvarchar(128), nt_username))`  
  
 `FROM sys.dm_exec_sessions WHERE spid = @@SPID)`  
  
 `SELECT  @nt_username + ' is connected to ' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('servername'))) +`  
  
 `' (' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('productversion'))) +`  
  
 `')'`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH 100`  
  
 `SET NOCOUNT OFF`  
  
 `GO`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH`  
  
 <span data-ttu-id="41564-245">Isto chama o arquivo `init.sql` quando o `sqlcmd` é iniciado.</span><span class="sxs-lookup"><span data-stu-id="41564-245">This calls the `init.sql` file when `sqlcmd` is started.</span></span>  
  
 `C:\> SET sqlcmdini=c:\init.sql`  
  
 `>1 Sqlcmd`  
  
 <span data-ttu-id="41564-246">Esta é a saída.</span><span class="sxs-lookup"><span data-stu-id="41564-246">This is the output.</span></span>  
  
 `>1 < user > is connected to < server > (9.00.2047.00)`  
  
> [!NOTE]  
>  <span data-ttu-id="41564-247">A opção **-X** desabilita o recurso de script de inicialização.</span><span class="sxs-lookup"><span data-stu-id="41564-247">The **-X** option disables the startup script feature.</span></span>  
  
### <a name="f-variable-expansion"></a><span data-ttu-id="41564-248">F.</span><span class="sxs-lookup"><span data-stu-id="41564-248">F.</span></span> <span data-ttu-id="41564-249">Expansão de variável</span><span class="sxs-lookup"><span data-stu-id="41564-249">Variable expansion</span></span>  
 <span data-ttu-id="41564-250">O exemplo a seguir mostra o trabalho com dados no formato de uma variável **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="41564-250">The following example shows working with data in the form of a **sqlcmd** variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `CREATE TABLE AdventureWorks2012.dbo.VariableTest`  
  
 `(`  
  
 `Col1 nvarchar(50)`  
  
 `);`  
  
 `GO`  
  
 <span data-ttu-id="41564-251">Insira uma linha em `Col1` de `dbo.VariableTest` que contém o valor `$(tablename)`.</span><span class="sxs-lookup"><span data-stu-id="41564-251">Insert one row into `Col1` of `dbo.VariableTest` that contains the value `$(tablename)`.</span></span>  
  
 `INSERT INTO AdventureWorks2012.dbo.VariableTest(Col1)`  
  
 `VALUES('$(tablename)');`  
  
 `GO`  
  
 <span data-ttu-id="41564-252">No prompt do `sqlcmd` , quando nenhuma variável for definida igual a `$(tablename)`, as instruções a seguir retornarão a linha.</span><span class="sxs-lookup"><span data-stu-id="41564-252">At the `sqlcmd` prompt, when no variable is set equal to `$(tablename)`, the following statements return the row.</span></span>  
  
 `C:\> sqlcmd`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>2 GO`  
  
 `>3 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>4 GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `>1 Col1`  
  
 `>2 ------------------`  
  
 `>3 $(tablename)`  
  
 `>4`  
  
 `>5 (1 rows affected)`  
  
 <span data-ttu-id="41564-253">Dado que a variável `MyVar` foi definida como `$(tablename)`.</span><span class="sxs-lookup"><span data-stu-id="41564-253">Given the variable `MyVar` is set to `$(tablename)`.</span></span>  
  
 `>6 :setvar MyVar $(tablename)`  
  
 <span data-ttu-id="41564-254">Estas instruções retornam a linha e também a mensagem "variável de script 'tablename' não definida".</span><span class="sxs-lookup"><span data-stu-id="41564-254">These statements return the row and also return the message "'tablename' scripting variable not defined."</span></span>  
  
 `>6 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>7 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>2 GO`  
  
 <span data-ttu-id="41564-255">Estas instruções retornam a linha.</span><span class="sxs-lookup"><span data-stu-id="41564-255">These statements return the row.</span></span>  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(MyVar)';`  
  
 `>2 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(MyVar)';`  
  
 `>2 GO`  
  
## <a name="see-also"></a><span data-ttu-id="41564-256">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="41564-256">See Also</span></span>  
 <span data-ttu-id="41564-257">[Usar o utilitário sqlcmd](sqlcmd-use-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="41564-257">[Use the sqlcmd Utility](sqlcmd-use-the-utility.md) </span></span>  
 <span data-ttu-id="41564-258">[Utilitário sqlcmd](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="41564-258">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 [<span data-ttu-id="41564-259">Referência de utilitários de prompt de comando &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="41564-259">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](../../tools/command-prompt-utility-reference-database-engine.md)  
  
  
