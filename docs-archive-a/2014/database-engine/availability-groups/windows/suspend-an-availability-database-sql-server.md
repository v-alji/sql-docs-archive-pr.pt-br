---
title: Suspender um banco de dados de disponibilidade (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.suspenddatamove.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], suspending a database
- Availability Groups [SQL Server], databases
ms.assetid: 86858982-6af1-4e80-9a93-87451f0d7ee9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49afe868a509f84160fc1ad154135e8e67f6900a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685290"
---
# <a name="suspend-an-availability-database-sql-server"></a><span data-ttu-id="a76dd-102">Suspender um banco de dados de disponibilidade (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a76dd-102">Suspend an Availability Database (SQL Server)</span></span>
  <span data-ttu-id="a76dd-103">Você pode suspender um banco de dados de disponibilidade no [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] usando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou PowerShell no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a76dd-103">You can suspend an availability database in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a76dd-104">Observe que um comando para suspender precisa ser emitido na instância do servidor que hospeda o banco de dados para ser suspenso ou retomado.</span><span class="sxs-lookup"><span data-stu-id="a76dd-104">Note that a suspend command needs to be issued on the server instance that hosts the database to be suspended or resumed.</span></span>  
  
 <span data-ttu-id="a76dd-105">O efeito de um comando de suspensão depende de se você suspende um banco de dados secundário ou um banco de dados primário, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a76dd-105">The effect of a suspend command depends on whether you suspend a secondary database or a primary database, as follows:</span></span>  
  
