---
title: Alterar os detalhes do agendamento para um trabalho mestre do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: f5414451-4d8e-464b-bd9e-f2b70c6899b3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 85546bc93e6626bfcc85a28f06a4c2fe24fe9fd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583330"
---
# <a name="change-the-scheduling-details-for-a-sql-server-agent-master-job"></a><span data-ttu-id="a024a-102">Change the Scheduling Details for a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="a024a-102">Change the Scheduling Details for a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="a024a-103">Este tópico descreve como alterar os detalhes do agendamento para uma definição de trabalho no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a024a-103">This topic describes how to change the scheduling details for a job definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a024a-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="a024a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a024a-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="a024a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a024a-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a024a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a024a-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="a024a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a024a-108">**Para alterar os detalhes do agendamento de uma definição de trabalho, usando:**</span><span class="sxs-lookup"><span data-stu-id="a024a-108">**To change the scheduling details for a job definition, using:**</span></span>  
  
     [<span data-ttu-id="a024a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a024a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a024a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a024a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a024a-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a024a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a024a-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a024a-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a024a-113">Um trabalho mestre do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não pode ser destino em ambos os servidores, local e remoto.</span><span class="sxs-lookup"><span data-stu-id="a024a-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a024a-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="a024a-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a024a-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="a024a-115">Permissions</span></span>  
 <span data-ttu-id="a024a-116">A menos que seja membro da função de servidor fixa **sysadmin** , você poderá modificar somente trabalhos de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="a024a-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="a024a-117">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="a024a-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a024a-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a024a-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="a024a-119">Para alterar os detalhes do agendamento de uma definição de trabalho</span><span class="sxs-lookup"><span data-stu-id="a024a-119">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="a024a-120">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor que contém o trabalho cujo agendamento você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="a024a-120">In **Object Explorer,** click the plus sign to expand the server that contains the job whose schedule you want to edit.</span></span>  
  
2.  <span data-ttu-id="a024a-121">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="a024a-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a024a-122">Clique no sinal de adição para expandir a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="a024a-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="a024a-123">Clique com o botão direito do mouse no trabalho cujo agendamento você quer editar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a024a-123">Right-click the job whose schedule you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="a024a-124">Na caixa de diálogo **Propriedades do trabalho –**_Job_name_ , em **selecionar uma página**, selecione **agendamentos**.</span><span class="sxs-lookup"><span data-stu-id="a024a-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Schedules**.</span></span> <span data-ttu-id="a024a-125">Para obter mais informações sobre as opções disponíveis nesta página, consulte [Propriedades do trabalho: novo trabalho &#40;agendas&#41;página ](job-properties-new-job-schedules-page.md).</span><span class="sxs-lookup"><span data-stu-id="a024a-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md).</span></span>  
  
6.  <span data-ttu-id="a024a-126">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a024a-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a024a-127">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a024a-127">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="a024a-128">Para alterar os detalhes do agendamento de uma definição de trabalho</span><span class="sxs-lookup"><span data-stu-id="a024a-128">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="a024a-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a024a-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a024a-130">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="a024a-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a024a-131">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a024a-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled status of the NightlyJobs schedule to 0   
    -- and sets the owner to terrid.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_schedule  
        @name = 'NightlyJobs',  
        @enabled = 0,  
        @owner_login_name = 'terrid' ;  
    GO  
    ```  
  
 <span data-ttu-id="a024a-132">Para obter mais informações, consulte [sp_update_schedule &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a024a-132">For more information, see [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span></span>  
  
  
