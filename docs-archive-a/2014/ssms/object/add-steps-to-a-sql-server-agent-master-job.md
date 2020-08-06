---
title: Adicionar etapas a um trabalho mestre do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9cc1e8ab-7ddc-427b-859e-203aa7e24642
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccff8d6f4faa7bef549b5a179a957ce798250dbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568327"
---
# <a name="add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="26b1f-102">Add Steps to a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="26b1f-102">Add Steps to a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="26b1f-103">Este tópico descreve como adicionar etapas a um trabalho mestre do SQL Server Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26b1f-103">This topic describes how to add steps to a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="26b1f-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="26b1f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="26b1f-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="26b1f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="26b1f-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="26b1f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="26b1f-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="26b1f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="26b1f-108">**Para adicionar etapas a um trabalho mestre do SQL Server Agent, usando:**</span><span class="sxs-lookup"><span data-stu-id="26b1f-108">**To add steps to a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="26b1f-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26b1f-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="26b1f-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="26b1f-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="26b1f-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="26b1f-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="26b1f-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="26b1f-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="26b1f-113">Um trabalho mestre do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não pode ser destino em ambos os servidores, local e remoto.</span><span class="sxs-lookup"><span data-stu-id="26b1f-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="26b1f-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="26b1f-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="26b1f-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="26b1f-115">Permissions</span></span>  
 <span data-ttu-id="26b1f-116">A menos que seja membro da função de servidor fixa **sysadmin** , você poderá modificar somente trabalhos de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="26b1f-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="26b1f-117">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](../agent/implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="26b1f-117">For detailed information, see [Implement SQL Server Agent Security](../agent/implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="26b1f-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26b1f-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="26b1f-119">Para adicionar etapas a um trabalho mestre do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="26b1f-119">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="26b1f-120">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor que contém o trabalho ao qual você deseja adicionar etapas.</span><span class="sxs-lookup"><span data-stu-id="26b1f-120">In **Object Explorer,** click the plus sign to expand the server that contains the job to which you want to add steps.</span></span>  
  
2.  <span data-ttu-id="26b1f-121">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="26b1f-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="26b1f-122">Clique no sinal de adição para expandir a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="26b1f-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="26b1f-123">Clique com o botão direito do mouse no trabalho ao qual você deseja adicionar etapas e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="26b1f-123">Right-click the job to which you want to add steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="26b1f-124">Na caixa de diálogo **Propriedades do Trabalho –** _job_name_, em **Selecionar uma página**, selecione **Etapas**.</span><span class="sxs-lookup"><span data-stu-id="26b1f-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span> <span data-ttu-id="26b1f-125">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: página novas etapas de &#40;de trabalho&#41;](../agent/job-properties-new-job-steps-page.md).</span><span class="sxs-lookup"><span data-stu-id="26b1f-125">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](../agent/job-properties-new-job-steps-page.md).</span></span>  

6.  <span data-ttu-id="26b1f-126">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="26b1f-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="26b1f-127">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="26b1f-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="26b1f-128">Para adicionar etapas a um trabalho mestre do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="26b1f-128">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="26b1f-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26b1f-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="26b1f-130">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="26b1f-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="26b1f-131">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="26b1f-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a job step that changes database access to read-only for the Sales database.   
    -- specifies 5 retry attempts, with each retry to occur after a 5 minute wait.   
    -- assumes that the Weekly Sales Data Backup job already exists  
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
  
 <span data-ttu-id="26b1f-132">Para obter mais informações, consulte [sp_add_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="26b1f-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
  
