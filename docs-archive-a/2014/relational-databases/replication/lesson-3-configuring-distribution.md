---
title: 'Lição 3: Configurando a distribuição | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f248984a-0b59-4c2f-a56d-31f8dafe72b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 52b284b6186e599b7afe73bd37ab0a8348ec38da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684654"
---
# <a name="lesson-3-configuring-distribution"></a><span data-ttu-id="bbf2f-102">Lição 3: Configurando a distribuição</span><span class="sxs-lookup"><span data-stu-id="bbf2f-102">Lesson 3: Configuring Distribution</span></span>
  <span data-ttu-id="bbf2f-103">Nesta lição você configurará a distribuição no Publicador e definirá as permissões necessárias nos bancos de dados de publicação e distribuição.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-103">In this lesson, you will configure distribution at the Publisher and set the required permissions on the publication and distribution databases.</span></span> <span data-ttu-id="bbf2f-104">Se você já tiver configurado o Distribuidor, antes de começar a lição será necessário desabilitar primeiramente a publicação e a distribuição.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-104">If you have already configured the Distributor, you must first disable publishing and distribution before you begin this lesson.</span></span> <span data-ttu-id="bbf2f-105">Não faça isto se for preciso manter uma topologia de replicação existente.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-105">Do not do this if you must retain an existing replication topology.</span></span>  
  
 <span data-ttu-id="bbf2f-106">A configuração de um Publicador com um Distribuidor remoto está fora do escopo deste tutorial.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-106">Configuring a Publisher with a remote Distributor is outside the scope of this tutorial.</span></span>  
  
### <a name="configuring-distribution-at-the-publisher"></a><span data-ttu-id="bbf2f-107">Configurando a distribuição no Publicador</span><span class="sxs-lookup"><span data-stu-id="bbf2f-107">Configuring distribution at the Publisher</span></span>  
  
1.  <span data-ttu-id="bbf2f-108">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="bbf2f-109">Clique com o botão direito do mouse na pasta **Replicação** e clique em **Configurar Distribuição**.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-109">Right-click the **Replication** folder and click **Configure Distribution**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bbf2f-110">Se você se conectou ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando **localhost** em vez do nome de servidor real, receberá um aviso de que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode se conectar ao **'localhost'** do servidor.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-110">If you have connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using **localhost** rather than the actual server name you will be prompted with a warning that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is unable to connect to server **'localhost'**.</span></span> <span data-ttu-id="bbf2f-111">Clique em **OK** na caixa de diálogo de aviso.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-111">Click **OK** on the warning dialog.</span></span> <span data-ttu-id="bbf2f-112">Na caixa de diálogo **Conectar ao Servidor** , altere o **Nome do Servidor** de **localhost** para o nome do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-112">In the **Connect to Server** dialog change the **Server name** from **localhost** to the name of your server.</span></span> <span data-ttu-id="bbf2f-113">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-113">Click **Connect**.</span></span>  
  
     <span data-ttu-id="bbf2f-114">O Assistente para Configuração de Distribuição é iniciado.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-114">The Distribution Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="bbf2f-115">Na página **distribuidor** , selecione **'** _\<ServerName>_ **' atuará como seu próprio distribuidor; SQL Server criará um banco de dados de distribuição e um log**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-115">On the **Distributor** page, select **'**_\<ServerName>_**' will act as its own Distributor; SQL Server will create a distribution database and log**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="bbf2f-116">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não estiver sendo executado, na página inicial do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Agent**, selecione **Sim** para configurar o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para iniciar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-116">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not running, on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Agent Start** page, select **Yes**, configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically.</span></span> <span data-ttu-id="bbf2f-117">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-117">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="bbf2f-118">Insira **\\\\** \<_Machine_Name> _**\repldata** na caixa de texto **pasta de instantâneo** , em que \<*Machine_Name> \* é o nome do Publicador e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-118">Enter **\\\\**\<_Machine_Name>_**\repldata** in the **Snapshot folder** text box, where \<*Machine_Name>\* is the name of the Publisher, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="bbf2f-119">Aceite os valores padrão das páginas restantes do assistente.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-119">Accept the default values on the remaining pages of the wizard.</span></span>  
  
