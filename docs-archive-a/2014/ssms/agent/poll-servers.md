---
title: Sondar servidores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- target servers [SQL Server], polling interval
- polling master servers [SQL Server]
- server polling [SQL Server]
- master servers [SQL Server], polling
- polling interval [SQL Server]
ms.assetid: 96f5fd43-3edd-4418-9dd0-4d34e618890e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6370e53083d2cf818e8c8b09752d49e092755a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575540"
---
# <a name="poll-servers"></a><span data-ttu-id="1724a-102">Sondar servidores</span><span class="sxs-lookup"><span data-stu-id="1724a-102">Poll Servers</span></span>
  <span data-ttu-id="1724a-103">Quando é implementada administração multisservidor, os servidores de destino contatam periodicamente o servidor mestre para carregar informações sobre trabalhos executados e baixar novos trabalhos.</span><span class="sxs-lookup"><span data-stu-id="1724a-103">When multiserver administration is implemented, target servers periodically contact the master server to upload information on jobs that have been executed, and download new jobs.</span></span> <span data-ttu-id="1724a-104">O processo de contatar o servidor mestre é chamado de *sondagem de servidor* , que acontece em *intervalos de sondagem*regulares.</span><span class="sxs-lookup"><span data-stu-id="1724a-104">The process of contacting the master server is called *server polling,* which takes place at regular *polling intervals.*</span></span>  
  
## <a name="polling-intervals"></a><span data-ttu-id="1724a-105">Intervalos de sondagem</span><span class="sxs-lookup"><span data-stu-id="1724a-105">Polling Intervals</span></span>  
 <span data-ttu-id="1724a-106">O intervalo de sondagem (um minuto, por padrão) controla a frequência com que o servidor de destino se conecta ao servidor mestre para baixar instruções e carregar os resultados da execução de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="1724a-106">The polling interval (one minute by default) controls how frequently the target server connects to the master server to download instructions and upload the results of job execution.</span></span>  
  
 <span data-ttu-id="1724a-107">Quando um servidor de destino sonda o servidor mestre, ele lê as operações atribuídas a si na tabela **sysdownloadlist** do banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="1724a-107">When a target server polls the master server, it reads the operations assigned to the target server from the **sysdownloadlist** table in the **msdb** database.</span></span> <span data-ttu-id="1724a-108">Essas operações controlam trabalhos multisservidor e diversos aspectos do comportamento de um servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="1724a-108">These operations control multiserver jobs and various aspects of the behavior of a target server.</span></span> <span data-ttu-id="1724a-109">São exemplos dessas operações a exclusão, inserção ou início de um trabalho e a atualização do intervalo de sondagem de um servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="1724a-109">Examples of operations include deleting a job, inserting a job, starting a job, and updating the polling interval of a target server.</span></span>  
  
 <span data-ttu-id="1724a-110">As operações são postadas na tabela **sysdownloadlist** , de um destes modos:</span><span class="sxs-lookup"><span data-stu-id="1724a-110">Operations are posted to the **sysdownloadlist** table in either of the following ways:</span></span>  
  
-   <span data-ttu-id="1724a-111">Explicitamente, usando o procedimento armazenado **sp_post_msx_operation** .</span><span class="sxs-lookup"><span data-stu-id="1724a-111">Explicitly by using the **sp_post_msx_operation** stored procedure.</span></span>  
  
-   <span data-ttu-id="1724a-112">Implicitamente, usando outros procedimentos armazenados de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1724a-112">Implicitly by using other job stored procedures.</span></span>  
  
 <span data-ttu-id="1724a-113">Se usar procedimentos armazenados de trabalho para modificar agendas ou etapas de trabalho multisservidor ou se usar o SQL Distributed Management Objects (SQL-DMO) para controlar trabalhos multisservidor, emita o seguinte comando após efetuar as modificações nas agendas ou etapas de trabalho:</span><span class="sxs-lookup"><span data-stu-id="1724a-113">If you use job stored procedures to modify multiserver job schedules or job steps, or SQL Distributed Management Objects (SQL-DMO) to control multiserver jobs, issue the following command after modifying a multiserver job's steps or schedules:</span></span>  
  
```  
EXECUTE msdb.dbo.sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="1724a-114">Emitir este comando mantém os servidores de destino sincronizados com a definição de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="1724a-114">Issue this command keeps the target servers synchronized with the current job definition.</span></span>  
  
 <span data-ttu-id="1724a-115">Você não terá que postar operações explicitamente se usar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1724a-115">You do not have to post operations explicitly if you use the following:</span></span>  
  
-   <span data-ttu-id="1724a-116">O Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , para controlar trabalhos multisservidor.</span><span class="sxs-lookup"><span data-stu-id="1724a-116">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to control multiserver jobs.</span></span>  
  
-   <span data-ttu-id="1724a-117">Procedimentos armazenados de trabalho que não modificam agendas nem etapas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1724a-117">Job stored procedures that do not modify job schedules or job steps.</span></span>  
  
 <span data-ttu-id="1724a-118">**Para forçar um servidor de destino a sondar o servidor mestre**</span><span class="sxs-lookup"><span data-stu-id="1724a-118">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="1724a-119">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1724a-119">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="1724a-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1724a-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="1724a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1724a-121">See Also</span></span>  
 [<span data-ttu-id="1724a-122">Gerenciar eventos</span><span class="sxs-lookup"><span data-stu-id="1724a-122">Manage Events</span></span>](manage-events.md)  
  
  
