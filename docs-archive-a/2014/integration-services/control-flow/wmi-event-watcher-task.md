---
title: Tarefa Detector de Eventos do WMI | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatchertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Event Watcher task [Integration Services]
ms.assetid: b5bb52e9-a77e-41e1-93f9-d4c3bc6b2c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: be20624e5ccdf665e6274f647c342498e9c0f0a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685223"
---
# <a name="wmi-event-watcher-task"></a><span data-ttu-id="f58bc-102">Tarefa Detector de Eventos do WMI</span><span class="sxs-lookup"><span data-stu-id="f58bc-102">WMI Event Watcher Task</span></span>
  <span data-ttu-id="f58bc-103">A tarefa Detector de Eventos do WMI detecta um evento de Instrumentação de Gerenciamento do Windows (WMI) por meio de uma consulta de evento WQL (Management Instrumentation Query Language, Linguagem de Consulta de Instrumentação de Gerenciamento) para especificar eventos de interesse.</span><span class="sxs-lookup"><span data-stu-id="f58bc-103">The WMI Event Watcher task watches for a Windows Management Instrumentation (WMI) event using a Management Instrumentation Query Language (WQL) event query to specify events of interest.</span></span> <span data-ttu-id="f58bc-104">É possível utilizar a tarefa Detector de Eventos do WMI para as seguintes finalidades:</span><span class="sxs-lookup"><span data-stu-id="f58bc-104">You can use the WMI Event Watcher task for the following purposes:</span></span>  
  
-   <span data-ttu-id="f58bc-105">Aguardar notificação de que foram adicionados arquivos a uma pasta e depois iniciar o processamento do arquivo.</span><span class="sxs-lookup"><span data-stu-id="f58bc-105">Wait for notification that files have been added to a folder and then initiate the processing of the file.</span></span>  
  
-   <span data-ttu-id="f58bc-106">Executar um pacote que exclui arquivos quando a memória disponível em um servidor elimina o que for inferior a um percentual especificado.</span><span class="sxs-lookup"><span data-stu-id="f58bc-106">Run a package that deletes files when the available memory on a server drops lower than a specified percentage.</span></span>  
  
-   <span data-ttu-id="f58bc-107">Detectar a instalação de um aplicativo e então executar um pacote que usa o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f58bc-107">Watch for installation of an application, and then run a package that uses the application.</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="f58bc-108">inclui uma tarefa que lê informações WMI.</span><span class="sxs-lookup"><span data-stu-id="f58bc-108">includes a task that reads WMI information.</span></span>  
  
 <span data-ttu-id="f58bc-109">Para obter mais informações sobre essa tarefa, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="f58bc-109">For more information about this task, click the following topic:</span></span>  
  
-   [<span data-ttu-id="f58bc-110">Tarefa Leitor de Dados do WMI</span><span class="sxs-lookup"><span data-stu-id="f58bc-110">WMI Data Reader Task</span></span>](wmi-data-reader-task.md)  
  
