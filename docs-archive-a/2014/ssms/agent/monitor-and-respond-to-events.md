---
title: Monitorar e responder a eventos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- notifications [SQL Server], alert
- events [SQL Server], alerts
- alerts [SQL Server]
- notifications [SQL Server]
- events [SQL Server], automatically responding to
- administrator notifications [SQL Server Agent]
- automatic event responses
- SQL Server Agent alerts
- monitoring [SQL Server], events
- responding to events automatically
ms.assetid: f7fbe155-5b68-4777-bc71-a47637471f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: afdf1beffd6099fce84f03a8ba65f7de9abb8f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680280"
---
# <a name="monitor-and-respond-to-events"></a><span data-ttu-id="cea03-102">Monitorar e responder a eventos</span><span class="sxs-lookup"><span data-stu-id="cea03-102">Monitor and Respond to Events</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cea03-103">Agent pode monitorar e responder automaticamente a *eventos*, como mensagens do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], condições de desempenho específicas e eventos WMI (Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="cea03-103">Agent can monitor and automatically respond to *events*, such as messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], specific performance conditions, and Windows Management Instrumentation (WMI) events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cea03-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="cea03-104">In This Section</span></span>  
 [<span data-ttu-id="cea03-105">Alertas</span><span class="sxs-lookup"><span data-stu-id="cea03-105">Alerts</span></span>](alerts.md)  
 <span data-ttu-id="cea03-106">Contém informações sobre como nomear um alerta e selecionar os eventos ou as condições de desempenho às quais os alertas respondem.</span><span class="sxs-lookup"><span data-stu-id="cea03-106">Contains information about naming an alert and selecting the events or performance conditions to which alerts respond.</span></span>  
  
 [<span data-ttu-id="cea03-107">Criar um evento definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="cea03-107">Create a User-Defined Event</span></span>](create-a-user-defined-event.md)  
 <span data-ttu-id="cea03-108">Contém informações sobre como criar eventos diferentes daqueles predefinidos pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cea03-108">Contains information about how to create events other than those that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="cea03-109">Operadores</span><span class="sxs-lookup"><span data-stu-id="cea03-109">Operators</span></span>](operators.md)  
 <span data-ttu-id="cea03-110">Contém informações sobre como criar aliases para administradores que podem ser utilizados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para enviar notificações sobre a falha ou o êxito de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="cea03-110">Contains information about creating aliases for administrators that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can use to send notifications when jobs fail or succeed.</span></span>  
  
## <a name="about-monitoring-and-responding-to-events"></a><span data-ttu-id="cea03-111">Sobre monitoramento e resposta a eventos</span><span class="sxs-lookup"><span data-stu-id="cea03-111">About Monitoring and Responding to Events</span></span>  
 <span data-ttu-id="cea03-112">As respostas automatizadas a eventos são chamadas de *alertas*.</span><span class="sxs-lookup"><span data-stu-id="cea03-112">Automated responses to events are called *alerts*.</span></span> <span data-ttu-id="cea03-113">Você pode definir um alerta em um ou mais eventos, para especificar como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve responder mediante sua ocorrência.</span><span class="sxs-lookup"><span data-stu-id="cea03-113">You can define an alert on one or more events to specify how you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to their occurrence.</span></span> <span data-ttu-id="cea03-114">Um alerta pode responder a um evento notificando um administrador ou executando um trabalho, ou ambos.</span><span class="sxs-lookup"><span data-stu-id="cea03-114">An alert can respond to an event by notifying an administrator or running a job, or both.</span></span> <span data-ttu-id="cea03-115">Um alerta também pode encaminhar um evento para o log de aplicativos do Microsoft Windows em um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="cea03-115">An alert can also forward an event to the Microsoft Windows application log on a different computer.</span></span> <span data-ttu-id="cea03-116">Por exemplo, é possível especificar que um operador seja notificado imediatamente caso ocorra um evento de severidade 19.</span><span class="sxs-lookup"><span data-stu-id="cea03-116">For example, you can specify that an operator be notified immediately if an event of severity 19 occurs.</span></span> <span data-ttu-id="cea03-117">Definindo alertas, os administradores de banco de dados podem monitorar e gerenciar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]com mais eficácia.</span><span class="sxs-lookup"><span data-stu-id="cea03-117">By defining alerts, database administrators can more effectively monitor and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cea03-118">O Agent só responde a eventos para os quais está definido um alerta.</span><span class="sxs-lookup"><span data-stu-id="cea03-118">Agent only responds to events for which an alert is defined.</span></span> <span data-ttu-id="cea03-119">O método utilizado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para monitorar eventos depende do tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="cea03-119">The method that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uses to monitor events depends on the type of event.</span></span>  
  
 <span data-ttu-id="cea03-120">Quando um alerta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é definido para um contador de desempenho, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent monitora diretamente esse contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="cea03-120">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert is defined for a performance counter, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent directly monitors the performance counter.</span></span> <span data-ttu-id="cea03-121">No caso de um evento WMI, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registra uma consulta de evento para o evento WMI.</span><span class="sxs-lookup"><span data-stu-id="cea03-121">For a WMI event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registers an event query for the WMI event.</span></span>  
  
 <span data-ttu-id="cea03-122">Para responder a mensagens do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent monitora o log de aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="cea03-122">To respond to messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent monitors the Windows application log.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cea03-123">O Agent só pode responder a mensagens que aparecem nesse log.</span><span class="sxs-lookup"><span data-stu-id="cea03-123">Agent can only respond to messages that appear in this log.</span></span> <span data-ttu-id="cea03-124">Por padrão, o SQL Server registra as seguintes mensagens no log de aplicativos do Windows:</span><span class="sxs-lookup"><span data-stu-id="cea03-124">By default, SQL Server logs the following messages in the Windows application log:</span></span>  
  
