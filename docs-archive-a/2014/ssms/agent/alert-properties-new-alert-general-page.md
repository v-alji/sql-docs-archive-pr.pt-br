---
title: Propriedades do alerta – novo alerta (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.general.f1
ms.assetid: f5c11610-62e3-44df-9800-a5dc35be4a09
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471b0062ecc805e83020495e422f8914baec5f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683920"
---
# <a name="alert-properties-new-alert-general-page"></a><span data-ttu-id="b86e8-102">Propriedades do alerta – novo alerta (página Geral)</span><span class="sxs-lookup"><span data-stu-id="b86e8-102">Alert Properties-New Alert (General Page)</span></span>
  <span data-ttu-id="b86e8-103">Use esta página para exibir e modificar as propriedades gerais de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertas do Agent.</span><span class="sxs-lookup"><span data-stu-id="b86e8-103">Use this page to view and modify the general properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b86e8-104">Opções</span><span class="sxs-lookup"><span data-stu-id="b86e8-104">Options</span></span>  
 <span data-ttu-id="b86e8-105">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b86e8-105">**Name**</span></span>  
 <span data-ttu-id="b86e8-106">Altere o nome do alerta.</span><span class="sxs-lookup"><span data-stu-id="b86e8-106">Change the name of the alert.</span></span>  
  
 <span data-ttu-id="b86e8-107">**Habilitar**</span><span class="sxs-lookup"><span data-stu-id="b86e8-107">**Enable**</span></span>  
 <span data-ttu-id="b86e8-108">Habilite o alerta.</span><span class="sxs-lookup"><span data-stu-id="b86e8-108">Enable the alert.</span></span> <span data-ttu-id="b86e8-109">Quando o alerta não está habilitado, as ações especificadas no alerta não acontecem.</span><span class="sxs-lookup"><span data-stu-id="b86e8-109">When the alert is not enabled, the actions specified in the alert do not occur.</span></span>  
  
 <span data-ttu-id="b86e8-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b86e8-110">**Type**</span></span>  
 <span data-ttu-id="b86e8-111">Selecione o tipo de alerta:</span><span class="sxs-lookup"><span data-stu-id="b86e8-111">Select the type of alert:</span></span>  
  
-   <span data-ttu-id="b86e8-112">O**Alerta de evento do SQL Server** responde às mensagens no log de eventos do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="b86e8-112">**SQL Server event alert** responds to messages in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows event log.</span></span>  
  
-   <span data-ttu-id="b86e8-113">O**Alerta de condição de desempenho do SQL Server** responde a uma condição específica em um contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="b86e8-113">**SQL Server performance condition alert** responds to a specific condition in a performance counter.</span></span>  
  
-   <span data-ttu-id="b86e8-114">O**Alerta de evento do WMI** responde a um evento WMI (Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="b86e8-114">**WMI event alert** responds to a Windows Management Instrumentation (WMI) event.</span></span>  
  
## <a name="sql-server-event-alert-options"></a><span data-ttu-id="b86e8-115">Opções de alerta de evento do SQL Server</span><span class="sxs-lookup"><span data-stu-id="b86e8-115">SQL Server Event Alert Options</span></span>  
 <span data-ttu-id="b86e8-116">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="b86e8-116">**Database name**</span></span>  
 <span data-ttu-id="b86e8-117">Especifica um banco de dados para o evento ou **todos os bancos de dados** para responder a uma mensagem independentemente do banco de dados no qual o evento ocorrer.</span><span class="sxs-lookup"><span data-stu-id="b86e8-117">Specify a database for the event, or **all databases** to respond to a message regardless of the database where the event occurs.</span></span>  
  
 <span data-ttu-id="b86e8-118">**Número do erro**</span><span class="sxs-lookup"><span data-stu-id="b86e8-118">**Error number**</span></span>  
 <span data-ttu-id="b86e8-119">Especifique que este evento responda a um erro e o número do erro.</span><span class="sxs-lookup"><span data-stu-id="b86e8-119">Specify that this event responds to an error, and specify the error number.</span></span>  
  
 <span data-ttu-id="b86e8-120">**Gravidade**</span><span class="sxs-lookup"><span data-stu-id="b86e8-120">**Severity**</span></span>  
 <span data-ttu-id="b86e8-121">Especifique que este evento responda a qualquer mensagem com um nível de severidade específico e o nível de severidade.</span><span class="sxs-lookup"><span data-stu-id="b86e8-121">Specify that this event responds to any message with a specific severity level, and specify the severity level.</span></span>  
  
 <span data-ttu-id="b86e8-122">**Gerar alertas quando a mensagem contiver**</span><span class="sxs-lookup"><span data-stu-id="b86e8-122">**Raise alert when message contains**</span></span>  
 <span data-ttu-id="b86e8-123">Filtre os eventos por uma cadeia de caracteres específica.</span><span class="sxs-lookup"><span data-stu-id="b86e8-123">Filter events by a specific string.</span></span> <span data-ttu-id="b86e8-124">Quando esta opção é selecionada, o alerta só responde a eventos que contenham uma cadeia de caracteres específica.</span><span class="sxs-lookup"><span data-stu-id="b86e8-124">When this option is selected, the alert only responds to events that contain a specific string.</span></span>  
  
 <span data-ttu-id="b86e8-125">**Texto da mensagem**</span><span class="sxs-lookup"><span data-stu-id="b86e8-125">**Message text**</span></span>  
 <span data-ttu-id="b86e8-126">Especifique a cadeia de caracteres usada para filtrar eventos.</span><span class="sxs-lookup"><span data-stu-id="b86e8-126">Specify the string to use to filter events.</span></span>  
  
## <a name="sql-server-performance-condition-alerts"></a><span data-ttu-id="b86e8-127">Alertas de condição de desempenho do SQL Server</span><span class="sxs-lookup"><span data-stu-id="b86e8-127">SQL Server Performance Condition Alerts</span></span>  
 <span data-ttu-id="b86e8-128">**Objeto**</span><span class="sxs-lookup"><span data-stu-id="b86e8-128">**Object**</span></span>  
 <span data-ttu-id="b86e8-129">Especifique o objeto de desempenho a ser monitorado.</span><span class="sxs-lookup"><span data-stu-id="b86e8-129">Specify the performance object to monitor.</span></span>  
  
 <span data-ttu-id="b86e8-130">**Contador**</span><span class="sxs-lookup"><span data-stu-id="b86e8-130">**Counter**</span></span>  
 <span data-ttu-id="b86e8-131">Especifique o contador dentro do objeto de desempenho a ser monitorado.</span><span class="sxs-lookup"><span data-stu-id="b86e8-131">Specify the counter within the performance object to monitor.</span></span>  
  
 <span data-ttu-id="b86e8-132">**Instância**</span><span class="sxs-lookup"><span data-stu-id="b86e8-132">**Instance**</span></span>  
 <span data-ttu-id="b86e8-133">Especifique a instância do contador a ser monitorado.</span><span class="sxs-lookup"><span data-stu-id="b86e8-133">Specify the instance of the counter to monitor.</span></span>  
  
 <span data-ttu-id="b86e8-134">**Alertar se o contador**</span><span class="sxs-lookup"><span data-stu-id="b86e8-134">**Alert if counter**</span></span>  
 <span data-ttu-id="b86e8-135">Especifique o comportamento do contador ao qual o alerta responde.</span><span class="sxs-lookup"><span data-stu-id="b86e8-135">Specify the behavior of the counter that the alert responds to.</span></span> <span data-ttu-id="b86e8-136">Por exemplo, o alerta pode responder a uma condição em que o valor do contador de **Espaço livre em tempdb (KB)** cai abaixo de um determinado valor ou responder a uma condição em que as **Compilações de SQL/s** subam acima de um determinado valor.</span><span class="sxs-lookup"><span data-stu-id="b86e8-136">For example, you may want the alert to respond to a condition where the value of the **Free space in tempdb (KB)** counter falls below a certain value, or you may want the alert to respond to a condition where the **SQL Compilations/sec** rises above a certain value.</span></span>  
  
 <span data-ttu-id="b86e8-137">**Valor**</span><span class="sxs-lookup"><span data-stu-id="b86e8-137">**Value**</span></span>  
 <span data-ttu-id="b86e8-138">Especifique um valor para o contador.</span><span class="sxs-lookup"><span data-stu-id="b86e8-138">Specify a value for the counter.</span></span>  
  
## <a name="wmi-event-alert-options"></a><span data-ttu-id="b86e8-139">Opções de alerta de evento WMI</span><span class="sxs-lookup"><span data-stu-id="b86e8-139">WMI Event Alert Options</span></span>  
 <span data-ttu-id="b86e8-140">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="b86e8-140">**Namespace**</span></span>  
 <span data-ttu-id="b86e8-141">Especifique o namespace a ser usado para a instrução WQL (WMI Query Language).</span><span class="sxs-lookup"><span data-stu-id="b86e8-141">Specify the namespace to use for the WMI Query Language (WQL) statement.</span></span> <span data-ttu-id="b86e8-142">Só têm suporte os namespaces em computadores que executam o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="b86e8-142">Only namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
 <span data-ttu-id="b86e8-143">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="b86e8-143">**Query**</span></span>  
 <span data-ttu-id="b86e8-144">Especifique a instrução WQL que identifica o evento ao qual o alerta responde.</span><span class="sxs-lookup"><span data-stu-id="b86e8-144">Specify the WQL statement that identifies the event that the alert responds to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b86e8-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b86e8-145">See Also</span></span>  
 <span data-ttu-id="b86e8-146">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="b86e8-146">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="b86e8-147">[Usando o WQL com o provedor WMI para eventos de servidor](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span><span class="sxs-lookup"><span data-stu-id="b86e8-147">[Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span></span>  
 <span data-ttu-id="b86e8-148">[Criar um alerta usando um número de erro](create-an-alert-using-an-error-number.md) </span><span class="sxs-lookup"><span data-stu-id="b86e8-148">[Create an Alert Using an Error Number](create-an-alert-using-an-error-number.md) </span></span>  
 [<span data-ttu-id="b86e8-149">Create an Alert Using Severity Level</span><span class="sxs-lookup"><span data-stu-id="b86e8-149">Create an Alert Using Severity Level</span></span>](create-an-alert-using-severity-level.md)  
  
  
