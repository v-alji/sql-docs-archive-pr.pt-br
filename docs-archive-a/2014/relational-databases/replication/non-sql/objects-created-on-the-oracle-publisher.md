---
title: Objetos criados no Publicador Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], objects created
ms.assetid: c58a124b-4da7-46e2-9292-af8ce9e6664b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8fa7f85ba482ed9b1f46d8ef62dfd24e4b306664
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576281"
---
# <a name="objects-created-on-the-oracle-publisher"></a><span data-ttu-id="4be15-102">Objetos criados no Editor Oracle</span><span class="sxs-lookup"><span data-stu-id="4be15-102">Objects Created on the Oracle Publisher</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="4be15-103">a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replicação instala objetos de banco de dados no Publicador Oracle para habilitar o controle de alterações e o encaminhamento (não [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instala arquivos binários no Publicador Oracle).</span><span class="sxs-lookup"><span data-stu-id="4be15-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replication installs database objects on the Oracle Publisher to enable change tracking and forwarding ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not install any binary files on the Oracle Publisher).</span></span> <span data-ttu-id="4be15-104">A tabela seguinte lista os objetos que são criados no Editor Oracle quando este é identificado como um Publicador no Distribuidor do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4be15-104">The following table lists the objects that are created at the Oracle Publisher when it is identified as a Publisher at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributor.</span></span> <span data-ttu-id="4be15-105">As descrições de objeto são fornecidas apenas para fins informativos.</span><span class="sxs-lookup"><span data-stu-id="4be15-105">The object descriptions are provided for informational purposes only.</span></span> <span data-ttu-id="4be15-106">Esses objetos não devem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="4be15-106">These objects should not be modified.</span></span>  
  
