---
title: Alterar etapas de um trabalho mestre do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 8f1a0ee6-49ff-4080-94ca-d661daeff2a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a9defc17b5b39ab8a322b6da29960eb9968c2e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583332"
---
# <a name="change-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="c03cb-102">Change Steps of a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="c03cb-102">Change Steps of a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="c03cb-103">Este tópico descreve como realizar alterações às etapas de um trabalho mestre do SQL Server Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c03cb-103">This topic describes how to make changes to the steps of a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c03cb-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="c03cb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c03cb-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="c03cb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c03cb-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c03cb-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c03cb-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="c03cb-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c03cb-108">**Para realizar alterações às etapas de um trabalho mestre do SQL Server Agent, usando:**</span><span class="sxs-lookup"><span data-stu-id="c03cb-108">**To make changes to the steps of a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="c03cb-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c03cb-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c03cb-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c03cb-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c03cb-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c03cb-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c03cb-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c03cb-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c03cb-113">Um trabalho mestre do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não pode ser destino em ambos os servidores, local e remoto.</span><span class="sxs-lookup"><span data-stu-id="c03cb-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c03cb-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="c03cb-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c03cb-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="c03cb-115">Permissions</span></span>  
 <span data-ttu-id="c03cb-116">A menos que seja membro da função de servidor fixa **sysadmin** , você poderá modificar somente trabalhos de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="c03cb-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="c03cb-117">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="c03cb-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c03cb-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c03cb-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="c03cb-119">Para realizar alterações às etapas de um trabalho mestre do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="c03cb-119">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="c03cb-120">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor que contém o trabalho onde você deseja modificar etapas.</span><span class="sxs-lookup"><span data-stu-id="c03cb-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify steps.</span></span>  
  
2.  <span data-ttu-id="c03cb-121">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="c03cb-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="c03cb-122">Clique no sinal de adição para expandir a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="c03cb-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="c03cb-123">Clique com o botão direito do mouse no trabalho no qual você deseja modificar etapas e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c03cb-123">Right-click the job where you want to modify steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="c03cb-124">Na caixa de diálogo **Propriedades do trabalho –**_Job_name_ , em **selecionar uma página**, selecione **etapas**.</span><span class="sxs-lookup"><span data-stu-id="c03cb-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="c03cb-125">Clique em **Editar** para abrir a caixa de diálogo **Propriedades da etapa de trabalho –**_job_step_name_ .</span><span class="sxs-lookup"><span data-stu-id="c03cb-125">Click **Edit** to open the **Job Step Properties -**_job_step_name_ dialog box.</span></span> <span data-ttu-id="c03cb-126">Para obter mais informações sobre as opções disponíveis nessa caixa de diálogo, consulte [Propriedades da etapa de trabalho: nova etapa de trabalho &#40;&#41;de página Geral](../../integration-services/general-page-of-integration-services-designers-options.md) e [Propriedades da etapa de trabalho: nova etapa de trabalho &#40;página avançado&#41;](job-step-properties-new-job-step-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="c03cb-126">For more information on the available options in this dialog box, see [Job Step Properties: New Job Step &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) and [Job Step Properties: New Job Step &#40;Advanced Page&#41;](job-step-properties-new-job-step-advanced-page.md).</span></span>  
  
7.  <span data-ttu-id="c03cb-127">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c03cb-127">When finished, click **OK**.</span></span>  
  
8.  <span data-ttu-id="c03cb-128">Na caixa de diálogo **Propriedades do trabalho –**_job_name_ , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c03cb-128">In the **Job Properties -**_job_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c03cb-129">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c03cb-129">Using Transact-SQL</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="c03cb-130">Para realizar alterações às etapas de um trabalho mestre do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="c03cb-130">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="c03cb-131">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c03cb-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c03cb-132">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c03cb-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c03cb-133">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c03cb-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the number of retry attempts for the first step of the Weekly Sales Data Backup job.   
    -- After running this example, the number of retry attempts is 10   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1,  
        @retry_attempts = 10 ;  
    GO  
    ```  
  
 <span data-ttu-id="c03cb-134">Para obter mais informações, consulte [sp_update_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c03cb-134">For more information, see [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span></span>  
  
  
