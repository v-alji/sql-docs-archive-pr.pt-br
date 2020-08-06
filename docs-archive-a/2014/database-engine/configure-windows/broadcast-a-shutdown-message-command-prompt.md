---
title: Difundir uma mensagem de desligamento (prompt de comando) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server, stopping
- named instances [SQL Server], broadcasting shutdown messages
- shutdown message broadcast
- broadcasting shutdown message
- command prompt [SQL Server], broadcasting shutdown messages
- default instances [SQL Server], broadcasting shutdown messages
- stopping SQL Server
ms.assetid: 9f20ccd5-d952-431d-ba12-339911af9430
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 540baada4a78d7b5caf54cbabb9196ce5a79780e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681180"
---
# <a name="broadcast-a-shutdown-message-command-prompt"></a><span data-ttu-id="73c37-102">Difundir uma mensagem de desligamento (prompt de comando)</span><span class="sxs-lookup"><span data-stu-id="73c37-102">Broadcast a Shutdown Message (Command Prompt)</span></span>
  <span data-ttu-id="73c37-103">Este tópico descreve como difundir uma mensagem de desligamento no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o comando **net send** .</span><span class="sxs-lookup"><span data-stu-id="73c37-103">This topic describes how to broadcast a shutdown message in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using the **net send** command.</span></span> <span data-ttu-id="73c37-104">Na mensagem, inclua a hora em que a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será interrompida de forma que os usuários possam terminar suas tarefas.</span><span class="sxs-lookup"><span data-stu-id="73c37-104">In the message, include the time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be stopped so that users can finish their tasks.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-broadcast-a-shutdown-message"></a><span data-ttu-id="73c37-105">Para difundir uma mensagem de desligamento</span><span class="sxs-lookup"><span data-stu-id="73c37-105">To broadcast a shutdown message</span></span>  
  
1.  <span data-ttu-id="73c37-106">Em um prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="73c37-106">From a command prompt, enter:</span></span>  
  
     <span data-ttu-id="73c37-107">**net send /users "mensagem"**</span><span class="sxs-lookup"><span data-stu-id="73c37-107">**net send /users "message"**</span></span>  
  
     <span data-ttu-id="73c37-108">A opção **/users** especifica que a mensagem será enviada a todos os usuários conectados no servidor</span><span class="sxs-lookup"><span data-stu-id="73c37-108">The **/users** option specifies that the message be sent to all users connected to the server</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73c37-109">O comando **net send** exige que o serviço de mensagens seja executado nos computadores de envio e de recebimento.</span><span class="sxs-lookup"><span data-stu-id="73c37-109">The **net send** command requires the messenger service to be running on both the sending and the receiving computers.</span></span> <span data-ttu-id="73c37-110">O serviço de mensagens é desabilitado por padrão no Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="73c37-110">The messenger service is disabled by default on Windows Server 2003.</span></span> <span data-ttu-id="73c37-111">Para obter informações sobre o **net send**, consulte a documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="73c37-111">For information about **net send**, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="73c37-112">Em sua rede, pode ser mais apropriado contatar os usuários por e-mail ou telefone.</span><span class="sxs-lookup"><span data-stu-id="73c37-112">On your network, it may be more appropriate to contact users by e-mail or the telephone.</span></span> <span data-ttu-id="73c37-113">Para determinar quais usuários estão conectados atualmente ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use o Monitor de Atividade.</span><span class="sxs-lookup"><span data-stu-id="73c37-113">To determine which users are currently connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the Activity Monitor.</span></span> <span data-ttu-id="73c37-114">Para obter informações sobre o Monitor de Atividade, veja [Monitor de Atividade](../../relational-databases/performance-monitor/activity-monitor.md) e [Abrir o Monitor de Atividade &#40;SQL Server Management Studio&#41;](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="73c37-114">For information on the Activity Monitor, see [Activity Monitor](../../relational-databases/performance-monitor/activity-monitor.md) and [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../../relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c37-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="73c37-115">See Also</span></span>  
 [<span data-ttu-id="73c37-116">Iniciar, parar, pausar, retomar, reiniciar o mecanismo de banco de dados, o SQL Server Agent ou o serviço SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="73c37-116">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)  
  
  
