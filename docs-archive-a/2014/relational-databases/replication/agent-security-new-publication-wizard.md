---
title: Segurança do agente (Assistente para nova publicação) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.agentsecurity.articles.f1
ms.assetid: 05ae44df-8e9f-46ea-95f6-972ad109c6c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a0da30cb49a73024ca83d8587a4f6477d21c49c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571966"
---
# <a name="agent-security-new-publication-wizard"></a><span data-ttu-id="ca952-102">Segurança do Agente (Assistente para Nova Publicação)</span><span class="sxs-lookup"><span data-stu-id="ca952-102">Agent Security (New Publication Wizard)</span></span>
  <span data-ttu-id="ca952-103">A página **Segurança do Agente** permite especificar as contas nas quais os seguintes agentes executam e fazem conexões com computadores em uma topologia de replicação:</span><span class="sxs-lookup"><span data-stu-id="ca952-103">The **Agent Security** page allows you to specify the accounts under which the following agents run and make connections to the computers in a replication topology:</span></span>  
  
-   <span data-ttu-id="ca952-104">O Agente de Instantâneo para todas as publicações.</span><span class="sxs-lookup"><span data-stu-id="ca952-104">The Snapshot Agent for all publications.</span></span>  
  
-   <span data-ttu-id="ca952-105">O Agente de Leitor de Log para todas as publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="ca952-105">The Log Reader Agent for all transactional publications.</span></span>  
  
