---
title: Tarefa Transferir Trabalhos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.f1
helpviewer_keywords:
- Transfer Jobs task [Integration Services]
ms.assetid: 1bf33885-9c5b-47e4-a549-f5920b66a1de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d692934d5f7c8c1449b123ee8b9caf1d8bb34744
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568722"
---
# <a name="transfer-jobs-task"></a><span data-ttu-id="5151d-102">Tarefa Transferir Trabalhos</span><span class="sxs-lookup"><span data-stu-id="5151d-102">Transfer Jobs Task</span></span>
  <span data-ttu-id="5151d-103">A tarefa Transferir Trabalhos transfere um ou mais trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent entre instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5151d-103">The Transfer Jobs task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5151d-104">A tarefa Transferir Trabalhos pode ser configurada para transferir todos os trabalhos ou só os trabalhos especificados.</span><span class="sxs-lookup"><span data-stu-id="5151d-104">The Transfer Jobs task can be configured to transfer all jobs, or only specified jobs.</span></span> <span data-ttu-id="5151d-105">Você também pode indicar se os trabalhos transferidos são habilitados no destino.</span><span class="sxs-lookup"><span data-stu-id="5151d-105">You can also indicate whether the transferred jobs are enabled at the destination.</span></span>  
  
 <span data-ttu-id="5151d-106">Os trabalhos a ser transferidos já podem existir no destino.</span><span class="sxs-lookup"><span data-stu-id="5151d-106">The jobs to be transferred may already exist on the destination.</span></span> <span data-ttu-id="5151d-107">A tarefa Transferir Trabalhos pode ser configurada para manipular os trabalhos existentes dos modos a seguir:</span><span class="sxs-lookup"><span data-stu-id="5151d-107">The Transfer Jobs task can be configured to handle existing jobs in the following ways:</span></span>  
  
-   <span data-ttu-id="5151d-108">Substituir os trabalhos existentes.</span><span class="sxs-lookup"><span data-stu-id="5151d-108">Overwrite existing jobs.</span></span>  
  
-   <span data-ttu-id="5151d-109">Interromper a tarefa quando houver trabalhos duplicados.</span><span class="sxs-lookup"><span data-stu-id="5151d-109">Fail the task when duplicate jobs exist.</span></span>  
  
