---
title: Exibir um trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], viewing
- viewing jobs
- SQL Server Agent jobs, viewing
- displaying jobs
ms.assetid: d2241a3f-dbcf-433c-b7bc-f96bdf0eac8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 26406aaf2ba0ac4809eb7ac2c84799469d0468d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583966"
---
# <a name="view-a-job"></a><span data-ttu-id="889c1-102">View a Job</span><span class="sxs-lookup"><span data-stu-id="889c1-102">View a Job</span></span>
  <span data-ttu-id="889c1-103">Este tópico descreve como exibir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalhos do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="889c1-103">This topic describes how to view [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="889c1-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="889c1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="889c1-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="889c1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="889c1-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="889c1-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="889c1-107">**Para exibir um trabalho, usando:**</span><span class="sxs-lookup"><span data-stu-id="889c1-107">**To view a job, using:**</span></span>  
  
     [<span data-ttu-id="889c1-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="889c1-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="889c1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="889c1-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="889c1-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="889c1-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="889c1-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="889c1-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="889c1-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="889c1-112">Security</span></span>  
 <span data-ttu-id="889c1-113">Você só pode exibir trabalhos de sua propriedade, a não ser que você seja membro da função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="889c1-113">You can only view jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="889c1-114">Membros dessa função podem exibir todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="889c1-114">Members of this role can view all jobs.</span></span> <span data-ttu-id="889c1-115">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="889c1-115">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="889c1-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="889c1-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="889c1-117">Para exibir um trabalho</span><span class="sxs-lookup"><span data-stu-id="889c1-117">To view a job</span></span>  
  
1.  <span data-ttu-id="889c1-118">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="889c1-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="889c1-119">Expanda o **SQL Server Agent**e, em seguida, **Trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="889c1-119">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="889c1-120">Clique com o botão direito do mouse em um trabalho e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="889c1-120">Right-click a job, and then click **Properties**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="889c1-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="889c1-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="889c1-122">Para exibir um trabalho</span><span class="sxs-lookup"><span data-stu-id="889c1-122">To view a job</span></span>  
  
1.  <span data-ttu-id="889c1-123">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="889c1-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="889c1-124">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="889c1-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="889c1-125">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="889c1-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all aspects of the information for the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_job  
        @job_name = N'NightlyBackups',  
        @job_aspect = N'ALL' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="889c1-126">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="889c1-126">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="889c1-127">**Para exibir um trabalho**</span><span class="sxs-lookup"><span data-stu-id="889c1-127">**To view a job**</span></span>  
  
 <span data-ttu-id="889c1-128">Use a classe `Job` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="889c1-128">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="889c1-129">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="889c1-129">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
