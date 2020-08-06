---
title: 'Exemplo: Criando um alerta de SQL Server Agent usando o provedor WMI para eventos de servidor | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SQL Server Agent [WMI]
- WMI Provider for Server Events, samples
- sample applications [WMI]
ms.assetid: d44811c7-cd46-4017-b284-c863ca088e8f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f23a3a8738435dc6a27a230f4521300a3ee2470f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681457"
---
# <a name="sample-creating-a-sql-server-agent-alert-by-using-the-wmi-provider-for-server-events"></a><span data-ttu-id="56e55-102">Exemplo: Criação de um alerta do SQL Server Agent usando o provedor WMI para eventos do servidor</span><span class="sxs-lookup"><span data-stu-id="56e55-102">Sample: Creating a SQL Server Agent Alert by Using the WMI Provider for Server Events</span></span>
  <span data-ttu-id="56e55-103">Uma forma comum de usar o Provedor de eventos de WMI é criar alertas do SQL Server Agent que respondem a eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="56e55-103">One common way to use the WMI Event Provider is to create SQL Server Agent alerts that respond to specific events.</span></span> <span data-ttu-id="56e55-104">O seguinte exemplo apresenta um alerta simples que salva eventos de gráfico de deadlock XML em uma tabela para análise posterior.</span><span class="sxs-lookup"><span data-stu-id="56e55-104">The following sample presents a simple alert that saves XML deadlock graph events in a table for later analysis.</span></span> <span data-ttu-id="56e55-105">O SQL Server Agent envia uma solicitação WQL, recebe eventos WMI, e executa um trabalho em resposta ao evento.</span><span class="sxs-lookup"><span data-stu-id="56e55-105">SQL Server Agent submits a WQL request, receives WMI events, and runs a job in response to the event.</span></span> <span data-ttu-id="56e55-106">Observe que, embora vários objetos do Service Broker estejam envolvidos no processamento da mensagem de notificação, o Provedor de eventos de WMI manipula os detalhes da criação e do gerenciamento desses objetos.</span><span class="sxs-lookup"><span data-stu-id="56e55-106">Notice that, although several Service Broker objects are involved in processing the notification message, the WMI Event Provider handles the details of creating and managing these objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56e55-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="56e55-107">Example</span></span>  
 <span data-ttu-id="56e55-108">Primeiro, uma tabela é criada no banco de dados `AdventureWorks` para conter o evento de gráfico de deadlock.</span><span class="sxs-lookup"><span data-stu-id="56e55-108">First, a table is created in the `AdventureWorks` database to hold the deadlock graph event.</span></span> <span data-ttu-id="56e55-109">A tabela contém duas colunas: a coluna `AlertTime` contém a hora em que o alerta é executado e a coluna `DeadlockGraph`, o documento XML que contém o gráfico de deadlock.</span><span class="sxs-lookup"><span data-stu-id="56e55-109">The table contains two columns: The `AlertTime` column holds the time that the alert runs, and the `DeadlockGraph` column holds the XML document that contains the deadlock graph.</span></span>  
  
 <span data-ttu-id="56e55-110">Então, o alerta é criado.</span><span class="sxs-lookup"><span data-stu-id="56e55-110">Then, the alert is created.</span></span> <span data-ttu-id="56e55-111">Primeiro, o script cria o trabalho que o alerta irá executar, depois adiciona uma etapa de trabalho ao trabalho e direciona o trabalho para a instância atual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56e55-111">The script first creates the job that the alert will run, adds a job step to the job, and targets the job to the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="56e55-112">Então, o script cria o alerta.</span><span class="sxs-lookup"><span data-stu-id="56e55-112">The script then creates the alert.</span></span>  
  
 <span data-ttu-id="56e55-113">A etapa de trabalho recupera a propriedade **TextData** da instância de evento WMI e insere esse valor na coluna **DeadlockGraph** da tabela **DeadlockEvents** .</span><span class="sxs-lookup"><span data-stu-id="56e55-113">The job step retrieves the **TextData** property of the WMI event instance and inserts that value into the **DeadlockGraph** column of the **DeadlockEvents** table.</span></span> <span data-ttu-id="56e55-114">Observe que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] converte implicitamente a cadeia de caracteres para o formato XML.</span><span class="sxs-lookup"><span data-stu-id="56e55-114">Notice that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implicitly converts the string into XML format.</span></span> <span data-ttu-id="56e55-115">Como a etapa de trabalho usa o subsistema [!INCLUDE[tsql](../../includes/tsql-md.md)], ela não especifica um proxy.</span><span class="sxs-lookup"><span data-stu-id="56e55-115">Because the job step uses the [!INCLUDE[tsql](../../includes/tsql-md.md)] subsystem, the job step does not specify a proxy.</span></span>  
  
 <span data-ttu-id="56e55-116">O alerta executa o trabalho sempre que um evento de rastreamento do grafo deadlock é registrado.</span><span class="sxs-lookup"><span data-stu-id="56e55-116">The alert runs the job whenever a deadlock graph trace event would be logged.</span></span> <span data-ttu-id="56e55-117">Para um alerta de WMI, o SQL Server Agent cria uma consulta de notificação que usa o namespace e a instrução WQL especificados.</span><span class="sxs-lookup"><span data-stu-id="56e55-117">For a WMI alert, SQL Server Agent creates a notification query using the namespace and WQL statement specified.</span></span> <span data-ttu-id="56e55-118">Para esse alerta, o SQL Server Agent monitora a instância padrão no computador local.</span><span class="sxs-lookup"><span data-stu-id="56e55-118">For this alert, SQL Server Agent monitors the default instance on the local computer.</span></span> <span data-ttu-id="56e55-119">A instrução WQL solicita quaisquer eventos `DEADLOCK_GRAPH` na instância padrão.</span><span class="sxs-lookup"><span data-stu-id="56e55-119">The WQL statement requests any `DEADLOCK_GRAPH` event in the default instance.</span></span> <span data-ttu-id="56e55-120">Para alterar a instância que o alerta monitora, substitua o nome de instância para `MSSQLSERVER` no `@wmi_namespace` para o alerta.</span><span class="sxs-lookup"><span data-stu-id="56e55-120">To change the instance that the alert monitors, substitute the instance name for `MSSQLSERVER` in the `@wmi_namespace` for the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56e55-121">Para SQL Server Agent receber eventos WMI, o [!INCLUDE[ssSB](../../includes/sssb-md.md)] deve estar habilitado no **msdb** e no [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56e55-121">For SQL Server Agent to receive WMI events, [!INCLUDE[ssSB](../../includes/sssb-md.md)] must be enabled in **msdb** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
