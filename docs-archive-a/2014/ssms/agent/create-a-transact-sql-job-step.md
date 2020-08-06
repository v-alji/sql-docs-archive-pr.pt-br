---
title: Criar uma etapa de trabalho Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: 69c571a7-debe-4063-9d38-e4b6a1e8e84c
author: stevestein
ms.author: sstein
ms.openlocfilehash: b83ee944d2ca5c10ff1b77f3e6e6da6054b5c99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683911"
---
# <a name="create-a-transact-sql-job-step"></a><span data-ttu-id="e7341-102">Create a Transact-SQL Job Step</span><span class="sxs-lookup"><span data-stu-id="e7341-102">Create a Transact-SQL Job Step</span></span>
  <span data-ttu-id="e7341-103">Este tópico descreve como criar uma [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] etapa de trabalho do Agent que executa [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , o ou o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="e7341-103">This topic describes how to create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step that executes [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="e7341-104">Esses scripts de etapa de trabalho podem chamar procedimentos armazenados e procedimentos armazenados estendidos.</span><span class="sxs-lookup"><span data-stu-id="e7341-104">These job step scripts may call stored procedures and extended stored procedures.</span></span> <span data-ttu-id="e7341-105">Uma mesma etapa de trabalho [!INCLUDE[tsql](../../includes/tsql-md.md)] pode conter vários lotes e comandos GO inseridos.</span><span class="sxs-lookup"><span data-stu-id="e7341-105">A single [!INCLUDE[tsql](../../includes/tsql-md.md)] job step can contain multiple batches and embedded GO commands.</span></span> <span data-ttu-id="e7341-106">Para obter mais informações sobre como criar um trabalho, consulte [Criando trabalhos](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e7341-106">For more information on creating a job, see [Creating Jobs](create-jobs.md).</span></span>  
  
 <span data-ttu-id="e7341-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="e7341-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e7341-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="e7341-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e7341-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="e7341-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e7341-110">**Para criar uma etapa de trabalho Transact-SQL usando:**</span><span class="sxs-lookup"><span data-stu-id="e7341-110">**To create a Transact-SQL job step, using:**</span></span>  
  
     [<span data-ttu-id="e7341-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7341-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="e7341-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7341-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="e7341-113">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e7341-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e7341-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e7341-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e7341-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="e7341-115">Security</span></span>  
 <span data-ttu-id="e7341-116">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e7341-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e7341-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7341-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="e7341-118">Para criar uma etapa de trabalho Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7341-118">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="e7341-119">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="e7341-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e7341-120">Expanda **SQL Server Agent**, crie um novo trabalho ou clique com o botão direito do mouse em um trabalho existente e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e7341-120">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e7341-121">Na caixa de diálogo **Propriedades do Trabalho** , clique na página **Etapas** e, em seguida, em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="e7341-121">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="e7341-122">Na caixa de diálogo **Nova Etapa de Trabalho** , digite o **Nome da etapa**de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e7341-122">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="e7341-123">Na lista **Tipo** , clique em **Script Transact-SQL (TSQL)**.</span><span class="sxs-lookup"><span data-stu-id="e7341-123">In the **Type** list, click **Transact-SQL Script (TSQL)**.</span></span>  
  
6.  <span data-ttu-id="e7341-124">Na caixa **Comando** , digite os lotes de comandos [!INCLUDE[tsql](../../includes/tsql-md.md)] ou clique em **Abrir** para selecionar um arquivo [!INCLUDE[tsql](../../includes/tsql-md.md)] a ser usado como comando.</span><span class="sxs-lookup"><span data-stu-id="e7341-124">In the **Command** box, type the [!INCLUDE[tsql](../../includes/tsql-md.md)] command batches, or click **Open** to select a [!INCLUDE[tsql](../../includes/tsql-md.md)] file to use as the command.</span></span>  
  
7.  <span data-ttu-id="e7341-125">Clique em **Analisar** para verificar a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="e7341-125">Click **Parse** to check your syntax.</span></span>  
  
8.  <span data-ttu-id="e7341-126">A mensagem "Êxito da análise" será exibida se a sintaxe estiver correta.</span><span class="sxs-lookup"><span data-stu-id="e7341-126">The message "Parse succeeded" is displayed when your syntax is correct.</span></span> <span data-ttu-id="e7341-127">Se um erro for encontrado, corrija a sintaxe antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e7341-127">If an error is found, correct the syntax before continuing.</span></span>  
  
9. <span data-ttu-id="e7341-128">Clique na página **Avançado** para definir opções para a etapa de trabalho, tais como: que ação deve ser adotada em caso de êxito ou falha da etapa, quantas vezes o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve tentar executar a etapa e em que arquivo ou tabela o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve gravar a saída da etapa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e7341-128">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file or table where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="e7341-129">Só membros da função de servidor fixa **sysadmin** podem gravar a saída de etapas de trabalho em um arquivo do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e7341-129">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span> <span data-ttu-id="e7341-130">Todos os usuários do SQL Server Agent podem registrar a saída em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="e7341-130">All SQL Server Agent users can log output to a table.</span></span>  
  
10. <span data-ttu-id="e7341-131">Se você for membro da função de servidor fixa **sysadmin** e desejar executar a etapa de trabalho como um logon SQL diferente, selecione esse logon na lista **Executar como usuário** .</span><span class="sxs-lookup"><span data-stu-id="e7341-131">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e7341-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7341-132">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-transact-sql-job-step"></a><span data-ttu-id="e7341-133">Para criar uma etapa de trabalho Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7341-133">To create a Transact-SQL job step</span></span>  
  
1.  <span data-ttu-id="e7341-134">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7341-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e7341-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e7341-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e7341-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e7341-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses Transact-SQL  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="e7341-137">Para obter mais informações, consulte [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e7341-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="e7341-138">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e7341-138">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="e7341-139">**Para criar uma etapa de trabalho Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="e7341-139">**To create a Transact-SQL job step**</span></span>  
  
 <span data-ttu-id="e7341-140">Use a classe `JobStep` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7341-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