7.  <span data-ttu-id="bbf2f-120">Clique em **Concluir** para ativar a distribuição.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-120">Click **Finish** to enable distribution.</span></span>  
  
### <a name="setting-database-permissions-at-the-publisher"></a><span data-ttu-id="bbf2f-121">Definindo permissões de banco de dados no Publicador</span><span class="sxs-lookup"><span data-stu-id="bbf2f-121">Setting database permissions at the Publisher</span></span>  
  
1.  <span data-ttu-id="bbf2f-122">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , expanda **segurança**, clique com o botão direito do mouse em **logons**e selecione **novo logon**.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Security**, right-click **Logins**, and then select **New Login**.</span></span>  
  
2.  <span data-ttu-id="bbf2f-123">Na página **geral** , clique em **Pesquisar**, insira \<_Machine_Name> _**\ repl_snapshot** na caixa **Inserir o nome do objeto a ser selecionado** , em que \<*Machine_Name> \* é o nome do servidor do Publicador local, clique em **verificar nomes**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-123">On the **General** page, click **Search**, enter \<_Machine_Name>_**\repl_snapshot** in the **Enter the object name to select** box, where \<*Machine_Name>\* is the name of the local Publisher server, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="bbf2f-124">Na página **mapeamento de usuário** , na lista **Usuários mapeados para este logon** , selecione a **distribuição** e os [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-124">On the **User Mapping** page, in the **Users mapped to this login** list select both the **distribution** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] databases.</span></span>  
  
     <span data-ttu-id="bbf2f-125">Na lista **associação da função de banco de dados** , selecione a `db_owner` função para o logon para ambos os bancos.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-125">In the **Database role membership** list select the `db_owner` role for the login for both databases.</span></span>  
  
4.  <span data-ttu-id="bbf2f-126">Clique em **OK** para criar o logon.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-126">Click **OK** to create the login.</span></span>  
  
5.  <span data-ttu-id="bbf2f-127">Repita as Etapas 1a 4 para criar um logon para a conta repl_logreader local.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-127">Repeat steps 1-4 to create a login for the local repl_logreader account.</span></span> <span data-ttu-id="bbf2f-128">Esse logon também deve ser mapeado para os usuários que são membros da `db_owner` função de banco de dados fixa na **distribuição** e no bancos de dados **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="bbf2f-128">This login must also be mapped to users that are members of the `db_owner` fixed database role in the **distribution** and **AdventureWorks** databases.</span></span>  
  
6.  <span data-ttu-id="bbf2f-129">Repita as Etapas 1a 4 para criar um logon para a conta repl_distribution local.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-129">Repeat steps 1-4 to create a login for the local repl_distribution account.</span></span> <span data-ttu-id="bbf2f-130">Esse logon deve ser mapeado para um usuário que seja membro da função de `db_owner` banco de dados fixa no banco de dados de **distribuição** .</span><span class="sxs-lookup"><span data-stu-id="bbf2f-130">This login must be mapped to a user that is a member of the `db_owner` fixed database role in the **distribution** database.</span></span>  
  
7.  <span data-ttu-id="bbf2f-131">Repita as etapas 1a 4 para criar um logon para a conta repl_merge local.</span><span class="sxs-lookup"><span data-stu-id="bbf2f-131">Repeat steps 1-4 to create a login for the local repl_merge account.</span></span> <span data-ttu-id="bbf2f-132">Esse logon deve ter mapeamentos de usuário nos bancos de dados **distribuição** e **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="bbf2f-132">This login must have user mappings in the **distribution** and **AdventureWorks** databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbf2f-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bbf2f-133">See Also</span></span>  
 <span data-ttu-id="bbf2f-134">[Configurar Distribuição](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="bbf2f-134">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="bbf2f-135">Modelo de segurança do agente de replicação</span><span class="sxs-lookup"><span data-stu-id="bbf2f-135">Replication Agent Security Model</span></span>](security/replication-agent-security-model.md)  
  
  
