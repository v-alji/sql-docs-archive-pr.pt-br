---
title: Propriedades do Publicador Replicação do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.distpubproperties.f1
- sql12.rep.configdistwizard.pubproperties.general.f1
- sql12.rep.configdistwizard.pubproperties.pubdb.f1
- sql12.rep.configdistwizard.pubproperties.subscribers.f1
ms.assetid: 98df1aea-0406-40bf-a917-4bd80464125c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e14f82e855cc29f83859d85dfdaaf85a1bda37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680902"
---
# <a name="sql-server-replication-publisher-properties"></a><span data-ttu-id="0029f-102">Propriedades do Publicador Replicação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="0029f-102">SQL Server Replication Publisher Properties</span></span>
  <span data-ttu-id="0029f-103">Esta seção contém informações sobre as propriedades do Publicador disponíveis no distribuidor e no Publicador.</span><span class="sxs-lookup"><span data-stu-id="0029f-103">This section contains information on Publisher properties available at the Distributor and the Publisher.</span></span> 

## <a name="general"></a><span data-ttu-id="0029f-104">Geral</span><span class="sxs-lookup"><span data-stu-id="0029f-104">General</span></span>  
  <span data-ttu-id="0029f-105"> A página **Geral** da caixa de diálogo **Propriedades do Publicador** exibe informações somente leitura no Distribuidor e no banco de dados de distribuição que o Publicador usa.</span><span class="sxs-lookup"><span data-stu-id="0029f-105">The **General** page of the **Publisher Properties** dialog box displays read-only information on the Distributor and distribution database that the Publisher uses.</span></span> <span data-ttu-id="0029f-106">Para alterar o Distribuidor ou o banco de dados de um Publicador:</span><span class="sxs-lookup"><span data-stu-id="0029f-106">To change the Distributor or distribution database for a Publisher:</span></span>  
  
