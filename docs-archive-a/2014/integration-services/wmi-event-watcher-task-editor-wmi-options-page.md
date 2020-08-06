---
title: Editor da tarefa detector de eventos do WMI (página Opções do WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatcher.wmiquery.f1
helpviewer_keywords:
- WMI Event Watcher Task Editor
ms.assetid: 525f3de7-a021-4e52-9939-3a83c88f131a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d7d95501f6442df3723261c970c7a90f48cbdc87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681740"
---
# <a name="wmi-event-watcher-task-editor-wmi-options-page"></a><span data-ttu-id="960d3-102">Editor do Detector de Eventos do WMI (página Opções do WMI)</span><span class="sxs-lookup"><span data-stu-id="960d3-102">WMI Event Watcher Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="960d3-103">Use a página **Opções do WMI** da caixa de diálogo **Editor do Detector de Eventos do WMI** para especificar a origem da consulta WQL (Instrumentação de Gerenciamento do Windows Query Language) e como a tarefa do Detector de Eventos do WMI responde aos eventos do WMI (Microsoft Windows Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="960d3-103">Use the **WMI Options** page of the **WMI Event Watcher Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and how the WMI Event Watcher task responds to Microsoft Windows Instrumentation (WMI) events.</span></span>  
  
 <span data-ttu-id="960d3-104">Para obter informações sobre essa tarefa, consulte [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span><span class="sxs-lookup"><span data-stu-id="960d3-104">To learn about this task, see [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span></span> <span data-ttu-id="960d3-105">Para obter mais informações sobre a linguagem WQL, consulte o tópico Instrumentação de Gerenciamento do Windows, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045)(Consultando com WQL), na Biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="960d3-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="960d3-106">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="960d3-106">Static Options</span></span>  
 <span data-ttu-id="960d3-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="960d3-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="960d3-108">Selecione um gerenciador de conexões WMI na lista ou clique em \<**New WMI Connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="960d3-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="960d3-109">**Tópicos relacionados:** [Gerenciador de Conexões WMI](connection-manager/wmi-connection-manager.md), [Editor do Gerenciador de Conexões WMI](../../2014/integration-services/wmi-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="960d3-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="960d3-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="960d3-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="960d3-111">Selecione o tipo de origem da consulta WQL que a tarefa executa.</span><span class="sxs-lookup"><span data-stu-id="960d3-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="960d3-112">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="960d3-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="960d3-113">Valor</span><span class="sxs-lookup"><span data-stu-id="960d3-113">Value</span></span>|<span data-ttu-id="960d3-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="960d3-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="960d3-115">**Entrada Direta**</span><span class="sxs-lookup"><span data-stu-id="960d3-115">**Direct input**</span></span>|<span data-ttu-id="960d3-116">Defina a origem de consultas WQL.</span><span class="sxs-lookup"><span data-stu-id="960d3-116">Set the source to a WQL query.</span></span> <span data-ttu-id="960d3-117">Selecionar este valor faz com que seja exibida a opção dinâmica **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="960d3-117">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="960d3-118">**Conexão do Arquivo**</span><span class="sxs-lookup"><span data-stu-id="960d3-118">**File connection**</span></span>|<span data-ttu-id="960d3-119">Selecione um arquivo que contém a consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="960d3-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="960d3-120">Selecionar este valor faz com que seja exibida a opção dinâmica **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="960d3-120">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="960d3-121">**Variável**</span><span class="sxs-lookup"><span data-stu-id="960d3-121">**Variable**</span></span>|<span data-ttu-id="960d3-122">Define a origem de uma variável que define a consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="960d3-122">Set the source to a variable that defines WQL query.</span></span> <span data-ttu-id="960d3-123">Selecionar este valor faz com que seja exibida a opção dinâmica **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="960d3-123">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
  
 <span data-ttu-id="960d3-124">**ActionAtEvent**</span><span class="sxs-lookup"><span data-stu-id="960d3-124">**ActionAtEvent**</span></span>  
 <span data-ttu-id="960d3-125">Especifique se o evento WMI efetua logon do evento e inicia uma ação do [!INCLUDE[ssIS](../includes/ssis-md.md)] ou só efetua logon do evento.</span><span class="sxs-lookup"><span data-stu-id="960d3-125">Specify whether the WMI event logs the event and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] action, or only logs the event.</span></span>  
  
 <span data-ttu-id="960d3-126">**AfterEvent**</span><span class="sxs-lookup"><span data-stu-id="960d3-126">**AfterEvent**</span></span>  
 <span data-ttu-id="960d3-127">Especifique se a tarefa é bem-sucedida ou falha depois que recebe o evento WMI ou se a tarefa continua observando se o evento ocorre novamente.</span><span class="sxs-lookup"><span data-stu-id="960d3-127">Specify whether the task succeeds or fails after it receives the WMI event, or if the task continues watching for the event to occur again.</span></span>  
  
 <span data-ttu-id="960d3-128">**ActionAtTimeout**</span><span class="sxs-lookup"><span data-stu-id="960d3-128">**ActionAtTimeout**</span></span>  
 <span data-ttu-id="960d3-129">Especifique se a tarefa registra o tempo limite excedido da consulta WMI e inicia um evento [!INCLUDE[ssIS](../includes/ssis-md.md)] em resposta ou só registra o tempo limite excedido.</span><span class="sxs-lookup"><span data-stu-id="960d3-129">Specify whether the task logs a WMI query time-out and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] event in response, or only logs the time-out.</span></span>  
  
 <span data-ttu-id="960d3-130">**AfterTimeout**</span><span class="sxs-lookup"><span data-stu-id="960d3-130">**AfterTimeout**</span></span>  
 <span data-ttu-id="960d3-131">Especifique se a tarefa é bem-sucedida ou falha em resposta ao tempo limite excedido ou se a tarefa continua observando se o tempo limite é excedido novamente.</span><span class="sxs-lookup"><span data-stu-id="960d3-131">Specify whether the task succeeds or fails in response to a time-out, or if the task continues watching for another time-out to recur.</span></span>  
  
 <span data-ttu-id="960d3-132">**NumberOfEvents**</span><span class="sxs-lookup"><span data-stu-id="960d3-132">**NumberOfEvents**</span></span>  
 <span data-ttu-id="960d3-133">Especifique o número de eventos a serem observados.</span><span class="sxs-lookup"><span data-stu-id="960d3-133">Specify the number of events to watch for.</span></span>  
  
 <span data-ttu-id="960d3-134">**Tempo Limite**</span><span class="sxs-lookup"><span data-stu-id="960d3-134">**Timeout**</span></span>  
 <span data-ttu-id="960d3-135">Especifique o número de segundos a esperar para que o evento ocorra.</span><span class="sxs-lookup"><span data-stu-id="960d3-135">Specify the number of seconds to wait for the event to occur.</span></span> <span data-ttu-id="960d3-136">Um valor de 0 significa que nenhum tempo limite está em efeito.</span><span class="sxs-lookup"><span data-stu-id="960d3-136">A value of 0 means that no time-out is in effect.</span></span>  
  
