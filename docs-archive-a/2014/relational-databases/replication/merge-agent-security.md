---
title: Segurança do Agente de Mesclagem | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.MA.f1
helpviewer_keywords:
- Merge Agent Security dialog box
ms.assetid: 9b86171a-4381-4b39-869a-cdc161e7cd15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecbb044ca87ccfc74c5cb39a016667d15cf7a859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681623"
---
# <a name="merge-agent-security"></a><span data-ttu-id="d902e-102">Segurança do Merge Agent</span><span class="sxs-lookup"><span data-stu-id="d902e-102">Merge Agent Security</span></span>
  <span data-ttu-id="d902e-103">A caixa de diálogo **Segurança do Merge Agent** permite especificar a conta do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows na qual o Merge Agent é executado.</span><span class="sxs-lookup"><span data-stu-id="d902e-103">The **Merge Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Merge Agent runs.</span></span> <span data-ttu-id="d902e-104">O Merge Agent é executado no Distribuidor para assinaturas push e no Assinante para assinaturas pull.</span><span class="sxs-lookup"><span data-stu-id="d902e-104">The Merge Agent runs at the Distributor for push subscriptions and at the Subscriber for pull subscriptions.</span></span> <span data-ttu-id="d902e-105">A conta do Windows é também referida como *conta do processo*, porque o processo do agente é executado nessa conta.</span><span class="sxs-lookup"><span data-stu-id="d902e-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span> <span data-ttu-id="d902e-106">Opções adicionais disponíveis na caixa de diálogo dependem de como você a acessa:</span><span class="sxs-lookup"><span data-stu-id="d902e-106">Additional options available in the dialog box depend on how you access it:</span></span>  
  
