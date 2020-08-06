---
title: Configurar a distribuição | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], distribution
- distribution configuration [SQL Server replication]
- remote Distributors [SQL Server replication]
- transactional replication, configuring distribution
- distribution databases [SQL Server replication], sizing
- Distributors [SQL Server replication], configuring
- distribution databases [SQL Server replication], about distribution databases
- distribution databases [SQL Server replication]
- merge replication [SQL Server replication], configuring distribution
ms.assetid: 94d52169-384e-4885-84eb-2304e967d9f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b0378fe285ba57e1420b7e6bebf5e2e6fe13d29e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571947"
---
# <a name="configure-distribution"></a><span data-ttu-id="d0977-102">Configurar a distribuição</span><span class="sxs-lookup"><span data-stu-id="d0977-102">Configure Distribution</span></span>
  <span data-ttu-id="d0977-103">O Distribuidor é um servidor que contém o banco de dados de distribuição, que armazena metadados e dados de histórico para todos os tipos de replicação e transações para replicação transacional.</span><span class="sxs-lookup"><span data-stu-id="d0977-103">The Distributor is a server that contains the distribution database, which stores metadata and history data for all types of replication and transactions for transactional replication.</span></span> <span data-ttu-id="d0977-104">Para configurar a replicação, deve-se configurar um Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d0977-104">To set up replication, you must configure a Distributor.</span></span> <span data-ttu-id="d0977-105">Cada Publicador pode ser atribuído a uma única instância do Distribuidor, mas vários publicadores podem compartilhar um Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d0977-105">Each Publisher can be assigned to only a single Distributor instance, but multiple publishers can share a Distributor.</span></span> <span data-ttu-id="d0977-106">O Distribuidor usa esses recursos adicionais no servidor onde fica localizado:</span><span class="sxs-lookup"><span data-stu-id="d0977-106">The Distributor uses these additional resources on the server where it is located:</span></span>  
  
-   <span data-ttu-id="d0977-107">Espaço em disco adicional, se os arquivos de instantâneo para a publicação forem armazenados no Distribuidor (o que geralmente acontece).</span><span class="sxs-lookup"><span data-stu-id="d0977-107">Additional disk space if the snapshot files for the publication are stored on the Distributor (which they typically are).</span></span>  
  
-   <span data-ttu-id="d0977-108">Espaço em disco adicional para armazenar o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="d0977-108">Additional disk space to store the distribution database.</span></span>  
  
-   <span data-ttu-id="d0977-109">Uso de processador adicional por agentes de replicação para assinaturas push executadas no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d0977-109">Additional processor usage by replication agents for push subscriptions running on the Distributor.</span></span>  
  
 <span data-ttu-id="d0977-110">O servidor selecionado como Distribuidor deve ter espaço em disco adequado e potência no processador para dar suporte a replicação e a qualquer outra atividade naquele servidor.</span><span class="sxs-lookup"><span data-stu-id="d0977-110">The server you select as the Distributor should have adequate disk space and processor power to support replication and any other activities on that server.</span></span> <span data-ttu-id="d0977-111">Ao configurar o Distribuidor, especifica-se o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d0977-111">When you configure the Distributor, you specify the following:</span></span>  
  
-   <span data-ttu-id="d0977-112">Uma pasta de instantâneo usada, por padrão, para todos os Publicadores que usam esse Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d0977-112">A snapshot folder, which is used, by default, for all Publishers that use this Distributor.</span></span> <span data-ttu-id="d0977-113">Certifique-se de que essa pasta já é compartilhada e tem as permissões apropriadas definidas.</span><span class="sxs-lookup"><span data-stu-id="d0977-113">Ensure that this folder is already shared and has the appropriate permissions set.</span></span> <span data-ttu-id="d0977-114">Para obter mais informações, consulte [Proteger a pasta de instantâneos](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="d0977-114">For more information, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span>  
  
-   <span data-ttu-id="d0977-115">Um nome e locais de arquivo para o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="d0977-115">A name and file locations for the distribution database.</span></span> <span data-ttu-id="d0977-116">O banco de dados de distribuição não pode ser renomeado depois de criado.</span><span class="sxs-lookup"><span data-stu-id="d0977-116">The distribution database cannot be renamed after it is created.</span></span> <span data-ttu-id="d0977-117">Para usar um nome diferente para o banco de dados, deve-se desabilitar a distribuição e reconfigurá-la.</span><span class="sxs-lookup"><span data-stu-id="d0977-117">To use a different name for the database, you must disable distribution and reconfigure it.</span></span>  
  
-   <span data-ttu-id="d0977-118">Quaisquer Publicadores autorizados a usar o Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d0977-118">Any Publishers authorized to use the Distributor.</span></span> <span data-ttu-id="d0977-119">Se você especificar Publicadores diferentes da instância em que o Distribuidor é executado, também deverá especificar uma senha para as conexões feitas pelo Publicador para o Distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="d0977-119">If you specify Publishers other than the instance on which the Distributor runs, you must also specify a password for the connections the Publishers make to the remote Distributor.</span></span>  
  
 <span data-ttu-id="d0977-120">Para replicação transacional, depois que configurar distribuição, recomendamos que você:</span><span class="sxs-lookup"><span data-stu-id="d0977-120">For transactional replication, after you configure distribution, we recommend that you:</span></span>  
  