|<span data-ttu-id="a76dd-106">Banco de dados suspenso</span><span class="sxs-lookup"><span data-stu-id="a76dd-106">Suspended Database</span></span>|<span data-ttu-id="a76dd-107">Efeito do comando de suspensão</span><span class="sxs-lookup"><span data-stu-id="a76dd-107">Effect of Suspend Command</span></span>|  
|------------------------|-------------------------------|  
|<span data-ttu-id="a76dd-108">Banco de dados secundário</span><span class="sxs-lookup"><span data-stu-id="a76dd-108">Secondary database</span></span>|<span data-ttu-id="a76dd-109">Somente o banco de dados secundário local é suspenso e seu estado de sincronização torna-se NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="a76dd-109">Only the local secondary database is suspended and its synchronization state becomes NOT SYNCHRONIZING.</span></span> <span data-ttu-id="a76dd-110">Outros bancos de dados secundários não são afetados.</span><span class="sxs-lookup"><span data-stu-id="a76dd-110">Other secondary databases are not affected.</span></span> <span data-ttu-id="a76dd-111">O banco de dados suspenso para de receber e aplicar dados (registros de log) e começa ficar desatualizado em relação ao banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="a76dd-111">The suspended database stops receiving and applying data (log records) and begins to fall behind the primary database.</span></span> <span data-ttu-id="a76dd-112">Conexões existentes nas secundários legíveis permanecem utilizáveis.</span><span class="sxs-lookup"><span data-stu-id="a76dd-112">Existing connections on the readable secondary remain usable.</span></span> <span data-ttu-id="a76dd-113">Novas conexões para o banco de dados suspenso na secundário legível não serão permitidas até que o movimento de dados seja continuado.</span><span class="sxs-lookup"><span data-stu-id="a76dd-113">New connections to the suspended database on the readable secondary are not allowed until data movement is resumed.</span></span><br /><br /> <span data-ttu-id="a76dd-114">O banco de dados primário permanece disponível.</span><span class="sxs-lookup"><span data-stu-id="a76dd-114">The primary database remains available.</span></span> <span data-ttu-id="a76dd-115">Se você suspender cada um dos bancos de dados secundários correspondentes, o banco de dados primário será executado exposto.</span><span class="sxs-lookup"><span data-stu-id="a76dd-115">If you suspend each of the corresponding secondary databases, the primary database runs exposed.</span></span><br /><br /> <span data-ttu-id="a76dd-116">**\*\* Importante \*\*** Enquanto um banco de dados secundário permanece suspenso, a fila de envio do banco de dados primário correspondente acumula registros de log de transação não enviados.</span><span class="sxs-lookup"><span data-stu-id="a76dd-116">**\*\* Important \*\*** While a secondary database is suspended, the send queue of the corresponding primary database will accumulate unsent transaction log records.</span></span> <span data-ttu-id="a76dd-117">As conexões para a réplica secundária retornam dados que estavam disponíveis no momento em que o movimento de dados foi suspenso.</span><span class="sxs-lookup"><span data-stu-id="a76dd-117">Connections to the secondary replica return data that was available at the time the data movement was suspended.</span></span>|  
|<span data-ttu-id="a76dd-118">Banco de dados primário</span><span class="sxs-lookup"><span data-stu-id="a76dd-118">Primary database</span></span>|<span data-ttu-id="a76dd-119">O banco de dados primário para o movimento de dados para todos os bancos de dados secundários conectados.</span><span class="sxs-lookup"><span data-stu-id="a76dd-119">The primary database stops data movement to every connected secondary database.</span></span> <span data-ttu-id="a76dd-120">O banco de dados primário continua sendo executado em um modo exposto.</span><span class="sxs-lookup"><span data-stu-id="a76dd-120">The primary database continues running, in an exposed mode.</span></span> <span data-ttu-id="a76dd-121">O banco de dados primário permanece disponível para clientes, e as conexões existentes em um banco de dados secundário legível permanecem utilizáveis e novas conexões podem ser feitas.</span><span class="sxs-lookup"><span data-stu-id="a76dd-121">The primary database remains available to clients, and existing connections on a readable secondary remain usable and new connections can be made.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="a76dd-122">Suspender um banco de dados secundário AlwaysOn não afetam diretamente a disponibilidade do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="a76dd-122">Suspending an AlwaysOn secondary database does not directly affect the availability of the primary database.</span></span> <span data-ttu-id="a76dd-123">Porém, suspender um banco de dados secundário pode afetar os recursos de redundância e failover para o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="a76dd-123">However, suspending a secondary database can impact redundancy and failover capabilities for the primary database.</span></span> <span data-ttu-id="a76dd-124">Isto está em contraste com o espelhamento de banco de dados, onde o estado de espelhamento é suspenso no banco de dados espelho e no banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="a76dd-124">This is in contrast to database mirroring, where the mirroring state is suspended on both the mirror database and the principal database.</span></span> <span data-ttu-id="a76dd-125">Suspender um banco de dados secundário AlwaysOn suspende o movimento de dados em todos os bancos de dados secundários correspondentes, e os recursos de failover e a redundância são eliminados para esse banco de dados até que o banco de dados primário seja retomado.</span><span class="sxs-lookup"><span data-stu-id="a76dd-125">Suspending an AlwaysOn primary database suspends data movement on all the corresponding secondary databases, and redundancy and failover capabilities cease for that database until the primary database is resumed.</span></span>  
  
-   <span data-ttu-id="a76dd-126">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="a76dd-126">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a76dd-127">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a76dd-127">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a76dd-128">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a76dd-128">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="a76dd-129">Recomendações</span><span class="sxs-lookup"><span data-stu-id="a76dd-129">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="a76dd-130">Segurança</span><span class="sxs-lookup"><span data-stu-id="a76dd-130">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a76dd-131">**Para suspender um banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="a76dd-131">**To suspend a database, using:**</span></span>  
  