1.  <span data-ttu-id="0029f-107">Desabilite a publicação no Publicador.</span><span class="sxs-lookup"><span data-stu-id="0029f-107">Disable publishing on the Publisher.</span></span> <span data-ttu-id="0029f-108">Para obter mais informações, consulte [Desabilitar a publicação e a distribuição](disable-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="0029f-108">For more information, see [Disable Publishing and Distribution](disable-publishing-and-distribution.md).</span></span>    
2.  <span data-ttu-id="0029f-109">Reconfigure a publicação e a distribuição</span><span class="sxs-lookup"><span data-stu-id="0029f-109">Reconfigure publishing and distribution.</span></span> <span data-ttu-id="0029f-110">Para obter mais informações, consulte [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="0029f-110">For more information, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span></span>  

## <a name="distributor"></a><span data-ttu-id="0029f-111">Distribuidor</span><span class="sxs-lookup"><span data-stu-id="0029f-111">Distributor</span></span>
  <span data-ttu-id="0029f-112">A caixa de diálogo **Propriedades do Publicador** permite exibir e modificar propriedades associadas com a relação entre o Publicador e seu Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="0029f-112">The **Publisher Properties** dialog box allows you to view and modify properties associated with the relationship between the Publisher and its Distributor.</span></span>  
  
### <a name="options"></a><span data-ttu-id="0029f-113">Opções</span><span class="sxs-lookup"><span data-stu-id="0029f-113">Options</span></span>  
 <span data-ttu-id="0029f-114">**Conexão do Agente com o Publicador**</span><span class="sxs-lookup"><span data-stu-id="0029f-114">**Agent Connection to the Publisher**</span></span>  
 <span data-ttu-id="0029f-115">Especifique o contexto no qual os agentes seguintes fazem conexões do Distribuidor com o Publicador:</span><span class="sxs-lookup"><span data-stu-id="0029f-115">Specify the context under which the following agents make connections from the Distributor to the Publisher:</span></span>  
  
-   <span data-ttu-id="0029f-116">O Agente de Leitor de Fila para publicações transacionais, que permite assinaturas de atualização enfileiradas.</span><span class="sxs-lookup"><span data-stu-id="0029f-116">The Queue Reader Agent for transactional publications that allow queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="0029f-117">O Agente de Instantâneo e Agente de Leitor de Log para publicações Oracle.</span><span class="sxs-lookup"><span data-stu-id="0029f-117">The Snapshot Agent and Log Reader Agent for Oracle publications.</span></span>  
  
 <span data-ttu-id="0029f-118">Selecione **Representar conta de processo do agente** para efetuar conexões com o Publicador usando o contexto de conta do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows na qual esses agentes executam ou especifique **Autenticação do SQL Server**e insira um valor para **Logon** e **Senha**.</span><span class="sxs-lookup"><span data-stu-id="0029f-118">Select **Impersonate agent process account** to make connections to the Publisher using the context of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which these agents run, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> <span data-ttu-id="0029f-119">É recomendado que você selecione **Representar conta de processo do agente**.</span><span class="sxs-lookup"><span data-stu-id="0029f-119">It is recommended that you select **Impersonate agent process account**.</span></span> <span data-ttu-id="0029f-120">Para obter mais informações sobre a segurança do agente, consulte [Modelo de segurança do agente de replicação](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="0029f-120">For more information on agent security, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
 <span data-ttu-id="0029f-121">As contas do Windows nas quais esses agentes executam são especificadas no Assistente para Nova Publicação.</span><span class="sxs-lookup"><span data-stu-id="0029f-121">The Windows accounts under which these agents run are specified in the New Publication Wizard.</span></span> <span data-ttu-id="0029f-122">Essas contas podem ser alteradas:</span><span class="sxs-lookup"><span data-stu-id="0029f-122">These accounts can be changed:</span></span>  
  
-   <span data-ttu-id="0029f-123">Na caixa de diálogo **Propriedades do Distribuidor** para o Agente de Leitor de Fila.</span><span class="sxs-lookup"><span data-stu-id="0029f-123">In the **Distributor Properties** dialog box for the Queue Reader Agent.</span></span>  
  
-   <span data-ttu-id="0029f-124">Na caixa de diálogo **Propriedades de Publicação** para o Agente de Instantâneo e Agente de Leitor de Log.</span><span class="sxs-lookup"><span data-stu-id="0029f-124">In the **Publication Properties** dialog box for the Snapshot Agent and Log Reader Agent.</span></span>  
  
 <span data-ttu-id="0029f-125">**Diversos**</span><span class="sxs-lookup"><span data-stu-id="0029f-125">**Miscellaneous**</span></span>  
 <span data-ttu-id="0029f-126">As propriedades **Tipo de Publicador** e **Nome do Banco de dados de Distribuição** são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="0029f-126">The properties **Publisher Type** and **Distribution Database Name** are read-only.</span></span> <span data-ttu-id="0029f-127">A propriedade **Pasta Padrão de Instantâneo** pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="0029f-127">The property **Default Snapshot Folder** can be changed.</span></span> <span data-ttu-id="0029f-128">Para obter mais informações sobre a pasta de instantâneos, consulte [Proteger a pasta de instantâneos](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="0029f-128">For more information about the snapshot folder, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span>  
  

## <a name="publication-databases"></a><span data-ttu-id="0029f-129">Bancos de Dados de Publicação</span><span class="sxs-lookup"><span data-stu-id="0029f-129">Publication Databases</span></span>
  <span data-ttu-id="0029f-130">A página **Bancos de dados de Publicação** da caixa de diálogo **Propriedades do Publicador** permite que um usuário da função de servidor fixa **sysadmin** habilite bancos de dados para replicação.</span><span class="sxs-lookup"><span data-stu-id="0029f-130">The **Publication Databases** page of the **Publisher Properties** dialog box allows a user in the **sysadmin** fixed server role to enable databases for replication.</span></span> <span data-ttu-id="0029f-131">Habilitar um banco de dados não publica esse banco de dados, mas permite que qualquer usuário na função de banco de dados fixa **db_owner** daquele banco de dados crie uma ou mais publicações no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0029f-131">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications on the database.</span></span>  
  
### <a name="options"></a><span data-ttu-id="0029f-132">Opções</span><span class="sxs-lookup"><span data-stu-id="0029f-132">Options</span></span>  
 <span data-ttu-id="0029f-133">**Transacional.**</span><span class="sxs-lookup"><span data-stu-id="0029f-133">**Transactional**</span></span>  
 <span data-ttu-id="0029f-134">Marque essa caixa de seleção para permitir que usuários na função de banco de dados fixa **db_owner** criem publicações de instantâneo ou transacionais no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0029f-134">Select this check box to allow users in the **db_owner** fixed database role to create snapshot publications or transactional publications in the database.</span></span> 
  
 <span data-ttu-id="0029f-135">**Mesclagem**</span><span class="sxs-lookup"><span data-stu-id="0029f-135">**Merge**</span></span>  
 <span data-ttu-id="0029f-136">Marque essa caixa de seleção para permitir que usuários na função de banco de dados fixa **db_owner** criem publicações de mesclagem no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0029f-136">Select this check box to allow users in the **db_owner** fixed database role to create merge publications in the database.</span></span>  

## <a name="subscribers"></a><span data-ttu-id="0029f-137">Publicadores</span><span class="sxs-lookup"><span data-stu-id="0029f-137">Subscribers</span></span>

  <span data-ttu-id="0029f-138">A página **Assinantes** da caixa de diálogo **Propriedades do Editor** é usada por Editores que executam versões do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0029f-138">The **Subscribers** page of the **Publisher Properties** dialog box is used for Publishers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="0029f-139">A página permite habilitar Publicadores a receber dados de publicações neste Publicador.</span><span class="sxs-lookup"><span data-stu-id="0029f-139">The page allows you to enable Subscribers to receive data from publications on this Publisher.</span></span> <span data-ttu-id="0029f-140">Permitir que um Assinante receba dados deste Publicador não cria assinaturas para publicações neste Publicador.</span><span class="sxs-lookup"><span data-stu-id="0029f-140">Enabling a Subscriber to receive data from this Publisher does not create subscriptions to publications on this Publisher.</span></span> <span data-ttu-id="0029f-141">Para criar uma assinatura, você deve usar o Assistente para Nova Assinatura.</span><span class="sxs-lookup"><span data-stu-id="0029f-141">To create a subscription, you must use the New Subscription Wizard.</span></span>  
  
### <a name="options"></a><span data-ttu-id="0029f-142">Opções</span><span class="sxs-lookup"><span data-stu-id="0029f-142">Options</span></span>  
 <span data-ttu-id="0029f-143">**Publicadores**</span><span class="sxs-lookup"><span data-stu-id="0029f-143">**Subscribers**</span></span>  
 <span data-ttu-id="0029f-144">A grade de propriedade **Assinantes** mostra Assinantes habilitados a receber dados de publicações neste Publicador.</span><span class="sxs-lookup"><span data-stu-id="0029f-144">The **Subscribers** property grid shows Subscribers that are enabled to receive data from publications on this Publisher.</span></span> <span data-ttu-id="0029f-145">Clique no botão de propriedades **(...)** próximo ao Assinante para exibir e definir propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="0029f-145">Click the properties button (**...**) next to a Subscriber to view and set additional properties.</span></span>  
  
 <span data-ttu-id="0029f-146">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="0029f-146">**Add**</span></span>  
 <span data-ttu-id="0029f-147">Clique em **Adicionar** para adicionar um Assinante e depois clique em **Adicionar Assinante SQL Server** ou **Adicionar Assinante não SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0029f-147">Click **Add** to add a Subscriber, and then click **Add SQL Server Subscriber** or **Add Non-SQL Server Subscriber**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0029f-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0029f-148">See Also</span></span>  
 [<span data-ttu-id="0029f-149">Exibir e modificar propriedades de Publicador e Distribuidor</span><span class="sxs-lookup"><span data-stu-id="0029f-149">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  
  
