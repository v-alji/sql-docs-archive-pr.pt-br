---
title: Exibir atividade do trabalho | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- viewing job activity
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- displaying job activity
ms.assetid: 5c284e5e-7775-435d-ac49-f3f12a27ddc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 56b159952c83ed243c4c5d8012c76e5a2a248519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685418"
---
# <a name="view-job-activity"></a><span data-ttu-id="11869-102">Exibir Atividade do Trabalho</span><span class="sxs-lookup"><span data-stu-id="11869-102">View Job Activity</span></span>
  <span data-ttu-id="11869-103">Este tópico descreve como exibir o estado de runtime de trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11869-103">This topic describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="11869-104">Quando o serviço do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é iniciado, é criada uma sessão e a tabela **sysjobactivity** no banco de dados **msdb** é preenchida com todas as tarefas definidas existentes.</span><span class="sxs-lookup"><span data-stu-id="11869-104">When the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service starts, a new session is created and the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="11869-105">Essa tabela registra atividade e status do trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="11869-105">This table records current job activity and status.</span></span> <span data-ttu-id="11869-106">Você pode usar o Monitor de Atividade do Trabalho no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para exibir o estado atual dos trabalhos.</span><span class="sxs-lookup"><span data-stu-id="11869-106">You can use the Job Activity Monitor in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to view the current state of jobs.</span></span> <span data-ttu-id="11869-107">Se o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent for concluído inesperadamente, pode-se recorrer à tabela **sysjobactivity** para consultar quais trabalhos estavam sendo executados quando o serviço foi finalizado.</span><span class="sxs-lookup"><span data-stu-id="11869-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service unexpectedly terminates, you can refer to the **sysjobactivity** table to see which jobs were being executed when the service terminated.</span></span>  
  
 <span data-ttu-id="11869-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="11869-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="11869-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="11869-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="11869-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="11869-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="11869-111">**Para exibir a atividade do trabalho usando:**</span><span class="sxs-lookup"><span data-stu-id="11869-111">**To view job activity, using:**</span></span>  
  
     [<span data-ttu-id="11869-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="11869-112">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="11869-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="11869-113">Transact-SQL</span></span>](#TSQL)  
  
## <a name="before-you-begin"></a><span data-ttu-id="11869-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="11869-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="11869-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="11869-115">Security</span></span>  
 <span data-ttu-id="11869-116">Para obter informações detalhadas, consulte [Implementar a segurança do SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="11869-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="11869-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="11869-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="11869-118">Para exibir atividade do trabalho</span><span class="sxs-lookup"><span data-stu-id="11869-118">To view job activity</span></span>  
  
1.  <span data-ttu-id="11869-119">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="11869-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="11869-120">Expanda o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="11869-120">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="11869-121">Clique com o botão direito em **Monitor de atividade do trabalho** e clique em **Exibir atividade do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="11869-121">Right-click **Job Activity Monitor** and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="11869-122">Em **Monitor de Atividade do Trabalho**, é possível exibir detalhes sobre cada trabalho que está definido para esse servidor.</span><span class="sxs-lookup"><span data-stu-id="11869-122">In the **Job Activity Monitor**, you can view details about each job that is defined for this server.</span></span>  
  
5.  <span data-ttu-id="11869-123">Clique com o botão direito do mouse em um trabalho para que ele seja iniciado, interrompido, habilitado ou desabilitado; tenha seu status atualizado conforme exibido no Monitor de Atividade do Trabalho; seja excluído, ou para que seu histórico ou propriedades sejam exibidos.</span><span class="sxs-lookup"><span data-stu-id="11869-123">Right-click a job to start it, stop it, enable or disable it, refresh its status as displayed in the Job Activity Monitor, delete it, or view its history or properties.</span></span>  <span data-ttu-id="11869-124">Para iniciar, interromper, habilitar ou desabilitar ou atualizar vários trabalhos, selecione várias linhas, no Monitor de Atividade do Trabalho, e clique com o botão direito do mouse para fazer sua seleção.</span><span class="sxs-lookup"><span data-stu-id="11869-124">To start, stop, enable or disable, or refresh multiple jobs, select multiple rows in the Job Activity Monitor, and right-click your selection.</span></span>  
  
6.  <span data-ttu-id="11869-125">Para atualizar o Monitor de Atividade do Trabalho, clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="11869-125">To update the Job Activity Monitor, click **Refresh**.</span></span> <span data-ttu-id="11869-126">Para exibir menos linhas, clique em **Filtrar** e digite parâmetros de filtro.</span><span class="sxs-lookup"><span data-stu-id="11869-126">To view fewer rows, click **Filter** and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="11869-127">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="11869-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="11869-128">Para exibir atividade do trabalho</span><span class="sxs-lookup"><span data-stu-id="11869-128">To view job activity</span></span>  
  
1.  <span data-ttu-id="11869-129">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11869-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="11869-130">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="11869-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="11869-131">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="11869-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- lists activity for all jobs that the current user has permission to view.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobactivity ;  
    GO  
    ```  
  
 <span data-ttu-id="11869-132">Para obter mais informações, consulte [sp_help_jobactivity &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="11869-132">For more information, see [sp_help_jobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span></span>  
  
  
