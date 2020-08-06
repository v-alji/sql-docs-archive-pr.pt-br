---
title: Logon para assinaturas atualizáveis | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptionslogin.f1
ms.assetid: 301ea227-0455-40ba-9009-d38f8676b325
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a5cc9190c77f506b13ba8b5fba0e32d5a925570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684649"
---
# <a name="login-for-updatable-subscriptions"></a><span data-ttu-id="015e1-102">Logon para Assinaturas Atualizáveis</span><span class="sxs-lookup"><span data-stu-id="015e1-102">Login for Updatable Subscriptions</span></span>
  <span data-ttu-id="015e1-103">Se você selecionou **replicar** na página **assinaturas atualizáveis** desse assistente, deverá especificar uma conta no Assinante sob a qual as conexões com o Publicador são feitas para assinaturas de atualização imediata.</span><span class="sxs-lookup"><span data-stu-id="015e1-103">If you selected **Replicate** on the **Updatable Subscriptions** page of this wizard, you must specify an account at the Subscriber under which connections to the Publisher are made for immediate updating subscriptions.</span></span> <span data-ttu-id="015e1-104">Conexões são usadas pelos gatilhos acionados no Assinante e que propagam as alterações no Publicador.</span><span class="sxs-lookup"><span data-stu-id="015e1-104">Connections are used by the triggers that fire at the Subscriber and propagate changes to the Publisher.</span></span> <span data-ttu-id="015e1-105">Essa conta é necessária mesmo se você selecionou **as alterações de fila e confirma quando possível** na página **assinaturas atualizáveis** , pois, por padrão, o assistente para nova assinatura configura a atualização em fila com a capacidade de alternar para a atualização imediata, se necessário.</span><span class="sxs-lookup"><span data-stu-id="015e1-105">This account is required even if you selected **Queue changes and commit when possible** on the **Updatable Subscriptions** page, because by default the New Subscription Wizard configures queued updating with the ability to switch to immediate updating if required.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="015e1-106">A conta especificada para a conexão só deve receber permissão para inserir, atualizar e excluir dados nas exibições criadas pela replicação no banco de dados de publicação; nenhuma permissão adicional será dada.</span><span class="sxs-lookup"><span data-stu-id="015e1-106">The account specified for the connection should only be granted permission to insert, update, and delete data on the views that replication creates in the publication database; it should not be given any additional permissions.</span></span> <span data-ttu-id="015e1-107">Conceda permissões nas exibições do banco de dados de publicação que são denominadas no formato **syncobj_** _\<HexadecimalNumber>_ para a conta configurada em cada Assinante.</span><span class="sxs-lookup"><span data-stu-id="015e1-107">Grant permissions on views in the publication database that are named in the form **syncobj_**_\<HexadecimalNumber>_ to the account you configured at each Subscriber.</span></span>  
  
 <span data-ttu-id="015e1-108">Há três opções disponíveis para o tipo de conexão:</span><span class="sxs-lookup"><span data-stu-id="015e1-108">There are three options available for the type of connection:</span></span>  
  
-   <span data-ttu-id="015e1-109">Um servidor vinculado ou remoto que você já definiu.</span><span class="sxs-lookup"><span data-stu-id="015e1-109">A linked server or remote server that you have already defined.</span></span>  
  
-   <span data-ttu-id="015e1-110">Um servidor vinculado que a replicação cria; a conexão é feita com as credenciais que você especifica nesse assistente.</span><span class="sxs-lookup"><span data-stu-id="015e1-110">A linked server that replication creates; the connection is made with the credentials you specify in this wizard.</span></span>  
  
