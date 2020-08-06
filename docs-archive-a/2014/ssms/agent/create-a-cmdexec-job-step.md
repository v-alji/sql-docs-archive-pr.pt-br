---
title: Criar uma etapa de trabalho CmdExec | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CmdExec jobs
ms.assetid: b48da5b4-6fe7-4eb7-bade-dc7d697c6d5c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48c557b8ea4228d27b73d361c50aac62232d1e00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573361"
---
# <a name="create-a-cmdexec-job-step"></a><span data-ttu-id="2d124-102">Create a CmdExec Job Step</span><span class="sxs-lookup"><span data-stu-id="2d124-102">Create a CmdExec Job Step</span></span>
  <span data-ttu-id="2d124-103">Este tópico descreve como criar e definir uma [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] etapa de trabalho do Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] que usa um programa executável ou um comando do sistema operacional usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="2d124-103">This topic describes how to create and define a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that uses an executable program or operating system command by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="2d124-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="2d124-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2d124-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="2d124-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2d124-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="2d124-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2d124-107">**Para criar uma etapa de trabalho CmdExec, usando:**</span><span class="sxs-lookup"><span data-stu-id="2d124-107">**To create a CmdExec job step, using:**</span></span>  
  
     [<span data-ttu-id="2d124-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d124-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="2d124-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d124-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="2d124-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="2d124-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2d124-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2d124-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2d124-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="2d124-112">Security</span></span>  
 <span data-ttu-id="2d124-113">Por padrão, só membros da função de servidor fixa **sysadmin** podem criar etapas de trabalho CmdExec.</span><span class="sxs-lookup"><span data-stu-id="2d124-113">By default, only members of the **sysadmin** fixed server role can create CmdExec job steps.</span></span> <span data-ttu-id="2d124-114">Essas etapas de trabalho são executadas no contexto da conta de serviço do SQL Server Agent, a menos que o usuário de **sysadmin** crie uma conta proxy.</span><span class="sxs-lookup"><span data-stu-id="2d124-114">These job steps run under the context of the SQL Server Agent service account unless the **sysadmin** user creates a proxy account.</span></span> <span data-ttu-id="2d124-115">Usuários que não sejam membros da função **sysadmin** poderão criar etapas de trabalho CmdExec se tiverem acesso à conta proxy de CmdExec.</span><span class="sxs-lookup"><span data-stu-id="2d124-115">Users who are not members of the **sysadmin** role can create CmdExec job steps if they have access to a CmdExec proxy account.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2d124-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="2d124-116">Permissions</span></span>  
 <span data-ttu-id="2d124-117">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="2d124-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="2d124-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d124-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="2d124-119">Para criar uma etapa de trabalho CmdExec</span><span class="sxs-lookup"><span data-stu-id="2d124-119">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="2d124-120">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="2d124-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2d124-121">Expanda **SQL Server Agent**, crie um novo trabalho ou clique com o botão direito do mouse em um trabalho existente e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2d124-121">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2d124-122">Na caixa de diálogo **Propriedades do Trabalho** , clique na página **Etapas** e, em seguida, em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="2d124-122">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="2d124-123">Na caixa de diálogo **Nova Etapa de Trabalho** , digite o **Nome da etapa**de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2d124-123">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="2d124-124">Na lista **Tipo** , escolha **Sistema operacional (CmdExec)**.</span><span class="sxs-lookup"><span data-stu-id="2d124-124">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
6.  <span data-ttu-id="2d124-125">Na lista **Executar como** , selecione a conta proxy com as credenciais que o trabalho usará.</span><span class="sxs-lookup"><span data-stu-id="2d124-125">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="2d124-126">Por padrão, etapas de trabalho CmdExec são executadas no contexto da conta do serviço do SQL Server Agent .</span><span class="sxs-lookup"><span data-stu-id="2d124-126">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
7.  <span data-ttu-id="2d124-127">Na caixa **Código de saída do processo de um comando bem sucedido** , insira um valor de 0 a 999999.</span><span class="sxs-lookup"><span data-stu-id="2d124-127">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
8.  <span data-ttu-id="2d124-128">Na caixa **Comando** , digite o comando de sistema operacional ou programa executável.</span><span class="sxs-lookup"><span data-stu-id="2d124-128">In the **Command** box, enter the operating system command or executable program.</span></span> <span data-ttu-id="2d124-129">Consulte "Usando Transact T-SQL para obter um exemplo.</span><span class="sxs-lookup"><span data-stu-id="2d124-129">See "Using Transact T-SQL for an example.</span></span>  
  
9. <span data-ttu-id="2d124-130">Clique na página **Avançado** para definir opções para a etapa de trabalho, como a ação a tomar em caso de êxito ou falha da etapa, quantas vezes o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve tentar executar a etapa e o arquivo onde o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent pode gravar a saída da etapa.</span><span class="sxs-lookup"><span data-stu-id="2d124-130">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="2d124-131">Só membros da função de servidor fixa **sysadmin** podem gravar a saída de etapas de trabalho em um arquivo do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2d124-131">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="2d124-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d124-132">Using Transact-SQL</span></span>  
  
### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="2d124-133">Para criar uma etapa de trabalho CmdExec</span><span class="sxs-lookup"><span data-stu-id="2d124-133">To create a CmdExec job step</span></span>  
  
1.  <span data-ttu-id="2d124-134">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d124-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2d124-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2d124-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2d124-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2d124-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a job step that uses CmdExec  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'CMDEXEC',  
        @command = C:\clickme_scripts\SQL11\PostBOLReorg GetHsX.exe',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="2d124-137">Para obter mais informações, consulte [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="2d124-137">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="2d124-138">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="2d124-138">Using SQL Server Management Objects</span></span>  

### <a name="to-create-a-cmdexec-job-step"></a><span data-ttu-id="2d124-139">Para criar uma etapa de trabalho CmdExec</span><span class="sxs-lookup"><span data-stu-id="2d124-139">To create a CmdExec job step</span></span>
  
 <span data-ttu-id="2d124-140">Use a classe `JobStep` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d124-140">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
