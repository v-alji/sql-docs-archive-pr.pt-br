---
title: Limpar o log do histórico do trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- clearing job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 34b9398a-c409-4040-8ea1-0deceb18f961
author: stevestein
ms.author: sstein
ms.openlocfilehash: 813c2c7c86a769eea09a093f2de999460d78ef54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583327"
---
# <a name="clear-the-job-history-log"></a><span data-ttu-id="61f4a-102">Clear the Job History Log</span><span class="sxs-lookup"><span data-stu-id="61f4a-102">Clear the Job History Log</span></span>
  <span data-ttu-id="61f4a-103">Este tópico descreve como excluir o conteúdo do log de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] histórico de trabalhos do Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="61f4a-103">This topic describes how to delete the contents of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="61f4a-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="61f4a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="61f4a-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="61f4a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="61f4a-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="61f4a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="61f4a-107">**Para limpar o log do histórico de trabalhos usando:**</span><span class="sxs-lookup"><span data-stu-id="61f4a-107">**To clear the job history log, using:**</span></span>  
  
     [<span data-ttu-id="61f4a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61f4a-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="61f4a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="61f4a-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="61f4a-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="61f4a-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="61f4a-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="61f4a-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="61f4a-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="61f4a-112">Security</span></span>  
 <span data-ttu-id="61f4a-113">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="61f4a-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="61f4a-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61f4a-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="61f4a-115">Para limpar o log de histórico do trabalho</span><span class="sxs-lookup"><span data-stu-id="61f4a-115">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="61f4a-116">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="61f4a-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="61f4a-117">Expanda o **SQL Server Agent**e, em seguida, **Trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="61f4a-117">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="61f4a-118">Clique com o botão direito do mouse em um trabalho e em **Exibir histórico**.</span><span class="sxs-lookup"><span data-stu-id="61f4a-118">Right-click a job and click **View history**.</span></span>  
  
4.  <span data-ttu-id="61f4a-119">No **Visualizador de Arquivos de Log**, selecione o trabalho cujo histórico você deseja limpar e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="61f4a-119">In the **Log File Viewer**, select the job for which you want to clear history, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="61f4a-120">Clique em **Excluir**e, em seguida, em **Excluir todo o histórico** , na caixa de diálogo **Excluir Histórico** .</span><span class="sxs-lookup"><span data-stu-id="61f4a-120">Click **Delete**, and then click **Delete all history** in the **Delete History** dialog.</span></span> <span data-ttu-id="61f4a-121">Você pode excluir todo o histórico de trabalhos ou apenas históricos anteriores a uma data especificada.</span><span class="sxs-lookup"><span data-stu-id="61f4a-121">You can delete all job history or only history that is older than a specified date.</span></span> <span data-ttu-id="61f4a-122">Se desejar remover todo o histórico de trabalhos, clique em **Excluir todo o histórico**.</span><span class="sxs-lookup"><span data-stu-id="61f4a-122">If you want to remove all job history, click **Delete all history**.</span></span> <span data-ttu-id="61f4a-123">Se desejar remover apenas logs de histórico de trabalhos mais antigos, clique em **Excluir histórico antes de**e especifique uma data.</span><span class="sxs-lookup"><span data-stu-id="61f4a-123">If you only want to remove older job history logs, click **Delete history before**, and then specify a date.</span></span>  
  
    -   <span data-ttu-id="61f4a-124">Clique em **Status do trabalho** se desejar limpar o log de histórico de um trabalho multisservidor.</span><span class="sxs-lookup"><span data-stu-id="61f4a-124">Click **Job status** if you want to clear the history log of a multiserver job.</span></span> <span data-ttu-id="61f4a-125">Clique em **Trabalho**, clique em um nome de trabalho e, em seguida, em **Exibir Histórico do Trabalho Remoto**.</span><span class="sxs-lookup"><span data-stu-id="61f4a-125">Click **Job**, click a job name, and then click **View Remote Job History**.</span></span>  
  
5.  <span data-ttu-id="61f4a-126">Clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="61f4a-126">Click **Delete**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="61f4a-127">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="61f4a-127">Using Transact-SQL</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="61f4a-128">Para limpar o log de histórico do trabalho</span><span class="sxs-lookup"><span data-stu-id="61f4a-128">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="61f4a-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61f4a-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="61f4a-130">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="61f4a-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="61f4a-131">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="61f4a-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- example removes the history for a job named NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_purge_jobhistory  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="61f4a-132">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="61f4a-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="61f4a-133">**Para limpar o log de histórico do trabalho**</span><span class="sxs-lookup"><span data-stu-id="61f4a-133">**To clear the job history log**</span></span>  
  
 <span data-ttu-id="61f4a-134">Use o método `PurgeJobHistory` da classe `JobServer` usando uma linguagem de programação que você escolher, como o Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61f4a-134">Use the `PurgeJobHistory` method of the `JobServer` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="61f4a-135">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="61f4a-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
