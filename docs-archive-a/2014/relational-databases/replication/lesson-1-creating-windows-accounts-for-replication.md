---
title: 'Lição 1: Criando contas do Windows para replicação | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
- replication [SQL Server], administering
ms.assetid: 65c3816b-47f0-448c-a4a4-ebd3e2a58820
author: rothja
ms.author: jroth
ms.openlocfilehash: 29f1008338b3ba728066ed611108477586a4c899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569870"
---
# <a name="lesson-1-creating-windows-accounts-for-replication"></a><span data-ttu-id="eccff-102">Lição 1: Criando contas do Windows para replicação</span><span class="sxs-lookup"><span data-stu-id="eccff-102">Lesson 1: Creating Windows Accounts for Replication</span></span>
  <span data-ttu-id="eccff-103">Nesta lição, você criará contas de Windows para executar os agentes de replicação.</span><span class="sxs-lookup"><span data-stu-id="eccff-103">In this lesson, you will create Windows accounts to run replication agents.</span></span> <span data-ttu-id="eccff-104">Você criará uma conta de Windows separada no servidor local para os seguintes agentes:</span><span class="sxs-lookup"><span data-stu-id="eccff-104">You will create a separate Windows account on the local server for the following agents:</span></span>  
  
|<span data-ttu-id="eccff-105">Agente</span><span class="sxs-lookup"><span data-stu-id="eccff-105">Agent</span></span>|<span data-ttu-id="eccff-106">Localização</span><span class="sxs-lookup"><span data-stu-id="eccff-106">Location</span></span>|<span data-ttu-id="eccff-107">Nome da conta</span><span class="sxs-lookup"><span data-stu-id="eccff-107">Account name</span></span>|  
|-----------|--------------|------------------|  
|<span data-ttu-id="eccff-108">Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="eccff-108">Snapshot Agent</span></span>|<span data-ttu-id="eccff-109">Publisher</span><span class="sxs-lookup"><span data-stu-id="eccff-109">Publisher</span></span>|<span data-ttu-id="eccff-110">\<*machine_name*>\ repl_snapshot</span><span class="sxs-lookup"><span data-stu-id="eccff-110">\<*machine_name*>\repl_snapshot</span></span>|  
|<span data-ttu-id="eccff-111">Agente de Leitor de Log</span><span class="sxs-lookup"><span data-stu-id="eccff-111">Log Reader Agent</span></span>|<span data-ttu-id="eccff-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="eccff-112">Publisher</span></span>|<span data-ttu-id="eccff-113">\<*machine_name*>\ repl_logreader</span><span class="sxs-lookup"><span data-stu-id="eccff-113">\<*machine_name*>\repl_logreader</span></span>|  
|<span data-ttu-id="eccff-114">Agente de Distribuição</span><span class="sxs-lookup"><span data-stu-id="eccff-114">Distribution Agent</span></span>|<span data-ttu-id="eccff-115">Publicador e assinante</span><span class="sxs-lookup"><span data-stu-id="eccff-115">Publisher and Subscriber</span></span>|<span data-ttu-id="eccff-116">\<*machine_name*>\ repl_distribution</span><span class="sxs-lookup"><span data-stu-id="eccff-116">\<*machine_name*>\repl_distribution</span></span>|  
|<span data-ttu-id="eccff-117">Merge Agent</span><span class="sxs-lookup"><span data-stu-id="eccff-117">Merge Agent</span></span>|<span data-ttu-id="eccff-118">Publicador e assinante</span><span class="sxs-lookup"><span data-stu-id="eccff-118">Publisher and Subscriber</span></span>|<span data-ttu-id="eccff-119">\<*machine_name*>\ repl_merge</span><span class="sxs-lookup"><span data-stu-id="eccff-119">\<*machine_name*>\repl_merge</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="eccff-120">Nos tutoriais de replicação, o Publicador e o Distribuidor compartilham a mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eccff-120">In the replication tutorials, the Publisher and Distributor share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eccff-121">O Publicador e o Assinante podem compartilhar a mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas isso não é um requisito.</span><span class="sxs-lookup"><span data-stu-id="eccff-121">The Publisher and Subscriber may share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but it is not a requirement.</span></span> <span data-ttu-id="eccff-122">Se o Publicador e o Assinante compartilharem a mesma instância, as etapas usadas para criar contas no Assinante não são necessárias.</span><span class="sxs-lookup"><span data-stu-id="eccff-122">If the Publisher and Subscriber share the same instance, the steps that are used to create accounts at the Subscriber are not required.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-publisher"></a><span data-ttu-id="eccff-123">Para criar contas locais do Windows local para agentes de replicação no Publicador</span><span class="sxs-lookup"><span data-stu-id="eccff-123">To create local Windows accounts for replication agents at the Publisher</span></span>  
  