IF OBJECT_ID('DeadlockEvents', 'U') IS NOT NULL  
BEGIN  
    DROP TABLE DeadlockEvents ;  
END ;  
GO  
  
CREATE TABLE DeadlockEvents  
    (AlertTime DATETIME, DeadlockGraph XML) ;  
GO  
-- Add a job for the alert to run.  
  
EXEC  msdb.dbo.sp_add_job @job_name=N'Capture Deadlock Graph',   
    @enabled=1,   
    @description=N'Job for responding to DEADLOCK_GRAPH events' ;  
GO  
  
-- Add a jobstep that inserts the current time and the deadlock graph into  
-- the DeadlockEvents table.  
  
EXEC msdb.dbo.sp_add_jobstep  
    @job_name = N'Capture Deadlock Graph',  
    @step_name=N'Insert graph into LogEvents',  
    @step_id=1,   
    @on_success_action=1,   
    @on_fail_action=2,   
    @subsystem=N'TSQL',   
    @command= N'INSERT INTO DeadlockEvents  
                (AlertTime, DeadlockGraph)  
                VALUES (getdate(), N''$(ESCAPE_SQUOTE(WMI(TextData)))'')',  
    @database_name=N'AdventureWorks' ;  
GO  
  
-- Set the job server for the job to the current instance of SQL Server.  
  
EXEC msdb.dbo.sp_add_jobserver @job_name = N'Capture Deadlock Graph' ;  
GO  
  
