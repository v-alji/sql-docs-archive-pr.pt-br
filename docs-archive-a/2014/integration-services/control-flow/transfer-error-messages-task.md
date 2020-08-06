---
title: Tarefa Transferir Mensagens de Erro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.f1
helpviewer_keywords:
- Transfer Error Messages task [Integration Services]
ms.assetid: da702289-035a-4d14-bd74-04461fbfee1b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952acc28a79fef7e7351c97400e05bc7ba5b9243
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568723"
---
# <a name="transfer-error-messages-task"></a><span data-ttu-id="17500-102">Tarefa Transferir Mensagens de Erro</span><span class="sxs-lookup"><span data-stu-id="17500-102">Transfer Error Messages Task</span></span>
  <span data-ttu-id="17500-103">A tarefa Transferir Mensagens de Erro transfere uma ou mais mensagens de erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] definidas pelo usuário entre instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17500-103">The Transfer Error Messages task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined error messages between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="17500-104">Mensagens definidas pelo usuário são mensagens com um identificador igual ou maior que 50000.</span><span class="sxs-lookup"><span data-stu-id="17500-104">User-defined messages are messages with an identifier that is equal to or greater than 50000.</span></span> <span data-ttu-id="17500-105">Mensagens com identificador menor que 50000 são mensagens de erro do sistema e não podem ser transferidas usando-se a tarefa Transferir Mensagens de Erro.</span><span class="sxs-lookup"><span data-stu-id="17500-105">Messages with an identifier less than 50000 are system error messages, and cannot be transferred by using the Transfer Error Messages task.</span></span>  
  
 <span data-ttu-id="17500-106">A tarefa Transferir Mensagens de Erro pode ser configurada para transferir todas as mensagens de erro ou só as mensagens de erro especificadas.</span><span class="sxs-lookup"><span data-stu-id="17500-106">The Transfer Error Messages task can be configured to transfer all error messages, or only the specified error messages.</span></span> <span data-ttu-id="17500-107">Mensagens de erro definidas pelo usuário podem estar disponíveis em vários idiomas diferentes e a tarefa pode ser configurada para só transferir mensagens em idiomas selecionados.</span><span class="sxs-lookup"><span data-stu-id="17500-107">User-defined error messages may be available in a number of different languages and the task can be configured to transfer only messages in selected languages.</span></span> <span data-ttu-id="17500-108">Uma versão us_english da mensagem, que usa a página de código 1033, deve estar no servidor de destino para que você possa transferir versões em outro idioma da mensagem para esse servidor.</span><span class="sxs-lookup"><span data-stu-id="17500-108">A us_english version of the message that uses code page 1033 must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
 <span data-ttu-id="17500-109">A tabela sysmessages no banco de dados mestre contém todas as mensagens de erro, tanto as de sistema como as definidas pelo usuário, que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa.</span><span class="sxs-lookup"><span data-stu-id="17500-109">The sysmessages table in the master database contains all the error messages-both system and user-defined-that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses.</span></span>  
  
 <span data-ttu-id="17500-110">As mensagens definidas pelo usuário a serem transferidas já podem existir no destino.</span><span class="sxs-lookup"><span data-stu-id="17500-110">The user-defined messages to be transferred may already exist on the destination.</span></span> <span data-ttu-id="17500-111">Uma mensagem de erro estará definida como mensagem de erro duplicada se o identificador e o idioma forem os mesmos.</span><span class="sxs-lookup"><span data-stu-id="17500-111">An error message is defined as a duplicate error message if the identifier and the language are the same.</span></span> <span data-ttu-id="17500-112">A tarefa Transferir Mensagens de Erro pode ser configurada para controlar mensagens de erro da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="17500-112">The Transfer Error Messages task can be configured to handle existing error messages in the following ways:</span></span>  
  
-   <span data-ttu-id="17500-113">Substituir mensagens de erro existentes.</span><span class="sxs-lookup"><span data-stu-id="17500-113">Overwrite existing error messages.</span></span>  
  
-   <span data-ttu-id="17500-114">Interromper a tarefa quando houver mensagens duplicadas.</span><span class="sxs-lookup"><span data-stu-id="17500-114">Fail the task when duplicate messages exist.</span></span>  
  
