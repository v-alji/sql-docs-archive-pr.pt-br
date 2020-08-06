---
title: Excluir um ou mais trabalhos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, deleting
- dropping jobs
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 67dcdad0-57b2-431c-b77f-4ffc926af93d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 436625f9ad629a6b0e574aa046059f4e7e9c2bf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569816"
---
# <a name="delete-one-or-more-jobs"></a><span data-ttu-id="82fb4-102">Excluir um ou mais trabalhos</span><span class="sxs-lookup"><span data-stu-id="82fb4-102">Delete One or More Jobs</span></span>
  <span data-ttu-id="82fb4-103">Este tópico descreve como excluir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalhos do Agent no usando o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , o ou o [!INCLUDE[tsql](../../includes/tsql-md.md)] SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="82fb4-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="82fb4-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="82fb4-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="82fb4-105">Segurança</span><span class="sxs-lookup"><span data-stu-id="82fb4-105">Security</span></span>  
 <span data-ttu-id="82fb4-106">A menos que seja membro da função de servidor fixa **sysadmin** , você só poderá excluir trabalhos de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="82fb4-106">Unless you are a member of the **sysadmin** fixed server role, you can only delete jobs that you own.</span></span>  
  
 
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="82fb4-107">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="82fb4-107">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="82fb4-108">Para excluir um trabalho</span><span class="sxs-lookup"><span data-stu-id="82fb4-108">To delete a job</span></span>  
  
1.  <span data-ttu-id="82fb4-109">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="82fb4-109">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="82fb4-110">Expanda **SQL Server Agent**, expanda **Trabalhos**, clique com o botão direito do mouse no trabalho que deseja excluir e então clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="82fb4-110">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="82fb4-111">Na caixa de diálogo **Excluir Objeto** , verifique se o trabalho que você pretende excluir está selecionado.</span><span class="sxs-lookup"><span data-stu-id="82fb4-111">In the **Delete Object** dialog box, confirm that the job you intend to delete is selected.</span></span>  
  
4.  <span data-ttu-id="82fb4-112">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="82fb4-112">Click **OK**.</span></span>  
  
#### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="82fb4-113">Para excluir vários trabalhos</span><span class="sxs-lookup"><span data-stu-id="82fb4-113">To delete multiple jobs</span></span>  
  
1.  <span data-ttu-id="82fb4-114">No Pesquisador de **objetos,** Conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda essa instância.</span><span class="sxs-lookup"><span data-stu-id="82fb4-114">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="82fb4-115">Expanda o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="82fb4-115">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="82fb4-116">Clique com o botão direito do mouse em **Monitor de Atividade do Trabalho**e clique em **Exibir Atividade do Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="82fb4-116">Right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="82fb4-117">No Monitor de Atividade do Trabalho, selecione os trabalhos que deseja excluir, clique com o botão direito do mouse em sua seleção e escolha **Excluir trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="82fb4-117">In the Job Activity Monitor, select the jobs you want to delete, right-click your selection, and choose **Delete jobs**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="82fb4-118">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="82fb4-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="82fb4-119">Para excluir um trabalho</span><span class="sxs-lookup"><span data-stu-id="82fb4-119">To delete a job</span></span>  
  
1.  <span data-ttu-id="82fb4-120">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82fb4-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="82fb4-121">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="82fb4-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="82fb4-122">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="82fb4-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC sp_delete_job  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="82fb4-123">Para obter mais informações, consulte [sp_delete_job &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82fb4-123">For more information, see [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="82fb4-124">Usando SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="82fb4-124">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="82fb4-125">Para excluir vários trabalhos</span><span class="sxs-lookup"><span data-stu-id="82fb4-125">To delete multiple jobs</span></span>
  
 <span data-ttu-id="82fb4-126">Use a classe `JobCollection` usando uma linguagem de programação da sua escolha, como o Visual Basic, o Visual C# ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82fb4-126">Use the `JobCollection` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="82fb4-127">Para obter mais informações, veja [SMO (SQL Server Management Objects)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="82fb4-127">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
