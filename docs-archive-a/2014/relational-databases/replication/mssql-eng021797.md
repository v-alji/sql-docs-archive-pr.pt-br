---
title: MSSQL_ENG021797 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021797 error
ms.assetid: 54d83a1e-43fd-449c-a2b2-fdda2609a534
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d33ade7e7eea9fa9e95453a5b232447f7b222b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679863"
---
# <a name="mssql_eng021797"></a><span data-ttu-id="096ec-102">MSSQL_ENG021797</span><span class="sxs-lookup"><span data-stu-id="096ec-102">MSSQL_ENG021797</span></span>
    
## <a name="message-details"></a><span data-ttu-id="096ec-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="096ec-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="096ec-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="096ec-104">Product Name</span></span>|<span data-ttu-id="096ec-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="096ec-105">SQL Server</span></span>|  
|<span data-ttu-id="096ec-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="096ec-106">Event ID</span></span>|<span data-ttu-id="096ec-107">21797</span><span class="sxs-lookup"><span data-stu-id="096ec-107">21797</span></span>|  
|<span data-ttu-id="096ec-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="096ec-108">Event Source</span></span>|<span data-ttu-id="096ec-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="096ec-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="096ec-110">Componente</span><span class="sxs-lookup"><span data-stu-id="096ec-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="096ec-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="096ec-111">Symbolic Name</span></span>||  
|<span data-ttu-id="096ec-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="096ec-112">Message Text</span></span>|<span data-ttu-id="096ec-113">'%s' deve ser um logon válido do Windows no formato: 'MACHINE\Login' ou 'DOMAIN\Login'.</span><span class="sxs-lookup"><span data-stu-id="096ec-113">'%s' must be a valid Windows Login in the form: 'MACHINE\Login' or 'DOMAIN\Login'.</span></span> <span data-ttu-id="096ec-114">Consulte a documentação de '%s'.</span><span class="sxs-lookup"><span data-stu-id="096ec-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="096ec-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="096ec-115">Explanation</span></span>  
 <span data-ttu-id="096ec-116">Esse erro será gerado pelos seguintes procedimentos armazenados de replicação se o valor especificado para o **@job_login** parâmetro for nulo ou inválido.</span><span class="sxs-lookup"><span data-stu-id="096ec-116">This error is raised by the following replication stored procedures if the value specified for the **@job_login** parameter is null or not valid.</span></span> <span data-ttu-id="096ec-117">Esse erro poderá ocorrer se um membro da função de banco de dados fixa **db_owner** executar scripts de versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="096ec-117">This error can occur if a member of the **db_owner** fixed database role runs scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="096ec-118">O modelo de segurança foi alterado no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]e esses scripts devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="096ec-118">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   [<span data-ttu-id="096ec-119">sp_addlogreader_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="096ec-119">sp_addlogreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql)  
  
-   [<span data-ttu-id="096ec-120">sp_addqreader_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="096ec-120">sp_addqreader_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql)  
  
-   [<span data-ttu-id="096ec-121">sp_addpublication_snapshot &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="096ec-121">sp_addpublication_snapshot &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpublication-snapshot-transact-sql)  
  
-   [<span data-ttu-id="096ec-122">sp_addpushsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="096ec-122">sp_addpushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="096ec-123">sp_addpullsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="096ec-123">sp_addpullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="096ec-124">sp_addmergepushsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="096ec-124">sp_addmergepushsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepushsubscription-agent-transact-sql)  
  
-   [<span data-ttu-id="096ec-125">sp_addmergepullsubscription_agent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="096ec-125">sp_addmergepullsubscription_agent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmergepullsubscription-agent-transact-sql)  
  
 <span data-ttu-id="096ec-126">Esses procedimentos armazenados podem ser executados por um membro da função de servidor fixa **sysadmin** no servidor apropriado ou por um membro da função de banco de dados fixa **db_owner** no banco de dados apropriado.</span><span class="sxs-lookup"><span data-stu-id="096ec-126">These stored procedures can be executed by a member of the **sysadmin** fixed server role on the appropriate server or a member of the **db_owner** fixed database role in the appropriate database.</span></span> <span data-ttu-id="096ec-127">Os procedimentos armazenados criam um trabalho de agente e permitem que o usuário especifique a conta do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows em que o agente é executado.</span><span class="sxs-lookup"><span data-stu-id="096ec-127">The stored procedures each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="096ec-128">Para usuários na função **sysadmin** , os trabalhos de agente são criados implicitamente, ainda que uma conta do Windows não seja especificada (se uma conta for especificada, deve ser válida); agentes são executados no contexto da conta do serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no servidor apropriado.</span><span class="sxs-lookup"><span data-stu-id="096ec-128">For users in the **sysadmin** role, agent jobs are created implicitly even if a Windows account is not specified (if an account is specified, it must be valid); agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the appropriate server.</span></span> <span data-ttu-id="096ec-129">Apesar da conta não ser exigida, é uma prática recomendada de segurança especificar uma conta separada para os agentes.</span><span class="sxs-lookup"><span data-stu-id="096ec-129">Although the account is not required, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="096ec-130">Para obter mais informações, consulte [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="096ec-130">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="096ec-131">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="096ec-131">User Action</span></span>  
 <span data-ttu-id="096ec-132">Certifique-se de especificar uma conta do Windows válida para o **@job_login** parâmetro de cada procedimento.</span><span class="sxs-lookup"><span data-stu-id="096ec-132">Ensure you specify a valid Windows account for the **@job_login** parameter of each procedure.</span></span> <span data-ttu-id="096ec-133">Se tiver scripts de replicação de versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], atualize esses scripts para incluir os procedimento e os parâmetros armazenados exigidos pelo [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="096ec-133">If you have replication scripts from previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="096ec-134">Para obter mais informações, consulte [Atualizar scripts de replicação &#40;programação Transact-SQL de replicação&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="096ec-134">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="096ec-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="096ec-135">See Also</span></span>  
 [<span data-ttu-id="096ec-136">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="096ec-136">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
