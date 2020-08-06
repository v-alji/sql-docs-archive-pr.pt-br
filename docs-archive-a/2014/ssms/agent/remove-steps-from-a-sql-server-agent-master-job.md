---
title: Remover etapas de um trabalho mestre do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 871e6162-1221-464d-8f7f-7e454dcd9edb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5996971225ee0b300b307c5af24dec464dbfd43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583300"
---
# <a name="remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="b8ba7-102">Remove Steps from a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="b8ba7-102">Remove Steps from a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="b8ba7-103">Este tópico descreve como remover etapas de um trabalho mestre do SQL Server Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8ba7-103">This topic describes how to remove steps from a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b8ba7-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="b8ba7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b8ba7-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b8ba7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b8ba7-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b8ba7-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b8ba7-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="b8ba7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b8ba7-108">**Para remover etapas de um trabalho mestre do SQL Server Agent, usando:**</span><span class="sxs-lookup"><span data-stu-id="b8ba7-108">**To remove steps from a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="b8ba7-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8ba7-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b8ba7-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b8ba7-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b8ba7-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b8ba7-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b8ba7-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b8ba7-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b8ba7-113">Um trabalho mestre do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não pode ser destino em ambos os servidores, local e remoto.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b8ba7-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="b8ba7-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b8ba7-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="b8ba7-115">Permissions</span></span>  
 <span data-ttu-id="b8ba7-116">A menos que seja membro da função de servidor fixa **sysadmin** , você poderá modificar somente trabalhos de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="b8ba7-117">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="b8ba7-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b8ba7-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8ba7-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="b8ba7-119">Para remover etapas de um trabalho mestre do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="b8ba7-119">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="b8ba7-120">No **Pesquisador de Objetos** , clique no sinal de adição para expandir o servidor que contém o trabalho onde você deseja excluir etapas.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to delete steps.</span></span>  
  
2.  <span data-ttu-id="b8ba7-121">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="b8ba7-122">Clique no sinal de adição para expandir a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="b8ba7-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="b8ba7-123">Clique com o botão direito do mouse no trabalho no qual você deseja excluir etapas e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-123">Right-click the job where you want to delete steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="b8ba7-124">Na caixa de diálogo **Propriedades do trabalho –**_Job_name_ , em **selecionar uma página**, selecione **etapas**.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="b8ba7-125">Na **Lista de etapas de trabalho**, selecione a etapa de trabalho que você deseja excluir e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-125">Under **Job step list**, select the job step you want to delete and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="b8ba7-126">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b8ba7-127">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b8ba7-127">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="b8ba7-128">Para remover etapas de um trabalho mestre do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="b8ba7-128">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="b8ba7-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8ba7-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b8ba7-130">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b8ba7-131">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b8ba7-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes job step 1 from the job Weekly Sales Data Backup   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="b8ba7-132">Para obter mais informações, consulte [sp_delete_jobstep &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b8ba7-132">For more information, see [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span></span>  
  
  
