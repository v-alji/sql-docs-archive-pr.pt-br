---
title: Gerenciar Eventos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- event-triggered jobs [SQL Server]
- forwarding events [SQL Server]
- alerts [SQL Server], forwarded events
- alerts [SQL Server], management servers
- SQL Server Agent alerts, management servers
ms.assetid: 8f4ee7f5-80df-49fd-b2b8-d020e04b6e1b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ca6d56440b06d285cbb90f8d92325d59a452c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678565"
---
# <a name="manage-events"></a><span data-ttu-id="5827b-102">Gerenciar eventos</span><span class="sxs-lookup"><span data-stu-id="5827b-102">Manage Events</span></span>
  <span data-ttu-id="5827b-103">É possível encaminhar a um instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] todas as mensagens de evento que atendam ou excedam um nível de severidade de erro específico.</span><span class="sxs-lookup"><span data-stu-id="5827b-103">You can forward to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all event messages that meet or exceed a specific error severity level.</span></span> <span data-ttu-id="5827b-104">A isso chamamos *encaminhamento de evento*.</span><span class="sxs-lookup"><span data-stu-id="5827b-104">This is called *event forwarding*.</span></span> <span data-ttu-id="5827b-105">O servidor de encaminhamento é um servidor dedicado que também pode ser um servidor mestre.</span><span class="sxs-lookup"><span data-stu-id="5827b-105">The forwarding server is a dedicated server that can also be a master server.</span></span> <span data-ttu-id="5827b-106">Você pode usar o encaminhamento de eventos para centralizar o gerenciamento de alertas para um grupo de servidores, reduzindo, assim, a carga de trabalho em servidores de intensa utilização.</span><span class="sxs-lookup"><span data-stu-id="5827b-106">You can use event forwarding to centralize alert management for a group of servers, thereby reducing the workload on heavily used servers.</span></span>  
  
 <span data-ttu-id="5827b-107">Quando um servidor recebe eventos para um grupo de outros servidores, esse servidor é chamado de *servidor de gerenciamento de alertas*.</span><span class="sxs-lookup"><span data-stu-id="5827b-107">When one server receives events for a group of other servers, the server that receives events is called an *alerts management server*.</span></span> <span data-ttu-id="5827b-108">Em um ambiente multisservidor, o servidor mestre é designado como servidor de gerenciamento de alertas.</span><span class="sxs-lookup"><span data-stu-id="5827b-108">In a multiserver environment, you designate the master server as the alerts management server.</span></span>  
  
## <a name="advantages-of-using-an-alerts-management-server"></a><span data-ttu-id="5827b-109">Vantagens de usar um servidor de gerenciamento de alertas</span><span class="sxs-lookup"><span data-stu-id="5827b-109">Advantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="5827b-110">São vantagens de se configurar um servidor de gerenciamento de alertas:</span><span class="sxs-lookup"><span data-stu-id="5827b-110">The advantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="5827b-111">**Centralização**.</span><span class="sxs-lookup"><span data-stu-id="5827b-111">**Centralization**.</span></span> <span data-ttu-id="5827b-112">Controle centralizado e exibição consolidada dos eventos de várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são possíveis a partir de um único servidor.</span><span class="sxs-lookup"><span data-stu-id="5827b-112">Centralized control and a consolidated view of the events of several instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are possible from a single server.</span></span>  
  
-   <span data-ttu-id="5827b-113">**Escalabilidade**.</span><span class="sxs-lookup"><span data-stu-id="5827b-113">**Scalability**.</span></span> <span data-ttu-id="5827b-114">Vários servidores físicos podem ser administrados como um mesmo servidor lógico.</span><span class="sxs-lookup"><span data-stu-id="5827b-114">Many physical servers can be administered as one logical server.</span></span> <span data-ttu-id="5827b-115">É possível adicionar ou remover servidores desse grupo de servidores físicos, conforme a necessidade.</span><span class="sxs-lookup"><span data-stu-id="5827b-115">You can add or remove servers to this physical server group as needed.</span></span>  
  
-   <span data-ttu-id="5827b-116">**Eficiência**.</span><span class="sxs-lookup"><span data-stu-id="5827b-116">**Efficiency**.</span></span> <span data-ttu-id="5827b-117">O tempo de configuração é reduzido, porque alertas e operadores precisam ser definidos apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="5827b-117">Configuration time is reduced, because you need to define alerts and operators only once.</span></span>  
  
