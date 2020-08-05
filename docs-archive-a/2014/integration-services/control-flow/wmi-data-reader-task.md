---
title: Tarefa Leitor de Dados do WMI | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Data Reader task [Integration Services]
ms.assetid: dae57067-0275-4ac3-8f34-1b9d169f1112
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1d2f16a28e8b6c94c7275468dedb6d2dfec76d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570799"
---
# <a name="wmi-data-reader-task"></a><span data-ttu-id="56685-102">Tarefa Leitor de Dados do WMI</span><span class="sxs-lookup"><span data-stu-id="56685-102">WMI Data Reader Task</span></span>
  <span data-ttu-id="56685-103">A tarefa Leitor de Dados do WMI executa consultas por meio da linguagem de consulta WMI (Instrumentação de Gerenciamento do Windows) que retorna informações de WMI sobre um sistema de computador.</span><span class="sxs-lookup"><span data-stu-id="56685-103">The WMI Data Reader task runs queries using the Windows Management Instrumentation (WMI) Query Language that returns information from WMI about a computer system.</span></span> <span data-ttu-id="56685-104">Pode-se utilizar o Leitor de Dados WMI para as seguintes finalidades:</span><span class="sxs-lookup"><span data-stu-id="56685-104">You can use the WMI Data Reader task for the following purposes:</span></span>  
  
-   <span data-ttu-id="56685-105">Consultar os logs de eventos do Windows em um computador local ou remoto e gravar as informações em um arquivo ou variável.</span><span class="sxs-lookup"><span data-stu-id="56685-105">Query the Windows event logs on a local or remote computer and write the information to a file or variable.</span></span>  
  
-   <span data-ttu-id="56685-106">Obter informações sobre a presença, o estado ou as propriedades de componentes de hardware e, depois, usar essas informações para determinar se outras tarefas no fluxo de controle devem ser executadas.</span><span class="sxs-lookup"><span data-stu-id="56685-106">Obtain information about the presence, state, or properties of hardware components, and then use this information to determine whether other tasks in the control flow should run.</span></span>  
  
-   <span data-ttu-id="56685-107">Obter uma lista de aplicativos e determinar qual versão de cada aplicativo está instalada.</span><span class="sxs-lookup"><span data-stu-id="56685-107">Get a list of applications and determine what version of each application is installed.</span></span>  
  
 <span data-ttu-id="56685-108">Você pode configurar a tarefa Leitura de Dados do WMI das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="56685-108">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="56685-109">Especifique o gerenciador de conexões WMI a ser usado.</span><span class="sxs-lookup"><span data-stu-id="56685-109">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="56685-110">Especifique a fonte da consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="56685-110">Specify the source of the WQL query.</span></span> <span data-ttu-id="56685-111">A consulta pode ser armazenada em uma propriedade de tarefa, ou pode ser armazenada fora da tarefa, em uma variável ou um arquivo.</span><span class="sxs-lookup"><span data-stu-id="56685-111">The query can be stored in a task property, or the query can be stored outside the task, in a variable or a file.</span></span>  
  
-   <span data-ttu-id="56685-112">Defina o formato dos resultados da consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="56685-112">Define the format of the WQL query results.</span></span> <span data-ttu-id="56685-113">A tarefa oferece suporte a uma tabela, par de nome/valor de propriedade ou formato de valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="56685-113">The task supports a table, property name/value pair, or property value format.</span></span>  
  
-   <span data-ttu-id="56685-114">Espefique o destino da consulta.</span><span class="sxs-lookup"><span data-stu-id="56685-114">Specify the destination of the query.</span></span> <span data-ttu-id="56685-115">O destino pode ser um variável ou um arquivo.</span><span class="sxs-lookup"><span data-stu-id="56685-115">The destination can be a variable or a file.</span></span>  
  
