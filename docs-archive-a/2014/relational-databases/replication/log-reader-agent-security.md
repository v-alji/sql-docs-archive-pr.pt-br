---
title: Segurança do Agente de Leitor de Log | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.LRA.f1
helpviewer_keywords:
- Log Reader Agent Security dialog box
ms.assetid: d6981e74-ddb8-41b8-9ea1-56c2ece63b8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4be41aa9135e20a334616b9cb9d76a773f8d0e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684651"
---
# <a name="log-reader-agent-security"></a><span data-ttu-id="564dc-102">Segurança do Log Reader Agent</span><span class="sxs-lookup"><span data-stu-id="564dc-102">Log Reader Agent Security</span></span>
  <span data-ttu-id="564dc-103">A caixa de diálogo **Segurança do Log Reader Agent** permite especificar:</span><span class="sxs-lookup"><span data-stu-id="564dc-103">The **Log Reader Agent Security** dialog box allows you to specify:</span></span>  
  
-   <span data-ttu-id="564dc-104">A conta do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows na qual o Log Reader Agent é executado no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="564dc-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="564dc-105">A conta do Windows é também referida como *conta do processo*, porque o processo do agente é executado nessa conta.</span><span class="sxs-lookup"><span data-stu-id="564dc-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span>  
  
-   <span data-ttu-id="564dc-106">O contexto no qual o Agente de Leitor de Log faz conexões com o Publicador do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="564dc-106">The context under which the Log Reader Agent makes connections to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.</span></span> <span data-ttu-id="564dc-107">A conexão pode ser feita representando a conta do Windows ou no contexto de uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especificada por você.</span><span class="sxs-lookup"><span data-stu-id="564dc-107">The connection can be made by impersonating the Windows account or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="564dc-108">O Log Reader Agent fará conexões com o Publicador mesmo que o Publicador e o Distribuidor estejam no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="564dc-108">The Log Reader Agent makes connections to the Publisher even if the Publisher and Distributor are on the same computer.</span></span> <span data-ttu-id="564dc-109">O Log Reader Agent também faz conexões com o Distribuidor; essas conexões sempre são feitas representando a conta do Windows na qual o agente é executado.</span><span class="sxs-lookup"><span data-stu-id="564dc-109">The Log Reader Agent also makes connections to the Distributor; these connections are always made by impersonating the Windows account under which the agent runs.</span></span>  
  
     <span data-ttu-id="564dc-110">Para Publicadores Oracle, especifique o contexto no qual o Log Reader Agent faz conexão com o Editor na caixa de diálogo **Propriedades do Publicador** (disponível na caixa de diálogo **Propriedades do Distribuidor** ).</span><span class="sxs-lookup"><span data-stu-id="564dc-110">For Oracle Publishers, specify the context under which the Log Reader Agent connects to the Publisher in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="564dc-111">Para obter mais informações, consulte [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="564dc-111">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="564dc-112">Todas as contas devem ser válidas, com a senha correta especificada para cada conta.</span><span class="sxs-lookup"><span data-stu-id="564dc-112">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="564dc-113">Contas e senhas não são validadas até que um agente seja executado.</span><span class="sxs-lookup"><span data-stu-id="564dc-113">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="564dc-114">Opções</span><span class="sxs-lookup"><span data-stu-id="564dc-114">Options</span></span>  
 <span data-ttu-id="564dc-115">**Conta do processo**</span><span class="sxs-lookup"><span data-stu-id="564dc-115">**Process account**</span></span>  
 <span data-ttu-id="564dc-116">Insira uma conta do Windows na qual o Log Reader Agent é executado no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="564dc-116">Enter a Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="564dc-117">A conta do Windows especificada deve ser, no mínimo, um membro da função de banco de dados fixa **db_owner** no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="564dc-117">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="564dc-118">**Senha** e **Confirmar Senha**</span><span class="sxs-lookup"><span data-stu-id="564dc-118">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="564dc-119">Insira a senha para a conta do Windows.</span><span class="sxs-lookup"><span data-stu-id="564dc-119">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="564dc-120">**Conectar ao Publicador**</span><span class="sxs-lookup"><span data-stu-id="564dc-120">**Connect to the Publisher**</span></span>  
 <span data-ttu-id="564dc-121">Selecione se o Log Reader Agent deverá fazer conexões com o Publicador e o Distribuidor representando a conta especificada na caixa de texto **Conta de processo** ou usando uma conta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="564dc-121">Select whether the Log Reader Agent should make connections to the Publisher by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="564dc-122">Se você optar por usar uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , insira um logon e uma senha [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="564dc-122">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="564dc-123">A[!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda a seleção para representar a conta do Windows em vez de usar uma conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="564dc-123">[!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="564dc-124">A conta do Windows ou do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usada para conexão com o Assinante deve ser, no mínimo, um membro da função de banco de dados fixa **db_owner** no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="564dc-124">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must at minimum be a member of the **db_owner** fixed database role in the publication database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="564dc-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="564dc-125">See Also</span></span>  
 <span data-ttu-id="564dc-126">[Gerenciar logons e senhas na replicação](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="564dc-126">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="564dc-127">[Modelo de segurança do agente de replicação](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="564dc-127">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="564dc-128">[Visão geral dos agentes de replicação](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="564dc-128">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="564dc-129">Replication Security Best Practices</span><span class="sxs-lookup"><span data-stu-id="564dc-129">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
