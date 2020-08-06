---
title: Utilitário sqlmaint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- database maintenance plans [SQL Server]
- sqlmaint utility
- maintaining databases [SQL Server]
- backups [SQL Server], sqlmaint utility
- command prompt utilities [SQL Server], sqlmaint
- maintenance plans [SQL Server], command prompt
- backing up [SQL Server], sqlmaint utility
ms.assetid: 937a9932-4aed-464b-b97a-a5acfe6a50de
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80e60b75305ee91e8b62a201d9c86af301326789
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678383"
---
# <a name="sqlmaint-utility"></a><span data-ttu-id="d05dc-102">utilitário sqlmaint</span><span class="sxs-lookup"><span data-stu-id="d05dc-102">sqlmaint Utility</span></span>
  <span data-ttu-id="d05dc-103">O utilitário**sqlmaint** executa um conjunto especificado de operações de manutenção em um ou mais bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-103">The**sqlmaint** utility performs a specified set of maintenance operations on one or more databases.</span></span> <span data-ttu-id="d05dc-104">Use o **sqlmaint** para executar verificações DBCC, fazer backup de um banco de dados e do respectivo log de transações, atualizar estatísticas e recompilar índices.</span><span class="sxs-lookup"><span data-stu-id="d05dc-104">Use **sqlmaint** to run DBCC checks, back up a database and its transaction log, update statistics, and rebuild indexes.</span></span> <span data-ttu-id="d05dc-105">Todas as atividades de manutenção de banco de dados geram um relatório que pode ser enviado a um arquivo de texto designado, arquivo HTML ou conta de email.</span><span class="sxs-lookup"><span data-stu-id="d05dc-105">All database maintenance activities generate a report that can be sent to a designated text file, HTML file, or e-mail account.</span></span> <span data-ttu-id="d05dc-106">O**sqlmaint** executa planos de manutenção de bancos de dados criados com versões anteriores do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d05dc-106">**sqlmaint** executes database maintenance plans created with previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d05dc-107">Para executar planos de manutenção do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no prompt de comando, use o [Utilitário dtexec](../integration-services/packages/dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="d05dc-107">To run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plans from the command prompt, use the [dtexec Utility](../integration-services/packages/dtexec-utility.md).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../includes/ssnotedepnextavoid-md.md)] <span data-ttu-id="d05dc-108">Em vez disso, use o recurso de plano de manutenção do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d05dc-108">Use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] maintenance plan feature instead.</span></span> <span data-ttu-id="d05dc-109">Para obter mais informações sobre planos de manutenção, veja [Planos de manutenção](../relational-databases/maintenance-plans/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="d05dc-109">For more information on maintenance plans, see [Maintenance Plans](../relational-databases/maintenance-plans/maintenance-plans.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d05dc-110">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d05dc-110">Syntax</span></span>  
  
```  
  
      sqlmaint   
[-?] |  
[  
     [-Sserver_name[\instance_name]]  
     [-Ulogin_ID [-Ppassword]]  
     {  
          [-Ddatabase_name | -PlanNamename | -PlanIDguid ]  
          [-Rpttext_file]  
          [-Tooperator_name]  
          [-HtmlRpthtml_file [-DelHtmlRpt <time_period>] ]  
          [-RmUnusedSpacethreshold_percentfree_percent]  
          [-CkDB | -CkDBNoIdx]  
          [-CkAl | -CkAlNoIdx]  
          [-CkCat]  
          [-UpdOptiStatssample_percent]  
          [-RebldIdxfree_space]  
          [-SupportComputedColumn]  
          [-WriteHistory]  
          [  
               {-BkUpDB [backup_path] | -BkUpLog [backup_path] }  
               {-BkUpMedia  
                    {DISK [  
                           [-DelBkUps<time_period>]   
                           [-CrBkSubDir ]   
                           [-UseDefDir ]   
                          ]  
                     | TAPE   
                    }  
               }  
               [-BkUpOnlyIfClean]  
               [-VrfyBackup]  
          ]  
     }  
]  
<time_period> ::=  
number[minutes | hours | days | weeks | months]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d05dc-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d05dc-111">Arguments</span></span>  
 <span data-ttu-id="d05dc-112">Os parâmetros e seus valores devem ser separados por um espaço.</span><span class="sxs-lookup"><span data-stu-id="d05dc-112">The parameters and their values must be separated by a space.</span></span> <span data-ttu-id="d05dc-113">Por exemplo, deve haver um espaço entre **-S** e *server_name*.</span><span class="sxs-lookup"><span data-stu-id="d05dc-113">For example, there must be a space between **-S** and *server_name*.</span></span>  
  
 <span data-ttu-id="d05dc-114">**-?**</span><span class="sxs-lookup"><span data-stu-id="d05dc-114">**-?**</span></span>  
 <span data-ttu-id="d05dc-115">Especifica que o diagrama de sintaxe para o **sqlmaint** seja retornado.</span><span class="sxs-lookup"><span data-stu-id="d05dc-115">Specifies that the syntax diagram for **sqlmaint** be returned.</span></span> <span data-ttu-id="d05dc-116">Este parâmetro deve ser usado sozinho.</span><span class="sxs-lookup"><span data-stu-id="d05dc-116">This parameter must be used alone.</span></span>  
  
 <span data-ttu-id="d05dc-117">**-S** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="d05dc-117">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="d05dc-118">Especifica a instância de destino do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d05dc-118">Specifies the target instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d05dc-119">Especifica *server_name* para a conexão com a instância padrão do [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="d05dc-119">Specify *server_name* to connect to the default instance of [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on that server.</span></span> <span data-ttu-id="d05dc-120">Especifique *server_name **_\\_** instance_name* para se conectar a uma instância nomeada do [!INCLUDE[ssDE](../includes/ssde-md.md)] nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="d05dc-120">Specify *server_name\*\*_\\_*\* instance_name\* to connect to a named instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="d05dc-121">Se nenhum servidor for especificado, o **sqlmaint** se conecta à instância padrão do [!INCLUDE[ssDE](../includes/ssde-md.md)] no computador local.</span><span class="sxs-lookup"><span data-stu-id="d05dc-121">If no server is specified, **sqlmaint** connects to the default instance of [!INCLUDE[ssDE](../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="d05dc-122">**-U** _login_ID_</span><span class="sxs-lookup"><span data-stu-id="d05dc-122">**-U** _login_ID_</span></span>  
 <span data-ttu-id="d05dc-123">Especifica a ID de logon a ser usada para se conectar ao servidor.</span><span class="sxs-lookup"><span data-stu-id="d05dc-123">Specifies the login ID to use when connecting to the server.</span></span> <span data-ttu-id="d05dc-124">Se não for fornecida, o **sqlmaint** tenta usar a [!INCLUDE[msCoName](../includes/msconame-md.md)] -Windows-Authentication.</span><span class="sxs-lookup"><span data-stu-id="d05dc-124">If not supplied, **sqlmaint** attempts to use [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span> <span data-ttu-id="d05dc-125">Se *login_ID* contiver caracteres especiais, ele deverá estar entre aspas duplas ("); caso contrário, as aspas duplas serão opcionais.</span><span class="sxs-lookup"><span data-stu-id="d05dc-125">If *login_ID* contains special characters, it must be enclosed in double quotation marks ("); otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d05dc-126">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="d05dc-126">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="d05dc-127">**-P** _password_</span><span class="sxs-lookup"><span data-stu-id="d05dc-127">**-P** _password_</span></span>  
 <span data-ttu-id="d05dc-128">Especifica a senha para a ID de logon.</span><span class="sxs-lookup"><span data-stu-id="d05dc-128">Specifies the password for the login ID.</span></span> <span data-ttu-id="d05dc-129">Válido somente se o parâmetro **-U** também for fornecido.</span><span class="sxs-lookup"><span data-stu-id="d05dc-129">Only valid if the **-U** parameter is also supplied.</span></span> <span data-ttu-id="d05dc-130">Se o *password* contiver caracteres especiais, ele deve estar entre aspas duplas; caso contrário, as aspas duplas são opcionais.</span><span class="sxs-lookup"><span data-stu-id="d05dc-130">If *password* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d05dc-131">A senha não é mascarada.</span><span class="sxs-lookup"><span data-stu-id="d05dc-131">The password is not masked.</span></span> <span data-ttu-id="d05dc-132">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="d05dc-132">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="d05dc-133">**-D** _database_name_</span><span class="sxs-lookup"><span data-stu-id="d05dc-133">**-D** _database_name_</span></span>  
 <span data-ttu-id="d05dc-134">Especifica o nome do banco de dados no qual a operação de manutenção deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="d05dc-134">Specifies the name of the database in which to perform the maintenance operation.</span></span> <span data-ttu-id="d05dc-135">Se o *database_name* contiver caracteres especiais, ele deverá estar entre aspas duplas; caso contrário, as aspas duplas são opcionais.</span><span class="sxs-lookup"><span data-stu-id="d05dc-135">If *database_name* contains special characters, it must be enclosed in double quotation marks; otherwise, the double quotation marks are optional.</span></span>  
  
 <span data-ttu-id="d05dc-136">**-PlanName** _name_</span><span class="sxs-lookup"><span data-stu-id="d05dc-136">**-PlanName** _name_</span></span>  
 <span data-ttu-id="d05dc-137">Especifica o nome de um plano de manutenção de banco de dados definido com o uso do Assistente para Planos de Manutenção de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-137">Specifies the name of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="d05dc-138">A única informação que **sqlmaint** usa do plano é a lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-138">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="d05dc-139">Todas as atividades de manutenção especificadas nos outros parâmetros do **sqlmaint** se aplicam a esta lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-139">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span>  
  
 <span data-ttu-id="d05dc-140">**-PlanID** _guid_</span><span class="sxs-lookup"><span data-stu-id="d05dc-140">**-PlanID** _guid_</span></span>  
 <span data-ttu-id="d05dc-141">Especifica o identificador global exclusivo (GUID) de um plano de manutenção de banco de dados definido com o uso do Assistente para Planos de Manutenção de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-141">Specifies the globally unique identifier (GUID) of a database maintenance plan defined using the Database Maintenance Plan Wizard.</span></span> <span data-ttu-id="d05dc-142">A única informação que **sqlmaint** usa do plano é a lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-142">The only information **sqlmaint** uses from the plan is the list of the databases in the plan.</span></span> <span data-ttu-id="d05dc-143">Todas as atividades de manutenção especificadas nos outros parâmetros do **sqlmaint** se aplicam a esta lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-143">Any maintenance activities you specify in the other **sqlmaint** parameters are applied to this list of databases.</span></span> <span data-ttu-id="d05dc-144">Isso deve corresponder a um valor do plan_id em msdb.dbo.sysdbmaintplans.</span><span class="sxs-lookup"><span data-stu-id="d05dc-144">This must match a plan_id value in msdb.dbo.sysdbmaintplans.</span></span>  
  
 <span data-ttu-id="d05dc-145">**-Rpt** _text_file_</span><span class="sxs-lookup"><span data-stu-id="d05dc-145">**-Rpt** _text_file_</span></span>  
 <span data-ttu-id="d05dc-146">Especifica o caminho completo e o nome do arquivo no qual será gerado o relatório.</span><span class="sxs-lookup"><span data-stu-id="d05dc-146">Specifies the full path and name of the file into which the report is to be generated.</span></span> <span data-ttu-id="d05dc-147">O relatório também é gerado na tela.</span><span class="sxs-lookup"><span data-stu-id="d05dc-147">The report is also generated on the screen.</span></span> <span data-ttu-id="d05dc-148">O relatório mantém informações de versão adicionando uma data ao nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d05dc-148">The report maintains version information by adding a date to the file name.</span></span> <span data-ttu-id="d05dc-149">A data é gerada da seguinte forma: ao final do nome do arquivo, mas antes do ponto final, no formato _*aaaaMMddhhmm*.</span><span class="sxs-lookup"><span data-stu-id="d05dc-149">The date is generated as follows: at the end of the file name but before the period, in the form _*yyyyMMddhhmm*.</span></span> <span data-ttu-id="d05dc-150">*aaaa* = ano, *MM* = mês, *dd* = dia, *hh* = hora, *mm* = minuto.</span><span class="sxs-lookup"><span data-stu-id="d05dc-150">*yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, *mm* = minute.</span></span>  
  
 <span data-ttu-id="d05dc-151">Se você executar o utilitário às 10h23</span><span class="sxs-lookup"><span data-stu-id="d05dc-151">If you run the utility at 10:23 A.M.</span></span> <span data-ttu-id="d05dc-152">em 1º de dezembro de 1996, e esse é o valor de *text_file* :</span><span class="sxs-lookup"><span data-stu-id="d05dc-152">on December 1, 1996, and this is the *text_file* value:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.rpt  
```  
  
 <span data-ttu-id="d05dc-153">O nome de arquivo gerado é:</span><span class="sxs-lookup"><span data-stu-id="d05dc-153">The generated file name is:</span></span>  
  
```  
c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint_199612011023.rpt  
```  
  
 <span data-ttu-id="d05dc-154">O nome do arquivo UNC completo é necessário para *text_file* , quando **sqlmaint** acessa um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="d05dc-154">The full Universal Naming Convention (UNC) file name is required for *text_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="d05dc-155">**-Para** _operator_name_</span><span class="sxs-lookup"><span data-stu-id="d05dc-155">**-To** _operator_name_</span></span>  
 <span data-ttu-id="d05dc-156">Especifica o operador para quem o relatório gerado será enviado por meio do SQL Mail.</span><span class="sxs-lookup"><span data-stu-id="d05dc-156">Specifies the operator to whom the generated report is sent through SQL Mail.</span></span>  
  
 <span data-ttu-id="d05dc-157">**-HtmlRpt** _html_file_</span><span class="sxs-lookup"><span data-stu-id="d05dc-157">**-HtmlRpt** _html_file_</span></span>  
 <span data-ttu-id="d05dc-158">Especifica o caminho completo e nome do arquivo no qual um relatório HTML será gerado.</span><span class="sxs-lookup"><span data-stu-id="d05dc-158">Specifies the full path and name of the file into which an HTML report is to be generated.</span></span> <span data-ttu-id="d05dc-159">**sqlmaint** gera o nome de arquivo, acrescentando uma cadeia de caracteres no formato _*aaaaMMddhhmm* ao nome do arquivo, da mesma forma que faz para o parâmetro **-Rpt** .</span><span class="sxs-lookup"><span data-stu-id="d05dc-159">**sqlmaint** generates the file name by appending a string of the format _*yyyyMMddhhmm* to the file name, just as it does for the **-Rpt** parameter.</span></span>  
  
 <span data-ttu-id="d05dc-160">O nome do arquivo UNC completo é necessário para *html_file* , quando **sqlmaint** acessa um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="d05dc-160">The full UNC file name is required for *html_file* when **sqlmaint** accesses a remote server.</span></span>  
  
 <span data-ttu-id="d05dc-161">**-DelHtmlRpt** \<*time_period*></span><span class="sxs-lookup"><span data-stu-id="d05dc-161">**-DelHtmlRpt** \<*time_period*></span></span>  
 <span data-ttu-id="d05dc-162">Especifica que qualquer relatório HTML no diretório de relatórios deverá ser excluído se o intervalo de tempo depois da criação do arquivo de relatório exceder o \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="d05dc-162">Specifies that any HTML report in the report directory be deleted if the time interval after the creation of the report file exceeds \<*time_period*>.</span></span> <span data-ttu-id="d05dc-163">**-DelHtmlRpt** procura arquivos cujos nomes correspondem ao padrão gerado pelo parâmetro *html_file*.</span><span class="sxs-lookup"><span data-stu-id="d05dc-163">**-DelHtmlRpt** looks for files whose name fits the pattern generated from the *html_file* parameter.</span></span> <span data-ttu-id="d05dc-164">Se *html_file* for C:\Arquivos de Programas\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm, **-DelHtmlRpt** fará com que **sqlmaint** exclua todos os arquivos cujos nomes correspondam ao padrão C:\Arquivos de Programas\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm e que sejam anteriores ao \<*time_period*> especificado.</span><span class="sxs-lookup"><span data-stu-id="d05dc-164">If *html_file* is c:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint.htm, then **-DelHtmlRpt** causes **sqlmaint** to delete any files whose names match the pattern C:\Program Files\Microsoft SQL Server\Mssql\Backup\AdventureWorks2012_maint\*.htm and that are older than the specified \<*time_period*>.</span></span>  
  
 <span data-ttu-id="d05dc-165">**-RmUnusedSpace** _threshold_percent free_percent_</span><span class="sxs-lookup"><span data-stu-id="d05dc-165">**-RmUnusedSpace** _threshold_percent free_percent_</span></span>  
 <span data-ttu-id="d05dc-166">Especifica que o espaço não usado seja removido do banco de dados especificado em **-D**.</span><span class="sxs-lookup"><span data-stu-id="d05dc-166">Specifies that unused space be removed from the database specified in **-D**.</span></span> <span data-ttu-id="d05dc-167">Essa opção só é útil para bancos de dados definidos para crescer automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d05dc-167">This option is only useful for databases that are defined to grow automatically.</span></span> <span data-ttu-id="d05dc-168">*Threshold_percent* especifica o tamanho em megabytes que o banco de dados deve atingir, antes que **sqlmaint** tente remover o espaço de dados não utilizado.</span><span class="sxs-lookup"><span data-stu-id="d05dc-168">*Threshold_percent* specifies in megabytes the size that the database must reach before **sqlmaint** attempts to remove unused data space.</span></span> <span data-ttu-id="d05dc-169">Se o banco de dados for menor que *threshold_percent*, nenhuma ação será tomada.</span><span class="sxs-lookup"><span data-stu-id="d05dc-169">If the database is smaller than the *threshold_percent*, no action is taken.</span></span> <span data-ttu-id="d05dc-170">*Free_percent* especifica quanto espaço não utilizado deve permanecer no banco de dados, especificado como um percentual do tamanho final do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-170">*Free_percent* specifies how much unused space must remain in the database, specified as a percentage of the final size of the database.</span></span> <span data-ttu-id="d05dc-171">Por exemplo, se um banco de dados com 200 MB contiver 100 MB de dados, especificar 10 para *free_percent* resultará em um tamanho final de banco de dados de 110 MB.</span><span class="sxs-lookup"><span data-stu-id="d05dc-171">For example, if a 200-MB database contains 100 MB of data, specifying 10 for *free_percent* results in the final database size being 110 MB.</span></span> <span data-ttu-id="d05dc-172">Observe que um banco de dados não será expandido se for menor do que *free_percent* somado à quantidade de dados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-172">Note that a database is not expanded if it is smaller than *free_percent* plus the amount of data in the database.</span></span> <span data-ttu-id="d05dc-173">Por exemplo, se um banco de dados de 108 MB tiver 100 MB de dados, especificar 10 para *free_percent* não expandirá o banco de dados para 110 MB; ele permanecerá com 108 MB.</span><span class="sxs-lookup"><span data-stu-id="d05dc-173">For example, if a 108-MB database has 100 MB of data, specifying 10 for *free_percent* does not expand the database to 110 MB; it remains at 108 MB.</span></span>  
  
 <span data-ttu-id="d05dc-174">**-CkDB** |  **-CkDBNoIdx**</span><span class="sxs-lookup"><span data-stu-id="d05dc-174">**-CkDB** | **-CkDBNoIdx**</span></span>  
 <span data-ttu-id="d05dc-175">Especifica que uma instrução DBCC CHECKDB ou DBCC CHECKDB com a opção de NOINDEX seja executada no banco de dados especificado em **-D**.</span><span class="sxs-lookup"><span data-stu-id="d05dc-175">Specifies that a DBCC CHECKDB statement or a DBCC CHECKDB statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="d05dc-176">Para obter mais informações, consulte DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="d05dc-176">For more information, see DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="d05dc-177">Um aviso será gravado em *text_file* , se o banco de dados estiver em uso, quando **sqlmaint** for executado.</span><span class="sxs-lookup"><span data-stu-id="d05dc-177">A warning is written to *text_file* if the database is in use when **sqlmaint** runs.</span></span>  
  
 <span data-ttu-id="d05dc-178">**-CkAl** |  **-CkAlNoIdx**</span><span class="sxs-lookup"><span data-stu-id="d05dc-178">**-CkAl** | **-CkAlNoIdx**</span></span>  
 <span data-ttu-id="d05dc-179">Especifica que uma instrução DBCC CHECKALLOC com a opção de NOINDEX seja executada no banco de dados especificado em **-D**.</span><span class="sxs-lookup"><span data-stu-id="d05dc-179">Specifies that a DBCC CHECKALLOC statement with the NOINDEX option be run in the database specified in **-D**.</span></span> <span data-ttu-id="d05dc-180">Para obter mais informações, veja [DBCC CHECKALLOC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d05dc-180">For more information, see [DBCC CHECKALLOC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkalloc-transact-sql).</span></span>  
  
 <span data-ttu-id="d05dc-181">**-CkCat**</span><span class="sxs-lookup"><span data-stu-id="d05dc-181">**-CkCat**</span></span>  
 <span data-ttu-id="d05dc-182">Especifica que uma instrução DBCC CHECKCATALOG (Transact-SQL) seja executada no banco de dados especificado em **-D**.</span><span class="sxs-lookup"><span data-stu-id="d05dc-182">Specifies that a DBCC CHECKCATALOG (Transact-SQL) statement be run in the database specified in **-D**.</span></span> <span data-ttu-id="d05dc-183">Para obter mais informações, veja [DBCC CHECKCATALOG &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d05dc-183">For more information, see [DBCC CHECKCATALOG &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkcatalog-transact-sql).</span></span>  
  
 <span data-ttu-id="d05dc-184">**-UpdOptiStats** _sample_percent_</span><span class="sxs-lookup"><span data-stu-id="d05dc-184">**-UpdOptiStats** _sample_percent_</span></span>  
 <span data-ttu-id="d05dc-185">Especifica que a instrução seguinte seja executada em cada tabela no banco de dados:</span><span class="sxs-lookup"><span data-stu-id="d05dc-185">Specifies that the following statement be run on each table in the database:</span></span>  
  
```  
UPDATE STATISTICS table WITH SAMPLE sample_percent PERCENT;  
```  
  
 <span data-ttu-id="d05dc-186">Se as tabelas incluírem colunas computadas, também será necessário especificar o argumento **-SupportedComputedColumn** quando usar **-UpdOptiStats**.</span><span class="sxs-lookup"><span data-stu-id="d05dc-186">If the tables contain computed columns, you must also specify the **-SupportedComputedColumn** argument when you use **-UpdOptiStats**.</span></span>  
  
 <span data-ttu-id="d05dc-187">Para obter mais informações, veja [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d05dc-187">For more information, see [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
 <span data-ttu-id="d05dc-188">**-RebldIdx** _free_space_</span><span class="sxs-lookup"><span data-stu-id="d05dc-188">**-RebldIdx** _free_space_</span></span>  
 <span data-ttu-id="d05dc-189">Especifica que os índices nas tabelas do banco de dados de destino devem ser reconstruídos usando o valor percentual de *free_space* como o inverso do fator de preenchimento.</span><span class="sxs-lookup"><span data-stu-id="d05dc-189">Specifies that indexes on tables in the target database should be rebuilt by using the *free_space* percent value as the inverse of the fill factor.</span></span> <span data-ttu-id="d05dc-190">Por exemplo, se o percentual de *free_space* for 30, o fator de preenchimento usado será 70.</span><span class="sxs-lookup"><span data-stu-id="d05dc-190">For example, if *free_space* percentage is 30, then the fill factor used is 70.</span></span> <span data-ttu-id="d05dc-191">Se for especificado um valor percentual de *free_space* de 100, os índices serão reconstruídos com o fator de preenchimento original.</span><span class="sxs-lookup"><span data-stu-id="d05dc-191">If a *free_space* percentage value of 100 is specified, then the indexes are rebuilt with the original fill factor value.</span></span>  
  
 <span data-ttu-id="d05dc-192">Se os índices estiverem em colunas computadas, também será necessário especificar o argumento **-SupportComputedColumn** quando usar **-RebldIdx**.</span><span class="sxs-lookup"><span data-stu-id="d05dc-192">If the indexes are on computed columns, you must also specify the **-SupportComputedColumn** argument when you use **-RebldIdx**.</span></span>  
  
 <span data-ttu-id="d05dc-193">**-SupportComputedColumn**</span><span class="sxs-lookup"><span data-stu-id="d05dc-193">**-SupportComputedColumn**</span></span>  
 <span data-ttu-id="d05dc-194">Deve ser especificado para executar comandos de manutenção DBCC com **sqlmaint** em colunas computadas.</span><span class="sxs-lookup"><span data-stu-id="d05dc-194">Must be specified to run DBCC maintenance commands with **sqlmaint** on computed columns.</span></span>  
  
 <span data-ttu-id="d05dc-195">**-WriteHistory**</span><span class="sxs-lookup"><span data-stu-id="d05dc-195">**-WriteHistory**</span></span>  
 <span data-ttu-id="d05dc-196">Especifica que deve haver uma entrada em msdb.dbo.sysdbmaintplan_history para cada ação de manutenção executada por **sqlmaint**.</span><span class="sxs-lookup"><span data-stu-id="d05dc-196">Specifies that an entry be made in msdb.dbo.sysdbmaintplan_history for each maintenance action performed by **sqlmaint**.</span></span> <span data-ttu-id="d05dc-197">Se **-PlanName** ou **-PlanID** for especificado, as entradas no sysdbmaintplan_history usarão a ID do plano especificado.</span><span class="sxs-lookup"><span data-stu-id="d05dc-197">If **-PlanName** or **-PlanID** is specified, the entries in sysdbmaintplan_history use the ID of the specified plan.</span></span> <span data-ttu-id="d05dc-198">Se **-D** for especificado, as entradas em sysdbmaintplan_history serão feitas com zeros para a ID do plano.</span><span class="sxs-lookup"><span data-stu-id="d05dc-198">If **-D** is specified, the entries in sysdbmaintplan_history are made with zeroes for the plan ID.</span></span>  
  
 <span data-ttu-id="d05dc-199">**-BkUpDB** [ *backup_path*] |  **-BkUpLog** [ *backup_path* ]</span><span class="sxs-lookup"><span data-stu-id="d05dc-199">**-BkUpDB** [ *backup_path*] |  **-BkUpLog** [ *backup_path* ]</span></span>  
 <span data-ttu-id="d05dc-200">Especifica uma ação de backup.</span><span class="sxs-lookup"><span data-stu-id="d05dc-200">Specifies a backup action.</span></span> <span data-ttu-id="d05dc-201">**-BkUpDb** faz o backup de todo o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-201">**-BkUpDb** backs up the entire database.</span></span> <span data-ttu-id="d05dc-202">**-BkUpLog** faz backup apenas do log de transações.</span><span class="sxs-lookup"><span data-stu-id="d05dc-202">**-BkUpLog** backs up only the transaction log.</span></span>  
  
 <span data-ttu-id="d05dc-203">*backup_path* especifica o diretório do backup.</span><span class="sxs-lookup"><span data-stu-id="d05dc-203">*backup_path* specifies the directory for the backup.</span></span> <span data-ttu-id="d05dc-204">*backup_path* não será necessário se **-UseDefDir** também for especificado e será substituído por **-UseDefDir** se ambos estiverem especificados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-204">*backup_path* is not needed if **-UseDefDir** is also specified, and is overridden by **-UseDefDir** if both are specified.</span></span> <span data-ttu-id="d05dc-205">O backup pode ser colocado em um diretório ou em um endereço de dispositivo de fita (por exemplo, \\\\.\TAPE0).</span><span class="sxs-lookup"><span data-stu-id="d05dc-205">The backup can be placed in a directory or a tape device address (for example, \\\\.\TAPE0).</span></span> <span data-ttu-id="d05dc-206">O nome do arquivo para um backup de banco de dados é gerado automaticamente como segue:</span><span class="sxs-lookup"><span data-stu-id="d05dc-206">The file name for a database backup is generated automatically as follows:</span></span>  
  
```  
dbname_db_yyyyMMddhhmm.BAK  
  
```  
  
 <span data-ttu-id="d05dc-207">onde</span><span class="sxs-lookup"><span data-stu-id="d05dc-207">where</span></span>  
  
-   <span data-ttu-id="d05dc-208">*dbname* é o nome do banco de dados do qual é feito o backup.</span><span class="sxs-lookup"><span data-stu-id="d05dc-208">*dbname* is the name of the database being backed up.</span></span>  
  
-   <span data-ttu-id="d05dc-209">*aaaaMMddhhmm* é o tempo da operação de backup com *aaaa* = ano, *MM* = mês *dd* = dia, *hh* = hora e *mm* = minuto.</span><span class="sxs-lookup"><span data-stu-id="d05dc-209">*yyyyMMddhhmm* is the time of the backup operation with *yyyy* = year, *MM* = month, *dd* = day, *hh* = hour, and *mm* = minute.</span></span>  
  
 <span data-ttu-id="d05dc-210">O nome do arquivo para um backup de transações é gerado automaticamente com um formato semelhante:</span><span class="sxs-lookup"><span data-stu-id="d05dc-210">The file name for a transaction backup is generated automatically with a similar format:</span></span>  
  
```  
dbname_log_yyyymmddhhmm.BAK  
  
```  
  
 <span data-ttu-id="d05dc-211">Se usar o parâmetro **-BkUpDB** , também será necessário especificar a mídia usando o parâmetro **-BkUpMedia** .</span><span class="sxs-lookup"><span data-stu-id="d05dc-211">If you use the **-BkUpDB** parameter, you must also specify the media by using the **-BkUpMedia** parameter.</span></span>  
  
 <span data-ttu-id="d05dc-212">**-BkUpMedia**</span><span class="sxs-lookup"><span data-stu-id="d05dc-212">**-BkUpMedia**</span></span>  
 <span data-ttu-id="d05dc-213">Especifica o tipo de mídia do backup: DISK ou TAPE.</span><span class="sxs-lookup"><span data-stu-id="d05dc-213">Specifies the media type of the backup, either DISK or TAPE.</span></span>  
  
 <span data-ttu-id="d05dc-214">**DISK**</span><span class="sxs-lookup"><span data-stu-id="d05dc-214">**DISK**</span></span>  
 <span data-ttu-id="d05dc-215">Especifica que a mídia de backup é disco.</span><span class="sxs-lookup"><span data-stu-id="d05dc-215">Specifies that the backup medium is disk.</span></span>  
  
 <span data-ttu-id="d05dc-216">**-DelBkUps**\< *time_period* ></span><span class="sxs-lookup"><span data-stu-id="d05dc-216">**-DelBkUps**\< *time_period* ></span></span>  
 <span data-ttu-id="d05dc-217">Para backups em disco, especifica que qualquer arquivo de backup no diretório de backups deverá ser excluído se o intervalo de tempo depois da criação do backup exceder o \<*time_period*>.</span><span class="sxs-lookup"><span data-stu-id="d05dc-217">For disk backups, specifies that any backup file in the backup directory be deleted if the time interval after the creation of the backup exceeds the \<*time_period*>.</span></span>  
  
 <span data-ttu-id="d05dc-218">**-CrBkSubDir**</span><span class="sxs-lookup"><span data-stu-id="d05dc-218">**-CrBkSubDir**</span></span>  
 <span data-ttu-id="d05dc-219">Para backups em disco, especifica que um subdiretório deverá ser criado no diretório [*backup_path*] ou no diretório de backup padrão se o **-UseDefDir** também for especificado.</span><span class="sxs-lookup"><span data-stu-id="d05dc-219">For disk backups, specifies that a subdirectory be created in the [*backup_path*] directory or in the default backup directory if **-UseDefDir** is also specified.</span></span> <span data-ttu-id="d05dc-220">O nome do subdiretório é gerado com base no nome do banco de dados especificado em **-D**.</span><span class="sxs-lookup"><span data-stu-id="d05dc-220">The name of the subdirectory is generated from the database name specified in **-D**.</span></span> <span data-ttu-id="d05dc-221">**-CrBkSubDir** oferece um modo fácil de colocar todos os backups de bancos de dados diferentes em subdiretórios separados, sem a necessidade de alterar o parâmetro *backup_path* .</span><span class="sxs-lookup"><span data-stu-id="d05dc-221">**-CrBkSubDir** offers an easy way to put all the backups for different databases into separate subdirectories without having to change the *backup_path* parameter.</span></span>  
  
 <span data-ttu-id="d05dc-222">**-UseDefDir**</span><span class="sxs-lookup"><span data-stu-id="d05dc-222">**-UseDefDir**</span></span>  
 <span data-ttu-id="d05dc-223">Para backups de disco, especifica que o arquivo de backup seja criado no diretório padrão de backup.</span><span class="sxs-lookup"><span data-stu-id="d05dc-223">For disk backups, specifies that the backup file be created in the default backup directory.</span></span> <span data-ttu-id="d05dc-224">**UseDefDir** substituirá *backup_path* se ambos forem especificados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-224">**UseDefDir** overrides *backup_path* if both are specified.</span></span> <span data-ttu-id="d05dc-225">Com uma instalação padrão do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], o diretório padrão de backup é C:\Arquivos de Programas\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup.</span><span class="sxs-lookup"><span data-stu-id="d05dc-225">With a default [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup, the default backup directory is C:\Program Files\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Backup.</span></span>  
  
 <span data-ttu-id="d05dc-226">**TAPE**</span><span class="sxs-lookup"><span data-stu-id="d05dc-226">**TAPE**</span></span>  
 <span data-ttu-id="d05dc-227">Especifica que a mídia de backup é fita.</span><span class="sxs-lookup"><span data-stu-id="d05dc-227">Specifies that the backup medium is tape.</span></span>  
  
 <span data-ttu-id="d05dc-228">**-BkUpOnlyIfClean**</span><span class="sxs-lookup"><span data-stu-id="d05dc-228">**-BkUpOnlyIfClean**</span></span>  
 <span data-ttu-id="d05dc-229">Especifica que o backup ocorrerá apenas se nenhuma verificação **-Ck** especificada encontrar problemas nos dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-229">Specifies that the backup occur only if any specified **-Ck** checks did not find problems with the data.</span></span> <span data-ttu-id="d05dc-230">As ações de manutenção são executadas na mesma sequência em que aparecem no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="d05dc-230">Maintenance actions run in the same sequence as they appear in the command prompt.</span></span> <span data-ttu-id="d05dc-231">Especifique o parâmetro **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**ou **-CkCat** antes de **-BkUpDB**/ **-BkUpLog** caso também for especificar **-BkUpOnlyIfClean**, ou o backup ocorrerá independentemente de a verificação relatar problemas ou não.</span><span class="sxs-lookup"><span data-stu-id="d05dc-231">Specify the parameters **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** before the **-BkUpDB**/**-BkUpLog** parameter(s) if you are also going to specify **-BkUpOnlyIfClean**, or the backup occurs whether or not the check reports problems.</span></span>  
  
 <span data-ttu-id="d05dc-232">**-VrfyBackup**</span><span class="sxs-lookup"><span data-stu-id="d05dc-232">**-VrfyBackup**</span></span>  
 <span data-ttu-id="d05dc-233">Especifica que o RESTORE VERIFYONLY será executado no backup quando este for concluído.</span><span class="sxs-lookup"><span data-stu-id="d05dc-233">Specifies that RESTORE VERIFYONLY be run on the backup when it completes.</span></span>  
  
 <span data-ttu-id="d05dc-234">*number*[**minutes**| **hours**| **day**| **weeks**| **months**]</span><span class="sxs-lookup"><span data-stu-id="d05dc-234">*number*[**minutes**| **hours**| **day**| **weeks**| **months**]</span></span>  
 <span data-ttu-id="d05dc-235">Especifica o intervalo de tempo usado para determinar se um relatório ou arquivo de backup é antigo o bastante para ser excluído.</span><span class="sxs-lookup"><span data-stu-id="d05dc-235">Specifies the time interval used to determine if a report or backup file is old enough to be deleted.</span></span> <span data-ttu-id="d05dc-236">*number* é um inteiro seguido (sem espaço) por uma unidade de tempo.</span><span class="sxs-lookup"><span data-stu-id="d05dc-236">*number* is an integer followed (without a space) by a unit of time.</span></span> <span data-ttu-id="d05dc-237">Exemplos válidos:</span><span class="sxs-lookup"><span data-stu-id="d05dc-237">Valid examples:</span></span>  
  
-   <span data-ttu-id="d05dc-238">**12semanas**</span><span class="sxs-lookup"><span data-stu-id="d05dc-238">**12weeks**</span></span>  
  
-   <span data-ttu-id="d05dc-239">**3meses**</span><span class="sxs-lookup"><span data-stu-id="d05dc-239">**3months**</span></span>  
  
-   <span data-ttu-id="d05dc-240">**15dias**</span><span class="sxs-lookup"><span data-stu-id="d05dc-240">**15days**</span></span>  
  
 <span data-ttu-id="d05dc-241">Se apenas o *number* for especificado, a parte de data padrão será **weeks**.</span><span class="sxs-lookup"><span data-stu-id="d05dc-241">If only *number* is specified, the default date part is **weeks**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d05dc-242">Comentários</span><span class="sxs-lookup"><span data-stu-id="d05dc-242">Remarks</span></span>  
 <span data-ttu-id="d05dc-243">O utilitário **sqlmaint** executa operações de manutenção em um ou mais bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-243">The **sqlmaint** utility performs maintenance operations on one or more databases.</span></span> <span data-ttu-id="d05dc-244">Se **-D** for especificado, as operações especificadas nas demais opções serão executadas apenas no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="d05dc-244">If **-D** is specified, the operations specified in the remaining switches are performed only on the specified database.</span></span> <span data-ttu-id="d05dc-245">Se **-PlanName** ou **-PlanID** forem especificados, a única informação que **sqlmaint** recuperará do plano de manutenção especificado será a lista de bancos de dados no plano.</span><span class="sxs-lookup"><span data-stu-id="d05dc-245">If **-PlanName** or **-PlanID** are specified, the only information **sqlmaint** retrieves from the specified maintenance plan is the list of databases in the plan.</span></span> <span data-ttu-id="d05dc-246">Todas as operações especificadas nos demais parâmetros do **sqlmaint** são aplicadas a cada banco de dados na lista obtida do plano.</span><span class="sxs-lookup"><span data-stu-id="d05dc-246">All operations specified in the remaining **sqlmaint** parameters are applied against each database in the list obtained from the plan.</span></span> <span data-ttu-id="d05dc-247">O utilitário **sqlmaint** não aplica atividades de manutenção definidas no próprio plano.</span><span class="sxs-lookup"><span data-stu-id="d05dc-247">The **sqlmaint** utility does not apply any of the maintenance activities defined in the plan itself.</span></span>  
  
 <span data-ttu-id="d05dc-248">O utilitário **sqlmaint** retorna 0 se for executado com êxito ou 1 se apresentar falha.</span><span class="sxs-lookup"><span data-stu-id="d05dc-248">The **sqlmaint** utility returns 0 if it runs successfully or 1 if it fails.</span></span> <span data-ttu-id="d05dc-249">A falha é informada:</span><span class="sxs-lookup"><span data-stu-id="d05dc-249">Failure is reported:</span></span>  
  
-   <span data-ttu-id="d05dc-250">Se alguma ação de manutenção apresentar falha.</span><span class="sxs-lookup"><span data-stu-id="d05dc-250">If any of the maintenance actions fail.</span></span>  
  
-   <span data-ttu-id="d05dc-251">Se as verificações **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**ou **-CkCat** encontrarem problemas nos dados.</span><span class="sxs-lookup"><span data-stu-id="d05dc-251">If **-CkDB**, **-CkDBNoIdx**, **-CkAl**, **-CkAlNoIdx**, **-CkTxtAl**, or **-CkCat** checks find problems with the data.</span></span>  
  
-   <span data-ttu-id="d05dc-252">Se uma falha geral for encontrada.</span><span class="sxs-lookup"><span data-stu-id="d05dc-252">If a general failure is encountered.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="d05dc-253">Permissões</span><span class="sxs-lookup"><span data-stu-id="d05dc-253">Permissions</span></span>  
 <span data-ttu-id="d05dc-254">O utilitário **sqlmaint** pode ser executado por qualquer usuário do Windows com a permissão **Ler e Executar** no `sqlmaint.exe`que, por padrão, é armazenado na pasta `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` .</span><span class="sxs-lookup"><span data-stu-id="d05dc-254">The **sqlmaint** utility can be executed by any Windows user with **Read and Execute** permission on `sqlmaint.exe`, which by default is stored in the `x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER1\MSSQL\Binn` folder.</span></span> <span data-ttu-id="d05dc-255">Adicionalmente, o logon [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] especificado com **-ID_logon** deve ter as permissões exigidas pelo [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para executar a ação especificada.</span><span class="sxs-lookup"><span data-stu-id="d05dc-255">Additionally, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login specified with **-login_ID** must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span> <span data-ttu-id="d05dc-256">Se a conexão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usar a autenticação do Windows, o logon do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] mapeado para autenticar o usuário do Windows deve ter as permissões do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] exigidas para realizar a ação especificada.</span><span class="sxs-lookup"><span data-stu-id="d05dc-256">If the connection to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses Windows Authentication, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login mapped to the authenticated Windows user must have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] permissions required to perform the specified action.</span></span>  
  
 <span data-ttu-id="d05dc-257">Por exemplo, o uso de **-BkUpDB** exige permissão para executar a instrução BACKUP.</span><span class="sxs-lookup"><span data-stu-id="d05dc-257">For example, using the **-BkUpDB** requires permission to execute the BACKUP statement.</span></span> <span data-ttu-id="d05dc-258">Além disso, o uso do argumento **-UpdOptiStats** exige permissão para executar a instrução UPDATE STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="d05dc-258">And using the **-UpdOptiStats** argument requires permission to execute the UPDATE STATISTICS statement.</span></span> <span data-ttu-id="d05dc-259">Para obter mais informações, consulte as seções "Permissões" dos tópicos correspondentes nos Manuais Online.</span><span class="sxs-lookup"><span data-stu-id="d05dc-259">For more information, see the "Permissions" sections of the corresponding topics in Books Online.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d05dc-260">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d05dc-260">Examples</span></span>  
  
### <a name="a-performing-dbcc-checks-on-a-database"></a><span data-ttu-id="d05dc-261">a.</span><span class="sxs-lookup"><span data-stu-id="d05dc-261">A.</span></span> <span data-ttu-id="d05dc-262">Realização de verificações DBCC em um banco de dados</span><span class="sxs-lookup"><span data-stu-id="d05dc-262">Performing DBCC checks on a database</span></span>  
  
```  
sqlmaint -S MyServer -D AdventureWorks2012 -CkDB -CkAl -CkCat -Rpt C:\MyReports\AdvWks_chk.rpt  
```  
  
### <a name="b-updating-statistics-using-a-15-sample-in-all-databases-in-a-plan-also-shrink-any-of-the-database-that-have-reached-110-mb-to-having-only-10-free-space"></a><span data-ttu-id="d05dc-263">B.</span><span class="sxs-lookup"><span data-stu-id="d05dc-263">B.</span></span> <span data-ttu-id="d05dc-264">Atualização de estatísticas usando uma amostra de 15% em todos os bancos de dados em um plano.</span><span class="sxs-lookup"><span data-stu-id="d05dc-264">Updating statistics using a 15% sample in all databases in a plan.</span></span> <span data-ttu-id="d05dc-265">Também, reduz qualquer banco de dados que tenha alcançado 110 MB para ter só 10% de espaço livre.</span><span class="sxs-lookup"><span data-stu-id="d05dc-265">Also, shrink any of the database that have reached 110 MB to having only 10% free space</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -UpdOptiStats 15 -RmUnusedSpace 110 10  
```  
  
### <a name="c-backing-up-all-the-databases-in-a-plan-to-their-individual-subdirectories-in-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory-also-delete-any-backups-older-than-2-weeks"></a><span data-ttu-id="d05dc-266">C.</span><span class="sxs-lookup"><span data-stu-id="d05dc-266">C.</span></span> <span data-ttu-id="d05dc-267">Realização de backup de todos os bancos de dados em um plano em seus subdiretórios individuais no diretório padrão x:\Arquivos de Programas\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span><span class="sxs-lookup"><span data-stu-id="d05dc-267">Backing up all the databases in a plan to their individual subdirectories in the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span> <span data-ttu-id="d05dc-268">Exclui também qualquer backup com mais de 2 semanas</span><span class="sxs-lookup"><span data-stu-id="d05dc-268">Also, delete any backups older than 2 weeks</span></span>  
  
```  
sqlmaint -S MyServer -PlanName MyUserDBPlan -BkUpDB -BkUpMedia DISK -UseDefDir -CrBkSubDir -DelBkUps 2weeks  
```  
  
### <a name="d-backing-up-a-database-to-the-default-xprogram-filesmicrosoft-sql-servermssql12mssqlservermssqlbackup-directory"></a><span data-ttu-id="d05dc-269">D.</span><span class="sxs-lookup"><span data-stu-id="d05dc-269">D.</span></span> <span data-ttu-id="d05dc-270">Fazendo backup de um banco de dados para o padrão X:\Arquivos de Programas\microsoft SQL Server\MSSQL12. Diretório MSSQLSERVER\MSSQL\Backup. </span><span class="sxs-lookup"><span data-stu-id="d05dc-270">Backing up a database to the default x:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup directory.</span></span>\  
  
```  
sqlmaint -S MyServer -BkUpDB -BkUpMedia DISK -UseDefDir  
```  
  
## <a name="see-also"></a><span data-ttu-id="d05dc-271">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d05dc-271">See Also</span></span>  
 <span data-ttu-id="d05dc-272">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d05dc-272">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="d05dc-273">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d05dc-273">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
