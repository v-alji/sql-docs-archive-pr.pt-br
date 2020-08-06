---
title: Tarefa Transferir Procedimentos Armazenados Mestres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfermasterspstask.f1
helpviewer_keywords:
- Transfer Master Stored Procedures task [Integration Services]
ms.assetid: 81702560-48a3-46d1-a469-e41304c7af8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1915a3129eeb6e14c4315c37f2c6c2bf5b0d5412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685226"
---
# <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="36754-102">Tarefa Transferir Procedimentos Armazenados Mestres</span><span class="sxs-lookup"><span data-stu-id="36754-102">Transfer Master Stored Procedures Task</span></span>
  <span data-ttu-id="36754-103">A tarefa Transferir Procedimentos Armazenados Mestres transfere um ou mais procedimentos armazenados definidos pelo usuário entre bancos de dados **mestre** em instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36754-103">The Transfer Master Stored Procedures task transfers one or more user-defined stored procedures between **master** databases on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="36754-104">Para transferir um procedimento armazenado do banco de dados **mestre** , o proprietário do procedimento deve ser dbo.</span><span class="sxs-lookup"><span data-stu-id="36754-104">To transfer a stored procedure from the **master** database, the owner of the procedure must be dbo.</span></span>  
  
 <span data-ttu-id="36754-105">A tarefa Transferir Procedimentos Armazenados Mestres pode ser configurada para transferir todos os procedimentos armazenados ou apenas procedimentos armazenados específicos.</span><span class="sxs-lookup"><span data-stu-id="36754-105">The Transfer Master Stored Procedures task can be configured to transfer all stored procedures or only specified stored procedures.</span></span> <span data-ttu-id="36754-106">Essa tarefa não copia procedimentos armazenados do sistema.</span><span class="sxs-lookup"><span data-stu-id="36754-106">This task does not copy system stored procedures.</span></span>  
  
 <span data-ttu-id="36754-107">Os procedimentos armazenados mestres a serem transferidos podem já existir no destino.</span><span class="sxs-lookup"><span data-stu-id="36754-107">The master stored procedures to be transferred may already exist on the destination.</span></span> <span data-ttu-id="36754-108">A tarefa Transferir Procedimentos Armazenados Mestres pode ser configurada para lidar com procedimentos já existentes armazenados das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="36754-108">The Transfer Master Stored Procedures task can be configured to handle existing stored procedures in the following ways:</span></span>  
  
-   <span data-ttu-id="36754-109">Substituir procedimentos armazenados existentes.</span><span class="sxs-lookup"><span data-stu-id="36754-109">Overwrite existing stored procedures.</span></span>  
  
-   <span data-ttu-id="36754-110">Interromper a tarefa quando existirem procedimentos armazenados duplicados.</span><span class="sxs-lookup"><span data-stu-id="36754-110">Fail the task when duplicate stored procedures exist.</span></span>  
  