## <a name="wql-queries"></a><span data-ttu-id="f58bc-111">Consultas WQL</span><span class="sxs-lookup"><span data-stu-id="f58bc-111">WQL Queries</span></span>  
 <span data-ttu-id="f58bc-112">WQL é um dialeto do SQL com extensões para dar suporte à notificação de eventos de WMI e outros recursos específicos ao WMI.</span><span class="sxs-lookup"><span data-stu-id="f58bc-112">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="f58bc-113">Para obter mais informações sobre WQL, consulte a documentação da Instrumentação de Gerenciamento do Windows na [Biblioteca do MSDN](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="f58bc-113">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f58bc-114">As classes WMI variam entre versões de Windows.</span><span class="sxs-lookup"><span data-stu-id="f58bc-114">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="f58bc-115">A consulta seguinte detecta notificação de que o uso da CPU é superior a 40 por cento.</span><span class="sxs-lookup"><span data-stu-id="f58bc-115">The following query watches for notification that the CPU use is more than 40 percent.</span></span>  
  
```  
SELECT * from __InstanceModificationEvent WITHIN 2 WHERE TargetInstance ISA 'Win32_Processor' and TargetInstance.LoadPercentage > 40  
```  
  
 <span data-ttu-id="f58bc-116">A consulta seguinte detecta notificação de que um arquivo foi adicionado a uma pasta.</span><span class="sxs-lookup"><span data-stu-id="f58bc-116">The following query watches for notification that a file has been added to a folder.</span></span>  
  
```  
SELECT * FROM __InstanceCreationEvent WITHIN 10 WHERE TargetInstance ISA "CIM_DirectoryContainsFile" and TargetInstance.GroupComponent= "Win32_Directory.Name=\"c:\\\\WMIFileWatcher\""   
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-event-watcher-task"></a><span data-ttu-id="f58bc-117">Mensagens de registro personalizadas disponíveis na tarefa Detector de Eventos do WMI</span><span class="sxs-lookup"><span data-stu-id="f58bc-117">Custom Logging Messages Available on the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="f58bc-118">A tabela a seguir relaciona as entradas de registro personalizadas da tarefa Detector de Eventos do WMI.</span><span class="sxs-lookup"><span data-stu-id="f58bc-118">The following table lists the custom log entries for the WMI Event Watcher task.</span></span> <span data-ttu-id="f58bc-119">Para obter mais informações, consulte [Log do SSIS &#40;Integration Services&#41;](../performance/integration-services-ssis-logging.md) e [Mensagens personalizadas para log](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="f58bc-119">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="f58bc-120">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="f58bc-120">Log entry</span></span>|<span data-ttu-id="f58bc-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="f58bc-121">Description</span></span>|  
|---------------|-----------------|  
|`WMIEventWatcherEventOccurred`|<span data-ttu-id="f58bc-122">Indica que ocorreu um evento que a tarefa estava monitorando.</span><span class="sxs-lookup"><span data-stu-id="f58bc-122">Indicates that an event occurred that the task was monitoring.</span></span>|  
|`WMIEventWatcherTimedout`|<span data-ttu-id="f58bc-123">Indica que o tempo limite da tarefa foi esgotado.</span><span class="sxs-lookup"><span data-stu-id="f58bc-123">Indicates that the task timed out.</span></span>|  
|`WMIEventWatcherWatchingForWMIEvents`|<span data-ttu-id="f58bc-124">Indica que a tarefa começou a executar a consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="f58bc-124">Indicates that the task began to execute the WQL query.</span></span> <span data-ttu-id="f58bc-125">A entrada inclui a consulta.</span><span class="sxs-lookup"><span data-stu-id="f58bc-125">The entry includes the query.</span></span>|  
  
## <a name="configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="f58bc-126">Configuração da tarefa Detector de Eventos do WMI</span><span class="sxs-lookup"><span data-stu-id="f58bc-126">Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="f58bc-127">Você pode configurar a tarefa Leitura de Dados do WMI das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="f58bc-127">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="f58bc-128">Especifique o gerenciador de conexões WMI a ser usado.</span><span class="sxs-lookup"><span data-stu-id="f58bc-128">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="f58bc-129">Especifique a fonte da consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="f58bc-129">Specify the source of the WQL query.</span></span> <span data-ttu-id="f58bc-130">A fonte pode ser armazenada fora da tarefa, em uma variável ou um arquivo, ou a consulta pode ser armazenada em uma propriedade de tarefa.</span><span class="sxs-lookup"><span data-stu-id="f58bc-130">The source can be external to the task, a variable or a file, or the query can be stored in a task property.</span></span>  
  
-   <span data-ttu-id="f58bc-131">Especificar a ação que a tarefa adotará quando o evento WMI ocorrer.</span><span class="sxs-lookup"><span data-stu-id="f58bc-131">Specify the action that the task takes when the WMI event occurs.</span></span> <span data-ttu-id="f58bc-132">Você pode registrar a notificação de eventos e o status após o evento ou levantar eventos personalizados do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que fornecem informações associadas ao evento WMI, à notificação e ao status após o evento.</span><span class="sxs-lookup"><span data-stu-id="f58bc-132">You can log the event notification and the status after the event, or raise custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] events that provide information associated with the WMI event, the notification, and the status after the event.</span></span>  
  
-   <span data-ttu-id="f58bc-133">Definir como a tarefa responde ao evento.</span><span class="sxs-lookup"><span data-stu-id="f58bc-133">Define how the task responds to the event.</span></span> <span data-ttu-id="f58bc-134">A tarefa pode ser configurada para ter êxito ou falhar, dependendo do evento, ou a tarefa pode apenas detectar o evento novamente.</span><span class="sxs-lookup"><span data-stu-id="f58bc-134">The task can be configured to succeed or fail, depending on the event, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="f58bc-135">Especificar a ação que a tarefa adotará quando a consulta WMI expirar. Você pode registrar a expiração e o status após a expiração ou levantar um evento personalizado do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , indicando que o evento WMI expirou e registrando a expiração e o status da expiração.</span><span class="sxs-lookup"><span data-stu-id="f58bc-135">Specify the action the task takes when the WMI query times out. You can log the time-out and the status after time-out, or raise a custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] event, indicating that the WMI event timed out and logging the time-out and time-out status.</span></span>  
  
-   <span data-ttu-id="f58bc-136">Definir como a tarefa responde à expiração. A tarefa pode ser configurada para ter êxito ou falhar, ou a tarefa pode apenas detectar o evento novamente.</span><span class="sxs-lookup"><span data-stu-id="f58bc-136">Define how the task responds to the time-out. The task can be configured to succeed or fail, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="f58bc-137">Especificar o número de vezes que a tarefa detecta o evento.</span><span class="sxs-lookup"><span data-stu-id="f58bc-137">Specify the number of times the task watches for the event.</span></span>  
  
-   <span data-ttu-id="f58bc-138">Especificar o limite de tempo.</span><span class="sxs-lookup"><span data-stu-id="f58bc-138">Specify the time-out.</span></span>  
  
 <span data-ttu-id="f58bc-139">Se a origem for um arquivo, a tarefa Detector de Eventos do WMI usará um gerenciador de conexões de Arquivo para se conectar ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="f58bc-139">If the source is a file, the WMI Event Watcher task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="f58bc-140">Para obter mais informações, consulte [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f58bc-140">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="f58bc-141">A tarefa Detector de Eventos do WMI usa um gerenciador de conexões WMI para se conectar ao servidor do qual lê informações de WMI.</span><span class="sxs-lookup"><span data-stu-id="f58bc-141">The WMI Event Watcher task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="f58bc-142">Para obter mais informações, consulte [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f58bc-142">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
 <span data-ttu-id="f58bc-143">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="f58bc-143">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="f58bc-144">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f58bc-144">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f58bc-145">Editor da Tarefa Detector de Eventos do WMI &#40;Página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="f58bc-145">WMI Event Watcher Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="f58bc-146">Editor do Detector de Eventos do WMI &#40;Página Opções do WMI&#41;</span><span class="sxs-lookup"><span data-stu-id="f58bc-146">WMI Event Watcher Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-event-watcher-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="f58bc-147">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="f58bc-147">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="f58bc-148">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="f58bc-148">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="f58bc-149">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="f58bc-149">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="f58bc-150">Configuração programática da tarefa Detector de Eventos do WMI</span><span class="sxs-lookup"><span data-stu-id="f58bc-150">Programmatic Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="f58bc-151">Para obter mais informações sobre como definir essas propriedades programaticamente, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="f58bc-151">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiEventWatcherTask.WmiEventWatcherTask>  
  
  
