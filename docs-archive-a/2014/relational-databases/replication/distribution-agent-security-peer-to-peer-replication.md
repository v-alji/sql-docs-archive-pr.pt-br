---
title: Segurança do agente de distribuição (replicação ponto a ponto) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.p2pwizard.DA.f1
ms.assetid: def6bf26-c640-4caf-ad30-05d1e649541d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72b5a52fbb3ddc11d0ea6f2c0b26786463e08eaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569929"
---
# <a name="distribution-agent-security-peer-to-peer-replication"></a><span data-ttu-id="119a2-102">Segurança do Agente de Distribuição (replicação ponto a ponto)</span><span class="sxs-lookup"><span data-stu-id="119a2-102">Distribution Agent Security (Peer-to-Peer Replication)</span></span>
  <span data-ttu-id="119a2-103">A página **Segurança do Agente de Distribuição** permite especificar as contas nas quais o Agente de Distribuição é executado e faz conexões com computadores em uma topologia ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="119a2-103">The **Distribution Agent Security** page allows you to specify the accounts under which the Distribution Agent runs and makes connections to the computers in a peer-to-peer topology.</span></span> <span data-ttu-id="119a2-104">Para obter informações sobre as permissões necessárias para os agentes e as melhores práticas de segurança da replicação, consulte [Modelo de segurança do agente de replicação](security/replication-agent-security-model.md) e [Melhores práticas de segurança da replicação](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="119a2-104">For information on permissions required by agents and best practices for replication security, see [Replication Agent Security Model](security/replication-agent-security-model.md) and [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="119a2-105">Se o Agente de Distribuição de uma assinatura já foi configurado em uma execução anterior deste assistente, você não poderá alterar as credenciais que ele usa neste assistente.</span><span class="sxs-lookup"><span data-stu-id="119a2-105">If the Distribution Agent for a subscription has already been configured in a previous run of this wizard, you cannot change the credentials it uses in this wizard.</span></span> <span data-ttu-id="119a2-106">Se você especificar credenciais novas, elas serão ignoradas.</span><span class="sxs-lookup"><span data-stu-id="119a2-106">If you specify new credentials, they are ignored.</span></span> <span data-ttu-id="119a2-107">Para alterar as credenciais, use a caixa de diálogo **Propriedades de Assinatura** .</span><span class="sxs-lookup"><span data-stu-id="119a2-107">To change credentials, use the **Subscription Properties** dialog box.</span></span> <span data-ttu-id="119a2-108">Para obter mais informações, consulte [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="119a2-108">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="119a2-109">Opções</span><span class="sxs-lookup"><span data-stu-id="119a2-109">Options</span></span>  
 <span data-ttu-id="119a2-110">Clique no botão de propriedades ( **...** ) na linha de cada Assinante para acessar a caixa de diálogo **Segurança do Agente de Distribuição** .</span><span class="sxs-lookup"><span data-stu-id="119a2-110">Click the properties button (**...**) in the row for each Subscriber to access the **Distribution Agent Security** dialog box.</span></span> <span data-ttu-id="119a2-111">Clique em **Ajuda** na caixa de diálogo **Segurança do Agente de Distribuição** que é iniciada para obter mais informações sobre as permissões requeridas para contas usadas pelos agentes.</span><span class="sxs-lookup"><span data-stu-id="119a2-111">Click **Help** on the **Distribution Agent Security** dialog box that is launched for more information on the permissions required for accounts used by the agents.</span></span>  
  
 <span data-ttu-id="119a2-112">Depois que as configurações forem inseridas em uma das caixas de diálogo, as informações de conexão para o Assinante serão exibidas na grade.</span><span class="sxs-lookup"><span data-stu-id="119a2-112">After settings have been entered in one of the dialog boxes, connection information for the Subscriber is displayed in the grid.</span></span>  
  
 <span data-ttu-id="119a2-113">**Agente para Assinante**</span><span class="sxs-lookup"><span data-stu-id="119a2-113">**Agent for Subscriber**</span></span>  
 <span data-ttu-id="119a2-114">O nome de cada computador par.</span><span class="sxs-lookup"><span data-stu-id="119a2-114">The name of each peer.</span></span>  
  
 <span data-ttu-id="119a2-115">**Banco de dados par**</span><span class="sxs-lookup"><span data-stu-id="119a2-115">**Peer Database**</span></span>  
 <span data-ttu-id="119a2-116">O banco de dados no mesmo nível que funciona como um banco de dados de publicação e um banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="119a2-116">The database at the peer that will serve as both a publication database and subscription database.</span></span>  
  
 <span data-ttu-id="119a2-117">**Conexão com o Distribuidor**</span><span class="sxs-lookup"><span data-stu-id="119a2-117">**Connection to Distributor**</span></span>  
 <span data-ttu-id="119a2-118">O contexto no qual a conexão com o Distribuidor é feita.</span><span class="sxs-lookup"><span data-stu-id="119a2-118">The context under which the connection to the Distributor is made.</span></span> <span data-ttu-id="119a2-119">Conexões locais sempre são feitas usando o contexto da conta do Windows na qual o agente é executado.</span><span class="sxs-lookup"><span data-stu-id="119a2-119">Local connections are always made using the context of the Windows account under which the agent runs.</span></span> <span data-ttu-id="119a2-120">Esse assistente cria assinaturas push (a conexão local é a conexão com o Distribuidor); portanto, esse campo sempre exibirá: **Representar '\<Domain>\\<Logon\>'** ou **Representar '\<Computer>\\<Logon\>'** .</span><span class="sxs-lookup"><span data-stu-id="119a2-120">This wizard creates push subscriptions (the local connection is the connection to the Distributor), so this field will always display: **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span>  
  
 <span data-ttu-id="119a2-121">**Conexão com o Assinante**</span><span class="sxs-lookup"><span data-stu-id="119a2-121">**Connection to Subscriber**</span></span>  
 <span data-ttu-id="119a2-122">O contexto no qual a conexão com o Assinante é feita.</span><span class="sxs-lookup"><span data-stu-id="119a2-122">The context under which the connection to the Subscriber is made.</span></span> <span data-ttu-id="119a2-123">A conexão pode ser feita usando o contexto da conta do Windows na qual o agente é executado ou no contexto de um logon no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="119a2-123">The connection can be made using the context of the Windows account under which the agent runs or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="119a2-124">O campo exibe uma das opções a seguir: **Usar o logon '\<Login>'** , **Representar '\<Domain>\\<Logon\>'** ou **Representar '\<Computer>\\<Logon\>'** .</span><span class="sxs-lookup"><span data-stu-id="119a2-124">The field displays one of the following: **Use login '\<Login>'**, **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span> <span data-ttu-id="119a2-125">A[!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda que todas as conexões sejam feitas com o uso do contexto da conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="119a2-125">[!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that all connections be made using the context of the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="119a2-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="119a2-126">See Also</span></span>  
 <span data-ttu-id="119a2-127">[Administrar uma topologia ponto a ponto &#40;programação Transact-SQL de replicação&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span><span class="sxs-lookup"><span data-stu-id="119a2-127">[Administer a Peer-to-Peer Topology &#40;Replication Transact-SQL Programming&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span></span>  
 [<span data-ttu-id="119a2-128">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="119a2-128">Peer-to-Peer Transactional Replication</span></span>](transactional/peer-to-peer-transactional-replication.md)  
  
  
