---
title: Assinatura, comandos não distribuídos (assinatura transacional, SQL Server 2005 e posterior) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.performance.f1
ms.assetid: 5451561e-0ce3-4bb5-844a-88cd15b0b371
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6bbd82b4f4855c99076404d8b621edca11a7e1e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680368"
---
# <a name="subscription-undistributed-commands-transactional-subscription-sql-server-2005-and-later"></a><span data-ttu-id="d520e-102">Assinatura, Comandos não Distribuídos (assinatura transacional, SQL Server 2005 e versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="d520e-102">Subscription, Undistributed Commands (Transactional Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="d520e-103">A guia **Comandos não Distribuídos** exibe informações sobre o número de comandos no banco de dados de distribuição que não foram entregues ao Assinante selecionado, e, o tempo estimado para entrega desses comandos.</span><span class="sxs-lookup"><span data-stu-id="d520e-103">The **Undistributed Commands** tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="d520e-104">Para obter informações sobre como exibir os comandos no banco de dados de distribuição, consulte [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d520e-104">For information about viewing the commands in the distribution database, see [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d520e-105">Opções</span><span class="sxs-lookup"><span data-stu-id="d520e-105">Options</span></span>  
 <span data-ttu-id="d520e-106">**Número de comandos no banco de dados de distribuição aguardando para serem aplicados a este Assinante**</span><span class="sxs-lookup"><span data-stu-id="d520e-106">**Number of commands in the distribution database waiting to be applied to this Subscriber**</span></span>  
 <span data-ttu-id="d520e-107">O número de comandos no banco de dados de distribuição que não foram entregues ao Assinante selecionado.</span><span class="sxs-lookup"><span data-stu-id="d520e-107">The number of commands in the distribution database that have not been delivered to the selected Subscriber.</span></span> <span data-ttu-id="d520e-108">Um comando consiste em uma instrução DML (linguagem de manipulação de dados) ou uma instrução DDL (linguagem de definição de dados) Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="d520e-108">A command consists of one Transact-SQL data manipulation language (DML) statement or one data definition language (DDL) statement.</span></span>  
  
 <span data-ttu-id="d520e-109">**Tempo estimado para aplicar esses comandos com base em desempenhos passados**</span><span class="sxs-lookup"><span data-stu-id="d520e-109">**Estimated time to apply these commands, based on past performance**</span></span>  
 <span data-ttu-id="d520e-110">A quantidade de tempo estimada para entrega de comandos ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="d520e-110">The estimated amount of time to deliver commands to the Subscriber.</span></span> <span data-ttu-id="d520e-111">Se esse valor for maior do que a quantidade de tempo requerida para gerar e aplicar um instantâneo ao Assinante, considere reiniciar o Assinante.</span><span class="sxs-lookup"><span data-stu-id="d520e-111">If this value is greater than the amount of time required to generate and apply a snapshot to the Subscriber, consider reinitializing the Subscriber.</span></span> <span data-ttu-id="d520e-112">Para obter mais informações, consulte [Reinicializar as assinaturas](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="d520e-112">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d520e-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d520e-113">See Also</span></span>  
 <span data-ttu-id="d520e-114">[Iniciar o Replication Monitor](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d520e-114">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="d520e-115">[Monitorar o desempenho com o Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d520e-115">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 [<span data-ttu-id="d520e-116">Monitorando a Replicação</span><span class="sxs-lookup"><span data-stu-id="d520e-116">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