-   [<span data-ttu-id="a76dd-132">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a76dd-132">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a76dd-133">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a76dd-133">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a76dd-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a76dd-134">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="a76dd-135">**Acompanhamento:** [evitar um log de transações cheio](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a76dd-135">**Follow up:** [Avoiding a Full Transaction Log](#FollowUp)</span></span>  
  
-   [<span data-ttu-id="a76dd-136">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a76dd-136">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a76dd-137">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a76dd-137">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a76dd-138">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a76dd-138">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a76dd-139">O comando SUSPEND retorna assim que é aceito pela réplica que hospeda o banco de dados de destino, mas, na verdade, a suspensão do banco de dados ocorre de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="a76dd-139">A SUSPEND command returns as soon as it has been accepted by the replica that hosts the target database, but actually suspending the database occurs asynchronously.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a76dd-140">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a76dd-140">Prerequisites</span></span>  
 <span data-ttu-id="a76dd-141">Você deve estar conectado à instância de servidor que hospeda o banco de dados a ser suspenso.</span><span class="sxs-lookup"><span data-stu-id="a76dd-141">You must be connected to the server instance that hosts the database that you want to suspend.</span></span> <span data-ttu-id="a76dd-142">Para suspender um banco de dados primários e os bancos de dados secundários correspondentes, conecte-se à instância de servidor que hospeda a réplica primária.</span><span class="sxs-lookup"><span data-stu-id="a76dd-142">To suspend a primary database and the corresponding secondary databases, connect to the server instance that hosts the primary replica.</span></span> <span data-ttu-id="a76dd-143">Para suspender um banco de dados secundário deixando o banco de dados primário disponível, conecte-se à réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="a76dd-143">To suspend a secondary database while leaving the primary database available, connect to the secondary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="a76dd-144">Recomendações</span><span class="sxs-lookup"><span data-stu-id="a76dd-144">Recommendations</span></span>  
 <span data-ttu-id="a76dd-145">Durante gargalos, a suspensão de um ou mais bancos de dados secundários brevemente poderá ser útil para melhorar temporariamente o desempenho na réplica primária.</span><span class="sxs-lookup"><span data-stu-id="a76dd-145">During bottlenecks, suspending one or more secondary databases briefly might be useful to improve performance temporarily on the primary replica.</span></span> <span data-ttu-id="a76dd-146">Desde que um banco de dados secundário permaneça suspenso, o log de transações do banco de dados primário correspondente não poderá ser truncado.</span><span class="sxs-lookup"><span data-stu-id="a76dd-146">As long as a secondary database remains suspended, the transaction log of the corresponding primary database cannot be truncated.</span></span> <span data-ttu-id="a76dd-147">Isso faz com que os registros de log sejam acumulados no banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="a76dd-147">This causes log records to accumulate on the primary database.</span></span> <span data-ttu-id="a76dd-148">Portanto, é recomendável retomar ou remover um banco de dados secundário suspenso rapidamente.</span><span class="sxs-lookup"><span data-stu-id="a76dd-148">Therefore, we recommend that you resume, or remove, a suspended secondary database quickly.</span></span> <span data-ttu-id="a76dd-149">Para obter mais informações, veja [Acompanhamento: evitar um log de transações cheio](#FollowUp) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a76dd-149">For more information, see [Follow up: Avoiding a Full Transaction Log](#FollowUp), later in this topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a76dd-150">Segurança</span><span class="sxs-lookup"><span data-stu-id="a76dd-150">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a76dd-151">Permissões</span><span class="sxs-lookup"><span data-stu-id="a76dd-151">Permissions</span></span>  
 <span data-ttu-id="a76dd-152">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a76dd-152">Requires ALTER permission on the database.</span></span>  
  
 <span data-ttu-id="a76dd-153">Requer a permissão ALTER AVAILABILITY GROUP no grupo de disponibilidade, a permissão CONTROL AVAILABILITY GROUP, a permissão ALTER ANY AVAILABILITY GROUP ou a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="a76dd-153">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a76dd-154">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a76dd-154">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a76dd-155">**Para suspender um banco de dados**</span><span class="sxs-lookup"><span data-stu-id="a76dd-155">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="a76dd-156">No Pesquisador de Objetos, conecte-se à instância de servidor que hospeda a réplica de disponibilidade na qual você deseja suspender um banco de dados e expanda a árvore de servidores.</span><span class="sxs-lookup"><span data-stu-id="a76dd-156">In Object Explorer, connect to the server instance that hosts the availability replica on which you want to suspend a database, and expand the server tree.</span></span> <span data-ttu-id="a76dd-157">Para obter mais informações, consulte [Pré-requisitos](#Prerequisites)anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a76dd-157">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="a76dd-158">Expanda os nós **Alta Disponibilidade AlwaysOn** e **Grupos de Disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="a76dd-158">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="a76dd-159">Expanda o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="a76dd-159">Expand the availability group.</span></span>  
  
4.  <span data-ttu-id="a76dd-160">Expanda o nó **Bancos de dados de Disponibilidade** , clique com o botão direito do mouse no banco de dados e clique **Suspender a Movimentação de Dados**.</span><span class="sxs-lookup"><span data-stu-id="a76dd-160">Expand the **Availability Databases** node, right-click the database, and click **Suspend Data Movement**.</span></span>  
  
5.  <span data-ttu-id="a76dd-161">Na caixa de diálogo **Suspender a Movimentação de Dados** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a76dd-161">In the **Suspend Data Movement** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="a76dd-162">O Pesquisador de Objetos indica que o banco de dados está suspenso alterando o ícone de banco de dados para exibir um indicador de pausa.</span><span class="sxs-lookup"><span data-stu-id="a76dd-162">Object Explorer indicates that the database is suspended by changing  the database icon to display a pause indicator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a76dd-163">Para suspender bancos de dados adicionais neste local de réplica, repita as etapas 4 e 5 para cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a76dd-163">To suspend additional databases on this replica location, repeat steps 4 and 5  for each database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a76dd-164">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a76dd-164">Using Transact-SQL</span></span>  
 <span data-ttu-id="a76dd-165">**Para suspender um banco de dados**</span><span class="sxs-lookup"><span data-stu-id="a76dd-165">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="a76dd-166">Conecte-se à instância do servidor que hospeda a réplica cujo banco de dados você deseja suspender.</span><span class="sxs-lookup"><span data-stu-id="a76dd-166">Connect to the server instance that hosts the replica whose database you want to suspend.</span></span> <span data-ttu-id="a76dd-167">Para obter mais informações, consulte [Pré-requisitos](#Prerequisites)anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a76dd-167">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="a76dd-168">Suspenda o banco de dados usando a seguinte instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr):</span><span class="sxs-lookup"><span data-stu-id="a76dd-168">Suspend the database by using the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)statement:</span></span>  
  
     <span data-ttu-id="a76dd-169">ALTER DATABASE *database_name* Set HADR Suspend</span><span class="sxs-lookup"><span data-stu-id="a76dd-169">ALTER DATABASE *database_name* SET HADR SUSPEND</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a76dd-170">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a76dd-170">Using PowerShell</span></span>  
 <span data-ttu-id="a76dd-171">**Para suspender um banco de dados**</span><span class="sxs-lookup"><span data-stu-id="a76dd-171">**To suspend a database**</span></span>  
  
1.  <span data-ttu-id="a76dd-172">Altere o diretório (`cd`) para a instância do servidor que hospeda a réplica cujo banco de dados você deseja suspender.</span><span class="sxs-lookup"><span data-stu-id="a76dd-172">Change directory (`cd`) to the server instance that hosts the replica whose database you want to suspend.</span></span> <span data-ttu-id="a76dd-173">Para obter mais informações, consulte [Pré-requisitos](#Prerequisites)anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a76dd-173">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="a76dd-174">Use o cmdlet `Suspend-SqlAvailabilityDatabase` para suspender o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="a76dd-174">Use the `Suspend-SqlAvailabilityDatabase` cmdlet to suspend the availability group.</span></span>  
  
     <span data-ttu-id="a76dd-175">Por exemplo, o comando a seguir suspende a sincronização de dados para o banco de dados de disponibilidade `MyDb3` no grupo de disponibilidade `MyAg` na instância de servidor denominada `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="a76dd-175">For example, the following command suspends data synchronization for the availability database `MyDb3` in the availability group `MyAg` on the server instance named `Computer\Instance`.</span></span>  
  
    ```powershell
    Suspend-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\Databases\MyDb3  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="a76dd-176">Para exibir a sintaxe de um cmdlet, use o cmdlet `Get-Help` no ambiente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a76dd-176">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="a76dd-177">Para obter mais informações, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a76dd-177">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="a76dd-178">**Para configurar e usar o provedor do SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a76dd-178">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="a76dd-179">Provedor do SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="a76dd-179">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-avoiding-a-full-transaction-log"></a><a name="FollowUp"></a> <span data-ttu-id="a76dd-180">Acompanhamento: evitar um log de transações cheio</span><span class="sxs-lookup"><span data-stu-id="a76dd-180">Follow Up: Avoiding a Full Transaction Log</span></span>  
 <span data-ttu-id="a76dd-181">Normalmente, quando um ponto de verificação automático é executado em um banco de dados, seu log de transações é truncado àquele ponto de verificação após o próximo backup de log.</span><span class="sxs-lookup"><span data-stu-id="a76dd-181">Normally, when an automatic checkpoint is performed on a database, its transaction log is truncated to that checkpoint after the next log backup.</span></span> <span data-ttu-id="a76dd-182">Porém, enquanto um banco de dados secundário está suspenso, todos os registros de log atuais permanecem ativos no banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="a76dd-182">However, while a secondary database is suspended, all of the current log records remain active on the primary database.</span></span> <span data-ttu-id="a76dd-183">Se o log de transações ficar cheio (por ter atingido seu tamanho máximo ou porque a instância de servidor ficou sem espaço), o banco de dados não poderá executar mais nenhuma atualização.</span><span class="sxs-lookup"><span data-stu-id="a76dd-183">If the transaction log fills up (either because it reaches its maximum size or the server instance runs out of space), the database cannot perform any more updates.</span></span>  
  
 <span data-ttu-id="a76dd-184">Para evitar esse problema, você deverá proceder da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a76dd-184">To avoid this problem, you should do one of the following:</span></span>  
  
-   <span data-ttu-id="a76dd-185">Adicionar mais espaço de log para o banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="a76dd-185">Add more log space for the primary database.</span></span>  
  
-   <span data-ttu-id="a76dd-186">Retomar o banco de dados secundário antes de o log ficar cheio.</span><span class="sxs-lookup"><span data-stu-id="a76dd-186">Resume the secondary database before the log fills up.</span></span> <span data-ttu-id="a76dd-187">Para obter mais informações, consulte [Retomar um banco de dados de disponibilidade &#40;SQL Server&#41;](resume-an-availability-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a76dd-187">For more information, see [Resume an Availability Database &#40;SQL Server&#41;](resume-an-availability-database-sql-server.md).</span></span>  
  
-   <span data-ttu-id="a76dd-188">Remover um banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="a76dd-188">Remove the secondary database.</span></span> <span data-ttu-id="a76dd-189">Para obter mais informações, veja [Remover um banco de dados secundário de um grupo de disponibilidade &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a76dd-189">For more information, see [Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="a76dd-190">**Para solucionar problemas de um log de transações completo**</span><span class="sxs-lookup"><span data-stu-id="a76dd-190">**To troubleshoot a full transaction log**</span></span>  
  
-   [<span data-ttu-id="a76dd-191">Solução de problemas de um log de transação completa &#40;Erro do SQL Server 9002&#41;</span><span class="sxs-lookup"><span data-stu-id="a76dd-191">Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;</span></span>](../../../relational-databases/logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a76dd-192">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a76dd-192">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a76dd-193">Retomar um banco de dados de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a76dd-193">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="a76dd-194">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a76dd-194">See Also</span></span>  
 <span data-ttu-id="a76dd-195">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a76dd-195">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="a76dd-196">Retomar um banco de dados de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a76dd-196">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
