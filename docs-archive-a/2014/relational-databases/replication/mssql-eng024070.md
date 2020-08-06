---
title: MSSQL_ENG024070 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG024070 error
ms.assetid: 23ac7e00-fab6-429b-9f85-2736a322aa65
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fcfcb96b284d46d46f63af4a650f925ef2de73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679859"
---
# <a name="mssql_eng024070"></a><span data-ttu-id="dd81b-102">MSSQL_ENG024070</span><span class="sxs-lookup"><span data-stu-id="dd81b-102">MSSQL_ENG024070</span></span>
    
## <a name="message-details"></a><span data-ttu-id="dd81b-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="dd81b-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd81b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="dd81b-104">Product Name</span></span>|<span data-ttu-id="dd81b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dd81b-105">SQL Server</span></span>|  
|<span data-ttu-id="dd81b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="dd81b-106">Event ID</span></span>|<span data-ttu-id="dd81b-107">24070</span><span class="sxs-lookup"><span data-stu-id="dd81b-107">24070</span></span>|  
|<span data-ttu-id="dd81b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="dd81b-108">Event Source</span></span>|<span data-ttu-id="dd81b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dd81b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dd81b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="dd81b-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="dd81b-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="dd81b-111">Symbolic Name</span></span>||  
|<span data-ttu-id="dd81b-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="dd81b-112">Message Text</span></span>|<span data-ttu-id="dd81b-113">O cliente não possui o privilégio exigido.</span><span class="sxs-lookup"><span data-stu-id="dd81b-113">A required privilege is not held by the client.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dd81b-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="dd81b-114">Explanation</span></span>  
 <span data-ttu-id="dd81b-115">Este é um erro geral que pode ocorrer independentemente do uso de replicação.</span><span class="sxs-lookup"><span data-stu-id="dd81b-115">This is a general error that can be raised regardless of whether replication is being used.</span></span> <span data-ttu-id="dd81b-116">Para um servidor em uma topologia de replicação, geralmente o erro ocorre porque a conta do serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é alterada usando o Gerenciador de Controle de Serviços do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows em vez do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="dd81b-116">For a server in a replication topology, the error is typically raised because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account is changed by using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Service Control Manager instead of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="dd81b-117">Ao tentar executar um trabalho de agente após alterar a conta de serviço, pode ocorrer falha no trabalho com uma mensagem de erro semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="dd81b-117">When you try to run an agent job after changing the service account, the job might fail with an error message that is similar to the following:</span></span>  
  
 <span data-ttu-id="dd81b-118">"Executado como usuário: \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="dd81b-118">"Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="dd81b-119">Replicação-subsistema de instantâneos de replicação: falha do agente \<AgentName> .</span><span class="sxs-lookup"><span data-stu-id="dd81b-119">Replication-Replication Snapshot Subsystem: agent \<AgentName> failed.</span></span> <span data-ttu-id="dd81b-120">Executado como usuário: \<UserAccount> .</span><span class="sxs-lookup"><span data-stu-id="dd81b-120">Executed as user: \<UserAccount>.</span></span> <span data-ttu-id="dd81b-121">O cliente não possui o privilégio exigido.</span><span class="sxs-lookup"><span data-stu-id="dd81b-121">A required privilege is not held by the client.</span></span> <span data-ttu-id="dd81b-122">A etapa falhou.</span><span class="sxs-lookup"><span data-stu-id="dd81b-122">The step failed.</span></span> <span data-ttu-id="dd81b-123">`[SQLSTATE 42000] (Error 14151)`.</span><span class="sxs-lookup"><span data-stu-id="dd81b-123">`[SQLSTATE 42000] (Error 14151)`.</span></span> <span data-ttu-id="dd81b-124">A etapa falhou."</span><span class="sxs-lookup"><span data-stu-id="dd81b-124">The step failed."</span></span>  
  
 <span data-ttu-id="dd81b-125">Esse problema ocorre porque o Gerenciador de Controle de Serviços do Windows não é capaz de conceder as permissões solicitadas para a nova conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="dd81b-125">This problem occurs because the Windows Service Control Manager cannot grant the required permissions to the new service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dd81b-126">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="dd81b-126">User Action</span></span>  
 <span data-ttu-id="dd81b-127">Para evitar esse problema posteriormente, sempre use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager em vez do Gerenciador de Controle de Serviços do Windows para alterar as contas e as senhas de serviço.</span><span class="sxs-lookup"><span data-stu-id="dd81b-127">To avoid this problem in the future, always use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager instead of the Windows Service Control Manager to change service accounts and passwords.</span></span>  
  
 <span data-ttu-id="dd81b-128">Para resolver esse problema, use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager para alterar a conta de serviço de volta para a conta original.</span><span class="sxs-lookup"><span data-stu-id="dd81b-128">To resolve this problem, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change the service account back to the original account.</span></span> <span data-ttu-id="dd81b-129">Em seguida, use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager para alterar para a nova conta.</span><span class="sxs-lookup"><span data-stu-id="dd81b-129">Then, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to change to the new account.</span></span> <span data-ttu-id="dd81b-130">Ao fazer isso, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager adiciona a nova conta ao seguinte grupo de segurança:</span><span class="sxs-lookup"><span data-stu-id="dd81b-130">When you do this, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager adds the new account to the following security group:</span></span>  
  
 <span data-ttu-id="dd81b-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span><span class="sxs-lookup"><span data-stu-id="dd81b-131">SQLServer2008SQLAgentUser$ComputerName$InstanceName</span></span>  
  
 <span data-ttu-id="dd81b-132">Ser um membro desse grupo de segurança concede à nova conta as permissões exigidas para executar o trabalho do agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="dd81b-132">Being a member of this security group grants to the new account the required permissions to run the replication agent job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd81b-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dd81b-133">See Also</span></span>  
 <span data-ttu-id="dd81b-134">[Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="dd81b-134">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="dd81b-135">[Gerenciar logons e senhas na replicação](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="dd81b-135">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 [<span data-ttu-id="dd81b-136">SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dd81b-136">SQL Server Configuration Manager</span></span>](../sql-server-configuration-manager.md)  
  
  
