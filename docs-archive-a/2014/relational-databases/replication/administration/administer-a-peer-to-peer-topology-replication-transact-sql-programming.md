---
title: Administrar uma topologia ponto a ponto (programação Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, peer-to-peer replication
ms.assetid: 4d0fa941-f9ea-4a14-aed9-34df593fc6f2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3a73af1c1f3a7196d87f77681ee9d62a3ef248a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571970"
---
# <a name="administer-a-peer-to-peer-topology-replication-transact-sql-programming"></a><span data-ttu-id="2ffbc-102">Administrar uma topologia ponto a ponto (Programação Transact-SQL de replicação)</span><span class="sxs-lookup"><span data-stu-id="2ffbc-102">Administer a Peer-to-Peer Topology (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="2ffbc-103">A administração de uma topologia ponto a ponto é semelhante à administração de uma topologia de replicação transacional comum, porém, há algumas áreas com considerações especiais.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-103">Administering a peer-to-peer topology is similar to administering a typical transactional replication topology, but there are a number of areas with special considerations.</span></span> <span data-ttu-id="2ffbc-104">A diferença principal na administração da topologia ponto a ponto é que algumas alterações exigem que o sistema seja *confirmado*.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-104">The principal difference in administering a peer-to-peer topology is that some changes require the system to be *quiesced*.</span></span> <span data-ttu-id="2ffbc-105">Fechar um sistema para novas sessões envolve parar as atividades em tabelas publicadas em todos os nós e garantir que todos os nós tenham recebido todas as alterações de todos os demais nós.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-105">Quiescing a system involves stopping activity on published tables at all nodes and ensuring that each node has received all changes from all other nodes.</span></span> <span data-ttu-id="2ffbc-106">Para obter mais informações, consulte [Como confirmar uma topologia de replicação &#40;Programação Transact-SQL de replicação&#41;](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="2ffbc-106">For more information, see [Quiesce a Replication Topology &#40;Replication Transact-SQL Programming&#41;](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ffbc-107">Em uma topologia ponto a ponto, o distribuidor não pode estar usando uma versão anterior do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de um assinante de pull.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-107">In a peer-to-peer topology, the distributor cannot be using an earlier version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] than a pull subscriber.</span></span>  
  
### <a name="to-add-an-article-to-an-existing-configuration"></a><span data-ttu-id="2ffbc-108">Para adicionar um artigo a uma configuração existente</span><span class="sxs-lookup"><span data-stu-id="2ffbc-108">To add an article to an existing configuration</span></span>  
  
1.  <span data-ttu-id="2ffbc-109">Confirme o sistema.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-109">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="2ffbc-110">Pare o Distribution Agent em cada nó na topologia.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-110">Stop the Distribution Agent at each node in the topology.</span></span> <span data-ttu-id="2ffbc-111">Para obter mais informações, consulte [Conceitos Executáveis do Agente de Replicação](../concepts/replication-agent-executables-concepts.md) ou [Iniciar e Parar um Agente de Replicação &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="2ffbc-111">For more information, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
3.  <span data-ttu-id="2ffbc-112">Execute a instrução CREATE TABLE para adicionar a nova tabela em cada nó na topologia.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-112">Execute the CREATE TABLE statement to add the new table at each node in the topology.</span></span>  
  
4.  <span data-ttu-id="2ffbc-113">Copie manualmente os dados em massa da nova tabela em todos os nós usando a [utilidade bcp](../../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2ffbc-113">Bulk copy the data for the new table manually at all nodes by using the [bcp utility](../../../tools/bcp-utility.md).</span></span>  
  
5.  <span data-ttu-id="2ffbc-114">Execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) para criar o novo artigo em cada nó na topologia.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-114">Execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) to create the new article at each node in the topology.</span></span> <span data-ttu-id="2ffbc-115">Para obter mais informações, consulte [Define an Article](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="2ffbc-115">For more information, see [Define an Article](../publish/define-an-article.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2ffbc-116">Depois que [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) é executado, a replicação adiciona automaticamente o artigo às assinaturas na topologia.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-116">After [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) is executed, replication automatically adds the article to the subscriptions in the topology.</span></span>  
  
6.  <span data-ttu-id="2ffbc-117">Reinicialize os Distribution Agents em cada nó na topologia.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-117">Restart the Distribution Agents at each node in the topology.</span></span>  
  
### <a name="to-make-schema-changes-to-a-publication-database"></a><span data-ttu-id="2ffbc-118">Para efetuar alterações de esquema em um banco de dados de publicação</span><span class="sxs-lookup"><span data-stu-id="2ffbc-118">To make schema changes to a publication database</span></span>  
  
1.  <span data-ttu-id="2ffbc-119">Confirme o sistema.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-119">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="2ffbc-120">Execute as instruções de linguagem de definição de dados (DDL) para modificar o esquema das tabelas publicadas.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-120">Execute the data definition language (DDL) statements to modify the schema of published tables.</span></span> <span data-ttu-id="2ffbc-121">Para obter mais informações sobre alterações de esquema com suporte, consulte [Fazer alterações de esquema em bancos de dados de publicação](../publish/make-schema-changes-on-publication-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2ffbc-121">For more information about supported schema changes, see [Make Schema Changes on Publication Databases](../publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
3.  <span data-ttu-id="2ffbc-122">Antes de retomar a atividade nas tabelas publicadas, confirme o sistema novamente.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-122">Before you resume activity on published tables, quiesce the system again.</span></span> <span data-ttu-id="2ffbc-123">Isto garante que as alterações de esquema foram recebidas por todos os nós antes que novas alterações de dados sejam replicadas.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-123">This ensures that schema changes have been received by all nodes before any new data changes are replicated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ffbc-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2ffbc-124">Example</span></span>  
 <span data-ttu-id="2ffbc-125">O exemplo a seguir demonstra como adicionar um novo artigo de tabela em uma topologia de replicação ponto a ponto existente que tenha dois nós.</span><span class="sxs-lookup"><span data-stu-id="2ffbc-125">The following example demonstrates how to add a new table article to an existing peer-to-peer replication topology that has two nodes.</span></span>  
  
 [!code-sql[HowTo#sp_addp2particle_createtables](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createtables)]  
  
 [!code-sql[HowTo#sp_addp2particle_cmdline](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_cmdline)]  
  
 [!code-sql[HowTo#sp_addp2particle_createarticle](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createarticle)]  
  
## <a name="see-also"></a><span data-ttu-id="2ffbc-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2ffbc-126">See Also</span></span>  
 <span data-ttu-id="2ffbc-127">[Perguntas Frequentes sobre Administração de Replicação](frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="2ffbc-127">[Replication Administration FAQ](frequently-asked-questions-for-replication-administrators.md) </span></span>  
 <span data-ttu-id="2ffbc-128">[Fazer backup e restaurar bancos de dados do SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="2ffbc-128">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="2ffbc-129">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="2ffbc-129">Peer-to-Peer Transactional Replication</span></span>](../transactional/peer-to-peer-transactional-replication.md)  
  
  
