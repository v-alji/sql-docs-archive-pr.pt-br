---
title: Ações comuns que requerem um backup atualizado | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], actions requiring a backup
- restoring [SQL Server replication], actions requiring a backup
- backups [SQL Server replication], actions requiring a backup
ms.assetid: a5975bf4-183e-42e3-b7d1-ad02f89d2e1d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3eb10bdca8ee188f7b322a46665c38129d57052b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679293"
---
# <a name="common-actions-requiring-an-updated-backup"></a><span data-ttu-id="0a7d7-102">Ações comuns que requerem um backup atualizado</span><span class="sxs-lookup"><span data-stu-id="0a7d7-102">Common Actions Requiring an Updated Backup</span></span>
  <span data-ttu-id="0a7d7-103">Se você executar backups de log regulares, qualquer alteração relacionada à replicação deverá ser capturada nos backups de log.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-103">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="0a7d7-104">Se não executar backups de log, faça um backup dos bancos de dados de publicação, distribuição, assinatura, **msdb**e **mestre** após fazer alterações ao seu esquema ou topologia de replicação.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-104">If you don't perform log backups, perform a backup of the publication, distribution, subscription, **msdb**, and **master** databases after making modifications to your replication schema or topology.</span></span>  
  
## <a name="publication-database"></a><span data-ttu-id="0a7d7-105">Banco de dados de publicação</span><span class="sxs-lookup"><span data-stu-id="0a7d7-105">Publication Database</span></span>  
 <span data-ttu-id="0a7d7-106">Faça o backup do banco de dados de publicação após:</span><span class="sxs-lookup"><span data-stu-id="0a7d7-106">Backup the publication database after:</span></span>  
  
-   <span data-ttu-id="0a7d7-107">Criar novas publicações.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-107">Creating new publications.</span></span>  
  
-   <span data-ttu-id="0a7d7-108">Alterar qualquer propriedade de publicação, inclusive filtragem.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-108">Changing any publication property, including filtering.</span></span>  
  
-   <span data-ttu-id="0a7d7-109">Adicionar artigos a uma publicação existente.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-109">Adding articles to an existing publication.</span></span>  
  
-   <span data-ttu-id="0a7d7-110">Executar uma reinicialização de publicação abrangente de assinaturas.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-110">Performing a publication-wide reinitialization of subscriptions.</span></span>  
  
-   <span data-ttu-id="0a7d7-111">Fazer uma alteração de esquema em uma tabela publicada.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-111">Making a schema change on a published table.</span></span>  
  
