---
title: Utilitário do criador de perfil | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- command prompt utilities [SQL Server], profiler90 utility
- profiler90 utility
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: e91c30a9-0d29-4f84-bcb8-e8fb62afadda
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8df3e8557bb52839d17291bae0c5ba507d0a671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678421"
---
# <a name="profiler-utility"></a><span data-ttu-id="60503-102">Utilitário Profiler</span><span class="sxs-lookup"><span data-stu-id="60503-102">Profiler Utility</span></span>
  <span data-ttu-id="60503-103">O utilitário **profiler** inicia a ferramenta [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60503-103">The **profiler** utility launches the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] tool.</span></span> <span data-ttu-id="60503-104">Os argumentos opcionais listados posteriormente neste tópico permitem controlar como o aplicativo é iniciado.</span><span class="sxs-lookup"><span data-stu-id="60503-104">The optional arguments listed later in this topic allow you to control how the application starts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="60503-105">O utilitário **profiler** não foi criado para ser usado para rastreamentos de script.</span><span class="sxs-lookup"><span data-stu-id="60503-105">The **profiler** utility is not intended for scripting traces.</span></span> <span data-ttu-id="60503-106">Para saber mais, confira [SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="60503-106">For more information, see [SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60503-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="60503-107">Syntax</span></span>  
  
```  
  
      profiler  
          [ /? ] |  
[  
{  
{ /U login_id [ /P password ] }  
| /E  
}  
{[ /S sql_server_name ] | [ /A analysis_services_server_name ] }  
[ /D database ]  
[ /T "template_name" ]  
[ /B { "trace_table_name" } ]  
{ [/F "filename" ] | [ /O "filename" ] }  
[ /L locale_ID ]  
[ /M "MM-DD-YY hh:mm:ss" ]  
[ /R ]  
[ /Z file_size ]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="60503-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="60503-108">Arguments</span></span>  
 <span data-ttu-id="60503-109">**/?**</span><span class="sxs-lookup"><span data-stu-id="60503-109">**/?**</span></span>  
 <span data-ttu-id="60503-110">Exibe o resumo da sintaxe dos argumentos de **profiler** .</span><span class="sxs-lookup"><span data-stu-id="60503-110">Displays the syntax summary of **profiler** arguments.</span></span>  
  
 <span data-ttu-id="60503-111">**/U** *id_de_login*</span><span class="sxs-lookup"><span data-stu-id="60503-111">**/U** *login_id*</span></span>  
 <span data-ttu-id="60503-112">ID de logon do usuário para autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60503-112">Is the user login ID for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="60503-113">IDs de logon diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="60503-113">Login IDs are case sensitive.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]<span data-ttu-id="60503-114">.</span><span class="sxs-lookup"><span data-stu-id="60503-114">.</span></span>  
  
 <span data-ttu-id="60503-115">**/P** *senha*</span><span class="sxs-lookup"><span data-stu-id="60503-115">**/P** *password*</span></span>  
 <span data-ttu-id="60503-116">Especifica uma senha especificada pelo usuário para a autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60503-116">Specifies a user-specified password for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="60503-117">**/E**</span><span class="sxs-lookup"><span data-stu-id="60503-117">**/E**</span></span>  
 <span data-ttu-id="60503-118">Especifica a conexão com a autenticação do Windows com as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="60503-118">Specifies connecting with Windows Authentication with the current user's credentials.</span></span>  
  
 <span data-ttu-id="60503-119">**/S**  *nome_servidor_sql*</span><span class="sxs-lookup"><span data-stu-id="60503-119">**/S**  *sql_server_name*</span></span>  
 <span data-ttu-id="60503-120">Especifica uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60503-120">Specifies an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="60503-121">O Profiler vai se conectar automaticamente ao servidor especificado usando as informações de autenticação especificadas nas opções **/U** e **/P** ou na opção **/E** .</span><span class="sxs-lookup"><span data-stu-id="60503-121">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="60503-122">Para se conectar a uma instância nomeada do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use **/S** *nome_servidor_sql*\\*nome_da_instância*.</span><span class="sxs-lookup"><span data-stu-id="60503-122">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use **/S** *sql_server_name*\\*instance_name*.</span></span>  
  
 <span data-ttu-id="60503-123">**/A**  *nome_do_servidor_de_analysis_services*</span><span class="sxs-lookup"><span data-stu-id="60503-123">**/A**  *analysis_services_server_name*</span></span>  
 <span data-ttu-id="60503-124">Especifica uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="60503-124">Specifies an instance of Analysis Services.</span></span> <span data-ttu-id="60503-125">O Profiler vai se conectar automaticamente ao servidor especificado usando as informações de autenticação especificadas nas opções **/U** e **/P** ou na opção **/E** .</span><span class="sxs-lookup"><span data-stu-id="60503-125">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="60503-126">Para se conectar a uma instância nomeada do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use **/A** *nome_do_servidor_de_analysis_services\nome_da_instância*.</span><span class="sxs-lookup"><span data-stu-id="60503-126">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] use **/A** *analysis_services_server_name\instance_name*.</span></span>  
  
 <span data-ttu-id="60503-127">**/D** *banco_de_dados*</span><span class="sxs-lookup"><span data-stu-id="60503-127">**/D** *database*</span></span>  
 <span data-ttu-id="60503-128">Especifica o nome do banco de dados a ser usado com a conexão.</span><span class="sxs-lookup"><span data-stu-id="60503-128">Specifies the name of the database to be used with the connection.</span></span> <span data-ttu-id="60503-129">Essa opção selecionará o banco de dados padrão para o usuário especificado se nenhum banco de dados for especificado.</span><span class="sxs-lookup"><span data-stu-id="60503-129">This option will select the default database for the specified user if no database is specified.</span></span>  
  
 <span data-ttu-id="60503-130">**/B "** *nome_da_tabela_de_rastreamento* **"**</span><span class="sxs-lookup"><span data-stu-id="60503-130">**/B "** *trace_table_name* **"**</span></span>  
 <span data-ttu-id="60503-131">Especifica uma tabela de rastreamento a ser carregada quando o profiler for iniciado.</span><span class="sxs-lookup"><span data-stu-id="60503-131">Specifies a trace table to load when the profiler is launched.</span></span> <span data-ttu-id="60503-132">Você deve especificar o banco de dados, o usuário ou esquema e a tabela.</span><span class="sxs-lookup"><span data-stu-id="60503-132">You must specify the database, the user or schema, and the table.</span></span>  
  
 <span data-ttu-id="60503-133">**/T "** *nome_do_modelo* **"**</span><span class="sxs-lookup"><span data-stu-id="60503-133">**/T"** *template_name* **"**</span></span>  
 <span data-ttu-id="60503-134">Especifica o modelo que será carregado para configurar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="60503-134">Specifies the template that will be loaded to configure the trace.</span></span> <span data-ttu-id="60503-135">O nome do modelo deve estar entre aspas.</span><span class="sxs-lookup"><span data-stu-id="60503-135">The template name must be in quotes.</span></span> <span data-ttu-id="60503-136">O nome do modelo deve estar no diretório de modelos de sistema ou no diretório de modelos de usuário.</span><span class="sxs-lookup"><span data-stu-id="60503-136">The template name must be in either the system template directory or the user template directory.</span></span> <span data-ttu-id="60503-137">Se existirem dois modelos com mesmo nome em ambos os diretórios, o modelo do diretório do sistema será carregado.</span><span class="sxs-lookup"><span data-stu-id="60503-137">If two templates with the same name exist in both directories, the template from the system directory will be loaded.</span></span> <span data-ttu-id="60503-138">Se nenhum modelo com o nome especificado existir, o modelo padrão será carregado.</span><span class="sxs-lookup"><span data-stu-id="60503-138">If no template with the specified name exists, the standard template will be loaded.</span></span> <span data-ttu-id="60503-139">Observe que a extensão de arquivo do modelo (.tdf) não deve ser especificada como parte do *template_name*.</span><span class="sxs-lookup"><span data-stu-id="60503-139">Note that the file extension for the template (.tdf) should not be specified as part of the *template_name*.</span></span> <span data-ttu-id="60503-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="60503-140">For example:</span></span>  
  
```  
/T "standard"  
```  
  
 <span data-ttu-id="60503-141">**/F"** *nome_do_arquivo* **"**</span><span class="sxs-lookup"><span data-stu-id="60503-141">**/F"** *filename* **"**</span></span>  
 <span data-ttu-id="60503-142">Especifica o caminho e o nome de um arquivo de rastreamento a ser carregado quando o profiler for iniciado.</span><span class="sxs-lookup"><span data-stu-id="60503-142">Specifies the path and filename of a trace file to load when profiler is launched.</span></span> <span data-ttu-id="60503-143">O caminho e o nome de arquivo completos devem estar entre aspas.</span><span class="sxs-lookup"><span data-stu-id="60503-143">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="60503-144">Essa opção não pode ser usada com **/O**.</span><span class="sxs-lookup"><span data-stu-id="60503-144">This option cannot be used with **/O**.</span></span>  
  
 <span data-ttu-id="60503-145">**/O "** *nome_do_arquivo*  **"**</span><span class="sxs-lookup"><span data-stu-id="60503-145">**/O "** *filename*  **"**</span></span>  
 <span data-ttu-id="60503-146">Especifica o caminho e o nome de um arquivo no qual devem ser gravados os resultados de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="60503-146">Specifies the path and filename of a file to which trace results should be written.</span></span> <span data-ttu-id="60503-147">O caminho e o nome de arquivo completos devem estar entre aspas.</span><span class="sxs-lookup"><span data-stu-id="60503-147">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="60503-148">Essa opção não pode ser usada com **/F.**</span><span class="sxs-lookup"><span data-stu-id="60503-148">This option cannot be used with **/F.**</span></span>  
  
 <span data-ttu-id="60503-149">**/L** *ID_do_local*</span><span class="sxs-lookup"><span data-stu-id="60503-149">**/L** *locale_ID*</span></span>  
 <span data-ttu-id="60503-150">Não disponível.</span><span class="sxs-lookup"><span data-stu-id="60503-150">Not available.</span></span>  
  
 <span data-ttu-id="60503-151">**/M "** *MM-DD-AA hh:mm:ss* **"**</span><span class="sxs-lookup"><span data-stu-id="60503-151">**/M "** *MM-DD-YY hh:mm:ss* **"**</span></span>  
 <span data-ttu-id="60503-152">Especifica a data e a hora para o rastreamento parar.</span><span class="sxs-lookup"><span data-stu-id="60503-152">Specifies the date and time for the trace to stop.</span></span> <span data-ttu-id="60503-153">A hora de parada deve estar entre aspas.</span><span class="sxs-lookup"><span data-stu-id="60503-153">The stop time must be in quotes.</span></span> <span data-ttu-id="60503-154">Especifique a hora de parada de acordo com os parâmetros na tabela abaixo:</span><span class="sxs-lookup"><span data-stu-id="60503-154">Specify the stop time according to the parameters in the table below:</span></span>  
  
|<span data-ttu-id="60503-155">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="60503-155">Parameter</span></span>|<span data-ttu-id="60503-156">Definição</span><span class="sxs-lookup"><span data-stu-id="60503-156">Definition</span></span>|  
|---------------|----------------|  
|<span data-ttu-id="60503-157">MM</span><span class="sxs-lookup"><span data-stu-id="60503-157">MM</span></span>|<span data-ttu-id="60503-158">Mês de dois dígitos</span><span class="sxs-lookup"><span data-stu-id="60503-158">Two-digit month</span></span>|  
|<span data-ttu-id="60503-159">DD</span><span class="sxs-lookup"><span data-stu-id="60503-159">DD</span></span>|<span data-ttu-id="60503-160">Dia de dois dígitos</span><span class="sxs-lookup"><span data-stu-id="60503-160">Two-digit day</span></span>|  
|<span data-ttu-id="60503-161">YY</span><span class="sxs-lookup"><span data-stu-id="60503-161">YY</span></span>|<span data-ttu-id="60503-162">Ano de dois dígitos</span><span class="sxs-lookup"><span data-stu-id="60503-162">Two-digit year</span></span>|  
|<span data-ttu-id="60503-163">hh</span><span class="sxs-lookup"><span data-stu-id="60503-163">hh</span></span>|<span data-ttu-id="60503-164">Hora de dois dígitos em um relógio de 24 horas</span><span class="sxs-lookup"><span data-stu-id="60503-164">Two-digit hour on a 24-hour clock</span></span>|  
|<span data-ttu-id="60503-165">MM</span><span class="sxs-lookup"><span data-stu-id="60503-165">mm</span></span>|<span data-ttu-id="60503-166">Minuto de dois dígitos</span><span class="sxs-lookup"><span data-stu-id="60503-166">Two-digit minute</span></span>|  
|<span data-ttu-id="60503-167">ss</span><span class="sxs-lookup"><span data-stu-id="60503-167">ss</span></span>|<span data-ttu-id="60503-168">Segundo de dois dígitos</span><span class="sxs-lookup"><span data-stu-id="60503-168">Two-digit second</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="60503-169">O formato “MM-DD-AA hh:mm:ss” só poderá ser usado se a opção **Usar configurações regionais para exibir valores de data e hora** estiver habilitada no [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60503-169">The "MM-DD-YY hh:mm:ss" format can only be used if the **Use regional settings to display date and time values** option is enabled in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="60503-170">Se essa opção não estiver habilitada, você deverá usar o formato de data e hora "AAAA-MM-DD hh:mm:ss".</span><span class="sxs-lookup"><span data-stu-id="60503-170">If this option is not enabled, you must use the "YYYY-MM-DD hh:mm:ss" date and time format.</span></span>  
  
 <span data-ttu-id="60503-171">**/R**</span><span class="sxs-lookup"><span data-stu-id="60503-171">**/R**</span></span>  
 <span data-ttu-id="60503-172">Habilita a substituição do arquivo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="60503-172">Enables trace file rollover.</span></span>  
  
 <span data-ttu-id="60503-173">**/Z**  *tamanho_do_arquivo*</span><span class="sxs-lookup"><span data-stu-id="60503-173">**/Z**  *file_size*</span></span>  
 <span data-ttu-id="60503-174">Especifica o tamanho do arquivo de rastreamento em megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="60503-174">Specifies the size of the trace file in megabytes (MB).</span></span> <span data-ttu-id="60503-175">O tamanho padrão é 5 MB.</span><span class="sxs-lookup"><span data-stu-id="60503-175">The default size is 5 MB.</span></span> <span data-ttu-id="60503-176">Se a substituição estiver habilitada, todos os arquivos de substituição serão limitados ao valor especificado neste argumento.</span><span class="sxs-lookup"><span data-stu-id="60503-176">If rollover is enabled, all rollover files will be limited to the value specified in this argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60503-177">Comentários</span><span class="sxs-lookup"><span data-stu-id="60503-177">Remarks</span></span>  
 <span data-ttu-id="60503-178">Para iniciar um rastreamento com um modelo específico, use as opções **/S** e **/T** juntas.</span><span class="sxs-lookup"><span data-stu-id="60503-178">To start a trace with a specific template, use the **/S** and **/T** options together.</span></span> <span data-ttu-id="60503-179">Por exemplo, para iniciar um rastreamento usando o modelo Padrão em MyServer\MyInstance, digite o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="60503-179">For example, to start a trace using the Standard template on MyServer\MyInstance, enter the following at the command prompt:</span></span>  
  
```  
profiler /S MyServer\MyInstance /T "Standard"  
```  
  
## <a name="see-also"></a><span data-ttu-id="60503-180">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60503-180">See Also</span></span>  
 [<span data-ttu-id="60503-181">Referência de utilitários de prompt de comando &#40;Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="60503-181">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](command-prompt-utility-reference-database-engine.md)  
  
  