-   <span data-ttu-id="5151d-110">Ignorar trabalhos duplicados.</span><span class="sxs-lookup"><span data-stu-id="5151d-110">Skip duplicate jobs.</span></span>  
  
 <span data-ttu-id="5151d-111">No tempo de execução, a tarefa Transferir Trabalhos conecta-se aos servidores de origem e de destino usando um ou dois gerenciadores de conexões SMO.</span><span class="sxs-lookup"><span data-stu-id="5151d-111">At run time, the Transfer Jobs task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="5151d-112">O gerenciador de conexões SMO é configurado separadamente da tarefa Transferir Trabalhos e depois é referenciado na tarefa Transferir Trabalhos.</span><span class="sxs-lookup"><span data-stu-id="5151d-112">The SMO connection manager is configured separately from the Transfer Jobs task, and then is referenced in the Transfer Jobs task.</span></span> <span data-ttu-id="5151d-113">O gerenciador de conexões SMO especifica o servidor e o modo de autenticação a ser usado ao acessar o servidor.</span><span class="sxs-lookup"><span data-stu-id="5151d-113">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="5151d-114">Para obter mais informações, consulte [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5151d-114">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-jobs-between-instances-of-sql-server"></a><span data-ttu-id="5151d-115">Transferindo trabalhos entre instâncias do SQL Server</span><span class="sxs-lookup"><span data-stu-id="5151d-115">Transferring Jobs Between Instances of SQL Server</span></span>  
 <span data-ttu-id="5151d-116">A tarefa Transferir Trabalhos dá suporte a uma origem e a um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5151d-116">The Transfer Jobs task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="5151d-117">Não há nenhuma restrição quanto à versão a ser usada como origem ou destino.</span><span class="sxs-lookup"><span data-stu-id="5151d-117">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="5151d-118">Eventos</span><span class="sxs-lookup"><span data-stu-id="5151d-118">Events</span></span>  
 <span data-ttu-id="5151d-119">A tarefa Transferir Trabalhos gera um evento de informação com o número de trabalhos transferidos e um evento de aviso quando um trabalho é substituído.</span><span class="sxs-lookup"><span data-stu-id="5151d-119">The Transfer Jobs task raises an information event that reports the number of jobs transferred and a warning event when a job is overwritten.</span></span> <span data-ttu-id="5151d-120">A tarefa não informa o progresso incremental da transferência de trabalhos; informa só 0% e 100% concluídos.</span><span class="sxs-lookup"><span data-stu-id="5151d-120">The task does not report incremental progress of the job transfer; it reports only 0% and 100% completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="5151d-121">Valor de execução</span><span class="sxs-lookup"><span data-stu-id="5151d-121">Execution Value</span></span>  
 <span data-ttu-id="5151d-122">O valor de execução, definido na propriedade `ExecutionValue` da tarefa retorna o número de trabalhos que são transferidos.</span><span class="sxs-lookup"><span data-stu-id="5151d-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of jobs that are transferred.</span></span> <span data-ttu-id="5151d-123">Ao atribuir uma variável definida pelo usuário à propriedade `ExecValueVariable` da tarefa Transferir Trabalhos, informações sobre a transferência de trabalhos podem se tornar disponíveis a outros objetos no pacote.</span><span class="sxs-lookup"><span data-stu-id="5151d-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Jobs task, information about the job transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="5151d-124">Para obter mais informações, consulte [Variáveis do Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) e [Usar variáveis em pacotes](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="5151d-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="5151d-125">Entradas de log</span><span class="sxs-lookup"><span data-stu-id="5151d-125">Log Entries</span></span>  
 <span data-ttu-id="5151d-126">A tarefa Transferir Trabalhos inclui as seguintes entradas de log personalizadas:</span><span class="sxs-lookup"><span data-stu-id="5151d-126">The Transfer Jobs task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="5151d-127">TransferJobsTaskStarTransferringObjects   Essa entrada de log informa que a transferência foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="5151d-127">TransferJobsTaskStarTransferringObjects   This log entry reports that the transfer has started.</span></span> <span data-ttu-id="5151d-128">A entrada do log contém a hora de início.</span><span class="sxs-lookup"><span data-stu-id="5151d-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="5151d-129">TransferJobsTaskFinishedTransferringObjects    Essa entrada de log informa que a transferência foi concluída.</span><span class="sxs-lookup"><span data-stu-id="5151d-129">TransferJobsTaskFinishedTransferringObjects    This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="5151d-130">A entrada do log contém a hora de término.</span><span class="sxs-lookup"><span data-stu-id="5151d-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="5151d-131">Além disso, uma entrada de log para o evento `OnInformation` informa o número de trabalhos que foram transferidos e uma entrada de log para o evento `OnWarning` é gravada para cada trabalho no destino que for substituído.</span><span class="sxs-lookup"><span data-stu-id="5151d-131">In addition, a log entry for the `OnInformation` event reports the number of jobs that were transferred and a log entry for the `OnWarning` event is written for each job on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="5151d-132">Segurança e permissões</span><span class="sxs-lookup"><span data-stu-id="5151d-132">Security and Permissions</span></span>  
 <span data-ttu-id="5151d-133">Para transferir trabalhos, o usuário deve ser membro da função de servidor fixa sysadmin ou de uma das funções de banco de dados fixas Agent do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no banco de dados msdb em ambas as instâncias de origem e de destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5151d-133">To transfer jobs, the user must be a member of the sysadmin fixed server role or one of the fixed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles on the msdb database on the both the source and destination instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="configuration-of-the-transfer-jobs-task"></a><span data-ttu-id="5151d-134">Configuração da tarefa Transferir Trabalhos</span><span class="sxs-lookup"><span data-stu-id="5151d-134">Configuration of the Transfer Jobs Task</span></span>  
 <span data-ttu-id="5151d-135">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="5151d-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="5151d-136">Para obter informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="5151d-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="5151d-137">Editor da Tarefa Transferir Trabalhos &#40;Página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="5151d-137">Transfer Jobs Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="5151d-138">Editor da Tarefa Transferir Trabalhos &#40;página Trabalhos&#41;</span><span class="sxs-lookup"><span data-stu-id="5151d-138">Transfer Jobs Task Editor &#40;Jobs Page&#41;</span></span>](../transfer-jobs-task-editor-jobs-page.md)  
  
-   [<span data-ttu-id="5151d-139">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="5151d-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="5151d-140">Para obter informações sobre como definir essas propriedades programaticamente, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="5151d-140">For information about programmatically setting these properties, click the of the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferJobsTask.TransferJobsTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="5151d-141">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="5151d-141">Related Tasks</span></span>  
 <span data-ttu-id="5151d-142">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="5151d-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="5151d-143">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="5151d-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="5151d-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5151d-144">See Also</span></span>  
 <span data-ttu-id="5151d-145">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="5151d-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="5151d-146">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="5151d-146">Control Flow</span></span>](control-flow.md)  
  
  