-   <span data-ttu-id="d902e-107">Se a caixa de diálogo for acessada do Assistente para Nova Assinatura, também permitirá que você especifique o contexto no qual o Merge Agent fará conexões com o Assinante (para assinaturas push) ou com o Publicador e o Distribuidor (para assinaturas pull).</span><span class="sxs-lookup"><span data-stu-id="d902e-107">If the dialog box is accessed from the New Subscription Wizard, it also allows you to specify the context under which the Merge Agent makes connections to the Subscriber (for push subscriptions) or the Publisher and Distributor (for pull subscriptions).</span></span> <span data-ttu-id="d902e-108">A conexão pode ser feita usando a conta do Windows ou no contexto de uma conta do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especificada.</span><span class="sxs-lookup"><span data-stu-id="d902e-108">The connection can be made using the Windows account or under the context of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
-   <span data-ttu-id="d902e-109">Se a caixa de diálogo for acessada pela caixa de diálogo **Propriedades da Assinatura** , especifique o contexto no qual o Merge Agent fará conexões ao clicar no botão de propriedades ( **...** ) na linha **Conexão do Assinante** ou **Conexão do Publicador** daquela caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d902e-109">If the dialog box is accessed from the **Subscription Properties** dialog box, specify the context under which the Merge Agent makes connections by clicking the properties button (**...**) in the **Subscriber Connection** or **Publisher Connection** row of that dialog box.</span></span> <span data-ttu-id="d902e-110">Para obter mais informações sobre como acessar a caixa de diálogo **Propriedades da Assinatura**, consulte [Exibir e modificar as propriedades da assinatura push](view-and-modify-push-subscription-properties.md) e [Exibir e modificar as propriedades da assinatura pull](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d902e-110">For more information about accessing the **Subscription Properties** dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and how to: [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
 <span data-ttu-id="d902e-111">Todas as contas devem ser válidas, com a senha correta especificada para cada conta.</span><span class="sxs-lookup"><span data-stu-id="d902e-111">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="d902e-112">Contas e senhas não são validadas até que um agente seja executado.</span><span class="sxs-lookup"><span data-stu-id="d902e-112">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d902e-113">Opções</span><span class="sxs-lookup"><span data-stu-id="d902e-113">Options</span></span>  
 <span data-ttu-id="d902e-114">**Process Account**</span><span class="sxs-lookup"><span data-stu-id="d902e-114">**Process Account**</span></span>  
 <span data-ttu-id="d902e-115">Insira uma conta Windows na qual o Merge Agent é executado.</span><span class="sxs-lookup"><span data-stu-id="d902e-115">Enter a Windows account under which the Merge Agent runs.</span></span>  
  
-   <span data-ttu-id="d902e-116">Para assinaturas push, a conta deve:</span><span class="sxs-lookup"><span data-stu-id="d902e-116">For push subscriptions, the account must:</span></span>  
  
    -   <span data-ttu-id="d902e-117">Ser, no mínimo, um membro da função de banco de dados fixa **db_owner** no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="d902e-117">At minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
    -   <span data-ttu-id="d902e-118">Ser um membro da PAL.</span><span class="sxs-lookup"><span data-stu-id="d902e-118">Be a member of the PAL.</span></span>  
  
    -   <span data-ttu-id="d902e-119">Ser um logon associado a um usuário no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="d902e-119">Be a login associated with a user in the publication database.</span></span>  
  
    -   <span data-ttu-id="d902e-120">Ter permissões de leitura no compartilhamento de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="d902e-120">Have read permissions on the snapshot share.</span></span>  
  
-   <span data-ttu-id="d902e-121">Para assinaturas pull, a conta deve ser, no mínimo, um membro da função de banco de dados fixa **db_owner** no banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="d902e-121">For pull subscriptions, the account must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
 <span data-ttu-id="d902e-122">Serão requeridas permissões adicionais se a conta do processo for representada quando as conexões forem feitas.</span><span class="sxs-lookup"><span data-stu-id="d902e-122">Additional permissions are required if the process account is impersonated when connections are made.</span></span> <span data-ttu-id="d902e-123">Consulte as seções **Conectar ao Publicador e ao Distribuidor** e **Conectar ao Assinante** a seguir.</span><span class="sxs-lookup"><span data-stu-id="d902e-123">See the **Connect to the Publisher and Distributor** and **Connect to the Subscriber** sections below.</span></span>  
  
 <span data-ttu-id="d902e-124">A **Conta do Processo** não pode ser especificada para assinaturas pull para o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], porque o Agente de Mesclagem não é executado em instâncias do [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d902e-124">**Process Account** cannot be specified for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], because the Merge Agent does not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
 <span data-ttu-id="d902e-125">**Senha** e **Confirmar Senha**</span><span class="sxs-lookup"><span data-stu-id="d902e-125">**Password** and **Confirm Password**</span></span>  
 <span data-ttu-id="d902e-126">Insira a senha para a conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="d902e-126">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="d902e-127">**Conectar ao Publicador e ao Distribuidor**</span><span class="sxs-lookup"><span data-stu-id="d902e-127">**Connect to the Publisher and Distributor**</span></span>  
 <span data-ttu-id="d902e-128">Para assinaturas push, as conexões com o Publicador e o Distribuidor são sempre feitas representando a conta especificada na caixa de texto **Conta do processo** .</span><span class="sxs-lookup"><span data-stu-id="d902e-128">For push subscriptions, connections to the Publisher and Distributor are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="d902e-129">Para assinaturas pull, selecione se o Merge Agent deve fazer conexões com o Publicador e o Distribuidor representando a conta especificada na caixa de texto **Conta do processo** ou usando uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d902e-129">For pull subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="d902e-130">Se você optar por usar uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , insira um logon e uma senha [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d902e-130">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d902e-131">A[!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda a seleção para representar a conta do Windows em vez de usar uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d902e-131">[!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="d902e-132">A conta do Windows ou do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usada para a conexão deve:</span><span class="sxs-lookup"><span data-stu-id="d902e-132">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must:</span></span>  
  
-   <span data-ttu-id="d902e-133">Ser um membro da PAL.</span><span class="sxs-lookup"><span data-stu-id="d902e-133">Be a member of the PAL.</span></span>  
  
-   <span data-ttu-id="d902e-134">Ser um logon associado a um usuário no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="d902e-134">Be a login associated with a user in the publication database.</span></span>  
  
-   <span data-ttu-id="d902e-135">Ser um logon associado a um usuário no banco de dados de distribuição (o usuário pode ser o usuário Convidado).</span><span class="sxs-lookup"><span data-stu-id="d902e-135">Be a login associated with a user in the distribution database (the user can be the Guest user).</span></span>  
  
-   <span data-ttu-id="d902e-136">Ter permissões de leitura no compartilhamento de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="d902e-136">Have read permissions on the snapshot share.</span></span>  
  
 <span data-ttu-id="d902e-137">**Conectar ao Assinante**</span><span class="sxs-lookup"><span data-stu-id="d902e-137">**Connect to the Subscriber**</span></span>  
 <span data-ttu-id="d902e-138">Para assinaturas pull, as conexões com o Assinante são sempre feitas representando a conta especificada na caixa de texto **Conta do processo** .</span><span class="sxs-lookup"><span data-stu-id="d902e-138">For pull subscriptions, connections to the Subscriber are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="d902e-139">Para assinaturas push, selecione se o Merge Agent deve fazer conexões com o Publicador e o Distribuidor representando a conta especificada na caixa de texto **Conta do processo** ou usando uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d902e-139">For push subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="d902e-140">Se você optar por usar uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , insira um logon e uma senha [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d902e-140">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d902e-141">É recomendável a seleção para representar a conta do Windows em vez de usar uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d902e-141">It is recommended that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="d902e-142">A conta do Windows ou do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usada para conexão com o Assinante deve ser, no mínimo, um membro da função de banco de dados fixa **db_owner** no banco de dados de assinatura.</span><span class="sxs-lookup"><span data-stu-id="d902e-142">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection to the Subscriber must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d902e-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d902e-143">See Also</span></span>  
 <span data-ttu-id="d902e-144">[Gerenciar logons e senhas na replicação](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="d902e-144">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="d902e-145">[Modelo de segurança do agente de replicação](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="d902e-145">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="d902e-146">[Visão geral dos agentes de replicação](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="d902e-146">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 <span data-ttu-id="d902e-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="d902e-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="d902e-148">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="d902e-148">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
