---
title: Alterar a associação de uma categoria de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- members [SQL Server], job categories
ms.assetid: 6a18f7f0-eb50-485f-a9c7-df31ae0f994e
author: stevestein
ms.author: sstein
ms.openlocfilehash: d9ed0db394f63594937ad923734b07fed8050955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583331"
---
# <a name="change-the-membership-of-a-job-category"></a><span data-ttu-id="1aab9-102">Change the Membership of a Job Category</span><span class="sxs-lookup"><span data-stu-id="1aab9-102">Change the Membership of a Job Category</span></span>
  <span data-ttu-id="1aab9-103">Este tópico descreve como alterar a associação da categoria de trabalho no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../includes/tsql-md.md)]ou o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="1aab9-103">This topic describes how to change the membership of the job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="1aab9-104">As categorias de trabalho ajudam a organizar os trabalhos de modo a facilitar sua filtragem e agrupamento.</span><span class="sxs-lookup"><span data-stu-id="1aab9-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="1aab9-105">Você pode criar suas próprias categorias de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1aab9-105">You can create your own job categories.</span></span> <span data-ttu-id="1aab9-106">Você também pode alterar a associação de trabalhos do Microsoft SQL Server Agent em categorias de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1aab9-106">You can also change Microsoft SQL Server Agent jobs membership in job categories.</span></span>  
  
 <span data-ttu-id="1aab9-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="1aab9-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1aab9-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="1aab9-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1aab9-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="1aab9-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1aab9-110">**Para alterar a associação de uma categoria de trabalho usando:**</span><span class="sxs-lookup"><span data-stu-id="1aab9-110">**To change the membership of a job category, using:**</span></span>  
  
     [<span data-ttu-id="1aab9-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1aab9-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="1aab9-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1aab9-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="1aab9-113">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="1aab9-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1aab9-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1aab9-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1aab9-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="1aab9-115">Security</span></span>  
 <span data-ttu-id="1aab9-116">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="1aab9-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="1aab9-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1aab9-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="1aab9-118">Para alterar a associação de uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="1aab9-118">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="1aab9-119">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja editar uma categoria de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1aab9-119">In **Object Explorer**, click the plus sign to expand the server where you want to edit a job category.</span></span>  
  
2.  <span data-ttu-id="1aab9-120">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="1aab9-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="1aab9-121">Clique com o botão direito do mouse na pasta **Trabalhos** e selecione **Gerenciar Categorias de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="1aab9-121">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="1aab9-122">Na caixa de diálogo **Gerenciar Categorias de Trabalho**_server_name_ , selecione a categoria de trabalho que você deseja editar e clique em **Exibir Trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="1aab9-122">In the **Manage Job Categories**_server_name_ dialog box, select the job category that you want to edit, and then click **View Jobs**.</span></span>  
  
5.  <span data-ttu-id="1aab9-123">Marque a caixa de seleção **Mostrar todos os trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="1aab9-123">Select the **Show all jobs** check box.</span></span>  
  
6.  <span data-ttu-id="1aab9-124">Para adicionar um trabalho à categoria, na grade principal, marque a caixa de seleção na coluna **Selecionar** correspondente ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="1aab9-124">To add a job to the category, in the main grid, select the check box in the **Select** column corresponding to the job.</span></span> <span data-ttu-id="1aab9-125">Para remover um trabalho da categoria, desmarque a caixa.</span><span class="sxs-lookup"><span data-stu-id="1aab9-125">To remove a job from the category, clear the box.</span></span> <span data-ttu-id="1aab9-126">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1aab9-126">When finished, click **OK**.</span></span>  
  
7.  <span data-ttu-id="1aab9-127">Feche a caixa de diálogo **gerenciar categorias de trabalho**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="1aab9-127">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="1aab9-128">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1aab9-128">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="1aab9-129">Para alterar a associação de uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="1aab9-129">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="1aab9-130">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1aab9-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1aab9-131">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="1aab9-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1aab9-132">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1aab9-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="1aab9-133">Para obter mais informações, consulte [sp_update_job &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1aab9-133">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="1aab9-134">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="1aab9-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="1aab9-135">**Para alterar a associação de uma categoria de trabalho**</span><span class="sxs-lookup"><span data-stu-id="1aab9-135">**To change the membership of a job category**</span></span>  
  
 <span data-ttu-id="1aab9-136">Use a classe `JobCategory` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1aab9-136">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