1.  <span data-ttu-id="eccff-124">No Publicador, abra **Gerenciamento do computador** em **Ferramentas administrativas** no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="eccff-124">At the Publisher, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="eccff-125">Em **Ferramentas do Sistema**, expanda **Usuários e Grupos Locais**.</span><span class="sxs-lookup"><span data-stu-id="eccff-125">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="eccff-126">Clique com o botão direito do mouse em **usuários** e clique em **novo usuário**.</span><span class="sxs-lookup"><span data-stu-id="eccff-126">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="eccff-127">Insira `repl_snapshot` na caixa **nome de usuário** , forneça a senha e outras informações relevantes e, em seguida, clique em **criar** para criar a conta de repl_snapshot.</span><span class="sxs-lookup"><span data-stu-id="eccff-127">Enter `repl_snapshot` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_snapshot account.</span></span>  
  
5.  <span data-ttu-id="eccff-128">Repita a etapa anterior para criar as contas de repl_logreader, repl_distribution e repl_merge.</span><span class="sxs-lookup"><span data-stu-id="eccff-128">Repeat the previous step to create the repl_logreader, repl_distribution, and repl_merge accounts.</span></span>  
  
6.  <span data-ttu-id="eccff-129">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="eccff-129">Click **Close**.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-subscriber"></a><span data-ttu-id="eccff-130">Para criar contas locais do Windows para agentes de replicação no Assinante</span><span class="sxs-lookup"><span data-stu-id="eccff-130">To create local Windows accounts for replication agents at the Subscriber</span></span>  
  
1.  <span data-ttu-id="eccff-131">No Assinante, abra **Gerenciamento do computador** em **Ferramentas administrativas** no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="eccff-131">At the Subscriber, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="eccff-132">Em **Ferramentas do Sistema**, expanda **Usuários e Grupos Locais**.</span><span class="sxs-lookup"><span data-stu-id="eccff-132">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="eccff-133">Clique com o botão direito do mouse em **usuários** e clique em **novo usuário**.</span><span class="sxs-lookup"><span data-stu-id="eccff-133">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="eccff-134">Insira `repl_distribution` na caixa **nome de usuário** , forneça a senha e outras informações relevantes e, em seguida, clique em **criar** para criar a conta de repl_distribution.</span><span class="sxs-lookup"><span data-stu-id="eccff-134">Enter `repl_distribution` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_distribution account.</span></span>  
  
5.  <span data-ttu-id="eccff-135">Repita a etapa anterior para criar a conta de repl_merge.</span><span class="sxs-lookup"><span data-stu-id="eccff-135">Repeat the previous step to create the repl_merge account.</span></span>  
  
6.  <span data-ttu-id="eccff-136">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="eccff-136">Click **Close**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eccff-137">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="eccff-137">Next Steps</span></span>  
 <span data-ttu-id="eccff-138">Você criou contas de Windows com sucesso para os agentes de replicação.</span><span class="sxs-lookup"><span data-stu-id="eccff-138">You have successfully created Windows accounts for replication agents.</span></span> <span data-ttu-id="eccff-139">A seguir, você configurará a pasta de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="eccff-139">Next, you will configure the snapshot folder.</span></span> <span data-ttu-id="eccff-140">Consulte [Lição 2: Preparando a pasta do instantâneo](lesson-2-preparing-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="eccff-140">See [Lesson 2: Preparing the Snapshot Folder](lesson-2-preparing-the-snapshot-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eccff-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eccff-141">See Also</span></span>  
 [<span data-ttu-id="eccff-142">Visão geral dos agentes de replicação</span><span class="sxs-lookup"><span data-stu-id="eccff-142">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