-   <span data-ttu-id="d0977-121">Dimensione adequadamente o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="d0977-121">Size the distribution database appropriately.</span></span> <span data-ttu-id="d0977-122">Teste a replicação com uma carga típica para seu sistema para determinar a quantidade de espaço necessária para armazenar comandos.</span><span class="sxs-lookup"><span data-stu-id="d0977-122">Test replication with a typical load for your system to determine how much space is required to store commands.</span></span> <span data-ttu-id="d0977-123">Certifique-se de que o banco de dados seja amplo o suficiente para armazenar comandos, sem ter que aumentá-lo frequentemente.</span><span class="sxs-lookup"><span data-stu-id="d0977-123">Ensure the database is large enough to store commands without having to auto-grow frequently.</span></span> <span data-ttu-id="d0977-124">Para obter mais informações sobre como alterar o tamanho de um banco de dados, consulte [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d0977-124">For more information about changing the size of a database, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
-   <span data-ttu-id="d0977-125">Defina a opção **sync with backup** no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="d0977-125">Set the **sync with backup** option on the distribution database.</span></span> <span data-ttu-id="d0977-126">Para obter mais informações, consulte [Estratégias para fazer backup e restaurar o instantâneo e a replicação transacional](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md) e [Habilitar backups coordenados para a replicação transacional &#40;Programação Transact-SQL de replicação&#41;](administration/enable-coordinated-backups-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="d0977-126">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md) and [Enable Coordinated Backups for Transactional Replication &#40;Replication Transact-SQL Programming&#41;](administration/enable-coordinated-backups-for-transactional-replication.md).</span></span>  
  
## <a name="local-and-remote-distributors"></a><span data-ttu-id="d0977-127">Distribuidores locais e remotos</span><span class="sxs-lookup"><span data-stu-id="d0977-127">Local and Remote Distributors</span></span>  
 <span data-ttu-id="d0977-128">Por padrão, o Distribuidor é o mesmo servidor que o Publicador (um Distribuidor local), mas também pode ser um servidor separado do Publicador (um Distribuidor remoto).</span><span class="sxs-lookup"><span data-stu-id="d0977-128">By default, the Distributor is the same server as the Publisher (a local Distributor), but it can also be a separate server from the Publisher (a remote Distributor).</span></span> <span data-ttu-id="d0977-129">Normalmente, escolheria usar um Distribuidor remoto se você quiser:</span><span class="sxs-lookup"><span data-stu-id="d0977-129">Typically, you would choose to use a remote Distributor if you want to:</span></span>  
  
-   <span data-ttu-id="d0977-130">Processamento de offload para outro computador se você quiser impacto mínimo de replicação no Publicador (por exemplo, se o Publicador for um servidor OLTP).</span><span class="sxs-lookup"><span data-stu-id="d0977-130">Offload processing to another computer if you want minimal impact from replication on the Publisher (for example, if the Publisher is an OLTP server).</span></span>  
  
-   <span data-ttu-id="d0977-131">Configurar um Distribuidor centralizado para vários Publicadores.</span><span class="sxs-lookup"><span data-stu-id="d0977-131">Configure a centralized Distributor for multiple Publishers.</span></span>  
  
 <span data-ttu-id="d0977-132">Distribuidores remotos são mais comuns na replicação transacional do que na replicação de mesclagem por duas razões:</span><span class="sxs-lookup"><span data-stu-id="d0977-132">Remote Distributors are more common in transactional replication than they are in merge replication for two reasons:</span></span>  
  
-   <span data-ttu-id="d0977-133">O Distribuidor tem um papel maior na replicação transacional por que todas as transações replicadas são gravadas para e lidas de um banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="d0977-133">The Distributor plays a larger role in transactional replication because all replicated transactions are written to and read from the distribution database.</span></span>  
  
-   <span data-ttu-id="d0977-134">Topologias de replicação de mesclagem normalmente usam assinaturas pull, por isso agentes são executados para cada Assinante, em vez de serem todos executados no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d0977-134">Merge replication topologies typically use pull subscriptions, so agents run at each Subscriber, rather than all running at the Distributor.</span></span> <span data-ttu-id="d0977-135">Para obter mais informações, consulte [Subscribe to Publications](subscribe-to-publications.md) (Assinar publicações).</span><span class="sxs-lookup"><span data-stu-id="d0977-135">For more information, see [Subscribe to Publications](subscribe-to-publications.md).</span></span> <span data-ttu-id="d0977-136">Na maioria dos casos, deve-se usar um Distribuidor local para replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="d0977-136">In most cases, you should use a local Distributor for merge replication.</span></span>  
  
 <span data-ttu-id="d0977-137">Para configurar publicação e distribuição, consulte [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="d0977-137">To configure publishing and distribution, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span></span>  
  
 <span data-ttu-id="d0977-138">Para modificar propriedades de Publicador e Distribuidor, consulte [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d0977-138">To modify Publisher and Distributor properties, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0977-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d0977-139">See Also</span></span>  
 <span data-ttu-id="d0977-140">[Publicar dados e objetos de banco de dados](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="d0977-140">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="d0977-141">Proteger o Distribuidor</span><span class="sxs-lookup"><span data-stu-id="d0977-141">Secure the Distributor</span></span>](security/secure-the-distributor.md)  
  
  