|<span data-ttu-id="4be15-107">Nome do Objeto</span><span class="sxs-lookup"><span data-stu-id="4be15-107">Object Name</span></span>|<span data-ttu-id="4be15-108">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="4be15-108">Object Type</span></span>|<span data-ttu-id="4be15-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4be15-109">Description</span></span>|  
|-----------------|-----------------|-----------------|  
|<span data-ttu-id="4be15-110">HREPL_ArticleNlog_V</span><span class="sxs-lookup"><span data-stu-id="4be15-110">HREPL_ArticleNlog_V</span></span>|<span data-ttu-id="4be15-111">Tabela</span><span class="sxs-lookup"><span data-stu-id="4be15-111">Table</span></span>|<span data-ttu-id="4be15-112">Tabela de controle de alterações usada para armazenar informações à medida que são feitas alterações à tabela publicada.</span><span class="sxs-lookup"><span data-stu-id="4be15-112">Change tracking table used to store information as changes are made to the published table.</span></span> <span data-ttu-id="4be15-113">É criada uma tabela de controle de alterações para cada tabela publicada.</span><span class="sxs-lookup"><span data-stu-id="4be15-113">A change tracking table is created for each published table.</span></span>|  
|<span data-ttu-id="4be15-114">HREPL_Changes</span><span class="sxs-lookup"><span data-stu-id="4be15-114">HREPL_Changes</span></span>|<span data-ttu-id="4be15-115">Tabela</span><span class="sxs-lookup"><span data-stu-id="4be15-115">Table</span></span>|<span data-ttu-id="4be15-116">Tabela usada internamente pelo trabalho Xactset para determinar o número de alterações que aguardam ser atribuídas a um conjunto de transações.</span><span class="sxs-lookup"><span data-stu-id="4be15-116">Table used internally by the Xactset Job to determine the number of changes waiting to be assigned to a transaction set.</span></span> <span data-ttu-id="4be15-117">Para obter mais informações sobre esse trabalho, consulte [Ajuste de desempenho para Publicadores Oracle](performance-tuning-for-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="4be15-117">For more information about this job, see [Performance Tuning for Oracle Publishers](performance-tuning-for-oracle-publishers.md).</span></span>|  
|<span data-ttu-id="4be15-118">HREPL_Distributor</span><span class="sxs-lookup"><span data-stu-id="4be15-118">HREPL_Distributor</span></span>|<span data-ttu-id="4be15-119">Tabela</span><span class="sxs-lookup"><span data-stu-id="4be15-119">Table</span></span>|<span data-ttu-id="4be15-120">Tabela de status de Distribuidor usada para manter informações sobre o Distribuidor do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] associado ao Editor Oracle.</span><span class="sxs-lookup"><span data-stu-id="4be15-120">Distributor status table used to maintain information about the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributor associated with the Oracle Publisher.</span></span>|  
|<span data-ttu-id="4be15-121">HREPL_Event</span><span class="sxs-lookup"><span data-stu-id="4be15-121">HREPL_Event</span></span>|<span data-ttu-id="4be15-122">Tabela</span><span class="sxs-lookup"><span data-stu-id="4be15-122">Table</span></span>|<span data-ttu-id="4be15-123">Tabela de eventos usada para sincronizar instantâneos e solicitações de número de linhas.</span><span class="sxs-lookup"><span data-stu-id="4be15-123">Event table used for synchronizing snapshots and row count requests.</span></span>|  
|<span data-ttu-id="4be15-124">HREPL_Mutex</span><span class="sxs-lookup"><span data-stu-id="4be15-124">HREPL_Mutex</span></span>|<span data-ttu-id="4be15-125">Tabela</span><span class="sxs-lookup"><span data-stu-id="4be15-125">Table</span></span>|<span data-ttu-id="4be15-126">Tabela usada para assegurar que o procedimento PopulatePollTable de pacote Oracle não seja executado ao mesmo tempo pelo Log Reader Agent e pelo trabalho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4be15-126">Table used to ensure that the Oracle package procedure PopulatePollTable is not executed concurrently by both the Log Reader Agent and the database job.</span></span>|  
|<span data-ttu-id="4be15-127">HREPL_Poll</span><span class="sxs-lookup"><span data-stu-id="4be15-127">HREPL_Poll</span></span>|<span data-ttu-id="4be15-128">Tabela</span><span class="sxs-lookup"><span data-stu-id="4be15-128">Table</span></span>|<span data-ttu-id="4be15-129">Tabela usada para identificar entradas de tabela de log associadas com conjuntos de alterações a tabelas publicadas.</span><span class="sxs-lookup"><span data-stu-id="4be15-129">Table used to identify log table entries associated with sets of changes to published tables.</span></span>|  
|<span data-ttu-id="4be15-130">HREPL_PublishedTables</span><span class="sxs-lookup"><span data-stu-id="4be15-130">HREPL_PublishedTables</span></span>|<span data-ttu-id="4be15-131">Tabela</span><span class="sxs-lookup"><span data-stu-id="4be15-131">Table</span></span>|<span data-ttu-id="4be15-132">Tabela que contém uma entrada para cada artigo em uma publicação transacional.</span><span class="sxs-lookup"><span data-stu-id="4be15-132">Table containing an entry for each article in a transactional publication.</span></span>|  
|<span data-ttu-id="4be15-133">HREPL_Publisher</span><span class="sxs-lookup"><span data-stu-id="4be15-133">HREPL_Publisher</span></span>|<span data-ttu-id="4be15-134">Tabela</span><span class="sxs-lookup"><span data-stu-id="4be15-134">Table</span></span>|<span data-ttu-id="4be15-135">Tabela de status do Publicador usada para manter informações específicas do Publicador.</span><span class="sxs-lookup"><span data-stu-id="4be15-135">Publisher status table used for maintaining Publisher specific information.</span></span>|  
|<span data-ttu-id="4be15-136">HREPL_SchemaFilter</span><span class="sxs-lookup"><span data-stu-id="4be15-136">HREPL_SchemaFilter</span></span>|<span data-ttu-id="4be15-137">Tabela</span><span class="sxs-lookup"><span data-stu-id="4be15-137">Table</span></span>|<span data-ttu-id="4be15-138">Tabela que contém esquemas que não são exibidos ao publicar por meio do Assistente de Nova Publicação.</span><span class="sxs-lookup"><span data-stu-id="4be15-138">Table containing schemas that are not displayed when publishing through the New Publication Wizard.</span></span>|  
|<span data-ttu-id="4be15-139">HREPL_XactsetCreateTimes</span><span class="sxs-lookup"><span data-stu-id="4be15-139">HREPL_XactsetCreateTimes</span></span>|<span data-ttu-id="4be15-140">Tabela</span><span class="sxs-lookup"><span data-stu-id="4be15-140">Table</span></span>|<span data-ttu-id="4be15-141">Tabela que identifica o momento de criação associado a cada conjunto de transações.</span><span class="sxs-lookup"><span data-stu-id="4be15-141">Table identifying the create time associated with each transaction set.</span></span>|  
|<span data-ttu-id="4be15-142">HREPL_XactsetJob</span><span class="sxs-lookup"><span data-stu-id="4be15-142">HREPL_XactsetJob</span></span>|<span data-ttu-id="4be15-143">Tabela</span><span class="sxs-lookup"><span data-stu-id="4be15-143">Table</span></span>|<span data-ttu-id="4be15-144">Tabela com configurações de parâmetro atuais para o trabalho Xactset.</span><span class="sxs-lookup"><span data-stu-id="4be15-144">Table with current parameter settings for the Xactset Job.</span></span>|  
|<span data-ttu-id="4be15-145">HREPL_Pollid</span><span class="sxs-lookup"><span data-stu-id="4be15-145">HREPL_Pollid</span></span>|<span data-ttu-id="4be15-146">Sequência</span><span class="sxs-lookup"><span data-stu-id="4be15-146">Sequence</span></span>|<span data-ttu-id="4be15-147">Sequência usada para gerar identificações de sondagem.</span><span class="sxs-lookup"><span data-stu-id="4be15-147">Sequence used to generate poll IDs.</span></span>|  
|<span data-ttu-id="4be15-148">HREPL_Seq</span><span class="sxs-lookup"><span data-stu-id="4be15-148">HREPL_Seq</span></span>|<span data-ttu-id="4be15-149">Sequência</span><span class="sxs-lookup"><span data-stu-id="4be15-149">Sequence</span></span>|<span data-ttu-id="4be15-150">Sequência usada para ordenar comandos de alteração.</span><span class="sxs-lookup"><span data-stu-id="4be15-150">Sequence used to order change commands.</span></span>|  
|<span data-ttu-id="4be15-151">HREPL_Stmt</span><span class="sxs-lookup"><span data-stu-id="4be15-151">HREPL_Stmt</span></span>|<span data-ttu-id="4be15-152">Sequência</span><span class="sxs-lookup"><span data-stu-id="4be15-152">Sequence</span></span>|<span data-ttu-id="4be15-153">Sequência usada para gerar identificações de instrução.</span><span class="sxs-lookup"><span data-stu-id="4be15-153">Sequence used to generate statement IDs.</span></span>|  
|<span data-ttu-id="4be15-154">HREPL</span><span class="sxs-lookup"><span data-stu-id="4be15-154">HREPL</span></span>|<span data-ttu-id="4be15-155">Pacote e corpo de pacote</span><span class="sxs-lookup"><span data-stu-id="4be15-155">Package and Package Body</span></span>|<span data-ttu-id="4be15-156">Código de suporte a pacote de Publicador criado no Publicador.</span><span class="sxs-lookup"><span data-stu-id="4be15-156">Package of Publisher support code that is created at the Publisher.</span></span>|  
|<span data-ttu-id="4be15-157">MSSQLSERVERDISTRIBUTOR</span><span class="sxs-lookup"><span data-stu-id="4be15-157">MSSQLSERVERDISTRIBUTOR</span></span>|<span data-ttu-id="4be15-158">Sinônimo público</span><span class="sxs-lookup"><span data-stu-id="4be15-158">Public Synonym</span></span>|<span data-ttu-id="4be15-159">Sinônimo público para a tabela HREPL_Distributor.</span><span class="sxs-lookup"><span data-stu-id="4be15-159">Public synonym for the HREPL_Distributor table.</span></span> <span data-ttu-id="4be15-160">Se você configura um Distribuidor para usar com um Editor Oracle e esse sinônimo já existe no banco de dados, ele é descartado e recriado.</span><span class="sxs-lookup"><span data-stu-id="4be15-160">If you configure a Distributor to use with an Oracle Publisher, and this synonym already exists in the database, it is dropped and recreated.</span></span><br /><br /> <span data-ttu-id="4be15-161">Descartar o sinônimo público e o usuário de replicação Oracle configurado usando a opção CASCADE remove todos os objetos de replicação do Editor Oracle.</span><span class="sxs-lookup"><span data-stu-id="4be15-161">Dropping the public synonym and the configured Oracle replication user with the CASCADE option removes all replication objects from the Oracle Publisher.</span></span>|  
|<span data-ttu-id="4be15-162">HREPL_Len_I_J_K</span><span class="sxs-lookup"><span data-stu-id="4be15-162">HREPL_Len_I_J_K</span></span>|<span data-ttu-id="4be15-163">Função</span><span class="sxs-lookup"><span data-stu-id="4be15-163">Function</span></span>|<span data-ttu-id="4be15-164">Função definida fora do código de pacote de publicação Oracle, usada para consultar o comprimento de uma coluna LONG (usada ao gerar comandos com parâmetros para tabelas com colunas LONG publicadas).</span><span class="sxs-lookup"><span data-stu-id="4be15-164">Function defined outside the Oracle publishing package code, used to query for the length of a LONG column (used when generating parameterized commands for tables with published LONG columns).</span></span> <span data-ttu-id="4be15-165">Uma função é criada para cada tabela publicada com uma coluna LONG.</span><span class="sxs-lookup"><span data-stu-id="4be15-165">A function is created for each published table with a LONG column.</span></span>|  
|<span data-ttu-id="4be15-166">HREPL_DropPublisher</span><span class="sxs-lookup"><span data-stu-id="4be15-166">HREPL_DropPublisher</span></span>|<span data-ttu-id="4be15-167">Procedimento</span><span class="sxs-lookup"><span data-stu-id="4be15-167">Procedure</span></span>|<span data-ttu-id="4be15-168">Procedimento definido fora do código de pacote de publicação Oracle, usado para descartar o Editor Oracle.</span><span class="sxs-lookup"><span data-stu-id="4be15-168">Procedure defined outside the Oracle publishing package code, used to drop the Oracle Publisher.</span></span>|  
|<span data-ttu-id="4be15-169">HREPL_ExecuteCommand</span><span class="sxs-lookup"><span data-stu-id="4be15-169">HREPL_ExecuteCommand</span></span>|<span data-ttu-id="4be15-170">Procedimento</span><span class="sxs-lookup"><span data-stu-id="4be15-170">Procedure</span></span>|<span data-ttu-id="4be15-171">Procedimento definido fora do código de pacote de publicação Oracle, usado para executar um comando no Publicador.</span><span class="sxs-lookup"><span data-stu-id="4be15-171">Procedure defined outside the Oracle publishing package code, used to execute a command at the Publisher.</span></span>|  
|<span data-ttu-id="4be15-172">HREPL_ArticleN_Trigger_Row</span><span class="sxs-lookup"><span data-stu-id="4be15-172">HREPL_ArticleN_Trigger_Row</span></span>|<span data-ttu-id="4be15-173">Gatilho</span><span class="sxs-lookup"><span data-stu-id="4be15-173">Trigger</span></span>|<span data-ttu-id="4be15-174">Gatilho gerado para cada tabela publicada, usado para controlar alterações de linha.</span><span class="sxs-lookup"><span data-stu-id="4be15-174">Trigger generated for each published table, used to track row changes.</span></span>|  
|<span data-ttu-id="4be15-175">HREPL_ArticleN_Trigger_Stmt</span><span class="sxs-lookup"><span data-stu-id="4be15-175">HREPL_ArticleN_Trigger_Stmt</span></span>|<span data-ttu-id="4be15-176">Gatilho</span><span class="sxs-lookup"><span data-stu-id="4be15-176">Trigger</span></span>|<span data-ttu-id="4be15-177">Gatilho gerado para cada tabela publicado, usado para controlar alterações de nível de instrução.</span><span class="sxs-lookup"><span data-stu-id="4be15-177">Trigger generated for each published table, used to track statement level changes.</span></span>|  
|<span data-ttu-id="4be15-178">HREPL_Article_I_J</span><span class="sxs-lookup"><span data-stu-id="4be15-178">HREPL_Article_I_J</span></span>|<span data-ttu-id="4be15-179">Visualizar</span><span class="sxs-lookup"><span data-stu-id="4be15-179">View</span></span>|<span data-ttu-id="4be15-180">Exibição criada para cada tabela publicada, usada para consultar a tabela publicada.</span><span class="sxs-lookup"><span data-stu-id="4be15-180">View created for each published table, used to query the published table.</span></span>|  
|<span data-ttu-id="4be15-181">HREPL_Log_I_J_K</span><span class="sxs-lookup"><span data-stu-id="4be15-181">HREPL_Log_I_J_K</span></span>|<span data-ttu-id="4be15-182">Visualizar</span><span class="sxs-lookup"><span data-stu-id="4be15-182">View</span></span>|<span data-ttu-id="4be15-183">Exibição criada para cada tabela publicada, usada para consultar a tabela de controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="4be15-183">View created for each published table, used to query the change tracking table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4be15-184">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4be15-184">See Also</span></span>  
 <span data-ttu-id="4be15-185">[Configurar um Publicador Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="4be15-185">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 <span data-ttu-id="4be15-186">[Glossário de termos para publicações Oracle](glossary-of-terms-for-oracle-publishing.md) </span><span class="sxs-lookup"><span data-stu-id="4be15-186">[Glossary of Terms for Oracle Publishing](glossary-of-terms-for-oracle-publishing.md) </span></span>  
 [<span data-ttu-id="4be15-187">Visão geral da publicação do Oracle</span><span class="sxs-lookup"><span data-stu-id="4be15-187">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  