---
title: Utilitário RS.exe (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- automatic report server tasks
- rs utility
- command prompt utilities [Reporting Services]
- report servers [Reporting Services], automating tasks
- command prompt utilities [SQL Server], rs
- scripts [Reporting Services], command prompt
- deploying reports [Reporting Services]
ms.assetid: bd6f958f-cce6-4e79-8a0f-9475da2919ce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bcf21a1bf2453d2bd1f0644e31ca46f3f94e6884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683378"
---
# <a name="rsexe-utility-ssrs"></a><span data-ttu-id="b8c27-102">RS.exe Utility (SSRS)</span><span class="sxs-lookup"><span data-stu-id="b8c27-102">RS.exe Utility (SSRS)</span></span>
  <span data-ttu-id="b8c27-103">O utilitário rs.exe processa o script que você fornece em um arquivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="b8c27-103">The rs.exe utility processes script that you provide in an input file.</span></span> <span data-ttu-id="b8c27-104">Use esse utilitário para automatizar a implantação de servidor de relatório e tarefas de administração.</span><span class="sxs-lookup"><span data-stu-id="b8c27-104">Use this utility to automate report server deployment and administration tasks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8c27-105">A partir do [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], o utilitário **rs** tem suporte nos servidores de relatório configurados para o modo integrado do SharePoint e em servidores configurados no modo nativo.</span><span class="sxs-lookup"><span data-stu-id="b8c27-105">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], the **rs** utility is supported against report servers that are configured for SharePoint integrated mode as well as servers configured in native mode.</span></span> <span data-ttu-id="b8c27-106">As versões anteriores suportavam apenas configurações em modo nativo.</span><span class="sxs-lookup"><span data-stu-id="b8c27-106">Previous versions only supported native mode configurations.</span></span>  
  
 <span data-ttu-id="b8c27-107">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="b8c27-107">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="b8c27-108">Local do arquivo</span><span class="sxs-lookup"><span data-stu-id="b8c27-108">File Location</span></span>](#bkmk_filelocation)  
  
-   [<span data-ttu-id="b8c27-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8c27-109">Arguments</span></span>](#bkmk_arguments)  
  
-   [<span data-ttu-id="b8c27-110">Permissões</span><span class="sxs-lookup"><span data-stu-id="b8c27-110">Permissions</span></span>](#bkmk_permissions)  
  
-   [<span data-ttu-id="b8c27-111">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b8c27-111">Examples</span></span>](#bkmk_examples)  
  
## <a name="syntax"></a><span data-ttu-id="b8c27-112">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b8c27-112">Syntax</span></span>  
  
```  
  
      rs {-?}  
{-i input_file=}  
{-s serverURL}  
{-u username}  
{-p password}  
{-e endpoint}  
{-l time_out}  
{-b batchmode}  
{-v globalvars=}  
{-t trace}  
```  
  
##  <a name="file-location"></a><a name="bkmk_filelocation"></a> <span data-ttu-id="b8c27-113">Local do arquivo</span><span class="sxs-lookup"><span data-stu-id="b8c27-113">File Location</span></span>  
 <span data-ttu-id="b8c27-114">**RS.exe** está localizado em **\Arquivos de Programas\Microsoft SQL Server\110\Tools\Binn**.</span><span class="sxs-lookup"><span data-stu-id="b8c27-114">**RS.exe** is located at **\Program Files\Microsoft SQL Server\110\Tools\Binn**.</span></span> <span data-ttu-id="b8c27-115">Você pode executar o utilitário de qualquer pasta em seu sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b8c27-115">You can run the utility from any folder on your file system.</span></span>  
  
##  <a name="arguments"></a><a name="bkmk_arguments"></a> <span data-ttu-id="b8c27-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8c27-116">Arguments</span></span>  
 <span data-ttu-id="b8c27-117">**-?**</span><span class="sxs-lookup"><span data-stu-id="b8c27-117">**-?**</span></span>  
 <span data-ttu-id="b8c27-118">(Opcional) Exibe a sintaxe de argumentos **rs** .</span><span class="sxs-lookup"><span data-stu-id="b8c27-118">(Optional) Displays the syntax of **rs** arguments.</span></span>  
  
 <span data-ttu-id="b8c27-119">`-i`*input_file*</span><span class="sxs-lookup"><span data-stu-id="b8c27-119">`-i` *input_file*</span></span>  
 <span data-ttu-id="b8c27-120">(Obrigatório) Especifica o arquivo .rss a ser executado.</span><span class="sxs-lookup"><span data-stu-id="b8c27-120">(Required) Specifies the .rss file to execute.</span></span> <span data-ttu-id="b8c27-121">Esse valor pode ser um parente ou caminho totalmente qualificado para o arquivo .rss.</span><span class="sxs-lookup"><span data-stu-id="b8c27-121">This value can be a relative or fully qualified path to the .rss file.</span></span>  
  
 <span data-ttu-id="b8c27-122">`-s`*ServerURL*</span><span class="sxs-lookup"><span data-stu-id="b8c27-122">`-s` *serverURL*</span></span>  
 <span data-ttu-id="b8c27-123">(Obrigatório) Especifica o nome do servidor Web e nome do diretório virtual do servidor de relatório no qual executar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b8c27-123">(Required) Specifies the Web server name and report server virtual directory name to execute the file against.</span></span> <span data-ttu-id="b8c27-124">Um exemplo de uma URL de servidor de relatório é `http://examplewebserver/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="b8c27-124">An example of a report server URL is `http://examplewebserver/reportserver`.</span></span> <span data-ttu-id="b8c27-125">O prefixo http:// ou https:// no início do nome do servidor é opcional.</span><span class="sxs-lookup"><span data-stu-id="b8c27-125">The prefix http:// or https:// at the beginning of the server name is optional.</span></span> <span data-ttu-id="b8c27-126">Se você omitir o prefixo, o host de script do servidor de relatório tentará usar https primeiro e depois usará http se https não funcionar.</span><span class="sxs-lookup"><span data-stu-id="b8c27-126">If you omit the prefix, the report server script host tries to use https first, and then uses http if https does not work.</span></span>  
  
 <span data-ttu-id="b8c27-127">`-u`[*domínio* \\ ] *nome de usuário*</span><span class="sxs-lookup"><span data-stu-id="b8c27-127">`-u` [*domain*\\]*username*</span></span>  
 <span data-ttu-id="b8c27-128">(Opcional) Especifica uma conta do usuário usada para conexão com o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="b8c27-128">(Optional) Specifies a user account used to connect to the report server.</span></span> <span data-ttu-id="b8c27-129">Se `-u` e `-p` forem omitidos, a conta do usuário do Windows atual será usada.</span><span class="sxs-lookup"><span data-stu-id="b8c27-129">If `-u` and `-p` are omitted, the current Windows user account is used.</span></span>  
  
 <span data-ttu-id="b8c27-130">`-p`*senha* do</span><span class="sxs-lookup"><span data-stu-id="b8c27-130">`-p` *password*</span></span>  
 <span data-ttu-id="b8c27-131">(Obrigatório se `-u` for especificado). Especifica a senha para usar com o argumento `-u`.</span><span class="sxs-lookup"><span data-stu-id="b8c27-131">(Required if `-u` is specified) Specifies the password to use with the `-u` argument.</span></span> <span data-ttu-id="b8c27-132">Esse valor diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b8c27-132">This value is case-sensitive.</span></span>  
  
 `-e`  
 <span data-ttu-id="b8c27-133">(Opcional) Especifica o ponto de extremidade SOAP no qual o script deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="b8c27-133">(Optional) Specifies the SOAP endpoint against which the script should run.</span></span> <span data-ttu-id="b8c27-134">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="b8c27-134">Valid values are the following:</span></span>  
  
-   <span data-ttu-id="b8c27-135">Mgmt2010</span><span class="sxs-lookup"><span data-stu-id="b8c27-135">Mgmt2010</span></span>  
  
-   <span data-ttu-id="b8c27-136">Mgmt2006</span><span class="sxs-lookup"><span data-stu-id="b8c27-136">Mgmt2006</span></span>  
  
-   <span data-ttu-id="b8c27-137">Mgmt2005</span><span class="sxs-lookup"><span data-stu-id="b8c27-137">Mgmt2005</span></span>  
  
-   <span data-ttu-id="b8c27-138">Exec2005</span><span class="sxs-lookup"><span data-stu-id="b8c27-138">Exec2005</span></span>  
  
 <span data-ttu-id="b8c27-139">Se não for especificado um valor, o ponto de extremidade Mgmt2005 será usado.</span><span class="sxs-lookup"><span data-stu-id="b8c27-139">If a value is not specified, the Mgmt2005 endpoint is used.</span></span> <span data-ttu-id="b8c27-140">Para obter mais informações sobre pontos de extremidade de SOAP, consulte [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="b8c27-140">For more information about the SOAP endpoints, see [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span></span>  
  
 <span data-ttu-id="b8c27-141">`-l`*time_out*</span><span class="sxs-lookup"><span data-stu-id="b8c27-141">`-l` *time_out*</span></span>  
 <span data-ttu-id="b8c27-142">Adicional Especifica o número de segundos decorridos antes que a conexão com o servidor expire. O padrão é 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="b8c27-142">(Optional) Specifies the number of seconds that elapse before the connection to the server times out. The default is 60 seconds.</span></span> <span data-ttu-id="b8c27-143">Se você não especificar um valor de tempo limite, o padrão será usado.</span><span class="sxs-lookup"><span data-stu-id="b8c27-143">If you do not specify a time-out value, the default is used.</span></span> <span data-ttu-id="b8c27-144">Um valor de `0` especifica que a conexão nunca expira.</span><span class="sxs-lookup"><span data-stu-id="b8c27-144">A value of `0` specifies that the connection never times out.</span></span>  
  
 <span data-ttu-id="b8c27-145">**-b**</span><span class="sxs-lookup"><span data-stu-id="b8c27-145">**-b**</span></span>  
 <span data-ttu-id="b8c27-146">(Opcional) Especifica que os comandos no arquivo de script são executados em um lote.</span><span class="sxs-lookup"><span data-stu-id="b8c27-146">(Optional) Specifies that the commands in the script file run in a batch.</span></span> <span data-ttu-id="b8c27-147">Se algum comando falhar, o lote será revertido.</span><span class="sxs-lookup"><span data-stu-id="b8c27-147">If any commands fail, the batch is rolled back.</span></span> <span data-ttu-id="b8c27-148">Alguns comandos não podem ser processados em lote e são executados como de costume.</span><span class="sxs-lookup"><span data-stu-id="b8c27-148">Some commands cannot be batched, and those run as usual.</span></span> <span data-ttu-id="b8c27-149">Somente exceções emitidas e não controladas no resultado de script resultam em reversão.</span><span class="sxs-lookup"><span data-stu-id="b8c27-149">Only exceptions that are thrown and are not handled within the script result in a rollback.</span></span> <span data-ttu-id="b8c27-150">Se o script controlar uma exceção e retornar normalmente de `Main`, o lote será confirmado.</span><span class="sxs-lookup"><span data-stu-id="b8c27-150">If the script handles an exception and returns normally from `Main`, the batch is committed.</span></span> <span data-ttu-id="b8c27-151">Se você omitir esse parâmetro, os comandos serão executados sem criar um lote.</span><span class="sxs-lookup"><span data-stu-id="b8c27-151">If you omit this parameter, the commands run without creating a batch.</span></span> <span data-ttu-id="b8c27-152">Para obter mais informações, consulte [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span><span class="sxs-lookup"><span data-stu-id="b8c27-152">For more information, see [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span></span>  
  
 <span data-ttu-id="b8c27-153">`-v`*globalvar*</span><span class="sxs-lookup"><span data-stu-id="b8c27-153">`-v` *globalvar*</span></span>  
 <span data-ttu-id="b8c27-154">(Opcional) Especifica variáveis globais usadas no script.</span><span class="sxs-lookup"><span data-stu-id="b8c27-154">(Optional) Specifies global variables that are used in the script.</span></span> <span data-ttu-id="b8c27-155">Se o script usa variáveis globais, você deve especificar esse argumento.</span><span class="sxs-lookup"><span data-stu-id="b8c27-155">If the script uses global variables, you must specify this argument.</span></span> <span data-ttu-id="b8c27-156">O valor que você especifica deve ser válido para a variável global definida no arquivo .rss.</span><span class="sxs-lookup"><span data-stu-id="b8c27-156">The value that you specify must be valid for global variable defined in the .rss file.</span></span> <span data-ttu-id="b8c27-157">Você deve especificar uma variável global para o argumento **de cada-v** .</span><span class="sxs-lookup"><span data-stu-id="b8c27-157">You must specify one global variable for each **-v** argument.</span></span>  
  
 <span data-ttu-id="b8c27-158">O argumento `-v` é especificado na linha de comando e é usado para definir o valor de uma variável global definida no seu script em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="b8c27-158">The `-v` argument is specified on the command line and is used to set the value for a global variable that is defined in your script at run time.</span></span> <span data-ttu-id="b8c27-159">Por exemplo, se seu script contiver uma variável nomeada *parentFolder*, você poderá especificar um nome para aquela pasta na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="b8c27-159">For example, if your script contains a variable named *parentFolder*, you can specify a name for that folder on the command line:</span></span>  
  
 `rs.exe -i myScriptFile.rss -s http://myServer/reportserver -v parentFolder="Financial Reports"`  
  
 <span data-ttu-id="b8c27-160">Variáveis globais são criadas com os nomes dados e definidos para os valores fornecidos.</span><span class="sxs-lookup"><span data-stu-id="b8c27-160">Global variables are created with the names given and set to the values supplied.</span></span> <span data-ttu-id="b8c27-161">Por exemplo, **-v a =**" `1` " **-v b =**" `2` " resulta em uma variável chamada `a` com um valor de " `1` " e uma variável **b** com um valor de " `2` ".</span><span class="sxs-lookup"><span data-stu-id="b8c27-161">For example, **-v a=**"`1`" **-v b=**"`2`" results in a variable named `a` with a value of"`1`" and a variable **b** with a value of "`2`".</span></span>  
  
 <span data-ttu-id="b8c27-162">Variáveis globais estão disponíveis para qualquer função no script.</span><span class="sxs-lookup"><span data-stu-id="b8c27-162">Global variables are available to any function in the script.</span></span> <span data-ttu-id="b8c27-163">Uma barra invertida e uma aspa (\*\* \\ "\*\*) são interpretadas como aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="b8c27-163">A backslash and quotation mark (**\\"**) is interpreted as a double quotation mark.</span></span> <span data-ttu-id="b8c27-164">As aspas só serão necessárias se a cadeia de caracteres contiver um espaço.</span><span class="sxs-lookup"><span data-stu-id="b8c27-164">The quotation marks are required only if the string contains a space.</span></span> <span data-ttu-id="b8c27-165">Os nomes de variáveis devem ser válidos para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ; eles devem começar com caracteres alfabéticos ou sublinhados e conter caracteres alfabéticos, dígitos ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="b8c27-165">Variable names must be valid for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]; they must start with alphabetical character or underscore and contain alphabetical characters, digits, or underscores.</span></span> <span data-ttu-id="b8c27-166">Palavras reservadas não podem ser usadas como nomes de variável.</span><span class="sxs-lookup"><span data-stu-id="b8c27-166">Reserved words cannot be used as variable names.</span></span> <span data-ttu-id="b8c27-167">Para obter mais informações sobre como usar variáveis globais, consulte [Coleções internas em expressões &#40;Construtor de Relatórios e SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b8c27-167">For more information about using global variables, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
 <span data-ttu-id="b8c27-168">**-t**</span><span class="sxs-lookup"><span data-stu-id="b8c27-168">**-t**</span></span>  
 <span data-ttu-id="b8c27-169">(Opcional) Produz mensagens de erro para o log de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="b8c27-169">(Optional) Outputs error messages to the trace log.</span></span> <span data-ttu-id="b8c27-170">Esse argumento não exige um valor.</span><span class="sxs-lookup"><span data-stu-id="b8c27-170">This argument does not take a value.</span></span> <span data-ttu-id="b8c27-171">Para obter mais informações, consulte [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="b8c27-171">For more information, see [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span></span>  
  
##  <a name="permissions"></a><a name="bkmk_permissions"></a> <span data-ttu-id="b8c27-172">Permissões</span><span class="sxs-lookup"><span data-stu-id="b8c27-172">Permissions</span></span>  
 <span data-ttu-id="b8c27-173">Para executar essa ferramenta, você deve ter permissão para se conectar à instância do servidor de relatório no qual o script está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="b8c27-173">To run the tool, you must have permission to connect to the report server instance you are running the script against.</span></span> <span data-ttu-id="b8c27-174">Você pode executar scripts para fazer alterações no computador local ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="b8c27-174">You can run scripts to make changes to the local computer or a remote computer.</span></span> <span data-ttu-id="b8c27-175">Para fazer alterações em um servidor de relatório instalado em um computador remoto, especifique o computador remoto no argumento `-s`.</span><span class="sxs-lookup"><span data-stu-id="b8c27-175">To make changes to a report server installed on a remote computer, specify the remote computer in the `-s` argument.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="b8c27-176">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b8c27-176">Examples</span></span>  
 <span data-ttu-id="b8c27-177">O exemplo a seguir ilustra como especificar o arquivo de script que contém o script [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET e os métodos do serviço Web que você quer executar.</span><span class="sxs-lookup"><span data-stu-id="b8c27-177">The following example illustrates how to specify the script file that contains [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET script and Web service methods that you want to execute.</span></span>  
  
```  
rs -i c:\scriptfiles\script_copycontent.rss -s http://localhost/reportserver  
```  
  
 <span data-ttu-id="b8c27-178"> Para obter um exemplo detalhado, consulte [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="b8c27-178">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
 <span data-ttu-id="b8c27-179">Para ver exemplos adicionais, consulte [Executar um arquivo de script do Reporting Services](run-a-reporting-services-script-file.md)</span><span class="sxs-lookup"><span data-stu-id="b8c27-179">For additional examples, see [Run a Reporting Services Script File](run-a-reporting-services-script-file.md)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8c27-180">Comentários</span><span class="sxs-lookup"><span data-stu-id="b8c27-180">Remarks</span></span>  
 <span data-ttu-id="b8c27-181">Você pode definir scripts para definir propriedades do sistema, publicar relatórios, e assim sucessivamente.</span><span class="sxs-lookup"><span data-stu-id="b8c27-181">You can define scripts to set system properties, publish reports, and so forth.</span></span> <span data-ttu-id="b8c27-182">Os scripts que você cria podem incluir qualquer método de API do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8c27-182">The scripts that you create can include any methods of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="b8c27-183">Para obter mais informações sobre os métodos e propriedades disponíveis, consulte [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="b8c27-183">For more information about the methods and properties available to you, see [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span></span>  
  
 <span data-ttu-id="b8c27-184">O script deve ser gravado no código [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET e armazenado em Unicode ou arquivo de texto UTF-8 com uma extensão de nome de arquivo .rss.</span><span class="sxs-lookup"><span data-stu-id="b8c27-184">The script must be written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET code, and stored in a Unicode or UTF-8 text file with an .rss file name extension.</span></span> <span data-ttu-id="b8c27-185">Você não pode depurar scripts com o utilitário **rs** .</span><span class="sxs-lookup"><span data-stu-id="b8c27-185">You cannot debug scripts with the **rs** utility.</span></span> <span data-ttu-id="b8c27-186">Para depurar um script, execute o código no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8c27-186">To debug a script, run the code within [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="b8c27-187"> Para obter um exemplo detalhado, consulte [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="b8c27-187">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8c27-188">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b8c27-188">See Also</span></span>  
 <span data-ttu-id="b8c27-189">[Executar um arquivo de script Reporting Services](run-a-reporting-services-script-file.md) </span><span class="sxs-lookup"><span data-stu-id="b8c27-189">[Run a Reporting Services Script File](run-a-reporting-services-script-file.md) </span></span>  
 <span data-ttu-id="b8c27-190">[Implantação de script e tarefas administrativas](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b8c27-190">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 <span data-ttu-id="b8c27-191">[Script com o utilitário rs.exe e o serviço Web](script-with-the-rs-exe-utility-and-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="b8c27-191">[Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md) </span></span>  
 [<span data-ttu-id="b8c27-192">Utilitários de prompt de comando do servidor de relatório &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b8c27-192">Report Server Command Prompt Utilities &#40;SSRS&#41;</span></span>](report-server-command-prompt-utilities-ssrs.md)  
  
  