-   <span data-ttu-id="36754-111">Ignorar procedimentos armazenados duplicados.</span><span class="sxs-lookup"><span data-stu-id="36754-111">Skip duplicate stored procedures.</span></span>  
  
 <span data-ttu-id="36754-112">Em tempo de execução, a tarefa Transferir Procedimentos Armazenados Mestres conecta-se aos servidores de origem e de destino usando dois gerenciadores de conexões SMO.</span><span class="sxs-lookup"><span data-stu-id="36754-112">At run time, the Transfer Master Stored Procedures task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="36754-113">Os gerenciadores de conexões SMO são configurados separadamente a partir da tarefa Transferir Procedimentos Armazenados Mestres e depois referenciados na tarefa Transferir Procedimentos Armazenados Mestres.</span><span class="sxs-lookup"><span data-stu-id="36754-113">The SMO connection managers are configured separately from the Transfer Master Stored Procedures task, and then referenced in the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="36754-114">Os gerenciadores de conexões SMO especificam o servidor e o modo de autenticação a serem usados ao acessar o servidor.</span><span class="sxs-lookup"><span data-stu-id="36754-114">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="36754-115">Para obter mais informações, consulte [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="36754-115">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-stored-procedures-between-instances-of-sql-server"></a><span data-ttu-id="36754-116">Transferindo procedimentos armazenados entre instâncias do SQL Server</span><span class="sxs-lookup"><span data-stu-id="36754-116">Transferring Stored Procedures Between Instances of SQL Server</span></span>  
 <span data-ttu-id="36754-117">A tarefa Transferir Procedimentos Armazenados Mestres dá suporte a uma origem e a um destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36754-117">The Transfer Master Stored Procedures task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="36754-118">Eventos</span><span class="sxs-lookup"><span data-stu-id="36754-118">Events</span></span>  
 <span data-ttu-id="36754-119">A tarefa gera um evento de informações que informa o número de procedimentos armazenados transferidos e um evento de aviso quando um procedimento armazenado é substituído.</span><span class="sxs-lookup"><span data-stu-id="36754-119">The task raises an information event that reports the number of stored procedures transferred and a warning event when a stored procedure is overwritten.</span></span>  
  
 <span data-ttu-id="36754-120">A tarefa Transferir Procedimentos Armazenados Mestres não informa o progresso incremental da transferência de logon; ela apenas informa 0% e 100% de conclusão.</span><span class="sxs-lookup"><span data-stu-id="36754-120">The Transfer Master Stored Procedures task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="36754-121">Valor de execução</span><span class="sxs-lookup"><span data-stu-id="36754-121">Execution Value</span></span>  
 <span data-ttu-id="36754-122">O valor de execução definido na propriedade da tarefa `ExecutionValue` retorna o número de procedimentos armazenados transferidos.</span><span class="sxs-lookup"><span data-stu-id="36754-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of stored procedures transferred.</span></span> <span data-ttu-id="36754-123">Atribuindo uma variável definida pelo usuário à `ExecValueVariable` propriedade da tarefa Transferir Procedimentos Armazenados Mestres, as informações sobre a transferência de procedimentos armazenados podem ser disponibilizadas para outros objetos do pacote.</span><span class="sxs-lookup"><span data-stu-id="36754-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Master Stored Procedures task, information about the stored procedure transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="36754-124">Para obter mais informações, consulte [Variáveis do Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) e [Usar variáveis em pacotes](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="36754-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="36754-125">Entradas de log</span><span class="sxs-lookup"><span data-stu-id="36754-125">Log Entries</span></span>  
 <span data-ttu-id="36754-126">A tarefa Transferir Procedimentos Armazenados Mestres inclui as seguintes entradas de log personalizadas:</span><span class="sxs-lookup"><span data-stu-id="36754-126">The Transfer Master Stored Procedures task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="36754-127">TransferStoredProceduresTaskStartTransferringObjects Essa entrada de log informa que a transferência foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="36754-127">TransferStoredProceduresTaskStartTransferringObjects  This log entry reports that the transfer has started.</span></span> <span data-ttu-id="36754-128">A entrada do log contém a hora de início.</span><span class="sxs-lookup"><span data-stu-id="36754-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="36754-129">TransferSStoredProceduresTaskFinishedTransferringObjects Essa entrada de log informa que a transferência foi concluída.</span><span class="sxs-lookup"><span data-stu-id="36754-129">TransferSStoredProceduresTaskFinishedTransferringObjects  This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="36754-130">A entrada do log contém a hora de término.</span><span class="sxs-lookup"><span data-stu-id="36754-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="36754-131">Além disso, uma entrada de log para o evento `OnInformation` informa o número de procedimentos armazenados que foram transferidos e uma entrada de log para o evento `OnWarning` é gravada para cada procedimento armazenado no destino que é substituído.</span><span class="sxs-lookup"><span data-stu-id="36754-131">In addition, a log entry for the `OnInformation` event reports the number of stored procedures that were transferred, and a log entry for the `OnWarning` event is written for each stored procedure on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="36754-132">Segurança e permissões</span><span class="sxs-lookup"><span data-stu-id="36754-132">Security and Permissions</span></span>  
 <span data-ttu-id="36754-133">O usuário deve ter permissão para exibir a lista do procedimento armazenado no banco de dados **mestre** na origem e deve ser um membro da função de servidor sysadmin ou ter permissão para procedimentos armazenados criados no banco de dados **mestre** no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="36754-133">The user must have permission to view the list of stored procedure in the **master** database on the source, and must be a member of the sysadmin server role or have permission to created stored procedures in the **master** database on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-master-stored-procedures-task"></a><span data-ttu-id="36754-134">Configuração da tarefa Transferir Procedimentos Armazenados Mestres</span><span class="sxs-lookup"><span data-stu-id="36754-134">Configuration of the Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="36754-135">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="36754-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="36754-136">Para obter informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="36754-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="36754-137">Editor da Tarefa Transferir Procedimentos Armazenados Mestres &#40;página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="36754-137">Transfer Master Stored Procedures Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="36754-138">Editor da Tarefa Transferir Procedimentos Armazenados Mestres &#40;Página Procedimentos Armazenados&#41;</span><span class="sxs-lookup"><span data-stu-id="36754-138">Transfer Master Stored Procedures Task Editor &#40;Stored Procedures Page&#41;</span></span>](../transfer-master-stored-procedures-task-editor-stored-procedures-page.md)  
  
-   [<span data-ttu-id="36754-139">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="36754-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="36754-140">Para obter informações sobre como definir essas propriedades programaticamente, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="36754-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferStoredProceduresTask.TransferStoredProceduresTask>  
  
### <a name="configuring-the-transfer-master-stored-procedures-task-programmatically"></a><span data-ttu-id="36754-141">Configurando a tarefa Transferir Procedimentos Armazenados Mestres programaticamente</span><span class="sxs-lookup"><span data-stu-id="36754-141">Configuring the Transfer Master Stored Procedures Task Programmatically</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="36754-142">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="36754-142">Related Tasks</span></span>  
 <span data-ttu-id="36754-143">Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="36754-143">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="36754-144">Definir as propriedades de uma tarefa ou contêiner</span><span class="sxs-lookup"><span data-stu-id="36754-144">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="36754-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="36754-145">See Also</span></span>  
 <span data-ttu-id="36754-146">[Tarefa Transferir Objetos do SQL Server](transfer-sql-server-objects-task.md) </span><span class="sxs-lookup"><span data-stu-id="36754-146">[Transfer SQL Server Objects Task](transfer-sql-server-objects-task.md) </span></span>  
 <span data-ttu-id="36754-147">[Tarefas do Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="36754-147">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="36754-148">Fluxo de Controle</span><span class="sxs-lookup"><span data-stu-id="36754-148">Control Flow</span></span>](control-flow.md)  
  
  
