---
title: Gerenciar trabalhos em toda a empresa | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver job management [SQL Server]
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
- target servers [SQL Server], job changes
ms.assetid: 4fe7f6c6-f89b-4430-979c-4994a5dcf7a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 385435302b2e987c86afb17eaebf90e91bc93e56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572353"
---
# <a name="manage-jobs-across-an-enterprise"></a><span data-ttu-id="7b621-102">Gerenciar trabalhos em toda a empresa</span><span class="sxs-lookup"><span data-stu-id="7b621-102">Manage Jobs Across an Enterprise</span></span>
  <span data-ttu-id="7b621-103">Se você fizer alterações nas definições de trabalho multisservidor fora do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , deverá postar as alterações na lista de download para que os servidores de destino possam baixar o trabalho atualizado novamente.</span><span class="sxs-lookup"><span data-stu-id="7b621-103">If you make changes to multiserver job definitions outside [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must post the changes to the download list so that target servers can download the updated job again.</span></span> <span data-ttu-id="7b621-104">Para garantir que os servidores de destino possuam as definições de trabalho atuais, poste uma instrução INSERT após atualizar o trabalho multisservidor, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7b621-104">To ensure that target servers have current job definitions, post an INSERT instruction after you update the multiserver job, as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="7b621-105">Para notificar servidores de destino de que um trabalho multisservidor foi modificado, é necessário invocar o comando precedente, depois de usar um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7b621-105">To notify target servers that a multiserver job has been modified, you must invoke the preceding command after using any of the following procedures:</span></span>  
  
-   [<span data-ttu-id="7b621-106">sp_add_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7b621-106">sp_add_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="7b621-107">sp_update_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7b621-107">sp_update_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql)  
  
-   [<span data-ttu-id="7b621-108">sp_delete_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7b621-108">sp_delete_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql)  
  
-   [<span data-ttu-id="7b621-109">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7b621-109">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="7b621-110">&#41;&#40;Transact-SQL de sp_detach_schedule</span><span class="sxs-lookup"><span data-stu-id="7b621-110">sp_detach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-schedule-transact-sql)  
  
    > [!NOTE]  
    >  <span data-ttu-id="7b621-111">Não é necessário chamar **sp_post_msx_operation** depois de chamar **sp_update_job** ou **sp_delete_job**, pois esses procedimentos armazenados postam as alterações requeridas na lista de downloads automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7b621-111">It is not necessary to call **sp_post_msx_operation** after you call **sp_update_job** or **sp_delete_job**, because these stored procedures post the required changes to the download list automatically.</span></span>  
  
 <span data-ttu-id="7b621-112">As seguintes tarefas são comuns no gerenciamento de trabalhos em toda a empresa:</span><span class="sxs-lookup"><span data-stu-id="7b621-112">The following are common tasks for managing jobs across an enterprise:</span></span>  
  
 <span data-ttu-id="7b621-113">**Para verificar o status de um servidor de destino**</span><span class="sxs-lookup"><span data-stu-id="7b621-113">**To check the status of a target server**</span></span>  
  
-   [<span data-ttu-id="7b621-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b621-114">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-targetserver-transact-sql)  
  
-   [<span data-ttu-id="7b621-115">SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="7b621-115">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="7b621-116">**Para alterar os servidores de destino quanto a um trabalho**</span><span class="sxs-lookup"><span data-stu-id="7b621-116">**To change the target servers for a job**</span></span>  
  
-   [<span data-ttu-id="7b621-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b621-117">SQL Server Management Studio</span></span>](modify-the-target-servers-for-a-job.md)  
  
-   [<span data-ttu-id="7b621-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b621-118">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
-   [<span data-ttu-id="7b621-119">SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="7b621-119">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="7b621-120">**Para alterar o local de um servidor de destino**</span><span class="sxs-lookup"><span data-stu-id="7b621-120">**To change the location of a target server**</span></span>  
  
-   [<span data-ttu-id="7b621-121">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b621-121">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="7b621-122">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b621-122">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)  
  
-   [<span data-ttu-id="7b621-123">SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="7b621-123">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="7b621-124">**Para sincronizar os relógios dos servidores de destino**</span><span class="sxs-lookup"><span data-stu-id="7b621-124">**To synchronize target server clocks**</span></span>  
  
-   [<span data-ttu-id="7b621-125">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b621-125">SQL Server Management Studio</span></span>](synchronize-target-server-clocks-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="7b621-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b621-126">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql)  
  
 <span data-ttu-id="7b621-127">**Para forçar um servidor de destino a sondar o servidor mestre**</span><span class="sxs-lookup"><span data-stu-id="7b621-127">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="7b621-128">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b621-128">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="7b621-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b621-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="7b621-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7b621-130">See Also</span></span>  
 [<span data-ttu-id="7b621-131">Gerenciar eventos</span><span class="sxs-lookup"><span data-stu-id="7b621-131">Manage Events</span></span>](manage-events.md)  
  
  