-   <span data-ttu-id="cea03-125">Erros de sysmessages com severidade 19 ou superior.</span><span class="sxs-lookup"><span data-stu-id="cea03-125">Severity 19 or higher sysmessages errors.</span></span>  
  
     <span data-ttu-id="cea03-126">Caso deseje registrar também erros de sysmessages específicos de severidade menor que 19, use o procedimento armazenado sp_altermessage para designar tais erros como "always logged" (registrar sempre).</span><span class="sxs-lookup"><span data-stu-id="cea03-126">If you also want to log specific sysmessages errors that have a severity lower than 19, use the sp_altermessage stored procedure to designate such errors as "always logged".</span></span>  
  
-   <span data-ttu-id="cea03-127">Qualquer instrução RAISERROR é invocada usando a sintaxe WITH LOG.</span><span class="sxs-lookup"><span data-stu-id="cea03-127">Any RAISERROR statement invoked by using the WITH LOG syntax.</span></span>  
  
     <span data-ttu-id="cea03-128">Usar RAISERROR WITH LOG é a maneira recomendada de fazer registros no log de aplicativos do Windows a partir de uma instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cea03-128">Using RAISERROR WITH LOG is the recommended way to write to the Windows application log from an instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="cea03-129">Qualquer evento de aplicativo que é registrado usando xp_logevent.</span><span class="sxs-lookup"><span data-stu-id="cea03-129">Any application event that is logged by using xp_logevent.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cea03-130">Registrar eventos de aplicativos consome espaço de log e pode fazer com que o log de aplicativos do Windows exceda seu tamanho máximo.</span><span class="sxs-lookup"><span data-stu-id="cea03-130">Logging application events consumes log space and can cause the Windows application log to exceed its maximum size.</span></span> <span data-ttu-id="cea03-131">Verifique que o tamanho máximo do log de aplicativos do Windows seja grande o suficiente para impedir perda de informações de eventos do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cea03-131">Make sure that the maximum Windows application log size is large enough to avoid loss of SQL Server event information.</span></span>  
  
 <span data-ttu-id="cea03-132">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registra uma mensagem, o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent compara a mensagem com os alertas definidos pelo administrador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cea03-132">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logs a message, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service compares the message against the alerts defined by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="cea03-133">Independentemente da origem do evento, o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent responde ao evento executando as tarefas especificadas no alerta correspondente.</span><span class="sxs-lookup"><span data-stu-id="cea03-133">Regardless of the source of the event, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service responds to the event by performing the tasks specified in the alert for the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cea03-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cea03-134">See Also</span></span>  
 [<span data-ttu-id="cea03-135">&#41;&#40;Transact-SQL de sp_altermessage</span><span class="sxs-lookup"><span data-stu-id="cea03-135">sp_altermessage &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
  
