---
title: 'Lição 2: Criando uma assinatura na publicação transacional | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 5995b7d2-7c06-46f5-b96c-2bee879bcda2
author: rothja
ms.author: jroth
ms.openlocfilehash: dbf40fa259302dffdd6c0b8e8717b7c35b0cf92d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569869"
---
# <a name="lesson-2-creating-a-subscription-to-the-transactional-publication"></a><span data-ttu-id="0430b-102">Lição 2: Criando uma assinatura na publicação transacional</span><span class="sxs-lookup"><span data-stu-id="0430b-102">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>
  <span data-ttu-id="0430b-103">Nessa lição, você criará uma assinatura usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0430b-103">In this lesson, you will create a subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0430b-104">Esta lição exige que você tenha concluído a lição anterior, [Lição 1: Publicando dados usando a replicação transacional](lesson-1-publishing-data-using-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="0430b-104">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Transactional Replication](lesson-1-publishing-data-using-transactional-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="0430b-105">Para criar a assinatura</span><span class="sxs-lookup"><span data-stu-id="0430b-105">To create the subscription</span></span>  
  
1.  <span data-ttu-id="0430b-106">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , expanda o nó do servidor e expanda a pasta **replicação** .</span><span class="sxs-lookup"><span data-stu-id="0430b-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="0430b-107">Na pasta **Publicações Locais** , clique com o botão direito do mouse na publicação **AdvWorksProductTrans** e clique em **Novas Assinaturas**.</span><span class="sxs-lookup"><span data-stu-id="0430b-107">In the **Local Publications** folder, right-click the **AdvWorksProductTrans** publication, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="0430b-108">O Assistente para Nova Assinatura é iniciado.</span><span class="sxs-lookup"><span data-stu-id="0430b-108">The New Subscription Wizard launches.</span></span>  
  
3.  <span data-ttu-id="0430b-109">Na página Publicação, selecione **AdvWorksProductTrans**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0430b-109">On the Publication page, select **AdvWorksProductTrans**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="0430b-110">Na página Local do Distribution Agent, selecione **Executar todos os agentes no Distribuidor**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0430b-110">On the Distribution Agent Location page, select **Run all agents at the Distributor**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="0430b-111">Na página Assinantes, se o nome da instância do Assinante não estiver exibido, clique em **Adicionar Assinante**, clique em **Adicionar Assinante de SQL Server**, digite o nome da instância do Assinante na caixa de diálogo **Conectar ao Servidor** e em seguida clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="0430b-111">On the Subscribers page, if the name of the Subscriber instance is not displayed, click **Add Subscriber**, click **Add SQL Server Subscriber**, enter the Subscriber instance name in the **Connect to Server** dialog box, and then click **Connect**.</span></span>  
  
6.  <span data-ttu-id="0430b-112">Na página assinantes, selecione o nome da instância do servidor do assinante e selecione **\<New Database>** em **banco de dados de assinatura**.</span><span class="sxs-lookup"><span data-stu-id="0430b-112">On the Subscribers page, select the instance name of the Subscriber server, and select **\<New Database>** under **Subscription Database**.</span></span>  
  
7.  <span data-ttu-id="0430b-113">Na caixa de diálogo **Novo Banco de Dados** , digite **ProductReplica** na caixa **Nome do Banco de Dados** , clique em **OK**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0430b-113">On the **New Database** dialog box, enter **ProductReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="0430b-114">Na caixa de diálogo **agente de distribuição segurança** , clique no botão de reticências (**...**), insira \<_Machine_Name> _**\ repl_distribution** na caixa **conta de processo** , digite a senha dessa conta, clique em **OK**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0430b-114">In the **Distribution Agent Security** dialog box, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_distribution** in the **Process account** box, enter the password for this account, click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="0430b-115">Clique em **Concluir** para aceitar os valores padrão nas páginas remanescentes e concluir o assistente.</span><span class="sxs-lookup"><span data-stu-id="0430b-115">Click **Finish** to accept the default values on the remaining pages and complete the wizard.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="0430b-116">Definindo permissões de banco de dados no Assinante</span><span class="sxs-lookup"><span data-stu-id="0430b-116">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="0430b-117">Conecte-se ao Assinante no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]; expanda **Databases**, **ProductReplica**e **Security**; clique com o botão direito do mouse em **Usuários**e selecione **Novo Usuário**.</span><span class="sxs-lookup"><span data-stu-id="0430b-117">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **ProductReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="0430b-118">Na página **Geral** , na lista **Tipo de usuário** , selecione **Usuário do Windows**.</span><span class="sxs-lookup"><span data-stu-id="0430b-118">On the **General** page, in the **User type** list, select **Windows user**.</span></span>  
  
