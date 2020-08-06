---
title: Modificar o (s) servidor (es) de destino associado a um trabalho mestre de SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 176e73b6-08aa-48ec-b349-e84b431e65cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6b7b5ab114366cdafe40b7a70f523fef43eb11d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583316"
---
# <a name="modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="ef235-102">Modificar o servidor de destino associado a um trabalho mestre do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="ef235-102">Modify the Target Server(s) Associated with a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="ef235-103">Este tópico descreve como modificar os servidores de destino associados a um trabalho mestre do SQL Server Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef235-103">This topic describes how to modify the target server(s) associated with a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ef235-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ef235-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ef235-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="ef235-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ef235-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="ef235-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ef235-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="ef235-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ef235-108">**Para modificar o servidor de destino associado a um trabalho mestre do SQL Server Agent, usando:**</span><span class="sxs-lookup"><span data-stu-id="ef235-108">**To modify the target server(s) associated with a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="ef235-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef235-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ef235-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef235-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ef235-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ef235-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ef235-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="ef235-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ef235-113">Um trabalho mestre do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não pode ser destino em ambos os servidores, local e remoto.</span><span class="sxs-lookup"><span data-stu-id="ef235-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ef235-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="ef235-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ef235-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="ef235-115">Permissions</span></span>  
 <span data-ttu-id="ef235-116">A menos que seja membro da função de servidor fixa **sysadmin** , você poderá modificar somente trabalhos de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="ef235-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="ef235-117">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="ef235-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ef235-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef235-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="ef235-119">Para modificar o servidor de destino associado a um trabalho mestre do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="ef235-119">To modify the target server(s) associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="ef235-120">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor que contém o trabalho onde você deseja modificar o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="ef235-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify the target server.</span></span>  
  
2.  <span data-ttu-id="ef235-121">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="ef235-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="ef235-122">Clique no sinal de adição para expandir a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="ef235-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="ef235-123">Clique com o botão direito do mouse no trabalho em que você quer modificar o servidor de destino e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ef235-123">Right-click the job where you want to modify the target server and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="ef235-124">Na caixa de diálogo **Propriedades do trabalho –**_Job_name_ , em **selecionar uma página**, selecione **destinos**.</span><span class="sxs-lookup"><span data-stu-id="ef235-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Targets**.</span></span> <span data-ttu-id="ef235-125">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: nova página de destinos de &#40;de trabalho&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="ef235-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
6.  <span data-ttu-id="ef235-126">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef235-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ef235-127">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef235-127">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-target-server-currently-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="ef235-128">Para excluir um servidor de destino atualmente associado a um trabalho mestre do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="ef235-128">To delete a target server currently associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="ef235-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef235-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ef235-130">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ef235-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ef235-131">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="ef235-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes the server SEATTLE2 from processing the Weekly Sales Backupsjob   
    -- assumes that the Weekly Sales Backups job exists  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="ef235-132">Para obter mais informações, consulte [sp_delete_jobserver &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ef235-132">For more information, see [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span></span>  
  
#### <a name="to-associate-a-target-server-with-the-current-sql-server-agent-master-job"></a><span data-ttu-id="ef235-133">Para associar um servidor de destino ao trabalho mestre atual do SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="ef235-133">To associate a target server with the current SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="ef235-134">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef235-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ef235-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ef235-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ef235-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="ef235-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2   
    -- assumes that the Weekly Sales Backups job already exists and that   
    -- SEATTLE2 is registered as a target server for the current instance  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="ef235-137">Para obter mais informações, consulte [sp_add_jobserver &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ef235-137">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
  