-   <span data-ttu-id="56685-116">Indique se o destino de consulta é substituído, mantido ou acrescentado.</span><span class="sxs-lookup"><span data-stu-id="56685-116">Indicate whether the query destination is overwritten, kept, or appended.</span></span>  
  
 <span data-ttu-id="56685-117">Se a origem ou o destino for um arquivo, a tarefa Leitor de Dados do WMI usará um gerenciador de conexões de Arquivo para se conectar ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="56685-117">If the source or destination is a file, the WMI Data Reader task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="56685-118">Para obter mais informações, consulte [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="56685-118">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="56685-119">A tarefa Leitor de Dados do WMI usa um gerenciador de conexões WMI para se conectar ao servidor do qual lê informações de WMI.</span><span class="sxs-lookup"><span data-stu-id="56685-119">The WMI Data Reader task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="56685-120">Para obter mais informações, consulte [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="56685-120">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="wql-query"></a><span data-ttu-id="56685-121">Consulta WQL</span><span class="sxs-lookup"><span data-stu-id="56685-121">WQL Query</span></span>  
 <span data-ttu-id="56685-122">WQL é um dialeto do SQL com extensões para dar suporte à notificação de eventos de WMI e outros recursos específicos ao WMI.</span><span class="sxs-lookup"><span data-stu-id="56685-122">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="56685-123">Para obter mais informações sobre WQL, consulte a documentação da Instrumentação de Gerenciamento do Windows na [Biblioteca do MSDN](https://go.microsoft.com/fwlink/?linkid=7022).</span><span class="sxs-lookup"><span data-stu-id="56685-123">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=7022).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56685-124">As classes WMI variam entre versões de Windows.</span><span class="sxs-lookup"><span data-stu-id="56685-124">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="56685-125">A consulta WQL a seguir retorna entradas no evento de logs do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="56685-125">The following WQL query returns entries in the Application log event.</span></span>  
  
```  
SELECT * FROM Win32_NTLogEvent WHERE LogFile = 'Application' AND (SourceName='SQLISService' OR SourceName='SQLISPackage') AND TimeGenerated > '20050117'  
```  
  
 <span data-ttu-id="56685-126">A consulta WQL a seguir retorna informações lógicas de disco.</span><span class="sxs-lookup"><span data-stu-id="56685-126">The following WQL query returns logical disk information.</span></span>  
  
```  
SELECT FreeSpace, DeviceId, Size, SystemName, Description FROM Win32_LlogicalDisk  
```  
  
 <span data-ttu-id="56685-127">A consulta WQL a seguir retorna uma lista das atualizações QFE (Quick Fix Engineering) ao sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="56685-127">The following WQL query returns a list of the quick fix engineering (QFE) updates to the operating system.</span></span>  
  
```  
Select * FROM Win32_QuickFixEngineering  
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-data-reader-task"></a><span data-ttu-id="56685-128">Mensagens de log personalizadas disponíveis na tarefa Leitor de Dados do WMI</span><span class="sxs-lookup"><span data-stu-id="56685-128">Custom Logging Messages Available on the WMI Data Reader Task</span></span>  
 <span data-ttu-id="56685-129">A tabela a seguir relaciona as entradas de log personalizadas para a tarefa Leitor de Dados do WMI.</span><span class="sxs-lookup"><span data-stu-id="56685-129">The following table lists the custom log entries for the WMI Data Reader task.</span></span> <span data-ttu-id="56685-130">Para obter mais informações, consulte [Log do SSIS &#40;Integration Services&#41;](../performance/integration-services-ssis-logging.md) e [Mensagens personalizadas para log](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="56685-130">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="56685-131">Entrada de log</span><span class="sxs-lookup"><span data-stu-id="56685-131">Log entry</span></span>|<span data-ttu-id="56685-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="56685-132">Description</span></span>|  
|---------------|-----------------|  
|`WMIDataReaderGettingWMIData`|<span data-ttu-id="56685-133">Indica que a tarefa começou a ser ler os dados do WMI.</span><span class="sxs-lookup"><span data-stu-id="56685-133">Indicates that the task began to read WMI data.</span></span>|  
|`WMIDataReaderOperation`|<span data-ttu-id="56685-134">Informa a consulta WQL executada pela tarefa.</span><span class="sxs-lookup"><span data-stu-id="56685-134">Reports the WQL query that the task ran.</span></span>|  
  
## <a name="configuration-of-the-wmi-data-reader-task"></a><span data-ttu-id="56685-135">Configuração da tarefa Leitor de Dados do WMI</span><span class="sxs-lookup"><span data-stu-id="56685-135">Configuration of the WMI Data Reader Task</span></span>  
 <span data-ttu-id="56685-136">Você pode definir propriedades programaticamente ou por meio do Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56685-136">You can set properties programmatically or through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="56685-137">Para obter informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="56685-137">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="56685-138">Editor da Tarefa Leitor de Dados do WMI &#40;Página Opções do WMI&#41;</span><span class="sxs-lookup"><span data-stu-id="56685-138">WMI Data Reader Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-data-reader-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="56685-139">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="56685-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="56685-140">Para obter informações sobre como definir essas propriedades programaticamente, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="56685-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiDataReaderTask.WmiDataReaderTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="56685-141">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="56685-141">Related Tasks</span></span>  
 <span data-ttu-id="56685-142">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="56685-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="56685-143">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="56685-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="56685-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="56685-144">See Also</span></span>  
 <span data-ttu-id="56685-145">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="56685-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="56685-146">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="56685-146">Control Flow</span></span>](control-flow.md)  
  
  