3.  <span data-ttu-id="0430b-119">Selecione a caixa **nome de usuário** e clique no botão de reticências (...), na caixa **Inserir o nome do objeto a ser selecionado** , digite <Machine_Name>**\ Repl_distribution**, clique em **verificar nomes**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0430b-119">Select the **User name** box and click the ellipsis (...) button, in the **Enter the object name to select** box type <Machine_Name>**\repl_distribution**, click **Check Names**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="0430b-120">Na página **Associação** , na área **Associação à função do banco de dados** , selecione **db_owner**e clique em **OK** para criar o usuário.</span><span class="sxs-lookup"><span data-stu-id="0430b-120">On the **Membership** page, in **Database role membership** area, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-view-the-synchronization-status-of-the-subscription"></a><span data-ttu-id="0430b-121">Para exibir o status da sincronização da assinatura</span><span class="sxs-lookup"><span data-stu-id="0430b-121">To view the synchronization status of the subscription</span></span>  
  
1.  <span data-ttu-id="0430b-122">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , expanda o nó do servidor e expanda a pasta **replicação** .</span><span class="sxs-lookup"><span data-stu-id="0430b-122">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="0430b-123">Na pasta **Assinaturas Locais** , expanda a publicação **AdvWorksProductTrans** , clique com o botão direito do mouse na assinatura no banco de dados **ProductReplica** e clique em **Exibir Status da Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="0430b-123">In the **Local Publications** folder, expand the **AdvWorksProductTrans** publication, right-click the subscription in the **ProductReplica** database, and then click **View Synchronization Status**.</span></span>  
  
     <span data-ttu-id="0430b-124">O status atual da sincronização da assinatura é exibido.</span><span class="sxs-lookup"><span data-stu-id="0430b-124">The current synchronization status of the subscription is displayed.</span></span>  
  
3.  <span data-ttu-id="0430b-125">Se a assinatura não for visível sob **AdvWorksProductTrans**, pressione F5 para atualizar a lista.</span><span class="sxs-lookup"><span data-stu-id="0430b-125">If the subscription is not visible under **AdvWorksProductTrans**, press F5 to refresh the list.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0430b-126">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="0430b-126">Next Steps</span></span>  
 <span data-ttu-id="0430b-127">Você criou com êxito uma assinatura para publicação transacional.</span><span class="sxs-lookup"><span data-stu-id="0430b-127">You have successfully created a subscription to the transactional publication.</span></span> <span data-ttu-id="0430b-128">Como o Distribution Agent dessa assinatura executa continuamente, a assinatura é inicializada quando ela é criada.</span><span class="sxs-lookup"><span data-stu-id="0430b-128">Because the Distribution Agent for this subscription runs continuously, the subscription is initialized when it is created.</span></span> <span data-ttu-id="0430b-129">Em seguida, você usará os tokens de rastreamento para verificar se as alterações estão sendo replicadas para o Assinante e para determinar a latência.</span><span class="sxs-lookup"><span data-stu-id="0430b-129">Next, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency.</span></span> <span data-ttu-id="0430b-130">Consulte [Lesson 3: Validating the Subscription and Measuring Latency](lesson-3-validating-the-subscription-and-measuring-latency.md).</span><span class="sxs-lookup"><span data-stu-id="0430b-130">See [Lesson 3: Validating the Subscription and Measuring Latency](lesson-3-validating-the-subscription-and-measuring-latency.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0430b-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0430b-131">See Also</span></span>  
 <span data-ttu-id="0430b-132">[Inicializar uma assinatura com um instantâneo](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="0430b-132">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="0430b-133">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="0430b-133">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="0430b-134">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="0430b-134">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
