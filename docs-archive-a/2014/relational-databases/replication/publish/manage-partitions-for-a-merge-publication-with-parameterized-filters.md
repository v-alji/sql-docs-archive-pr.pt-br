---
title: Gerenciar partições de uma publicação de mesclagem com filtros com parâmetros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- partitions [SQL Server replication]
- merge replication partitions [SQL Server replication], SQL Server Management Studio
- parameterized filters [SQL Server replication], partition management
ms.assetid: fb5566fe-58c5-48f7-8464-814ea78e6221
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 983b02865c0564919259f896bf09d8bdb0cd969f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569338"
---
# <a name="manage-partitions-for-a-merge-publication-with-parameterized-filters"></a><span data-ttu-id="0195b-102">Gerenciar partições para uma publicação de mesclagem com filtros com parâmetros</span><span class="sxs-lookup"><span data-stu-id="0195b-102">Manage Partitions for a Merge Publication with Parameterized Filters</span></span>
  <span data-ttu-id="0195b-103">Este tópico descreve como gerenciar partições para uma publicação de mesclagem com filtros com parâmetros no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="0195b-103">This topic describes how to manage partitions for a merge publication with parameterized filters in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span> <span data-ttu-id="0195b-104">Filtros de linha com parâmetros podem ser usados para gerar partições não sobrepostas.</span><span class="sxs-lookup"><span data-stu-id="0195b-104">Parameterized row filters can be used to generate nonoverlapping partitions.</span></span> <span data-ttu-id="0195b-105">Essas partições podem ser restringidas de forma que só uma assinatura receba uma determinada partição.</span><span class="sxs-lookup"><span data-stu-id="0195b-105">These partitions can be restricted so that only one subscription receives a given partition.</span></span> <span data-ttu-id="0195b-106">Nesses casos, um grande número de assinantes resultará em um grande número de partições, que por sua vez, exige um número igual de instantâneos particionados.</span><span class="sxs-lookup"><span data-stu-id="0195b-106">In these cases, a large number of subscribers will result in a large number of partitions, which in turn requires an equal number of partitioned snapshots.</span></span> <span data-ttu-id="0195b-107">Para obter mais informações, consulte [Filtros de linha com parâmetros](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="0195b-107">For more information, see [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 <span data-ttu-id="0195b-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="0195b-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0195b-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="0195b-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0195b-110">Recomendações</span><span class="sxs-lookup"><span data-stu-id="0195b-110">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="0195b-111">**Para gerenciar partições para uma publicação de mesclagem com filtros com parâmetros, usando:**</span><span class="sxs-lookup"><span data-stu-id="0195b-111">**To manage partitions for a merge publication with parameterized filters, using:**</span></span>  
  
     [<span data-ttu-id="0195b-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0195b-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0195b-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0195b-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="0195b-114">RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="0195b-114">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0195b-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0195b-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="0195b-116">Recomendações</span><span class="sxs-lookup"><span data-stu-id="0195b-116">Recommendations</span></span>  
  
-   <span data-ttu-id="0195b-117">Se você fizer um script de topologia de replicação, o que é recomendado, os scripts de publicação contêm as chamadas de procedimento armazenado para criar partições de dados.</span><span class="sxs-lookup"><span data-stu-id="0195b-117">If you script a replication topology, which is recommended, publication scripts contain the stored procedure calls to create data partitions.</span></span> <span data-ttu-id="0195b-118">O script fornece uma referência para as partições criadas e um modo para recriar uma ou mais partições, caso seja necessário.</span><span class="sxs-lookup"><span data-stu-id="0195b-118">The script provides a reference for the partitions created and a way in which to re-create one or more partitions if necessary.</span></span> <span data-ttu-id="0195b-119">Para obter mais informações, consulte [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="0195b-119">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
-   <span data-ttu-id="0195b-120">Quando uma publicação tiver filtros com parâmetros que geram assinaturas com partições não sobrepostas ou se uma assinatura específica estiver perdida e necessitar de nova criação, faça o seguinte: remova a partição que estava com assinatura, recrie a assinatura e, em seguida, recrie a partição.</span><span class="sxs-lookup"><span data-stu-id="0195b-120">When a publication has parameterized filters that yield subscriptions with nonoverlapping partitions, and if a particular subscription is lost and needs to be re-created, you must do the following: remove the partition that was subscribed to, re-create the subscription, and then re-create the partition.</span></span> <span data-ttu-id="0195b-121">Para obter mais informações, consulte [Filtros de linha com parâmetros](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="0195b-121">For more information, see [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span> <span data-ttu-id="0195b-122">A replicação gera scripts de criação para as partições de Assinante existentes quando um script de criação de publicação é gerado.</span><span class="sxs-lookup"><span data-stu-id="0195b-122">Replication generates creation scripts for existing Subscriber partitions when a publication creation script is generated.</span></span> <span data-ttu-id="0195b-123">Para obter mais informações, consulte [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="0195b-123">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0195b-124">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0195b-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="0195b-125">Gerencie as partições na página **Partições de Dados** da caixa de diálogo **Propriedades da Publicação – \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="0195b-125">Manage partitions on the **Data Partitions** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="0195b-126">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0195b-126">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="0195b-127">Nessa página você pode: criar e excluir partições, permitir que Assinantes iniciem a geração e entrega de instantâneo, gerar instantâneos para uma ou mais partições e limpar instantâneos.</span><span class="sxs-lookup"><span data-stu-id="0195b-127">On this page you can: create and delete partitions; allow Subscribers to initiate snapshot generation and delivery; generate snapshots for one or more partitions; and clean up snapshots.</span></span>  
  
#### <a name="to-create-a-partition"></a><span data-ttu-id="0195b-128">Para criar uma partição</span><span class="sxs-lookup"><span data-stu-id="0195b-128">To create a partition</span></span>  
  
1.  <span data-ttu-id="0195b-129">Na página **Partições de Dados** da caixa de diálogo **Propriedades da Publicação – \<Publication>** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0195b-129">On the **Data Partitions** page of the **Publication Properties - \<Publication>** dialog box, click **Add**.</span></span>  
  
2.  <span data-ttu-id="0195b-130">Na caixa de diálogo **Adicionar Partição de Dados** coloque o valor para **HOST_NAME()** e/ou o valor **SUSER_SNAME()** associado com a partição que você quer criar.</span><span class="sxs-lookup"><span data-stu-id="0195b-130">In the **Add Data Partition** dialog box, enter a value for the **HOST_NAME()** and/or **SUSER_SNAME()** value associated with the partition you want to create.</span></span>  
  
3.  <span data-ttu-id="0195b-131">Especifique, opcionalmente, um cronograma para atualizar instantâneos:</span><span class="sxs-lookup"><span data-stu-id="0195b-131">Optionally specify a schedule for refreshing snapshots:</span></span>  
  
    1.  <span data-ttu-id="0195b-132">Selecione **Agendar o Snapshot Agent para que esta partição seja executada no(s) seguinte(s) horário(s):**</span><span class="sxs-lookup"><span data-stu-id="0195b-132">Select **Schedule the Snapshot Agent for this partition to run at the following time(s)**</span></span>  
  
    2.  <span data-ttu-id="0195b-133">Aceite o cronograma padrão para atualizar instantâneos ou clique em **Alterar** para especificar um cronograma diferente.</span><span class="sxs-lookup"><span data-stu-id="0195b-133">Accept the default schedule for refreshing snapshots, or click **Change** to specify a different schedule.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-delete-a-partition"></a><span data-ttu-id="0195b-134">Para excluir uma partição</span><span class="sxs-lookup"><span data-stu-id="0195b-134">To delete a partition</span></span>  
  
1.  <span data-ttu-id="0195b-135">Na página **Partições de Dados** , selecione uma partição na grade.</span><span class="sxs-lookup"><span data-stu-id="0195b-135">On the **Data Partitions** page, select a partition in the grid.</span></span>  
  
2.  <span data-ttu-id="0195b-136">Clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="0195b-136">Click **Delete**.</span></span>  
  
#### <a name="to-allow-subscribers-to-initiate-snapshot-generation-and-delivery"></a><span data-ttu-id="0195b-137">Para permitir que os Assinantes iniciem a geração e entrega de instantâneo</span><span class="sxs-lookup"><span data-stu-id="0195b-137">To allow Subscribers to initiate snapshot generation and delivery</span></span>  
  
1.  <span data-ttu-id="0195b-138">Na página **Partições de Dados** selecione **Definir automaticamente uma partição e gerar um instantâneo, se necessário, quando um novo Assinante tentar sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="0195b-138">On the **Data Partitions** page, select **Automatically define a partition and generate a snapshot if needed when a new Subscriber tries to synchronize**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-generate-a-snapshot-for-a-partition"></a><span data-ttu-id="0195b-139">Para gerar um instantâneo para uma partição</span><span class="sxs-lookup"><span data-stu-id="0195b-139">To generate a snapshot for a partition</span></span>  
  
1.  <span data-ttu-id="0195b-140">Na página **Partições de Dados** , selecione uma partição na grade.</span><span class="sxs-lookup"><span data-stu-id="0195b-140">On the **Data Partitions** page, select a partition in the grid.</span></span>  
  
2.  <span data-ttu-id="0195b-141">Clique em **Gerar os instantâneos selecionados agora**</span><span class="sxs-lookup"><span data-stu-id="0195b-141">Click **Generate the selected snapshots now**.</span></span>  
  
#### <a name="to-clean-up-a-snapshot-for-a-partition"></a><span data-ttu-id="0195b-142">Limpar um instantâneo para uma partição</span><span class="sxs-lookup"><span data-stu-id="0195b-142">To clean up a snapshot for a partition</span></span>  
  
1.  <span data-ttu-id="0195b-143">Na página **Partições de Dados** , selecione uma partição na grade.</span><span class="sxs-lookup"><span data-stu-id="0195b-143">On the **Data Partitions** page, select a partition in the grid.</span></span>  
  
2.  <span data-ttu-id="0195b-144">Clique em **Limpar os instantâneos existentes**.</span><span class="sxs-lookup"><span data-stu-id="0195b-144">Click **Clean up the existing snapshots**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0195b-145">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0195b-145">Using Transact-SQL</span></span>  
 <span data-ttu-id="0195b-146">Para administrar melhor uma publicação com filtros com parâmetros, você pode enumerar programaticamente as partições existentes que usam procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="0195b-146">To better manage a publication with parameterized filters, you can programmatically enumerate the existing partitions using replication stored procedures.</span></span> <span data-ttu-id="0195b-147">Você também pode criar e excluir partições existentes.</span><span class="sxs-lookup"><span data-stu-id="0195b-147">You can also create and delete existing partitions.</span></span> <span data-ttu-id="0195b-148">Podem ser obtidas as seguintes informações a respeito das partições existentes:</span><span class="sxs-lookup"><span data-stu-id="0195b-148">The following information on existing partitions can be obtained:</span></span>  
  
-   <span data-ttu-id="0195b-149">Como uma partição é filtrada (usando [SUSER_SNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/suser-sname-transact-sql) ou [HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="0195b-149">How a partition is filtered (using [SUSER_SNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/suser-sname-transact-sql) or [HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql)).</span></span>  
  
-   <span data-ttu-id="0195b-150">O nome do trabalho que gera um instantâneo particionado.</span><span class="sxs-lookup"><span data-stu-id="0195b-150">The name of the job that generates a partitioned snapshot.</span></span>  
  
-   <span data-ttu-id="0195b-151">A última vez que um trabalho de instantâneo particionado foi executado.</span><span class="sxs-lookup"><span data-stu-id="0195b-151">The last time that a partitioned snapshot job ran.</span></span>  
  
 <span data-ttu-id="0195b-152">Enquanto a segunda parte do instantâneo de duas partes pode ser gerada sob solicitação quando uma nova assinatura for incializada, os procedimentos abaixo permitem a você controlar o modo que é gerado o instantâneo e como pré-gerar esse instantâneo quando for mais conveniente.</span><span class="sxs-lookup"><span data-stu-id="0195b-152">While the second part of the two-part snapshot can be generated on-demand when a new subscription is initialized, the procedures below enable you to control how this snapshot is generated and to pre-generate this snapshot when it is most convenient.</span></span> <span data-ttu-id="0195b-153">Para obter mais informações, consulte [Snapshots for Merge Publications with Parameterized Filters](../snapshots-for-merge-publications-with-parameterized-filters.md).</span><span class="sxs-lookup"><span data-stu-id="0195b-153">For more information, see [Snapshots for Merge Publications with Parameterized Filters](../snapshots-for-merge-publications-with-parameterized-filters.md).</span></span>  
  
#### <a name="to-view-information-on-existing-partitions"></a><span data-ttu-id="0195b-154">Para exibir informações sobre partições existentes</span><span class="sxs-lookup"><span data-stu-id="0195b-154">To view information on existing partitions</span></span>  
  
1.  <span data-ttu-id="0195b-155">No Publicador do banco de dados de publicação, execute [sp_helpmergepartition &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepartition-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0195b-155">At the Publisher on the publication database, execute [sp_helpmergepartition &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepartition-transact-sql).</span></span> <span data-ttu-id="0195b-156">Especifique o nome da publicação para \*\* \@ publicação\*\*.</span><span class="sxs-lookup"><span data-stu-id="0195b-156">Specify the name of the publication for **\@publication**.</span></span> <span data-ttu-id="0195b-157">Adicional Especifique \*\* \@ suser_sname\*\* ou \*\* \@ HOST_NAME\*\* para retornar apenas informações com base em um único critério de filtragem.</span><span class="sxs-lookup"><span data-stu-id="0195b-157">(Optional) Specify **\@suser_sname** or **\@host_name** to return only information based on a single filtering criterion.</span></span>  
  
#### <a name="to-define-a-new-partition-and-generate-a-new-partitioned-snapshot"></a><span data-ttu-id="0195b-158">Para definir uma partição nova e gerar um instantâneo particionado novo</span><span class="sxs-lookup"><span data-stu-id="0195b-158">To define a new partition and generate a new partitioned snapshot</span></span>  
  
1.  <span data-ttu-id="0195b-159">No Publicador do banco de dados de publicação, execute [sp_addmergepartition &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepartition-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0195b-159">At the Publisher on the publication database, execute [sp_addmergepartition &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepartition-transact-sql).</span></span> <span data-ttu-id="0195b-160">Especifique o nome da publicação para \*\* \@ publicação\*\*e o valor com parâmetros que define a partição para um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="0195b-160">Specify the name of the publication for **\@publication**, and the parameterized value that defines the partition for one of the following:</span></span>  
  
    -   <span data-ttu-id="0195b-161">\*\* \@ SUSER_SNAME\*\* -quando o filtro com parâmetros é definido pelo valor retornado por [SUSER_SNAME &#40;&#41;do Transact-SQL ](/sql/t-sql/functions/suser-sname-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0195b-161">**\@suser_sname** - when the parameterized filter is defined by the value returned by [SUSER_SNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/suser-sname-transact-sql).</span></span>  
  
    -   <span data-ttu-id="0195b-162">\*\* \@ HOST_NAME\*\* -quando o filtro com parâmetros é definido pelo valor retornado por [HOST_NAME &#40;&#41;do Transact-SQL ](/sql/t-sql/functions/host-name-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0195b-162">**\@host_name** - when the parameterized filter is defined by the value returned by [HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql).</span></span>  
  
2.  <span data-ttu-id="0195b-163">Crie e inicialize o instantâneo com parâmetros para esta partição nova.</span><span class="sxs-lookup"><span data-stu-id="0195b-163">Create and initialize the parameterized snapshot for this new partition.</span></span> <span data-ttu-id="0195b-164">Para obter mais informações, consulte [Criar um instantâneo para uma publicação de mesclagem com filtros com parâmetros](../create-a-snapshot-for-a-merge-publication-with-parameterized-filters.md).</span><span class="sxs-lookup"><span data-stu-id="0195b-164">For more information, see [Create a Snapshot for a Merge Publication with Parameterized Filters](../create-a-snapshot-for-a-merge-publication-with-parameterized-filters.md).</span></span>  
  
#### <a name="to-delete-a-partition"></a><span data-ttu-id="0195b-165">Para excluir uma partição</span><span class="sxs-lookup"><span data-stu-id="0195b-165">To delete a partition</span></span>  
  
1.  <span data-ttu-id="0195b-166">No Publicador do banco de dados de publicação, execute [sp_dropmergepartition &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergepartition-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0195b-166">At the Publisher on the publication database, execute [sp_dropmergepartition &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergepartition-transact-sql).</span></span> <span data-ttu-id="0195b-167">Especifique o nome da publicação para \*\* \@ publicação\*\* e o valor com parâmetros que define a partição para um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="0195b-167">Specify the name of the publication for **\@publication** and the parameterized value that defines the partition for one of the following:</span></span>  
  
    -   <span data-ttu-id="0195b-168">\*\* \@ SUSER_SNAME\*\* -quando o filtro com parâmetros é definido pelo valor retornado por [SUSER_SNAME &#40;&#41;do Transact-SQL ](/sql/t-sql/functions/suser-sname-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0195b-168">**\@suser_sname** - when the parameterized filter is defined by the value returned by [SUSER_SNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/suser-sname-transact-sql).</span></span>  
  
    -   <span data-ttu-id="0195b-169">\*\* \@ HOST_NAME\*\* -quando o filtro com parâmetros é definido pelo valor retornado por [HOST_NAME &#40;&#41;do Transact-SQL ](/sql/t-sql/functions/host-name-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0195b-169">**\@host_name** - when the parameterized filter is defined by the value returned by [HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql).</span></span>  
  
     <span data-ttu-id="0195b-170">Isso também remove o trabalho de instantâneo e qualquer arquivo de instantâneo para a partição.</span><span class="sxs-lookup"><span data-stu-id="0195b-170">This also removes the snapshot job and any snapshot files for the partition.</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="0195b-171">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="0195b-171">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="0195b-172">Para gerenciar melhor uma publicação com filtros com parâmetros, você pode criar programaticamente novas partições de Assinante, enumerar as partições de Assinante existentes e excluir partições de Assinante usando RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="0195b-172">To better manage a publication with parameterized filters, you can programmatically create new Subscriber partitions, enumerate the existing Subscriber partitions, and delete Subscriber partitions by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="0195b-173">Para obter informações sobre como criar partições de Assinante, consulte [Criar um instantâneo para uma publicação de mesclagem com filtros com parâmetros](../create-a-snapshot-for-a-merge-publication-with-parameterized-filters.md).</span><span class="sxs-lookup"><span data-stu-id="0195b-173">For information about how to create Subscriber partitions, see [Create a Snapshot for a Merge Publication with Parameterized Filters](../create-a-snapshot-for-a-merge-publication-with-parameterized-filters.md).</span></span> <span data-ttu-id="0195b-174">As informações a seguir a respeito das partições existentes podem ser obtidas:</span><span class="sxs-lookup"><span data-stu-id="0195b-174">The following information about existing partitions can be obtained:</span></span>  
  
-   <span data-ttu-id="0195b-175">A função do valor e da filtragem sobre a qual a partição está baseada.</span><span class="sxs-lookup"><span data-stu-id="0195b-175">The value and filtering function upon which the partition is based.</span></span>  
  
-   <span data-ttu-id="0195b-176">O nome do trabalho que gera um instantâneo com parâmetros para o Assinante.</span><span class="sxs-lookup"><span data-stu-id="0195b-176">The name of the job that generates a parameterized snapshot for the Subscriber.</span></span>  
  
-   <span data-ttu-id="0195b-177">A última vez em que um trabalho de instantâneo com parâmetros foi executado.</span><span class="sxs-lookup"><span data-stu-id="0195b-177">The last time that a parameterized snapshot job ran.</span></span>  
  
#### <a name="to-view-information-on-existing-partitions"></a><span data-ttu-id="0195b-178">Para exibir informações sobre partições existentes</span><span class="sxs-lookup"><span data-stu-id="0195b-178">To view information on existing partitions</span></span>  
  
1.  <span data-ttu-id="0195b-179">Crie uma conexão com o Publicador usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="0195b-179">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="0195b-180">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.MergePublication>.</span><span class="sxs-lookup"><span data-stu-id="0195b-180">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePublication> class.</span></span> <span data-ttu-id="0195b-181">Defina as propriedades <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> e <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> para a publicação, e a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> para a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> criada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="0195b-181">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> created in step 1.</span></span>  
  
3.  <span data-ttu-id="0195b-182">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="0195b-182">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="0195b-183">Se esse método retornar `false`, as propriedades de publicação na etapa 2 foram definidas incorretamente ou a publicação não existe.</span><span class="sxs-lookup"><span data-stu-id="0195b-183">If this method returns `false`, either the publication properties in step 2 were defined incorrectly or the publication does not exist.</span></span>  
  
4.  <span data-ttu-id="0195b-184">Chame o método <xref:Microsoft.SqlServer.Replication.MergePublication.EnumMergePartitions%2A> e passe o resultado para uma matriz de objetos <xref:Microsoft.SqlServer.Replication.MergePartition> .</span><span class="sxs-lookup"><span data-stu-id="0195b-184">Call the <xref:Microsoft.SqlServer.Replication.MergePublication.EnumMergePartitions%2A> method, and pass the result to an array of <xref:Microsoft.SqlServer.Replication.MergePartition> objects.</span></span>  
  
5.  <span data-ttu-id="0195b-185">Para cada objeto <xref:Microsoft.SqlServer.Replication.MergePartition> na matriz, obtenha as propriedades de interesse.</span><span class="sxs-lookup"><span data-stu-id="0195b-185">For each <xref:Microsoft.SqlServer.Replication.MergePartition> object in the array, get any properties of interest.</span></span>  
  
#### <a name="to-delete-existing-partitions"></a><span data-ttu-id="0195b-186">Para excluir partições existentes</span><span class="sxs-lookup"><span data-stu-id="0195b-186">To delete existing partitions</span></span>  
  
1.  <span data-ttu-id="0195b-187">Crie uma conexão com o Publicador usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="0195b-187">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="0195b-188">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.MergePublication>.</span><span class="sxs-lookup"><span data-stu-id="0195b-188">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePublication> class.</span></span> <span data-ttu-id="0195b-189">Defina as propriedades <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> e <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> para a publicação, e a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> para a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> criada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="0195b-189">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> created in step 1.</span></span>  
  
3.  <span data-ttu-id="0195b-190">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="0195b-190">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="0195b-191">Se esse método retornar `false`, as propriedades de publicação na etapa 2 foram definidas incorretamente ou a publicação não existe.</span><span class="sxs-lookup"><span data-stu-id="0195b-191">If this method returns `false`, either the publication properties in step 2 were defined incorrectly or the publication does not exist.</span></span>  
  
4.  <span data-ttu-id="0195b-192">Chame o método <xref:Microsoft.SqlServer.Replication.MergePublication.EnumMergePartitions%2A> e passe o resultado para uma matriz de objetos <xref:Microsoft.SqlServer.Replication.MergePartition> .</span><span class="sxs-lookup"><span data-stu-id="0195b-192">Call the <xref:Microsoft.SqlServer.Replication.MergePublication.EnumMergePartitions%2A> method, and pass the result to an array of <xref:Microsoft.SqlServer.Replication.MergePartition> objects.</span></span>  
  
5.  <span data-ttu-id="0195b-193">Para cada objeto <xref:Microsoft.SqlServer.Replication.MergePartition> na matriz, determine se a partição deve ser excluída.</span><span class="sxs-lookup"><span data-stu-id="0195b-193">For each <xref:Microsoft.SqlServer.Replication.MergePartition> object in the array, determine whether the partition should be deleted.</span></span> <span data-ttu-id="0195b-194">Normalmente, essa decisão se baseia no valor da propriedade <xref:Microsoft.SqlServer.Replication.MergePartition.DynamicFilterLogin%2A> ou da propriedade <xref:Microsoft.SqlServer.Replication.MergePartition.DynamicFilterHostName%2A> .</span><span class="sxs-lookup"><span data-stu-id="0195b-194">This decision is usually based on the value of the <xref:Microsoft.SqlServer.Replication.MergePartition.DynamicFilterLogin%2A> property or the <xref:Microsoft.SqlServer.Replication.MergePartition.DynamicFilterHostName%2A> property.</span></span>  
  
6.  <span data-ttu-id="0195b-195">Chame o método <xref:Microsoft.SqlServer.Replication.MergePublication.RemoveMergePartition%2A> no objeto <xref:Microsoft.SqlServer.Replication.MergePublication> da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="0195b-195">Call the <xref:Microsoft.SqlServer.Replication.MergePublication.RemoveMergePartition%2A> method on the <xref:Microsoft.SqlServer.Replication.MergePublication> object from step 2.</span></span> <span data-ttu-id="0195b-196">Passe o objeto <xref:Microsoft.SqlServer.Replication.MergePartition> da etapa 5.</span><span class="sxs-lookup"><span data-stu-id="0195b-196">Pass the <xref:Microsoft.SqlServer.Replication.MergePartition> object from step 5.</span></span>  
  
7.  <span data-ttu-id="0195b-197">Repita a etapa 6 para cada partição excluída.</span><span class="sxs-lookup"><span data-stu-id="0195b-197">Repeat step 6 for each partition that is deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0195b-198">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0195b-198">See Also</span></span>  
 <span data-ttu-id="0195b-199">[Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md) </span><span class="sxs-lookup"><span data-stu-id="0195b-199">[Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md) </span></span>  
 [<span data-ttu-id="0195b-200">Snapshots for Merge Publications with Parameterized Filters</span><span class="sxs-lookup"><span data-stu-id="0195b-200">Snapshots for Merge Publications with Parameterized Filters</span></span>](../snapshots-for-merge-publications-with-parameterized-filters.md)  
  
  