---
title: Criar uma etapa de trabalho de script do PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- PowerShell [SQL Server], job steps
- jobs [SQL Server Agent], PowerShell
- job steps [PowerShell]
- SQL Server Agent jobs, PowerShell steps
ms.assetid: 50afcf84-fae0-4eb5-9b0f-f2cf144c1433
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4232cdfa584fdcc2e13786ecc9bd00f0c6fe7066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573363"
---
# <a name="create-a-powershell-script-job-step"></a><span data-ttu-id="007c1-102">Create a PowerShell Script Job Step</span><span class="sxs-lookup"><span data-stu-id="007c1-102">Create a PowerShell Script Job Step</span></span>
  <span data-ttu-id="007c1-103">Este tópico descreve como criar e definir uma etapa de trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que execute um script PowerShell no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="007c1-103">This topic describes how to create and define a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes a PowerShell script in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="007c1-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="007c1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="007c1-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="007c1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="007c1-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="007c1-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="007c1-107">**Para criar uma etapa de trabalho de script do PowerShell usando:**</span><span class="sxs-lookup"><span data-stu-id="007c1-107">**To create a PowerShell Script job step, using:**</span></span>  
  
     [<span data-ttu-id="007c1-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="007c1-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="007c1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="007c1-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="007c1-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="007c1-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="007c1-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="007c1-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="007c1-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="007c1-112">Security</span></span>  
 <span data-ttu-id="007c1-113">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="007c1-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="007c1-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="007c1-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="007c1-115">Para criar uma etapa de trabalho de script PowerShell</span><span class="sxs-lookup"><span data-stu-id="007c1-115">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="007c1-116">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="007c1-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="007c1-117">Expanda **SQL Server Agent**, crie um novo trabalho ou clique com o botão direito do mouse em um trabalho existente e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="007c1-117">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="007c1-118">Para obter mais informações sobre como criar um trabalho, consulte [Criando trabalhos](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="007c1-118">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="007c1-119">Na caixa de diálogo **Propriedades do Trabalho** , clique na página **Etapas** e, em seguida, em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="007c1-119">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="007c1-120">Na caixa de diálogo **Nova Etapa de Trabalho** , digite o **Nome da etapa**de trabalho.</span><span class="sxs-lookup"><span data-stu-id="007c1-120">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="007c1-121">Na lista **Tipo** , clique em **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="007c1-121">In the **Type** list, click **PowerShell**.</span></span>  
  
6.  <span data-ttu-id="007c1-122">Na lista **Executar como** , selecione a conta proxy com as credenciais que o trabalho usará.</span><span class="sxs-lookup"><span data-stu-id="007c1-122">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
7.  <span data-ttu-id="007c1-123">Na caixa **Comando** , digite a sintaxe do script PowerShell que será executada para a etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="007c1-123">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="007c1-124">Como alternativa, clique em **Abrir** e selecione um arquivo que contenha a sintaxe de script.</span><span class="sxs-lookup"><span data-stu-id="007c1-124">Alternately, click **Open** and select a file containing the script syntax.</span></span> <span data-ttu-id="007c1-125">Para obter um exemplo de um script do PowerShell, consulte **Como usar o Transact-SQL** abaixo.</span><span class="sxs-lookup"><span data-stu-id="007c1-125">For an example of a PowerShell script, see **Using Transact-SQL** below.</span></span>  
  
8.  <span data-ttu-id="007c1-126">Clique na página **Avançado** para definir as seguintes opções de etapa de trabalho: a ação a tomar em caso de êxito ou falha da etapa, quantas vezes o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve tentar executar a etapa e com que frequência.</span><span class="sxs-lookup"><span data-stu-id="007c1-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="007c1-127">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="007c1-127">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-powershell-script-job-step"></a><span data-ttu-id="007c1-128">Para criar uma etapa de trabalho de script PowerShell</span><span class="sxs-lookup"><span data-stu-id="007c1-128">To create a PowerShell Script job step</span></span>  
  
1.  <span data-ttu-id="007c1-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="007c1-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="007c1-130">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="007c1-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="007c1-131">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="007c1-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a PowerShell job step that finds the processes that use more than 1000 MB of memory and kills them  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Kills all processes that use more than 1000 MB of memory',  
        @subsystem = N'PowerShell',  
        @command = N'Get-Process | Where-Object { $_.WS -gt 1000MB } | Stop-Process',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="007c1-132">Para obter mais informações, consulte [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="007c1-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="007c1-133">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="007c1-133">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="007c1-134">**Para criar uma etapa de trabalho de script PowerShell**</span><span class="sxs-lookup"><span data-stu-id="007c1-134">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="007c1-135">Use a classe `JobStep` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="007c1-135">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
