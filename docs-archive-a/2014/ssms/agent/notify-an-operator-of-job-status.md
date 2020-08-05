---
title: Notificar um operador sobre o status do trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- jobs [SQL Server Agent], notification options
- SQL Server Agent jobs, status
- jobs [SQL Server Agent], status
- SQL Server Agent jobs, notification options
- notifications [SQL Server], job status
ms.assetid: e7399505-27ac-48d9-a637-73bf92b9df49
author: stevestein
ms.author: sstein
ms.openlocfilehash: a202327ad63cf7ef8f51d3572b257816ee6d9419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572335"
---
# <a name="notify-an-operator-of-job-status"></a><span data-ttu-id="ffed2-102">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="ffed2-102">Notify an Operator of Job Status</span></span>
  <span data-ttu-id="ffed2-103">Este tópico descreve como definir as opções de notificação no usando [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects, para que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent possa enviar notificações para operadores sobre trabalhos.</span><span class="sxs-lookup"><span data-stu-id="ffed2-103">This topic describes how to set notification options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects, so [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can send notifications to operators about jobs.</span></span>  
  
 <span data-ttu-id="ffed2-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ffed2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ffed2-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="ffed2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ffed2-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="ffed2-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ffed2-107">**Para notificar um operador sobre o status do trabalho usando:**</span><span class="sxs-lookup"><span data-stu-id="ffed2-107">**To notify an operator of job status, using:**</span></span>  
  
     [<span data-ttu-id="ffed2-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ffed2-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="ffed2-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ffed2-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="ffed2-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="ffed2-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ffed2-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ffed2-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ffed2-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="ffed2-112">Security</span></span>  
 <span data-ttu-id="ffed2-113">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="ffed2-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="ffed2-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ffed2-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="ffed2-115">Para notificar um operador sobre o status do trabalho</span><span class="sxs-lookup"><span data-stu-id="ffed2-115">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="ffed2-116">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="ffed2-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ffed2-117">Expanda **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho que deseja editar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ffed2-117">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="ffed2-118">Na caixa de diálogo **Propriedades do Trabalho** , selecione a página **Notificações** .</span><span class="sxs-lookup"><span data-stu-id="ffed2-118">In the **Job Properties** dialog box, select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="ffed2-119">Se desejar notificar um operador via email, marque **Email**, escolha um operador na lista e selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="ffed2-119">If you want to notify an operator by e-mail, check **E-mail**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="ffed2-120">**Quando o trabalho for bem-sucedido** , para notificar o operador quando o trabalho for concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="ffed2-120">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="ffed2-121">**Quando ocorrer falha no trabalho** para notificar o operador quando o trabalho não for concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="ffed2-121">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="ffed2-122">**Quando o trabalho for concluído** , para notificar o operador independentemente do status de conclusão.</span><span class="sxs-lookup"><span data-stu-id="ffed2-122">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
5.  <span data-ttu-id="ffed2-123">Se desejar notificar um operador via pager, marque **Pager**, escolha um operador na lista e selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="ffed2-123">If you want to notify an operator by pager, check **Page**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="ffed2-124">**Quando o trabalho for bem-sucedido** , para notificar o operador quando o trabalho for concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="ffed2-124">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="ffed2-125">**Quando ocorrer falha no trabalho** para notificar o operador quando o trabalho não for concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="ffed2-125">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="ffed2-126">**Quando o trabalho for concluído** , para notificar o operador independentemente do status de conclusão.</span><span class="sxs-lookup"><span data-stu-id="ffed2-126">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
6.  <span data-ttu-id="ffed2-127">Se desejar notificar um operador via net send, marque **Net send**, escolha um operador na lista e selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="ffed2-127">If you want to notify an operator by net send, check **Net send**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="ffed2-128">**Quando o trabalho for bem-sucedido** , para notificar o operador quando o trabalho for concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="ffed2-128">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="ffed2-129">**Quando ocorrer falha no trabalho** para notificar o operador quando o trabalho não for concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="ffed2-129">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="ffed2-130">**Quando o trabalho for concluído** , para notificar o operador independentemente do status de conclusão.</span><span class="sxs-lookup"><span data-stu-id="ffed2-130">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="ffed2-131">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ffed2-131">Using Transact-SQL</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="ffed2-132">Para notificar um operador sobre o status do trabalho</span><span class="sxs-lookup"><span data-stu-id="ffed2-132">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="ffed2-133">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffed2-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ffed2-134">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ffed2-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ffed2-135">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="ffed2-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adds an e-mail notification for the specified alert (Test Alert).  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_notification   
    @alert_name = N'Test Alert',   
    @operator_name = N'Fran??ois Ajenstat',   
    @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="ffed2-136">Para obter mais informações, consulte [sp_add_notification &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ffed2-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="ffed2-137">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="ffed2-137">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="ffed2-138">**Para notificar um operador sobre o status do trabalho**</span><span class="sxs-lookup"><span data-stu-id="ffed2-138">**To notify an operator of job status**</span></span>  
  
 <span data-ttu-id="ffed2-139">Use a classe `Job` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ffed2-139">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="ffed2-140">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="ffed2-140">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
