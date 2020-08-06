---
title: Atribuir um trabalho a uma categoria de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], assigning
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- SQL Server Agent jobs, assigning
- assigning job to category
ms.assetid: a9ea65a2-1d73-4582-a335-63adeb450cb6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 208ff6722a9c18fd4dd0d061575f0d496af27810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583334"
---
# <a name="assign-a-job-to-a-job-category"></a><span data-ttu-id="1d6a0-102">Atribuir um trabalho a uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="1d6a0-102">Assign a Job to a Job Category</span></span>
  <span data-ttu-id="1d6a0-103">Este tópico descreve como atribuir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalhos do Agent a categorias de trabalho no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to job categories in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="1d6a0-104">As categorias de trabalho ajudam a organizar os trabalhos de modo a facilitar sua filtragem e agrupamento.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="1d6a0-105">Por exemplo, você pode organizar todos os seus trabalhos de backup de banco de dados na categoria Manutenção de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="1d6a0-106">É possível atribuir trabalhos a categorias de trabalho internas ou criar uma categoria de trabalho definida pelo usuário e atribuir trabalhos a ela.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-106">You can assign jobs to built-in job categories, or you can create a user-defined job category and then assign jobs to that.</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1d6a0-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1d6a0-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1d6a0-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="1d6a0-108">Security</span></span>  
 <span data-ttu-id="1d6a0-109">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="1d6a0-109">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="1d6a0-110">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d6a0-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="1d6a0-111">Para atribuir um trabalho a uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="1d6a0-111">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="1d6a0-112">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja atribuir um trabalho a uma categoria de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-112">In **Object Explorer**, click the plus sign to expand the server where you want to assign a job to a job category.</span></span>  
  
2.  <span data-ttu-id="1d6a0-113">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-113">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="1d6a0-114">Clique no sinal de adição para expandir a pasta **Trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="1d6a0-114">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="1d6a0-115">Clique com o botão direito do mouse no trabalho que deseja editar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-115">Right-click the job you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="1d6a0-116">Na caixa de diálogo **Propriedades do trabalho –**_job_name_ , na lista **categoria** , selecione a categoria de trabalho que você deseja atribuir ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-116">In the **Job Properties -**_job_name_ dialog box, in the **Category** list, select the job category you want to assign to the job.</span></span>  
  
6.  <span data-ttu-id="1d6a0-117">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-117">Click **OK**.</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="1d6a0-118">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1d6a0-118">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="1d6a0-119">Para atribuir um trabalho a uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="1d6a0-119">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="1d6a0-120">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d6a0-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1d6a0-121">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1d6a0-122">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="1d6a0-123">Para obter mais informações, consulte [sp_update_job &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1d6a0-123">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="1d6a0-124">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="1d6a0-124">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="1d6a0-125">**Para atribuir um trabalho a uma categoria de trabalho**</span><span class="sxs-lookup"><span data-stu-id="1d6a0-125">**To assign a job to a job category**</span></span>  
  
 <span data-ttu-id="1d6a0-126">Use a classe `JobCategory` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d6a0-126">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
  
  
