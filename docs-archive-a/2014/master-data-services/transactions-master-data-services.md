---
title: Transações (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], about transactions
- transactions [Master Data Services]
ms.assetid: 4cd2fa6f-9c76-4b7a-ae18-d4e5fd2f03f5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c693b550e0c1adb8f5910d99c7125c85f41abb8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684789"
---
# <a name="transactions-master-data-services"></a><span data-ttu-id="71515-102">Transações (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="71515-102">Transactions (Master Data Services)</span></span>
  <span data-ttu-id="71515-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], uma transação é registrada sempre que uma ação é tomada em um membro.</span><span class="sxs-lookup"><span data-stu-id="71515-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a transaction is recorded each time action is taken on a member.</span></span> <span data-ttu-id="71515-104">Transações podem ser exibidas por todos os usuários e revertidas por administradores.</span><span class="sxs-lookup"><span data-stu-id="71515-104">Transactions can be viewed by all users and reversed by administrators.</span></span> <span data-ttu-id="71515-105">As transações mostram a data, a hora e o usuário que tomou a ação, além de outros detalhes.</span><span class="sxs-lookup"><span data-stu-id="71515-105">Transactions show the date, time, and user who took the action, along with other details.</span></span> <span data-ttu-id="71515-106">Usuários podem adicionar uma anotação a uma transação, para indicar por que uma transação aconteceu.</span><span class="sxs-lookup"><span data-stu-id="71515-106">Users can add an annotation to a transaction, to indicate why a transaction took place.</span></span>  
  
## <a name="when-transaction-are-recorded"></a><span data-ttu-id="71515-107">Quando as transações são registradas</span><span class="sxs-lookup"><span data-stu-id="71515-107">When Transaction Are Recorded</span></span>  
 <span data-ttu-id="71515-108">As transações são registradas quando os membros:</span><span class="sxs-lookup"><span data-stu-id="71515-108">Transactions are recorded when members:</span></span>  
  
-   <span data-ttu-id="71515-109">São criados, excluídos ou reativados.</span><span class="sxs-lookup"><span data-stu-id="71515-109">Are created, deleted, or reactivated.</span></span>  
  
-   <span data-ttu-id="71515-110">Têm valores de atributo alterados.</span><span class="sxs-lookup"><span data-stu-id="71515-110">Have attribute values changed.</span></span>  
  
-   <span data-ttu-id="71515-111">São movidos em uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="71515-111">Are moved in a hierarchy.</span></span>  
  
 <span data-ttu-id="71515-112">As transações não são gravadas quando as regras de negócios alteram os valores do atributo.</span><span class="sxs-lookup"><span data-stu-id="71515-112">Transactions are not recorded when business rules change attribute values.</span></span>  
  
## <a name="view-and-manage-transactions"></a><span data-ttu-id="71515-113">Exibir e gerenciar transações</span><span class="sxs-lookup"><span data-stu-id="71515-113">View and Manage Transactions</span></span>  
 <span data-ttu-id="71515-114">Na área funcional **Explorer** , você pode exibir e anotar (adicionar comentários) as transações que você mesmo criou.</span><span class="sxs-lookup"><span data-stu-id="71515-114">In the **Explorer** functional area, you can view and annotate (add comments to) the transactions that you made yourself.</span></span>  
  
 <span data-ttu-id="71515-115">Na área funcional **Gerenciamento de Versões** , os administradores podem exibir todas as transações de todos os usuários dos modelos aos quais têm acesso e reverter qualquer uma dessas transações.</span><span class="sxs-lookup"><span data-stu-id="71515-115">In the **Version Management** functional area, administrators can view all transactions for all users for the models they have access to, and reverse any of these transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71515-116">Os administradores podem exibir todas as transações para todos os usuários, desde que não tenham o nível de permissão somente leitura aplicado na área funcional **Gerenciamento de Versão**.</span><span class="sxs-lookup"><span data-stu-id="71515-116">Administrators can view all transactions for all users as long as they don't have the read-only permission level applied in the **Version Management** functional area .</span></span> <span data-ttu-id="71515-117">Por exemplo, se o nível de permissão somente leitura e de permissão de atualização estiver definido para o administrador, ele não poderá ver as transações de outro usuário porque a permissão somente leitura terá precedência sobre a permissão de atualização.</span><span class="sxs-lookup"><span data-stu-id="71515-117">For example, if the read-only permission and update permission level is set for the administrator, the administrator will not be able to see other user transactions because the read-only permission will take precedence over the update permission.</span></span>