-   <span data-ttu-id="0a7d7-112">Executando um script sob demanda com [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-112">Performing on-demand script execution with [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span>  
  
-   <span data-ttu-id="0a7d7-113">Alterar qualquer propriedade de artigo.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-113">Changing any article property.</span></span>  
  
-   <span data-ttu-id="0a7d7-114">Descartar qualquer publicação.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-114">Dropping any publications.</span></span>  
  
-   <span data-ttu-id="0a7d7-115">Descartar qualquer artigo.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-115">Dropping any articles.</span></span>  
  
-   <span data-ttu-id="0a7d7-116">Desabilitar a replicação.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-116">Disabling replication.</span></span>  
  
## <a name="distribution-database"></a><span data-ttu-id="0a7d7-117">Banco de dados de distribuição</span><span class="sxs-lookup"><span data-stu-id="0a7d7-117">Distribution Database</span></span>  
 <span data-ttu-id="0a7d7-118">Faça o backup do banco de dados de distribuição após:</span><span class="sxs-lookup"><span data-stu-id="0a7d7-118">Backup the distribution database after:</span></span>  
  
-   <span data-ttu-id="0a7d7-119">Criar ou modificar perfis de agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-119">Creating or modifying replication agent profiles.</span></span>  
  
-   <span data-ttu-id="0a7d7-120">Modificar parâmetros de perfil do agente de replicação.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-120">Modifying replication agent profile parameters.</span></span>  
  
-   <span data-ttu-id="0a7d7-121">Alterar as propriedades do agente de replicação (inclusive agendas) para qualquer assinatura push.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-121">Changing the replication agent properties (including schedules) for any push subscriptions.</span></span>  
  
-   <span data-ttu-id="0a7d7-122">Um novo intervalo de identidades é atribuído pelo recurso de gerenciamento automático de intervalo de identidade.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-122">A new range of identities is assigned by the automatic identity range management feature.</span></span>  
  
## <a name="subscription-database"></a><span data-ttu-id="0a7d7-123">Banco de dados de assinatura</span><span class="sxs-lookup"><span data-stu-id="0a7d7-123">Subscription Database</span></span>  
 <span data-ttu-id="0a7d7-124">Faça o backup do banco de dados de assinatura após:</span><span class="sxs-lookup"><span data-stu-id="0a7d7-124">Backup the subscription database after:</span></span>  
  
-   <span data-ttu-id="0a7d7-125">Alterar qualquer propriedade de assinatura.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-125">Changing any subscription property.</span></span>  
  
-   <span data-ttu-id="0a7d7-126">Alterar a prioridade para uma assinatura de mesclagem no Publicador.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-126">Changing the priority for a merge subscription at the Publisher.</span></span>  
  
-   <span data-ttu-id="0a7d7-127">Descartar qualquer assinatura.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-127">Dropping any subscriptions.</span></span>  
  
-   <span data-ttu-id="0a7d7-128">Desabilitar a replicação.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-128">Disabling replication.</span></span>  
  
## <a name="msdb-database"></a><span data-ttu-id="0a7d7-129">Banco de dados msdb</span><span class="sxs-lookup"><span data-stu-id="0a7d7-129">msdb Database</span></span>  
 <span data-ttu-id="0a7d7-130">Faça o backup do banco de dados de sistema **msdb** no nó apropriado após:</span><span class="sxs-lookup"><span data-stu-id="0a7d7-130">Backup the **msdb** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="0a7d7-131">Habilitar ou desabilitar a replicação.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-131">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="0a7d7-132">Adicionar ou descartar um banco de dados de distribuição (no Distribuidor).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-132">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="0a7d7-133">Habilitar ou desabilitar um banco de dados para publicação (no Publicador).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-133">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="0a7d7-134">Criar ou modificar perfis de agente de replicação (no Distribuidor).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-134">Creating or modifying replication agent profiles (at the Distributor).</span></span>  
  
-   <span data-ttu-id="0a7d7-135">Modificar qualquer parâmetro de perfil do agente de replicação (no Distribuidor).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-135">Modifying any replication agent profile parameters (at the Distributor).</span></span>  
  
-   <span data-ttu-id="0a7d7-136">Alterar as propriedades do agente de replicação (inclusive agendas) para qualquer assinatura push (no Distribuidor).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-136">Changing the replication agent properties (including schedules) for any push subscriptions (at the Distributor).</span></span>  
  
-   <span data-ttu-id="0a7d7-137">Alterar as propriedades do agente de replicação (inclusive agendas) para qualquer assinatura pull (no Distribuidor).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-137">Changing the replication agent properties (including schedules) for any pull subscriptions (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="0a7d7-138">Criar um pacote DTS associado com uma publicação transacional que usa assinatura transformáveis (no Distribuidor e no Assinante).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-138">Creating a DTS package associated with a transactional publication that uses transformable subscriptions (at the Distributor and Subscriber).</span></span>  
  
-   <span data-ttu-id="0a7d7-139">Adicionar ou descartar uma assinatura transformável (no Distribuidor e no Assinante)).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-139">Adding or dropping a transformable subscription (at the Distributor and Subscriber).</span></span>  
  
## <a name="master-database"></a><span data-ttu-id="0a7d7-140">Banco de dados mestre</span><span class="sxs-lookup"><span data-stu-id="0a7d7-140">master Database</span></span>  
 <span data-ttu-id="0a7d7-141">Faça o backup do banco de dados de sistema **mestre** no nó apropriado após:</span><span class="sxs-lookup"><span data-stu-id="0a7d7-141">Backup the **master** system database at the appropriate node after:</span></span>  
  
-   <span data-ttu-id="0a7d7-142">Habilitar ou desabilitar a replicação.</span><span class="sxs-lookup"><span data-stu-id="0a7d7-142">Enabling or disabling replication.</span></span>  
  
-   <span data-ttu-id="0a7d7-143">Adicionar ou descartar um banco de dados de distribuição (no Distribuidor).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-143">Adding or dropping a distribution database (at the Distributor).</span></span>  
  
-   <span data-ttu-id="0a7d7-144">Habilitar ou desabilitar um banco de dados para publicação (no Publicador).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-144">Enabling or disabling a database for publishing (at the Publisher).</span></span>  
  
-   <span data-ttu-id="0a7d7-145">Adicionar a primeira ou descartar a última publicação em qualquer banco de dados (no Publicador).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-145">Adding the first or dropping the last publication in any database (at the Publisher).</span></span>  
  
-   <span data-ttu-id="0a7d7-146">Adicionar a primeira ou descartar a última assinatura em qualquer banco de dados (no Assinante).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-146">Adding the first or dropping the last subscription in any database (at the Subscriber).</span></span>  
  
-   <span data-ttu-id="0a7d7-147">Habilitar ou desabilitar um Publicador em um Publicador de Distribuição (no Publicador e no Distribuidor).</span><span class="sxs-lookup"><span data-stu-id="0a7d7-147">Enabling or disabling a Publisher at a Distribution Publisher (at the Publisher and Distributor).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a7d7-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a7d7-148">See Also</span></span>  
 <span data-ttu-id="0a7d7-149">[Fazer backup e restaurar bancos de dados do SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="0a7d7-149">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="0a7d7-150">Fazer backup e restaurar bancos de dados replicados</span><span class="sxs-lookup"><span data-stu-id="0a7d7-150">Back Up and Restore Replicated Databases</span></span>](back-up-and-restore-replicated-databases.md)  
  
  
