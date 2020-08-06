---
title: Excluir uma categoria de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- deleting job category
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- removing job category
ms.assetid: 47a7640b-20b3-4639-ab37-b6fc73575e6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: e96dd0461f3dace138b7822cdbaaa2fa242e2cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679120"
---
# <a name="delete-a-job-category"></a><span data-ttu-id="ac8c2-102">Excluir uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="ac8c2-102">Delete a Job Category</span></span>
  <span data-ttu-id="ac8c2-103">Este tópico descreve como excluir uma [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] categoria de trabalho do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-103">This topic describes how to delete a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="ac8c2-104">As categorias de trabalho ajudam a organizar os trabalhos de modo a facilitar sua filtragem e agrupamento.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="ac8c2-105">Por exemplo, você pode organizar todos os seus trabalhos de backup de banco de dados na categoria Manutenção de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span>  

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ac8c2-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ac8c2-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ac8c2-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="ac8c2-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ac8c2-108">Quando se exclui uma categoria de trabalho definida pelo usuário, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent solicita que os trabalhos a ela atribuídos sejam reatribuídos a outra categoria.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-108">When you delete a user-defined job category, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent prompts you to reassign the jobs that are assigned to it to another job category.</span></span> <span data-ttu-id="ac8c2-109">Você só pode excluir categorias de trabalho definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-109">You can only delete user-defined job categories.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ac8c2-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="ac8c2-110">Security</span></span>  
 <span data-ttu-id="ac8c2-111">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="ac8c2-111">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="ac8c2-112">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ac8c2-112">Using SQL Server Management Studio</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="ac8c2-113">Para excluir uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="ac8c2-113">To delete a job category</span></span>  
  
1.  <span data-ttu-id="ac8c2-114">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja excluir uma categoria de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-114">In **Object Explorer**, click the plus sign to expand the server where you want to delete a job category.</span></span>  
  
2.  <span data-ttu-id="ac8c2-115">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-115">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="ac8c2-116">Clique com o botão direito do mouse na pasta **Trabalhos** e selecione **Gerenciar Categorias de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-116">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="ac8c2-117">Na caixa de diálogo **gerenciar categorias de trabalho**_server_name_ , selecione a categoria de trabalho a ser excluída.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-117">In the **Manage Job Categories**_server_name_ dialog box, select the job category to delete.</span></span>  
  
5.  <span data-ttu-id="ac8c2-118">Clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-118">Click **Delete**.</span></span>  
  
6.  <span data-ttu-id="ac8c2-119">Na caixa de diálogo **Categorias de Trabalho** , clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-119">In the **Job Categories** dialog box, click **Yes**.</span></span>  
  
7.  <span data-ttu-id="ac8c2-120">Feche a caixa de diálogo **gerenciar categorias de trabalho**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="ac8c2-120">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="ac8c2-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ac8c2-121">Using Transact-SQL</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="ac8c2-122">Para excluir uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="ac8c2-122">To delete a job category</span></span>  
  
1.  <span data-ttu-id="ac8c2-123">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac8c2-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ac8c2-124">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ac8c2-125">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- deletes the job category named AdminJobs.  
    USE msdb ;  
    GO   
    EXEC dbo.sp_delete_category  
        @name = N'AdminJobs',  
        @class = N'JOB' ;  
    GO  
    ```  
  
 <span data-ttu-id="ac8c2-126">Para obter mais informações, consulte [sp_delete_category &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ac8c2-126">For more information, see [sp_delete_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span></span>  

  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="ac8c2-127">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="ac8c2-127">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-a-job-category"></a><span data-ttu-id="ac8c2-128">Para excluir uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="ac8c2-128">To delete a job category</span></span>
  
 <span data-ttu-id="ac8c2-129">Chame a classe `JobCategory` usando uma linguagem de programação que você escolher, como Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac8c2-129">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