-- Add an alert that responds to all DEADLOCK_GRAPH events for  
-- the default instance. To monitor deadlocks for a different instance,  
-- change MSSQLSERVER to the name of the instance.  
  
EXEC msdb.dbo.sp_add_alert @name=N'Respond to DEADLOCK_GRAPH',   
@wmi_namespace=N'\\.\root\Microsoft\SqlServer\ServerEvents\MSSQLSERVER',   
    @wmi_query=N'SELECT * FROM DEADLOCK_GRAPH',   
    @job_name='Capture Deadlock Graph' ;  
GO  
```  
  
## <a name="testing-the-sample"></a><span data-ttu-id="56e55-122">Testando o exemplo</span><span class="sxs-lookup"><span data-stu-id="56e55-122">Testing the Sample</span></span>  
 <span data-ttu-id="56e55-123">Para ver a execução do trabalho, provoque um deadlock.</span><span class="sxs-lookup"><span data-stu-id="56e55-123">To see the job run, provoke a deadlock.</span></span> <span data-ttu-id="56e55-124">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , abra duas guias de **consulta SQL** e conecte ambas as consultas à mesma instância.</span><span class="sxs-lookup"><span data-stu-id="56e55-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open two **SQL Query** tabs and connect both queries to the same instance.</span></span> <span data-ttu-id="56e55-125">Execute o seguinte script em um das guias de consulta.</span><span class="sxs-lookup"><span data-stu-id="56e55-125">Run the following script in one of the query tabs.</span></span> <span data-ttu-id="56e55-126">Este script produz um conjunto de resultados e é encerrado.</span><span class="sxs-lookup"><span data-stu-id="56e55-126">This script produces one result set and finishes.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="56e55-127">Execute o script a seguir na segunda guia de consulta. Esse script produz um conjunto de resultados e, em seguida, os bloqueia, aguardando a aquisição de um bloqueio `Production.Product` .</span><span class="sxs-lookup"><span data-stu-id="56e55-127">Run the following script in the second query tab. This script produces one result set and then blocks, waiting to acquire a lock on `Production.Product`.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="56e55-128">Execute o script a seguir na primeira guia de consulta. Esse script é bloqueado, aguardando a aquisição de um bloqueio `Production.Location` .</span><span class="sxs-lookup"><span data-stu-id="56e55-128">Run the following script in the first query tab. This script blocks, waiting to acquire a lock on `Production.Location`.</span></span> <span data-ttu-id="56e55-129">Depois de um tempo limite curto, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escolherá este script ou o script no exemplo como a vítima de deadlock e encerrará a transação.</span><span class="sxs-lookup"><span data-stu-id="56e55-129">After a short time-out, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will choose either this script or the script in the sample as the deadlock victim and end the transaction.</span></span>  
  
```  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="56e55-130">Depois de provocar o deadlock, aguarde algum tempo para o SQL Server Agent ativar o alerta e executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="56e55-130">After provoking the deadlock, wait several moments for SQL Server Agent to activate the alert and run the job.</span></span> <span data-ttu-id="56e55-131">Examine o conteúdo da tabela `DeadlockEvents` executando o seguinte script:</span><span class="sxs-lookup"><span data-stu-id="56e55-131">Examine the contents of the `DeadlockEvents` table by running the following script:</span></span>  
  
```  
SELECT * FROM DeadlockEvents ;  
GO  
```  
  
 <span data-ttu-id="56e55-132">A coluna `DeadlockGraph` deve conter um documento XML que mostra todas as propriedades do evento do gráfico de deadlock.</span><span class="sxs-lookup"><span data-stu-id="56e55-132">The `DeadlockGraph` column should contain an XML document that shows all the properties of the deadlock graph event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e55-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="56e55-133">See Also</span></span>  
 [<span data-ttu-id="56e55-134">Provedor WMI para conceitos de eventos de servidor</span><span class="sxs-lookup"><span data-stu-id="56e55-134">WMI Provider for Server Events Concepts</span></span>](wmi-provider-for-server-events-concepts.md)  
  
  
