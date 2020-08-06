---
title: Desabilitar ou habilitar um trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- stopping jobs
- disabling jobs
- SQL Server Agent jobs, disabling
- jobs [SQL Server Agent], disabling
ms.assetid: 5041261f-0c32-4d4a-8bee-59a6c16200dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42fe7cbeed1e2ff3f93b1afef52b165a7d660ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569025"
---
# <a name="disable-or-enable-a-job"></a><span data-ttu-id="00eef-102">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="00eef-102">Disable or Enable a Job</span></span>
  <span data-ttu-id="00eef-103">Este tópico descreve como desabilitar um trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00eef-103">This topic describes how to disable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="00eef-104">Quando um trabalho é desabilitado, ele não é excluído e pode ser habilitado novamente quando necessário.</span><span class="sxs-lookup"><span data-stu-id="00eef-104">When you disable a job, it is not deleted and can be enabled again when necessary.</span></span>  
  
 <span data-ttu-id="00eef-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="00eef-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="00eef-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="00eef-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="00eef-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="00eef-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="00eef-108">**Para desabilitar ou habilitar um trabalho usando:**</span><span class="sxs-lookup"><span data-stu-id="00eef-108">**To disable or enable a job, using:**</span></span>  
  
     [<span data-ttu-id="00eef-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="00eef-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="00eef-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="00eef-110">Transact-SQL</span></span>](#TSQL)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="00eef-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="00eef-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="00eef-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="00eef-112">Security</span></span>  
 <span data-ttu-id="00eef-113">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="00eef-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="00eef-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="00eef-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="00eef-115">Para desabilitar ou habilitar um trabalho</span><span class="sxs-lookup"><span data-stu-id="00eef-115">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="00eef-116">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="00eef-116">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="00eef-117">Expanda o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="00eef-117">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="00eef-118">Expanda **Trabalhos**e clique com o botão direito do mouse no trabalho que deseja desabilitar ou habilitar.</span><span class="sxs-lookup"><span data-stu-id="00eef-118">Expand **Jobs**, and then right-click the job that you want to disable or enable.</span></span>  
  
4.  <span data-ttu-id="00eef-119">Para desabilitar um trabalho, clique em **Desabilitar**.</span><span class="sxs-lookup"><span data-stu-id="00eef-119">To disable a job, click **Disable**.</span></span> <span data-ttu-id="00eef-120">Para habilitar um trabalho, clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="00eef-120">To enable a job, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="00eef-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="00eef-121">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="00eef-122">Para desabilitar ou habilitar um trabalho</span><span class="sxs-lookup"><span data-stu-id="00eef-122">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="00eef-123">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00eef-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="00eef-124">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="00eef-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="00eef-125">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="00eef-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the name, description, and enables status of the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @new_name = N'NightlyBackups -- Disabled',  
        @description = N'Nightly backups disabled during server migration.',  
        @enabled = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="00eef-126">Para obter mais informações, consulte [sp_update_job &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="00eef-126">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
