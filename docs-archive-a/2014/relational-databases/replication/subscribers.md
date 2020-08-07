---
title: Assinantes | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscribers.f1
helpviewer_keywords:
- Subscribers [SQL Server replication]
ms.assetid: 43fb2454-c220-4d25-a826-83c332eb00d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c5281a53b755bc171cdf96e7856e38ee6a54a1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571924"
---
# <a name="subscribers"></a><span data-ttu-id="0fcc4-102">Publicadores</span><span class="sxs-lookup"><span data-stu-id="0fcc4-102">Subscribers</span></span>
  <span data-ttu-id="0fcc4-103">Especifique os [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assinantes ou não que receberão uma assinatura para a publicação selecionada.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-103">Specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers that will receive a subscription to the selected publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0fcc4-104">Opções</span><span class="sxs-lookup"><span data-stu-id="0fcc4-104">Options</span></span>  
 <span data-ttu-id="0fcc4-105">**Publicadores**</span><span class="sxs-lookup"><span data-stu-id="0fcc4-105">**Subscribers**</span></span>  
 <span data-ttu-id="0fcc4-106">Marque a caixa de seleção na grade para habilitar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondente ou a fonte de dados não[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como um Assinante da publicação escolhida na página **Publicação** .</span><span class="sxs-lookup"><span data-stu-id="0fcc4-106">Select the check box in the grid to enable the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source as a Subscriber to the publication chosen on the **Publication** page.</span></span> <span data-ttu-id="0fcc4-107">Se o Assinante não estiver na lista, clique em **Adicionar Assinante** ou **Adicionar Assinante SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-107">If the Subscriber is not listed, click **Add Subscriber** or **Add SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="0fcc4-108">**Banco de dados de assinatura**</span><span class="sxs-lookup"><span data-stu-id="0fcc4-108">**Subscription database**</span></span>  
 <span data-ttu-id="0fcc4-109">As informações exibidas e as informações exibidas nessa coluna dependem do tipo de Assinante listado na coluna **Assinantes** :</span><span class="sxs-lookup"><span data-stu-id="0fcc4-109">The information displayed in and actions available from this column depend on the type of Subscriber listed in the **Subscribers** column:</span></span>  
  
-   <span data-ttu-id="0fcc4-110">Para Assinantes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , selecione um banco de dados de assinatura da lista **Banco de Dados de Assinatura** para criar um novo banco de dados selecionando o comando **Novo banco de dados** na mesma lista.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-110">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, select a subscription database from the **Subscription Database** list or create a new database by selecting the **New database** command from the same list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0fcc4-111">Se você estiver habilitando o Publicador como um Assinante, o banco de dados de assinatura deverá ser diferente do banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-111">If you are enabling the Publisher as a Subscriber, the subscription database must be different from the publication database.</span></span>  
  
-   <span data-ttu-id="0fcc4-112">Para Assinantes não[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o banco de dados de assinatura não é exibido.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-112">For non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, the subscription database is not displayed.</span></span> <span data-ttu-id="0fcc4-113">Especifique o banco de dados, juntamente com outras informações de conexão, no campo **Nome da fonte de dados** da caixa de diálogo **Adicionar não SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="0fcc4-113">Specify the database, along with other connection information, in the **Data source name** field of the **Add Non-SQL Server** dialog box.</span></span> <span data-ttu-id="0fcc4-114">Essa caixa de diálogo está disponível clicando em **Adicionar Assinante** e depois clicando em **Adicionar Assinante não SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-114">This dialog box is available by clicking **Add Subscriber** and then clicking **Add Non-SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="0fcc4-115">**Adicionar Assinante**</span><span class="sxs-lookup"><span data-stu-id="0fcc4-115">**Add Subscriber**</span></span>  
 <span data-ttu-id="0fcc4-116">Adicione um servidor à lista de servidores que podem ser habilitados como Assinantes.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-116">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="0fcc4-117">Esse botão é exibido quando todas as condições seguintes são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="0fcc4-117">This button is displayed when all of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="0fcc4-118">A publicação selecionada é uma publicação de instantâneo ou transacional que não oferece suporte a assinaturas de atualização.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-118">The publication you selected is a snapshot or transactional publication that does not support updating subscriptions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0fcc4-119">Se a publicação que você estiver assinando tiver assinaturas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e a publicação ainda não tiver sido habilitada como Assinantes não[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , não será possível adicionar uma assinatura não[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0fcc4-119">If the publication you are subscribing to has [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscriptions and the publication is not already enabled for non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, you cannot add a non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscription.</span></span>  
  
-   <span data-ttu-id="0fcc4-120">A assinatura é uma assinatura push.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-120">The subscription is a push subscription.</span></span>  
  
-   <span data-ttu-id="0fcc4-121">O Publicador da publicação selecionada é o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou posterior.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-121">The Publisher of the selected publication is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later.</span></span>  
  
 <span data-ttu-id="0fcc4-122">Clicar em **Adicionar Assinante** mostra um menu com duas opções: **Adicionar Assinante SQL Server** e **Adicionar Assinante não SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-122">Clicking **Add Subscriber** shows a menu with two choices: **Add SQL Server Subscriber** and **Add Non-SQL Server Subscriber**.</span></span> <span data-ttu-id="0fcc4-123">Clique em **Adicionar Assinante não SQL Server** para adicionar um Assinante Oracle ou IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-123">Click **Add Non-SQL Server Subscriber** to add an Oracle or IBM DB2 Subscriber.</span></span>  
  
 <span data-ttu-id="0fcc4-124">**Adicionar Assinante SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0fcc4-124">**Add SQL Server Subscriber**</span></span>  
 <span data-ttu-id="0fcc4-125">Adicione um servidor à lista de servidores que podem ser habilitados como Assinantes.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-125">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="0fcc4-126">Esse botão é exibido quando uma ou mais das condições seguintes são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="0fcc4-126">This button is displayed when one or more of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="0fcc4-127">A publicação selecionada é uma publicação de mesclagem, de instantâneo ou transacional que não oferece suporte a assinaturas de atualização.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-127">The publication you selected is a merge publication, or a snapshot or transactional publication that supports updating subscriptions.</span></span>  
  
-   <span data-ttu-id="0fcc4-128">A assinatura é uma assinatura pull.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-128">The subscription is a pull subscription.</span></span>  
  
-   <span data-ttu-id="0fcc4-129">O Editor da publicação selecionada é anterior ao [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fcc4-129">The Publisher of the selected publication is earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="0fcc4-130">Para versões anteriores, o botão só será exibido se uma ou mais das condições seguintes forem verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="0fcc4-130">For earlier versions, the button is displayed only if one or more of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="0fcc4-131">Você é um membro da função de servidor fixa **sysadmin** no Publicador.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-131">You are a member of the **sysadmin** fixed server role at the Publisher.</span></span>  
  
    -   <span data-ttu-id="0fcc4-132">O Assinante foi adicionado na página **Assinante** da caixa de diálogo **Propriedades do Publicador** .</span><span class="sxs-lookup"><span data-stu-id="0fcc4-132">The Subscriber has been added on the **Subscribers** page of the **Publisher Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="0fcc4-133">A publicação permite assinaturas anônimas.</span><span class="sxs-lookup"><span data-stu-id="0fcc4-133">The publication allows anonymous subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fcc4-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0fcc4-134">See Also</span></span>  
 <span data-ttu-id="0fcc4-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="0fcc4-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="0fcc4-136">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="0fcc4-136">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="0fcc4-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="0fcc4-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="0fcc4-138">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="0fcc4-138">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
