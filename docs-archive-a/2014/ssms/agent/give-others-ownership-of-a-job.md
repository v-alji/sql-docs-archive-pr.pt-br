---
title: Conceder a propriedade de um trabalho a outras pessoas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], owners
- owners [SQL Server], jobs
- SQL Server Agent jobs, owners
ms.assetid: 2ded5e9c-4251-4fb1-a047-99f13d150b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2cf03fdc9031ce9761125d95619438837f2959bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569012"
---
# <a name="give-others-ownership-of-a-job"></a><span data-ttu-id="760be-102">Give Others Ownership of a Job</span><span class="sxs-lookup"><span data-stu-id="760be-102">Give Others Ownership of a Job</span></span>
  <span data-ttu-id="760be-103">Este tópico descreve como reatribuir a propriedade de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalhos do Agent a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="760be-103">This topic describes how to reassign ownership of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>  
  
-   <span data-ttu-id="760be-104">**Antes de começar:**  [Limitações e Restrições](#Restrictions), [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="760be-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="760be-105">**Para conceder a propriedade de um trabalho a outros usando:**</span><span class="sxs-lookup"><span data-stu-id="760be-105">**To give others ownership of a job, using:**</span></span>  
  
     [<span data-ttu-id="760be-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="760be-106">SQL Server Management Studio</span></span>](#SSMSProc2)  
  
     [<span data-ttu-id="760be-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="760be-107">Transact-SQL</span></span>](#TsqlProc2)  
  
     [<span data-ttu-id="760be-108">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="760be-108">SQL Server Management Objects</span></span>](#SMOProc2)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="760be-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="760be-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="760be-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="760be-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="760be-111">Para criar um trabalho, o usuário deve ser membro de uma das funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ou da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="760be-111">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="760be-112">Um trabalho só pode ser editado por seu proprietário ou por membros da função **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="760be-112">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="760be-113">Para obter mais informações sobre as funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consulte [Funções de banco de dados fixas do SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="760be-113">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="760be-114">Você precisa ser um administrador do sistema para alterar o proprietário de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="760be-114">You must be a system administrator to change the owner of a job.</span></span>  
  
 <span data-ttu-id="760be-115">Atribuir um trabalho a outro logon não garante que o novo proprietário tenha permissões adequadas para executar o trabalho com êxito.</span><span class="sxs-lookup"><span data-stu-id="760be-115">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="760be-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="760be-116">Security</span></span>  
 <span data-ttu-id="760be-117">Por questão de segurança, apenas o proprietário do trabalho ou um membro da função **sysadmin** pode alterar a definição do trabalho.</span><span class="sxs-lookup"><span data-stu-id="760be-117">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="760be-118">Somente os membros da função de servidor fixa **sysadmin** podem atribuir a propriedade do trabalho a outros usuários, bem como executar qualquer trabalho, independentemente de seu proprietário.</span><span class="sxs-lookup"><span data-stu-id="760be-118">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="760be-119">Se você transmitir a propriedade a um usuário que não seja membro da função de servidor fixa **sysadmin** e o trabalho estiver executando etapas que exijam contas proxy (por exemplo, execução de pacotes [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), verifique se o usuário tem acesso à conta proxy necessária, ou o trabalho falhará.</span><span class="sxs-lookup"><span data-stu-id="760be-119">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="760be-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="760be-120">Permissions</span></span>  
 <span data-ttu-id="760be-121">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="760be-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProc2"></a> <span data-ttu-id="760be-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="760be-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="760be-123">**Para conceder a propriedade de um trabalho a outros**</span><span class="sxs-lookup"><span data-stu-id="760be-123">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="760be-124">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="760be-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="760be-125">Expanda **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho e então clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="760be-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="760be-126">Na lista **Proprietário** , selecione um logon.</span><span class="sxs-lookup"><span data-stu-id="760be-126">In the **Owner** list, select a login.</span></span> <span data-ttu-id="760be-127">Você precisa ser um administrador do sistema para alterar o proprietário de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="760be-127">You must be a system administrator to change the owner of a job.</span></span>  
  
     <span data-ttu-id="760be-128">Atribuir um trabalho a outro logon não garante que o novo proprietário tenha permissões adequadas para executar o trabalho com êxito.</span><span class="sxs-lookup"><span data-stu-id="760be-128">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProc2"></a> <span data-ttu-id="760be-129">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="760be-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="760be-130">**Para conceder a propriedade de um trabalho a outros**</span><span class="sxs-lookup"><span data-stu-id="760be-130">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="760be-131">No Pesquisador de Objetos, conecte-se a uma instância do Mecanismo de Banco de Dados e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="760be-131">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="760be-132">Na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="760be-132">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="760be-133">Na janela de consulta, insira as instruções a seguir que usam o sp_manage_jobs_by_login &#40;procedimento armazenado do sistema [&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="760be-133">In the query window, enter the following statements that use the [sp_manage_jobs_by_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) system stored procedure.</span></span> <span data-ttu-id="760be-134">O exemplo a seguir reatribui todos os trabalhos de `danw` para `fran??oisa`.</span><span class="sxs-lookup"><span data-stu-id="760be-134">The following example reassigns all jobs from `danw` to `fran??oisa`.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_manage_jobs_by_login  
        @action = N'REASSIGN',  
        @current_owner_login_name = N'danw',  
        @new_owner_login_name = N'fran??oisa' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProc2"></a><span data-ttu-id="760be-135">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="760be-135">Using SQL Server Management Objects</span></span>  

### <a name="to-give-others-ownership-of-a-job"></a><span data-ttu-id="760be-136">Para conceder a propriedade de um trabalho a outros</span><span class="sxs-lookup"><span data-stu-id="760be-136">To give others ownership of a job</span></span>
  
1.  <span data-ttu-id="760be-137">Chame a classe `Job` usando uma linguagem de programação que você escolher, como Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="760be-137">Call the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="760be-138">Para obter um código de exemplo, consulte [Agendamento de tarefas administrativas automáticas no SQL Server Agent](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="760be-138">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760be-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="760be-139">See Also</span></span>  
 <span data-ttu-id="760be-140">[Implementar trabalhos](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="760be-140">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="760be-141">Criar trabalhos</span><span class="sxs-lookup"><span data-stu-id="760be-141">Create Jobs</span></span>](create-jobs.md)  
