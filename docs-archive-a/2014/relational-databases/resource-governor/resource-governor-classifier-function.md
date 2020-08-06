---
title: Função do classificador do Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function
- user-defined functions [SQL Server], classifier function
- classifier function [SQL Server]
- classifier function [SQL Server], overview
ms.assetid: 64c25012-7068-476f-afa2-0b4f3adde9a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69b6fd10ac0adc6f76925e0d41f110b917111466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680349"
---
# <a name="resource-governor-classifier-function"></a><span data-ttu-id="4af56-102">Função de classificação do Administrador de Recursos</span><span class="sxs-lookup"><span data-stu-id="4af56-102">Resource Governor Classifier Function</span></span>
  <span data-ttu-id="4af56-103">O processo de classificação do administrador de recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atribui sessões de entrada a um grupo de cargas de trabalho baseado nas características da sessão.</span><span class="sxs-lookup"><span data-stu-id="4af56-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource governor classification process assigns incoming sessions to a workload group based on the characteristics of the session.</span></span> <span data-ttu-id="4af56-104">Você pode personalizar a lógica de classificação gravando uma função definida pelo usuário, chamado de função de classificador.</span><span class="sxs-lookup"><span data-stu-id="4af56-104">You can tailor the classification logic by writing a user-defined function, called a classifier function.</span></span>  
  
## <a name="classification"></a><span data-ttu-id="4af56-105">classificação</span><span class="sxs-lookup"><span data-stu-id="4af56-105">Classification</span></span>  
 <span data-ttu-id="4af56-106">O Administrador de Recursos oferece suporte à classificação de sessões de entrada.</span><span class="sxs-lookup"><span data-stu-id="4af56-106">Resource Governor supports the classification of incoming sessions.</span></span> <span data-ttu-id="4af56-107">A classificação baseia-se em um conjunto de critérios gravados pelo usuário contido em uma função.</span><span class="sxs-lookup"><span data-stu-id="4af56-107">Classification is based on a set of user-written criteria contained in a function.</span></span> <span data-ttu-id="4af56-108">Os resultados da lógica de função permitem que o Administrador de Recursos classifique as sessões em grupos de carga de trabalho existentes.</span><span class="sxs-lookup"><span data-stu-id="4af56-108">The results of the function logic enable Resource Governor to classify sessions into existing workload groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4af56-109">O grupo de carga de trabalho interno é populado com solicitações que são apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4af56-109">The internal workload group is populated with requests that are for internal use only.</span></span> <span data-ttu-id="4af56-110">Você não pode alterar os critérios usados para direcionar essas solicitações nem classificar as solicitações no grupo de carga de trabalho interno.</span><span class="sxs-lookup"><span data-stu-id="4af56-110">You cannot change the criteria used for routing these requests and you cannot classify requests into the internal workload group.</span></span>  
  
 <span data-ttu-id="4af56-111">É possível gravar uma função escalar contendo a lógica que é usada para atribuir sessões de entrada a um grupo de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4af56-111">You can write a scalar function that contains the logic that is used to assign incoming sessions to a workload group.</span></span> <span data-ttu-id="4af56-112">Para que você possa usar essa função, é necessário concluir as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="4af56-112">Before you can use this function, you must complete the following actions:</span></span>  
  
