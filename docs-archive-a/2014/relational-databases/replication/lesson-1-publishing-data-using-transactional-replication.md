---
title: 'Lição 1: Publicando dados que usam a replicação transacional | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 9c55aa3c-4664-41fc-943f-e817c31aad5e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce20f4ed8863ede34c8709d2b77bf032e7d14a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679292"
---
# <a name="lesson-1-publishing-data-using-transactional-replication"></a><span data-ttu-id="19c87-102">Lição 1: publicando dados que usam replicação transacional</span><span class="sxs-lookup"><span data-stu-id="19c87-102">Lesson 1: Publishing Data Using Transactional Replication</span></span>
  <span data-ttu-id="19c87-103"> Nesta lição, você aprenderá a criar uma publicação transacional usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para publicar um subconjunto filtrado da tabela **Produto** no banco de dados de exemplo do [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19c87-103">In this lesson, you will create a transactional publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a filtered subset of the **Product** table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="19c87-104">Você também adicionará o logon do SQL Server usado pelo Distribution Agent à PAL (lista de acesso à publicação).</span><span class="sxs-lookup"><span data-stu-id="19c87-104">You will also add the SQL Server login used by the Distribution Agent to the publication access list (PAL).</span></span> <span data-ttu-id="19c87-105">Antes de iniciar este tutorial, você deverá ter completado o tutorial anterior, [Preparando o servidor para replicação](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="19c87-105">Before starting this tutorial, you should have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="19c87-106">Para criar uma publicação e definir artigos</span><span class="sxs-lookup"><span data-stu-id="19c87-106">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="19c87-107">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="19c87-107">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="19c87-108">Expanda a pasta **Replicação** , clique com o botão direito do mouse na pasta **Publicações Locais** e clique em **Nova Publicação**.</span><span class="sxs-lookup"><span data-stu-id="19c87-108">Expand the **Replication** folder, right-click the **Local Publications** folder, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="19c87-109">O Assistente de Configuração de Publicação é inicializado.</span><span class="sxs-lookup"><span data-stu-id="19c87-109">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="19c87-110">Na página Banco de Dados de Publicação, selecione [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19c87-110">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="19c87-111">Na página Tipo de Publicação, selecione **Publicação transacional**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19c87-111">On the Publication Type page, select **Transactional publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="19c87-112">Na página Artigos, expanda o nó **Tabelas** , selecione a caixa de seleção **Produto** , expanda **Produto** e desmarque as caixas de seleção **ListPrice** e **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="19c87-112">On the Articles page, expand the **Tables** node, select the **Product** check box, then expand **Product** and clear the **ListPrice** and **StandardCost** check boxes.</span></span> <span data-ttu-id="19c87-113">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19c87-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="19c87-114">Na página Filtrar Linhas da Tabela, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="19c87-114">On the Filter Table Rows page, click **Add**.</span></span>  
  
7.  <span data-ttu-id="19c87-115">Na caixa de diálogo **Adicionar Filtro** , clique na coluna **SafetyStockLevel** , clique na seta para a direita para adicionar a coluna à cláusula WHERE da instrução de Filtro da consulta de filtro e modifique a cláusula WHERE da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="19c87-115">In the **Add Filter** dialog box, click the **SafetyStockLevel** column, click the right arrow to add the column to the Filter statement WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [SafetyStockLevel] < 500  
    ```  
  
8.  <span data-ttu-id="19c87-116">Clique em **OK** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19c87-116">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="19c87-117">Marque a caixa de seleção **Criar um instantâneo imediatamente e mantê-lo disponível para inicializar assinaturas** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="19c87-117">Select the **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** check box, and click **Next**.</span></span>  
  
10. <span data-ttu-id="19c87-118">Na página Segurança do Agente, desmarque a caixa de seleção **Usar as configurações de segurança do Agente de Instantâneo** .</span><span class="sxs-lookup"><span data-stu-id="19c87-118">On the Agent Security page, clear **Use the security settings from the Snapshot Agent** check box.</span></span>  
  
11. <span data-ttu-id="19c87-119">Clique em **configurações de segurança** para a agente de instantâneo, digite \<_Machine_Name> _**\ repl_snapshot** na caixa **conta de processo** , forneça a senha dessa conta e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="19c87-119">Click **Security Settings** for the Snapshot Agent, enter \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="19c87-120">Repita a etapa anterior para configurar repl_logreader como a conta de processo do Agente de Leitor de Log e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="19c87-120">Repeat the previous step to set repl_logreader as the process account for the Log Reader Agent, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="19c87-121">Na página Concluir o Assistente, digite **AdvWorksProductTrans** na caixa **Nome da publicação** e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="19c87-121">On the Complete the Wizard page, type **AdvWorksProductTrans** in the **Publication name** box, and click **Finish**.</span></span>  
  
14. <span data-ttu-id="19c87-122">Depois que a publicação for criada, clique em **Fechar** para concluir o assistente.</span><span class="sxs-lookup"><span data-stu-id="19c87-122">After the publication is created, click **Close** to complete the wizard.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="19c87-123">Para exibir o status de geração do instantâneo</span><span class="sxs-lookup"><span data-stu-id="19c87-123">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="19c87-124">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , expanda o nó do servidor e expanda a pasta **replicação** .</span><span class="sxs-lookup"><span data-stu-id="19c87-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="19c87-125">Na pasta **Publicações Locais** , clique com o botão direito do mouse em **AdvWorksProductTrans**e clique em **Exibir Status do Agente de Instantâneo**.</span><span class="sxs-lookup"><span data-stu-id="19c87-125">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="19c87-126">O status atual do trabalho do Snapshot Agent para a publicação é exibido.</span><span class="sxs-lookup"><span data-stu-id="19c87-126">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="19c87-127">Verifique se o trabalho de instantâneo teve êxito antes de continuar à próxima lição.</span><span class="sxs-lookup"><span data-stu-id="19c87-127">Verify that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-distribution-agent-login-to-the-pal"></a><span data-ttu-id="19c87-128">Para adicionar o logon Distribution Agent à PAL</span><span class="sxs-lookup"><span data-stu-id="19c87-128">To add the Distribution Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="19c87-129">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , expanda o nó do servidor e expanda a pasta **replicação** .</span><span class="sxs-lookup"><span data-stu-id="19c87-129">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="19c87-130">Na pasta **Publicações Locais** , clique com o botão direito do mouse em **AdvWorksProductTrans**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="19c87-130">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="19c87-131">A caixa de diálogo **Propriedades da Publicação** é exibida.</span><span class="sxs-lookup"><span data-stu-id="19c87-131">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="19c87-132">Selecione a página **Lista de Acesso à Publicação** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="19c87-132">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="19c87-133">Na caixa de diálogo **Adicionar Acesso à Publicação**, selecione _<Machine_Name>_**\repl_distribution** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="19c87-133">\In the **Add Publication Access** dialog box, select _<Machine_Name>_**\repl_distribution** and click **OK**.</span></span> <span data-ttu-id="19c87-134">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="19c87-134">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="19c87-135">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="19c87-135">Next Steps</span></span>  
 <span data-ttu-id="19c87-136">Você criou a publicação transacional com êxito.</span><span class="sxs-lookup"><span data-stu-id="19c87-136">You have successfully created the transactional publication.</span></span> <span data-ttu-id="19c87-137">A seguir, você assinará essa publicação.</span><span class="sxs-lookup"><span data-stu-id="19c87-137">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="19c87-138">Consulte [Lição 2: Criando uma assinatura na publicação transacional](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="19c87-138">See [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c87-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="19c87-139">See Also</span></span>  
 <span data-ttu-id="19c87-140">[Filtrar os dados publicados](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="19c87-140">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="19c87-141">[Define an Article](publish/define-an-article.md) </span><span class="sxs-lookup"><span data-stu-id="19c87-141">[Define an Article](publish/define-an-article.md) </span></span>  
 [<span data-ttu-id="19c87-142">Criar e aplicar o instantâneo</span><span class="sxs-lookup"><span data-stu-id="19c87-142">Create and Apply the Snapshot</span></span>](create-and-apply-the-snapshot.md)  
  
  
