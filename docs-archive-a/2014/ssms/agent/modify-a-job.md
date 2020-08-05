---
title: Modificar um Trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
ms.assetid: dd5e5f20-20c4-4ab9-a19a-db87577dcd43
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0d25830ad119a1f5f344a4dcf318c35bee5f86ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572350"
---
# <a name="modify-a-job"></a><span data-ttu-id="f497d-102">Modify a Job</span><span class="sxs-lookup"><span data-stu-id="f497d-102">Modify a Job</span></span>
  <span data-ttu-id="f497d-103">Este tópico descreve como alterar as propriedades de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalhos do Agent no usando [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="f497d-103">This topic describes how to change the properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="f497d-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="f497d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f497d-105">**Antes de começar:** ,</span><span class="sxs-lookup"><span data-stu-id="f497d-105">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="f497d-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="f497d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f497d-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="f497d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f497d-108">**Para modificar um trabalho, usando:**</span><span class="sxs-lookup"><span data-stu-id="f497d-108">**To modify a job, using:**</span></span>  
  
     [<span data-ttu-id="f497d-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f497d-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="f497d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f497d-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="f497d-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="f497d-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f497d-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f497d-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f497d-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="f497d-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f497d-114">Um trabalho mestre do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não pode ser destino em ambos os servidores, local e remoto.</span><span class="sxs-lookup"><span data-stu-id="f497d-114">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f497d-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="f497d-115">Security</span></span>  
 <span data-ttu-id="f497d-116">A menos que seja membro da função de servidor fixa **sysadmin** , você poderá modificar somente trabalhos de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="f497d-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="f497d-117">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="f497d-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="f497d-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f497d-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="f497d-119">Para modificar um trabalho</span><span class="sxs-lookup"><span data-stu-id="f497d-119">To modify a job</span></span>  
  
1.  <span data-ttu-id="f497d-120">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="f497d-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f497d-121">Expanda o **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho que deseja modificar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f497d-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f497d-122">Na caixa de diálogo **Propriedades do Trabalho** , atualize as propriedades, etapas, agenda, alertas e notificações do trabalho, usando as páginas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="f497d-122">In the **Job Properties** dialog box, update the job's properties, steps, schedule, alerts, and notifications using the corresponding pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="f497d-123">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f497d-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="f497d-124">Para modificar um trabalho</span><span class="sxs-lookup"><span data-stu-id="f497d-124">To modify a job</span></span>  
  
1.  <span data-ttu-id="f497d-125">No Pesquisador de Objetos, conecte-se a uma instância do Mecanismo de Banco de Dados e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="f497d-125">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f497d-126">Na barra de ferramentas, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="f497d-126">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f497d-127">Na janela de consulta, use os procedimentos armazenados do sistema a seguir para modificar um trabalho.</span><span class="sxs-lookup"><span data-stu-id="f497d-127">In the query window, use the following system stored procedures to modify a job.</span></span>  
  
    -   <span data-ttu-id="f497d-128">Execute [sp_update_job &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) para alterar os atributos de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="f497d-128">Execute [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) to change the attributes of a job.</span></span>  
  
    -   <span data-ttu-id="f497d-129">Execute [sp_update_schedule &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) para alterar os detalhes de agendamento de uma definição de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f497d-129">Execute [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) to change the scheduling details for a job definition.</span></span>  
  
    -   <span data-ttu-id="f497d-130">Execute [sp_add_jobstep &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) para adicionar novas etapas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f497d-130">Execute [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) to add new job steps.</span></span>  
  
    -   <span data-ttu-id="f497d-131">Execute [sp_update_jobstep &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) para alterar as etapas de trabalho pré-existentes.</span><span class="sxs-lookup"><span data-stu-id="f497d-131">Execute [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) to change pre-existing job steps.</span></span>  
  
    -   <span data-ttu-id="f497d-132">Execute [sp_delete_jobstep &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) para remover uma etapa de trabalho de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="f497d-132">Execute [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) to remove a job step from a job.</span></span>  
  
    -   <span data-ttu-id="f497d-133">Procedimentos armazenados adicionais para modificar qualquer trabalho mestre do SQL Server Agent:</span><span class="sxs-lookup"><span data-stu-id="f497d-133">Additional stored procedures to modify any SQL Server Agent master job:</span></span>  
  
        -   <span data-ttu-id="f497d-134">Execute [sp_delete_jobserver &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) para excluir um servidor atualmente associado a um trabalho.</span><span class="sxs-lookup"><span data-stu-id="f497d-134">Execute [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) to delete a server currently associated with a job.</span></span>  
  
        -   <span data-ttu-id="f497d-135">Execute [sp_add_jobserver &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) associe um servidor ao trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="f497d-135">Execute [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) to associate a server with the current job.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="f497d-136">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="f497d-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="f497d-137">**Para modificar um trabalho**</span><span class="sxs-lookup"><span data-stu-id="f497d-137">**To modify a job**</span></span>  
  
 <span data-ttu-id="f497d-138">Use a classe `Job` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f497d-138">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="f497d-139">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="f497d-139">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