## <a name="disadvantages-of-using-an-alerts-management-server"></a><span data-ttu-id="5827b-118">Desvantagens de usar um servidor de gerenciamento de alertas</span><span class="sxs-lookup"><span data-stu-id="5827b-118">Disadvantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="5827b-119">São desvantagens de se configurar um servidor de gerenciamento de alertas:</span><span class="sxs-lookup"><span data-stu-id="5827b-119">The disadvantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="5827b-120">**Aumento do tráfego**.</span><span class="sxs-lookup"><span data-stu-id="5827b-120">**Increased traffic**.</span></span> <span data-ttu-id="5827b-121">Encaminhar eventos a um servidor de gerenciamento de alertas pode aumentar o tráfego da rede.</span><span class="sxs-lookup"><span data-stu-id="5827b-121">Forwarding events to an alerts management server can increase network traffic.</span></span> <span data-ttu-id="5827b-122">Esse aumento pode ser moderado pela restrição do encaminhamento a eventos que estejam acima de um nível de severidade designado.</span><span class="sxs-lookup"><span data-stu-id="5827b-122">This increase can be moderated by restricting event forwarding to events that are above a designated severity level.</span></span>  
  
-   <span data-ttu-id="5827b-123">**Ponto de falha único**.</span><span class="sxs-lookup"><span data-stu-id="5827b-123">**Single point of failure**.</span></span> <span data-ttu-id="5827b-124">Se o servidor de gerenciamento de alertas ficar offline, nenhum alerta será emitido para qualquer evento no grupo gerenciado de servidores.</span><span class="sxs-lookup"><span data-stu-id="5827b-124">If the alerts management server goes offline, no alerts are issued for any event on the managed group of servers.</span></span>  
  
-   <span data-ttu-id="5827b-125">**Carga do servidor**.</span><span class="sxs-lookup"><span data-stu-id="5827b-125">**Server load**.</span></span> <span data-ttu-id="5827b-126">A manipulação de alertas para os eventos encaminhados provocam um aumento na carga de processamento no servidor de gerenciamento de alertas.</span><span class="sxs-lookup"><span data-stu-id="5827b-126">Handling alerts for the forwarded events causes an increased processing load on the alerts management server.</span></span>  
  
## <a name="guidelines-for-using-an-alerts-management-server"></a><span data-ttu-id="5827b-127">Diretrizes para usar um servidor de gerenciamento de alertas</span><span class="sxs-lookup"><span data-stu-id="5827b-127">Guidelines for Using an Alerts Management Server</span></span>  
 <span data-ttu-id="5827b-128">Ao configurar um servidor de gerenciamento de alertas, siga estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="5827b-128">When configuring an alerts management server, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="5827b-129">Para receber eventos encaminhados, o servidor de gerenciamento de alertas deve ser uma instância padrão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5827b-129">In order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="5827b-130">Evite executar aplicativos críticos ou intensamente utilizados no servidor de gerenciamento de alertas.</span><span class="sxs-lookup"><span data-stu-id="5827b-130">Avoid running critical or heavily used applications on the alerts management server.</span></span>  
  
-   <span data-ttu-id="5827b-131">Planeje cuidadosamente o tráfego de rede envolvido na configuração de muitos servidores compartilhando o mesmo servidor de gerenciamento de alertas.</span><span class="sxs-lookup"><span data-stu-id="5827b-131">Carefully plan for the network traffic involved in configuring many servers to share the same alerts management server.</span></span> <span data-ttu-id="5827b-132">Se houver congestionamento, reduza o número de servidores que usam o servidor de gerenciamento de alertas em questão.</span><span class="sxs-lookup"><span data-stu-id="5827b-132">If congestion results, reduce the number of servers that use a particular alerts management server.</span></span>  
  
     <span data-ttu-id="5827b-133">Os servidores registrados no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] constituem a lista de servidores disponíveis para eleição como servidor de encaminhamento de alerta.</span><span class="sxs-lookup"><span data-stu-id="5827b-133">The servers that are registered within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] constitute the list of servers available to be chosen by that server as the alerts-forwarding server.</span></span>  
  
-   <span data-ttu-id="5827b-134">Defina alertas na instância local do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que requeira uma resposta específica a servidor, em vez de encaminhar os alertas ao servidor de gerenciamento de alertas.</span><span class="sxs-lookup"><span data-stu-id="5827b-134">Define alerts on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that require a server-specific response, instead of forwarding the alerts to the alerts management server.</span></span>  
  
     <span data-ttu-id="5827b-135">O servidor de gerenciamento de alertas exibe todos os servidores do quais recebe encaminhamentos como um todo lógico.</span><span class="sxs-lookup"><span data-stu-id="5827b-135">The alerts management server views all the servers forwarding to it as a logical whole.</span></span> <span data-ttu-id="5827b-136">Por exemplo, um servidor de gerenciamento de alertas responde do mesmo modo a um evento 605 tanto de um servidor A, quanto de um servidor B.</span><span class="sxs-lookup"><span data-stu-id="5827b-136">For example, an alerts management server responds in the same way to a 605 event from server A and a 605 event from server B.</span></span>  
  
