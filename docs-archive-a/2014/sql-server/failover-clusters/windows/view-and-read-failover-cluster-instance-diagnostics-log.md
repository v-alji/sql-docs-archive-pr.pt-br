---
title: Exibir e ler o log de diagnóstico da instância do cluster de failover | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 68074bd5-be9d-4487-a320-5b51ef8e2b2d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 774dc4ec4a02c72420d004909cb7e6ee1b31f3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573561"
---
# <a name="view-and-read-failover-cluster-instance-diagnostics-log"></a><span data-ttu-id="c51f6-102">Exibir e ler o log de diagnóstico da instância do cluster de failover</span><span class="sxs-lookup"><span data-stu-id="c51f6-102">View and Read Failover Cluster Instance Diagnostics Log</span></span>
  <span data-ttu-id="c51f6-103">Todos os erros críticos e eventos de aviso para a DLL de Recursos do SQL Server são gravados no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="c51f6-103">All critical errors and warning events for the SQL Server Resource DLL are written to the Windows event log.</span></span> <span data-ttu-id="c51f6-104">Um log em execução das informações de diagnóstico específicas do SQL Server é capturado pelo procedimento armazenado do sistema [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) e gravado nos arquivos de log de diagnóstico do cluster de failover do SQL Server (também conhecidos como logs *SQLDIAG*).</span><span class="sxs-lookup"><span data-stu-id="c51f6-104">A running log of the diagnostic information specific to SQL Server is captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) system stored procedure and is written to the SQL Server failover cluster diagnostics (also known as the *SQLDIAG* logs) log files.</span></span>  
  
