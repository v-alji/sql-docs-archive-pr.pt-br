---
title: MSSQL_ENG021798 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021798 error
ms.assetid: 596f5092-75ab-4a19-8582-588687c7b089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 327b4a373c28376701ea12400215ab00367df66a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679861"
---
# <a name="mssql_eng021798"></a><span data-ttu-id="e9ed4-102">MSSQL_ENG021798</span><span class="sxs-lookup"><span data-stu-id="e9ed4-102">MSSQL_ENG021798</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e9ed4-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="e9ed4-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e9ed4-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="e9ed4-104">Product Name</span></span>|<span data-ttu-id="e9ed4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9ed4-105">SQL Server</span></span>|  
|<span data-ttu-id="e9ed4-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e9ed4-106">Event ID</span></span>|<span data-ttu-id="e9ed4-107">21798</span><span class="sxs-lookup"><span data-stu-id="e9ed4-107">21798</span></span>|  
|<span data-ttu-id="e9ed4-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="e9ed4-108">Event Source</span></span>|<span data-ttu-id="e9ed4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e9ed4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e9ed4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e9ed4-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e9ed4-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="e9ed4-111">Symbolic Name</span></span>||  
|<span data-ttu-id="e9ed4-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="e9ed4-112">Message Text</span></span>|<span data-ttu-id="e9ed4-113">O trabalho do agente '%s' deve ser adicionado por meio de '%s' antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e9ed4-113">The '%s' agent job must be added through '%s' before continuing.</span></span> <span data-ttu-id="e9ed4-114">Consulte a documentação de '%s'.</span><span class="sxs-lookup"><span data-stu-id="e9ed4-114">Please see the documentation for '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e9ed4-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="e9ed4-115">Explanation</span></span>  
 <span data-ttu-id="e9ed4-116">Para criar uma publicação, é necessário ser membro da função de servidor fixa **sysadmin** no Publicador ou membro da função de banco de dados fixa **db_owner** no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="e9ed4-116">To create a publication, you must be a member of the **sysadmin** fixed server role on the Publisher or a member of the **db_owner** fixed database role in the publication database.</span></span> <span data-ttu-id="e9ed4-117">Se você for membro da função **db_owner** , o erro será gerado se:</span><span class="sxs-lookup"><span data-stu-id="e9ed4-117">If you are a member of the **db_owner** role, this error is raised if:</span></span>  
  
-   <span data-ttu-id="e9ed4-118">Você executar scripts do [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9ed4-118">You run scripts from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="e9ed4-119">O modelo de segurança foi alterado no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]e esses scripts devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="e9ed4-119">The security model changed in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and these scripts must be updated.</span></span>  
  
-   <span data-ttu-id="e9ed4-120">O procedimento armazenado **sp_addpublication** é executado antes da execução de [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9ed4-120">The stored procedure **sp_addpublication** is executed before executing [sp_addlogreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogreader-agent-transact-sql).</span></span> <span data-ttu-id="e9ed4-121">Isso se aplica a todas as publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="e9ed4-121">This applies to all transactional publications.</span></span>  
  
-   <span data-ttu-id="e9ed4-122">O procedimento armazenado **sp_addpublication** é executado antes da execução de [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9ed4-122">The stored procedure **sp_addpublication** is executed before executing [sp_addqreader_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql).</span></span> <span data-ttu-id="e9ed4-123">Isso se aplica a publicações transacionais habilitadas para assinaturas de atualização enfileiradas (um valor de TRUE para o **@allow_queued_tran** parâmetro de **sp_addpublication**).</span><span class="sxs-lookup"><span data-stu-id="e9ed4-123">This applies to transactional publications that are enabled for queued updating subscriptions (a value of TRUE for the **@allow_queued_tran** parameter of **sp_addpublication**).</span></span>  
  
 <span data-ttu-id="e9ed4-124">Os procedimentos armazenados **sp_addlogreader_agent** e **sp_addqreader_agent** criam um trabalho de agente e permitem que você especifique a conta do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows em que o agente é executado.</span><span class="sxs-lookup"><span data-stu-id="e9ed4-124">The stored procedures **sp_addlogreader_agent** and **sp_addqreader_agent** each create an agent job and allow you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the agent runs.</span></span> <span data-ttu-id="e9ed4-125">Para usuários na função **sysadmin** , os trabalhos de agente são criados implicitamente se **sp_addlogreader_agent** e **sp_addqreader_agent** não forem executados. Os agentes são executados no contexto da conta do serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e9ed4-125">For users in the **sysadmin** role, agent jobs are created implicitly if **sp_addlogreader_agent** and **sp_addqreader_agent** are not executed; agents run under the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account at the Distributor.</span></span> <span data-ttu-id="e9ed4-126">Embora **sp_addlogreader_agent** e **sp_addqreader_agent** não sejam solicitados para usuários na função **sysadmin** , é uma prática recomendada de segurança especificar uma conta separada para os agentes.</span><span class="sxs-lookup"><span data-stu-id="e9ed4-126">Although **sp_addlogreader_agent** and **sp_addqreader_agent** are not required for users in the **sysadmin** role, it is a security best practice to specify a separate account for the agents.</span></span> <span data-ttu-id="e9ed4-127">Para obter mais informações, consulte [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="e9ed4-127">For more information, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e9ed4-128">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="e9ed4-128">User Action</span></span>  
 <span data-ttu-id="e9ed4-129">Certifique-se de executar os procedimentos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="e9ed4-129">Ensure you execute procedures in the correct order.</span></span> <span data-ttu-id="e9ed4-130">Para obter mais informações, consulte [criar uma publicação](publish/create-a-publication.md), atualizar esses scripts para incluir os procedimentos armazenados e os parâmetros exigidos pelo [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e pelas versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="e9ed4-130">For more information, see [Create a Publication](publish/create-a-publication.md), update these scripts to include the stored procedures and parameters required by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="e9ed4-131">Para obter mais informações, consulte [Atualizar scripts de replicação &#40;programação Transact-SQL de replicação&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="e9ed4-131">For more information, see [Upgrade Replication Scripts &#40;Replication Transact-SQL Programming&#41;](administration/upgrade-replication-scripts-replication-transact-sql-programming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ed4-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e9ed4-132">See Also</span></span>  
 [<span data-ttu-id="e9ed4-133">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="e9ed4-133">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
