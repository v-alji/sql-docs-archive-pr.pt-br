---
title: Excluir um log de etapa de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [SQL Server Agent]
- deleting job step logs
- logs [SQL Server], jobs
- removing job step logs
ms.assetid: ee20c6cd-0258-4550-bdb0-71e86a0fb330
author: stevestein
ms.author: sstein
ms.openlocfilehash: de7c64c4d7cf461eef563ae6989e043d125c6f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575000"
---
# <a name="delete-a-job-step-log"></a><span data-ttu-id="311ed-102">Delete a Job Step Log</span><span class="sxs-lookup"><span data-stu-id="311ed-102">Delete a Job Step Log</span></span>
  <span data-ttu-id="311ed-103">Este tópico descreve como excluir um log de etapa de trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="311ed-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step log.</span></span>  
  
-   <span data-ttu-id="311ed-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="311ed-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="311ed-105">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="311ed-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="311ed-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="311ed-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="311ed-107">**Para excluir um log de etapas de trabalho do SQL Server Agent usando:**</span><span class="sxs-lookup"><span data-stu-id="311ed-107">**To delete a SQL Server Agent job step log, using:**</span></span>  
  
     [<span data-ttu-id="311ed-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="311ed-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="311ed-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="311ed-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="311ed-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="311ed-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="311ed-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="311ed-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="311ed-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="311ed-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="311ed-113">Quando etapas de trabalho são excluídas seu log de saída é excluído automaticamente.</span><span class="sxs-lookup"><span data-stu-id="311ed-113">When job steps are deleted their output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="311ed-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="311ed-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="311ed-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="311ed-115">Permissions</span></span>  
 <span data-ttu-id="311ed-116">A menos que seja membro da função de servidor fixa **sysadmin** , você poderá modificar somente trabalhos de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="311ed-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="311ed-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="311ed-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="311ed-118">Para excluir um log de etapas de trabalho do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="311ed-118">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="311ed-119">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="311ed-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="311ed-120">Expanda o **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho que deseja modificar e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="311ed-120">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="311ed-121">Na caixa de diálogo **Propriedades do Trabalho** , exclua a etapa de trabalho selecionada.</span><span class="sxs-lookup"><span data-stu-id="311ed-121">In the **Job Properties** dialog box, delete the selected job step.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="311ed-122">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="311ed-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="311ed-123">Para excluir um log de etapas de trabalho do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="311ed-123">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="311ed-124">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="311ed-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="311ed-125">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="311ed-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="311ed-126">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="311ed-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- removes the job step log for step 2 in the job Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobsteplog  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 2;  
    GO  
    ```  
  
 <span data-ttu-id="311ed-127">Para obter mais informações, consulte [sp_delete_jobsteplog &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="311ed-127">For more information, see [sp_delete_jobsteplog &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="311ed-128">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="311ed-128">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="311ed-129">Use os métodos `DeleteJobStepLogs` da classe `Job` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="311ed-129">Use the `DeleteJobStepLogs` methods of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="311ed-130">Para obter mais informações, consulte[SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="311ed-130">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
```powershell
# Delete all job step log files that have ID values larger than 5.  
$srv = New-Object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = $srv.JobServer.Jobs["Test Job"]  
$jb.DeleteJobStepLogs(5)  
```