-   <span data-ttu-id="4af56-113">Crie e registre a função usando a instrução ALTER RESOURCE GOVERNOR.</span><span class="sxs-lookup"><span data-stu-id="4af56-113">Create and register the function using the ALTER RESOURCE GOVERNOR statement.</span></span> <span data-ttu-id="4af56-114">Para obter mais informações, veja [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4af56-114">For more information, see [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span></span>  
  
-   <span data-ttu-id="4af56-115">Atualize a configuração do Administrador de Recursos usando a instrução ALTER RESOURCE GOVERNOR com o parâmetro RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="4af56-115">Update the Resource Governor configuration using the ALTER RESOURCE GOVERNOR statement with the RECONFIGURE parameter.</span></span>  
  
 <span data-ttu-id="4af56-116">Depois que você criar a função e aplicar as alterações de configuração, o classificador do Administrador de Recursos usará o nome do grupo de carga de trabalho retornado pela função para enviar uma nova solicitação ao grupo de carga de trabalho adequado.</span><span class="sxs-lookup"><span data-stu-id="4af56-116">After you create the function and apply the configuration changes, the Resource Governor classifier will use the workload group name returned by the function to send a new request to the appropriate workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4af56-117">A sessão do cliente pode expirar caso a função de classificação não seja concluída dentro do tempo limite especificado para o logon.</span><span class="sxs-lookup"><span data-stu-id="4af56-117">The client session may time out if the classification function does not complete within the specified time-out for the login.</span></span> <span data-ttu-id="4af56-118">Tempo limite de logon é uma propriedade do cliente e, como tal, o servidor desconhece o tempo limite. Uma função de classificação com execução longa pode deixar o servidor com conexões órfãs por períodos longos.</span><span class="sxs-lookup"><span data-stu-id="4af56-118">Login time-out is a client property and as such, the server is unaware of a time-out. A long-running classifier function can leave the server with orphaned connections for long periods.</span></span> <span data-ttu-id="4af56-119">É importante que se criem funções de classificação que terminem de executar antes do tempo limite de conexão.</span><span class="sxs-lookup"><span data-stu-id="4af56-119">It is important that you create classifier functions that finish executing before a connection time-out.</span></span>  
  
 <span data-ttu-id="4af56-120">A função definida pelo usuário tem as seguintes características e comportamentos:</span><span class="sxs-lookup"><span data-stu-id="4af56-120">The user-defined function has the following characteristics and behaviors:</span></span>  
  
-   <span data-ttu-id="4af56-121">A função definida pelo usuário é avaliada para cada sessão nova, mesmo quando o pooling de conexões está habilitado.</span><span class="sxs-lookup"><span data-stu-id="4af56-121">The user-defined function is evaluated for every new session, even when connection pooling is enabled.</span></span>  
  
-   <span data-ttu-id="4af56-122">A função definida pelo usuário fornece contexto de grupo de carga de trabalho para a sessão.</span><span class="sxs-lookup"><span data-stu-id="4af56-122">The user-defined function gives workload group context for the session.</span></span> <span data-ttu-id="4af56-123">Depois que a associação em grupo é determinada, a sessão é associada ao grupo de carga de trabalho durante o tempo de vida da sessão.</span><span class="sxs-lookup"><span data-stu-id="4af56-123">After group membership is determined, the session is bound to the workload group for the lifetime of the session.</span></span>  
  
-   <span data-ttu-id="4af56-124">Se a função definida pelo usuário retornar NULL, padrão ou o nome de um grupo inexistente, o contexto de grupo de carga de trabalho padrão será dado à sessão.</span><span class="sxs-lookup"><span data-stu-id="4af56-124">If the user-defined function returns NULL, default, or the name of non-existent group the session is given the default workload group context.</span></span> <span data-ttu-id="4af56-125">O contexto padrão também será dado à sessão caso a função falhe por qualquer motivo.</span><span class="sxs-lookup"><span data-stu-id="4af56-125">The session is also given the default context if the function fails for any reason.</span></span>  
  
-   <span data-ttu-id="4af56-126">A função deve ser definida com escopo do servidor (banco de dados mestre).</span><span class="sxs-lookup"><span data-stu-id="4af56-126">The function should be defined with server scope (master database).</span></span>  
  
-   <span data-ttu-id="4af56-127">A designação de função de classificação definida pelo usuário só entrará em vigor depois que ALTER RESOURCE GOVERNOR RECONFIGURE for executada.</span><span class="sxs-lookup"><span data-stu-id="4af56-127">The classifier user-defined function designation only takes effect after ALTER RESOURCE GOVERNOR RECONFIGURE is executed.</span></span>  
  
-   <span data-ttu-id="4af56-128">Só uma função definida pelo usuário pode ser designada como classificação por vez.</span><span class="sxs-lookup"><span data-stu-id="4af56-128">Only one user-defined function can be designated as a classifier at a time.</span></span>  
  
-   <span data-ttu-id="4af56-129">A função de classificação definida pelo usuário não pode ser descartada ou alterada a menos que seu estado de classificação seja removido.</span><span class="sxs-lookup"><span data-stu-id="4af56-129">The classifier user-defined function cannot be dropped or altered unless its classifier status is removed.</span></span>  
  
-   <span data-ttu-id="4af56-130">Na ausência de uma função de classificação definida pelo usuário, todas as sessões são classificadas no grupo padrão.</span><span class="sxs-lookup"><span data-stu-id="4af56-130">In the absence of a classifier user-defined function, all sessions are classified into the default group.</span></span>  
  
-   <span data-ttu-id="4af56-131">O grupo de carga de trabalho retornado pela função de classificação está fora do escopo da restrição de associação de esquema.</span><span class="sxs-lookup"><span data-stu-id="4af56-131">The workload group returned by the classifier function is outside the scope of the schema-binding restriction.</span></span> <span data-ttu-id="4af56-132">Por exemplo, você não pode descartar uma tabela, mas pode descartar um grupo de cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4af56-132">For example, you cannot drop a table, but you can drop a workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4af56-133">É recomendável habilitar a conexão de administrador dedicada (DAC) no servidor.</span><span class="sxs-lookup"><span data-stu-id="4af56-133">We recommend enabling the Dedicated Administrator Connection (DAC) on the server.</span></span> <span data-ttu-id="4af56-134">A DAC não está sujeita à classificação do Administrador de Recursos e pode ser usada para monitorar e solucionar problemas de uma função de classificação.</span><span class="sxs-lookup"><span data-stu-id="4af56-134">The DAC is not subject to Resource Governor classification and can be used to monitor and troubleshoot a classifier function.</span></span> <span data-ttu-id="4af56-135">Para obter mais informações, veja [Conexão de diagnóstico para administradores de banco de dados](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="4af56-135">For more information, see [Diagnostic Connection for Database Administrators](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span></span> <span data-ttu-id="4af56-136">Se uma DAC não estiver disponível para a solução de problemas, a outra opção é reiniciar o sistema no modo de usuário único.</span><span class="sxs-lookup"><span data-stu-id="4af56-136">If a DAC is not available for troubleshooting, the other option is to restart the system in single user mode.</span></span> <span data-ttu-id="4af56-137">Embora o modo de usuário único não esteja sujeito a classificação, ele não oferece a você a capacidade de diagnosticar a classificação do Administrador de Recursos enquanto está em execução.</span><span class="sxs-lookup"><span data-stu-id="4af56-137">Although single user mode is not subject to classification, it does not give you the ability to diagnose Resource Governor classification while it is running.</span></span>  
  
### <a name="classification-process"></a><span data-ttu-id="4af56-138">Processo de classificação</span><span class="sxs-lookup"><span data-stu-id="4af56-138">Classification Process</span></span>  
 <span data-ttu-id="4af56-139">No contexto do Administrador de Recursos, o processo de logon para uma sessão consiste nas seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4af56-139">In the context of Resource Governor, the login process for a session consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="4af56-140">Autenticação de logon</span><span class="sxs-lookup"><span data-stu-id="4af56-140">Login authentication</span></span>  
  
2.  <span data-ttu-id="4af56-141">Execução de gatilhos LOGON</span><span class="sxs-lookup"><span data-stu-id="4af56-141">LOGON trigger execution</span></span>  
  
3.  <span data-ttu-id="4af56-142">classificação</span><span class="sxs-lookup"><span data-stu-id="4af56-142">Classification</span></span>  
  
 <span data-ttu-id="4af56-143">Quando a classificação é iniciada, o Administrador de Recursos executa a função de classificação e usa o valor retornado pela função para enviar solicitações ao grupo de cargas de trabalho apropriado.</span><span class="sxs-lookup"><span data-stu-id="4af56-143">When classification starts, Resource Governor executes the classifier function and uses the value returned by the function to send requests to the appropriate workload group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4af56-144">As informações sobre a execução da função de classificação e dos gatilhos LOGON são expostas em [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) e [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4af56-144">Information about the execution of the classifier function and LOGON triggers is exposed in [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql).</span></span>  
  
## <a name="classification-function-tasks"></a><span data-ttu-id="4af56-145">Tarefas da função de classificação</span><span class="sxs-lookup"><span data-stu-id="4af56-145">Classification Function Tasks</span></span>  
  
|<span data-ttu-id="4af56-146">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="4af56-146">Task Description</span></span>|<span data-ttu-id="4af56-147">Tópico</span><span class="sxs-lookup"><span data-stu-id="4af56-147">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="4af56-148">Descreve como criar e testar uma função de classificação definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="4af56-148">Describes how to create and test a classifier user-defined function.</span></span>|[<span data-ttu-id="4af56-149">Criar e testar uma função de classificador definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="4af56-149">Create and Test a Classifier User-Defined Function</span></span>](create-and-test-a-classifier-user-defined-function.md)|  
  
## <a name="see-also"></a><span data-ttu-id="4af56-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4af56-150">See Also</span></span>  
 <span data-ttu-id="4af56-151">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="4af56-151">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="4af56-152">[Habilitar Administrador de Recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="4af56-152">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="4af56-153">[Pool de recursos do Administrador de Recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="4af56-153">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="4af56-154">[Grupos de carga de trabalho do Administrador de Recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="4af56-154">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="4af56-155">[Configurar o administrador de recursos usando um modelo](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="4af56-155">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="4af56-156">Exibir Propriedades do Administrador de Recursos</span><span class="sxs-lookup"><span data-stu-id="4af56-156">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
