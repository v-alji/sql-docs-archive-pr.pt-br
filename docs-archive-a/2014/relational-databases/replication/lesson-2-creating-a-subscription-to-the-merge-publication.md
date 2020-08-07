---
title: 'Lição 2: Criando uma assinatura na publicação de mesclagem | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 06722baa-9065-443e-b1d5-99036cf89074
author: rothja
ms.author: jroth
ms.openlocfilehash: 2ca4f9cdf9c40d80b428d65b4201be61c2ea3eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575075"
---
# <a name="lesson-2-creating-a-subscription-to-the-merge-publication"></a><span data-ttu-id="1dbbe-102">Lição 2: Criando uma assinatura na publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="1dbbe-102">Lesson 2: Creating a Subscription to the Merge Publication</span></span>
  <span data-ttu-id="1dbbe-103">Nesta lição, você criará uma assinatura usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1dbbe-103">In this lesson, you will create the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="1dbbe-104">Em seguida, definirá permissões no banco de dados da assinatura e gerará manualmente o instantâneo de dados filtrados para a nova assinatura.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-104">You will then set permissions on the subscription database and manually generate the filtered data snapshot for the new subscription.</span></span> <span data-ttu-id="1dbbe-105">Esta lição exige que você tenha concluído a lição anterior, [Lição 1: Publicando dados usando a replicação de mesclagem](lesson-1-publishing-data-using-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="1dbbe-105">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Merge Replication](lesson-1-publishing-data-using-merge-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="1dbbe-106">Para criar a assinatura</span><span class="sxs-lookup"><span data-stu-id="1dbbe-106">To create the subscription</span></span>  
  
1.  <span data-ttu-id="1dbbe-107">Conecte-se ao Assinante no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda o nó de servidor, expanda a pasta **Replicação** , clique com o botão direito do mouse na pasta **Assinaturas Locais** e clique em **Novas Assinaturas**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, expand the **Replication** folder, right-click the **Local Subscriptions** folder, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="1dbbe-108">O Assistente para Nova Assinatura é iniciado.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-108">The New Subscription Wizard launches.</span></span>  
  
2.  <span data-ttu-id="1dbbe-109">Na página **Publicação** , clique em **Encontrar Publicador SQL Server** na lista **Publicador** .</span><span class="sxs-lookup"><span data-stu-id="1dbbe-109">On the **Publication** page, click **Find SQL Server Publisher** in the **Publisher** list.</span></span>  
  
3.  <span data-ttu-id="1dbbe-110">Na caixa de diálogo **Conectar ao Servidor** , insira o nome da instância do Publicador na caixa **Nome do servidor** e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-110">In the **Connect to Server** dialog box, enter the name of the Publisher instance in the **Server name** box, and click **Connect**.</span></span>  
  
4.  <span data-ttu-id="1dbbe-111">Clique em **AdvWorksSalesOrdersMerge**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-111">Click **AdvWorksSalesOrdersMerge**, and click **Next**.</span></span>  
  
5.  <span data-ttu-id="1dbbe-112">Na página Local do Agente de Mesclagem, clique em **Executar cada agente em seu Assinante**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-112">On the Merge Agent Location page, click **Run each agent at its Subscriber**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="1dbbe-113">Na página Assinantes, selecione o nome da instância do servidor Assinante e, em **Banco de Dados de Assinatura**, selecione **\<New Database>** na lista.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-113">On the Subscribers page, select the instance name of the Subscriber server, and under **Subscription Database**, select **\<New Database>** from the list.</span></span>  
  
7.  <span data-ttu-id="1dbbe-114">Na caixa de diálogo **Novo Banco de Dados** , insira **SalesOrdersReplica** na caixa **Nome do banco de dados** , clique em **OK**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-114">In the **New Database** dialog box, enter **SalesOrdersReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="1dbbe-115">Na página segurança do Agente de Mesclagem, clique no botão de reticências (**...**), insira \<_Machine_Name> _**\ repl_merge** na caixa **conta de processo** , forneça a senha dessa conta, clique em **OK**, em **Avançar**e em **Avançar** novamente.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-115">On the Merge Agent Security page, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_merge** in the **Process account** box, supply the password for this account, click **OK**, click **Next**, and then click **Next** again.</span></span>  
  
9. <span data-ttu-id="1dbbe-116">Na página Inicializar Assinaturas, selecione **Na primeira sincronização** na lista **Inicializar Quando** , clique em **Avançar**e em **Avançar** novamente.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-116">On the Initialize Subscriptions page, select **At first synchronization** from the **Initialize When** list, click **Next**, and then click **Next** again.</span></span>  
  
10. <span data-ttu-id="1dbbe-117">Na página valores de HOST_NAME, insira um valor de `adventure-works\pamela0` na caixa **valor de HOST_NAME** e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-117">On the HOST_NAME Values page, enter a value of `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="1dbbe-118">Clique em **Concluir** novamente. Após a criação da assinatura, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-118">Click **Finish** again, and after the subscription is created, click **Close**.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="1dbbe-119">Definindo permissões de banco de dados no Assinante</span><span class="sxs-lookup"><span data-stu-id="1dbbe-119">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="1dbbe-120">Conecte-se ao Assinante no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda **Bancos de Dados**, **SalesOrdersReplica**e **Segurança**, clique com o botão direito do mouse em **Usuários**e selecione **Novo Usuário**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **SalesOrdersReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="1dbbe-121">Na página **geral** , digite \<_Machine_Name> _ **\ repl_merge** na caixa **nome de usuário** , clique no botão de reticências (**...**), clique em **procurar**, \<_Machine_Name> selecione _ **\ repl_merge**, clique em **OK**, em **verificar nomes**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-121">On the **General** page, enter \<_Machine_Name>_**\repl_merge** in the **User name** box, click the ellipsis (**...**) button, click **Browse**, select \<_Machine_Name>_**\repl_merge**, click **OK**, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1dbbe-122">Em **Associação à função do banco de dados**, selecione **db_owner**e clique em **OK** para criar o usuário.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-122">In **Database role membership**, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-create-the-filtered-data-snapshot-for-the-subscription"></a><span data-ttu-id="1dbbe-123">Para criar o instantâneo de dados filtrados para a assinatura</span><span class="sxs-lookup"><span data-stu-id="1dbbe-123">To create the filtered data snapshot for the subscription</span></span>  
  
1.  <span data-ttu-id="1dbbe-124">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , expanda o nó do servidor e expanda a pasta **replicação** .</span><span class="sxs-lookup"><span data-stu-id="1dbbe-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="1dbbe-125">Na pasta **Publicações Locais** , clique com o botão direito do mouse na publicação **AdvWorksSalesOrdersMerge** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-125">In the **Local Publications** folder, right-click the **AdvWorksSalesOrdersMerge** publication, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="1dbbe-126">A caixa de diálogo **Propriedades da Publicação** é exibida.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-126">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="1dbbe-127">Selecione a página **Partições de Dados** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-127">Select the **Data Partitions** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="1dbbe-128">Na caixa de diálogo **Adicionar partição de dados** , digite `adventure-works\pamela0` a caixa **valor de HOST_NAME** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-128">In the **Add Data Partition** dialog box, type `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="1dbbe-129">Selecione a partição recém-adicionada, clique em **Gerar os instantâneos selecionados agora**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-129">Select the newly added partition, click **Generate the selected snapshots now**, and then click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1dbbe-130">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="1dbbe-130">Next Steps</span></span>  
 <span data-ttu-id="1dbbe-131">Você criou com êxito uma assinatura para a publicação mesclada e gerou o instantâneo filtrado para a partição de dados da nova assinatura, de modo que ele esteja disponível no momento da inicialização das assinaturas.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-131">You have successfully created a subscription to the merge publication and generated the filtered snapshot for the new subscription's data partition so that it will be available when the subscription is initialized.</span></span> <span data-ttu-id="1dbbe-132">Em seguida, conceda direitos ao Merge Agent no banco de dados de assinatura e execute o Merge Agent para iniciar a sincronização e iniciar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="1dbbe-132">Next, you will grant rights to the Merge Agent on the subscription database and run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="1dbbe-133">Consulte [Lição 3: Sincronizando a assinatura com a publicação de mesclagem](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="1dbbe-133">See [Lesson 3: Synchronizing the Subscription to the Merge Publication](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dbbe-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1dbbe-134">See Also</span></span>  
 <span data-ttu-id="1dbbe-135">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="1dbbe-135">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="1dbbe-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="1dbbe-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="1dbbe-137">Snapshots for Merge Publications with Parameterized Filters</span><span class="sxs-lookup"><span data-stu-id="1dbbe-137">Snapshots for Merge Publications with Parameterized Filters</span></span>](snapshots-for-merge-publications-with-parameterized-filters.md)  
  
  
