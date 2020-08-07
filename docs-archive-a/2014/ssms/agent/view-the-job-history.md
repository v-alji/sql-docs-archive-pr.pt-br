---
title: Exibir o histórico de trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- viewing job history
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
- displaying job history
ms.assetid: 3bbd1556-abdb-48a3-b249-546eace76343
author: stevestein
ms.author: sstein
ms.openlocfilehash: e84fafdaeddb5748a8129cd5d71d667db7e5fa37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682062"
---
# <a name="view-the-job-history"></a><span data-ttu-id="95d8f-102">View the Job History</span><span class="sxs-lookup"><span data-stu-id="95d8f-102">View the Job History</span></span>
  <span data-ttu-id="95d8f-103">Este tópico descreve como exibir o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log de histórico de trabalhos do Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="95d8f-103">This topic describes how to view the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="95d8f-104">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="95d8f-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="95d8f-105">Segurança</span><span class="sxs-lookup"><span data-stu-id="95d8f-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="95d8f-106">**Para exibir o log do histórico de trabalhos usando:**</span><span class="sxs-lookup"><span data-stu-id="95d8f-106">**To view the job history log, using:**</span></span>  
  
     [<span data-ttu-id="95d8f-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="95d8f-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="95d8f-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="95d8f-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="95d8f-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="95d8f-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="95d8f-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="95d8f-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="95d8f-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="95d8f-111">Security</span></span>  
 <span data-ttu-id="95d8f-112">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="95d8f-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="95d8f-113">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="95d8f-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="95d8f-114">Para exibir o log de histórico do trabalho</span><span class="sxs-lookup"><span data-stu-id="95d8f-114">To view the job history log</span></span>  
  
1.  <span data-ttu-id="95d8f-115">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="95d8f-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="95d8f-116">Expanda o **SQL Server Agent**e, em seguida, **Trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="95d8f-116">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="95d8f-117">Clique com o botão direito do mouse em um trabalho e então em **Exibir Histórico**.</span><span class="sxs-lookup"><span data-stu-id="95d8f-117">Right-click a job, and then click **View History**.</span></span>  
  
4.  <span data-ttu-id="95d8f-118">No Visualizador de Arquivos de Log, examine o histórico do trabalho.</span><span class="sxs-lookup"><span data-stu-id="95d8f-118">In the Log File Viewer, view the job history.</span></span>  
  
5.  <span data-ttu-id="95d8f-119">Para atualizar o histórico do trabalho, clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="95d8f-119">To update the job history, click **Refresh**.</span></span> <span data-ttu-id="95d8f-120">Para exibir menos linhas, clique no botão **Filtro** e insira parâmetros de filtro.</span><span class="sxs-lookup"><span data-stu-id="95d8f-120">To view fewer rows, click the **Filter** button and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="95d8f-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="95d8f-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="95d8f-122">Para exibir o log de histórico do trabalho</span><span class="sxs-lookup"><span data-stu-id="95d8f-122">To view the job history log</span></span>  
  
1.  <span data-ttu-id="95d8f-123">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95d8f-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="95d8f-124">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="95d8f-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="95d8f-125">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="95d8f-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all job information for the NightlyBackups job.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobhistory   
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="95d8f-126">Para obter mais informações, consulte [sp_help_jobhistory &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="95d8f-126">For more information, see [sp_help_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="95d8f-127">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="95d8f-127">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="95d8f-128">**Para exibir o log de histórico do trabalho**</span><span class="sxs-lookup"><span data-stu-id="95d8f-128">**To view the job history log**</span></span>  
  
 <span data-ttu-id="95d8f-129">Chame o método `EnumHistory` da classe `Job` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95d8f-129">Call the `EnumHistory` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="95d8f-130">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="95d8f-130">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