-   <span data-ttu-id="5827b-137">Configurado o seu sistema de alertas, verifique periodicamente o log de aplicativos do Microsoft Windows quanto a eventos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="5827b-137">After configuring your alert system, periodically check the Microsoft Windows application log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events.</span></span>  
  
     <span data-ttu-id="5827b-138">As condições de falha encontradas pelo mecanismo de alerta são gravadas no log de aplicativos do Windows local, com nome de origem "SQL Server Agent."</span><span class="sxs-lookup"><span data-stu-id="5827b-138">Failure conditions encountered by the alerts engine are written to the local Windows application log with a source name of "SQL Server Agent."</span></span> <span data-ttu-id="5827b-139">Por exemplo, se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent não puder enviar uma notificação por email, conforme está definido, será registrado um evento no log de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5827b-139">For example, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent cannot send an e-mail notification as it has been defined, an event is logged in the application log.</span></span>  
  
 <span data-ttu-id="5827b-140">Se um alerta definido localmente estiver inativo e ocorrer um evento que o dispararia, este será encaminhado ao servidor de gerenciamento de alertas (caso satisfaça a condição de encaminhamento de alerta).</span><span class="sxs-lookup"><span data-stu-id="5827b-140">If a locally defined alert is inactivated, and an event occurs that would have caused the alert to fire, the event is forwarded to the alerts management server (if it satisfies the alert-forwarding condition).</span></span> <span data-ttu-id="5827b-141">Esse encaminhamento permite a desativação e a ativação de substituições locais (alertas definidos localmente que também estão definidos no servidor de gerenciamento de alertas), conforme a necessidade, pelo usuário no site local.</span><span class="sxs-lookup"><span data-stu-id="5827b-141">This forwarding allows local overrides (alerts defined locally that are also defined on the alerts management server) to be turned off and on as needed by the user at the local site.</span></span> <span data-ttu-id="5827b-142">Você também pode solicitar que os eventos sempre sejam encaminhados, mesmo quando eles também são manipulados por alertas locais.</span><span class="sxs-lookup"><span data-stu-id="5827b-142">You can also request that events always be forwarded, even if they are also handled by local alerts.</span></span>  
  
 <span data-ttu-id="5827b-143">A seguir, encontram-se tarefas comuns do gerenciamento de eventos em um ambiente multisservidor:</span><span class="sxs-lookup"><span data-stu-id="5827b-143">The following are common tasks for managing events in a multiserver environment:</span></span>  
  
 <span data-ttu-id="5827b-144">**Para designar um servidor de gerenciamento de alertas**</span><span class="sxs-lookup"><span data-stu-id="5827b-144">**To designate an alerts management server**</span></span>  
  
-   [<span data-ttu-id="5827b-145">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5827b-145">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
 <span data-ttu-id="5827b-146">**Para definir uma resposta a um alerta**</span><span class="sxs-lookup"><span data-stu-id="5827b-146">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="5827b-147">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5827b-147">SQL Server Management Studio</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="5827b-148">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5827b-148">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
## <a name="running-event-triggered-jobs"></a><span data-ttu-id="5827b-149">Executando trabalhos acionados por eventos</span><span class="sxs-lookup"><span data-stu-id="5827b-149">Running Event-Triggered Jobs</span></span>  
 <span data-ttu-id="5827b-150">Você pode definir que um trabalho seja executado em resposta a um alerta.</span><span class="sxs-lookup"><span data-stu-id="5827b-150">You can define a job to be executed in response to an alert.</span></span> <span data-ttu-id="5827b-151">Por exemplo, é possível executar um trabalho que corrija ou aprofunde o diagnóstico de um problema detectado pelo alerta.</span><span class="sxs-lookup"><span data-stu-id="5827b-151">For example, you can execute a job that corrects or further diagnoses a problem detected by the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5827b-152">Uma vez que um trabalho pode emitir um evento, tenha cuidado para não criar um loop recursivo alerta-trabalho.</span><span class="sxs-lookup"><span data-stu-id="5827b-152">Because a job can raise an event, be careful not to create a recursive alert-job loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5827b-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5827b-153">See Also</span></span>  
 [<span data-ttu-id="5827b-154">sys.sysmensagens &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5827b-154">sys.sysmessages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysmessages-transact-sql)  
  
  
