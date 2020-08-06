---
title: Criar uma categoria de trabalho | Microsoft Docs
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
ms.assetid: e24a6d38-d231-4f64-ab89-2d1ef6f5792c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f6daeeca6253861e8a9dcbb72faa2bd55eb2761
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683304"
---
# <a name="create-a-job-category"></a><span data-ttu-id="70554-102">Criar uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="70554-102">Create a Job Category</span></span>
  <span data-ttu-id="70554-103">Este tópico descreve como criar uma categoria de trabalho no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects.</span><span class="sxs-lookup"><span data-stu-id="70554-103">This topic describes how to create a job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="70554-104">O Agent fornece categorias de trabalho internas às quais é possível atribuir trabalhos, mas você também pode criar uma categoria e atribuir-lhe trabalhos.</span><span class="sxs-lookup"><span data-stu-id="70554-104">Agent provides built-in job categories that you can assign jobs to, or you can create a job category and assign jobs to it.</span></span> <span data-ttu-id="70554-105">As categorias de trabalho ajudam a organizar os trabalhos de modo a facilitar sua filtragem e agrupamento.</span><span class="sxs-lookup"><span data-stu-id="70554-105">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="70554-106">Por exemplo, você pode organizar todos os seus trabalhos de backup de banco de dados na categoria Manutenção de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="70554-106">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="70554-107">Você também pode criar suas próprias categorias de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70554-107">You can also create your own job categories.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="70554-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="70554-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="70554-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="70554-109">Limitations and Restrictions</span></span>  
 <span data-ttu-id="70554-110">As categorias multisservidor só existem em um servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="70554-110">Multiserver categories exist only on a master server.</span></span> <span data-ttu-id="70554-111">Há apenas uma categoria de trabalho padrão disponível em um servidor mestre: [**Não Categorizado (Multisservidor)**].</span><span class="sxs-lookup"><span data-stu-id="70554-111">There is only one default job category available on a master server: [**Uncategorized (Multi-Server)**].</span></span> <span data-ttu-id="70554-112">Quando um trabalho multisservidor é baixado, sua categoria é alterada para **Trabalhos do MSX** no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="70554-112">When a multiserver job is downloaded, its category is changed to **Jobs From MSX** at the target server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="70554-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="70554-113">Security</span></span>  
 <span data-ttu-id="70554-114">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="70554-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="70554-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70554-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="70554-116">Para criar uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="70554-116">To create a job category</span></span>  
  
1.  <span data-ttu-id="70554-117">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor no qual você deseja criar uma categoria de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70554-117">In **Object Explorer**, click the plus sign to expand the server where you want to create a job category.</span></span>  
  
2.  <span data-ttu-id="70554-118">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="70554-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="70554-119">Clique com o botão direito do mouse na pasta **Trabalhos** e selecione **Gerenciar Categorias de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="70554-119">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="70554-120">Na caixa de diálogo **gerenciar categorias de trabalho**_server_name_ , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="70554-120">In the **Manage Job Categories**_server_name_ dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="70554-121">Na nova caixa de diálogo, na caixa **Nome** , insira um nome para a nova categoria de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70554-121">In the new dialog box, in the **Name** box, enter a name for the new job category.</span></span>  
  
6.  <span data-ttu-id="70554-122">Marque a caixa de seleção **Mostrar todos os trabalhos** .</span><span class="sxs-lookup"><span data-stu-id="70554-122">Select the **Show all jobs** check box.</span></span> <span data-ttu-id="70554-123">Selecione um ou mais trabalhos para a nova categorias, marcando as caixas correspondentes a eles.</span><span class="sxs-lookup"><span data-stu-id="70554-123">Select one or more jobs for the new category by checking the boxes corresponding to the jobs.</span></span>  
  
7.  <span data-ttu-id="70554-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="70554-124">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="70554-125">Na caixa de diálogo **gerenciar categorias de trabalho**_server_name_ , clique em **Atualizar** para garantir que a nova categoria de trabalho esteja ativa.</span><span class="sxs-lookup"><span data-stu-id="70554-125">In the **Manage Job Categories**_server_name_ dialog box, click **Refresh** to ensure that the new job category is active.</span></span> <span data-ttu-id="70554-126">Se tudo estiver como esperado, feche a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="70554-126">If everything looks as expected, close this dialog box.</span></span>  
  
 <span data-ttu-id="70554-127">Para obter mais informações sobre essas caixas de diálogo, consulte [categorias de trabalho: gerenciar categorias de trabalho](job-categories-manage-job-categories.md) e propriedades de categorias de trabalho [e nova categoria de trabalho](job-categories-properties-new-job-category.md).</span><span class="sxs-lookup"><span data-stu-id="70554-127">For more information on these dialog boxes, see [Job Categories: Manage Job Categories](job-categories-manage-job-categories.md) and [Job Categories Properties and New Job Category](job-categories-properties-new-job-category.md).</span></span>  

##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="70554-128">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="70554-128">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="70554-129">Para criar uma categoria de trabalho</span><span class="sxs-lookup"><span data-stu-id="70554-129">To create a job category</span></span>  
  
1.  <span data-ttu-id="70554-130">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70554-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="70554-131">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="70554-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="70554-132">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="70554-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a local job category named AdminJobs   
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_category  
        @class=N'JOB',  
        @type=N'LOCAL',  
        @name=N'AdminJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="70554-133">Para obter mais informações, consulte [sp_add_category &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70554-133">For more information, see [sp_add_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="70554-134">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="70554-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="70554-135">**Para criar uma categoria de trabalho**</span><span class="sxs-lookup"><span data-stu-id="70554-135">**To create a job category**</span></span>  
  
 <span data-ttu-id="70554-136">Chame a classe `JobCategory` usando uma linguagem de programação que você escolher, como Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70554-136">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="70554-137">Para obter um código de exemplo, consulte [Agendamento de tarefas administrativas automáticas no SQL Server Agent](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="70554-137">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