## <a name="wqlquerysource-dynamic-options"></a><span data-ttu-id="960d3-137">Opções dinâmicas do WQLQuerySource</span><span class="sxs-lookup"><span data-stu-id="960d3-137">WQLQuerySource Dynamic Options</span></span>  
  
### <a name="wqlquerysource--direct-input"></a><span data-ttu-id="960d3-138">WQLQuerySource = Entrada direta</span><span class="sxs-lookup"><span data-stu-id="960d3-138">WQLQuerySource = Direct input</span></span>  
 <span data-ttu-id="960d3-139">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="960d3-139">**WQLQuerySource**</span></span>  
 <span data-ttu-id="960d3-140">Forneça uma consulta ou clique no botão de reticências (...) e digite uma consulta usando a caixa de diálogo **Consulta WQL**.</span><span class="sxs-lookup"><span data-stu-id="960d3-140">Provide a query, or click the ellipsis button (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysource--file-connection"></a><span data-ttu-id="960d3-141">WQLQuerySource = Conexão do arquivo</span><span class="sxs-lookup"><span data-stu-id="960d3-141">WQLQuerySource = File connection</span></span>  
 <span data-ttu-id="960d3-142">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="960d3-142">**WQLQuerySource**</span></span>  
 <span data-ttu-id="960d3-143">Selecione um gerenciador de conexões de Arquivos na lista ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="960d3-143">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="960d3-144">**Tópicos relacionados:** [Gerenciador de conexões de arquivos](connection-manager/file-connection-manager.md), [Editor do Gerenciador de conexões de Arquivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="960d3-144">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysource--variable"></a><span data-ttu-id="960d3-145">WQLQuerySource = Variável</span><span class="sxs-lookup"><span data-stu-id="960d3-145">WQLQuerySource = Variable</span></span>  
 <span data-ttu-id="960d3-146">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="960d3-146">**WQLQuerySource**</span></span>  
 <span data-ttu-id="960d3-147">Selecione uma variável na lista ou clique em \<**New variable...**> para criar uma variável.</span><span class="sxs-lookup"><span data-stu-id="960d3-147">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="960d3-148">**Tópicos relacionados:** [Variáveis do Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Adicionar variável](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="960d3-148">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="960d3-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="960d3-149">See Also</span></span>  
 <span data-ttu-id="960d3-150">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="960d3-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="960d3-151">[Editor da tarefa Inspetor de eventos do WMI &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="960d3-151">[WMI Event Watcher Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="960d3-152">[Página Expressões](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="960d3-152">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="960d3-153">Tarefa Leitor de Dados do WMI</span><span class="sxs-lookup"><span data-stu-id="960d3-153">WMI Data Reader Task</span></span>](control-flow/wmi-data-reader-task.md)  
  
  