-   <span data-ttu-id="17500-115">Ignorar mensagens de erro duplicadas.</span><span class="sxs-lookup"><span data-stu-id="17500-115">Skip duplicate error messages.</span></span>  
  
 <span data-ttu-id="17500-116">No tempo de execução, a tarefa Transferir Mensagens de Erro conecta-se aos servidores de origem e de destino usando um ou dois gerenciadores de conexões SMO.</span><span class="sxs-lookup"><span data-stu-id="17500-116">At run time, the Transfer Error Messages task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="17500-117">O gerenciador de conexões SMO é configurado separadamente da tarefa Transferir Mensagens de Erro e, depois, é consultado na tarefa Transferir Mensagens de Erro.</span><span class="sxs-lookup"><span data-stu-id="17500-117">The SMO connection manager is configured separately from the Transfer Error Messages task, and then is referenced in the Transfer Error Messages task.</span></span> <span data-ttu-id="17500-118">O gerenciador de conexões SMO especifica o servidor e o modo de autenticação a ser usado ao acessar o servidor.</span><span class="sxs-lookup"><span data-stu-id="17500-118">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="17500-119">Para obter mais informações, consulte [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="17500-119">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="17500-120">A tarefa Transferir Mensagens de Erro dá suporte a uma origem e a um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="17500-120">The Transfer Error Messages task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="17500-121">Não há nenhuma restrição quanto à versão a ser usada como origem ou destino.</span><span class="sxs-lookup"><span data-stu-id="17500-121">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="17500-122">Eventos</span><span class="sxs-lookup"><span data-stu-id="17500-122">Events</span></span>  
 <span data-ttu-id="17500-123">A tarefa gera  um evento de informações que informa o número de mensagens de erro que foram transferidas.</span><span class="sxs-lookup"><span data-stu-id="17500-123">The task raises an information event that reports the number of error messages that have been transferred.</span></span>  
  
 <span data-ttu-id="17500-124">A tarefa Transferir Mensagens de Erro não informa o progresso incremental da transferência de mensagem de erro; informa somente conclusão 0% e 100 %.</span><span class="sxs-lookup"><span data-stu-id="17500-124">The Transfer Error Messages task does not report incremental progress of the error message transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="17500-125">Valor de execução</span><span class="sxs-lookup"><span data-stu-id="17500-125">Execution Value</span></span>  
 <span data-ttu-id="17500-126">O valor de execução, definido na propriedade `ExecutionValue` da tarefa retorna o número de mensagens de erro que foram transferidas.</span><span class="sxs-lookup"><span data-stu-id="17500-126">The execution value, defined in the `ExecutionValue` property of the task, returns the number of error messages that have been transferred.</span></span> <span data-ttu-id="17500-127">Ao atribuir uma variável definida pelo usuário à propriedade `ExecValueVariable` da tarefa Transferir Mensagens de Erro, as informações sobre a mensagem de erro podem ser disponibilizadas para outros objetos no pacote.</span><span class="sxs-lookup"><span data-stu-id="17500-127">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Error Message task, information about the error message transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="17500-128">Para obter mais informações, consulte [Variáveis do Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) e [Usar variáveis em pacotes](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="17500-128">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="17500-129">Entradas de log</span><span class="sxs-lookup"><span data-stu-id="17500-129">Log Entries</span></span>  
 <span data-ttu-id="17500-130">A tarefa Transferir Mensagens de Erro inclui as seguintes entradas de log personalizadas:</span><span class="sxs-lookup"><span data-stu-id="17500-130">The Transfer Error Messages task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="17500-131">TransferErrorMessagesTaskStartTransferringObjects   Essa entrada de log informa que a transferência foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="17500-131">TransferErrorMessagesTaskStartTransferringObjects    This log entry reports that the transfer has started.</span></span> <span data-ttu-id="17500-132">A entrada do log contém a hora de início.</span><span class="sxs-lookup"><span data-stu-id="17500-132">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="17500-133">TransferErrorMessagesTaskFinishedTransferringObjects    Essa entrada de log informa que a transferência foi concluída.</span><span class="sxs-lookup"><span data-stu-id="17500-133">TransferErrorMessagesTaskFinishedTransferringObjects   This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="17500-134">A entrada do log contém a hora de término.</span><span class="sxs-lookup"><span data-stu-id="17500-134">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="17500-135">Além disso, uma entrada de log para o evento `OnInformation` informa o número de mensagens de erro transferidas e uma entrada de log para `OnWarning event` é gravada para cada mensagem de erro no destino que for substituído.</span><span class="sxs-lookup"><span data-stu-id="17500-135">In addition, a log entry for the `OnInformation` event reports the number of error messages that were transferred, and a log entry for the `OnWarning event` is written for each error message on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="17500-136">Segurança e permissões</span><span class="sxs-lookup"><span data-stu-id="17500-136">Security and Permissions</span></span>  
 <span data-ttu-id="17500-137">Para criar novas mensagens de erro, o usuário que executa o pacote deve ser um membro do sysadmin ou ter função de servidor  serveradmin no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="17500-137">To create new error messages, the user that runs the package must be a member of the sysadmin or serveradmin server role on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-error-messages-task"></a><span data-ttu-id="17500-138">Configuração da tarefa Transferir Mensagens de Erro</span><span class="sxs-lookup"><span data-stu-id="17500-138">Configuration of the Transfer Error Messages Task</span></span>  
 <span data-ttu-id="17500-139">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="17500-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="17500-140">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="17500-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="17500-141">Editor da Tarefa Transferir Mensagens de Erro &#40;Página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="17500-141">Transfer Error Messages Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="17500-142">Editor da Tarefa Transferir Mensagens de Erro &#40;Página Mensagens&#41;</span><span class="sxs-lookup"><span data-stu-id="17500-142">Transfer Error Messages Task Editor &#40;Messages Page&#41;</span></span>](../transfer-error-messages-task-editor-messages-page.md)  
  
-   [<span data-ttu-id="17500-143">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="17500-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="17500-144">Para obter informações sobre como definir essas propriedades programaticamente, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="17500-144">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferErrorMessagesTask.TransferErrorMessagesTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="17500-145">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="17500-145">Related Tasks</span></span>  
 <span data-ttu-id="17500-146">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="17500-146">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="17500-147">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="17500-147">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="17500-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="17500-148">See Also</span></span>  
 <span data-ttu-id="17500-149">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="17500-149">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="17500-150">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="17500-150">Control Flow</span></span>](control-flow.md)  
  
  