## <a name="system-settings"></a><span data-ttu-id="71515-118">Configurações do sistema</span><span class="sxs-lookup"><span data-stu-id="71515-118">System Settings</span></span>  
 <span data-ttu-id="71515-119">Há uma configuração no [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] que afeta se as transações são ou não registradas quando os registros são preparados.</span><span class="sxs-lookup"><span data-stu-id="71515-119">There is a setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affects whether or not transactions are recorded when records are staged.</span></span> <span data-ttu-id="71515-120">Esta configuração só afeta o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="71515-120">This setting affects SQL Server 2008 R2 only.</span></span> <span data-ttu-id="71515-121">É possível ajustar essa configuração no [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] ou diretamente na tabela Configurações do Sistema do banco de dados [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71515-121">You can adjust this setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="71515-122">Para obter mais informações, veja [Configurações do sistema &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="71515-122">For more information, see [System Settings &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span></span>  
  
 <span data-ttu-id="71515-123">Ao importar dados nesta versão do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], você poderá especificar se deseja ou não registrar em log as transações ao iniciar o procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="71515-123">When importing data in this version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify whether or not to log transactions when initiating the stored procedure.</span></span> <span data-ttu-id="71515-124">Para obter mais informações, consulte [Preparando um procedimento armazenado &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="71515-124">For more information, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="concurrency"></a><span data-ttu-id="71515-125">Simultaneidade</span><span class="sxs-lookup"><span data-stu-id="71515-125">Concurrency</span></span>  
 <span data-ttu-id="71515-126">Se um valor de entidade específico for mostrado simultaneamente em mais de uma sessão do Explorer, as edições simultâneas do mesmo valor serão permitidas.</span><span class="sxs-lookup"><span data-stu-id="71515-126">If a particular entity value is shown simultaneously in more than one Explorer session, concurrent edits to the same value are possible.</span></span> <span data-ttu-id="71515-127">As edições simultâneas não serão detectadas automaticamente pelo MDS.</span><span class="sxs-lookup"><span data-stu-id="71515-127">Concurrent edits will not be detected automatically by MDS.</span></span> <span data-ttu-id="71515-128">Isso pode ocorrer quando vários usuários utilizarem o MDS Explorer no navegador da Web de várias sessões como, por exemplo, de vários computadores, várias guias ou janelas de navegador ou várias contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="71515-128">This can occur when multiple users use the MDS Explorer in the Web browser from multiple sessions, for example from multiple computers, multiple browser tabs or windows, or multiple user accounts.</span></span>  
  
 <span data-ttu-id="71515-129">Mais de um usuário pode atualizar os mesmos valores de entidade sem erro apesar das transações habilitadas.</span><span class="sxs-lookup"><span data-stu-id="71515-129">More than one user can update the same entity values without error despite transactions being enabled.</span></span> <span data-ttu-id="71515-130">Normalmente, a última edição do valor em determinado período terá precedência.</span><span class="sxs-lookup"><span data-stu-id="71515-130">Typically the last edit to the value in a sequence of time will take precedence.</span></span> <span data-ttu-id="71515-131">O conflito de edição duplicada pode ser observado manualmente no histórico de transação e pode ser revertido manualmente pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="71515-131">The duplicate edit conflict can be manually observed in the transaction history and can be reversed manually by the administrator.</span></span> <span data-ttu-id="71515-132">O histórico de transações mostrará as transações individuais para o **Valor anterior** e o **Novo valor** do atributo em questão de cada sessão, mas não resolverá o conflito automaticamente quando vários **Novos Valores** existirem para o mesmo valor antigo.</span><span class="sxs-lookup"><span data-stu-id="71515-132">The transaction history will show the individual transactions for the **Prior value** and **New value** for the attribute in question from each session, but will not automatically resolve the conflict when multiple **New Values** exist for the same old value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="71515-133">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="71515-133">Related Tasks</span></span>  
  
|<span data-ttu-id="71515-134">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="71515-134">Task Description</span></span>|<span data-ttu-id="71515-135">Tópico</span><span class="sxs-lookup"><span data-stu-id="71515-135">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="71515-136">Desfazer uma ação por meio de reversão de uma transação (somente administradores).</span><span class="sxs-lookup"><span data-stu-id="71515-136">Undo an action by reversing a transaction (administrators only).</span></span>|[<span data-ttu-id="71515-137">Inverter uma transação &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="71515-137">Reverse a Transaction &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reverse-a-transaction-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="71515-138">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="71515-138">Related Content</span></span>  
  
-   [<span data-ttu-id="71515-139">Administradores &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="71515-139">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
-   [<span data-ttu-id="71515-140">Anotações &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="71515-140">Annotations &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/annotations-master-data-services.md)  
  
  