-   <span data-ttu-id="ca952-106">O Agente de Leitor de Fila para publicações transacionais que permitem assinaturas atualizáveis.</span><span class="sxs-lookup"><span data-stu-id="ca952-106">The Queue Reader Agent for transactional publications that allow updatable subscriptions.</span></span> <span data-ttu-id="ca952-107">O trabalho do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para esse agente será criado se você especificar **Publicação transacional com assinaturas atualizáveis** na página **Tipo de Publicação**, independentemente do tipo de assinatura atualizável usado.</span><span class="sxs-lookup"><span data-stu-id="ca952-107">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job for this agent is created if you specified **Transactional publication with updatable subscriptions** on the **Publication Type** page, regardless of the type of updatable subscriptions you use.</span></span> <span data-ttu-id="ca952-108">Para obter mais informações sobre assinaturas atualizáveis, consulte [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ca952-108">For more information about updatable subscriptions, see [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="ca952-109">Para obter mais informações sobre permissões requeridas por agentes e práticas recomendadas para segurança de replicação, consulte [Replication Agent Security Model](security/replication-agent-security-model.md) e [Replication Security Best Practices](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="ca952-109">For information about permissions required by agents and best practices for replication security, see [Replication Agent Security Model](security/replication-agent-security-model.md) and [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ca952-110">Opções</span><span class="sxs-lookup"><span data-stu-id="ca952-110">Options</span></span>  
 <span data-ttu-id="ca952-111">**Snapshot Agent**</span><span class="sxs-lookup"><span data-stu-id="ca952-111">**Snapshot Agent**</span></span>  
 <span data-ttu-id="ca952-112">Exibido para todas as publicações.</span><span class="sxs-lookup"><span data-stu-id="ca952-112">Displayed for all publications.</span></span> <span data-ttu-id="ca952-113">Clique em **Configurações de Segurança** para especificar configurações de segurança na caixa de diálogo **Segurança do Agente de Instantâneo** .</span><span class="sxs-lookup"><span data-stu-id="ca952-113">Click **Security Settings** to specify security settings in the **Snapshot Agent Security** dialog box.</span></span>  
  
 <span data-ttu-id="ca952-114">Clique em **Ajuda** na caixa de diálogo **Segurança do Agente de Instantâneo** para obter mais informações sobre as permissões necessárias para contas usadas pelo Agente de Instantâneo.</span><span class="sxs-lookup"><span data-stu-id="ca952-114">Click **Help** on the **Snapshot Agent Security** dialog box for more information about the permissions required for accounts used by the Snapshot Agent.</span></span>  
  
 <span data-ttu-id="ca952-115">**Agente de Leitor de Log**</span><span class="sxs-lookup"><span data-stu-id="ca952-115">**Log Reader Agent**</span></span>  
 <span data-ttu-id="ca952-116">Exibido para todas as publicações transacionais.</span><span class="sxs-lookup"><span data-stu-id="ca952-116">Displayed for all transactional publications.</span></span> <span data-ttu-id="ca952-117">Clique em **Configurações de Segurança** para especificar configurações de segurança na caixa de diálogo **Segurança do Agente de Leitor de Log** .</span><span class="sxs-lookup"><span data-stu-id="ca952-117">Click **Security Settings** to specify security settings in the **Log Reader Agent Security** dialog box.</span></span>  
  
 <span data-ttu-id="ca952-118">Clique em **Ajuda** na caixa de diálogo **Segurança do Agente de Leitor de Log** para obter mais informações sobre as permissões requeridas para contas usadas pelo Agente de Leitor de Log.</span><span class="sxs-lookup"><span data-stu-id="ca952-118">Click **Help** on the **Log Reader Agent Security** dialog box for more information about the permissions required for accounts used by the Log Reader Agent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca952-119">Há um Agente de Leitor de Log para cada banco de dados publicado que usa a replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="ca952-119">There is one Log Reader Agent for each database that is published using transactional replication.</span></span> <span data-ttu-id="ca952-120">Se uma publicação transacional já existir no banco de dados, as configurações de segurança serão somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ca952-120">If a transactional publication already exists in the database, the security settings are read-only.</span></span> <span data-ttu-id="ca952-121">Você pode alterar as configurações na caixa de diálogo **Propriedades de Publicação** , mas as alterações afetam todas as publicações transacionais no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ca952-121">You can change the settings in the **Publication Properties** dialog box, but changes affect all transactional publications in the database.</span></span>  
  
 <span data-ttu-id="ca952-122">**Queue Reader Agent**</span><span class="sxs-lookup"><span data-stu-id="ca952-122">**Queue Reader Agent**</span></span>  
 <span data-ttu-id="ca952-123">Exibido para todas as publicações transacionais que permitem assinaturas atualizáveis.</span><span class="sxs-lookup"><span data-stu-id="ca952-123">Displayed for transactional publications that allow updatable subscriptions.</span></span> <span data-ttu-id="ca952-124">Clique em **Configurações de Segurança** para especificar configurações de segurança na caixa de diálogo **Segurança do Agente de Leitor de Fila** .</span><span class="sxs-lookup"><span data-stu-id="ca952-124">Click **Security Settings** to specify security settings in the **Queue Reader Agent Security** dialog box.</span></span> <span data-ttu-id="ca952-125">O trabalho Agente de Leitor de Fila é criado quando o assistente é concluído; ele não depende da criação de nenhuma assinatura de atualização enfileirada.</span><span class="sxs-lookup"><span data-stu-id="ca952-125">A Queue Reader Agent job is created when this wizard completes; it does not depend on you creating any queued updating subscriptions.</span></span> <span data-ttu-id="ca952-126">Se você não planeja criar assinaturas de atualização enfileirada, pode desabilitar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="ca952-126">If you do not plan to create any queued updating subscriptions, you can disable the job.</span></span> <span data-ttu-id="ca952-127">Clique com o botão direito do mouse no trabalho (citado no formato: *[\<Publisher>].\<integer>* .) na pasta **Trabalhos** do agente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], e clique em **Desabilitar**.</span><span class="sxs-lookup"><span data-stu-id="ca952-127">Right-click the job (named in the form: *[\<Publisher>].\<integer>*.) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **Jobs** folder, and then click **Disable**.</span></span>  
  
 <span data-ttu-id="ca952-128">Clique em **Ajuda** na caixa de diálogo **Segurança do Agente de Leitor de Fila** para obter mais informações sobre as permissões requeridas para contas usadas pelo Agente de Leitor de Fila.</span><span class="sxs-lookup"><span data-stu-id="ca952-128">Click **Help** on the **Queue Reader Agent Security** dialog box for more information about the permissions required for accounts used by the Queue Reader Agent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca952-129">Há um Agente de Leitor de Fila para cada banco de dados de distribuição (e todos os Publicadores que ele serve).</span><span class="sxs-lookup"><span data-stu-id="ca952-129">There is one Queue Reader Agent for each distribution database (and all Publishers that it serves).</span></span> <span data-ttu-id="ca952-130">Se uma publicação transacional que permite assinaturas de atualização enfileiradas já existir em qualquer um dos Publicadores que usam um banco de dados de distribuição específico, as configurações de segurança serão somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ca952-130">If a transactional publication that allows queued updating subscriptions already exists on any of the Publishers that use a given distribution database, the security settings are read-only.</span></span> <span data-ttu-id="ca952-131">Você pode alterar a conta na qual o Agente de Leitor de Fila executa e faz conexões na caixa de diálogo **Propriedades do Distribuidor** , mas as alterações afetam as publicações em todos os Publicadores que usam o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="ca952-131">You can change the account under which the Queue Reader Agent runs and makes connections in the **Distributor Properties** dialog box, but changes affect publications at all Publishers that use the distribution database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca952-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ca952-132">See Also</span></span>  
 <span data-ttu-id="ca952-133">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="ca952-133">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="ca952-134">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span><span class="sxs-lookup"><span data-stu-id="ca952-134">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span></span>  
 <span data-ttu-id="ca952-135">[Exibir e modificar propriedades de Publicador e Distribuidor](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ca952-135">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 <span data-ttu-id="ca952-136">[Exibir e modificar as propriedades da publicação](publish/view-and-modify-publication-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ca952-136">[View and Modify Publication Properties](publish/view-and-modify-publication-properties.md) </span></span>  
 <span data-ttu-id="ca952-137">[Gerenciar logons e senhas na replicação](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="ca952-137">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="ca952-138">[Publicar dados e objetos de banco de dados](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="ca952-138">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="ca952-139">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="ca952-139">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  