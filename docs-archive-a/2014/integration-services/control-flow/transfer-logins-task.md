---
title: Tarefa Transferir Logons | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.f1
helpviewer_keywords:
- Transfer Logins task [Integration Services]
ms.assetid: 1df60fd6-c019-405d-8155-c330dbac2cc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d42d39b6cc7c2f350e3e3adc774be23934981369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568720"
---
# <a name="transfer-logins-task"></a><span data-ttu-id="e6180-102">Tarefa Transferir Logons</span><span class="sxs-lookup"><span data-stu-id="e6180-102">Transfer Logins Task</span></span>
  <span data-ttu-id="e6180-103">A tarefa Transferir Logons transfere um ou mais logons entre instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6180-103">The Transfer Logins task transfers one or more logins between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="transfer-logins-between-instances-of-sql-server"></a><span data-ttu-id="e6180-104">Transfer logons entre instâncias do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6180-104">Transfer Logins Between Instances of SQL Server</span></span>  
 <span data-ttu-id="e6180-105">A tarefa Transferir Logons dá suporte a uma origem e a um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6180-105">The Transfer Logins task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="e6180-106">Eventos</span><span class="sxs-lookup"><span data-stu-id="e6180-106">Events</span></span>  
 <span data-ttu-id="e6180-107">A tarefa gera um evento de informação com o número de logons transferidos e um evento de aviso quando um logon é substituído.</span><span class="sxs-lookup"><span data-stu-id="e6180-107">The task raises an information event that reports the number of logins transferred and a warning event when a login is overwritten.</span></span>  
  
 <span data-ttu-id="e6180-108">A tarefa Transferir Logons não informa o progresso incremental da transferência de logons; informa só 0% e 100% concluídos.</span><span class="sxs-lookup"><span data-stu-id="e6180-108">The Transfer Logins task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="e6180-109">Valor de execução</span><span class="sxs-lookup"><span data-stu-id="e6180-109">Execution Value</span></span>  
 <span data-ttu-id="e6180-110">O valor de execução, definido na propriedade da tarefa `ExecutionValue` retorna o número de logons que são transferidos.</span><span class="sxs-lookup"><span data-stu-id="e6180-110">The execution value, defined in the `ExecutionValue` property of the task, returns the number of logins transferred.</span></span> <span data-ttu-id="e6180-111">Ao atribuir uma variável definida pelo usuário à propriedade `ExecValueVariable` da tarefa Transferir Logons, informações sobre a transferência de logons podem se tornar disponíveis a outros objetos no pacote.</span><span class="sxs-lookup"><span data-stu-id="e6180-111">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Logins task, information about the login transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="e6180-112">Para obter mais informações, consulte [Variáveis do Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) e [Usar variáveis em pacotes](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="e6180-112">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="e6180-113">Entradas de log</span><span class="sxs-lookup"><span data-stu-id="e6180-113">Log Entries</span></span>  
 <span data-ttu-id="e6180-114">A tarefa Transferir Logons inclui as seguintes entradas de log personalizadas:</span><span class="sxs-lookup"><span data-stu-id="e6180-114">The Transfer Logins task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="e6180-115">TransferLoginsTaskStarTransferringObjects    Essa entrada de log informa que a transferência foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="e6180-115">TransferLoginsTaskStarTransferringObjects    This log entry reports the transfer has started.</span></span> <span data-ttu-id="e6180-116">A entrada do log contém a hora de início.</span><span class="sxs-lookup"><span data-stu-id="e6180-116">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="e6180-117">TransferLoginsTaskFinishedTransferringObjects   Essa entrada de log informa que a transferência foi concluída.</span><span class="sxs-lookup"><span data-stu-id="e6180-117">TransferLoginsTaskFinishedTransferringObjects   This log entry reports the transfer has completed.</span></span> <span data-ttu-id="e6180-118">A entrada do log contém a hora de término.</span><span class="sxs-lookup"><span data-stu-id="e6180-118">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="e6180-119">Além disso, uma entrada de log para o evento `OnInformation` informa o número de logons que foram transferidos e uma entrada de log para o evento `OnWarning` é gravada para cada logon no destino que for substituído.</span><span class="sxs-lookup"><span data-stu-id="e6180-119">In addition, a log entry for the `OnInformation` event reports the number of logins that were transferred, and a log entry for the `OnWarning` event is written for each login on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="e6180-120">Segurança e permissões</span><span class="sxs-lookup"><span data-stu-id="e6180-120">Security and Permissions</span></span>  
 <span data-ttu-id="e6180-121">Para procurar logons no servidor de origem e criar logons no servidor de destino, o usuário deve ser um membro da função de sysadmin em ambos os servidores.</span><span class="sxs-lookup"><span data-stu-id="e6180-121">To browse logins on the source server and to create logins on the destination server, the user must be a member of the sysadmin server role on both servers.</span></span>  
  
## <a name="configuration-of-the-transfer-logins-task"></a><span data-ttu-id="e6180-122">Configuração da tarefa Transferir Logons</span><span class="sxs-lookup"><span data-stu-id="e6180-122">Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="e6180-123">A tarefa Transferira Logons pode ser configurada para transferir todos os logons, só os logons especificados ou todos os logons que só têm acesso a bancos de dados especificados.</span><span class="sxs-lookup"><span data-stu-id="e6180-123">The Transfer Logins task can be configured to transfer all logins, only specified logins, or all logins that have access to specified databases only.</span></span> <span data-ttu-id="e6180-124">O logon do sa não pode ser transferido.</span><span class="sxs-lookup"><span data-stu-id="e6180-124">The sa login cannot be transferred.</span></span> <span data-ttu-id="e6180-125">O logon sa pode ser renomeado; porém, o logon sa renomeado não pode ser transferido.</span><span class="sxs-lookup"><span data-stu-id="e6180-125">The sa login may be renamed; however, the renamed sa login cannot be transferred either.</span></span>  
  
 <span data-ttu-id="e6180-126">Você também pode indicar se a tarefa deve copiar os SIDs (identificadores de segurança) associados aos logons.</span><span class="sxs-lookup"><span data-stu-id="e6180-126">You can also indicate whether the task copies the security identifiers (SIDs) associated with the logins.</span></span> <span data-ttu-id="e6180-127">Se a tarefa Transferir Logons for usada junto com a tarefa Transferir Banco de Dados, os SIDs deverão ser copiados para o destino; caso contrário, os logons transferidos não serão reconhecidos pelo banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="e6180-127">If the Transfer Logins task is used in conjunction with the Transfer Database task the SIDs must be copied to the destination; otherwise, the transferred logins are not recognized by the destination database.</span></span>  
  
 <span data-ttu-id="e6180-128">No destino, os logons transferidos são desabilitados e senhas aleatórias são atribuídas a eles.</span><span class="sxs-lookup"><span data-stu-id="e6180-128">At the destination, the transferred logins are disabled and assigned random passwords.</span></span> <span data-ttu-id="e6180-129">Um membro da função de sysadmin no servidor de destino deve alterar as senhas e habilitar os logons antes de os logons poderem ser usados.</span><span class="sxs-lookup"><span data-stu-id="e6180-129">A member of the sysadmin role on the destination server must change the passwords and enable the logins before the logins can be used.</span></span>  
  
 <span data-ttu-id="e6180-130">Os logons a serem transferidos já podem existir no destino.</span><span class="sxs-lookup"><span data-stu-id="e6180-130">The logins to be transferred may already exist on the destination.</span></span> <span data-ttu-id="e6180-131">A tarefa Transferir Logons pode ser configurada para manipular os logons existentes dos modos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e6180-131">The Transfer Logins task can be configured to handle existing logins in the following ways:</span></span>  
  
-   <span data-ttu-id="e6180-132">Substituir os logons existentes.</span><span class="sxs-lookup"><span data-stu-id="e6180-132">Overwrite existing logins.</span></span>  
  
-   <span data-ttu-id="e6180-133">Interromper a tarefa quando houver logons duplicados.</span><span class="sxs-lookup"><span data-stu-id="e6180-133">Fail the task when duplicate logins exist.</span></span>  
  
-   <span data-ttu-id="e6180-134">Ignorar logons duplicados.</span><span class="sxs-lookup"><span data-stu-id="e6180-134">Skip duplicate logins.</span></span>  
  
 <span data-ttu-id="e6180-135">No tempo de execução, a tarefa Transferir Logons conecta-se aos servidores de origem e de destino usando dois gerenciadores de conexões SMO.</span><span class="sxs-lookup"><span data-stu-id="e6180-135">At run time, the Transfer Logins task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="e6180-136">Os gerenciadores de conexões SMO são configurados separadamente da tarefa Transferir Logons e depois são referenciados na tarefa Transferir Logons.</span><span class="sxs-lookup"><span data-stu-id="e6180-136">The SMO connection managers are configured separately from the Transfer Logins task, and then referenced in the Transfer Logins task.</span></span> <span data-ttu-id="e6180-137">Os gerenciadores de conexões SMO especificam o servidor e o modo de autenticação a serem usados ao acessar o servidor.</span><span class="sxs-lookup"><span data-stu-id="e6180-137">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="e6180-138">Para obter mais informações, consulte [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e6180-138">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="e6180-139">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="e6180-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e6180-140">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e6180-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e6180-141">Editor da Tarefa Transferir Logons &#40;Página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="e6180-141">Transfer Logins Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="e6180-142">Editor da Tarefa Transferir Logons &#40;Página Logons&#41;</span><span class="sxs-lookup"><span data-stu-id="e6180-142">Transfer Logins Task Editor &#40;Logins Page&#41;</span></span>](../transfer-logins-task-editor-logins-page.md)  
  
-   [<span data-ttu-id="e6180-143">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="e6180-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="e6180-144">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="e6180-144">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e6180-145">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="e6180-145">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-transfer-logins-task"></a><span data-ttu-id="e6180-146">Configuração programática da tarefa Transferir Logons</span><span class="sxs-lookup"><span data-stu-id="e6180-146">Programmatic Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="e6180-147">Para obter mais informações sobre como definir essas propriedades programaticamente, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="e6180-147">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferLoginsTask.TransferLoginsTask>  
  
  