-   <span data-ttu-id="c51f6-105">**Antes de começar:**  [Recomendações](#Recommendations), [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="c51f6-105">**Before you begin:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="c51f6-106">**Para exibir o Log de Diagnóstico, usando:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="c51f6-106">**To View the Diagnostic Log, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="c51f6-107">**Para configurar definições do Log de Diagnóstico, usando:** [Transact-SQL](#TsqlConfigure)</span><span class="sxs-lookup"><span data-stu-id="c51f6-107">**To Configure Diagnostic Log settings, using:** [Transact-SQL](#TsqlConfigure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c51f6-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c51f6-108">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c51f6-109">Recomendações</span><span class="sxs-lookup"><span data-stu-id="c51f6-109">Recommendations</span></span>  
 <span data-ttu-id="c51f6-110">Por padrão, o SQLDIAG é armazenado em uma pasta de LOG local do diretório da instância do SQL Server, por exemplo, ' C\Program Files\Microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\LOG ' do nó proprietário da FCI (instância de cluster de failover) do AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c51f6-110">By default, the SQLDIAG are stored under a local LOG folder of the SQL Server instance directory, for example, 'C\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\LOG' of the owning node of the AlwaysOn Failover Cluster Instance (FCI).</span></span> <span data-ttu-id="c51f6-111">O tamanho de cada arquivo de log de SQLDIAG é fixo em 100 MB.</span><span class="sxs-lookup"><span data-stu-id="c51f6-111">The size of each SQLDIAG log file is fixed at 100 MB.</span></span> <span data-ttu-id="c51f6-112">Dez arquivos de log desse tipo são armazenados no computador antes de serem reciclados para novos logs.</span><span class="sxs-lookup"><span data-stu-id="c51f6-112">Ten such log files are stored on the computer before they are recycled for new logs.</span></span>  
  
 <span data-ttu-id="c51f6-113">Os logs usam o formato de arquivo de eventos estendidos.</span><span class="sxs-lookup"><span data-stu-id="c51f6-113">The logs use the extended events file format.</span></span> <span data-ttu-id="c51f6-114">A função do sistema **sys.fn_xe_file_target_read_file** pode ser usada para leitura dos arquivos criados por Eventos Estendidos.</span><span class="sxs-lookup"><span data-stu-id="c51f6-114">The **sys.fn_xe_file_target_read_file** system function can be used to read the files that are created by Extended Events.</span></span> <span data-ttu-id="c51f6-115">É retornado um evento, em formato XML, por linha.</span><span class="sxs-lookup"><span data-stu-id="c51f6-115">One event, in XML format, is returned per row.</span></span> <span data-ttu-id="c51f6-116">Consulte a exibição do sistema para analisar os dados XML como um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="c51f6-116">Query the system view to parse the XML data as a result-set.</span></span> <span data-ttu-id="c51f6-117">Para obter mais informações, veja [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c51f6-117">For more information, see [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c51f6-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="c51f6-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c51f6-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="c51f6-119">Permissions</span></span>  
 <span data-ttu-id="c51f6-120">A permissão VIEW SERVER STATE é necessária para executar **fn_xe_file_target_read_file**.</span><span class="sxs-lookup"><span data-stu-id="c51f6-120">VIEW SERVER STATE permission is needed to run **fn_xe_file_target_read_file**.</span></span>  
  
 <span data-ttu-id="c51f6-121">Abra o SQL Server Management Studio como administrador</span><span class="sxs-lookup"><span data-stu-id="c51f6-121">Open SQL Server Management Studio as Administrator</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c51f6-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c51f6-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c51f6-123">**Para exibir os arquivos de log de diagnóstico:**</span><span class="sxs-lookup"><span data-stu-id="c51f6-123">**To view the Diagnostic log files:**</span></span>  
  
1.  <span data-ttu-id="c51f6-124">No menu **Arquivo** , selecione **Abrir**, **Arquivo**e escolha o arquivo de log de diagnóstico a ser exibido.</span><span class="sxs-lookup"><span data-stu-id="c51f6-124">From the **File** menu, select **Open**, **File**, and choose the diagnostic log file you want to view.</span></span>  
  
2.  <span data-ttu-id="c51f6-125">Os eventos são exibidos como linhas no painel direito e, por padrão, **nome**e **carimbo de data/hora** são as únicas duas colunas exibidas.</span><span class="sxs-lookup"><span data-stu-id="c51f6-125">The events are displayed as rows in the right pane, and by default **name**, and **timestamp** are the only two columns displayed.</span></span>  
  
     <span data-ttu-id="c51f6-126">Isso também ativa o menu **ExtendedEvents** .</span><span class="sxs-lookup"><span data-stu-id="c51f6-126">This also activates the **ExtendedEvents** menu.</span></span>  
  
3.  <span data-ttu-id="c51f6-127">Para ver mais colunas, vá até o menu **ExtendedEvents** e marque **Selecionar Colunas**.</span><span class="sxs-lookup"><span data-stu-id="c51f6-127">To see more columns, go the **ExtendedEvents** menu, and select **Choose Columns**.</span></span>  
  
     <span data-ttu-id="c51f6-128">Uma caixa de diálogo é aberta com as colunas disponíveis que lhe permitem selecionar as colunas para exibição.</span><span class="sxs-lookup"><span data-stu-id="c51f6-128">A dialog box opens with the available columns allowing you to select the columns for display.</span></span>  
  
4.  <span data-ttu-id="c51f6-129">Você pode filtrar e classificar os dados de evento usando o menu **ExtendedEvents** e selecionando a opção **Filtrar** .</span><span class="sxs-lookup"><span data-stu-id="c51f6-129">You can filter, and sort the event data using the **ExtendedEvents** menu and selecting the **Filter** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c51f6-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c51f6-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="c51f6-131">**Para exibir os arquivos de log de diagnóstico:**</span><span class="sxs-lookup"><span data-stu-id="c51f6-131">**To view the Diagnostic log files:**</span></span>  
  
 <span data-ttu-id="c51f6-132">Para exibir todos os itens do log no arquivo de log SQLDIAG, use a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="c51f6-132">To view all the log items in the SQLDIAG log file, use the following query:</span></span>  
  
```  
SELECT  
xml_data.value('(event/@name)[1]','varchar(max)') AS 'Name'  
,xml_data.value('(event/@package)[1]','varchar(max)') AS 'Package'  
,xml_data.value('(event/@timestamp)[1]','datetime') AS 'Time'  
,xml_data.value('(event/data[@name=''state'']/value)[1]','int') AS 'State'  
,xml_data.value('(event/data[@name=''state_desc'']/text)[1]','varchar(max)') AS 'State Description'  
,xml_data.value('(event/data[@name=''failure_condition_level'']/value)[1]','int') AS 'Failure Conditions'  
,xml_data.value('(event/data[@name=''node_name'']/value)[1]','varchar(max)') AS 'Node_Name'  
,xml_data.value('(event/data[@name=''instancename'']/value)[1]','varchar(max)') AS 'Instance Name'  
,xml_data.value('(event/data[@name=''creation time'']/value)[1]','datetime') AS 'Creation Time'  
,xml_data.value('(event/data[@name=''component'']/value)[1]','varchar(max)') AS 'Component'  
,xml_data.value('(event/data[@name=''data'']/value)[1]','varchar(max)') AS 'Data'  
,xml_data.value('(event/data[@name=''info'']/value)[1]','varchar(max)') AS 'Info'  
FROM  
 ( SELECT object_name AS 'event'  
  ,CONVERT(xml,event_data) AS 'xml_data'  
  FROM sys.fn_xe_file_target_read_file('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log\SQLNODE1_MSSQLSERVER_SQLDIAG_0_129936003752530000.xel',NULL,NULL,NULL)   
)   
AS XEventData  
ORDER BY Time;  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c51f6-133">Você pode filtrar os resultados para componentes específicos ou um estado usando a cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="c51f6-133">You can filter the results for specific components or state using the WHERE clause.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlConfigure"></a> <span data-ttu-id="c51f6-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c51f6-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="c51f6-135">**Para configurar as propriedades de log de diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="c51f6-135">**To configure the Diagnostic Log Properties**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c51f6-136">Para obter um exemplo desse procedimento, veja [Exemplo (Transact-SQL)](#TsqlExample), mais adiante nesta seção.</span><span class="sxs-lookup"><span data-stu-id="c51f6-136">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
 <span data-ttu-id="c51f6-137">Usando a instrução DDL (linguagem de definição de dados), `ALTER SERVER CONFIGURATION` você pode iniciar ou parar o log de dados de diagnóstico capturados pelo [sp_server_diagnostics &#40;procedimento de&#41;TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) e definir parâmetros de configuração de log SQLdiag, como a contagem de sobreposição do arquivo de log, o tamanho do arquivo de log e o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c51f6-137">Using the Data Definition Language (DDL) statement, `ALTER SERVER CONFIGURATION`, you can start or stop logging diagnostic data captured by the [sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) procedure, and set SQLDIAG log configuration parameters such as the log file rollover count, log file size, and file location.</span></span> <span data-ttu-id="c51f6-138">Para obter detalhes da sintaxe, consulte [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span><span class="sxs-lookup"><span data-stu-id="c51f6-138">For syntax details, see [Setting diagnostic log options](/sql/t-sql/statements/alter-server-configuration-transact-sql#Diagnostic).</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="ConfigTsqlExample"></a> <span data-ttu-id="c51f6-139">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c51f6-139">Examples (Transact-SQL)</span></span>  
  
####  <a name="setting-diagnostic-log-options"></a><a name="TsqlExample"></a> <span data-ttu-id="c51f6-140">Setting diagnostic log options</span><span class="sxs-lookup"><span data-stu-id="c51f6-140">Setting diagnostic log options</span></span>  
 <span data-ttu-id="c51f6-141">Os exemplos desta seção mostram como definir os valores para a opção de log de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c51f6-141">The examples in this section show how to set the values for the diagnostic log option.</span></span>  
  
##### <a name="a-starting-diagnostic-logging"></a><span data-ttu-id="c51f6-142">a.</span><span class="sxs-lookup"><span data-stu-id="c51f6-142">A.</span></span> <span data-ttu-id="c51f6-143">Iniciando o log de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c51f6-143">Starting diagnostic logging</span></span>  
 <span data-ttu-id="c51f6-144">O exemplo a seguir inicia o log de dados de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c51f6-144">The following example starts the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG ON;  
```  
  
##### <a name="b-stopping-diagnostic-logging"></a><span data-ttu-id="c51f6-145">B.</span><span class="sxs-lookup"><span data-stu-id="c51f6-145">B.</span></span> <span data-ttu-id="c51f6-146">Interrompendo o log de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c51f6-146">Stopping diagnostic logging</span></span>  
 <span data-ttu-id="c51f6-147">O exemplo a seguir interrompe o log de dados de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c51f6-147">The following example stops the logging of diagnostic data.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG OFF;  
```  
  
##### <a name="c-specifying-the-location-of-the-diagnostic-logs"></a><span data-ttu-id="c51f6-148">C.</span><span class="sxs-lookup"><span data-stu-id="c51f6-148">C.</span></span> <span data-ttu-id="c51f6-149">Especificando o local dos logs de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c51f6-149">Specifying the location of the diagnostic logs</span></span>  
 <span data-ttu-id="c51f6-150">O exemplo a seguir define o local dos logs de diagnóstico como o caminho do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c51f6-150">The following example sets the location of the diagnostic logs to the specified file path.</span></span>  
  
```  
ALTER SERVER CONFIGURATION  
SET DIAGNOSTICS LOG PATH = 'C:\logs';  
```  
  
##### <a name="d-specifying-the-maximum-size-of-each-diagnostic-log"></a><span data-ttu-id="c51f6-151">D.</span><span class="sxs-lookup"><span data-stu-id="c51f6-151">D.</span></span> <span data-ttu-id="c51f6-152">Especificando o tamanho máximo de cada log de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c51f6-152">Specifying the maximum size of each diagnostic log</span></span>  
 <span data-ttu-id="c51f6-153">O exemplo a seguir define o tamanho máximo de cada log de diagnóstico como 10 megabytes.</span><span class="sxs-lookup"><span data-stu-id="c51f6-153">The following example set the maximum size of each diagnostic log to 10 megabytes.</span></span>  
  
```  
ALTER SERVER CONFIGURATION   
SET DIAGNOSTICS LOG MAX_SIZE = 10 MB;  
```  
  
## <a name="see-also"></a><span data-ttu-id="c51f6-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c51f6-154">See Also</span></span>  
 [<span data-ttu-id="c51f6-155">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="c51f6-155">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
  
  