-   <span data-ttu-id="015e1-111">Um servidor vinculado que a replicação cria; a conexão é feita com as credenciais do usuário que faz a alteração no Assinante.</span><span class="sxs-lookup"><span data-stu-id="015e1-111">A linked server that replication creates; the connection is made with the credentials of the user making the change at the Subscriber.</span></span>  
  
 <span data-ttu-id="015e1-112">As duas primeiras opções podem ser especificadas nesse assistente.</span><span class="sxs-lookup"><span data-stu-id="015e1-112">The first two options can be specified in this wizard.</span></span> <span data-ttu-id="015e1-113">A última opção só pode ser especificada usando [sp_link_publication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql); Especifique um valor de **1** para o parâmetro **@security_mode** .</span><span class="sxs-lookup"><span data-stu-id="015e1-113">The last option can only be specified using [sp_link_publication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql); specify a value of **1** for the parameter **@security_mode**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="015e1-114">Opções</span><span class="sxs-lookup"><span data-stu-id="015e1-114">Options</span></span>  
 <span data-ttu-id="015e1-115">**Criar um servidor vinculado que conecta usando o seguinte logon de Autenticação do SQL Server:**</span><span class="sxs-lookup"><span data-stu-id="015e1-115">**Create a linked server that connects using the following SQL Server Authentication login:**</span></span>  
 <span data-ttu-id="015e1-116">A replicação cria um servidor vinculado usando as credenciais especificadas nos campos **Logon** e **Senha** .</span><span class="sxs-lookup"><span data-stu-id="015e1-116">Replication creates a linked server using the credentials specified in the **Login** and **Password** fields.</span></span>  
  
 <span data-ttu-id="015e1-117">**Logon**</span><span class="sxs-lookup"><span data-stu-id="015e1-117">**Login**</span></span>  
 <span data-ttu-id="015e1-118">Insira um logon [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que tenha somente as permissões descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="015e1-118">Enter a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that has only the permissions described in this topic.</span></span>  
  
 <span data-ttu-id="015e1-119">**Senha**</span><span class="sxs-lookup"><span data-stu-id="015e1-119">**Password**</span></span>  
 <span data-ttu-id="015e1-120">Insira uma senha forte para o logon especificado em **Logon**.</span><span class="sxs-lookup"><span data-stu-id="015e1-120">Enter a strong password for the login specified in **Login**.</span></span>  
  
 <span data-ttu-id="015e1-121">**Confirmar Senha**</span><span class="sxs-lookup"><span data-stu-id="015e1-121">**Confirm Password**</span></span>  
 <span data-ttu-id="015e1-122">Reinsira a senha para confirmar que ela foi inserida corretamente.</span><span class="sxs-lookup"><span data-stu-id="015e1-122">Re-enter the password to confirm that it was entered correctly.</span></span>  
  
 <span data-ttu-id="015e1-123">**Usar servidor vinculado ou remoto já definido.**</span><span class="sxs-lookup"><span data-stu-id="015e1-123">**Use a linked server or remote server that you have already defined.**</span></span>  
 <span data-ttu-id="015e1-124">Essa opção requer um servidor vinculado ou remoto já definido.</span><span class="sxs-lookup"><span data-stu-id="015e1-124">This option requires a linked server or remote server that you have already defined.</span></span> <span data-ttu-id="015e1-125">Para obter mais informações, consulte [Servidores vinculados &#40;Mecanismo de Banco de Dados&#41;](../linked-servers/linked-servers-database-engine.md) e [Servidores remotos](../../database-engine/configure-windows/remote-servers.md).</span><span class="sxs-lookup"><span data-stu-id="015e1-125">For more information, see [Linked Servers &#40;Database Engine&#41;](../linked-servers/linked-servers-database-engine.md) and [Remote Servers](../../database-engine/configure-windows/remote-servers.md).</span></span> <span data-ttu-id="015e1-126">Verifique se o logon usado para o servidor vinculado ou servidor remoto tem uma senha forte e somente as permissões descritas nesse tópico.</span><span class="sxs-lookup"><span data-stu-id="015e1-126">Ensure that the login used for the linked server or remote server has a strong password and has only the permissions described in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="015e1-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="015e1-127">See Also</span></span>  
 <span data-ttu-id="015e1-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span><span class="sxs-lookup"><span data-stu-id="015e1-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span></span>  
 <span data-ttu-id="015e1-129">[Exibir e modificar configurações de segurança de replicação](security/view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="015e1-129">[View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md) </span></span>  
 <span data-ttu-id="015e1-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="015e1-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span></span>  
 [<span data-ttu-id="015e1-131">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="015e1-131">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
