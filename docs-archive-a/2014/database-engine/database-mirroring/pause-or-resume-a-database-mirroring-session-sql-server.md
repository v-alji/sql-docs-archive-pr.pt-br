---
title: Pausar ou retomar uma sessão de espelhamento de banco de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- resuming database mirroring
- database mirroring [SQL Server], sessions
- database mirroring [SQL Server], pausing
- database mirroring [SQL Server], resuming
- pausing database mirroring
ms.assetid: 05ede3b4-6abe-4442-abb7-9f5aee1d6bc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8a9e30bed3ff268fcfdc6e352ad15ebedfe4e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681173"
---
# <a name="pause-or-resume-a-database-mirroring-session-sql-server"></a><span data-ttu-id="d62ad-102">Pausar ou retomar uma sessão de espelhamento de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d62ad-102">Pause or Resume a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="d62ad-103">Este tópico descreve como pausar ou retomar o espelhamento de banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d62ad-103">This topic describes how to pause or resume database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d62ad-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="d62ad-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d62ad-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="d62ad-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d62ad-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="d62ad-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d62ad-107">**Para ReplaceThisText usando:**</span><span class="sxs-lookup"><span data-stu-id="d62ad-107">**To ReplaceThisText, using:**</span></span>  
  
     [<span data-ttu-id="d62ad-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d62ad-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d62ad-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d62ad-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="d62ad-110">**Acompanhamento:**  [depois de pausar ou retomar o espelhamento do banco de dados](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d62ad-110">**Follow Up:**  [After Pausing or Resuming Database Mirroring](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d62ad-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d62ad-111">Before You Begin</span></span>  
 <span data-ttu-id="d62ad-112">A qualquer momento, você pode suspender uma sessão de espelhamento de banco de dados, o que pode melhorar o desempenho durante gargalos, e pode retomar uma sessão suspensa.</span><span class="sxs-lookup"><span data-stu-id="d62ad-112">At any time, you can suspend a database mirroring session, which might improve performance during bottlenecks, and you can resume a suspended session at any time.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="d62ad-113">Depois um serviço forçado, quando o servidor principal original é reconectado, o espelhamento é suspenso.</span><span class="sxs-lookup"><span data-stu-id="d62ad-113">After a forced service, when the original principal server reconnects, mirroring is suspended.</span></span> <span data-ttu-id="d62ad-114">A retomada do espelhamento nessa situação pode causar perda de dados no servidor principal original.</span><span class="sxs-lookup"><span data-stu-id="d62ad-114">Resuming mirroring in this situation could possibly cause data loss on the original principal server.</span></span> <span data-ttu-id="d62ad-115">Para obter informações sobre o gerenciamento de perda de dados em potencial, veja [Troca de função durante uma Sessão de Espelhamento de Banco de Dados &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d62ad-115">For information about managing the potential data loss, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d62ad-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="d62ad-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d62ad-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="d62ad-117">Permissions</span></span>  
 <span data-ttu-id="d62ad-118">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d62ad-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d62ad-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d62ad-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d62ad-120">Para pausar ou retomar uma sessão de espelhamento de banco de dados, use a página **Espelhamento de Propriedades do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="d62ad-120">To pause or resume a database mirroring session use the **Database Properties Mirroring** page.</span></span>  
  
#### <a name="to-pause-or-resume-database-mirroring"></a><span data-ttu-id="d62ad-121">Para pausar ou retomar o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="d62ad-121">To pause or resume database mirroring</span></span>  
  
1.  <span data-ttu-id="d62ad-122">Durante uma sessão de espelhamento de banco de dados, faça a conexão com a instância do servidor principal e, no Pesquisador de Objetos, clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="d62ad-122">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="d62ad-123">Expanda **Bancos de Dados**e selecione o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d62ad-123">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="d62ad-124">Clique com o botão direito do mouse no banco de dados, selecione **Tarefas**e clique em **Espelhar**.</span><span class="sxs-lookup"><span data-stu-id="d62ad-124">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="d62ad-125">Isso abre a página **Espelhamento** da caixa de diálogo **Propriedades do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="d62ad-125">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="d62ad-126">Para pausar a sessão, clique em **Pausar**.</span><span class="sxs-lookup"><span data-stu-id="d62ad-126">To pause the session, click **Pause**.</span></span>  
  
     <span data-ttu-id="d62ad-127">Um prompt pedirá confirmação; se você clicar em **Sim**, a sessão será pausada e o botão será alterado para **Retomar**.</span><span class="sxs-lookup"><span data-stu-id="d62ad-127">A prompt asks for confirmation; if you click **Yes**, the session is paused, and the button changes to **Resume**.</span></span>  
  
     <span data-ttu-id="d62ad-128">Para obter mais informações sobre o impacto de pausar uma sessão, veja [Pausar e retomar o Espelhamento de Banco de Dados &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d62ad-128">For more information about the impact of pausing a session, see [Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="d62ad-129">Para retomar a sessão, clique em **Retomar**.</span><span class="sxs-lookup"><span data-stu-id="d62ad-129">To resume the session, click **Resume**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d62ad-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d62ad-130">Using Transact-SQL</span></span>  
  
#### <a name="to-pause-database-mirroring"></a><span data-ttu-id="d62ad-131">Para pausar o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="d62ad-131">To pause database mirroring</span></span>  
  
1.  <span data-ttu-id="d62ad-132">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)] para qualquer um dos parceiros.</span><span class="sxs-lookup"><span data-stu-id="d62ad-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="d62ad-133">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="d62ad-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d62ad-134">Emita a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="d62ad-134">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="d62ad-135">ALTER DATABASE *database_name* SET PARTNER SUSPEND</span><span class="sxs-lookup"><span data-stu-id="d62ad-135">ALTER DATABASE *database_name* SET PARTNER SUSPEND</span></span>  
  
     <span data-ttu-id="d62ad-136">em que *database_name* é o banco de dados espelhado cuja sessão você deseja suspender.</span><span class="sxs-lookup"><span data-stu-id="d62ad-136">where *database_name* is the mirrored database whose session you want to you want to suspend.</span></span>  
  
     <span data-ttu-id="d62ad-137">O exemplo a seguir pausa o banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d62ad-137">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER SUSPEND;  
    ```  
  
##### <a name="to-resume-database-mirroring"></a><span data-ttu-id="d62ad-138">Para retomar o espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d62ad-138">To resume database mirroring</span></span>  
  
1.  <span data-ttu-id="d62ad-139">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)] para qualquer um dos parceiros.</span><span class="sxs-lookup"><span data-stu-id="d62ad-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="d62ad-140">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="d62ad-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d62ad-141">Emita a seguinte instrução Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="d62ad-141">Issue the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="d62ad-142">ALTER DATABASE *database_name* SET PARTNER RESUME</span><span class="sxs-lookup"><span data-stu-id="d62ad-142">ALTER DATABASE *database_name* SET PARTNER RESUME</span></span>  
  
     <span data-ttu-id="d62ad-143">em que *database_name* é o banco de dados espelhado cuja sessão você deseja retomar.</span><span class="sxs-lookup"><span data-stu-id="d62ad-143">where *database_name* is the mirrored database whose session you want to resume.</span></span>  
  
     <span data-ttu-id="d62ad-144">O exemplo a seguir pausa o banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d62ad-144">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER RESUME;  
    ```  
  
##  <a name="follow-up-after-pausing-or-resuming-database-mirroring"></a><a name="FollowUp"></a><span data-ttu-id="d62ad-145">Acompanhamento: depois de pausar ou retomar o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="d62ad-145">Follow Up: After Pausing or Resuming Database Mirroring</span></span>  
  
-   <span data-ttu-id="d62ad-146">**Depois de pausar o espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="d62ad-146">**After pausing database mirroring**</span></span>  
  
     <span data-ttu-id="d62ad-147">No banco de dados primário, tome precauções para evitar um log de transações cheio.</span><span class="sxs-lookup"><span data-stu-id="d62ad-147">On the primary database, take precautions to avoid a full transaction log.</span></span> <span data-ttu-id="d62ad-148">Para obter mais informações, consulte [O log de transações &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d62ad-148">For more information, see [The Transaction Log &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="d62ad-149">**Depois de retomar o espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="d62ad-149">**After resuming database mirroring**</span></span>  
  
     <span data-ttu-id="d62ad-150">A retomada do espelhamento de banco de dados coloca o banco de dados espelho no estado SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="d62ad-150">Resuming database mirroring places the mirror database in the SYNCHRONIZING state.</span></span> <span data-ttu-id="d62ad-151">Se o nível de segurança for FULL, o espelho alcançará o banco de dados principal e o banco de dados espelho entrará no estado SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="d62ad-151">If the safety level is FULL, the mirror catches up with the principal and the mirror database enters the SYNCHRONIZED state.</span></span> <span data-ttu-id="d62ad-152">Neste momento, o failover torna-se possível.</span><span class="sxs-lookup"><span data-stu-id="d62ad-152">At this point, failover becomes possible.</span></span> <span data-ttu-id="d62ad-153">Se a testemunha estiver presente e ON, o failover automático será possível.</span><span class="sxs-lookup"><span data-stu-id="d62ad-153">If the witness is present and ON, automatic failover is possible.</span></span> <span data-ttu-id="d62ad-154">Na ausência de uma testemunha, o failover manual será possível.</span><span class="sxs-lookup"><span data-stu-id="d62ad-154">In the absence of a witness, manual failover is possible.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d62ad-155">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="d62ad-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d62ad-156">Remover o espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d62ad-156">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d62ad-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d62ad-157">See Also</span></span>  
 [<span data-ttu-id="d62ad-158">Espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d62ad-158">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
