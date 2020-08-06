---
title: Preencher índices de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- index populations [full-text search]
- incremental populations [full-text search]
- populations [full-text search]
- full-text search [SQL Server], populations
- crawls [full-text search]
- automatic full-text index updates
- change tracking-based populations [full-text search]
- manual updates [full-text search]
- manual populations [full-text search]
- auto populations [full-text search]
- full-text indexes [SQL Server], key column
- full populations [full-text search]
- full-text indexes [SQL Server], populations
ms.assetid: 76767b20-ef55-49ce-8dc4-e77cb8ff618a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9ab93a3514fa260c8c3836da85c767da3c3051a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581734"
---
# <a name="populate-full-text-indexes"></a><span data-ttu-id="1a180-102">Popular índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="1a180-102">Populate Full-Text Indexes</span></span>
  <span data-ttu-id="1a180-103">A criação e a manutenção de um índice de texto completo envolvem popular o índice usando um processo chamado *população* (também conhecido como *rastreamento*).</span><span class="sxs-lookup"><span data-stu-id="1a180-103">Creating and maintaining a full-text index involves populating the index by using a process called a *population* (also known as a *crawl*).</span></span>  
  
##  <a name="types-of-population"></a><a name="types"></a><span data-ttu-id="1a180-104">Tipos de população</span><span class="sxs-lookup"><span data-stu-id="1a180-104">Types of Population</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="1a180-105">o dá suporte aos seguintes tipos de população: população completa, população automática baseada em controle de alterações ou preenchimento manual e população incremental baseada em carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="1a180-105">supports the following types of population: full population, change tracking-based automatic or manual population, and incremental timestamp-based population.</span></span>  
  
### <a name="full-population"></a><span data-ttu-id="1a180-106">População completa</span><span class="sxs-lookup"><span data-stu-id="1a180-106">Full Population</span></span>  
 <span data-ttu-id="1a180-107">Durante uma população completa, entradas de índice são criadas para todas as linhas de uma tabela ou exibição indexada.</span><span class="sxs-lookup"><span data-stu-id="1a180-107">During a full population, index entries are built for all the rows of a table or indexed view.</span></span> <span data-ttu-id="1a180-108">Uma população completa de um índice de texto completo cria entradas de índice para todas as linhas da tabela base ou da exibição indexada.</span><span class="sxs-lookup"><span data-stu-id="1a180-108">A full population of a full-text index, builds index entries for all the rows of the base table or indexed view.</span></span>  
  
 <span data-ttu-id="1a180-109">Por padrão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] popula totalmente um novo índice de texto completo assim que ele é criado.</span><span class="sxs-lookup"><span data-stu-id="1a180-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] populates a new full-text index fully as soon as it is created.</span></span> <span data-ttu-id="1a180-110">No entanto, uma população completa pode consumir recursos consideráveis.</span><span class="sxs-lookup"><span data-stu-id="1a180-110">However, a full population can consume a significant amount of resources.</span></span> <span data-ttu-id="1a180-111">Portanto, quando você criar um índice de texto completo durante períodos de pico, uma prática recomendada será atrasar a população completa até uma hora fora do horário de pico, principalmente se a tabela base de um índice de texto completo for grande.</span><span class="sxs-lookup"><span data-stu-id="1a180-111">Therefore, when creating a full-text index during peak periods, it is often a best practice to delay the full population until an off-peak time, particularly if the base table of an full-text index is large.</span></span> <span data-ttu-id="1a180-112">Todavia, o catálogo de texto completo ao qual o índice pertence não poderá ser utilizado até que todos os índices de texto completo estejam populados.</span><span class="sxs-lookup"><span data-stu-id="1a180-112">However, the full-text catalog to which the index belongs is not usable until all of its full-text indexes are populated.</span></span> <span data-ttu-id="1a180-113">Para criar um índice de texto completo sem populá-lo imediatamente, especifique a cláusula CHANGE_TRACKING OFF, NO POPULATION na instrução CREATE FULLTEXT INDEX.</span><span class="sxs-lookup"><span data-stu-id="1a180-113">To create a full-text index without populating it immediately, specify the CHANGE_TRACKING OFF, NO POPULATION clause in the CREATE FULLTEXT INDEX statement.</span></span> <span data-ttu-id="1a180-114">Se você especificar CHANGE_TRACKING MANUAL, o Mecanismo de Texto Completo usará a instrução.</span><span class="sxs-lookup"><span data-stu-id="1a180-114">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses statement.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="1a180-115">o não preencherá o novo índice de texto completo até que você execute uma instrução ALTER FULLTEXT INDEX usando a cláusula iniciar população completa ou iniciar população INCREMENTAL.</span><span class="sxs-lookup"><span data-stu-id="1a180-115">will not populate the new full-text index until you execute an ALTER FULLTEXT INDEX statement using the START FULL POPULATION or START INCREMENTAL POPULATION clause.</span></span> <span data-ttu-id="1a180-116">Para obter mais informações, consulte os exemplos “A.</span><span class="sxs-lookup"><span data-stu-id="1a180-116">For more information, see examples "A.</span></span> <span data-ttu-id="1a180-117">Criando um índice de texto completo sem executar uma população completa" e "B.</span><span class="sxs-lookup"><span data-stu-id="1a180-117">Creating a full-text index without running a full population" and "B.</span></span> <span data-ttu-id="1a180-118">Executando uma população completa em tabela", mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="1a180-118">Running a full population on table," later in this topic.</span></span>  
  

  
### <a name="change-tracking-based-population"></a><span data-ttu-id="1a180-119">População com base em controle de alterações</span><span class="sxs-lookup"><span data-stu-id="1a180-119">Change Tracking-Based Population</span></span>  
 <span data-ttu-id="1a180-120">Como opção, você pode usar o controle de alterações para manter um índice de texto completo após a população completa inicial.</span><span class="sxs-lookup"><span data-stu-id="1a180-120">Optionally, you can use change tracking to maintain a full-text index after its initial full population.</span></span> <span data-ttu-id="1a180-121">Há uma pequena sobrecarga associada ao controle de alterações porque o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mantém uma tabela em que controla as alterações feitas na tabela base desde a última população.</span><span class="sxs-lookup"><span data-stu-id="1a180-121">There is a small overhead associated with change tracking because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a table in which it tracks changes to the base table since the last population.</span></span> <span data-ttu-id="1a180-122">Quando é usado o controle de alterações, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mantém um registro das linhas da tabela base ou exibição indexada que foram modificadas por atualizações, exclusões ou inserções.</span><span class="sxs-lookup"><span data-stu-id="1a180-122">When change tracking is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a record of the rows in the base table or indexed view that have been modified by updates, deletes, or inserts.</span></span> <span data-ttu-id="1a180-123">As alterações de dados por meio de WRITETEXT e UPDATETEXT não são refletidas no índice de texto completo e não são coletadas com o controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="1a180-123">Data changes through WRITETEXT and UPDATETEXT are not reflected in the full-text index, and are not picked up with change tracking.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a180-124">Para tabelas que contêm uma coluna `timestamp`, você pode usar populações incrementais.</span><span class="sxs-lookup"><span data-stu-id="1a180-124">For tables containing a `timestamp` column, you can use incremental populations.</span></span>  
  
 <span data-ttu-id="1a180-125">Quando o controle de alterações é habilitado durante a criação do índice, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] popula completamente o novo índice de texto completo logo após sua criação.</span><span class="sxs-lookup"><span data-stu-id="1a180-125">When change tracking is enabled during index creation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fully populates the new full-text index immediately after it is created.</span></span> <span data-ttu-id="1a180-126">Consequentemente, as alterações são controladas e propagadas para o índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1a180-126">Thereafter, changes are tracked and propagated to the full-text index.</span></span> <span data-ttu-id="1a180-127">Há dois tipos de controle de alterações: automático (opção CHANGE_TRACKING AUTO) e manual (opção CHANGE_TRACKING MANUAL).</span><span class="sxs-lookup"><span data-stu-id="1a180-127">There are two types of change tracking, automatic (CHANGE_TRACKING AUTO option) and manual (CHANGE_TRACKING MANUAL option).</span></span> <span data-ttu-id="1a180-128">O controle de alterações automático é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="1a180-128">Automatic change tracking is the default behavior.</span></span>  
  
 <span data-ttu-id="1a180-129">O tipo de controle de alterações determina como o índice de texto completo é populado, como segue:</span><span class="sxs-lookup"><span data-stu-id="1a180-129">The type of change tracking determines how the full-text index is populated, as follows:</span></span>  
  
-   <span data-ttu-id="1a180-130">População automática</span><span class="sxs-lookup"><span data-stu-id="1a180-130">Automatic population</span></span>  
  
     <span data-ttu-id="1a180-131">Por padrão, ou se você especificar CHANGE_TRACKING AUTO, o Mecanismo de Texto Completo usa população automática no índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1a180-131">By default, or if you specify CHANGE_TRACKING AUTO, the Full-Text Engine uses automatic population on the full-text index.</span></span> <span data-ttu-id="1a180-132">Depois que a população completa inicial é concluída, as alterações são controladas à medida que os dados são modificados na tabela base, e as alterações controladas são propagadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1a180-132">After the initial full population completes, changes are tracked as data is modified in the base table, and the tracked changes are propagated automatically.</span></span> <span data-ttu-id="1a180-133">O índice de texto completo é atualizado em segundo plano, mas as alterações propagadas podem não ser refletidas imediatamente no índice.</span><span class="sxs-lookup"><span data-stu-id="1a180-133">The full-text index is updated in the background, however, so propagated changes might not be reflected immediately in the index.</span></span>  
  
     <span data-ttu-id="1a180-134">**Para configurar o controle de alterações com população automática**</span><span class="sxs-lookup"><span data-stu-id="1a180-134">**To set up tracking changes with automatic population**</span></span>  
  
    -   <span data-ttu-id="1a180-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql)... WITH CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="1a180-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING AUTO</span></span>  
  
    -   <span data-ttu-id="1a180-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql)... SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="1a180-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING AUTO</span></span>  
  
     <span data-ttu-id="1a180-137">Para obter mais informações, consulte o exemplo “E.</span><span class="sxs-lookup"><span data-stu-id="1a180-137">For more information, see example "E.</span></span> <span data-ttu-id="1a180-138">Alterando um índice de texto completo para usar o controle de alterações automáticas”, mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="1a180-138">Altering a full-text index to use automatic change tracking," later in this topic.</span></span>  
  
-   <span data-ttu-id="1a180-139">População manual</span><span class="sxs-lookup"><span data-stu-id="1a180-139">Manual population</span></span>  
  
     <span data-ttu-id="1a180-140">Se você especificar CHANGE_TRACKING MANUAL, o Mecanismo de Texto Completo usará população manual no índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1a180-140">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses manual population on the full-text index.</span></span> <span data-ttu-id="1a180-141">Depois que a população completa inicial é concluída, as alterações são controladas à medida que os dados são modificados na tabela base.</span><span class="sxs-lookup"><span data-stu-id="1a180-141">After the initial full population completes, changes are tracked as data is modified in the base table.</span></span> <span data-ttu-id="1a180-142">Porém, eles não serão propagados para o índice de texto completo até que você execute uma instrução ALTER FULLTEXT INDEX... Instrução START UPDATE POPULATION .</span><span class="sxs-lookup"><span data-stu-id="1a180-142">However, they are not propagated to the full-text index until you execute an ALTER FULLTEXT INDEX ... START UPDATE POPULATION statement.</span></span> <span data-ttu-id="1a180-143">É possível usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para chamar essa instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] periodicamente.</span><span class="sxs-lookup"><span data-stu-id="1a180-143">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to call this [!INCLUDE[tsql](../../includes/tsql-md.md)] statement periodically.</span></span>  
  
     <span data-ttu-id="1a180-144">**Para começar a controlar alterações com população manual**</span><span class="sxs-lookup"><span data-stu-id="1a180-144">**To start tracking changes with manual population**</span></span>  
  
    -   <span data-ttu-id="1a180-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql)... WITH CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="1a180-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING MANUAL</span></span>  
  
    -   <span data-ttu-id="1a180-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql)... SET CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="1a180-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING MANUAL</span></span>  
  
     <span data-ttu-id="1a180-147">Para obter mais informações, consulte o exemplo “C.</span><span class="sxs-lookup"><span data-stu-id="1a180-147">For more information, see examples "C.</span></span> <span data-ttu-id="1a180-148">Criando um índice de texto completo com controle de alterações manual" e "D.</span><span class="sxs-lookup"><span data-stu-id="1a180-148">Creating a full-text index with manual change tracking" and "D.</span></span> <span data-ttu-id="1a180-149">Executando uma população manual", posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="1a180-149">Running a manual population," later in this topic.</span></span>  
  
 <span data-ttu-id="1a180-150">**Para desativar o rastreamento de alterações**</span><span class="sxs-lookup"><span data-stu-id="1a180-150">**To turn off change tracking**</span></span>  
  
-   <span data-ttu-id="1a180-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql)... WITH CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="1a180-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING OFF</span></span>  
  
-   <span data-ttu-id="1a180-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql)... SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="1a180-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING OFF</span></span>  
  

  
### <a name="incremental-timestamp-based-population"></a><span data-ttu-id="1a180-153">População incremental baseada em carimbo de data e hora</span><span class="sxs-lookup"><span data-stu-id="1a180-153">Incremental Timestamp-Based Population</span></span>  
 <span data-ttu-id="1a180-154">Uma população incremental é um mecanismo alternativo para popular um índice de texto completo manualmente.</span><span class="sxs-lookup"><span data-stu-id="1a180-154">An incremental population is an alternative mechanism for manually populating a full-text index.</span></span> <span data-ttu-id="1a180-155">Você pode executar uma população incremental para um índice de texto completo que tem CHANGE_TRACKING definido como MANUAL ou OFF.</span><span class="sxs-lookup"><span data-stu-id="1a180-155">You can run an incremental population for a full-text index that has CHANGE_TRACKING set to MANUAL or OFF.</span></span> <span data-ttu-id="1a180-156">Se a primeira população em um índice de texto completo for uma população incremental, ele indexará todas as linhas, tornando-a equivalente a uma população completa.</span><span class="sxs-lookup"><span data-stu-id="1a180-156">If the first population on a full-text index is an incremental population, it indexes all rows, making it equivalent to a full population.</span></span>  
  
 <span data-ttu-id="1a180-157">O requisito para população incremental é que a tabela indexada deve ter uma coluna do tipo de dados `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="1a180-157">The requirement for incremental population is that the indexed table must have a column of the `timestamp` data type.</span></span> <span data-ttu-id="1a180-158">Se uma coluna `timestamp` não existir, a população incremental não poderá ser executada.</span><span class="sxs-lookup"><span data-stu-id="1a180-158">If a `timestamp` column does not exist, incremental population cannot be performed.</span></span> <span data-ttu-id="1a180-159">Uma solicitação para população incremental em uma tabela sem uma coluna `timestamp` resulta em uma operação de população completa.</span><span class="sxs-lookup"><span data-stu-id="1a180-159">A request for incremental population on a table without a `timestamp` column results in a full population operation.</span></span> <span data-ttu-id="1a180-160">Além disso, se nenhum metadado que afeta o índice de texto completo da tabela foi alterado desde a última população, as solicitações de população incremental serão implementadas como populações completas.</span><span class="sxs-lookup"><span data-stu-id="1a180-160">Also, if any metadata that affects the full-text index for the table has changed since the last population, incremental population requests are implemented as full populations.</span></span> <span data-ttu-id="1a180-161">Isso inclui alterações de metadados geradas pela alteração de qualquer coluna, índice ou definições de índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1a180-161">This includes metadata changes caused by altering any column, index, or full-text index definitions.</span></span>  
  
 <span data-ttu-id="1a180-162">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa a coluna `timestamp` para identificar linhas que foram alteradas desde a última população.</span><span class="sxs-lookup"><span data-stu-id="1a180-162">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the `timestamp` column to identify rows that have changed since the last population.</span></span> <span data-ttu-id="1a180-163">A população incremental então atualiza o índice de texto completo com linhas adicionadas, excluídas ou modificadas após a última população ou enquanto a última população estava em andamento.</span><span class="sxs-lookup"><span data-stu-id="1a180-163">The incremental population then updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="1a180-164">Se uma tabela tiver um volume alto de inserções, usar a população incremental poderá ser mais eficiente do que usar a população manual.</span><span class="sxs-lookup"><span data-stu-id="1a180-164">If a table experiences a high volume of inserts, using incremental population can be more efficient that using manual population.</span></span>  
  
 <span data-ttu-id="1a180-165">Ao término de uma população, o Mecanismo de Texto Completo registra um novo valor de `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="1a180-165">At the end of a population, the Full-Text Engine records a new `timestamp` value.</span></span> <span data-ttu-id="1a180-166">Esse valor é o maior valor de `timestamp` que o SQL Gatherer encontrou.</span><span class="sxs-lookup"><span data-stu-id="1a180-166">This value is the largest `timestamp` value that SQL Gatherer has encountered.</span></span> <span data-ttu-id="1a180-167">Esse valor será usado quando uma população incremental subsequente for iniciada.</span><span class="sxs-lookup"><span data-stu-id="1a180-167">This value will be used when a subsequent incremental population starts.</span></span>  
  
 <span data-ttu-id="1a180-168">Para executar uma população incremental, execute uma instrução ALTER FULLTEXT INDEX usando a cláusula START INCREMENTAL POPULATION.</span><span class="sxs-lookup"><span data-stu-id="1a180-168">To run an incremental population, execute an ALTER FULLTEXT INDEX statement using the START INCREMENTAL POPULATION clause.</span></span>  
  

  
##  <a name="examples-of-populating-full-text-indexes"></a><a name="examples"></a><span data-ttu-id="1a180-169">Exemplos de preenchimento de índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="1a180-169">Examples of Populating Full-Text Indexes</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a180-170">Os exemplos desta seção usam a tabela `Production.Document` ou `HumanResources.JobCandidate` do banco de dados de exemplo `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="1a180-170">The examples in this section use the `Production.Document` or `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
### <a name="a-creating-a-full-text-index-without-running-a-full-population"></a><span data-ttu-id="1a180-171">a.</span><span class="sxs-lookup"><span data-stu-id="1a180-171">A.</span></span> <span data-ttu-id="1a180-172">Criando um índice de texto completo sem executar uma população completa</span><span class="sxs-lookup"><span data-stu-id="1a180-172">Creating a full-text index without running a full population</span></span>  
 <span data-ttu-id="1a180-173">O exemplo a seguir cria um índice de texto completo na tabela `Production.Document` do banco de dados de exemplo `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="1a180-173">The following example creates a full-text index on the `Production.Document` table of the `AdventureWorks` sample database.</span></span> <span data-ttu-id="1a180-174">Este exemplo usa WITH CHANGE_TRACKING OFF, NO POPULATION para atrasar a população completa inicial.</span><span class="sxs-lookup"><span data-stu-id="1a180-174">This example uses WITH CHANGE_TRACKING OFF, NO POPULATION to delay the initial full population.</span></span>  
  
```  
CREATE UNIQUE INDEX ui_ukDoc ON Production.Document(DocumentID);  
CREATE FULLTEXT CATALOG AW_Production_FTCat;  
CREATE FULLTEXT INDEX ON Production.Document  
(  
    Document                         --Full-text index column name   
        TYPE COLUMN FileExtension    --Name of column that contains file type information  
        Language 1033                 --1033 is LCID for the English language  
)  
    KEY INDEX ui_ukDoc  
    ON AW_Production_FTCat  
    WITH CHANGE_TRACKING OFF, NO POPULATION;  
GO  
  
```  
  
### <a name="b-running-a-full-population-on-table"></a><span data-ttu-id="1a180-175">B.</span><span class="sxs-lookup"><span data-stu-id="1a180-175">B.</span></span> <span data-ttu-id="1a180-176">Executando uma população completa em tabela</span><span class="sxs-lookup"><span data-stu-id="1a180-176">Running a full population on table</span></span>  
 <span data-ttu-id="1a180-177">O exemplo a seguir executa uma população completa na tabela `Production.Document` do banco de dados de exemplo `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="1a180-177">The following example runs a full population on the `Production.Document` table of the `AdventureWorks` sample database.</span></span>  
  
```  
ALTER FULLTEXT INDEX ON Production.Document  
   START FULL POPULATION;  
```  
  
### <a name="c-creating-a-full-text-index-with-manual-change-tracking"></a><span data-ttu-id="1a180-178">C.</span><span class="sxs-lookup"><span data-stu-id="1a180-178">C.</span></span> <span data-ttu-id="1a180-179">Criando um índice de texto completo com controle de alterações manuais</span><span class="sxs-lookup"><span data-stu-id="1a180-179">Creating a full-text index with manual change tracking</span></span>  
 <span data-ttu-id="1a180-180">O exemplo a seguir cria um índice de texto completo que usará o controle de alterações com população manual na tabela `HumanResources.JobCandidate` do banco de dados de exemplo `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="1a180-180">The following example creates a full-text index that will use change tracking with manual population on the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE UNIQUE INDEX ui_ukJobCand ON HumanResources.JobCandidate(JobCandidateID);  
CREATE FULLTEXT CATALOG ft AS DEFAULT;  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate(Resume)   
   KEY INDEX ui_ukJobCand   
   WITH CHANGE_TRACKING=MANUAL;  
GO  
```  
  
### <a name="d-running-a-manual-population"></a><span data-ttu-id="1a180-181">D.</span><span class="sxs-lookup"><span data-stu-id="1a180-181">D.</span></span> <span data-ttu-id="1a180-182">Executando uma população manual</span><span class="sxs-lookup"><span data-stu-id="1a180-182">Running a manual population</span></span>  
 <span data-ttu-id="1a180-183">O exemplo a seguir executa uma população manual no índice de texto completo com controle de alterações da tabela `HumanResources.JobCandidate` do banco de dados de exemplo `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="1a180-183">The following example runs a manual population on the change-tracked full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate START UPDATE POPULATION;  
GO  
```  
  
### <a name="e-altering-a-full-text-index-to-use-automatic-change-tracking"></a><span data-ttu-id="1a180-184">E.</span><span class="sxs-lookup"><span data-stu-id="1a180-184">E.</span></span> <span data-ttu-id="1a180-185">Alterando um índice de texto completo para usar o controle de alterações automáticas</span><span class="sxs-lookup"><span data-stu-id="1a180-185">Altering a full-text index to use automatic change tracking</span></span>  
 <span data-ttu-id="1a180-186">O exemplo a seguir altera o índice de texto completo da tabela `HumanResources.JobCandidate` do banco de dados de exemplo `AdventureWorks` para usar o controle de alterações com população automática.</span><span class="sxs-lookup"><span data-stu-id="1a180-186">The following example changes the full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database to use change tracking with automatic population.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate SET CHANGE_TRACKING AUTO;  
GO   
```  
  

  
##  <a name="creating-or-changing-a-schedule-for-incremental-population"></a><a name="create"></a><span data-ttu-id="1a180-187">Criando ou alterando uma agenda para população incremental</span><span class="sxs-lookup"><span data-stu-id="1a180-187">Creating or Changing a Schedule for Incremental Population</span></span>  
  
#### <a name="to-create-or-change-a-schedule-for-incremental-population-in-management-studio"></a><span data-ttu-id="1a180-188">Para criar ou alterar uma agenda para população incremental no Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a180-188">To create or change a schedule for incremental population in Management Studio</span></span>  
  
1.  <span data-ttu-id="1a180-189">No Pesquisador de Objetos, expanda o servidor.</span><span class="sxs-lookup"><span data-stu-id="1a180-189">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="1a180-190">Expanda **Bancos de Dados**e expanda o banco de dados que contém o índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1a180-190">Expand **Databases**, and then expand the database that contains the full-text index.</span></span>  
  
3.  <span data-ttu-id="1a180-191">Expanda **Tabelas**.</span><span class="sxs-lookup"><span data-stu-id="1a180-191">Expand **Tables**.</span></span>  
  
 <span data-ttu-id="1a180-192">Clique com o botão direito do mouse na tabela em que o índice de texto completo está definido, selecione **Índice de Texto Completo**e, no menu de contexto **Índice de Texto Completo** , clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1a180-192">Right-click the table on which the full-text index is defined, select **Full-Text index**, and on the **Full-Text index** context menu, click **Properties**.</span></span> <span data-ttu-id="1a180-193">Este procedimento abre a caixa de diálogo **Propriedades do Índice de Texto Completo** .</span><span class="sxs-lookup"><span data-stu-id="1a180-193">This opens the **Full-text index Properties** dialog box.</span></span>  
  
1.  <span data-ttu-id="1a180-194">No painel **selecionar uma página** , selecione agendas.</span><span class="sxs-lookup"><span data-stu-id="1a180-194">In the **Select a page** pane, select Schedules.</span></span>  
  
     <span data-ttu-id="1a180-195">Use esta página para criar ou gerenciar agendas para um trabalho do SQL Server Agent que inicia uma população incremental de tabela na tabela base ou na exibição indexada do índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1a180-195">Use this page to create or manage schedules for a SQL Server Agent job that starts an incremental table population on the base table or indexed view of the full-text index.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1a180-196">Se a tabela base ou a exibição não contiver uma coluna do tipo de dados `timestamp`, uma população completa será executada.</span><span class="sxs-lookup"><span data-stu-id="1a180-196">If the base table or view does not contain a column of the `timestamp` data type, a full population is performed.</span></span>  
  
     <span data-ttu-id="1a180-197">As opções são as descritas a seguir:</span><span class="sxs-lookup"><span data-stu-id="1a180-197">The options are as follows:</span></span>  
  
    -   <span data-ttu-id="1a180-198">Para criar uma nova agenda, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="1a180-198">To create a new schedule, click **New**.</span></span>  
  
         <span data-ttu-id="1a180-199">Este procedimento abre a caixa de diálogo **Novo Agendamento da Tabela de Indexação de Texto Completo** , em que é possível criar um agendamento.</span><span class="sxs-lookup"><span data-stu-id="1a180-199">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can create a schedule.</span></span> <span data-ttu-id="1a180-200">Para salvar o agendamento, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a180-200">To save the schedule, click **OK**.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="1a180-201">Um trabalho do SQL Server Agent (Iniciar População Incremental da Tabela em *database_name*.*table_name*) é associado a um novo agendamento depois que você sai da caixa de diálogo **Propriedades do Índice de Texto Completo** .</span><span class="sxs-lookup"><span data-stu-id="1a180-201">A SQL Server Agent job (Start Incremental Table Population on *database_name*.*table_name*) is associated with a new schedule after you exit the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="1a180-202">Se você criar várias agendas para o índice de texto completo, todos eles usarão o mesmo trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a180-202">If you create multiple schedules for the full-text index, they all use the same job.</span></span>  
  
    -   <span data-ttu-id="1a180-203">Para alterar um agendamento, selecione-o e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1a180-203">To change a schedule, select it and click **Edit**.</span></span>  
  
         <span data-ttu-id="1a180-204">Este procedimento abre a caixa de diálogo **Novo Agendamento da Tabela de Indexação de Texto Completo** , em que é possível modificar o agendamento.</span><span class="sxs-lookup"><span data-stu-id="1a180-204">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can modify the schedule.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1a180-205">Para obter informações sobre como modificar um trabalho, veja [Modificar um trabalho](../../ssms/agent/modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="1a180-205">For information about modifying a job, see [Modify a Job](../../ssms/agent/modify-a-job.md).</span></span>  
  
    -   <span data-ttu-id="1a180-206">Para remover um agendamento, selecione-o e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="1a180-206">To remove a schedule, select it and click **Delete**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  

  
##  <a name="troubleshooting-errors-in-a-full-text-population-crawl"></a><a name="crawl"></a><span data-ttu-id="1a180-207">Solucionando problemas de erros em uma população de texto completo (rastreamento)</span><span class="sxs-lookup"><span data-stu-id="1a180-207">Troubleshooting Errors in a Full-Text Population (Crawl)</span></span>  
 <span data-ttu-id="1a180-208">Quando um erro ocorrer durante um rastreamento, o recurso de registro de rastreamento de pesquisa de texto completo cria e mantém um log de rastreamento, que é um texto sem-formatação.</span><span class="sxs-lookup"><span data-stu-id="1a180-208">When an error occurs during a crawl, the Full-Text Search crawl logging facility creates and maintains a crawl log, which is a plain text file.</span></span> <span data-ttu-id="1a180-209">Cada log de rastreamento corresponde a um catálogo de texto completo específico.</span><span class="sxs-lookup"><span data-stu-id="1a180-209">Each crawl log corresponds to a particular full-text catalog.</span></span> <span data-ttu-id="1a180-210">Por padrão, os logs de rastreamento para uma determinada instância, neste caso, a primeira instância, estão localizados na pasta %Arquivos de programas%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG.</span><span class="sxs-lookup"><span data-stu-id="1a180-210">By default crawl logs for a given instance, in this case, the first instance, are located in %ProgramFiles%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG folder.</span></span> <span data-ttu-id="1a180-211">O arquivo de log de rastreamento segue o seguinte esquema de nomeação:</span><span class="sxs-lookup"><span data-stu-id="1a180-211">The crawl log file follows the following naming scheme:</span></span>  
  
 <span data-ttu-id="1a180-212">SQLFT \<DatabaseID> \<FullTextCatalogID> . LOG [ \<n> ]</span><span class="sxs-lookup"><span data-stu-id="1a180-212">SQLFT\<DatabaseID>\<FullTextCatalogID>.LOG[\<n>]</span></span>  
  
 <`DatabaseID`>  
 <span data-ttu-id="1a180-213">A ID de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1a180-213">The ID of a database.</span></span><span data-ttu-id="1a180-214"> <`dbid`> é um número de cinco dígitos com zeros à esquerda.</span><span class="sxs-lookup"><span data-stu-id="1a180-214"> <`dbid`> is a five digit number with leading zeros.</span></span>  
  
 <`FullTextCatalogID`>  
 <span data-ttu-id="1a180-215">ID do catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1a180-215">Full-text catalog ID.</span></span><span data-ttu-id="1a180-216"> <`catid`> é um número de cinco dígitos com zeros à esquerda.</span><span class="sxs-lookup"><span data-stu-id="1a180-216"> <`catid`> is a five digit number with leading zeros.</span></span>  
  
 <`n`>  
 <span data-ttu-id="1a180-217">É um inteiro que indica um ou mais logs de rastreamento que existem do mesmo catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="1a180-217">Is an integer that indicates one or more crawl logs of the same full-text catalog exist.</span></span>  
  
 <span data-ttu-id="1a180-218">Por exemplo, SQLFT0000500008.2 é o arquivo de log de rastreamento para o banco de dados com o ID de banco de dados = 5 e ID de catálogo de texto completo = 8.</span><span class="sxs-lookup"><span data-stu-id="1a180-218">For example, SQLFT0000500008.2 is the crawl log file for a database with database ID = 5, and full-text catalog ID = 8.</span></span> <span data-ttu-id="1a180-219">O 2 no final do nome do arquivo indica que há dois arquivos de log de rastreamento para esse par de banco de dados/catálogo.</span><span class="sxs-lookup"><span data-stu-id="1a180-219">The 2 at the end of the file name indicates that there are two crawl log files for this database/catalog pair.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="1a180-220">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1a180-220">See Also</span></span>  
 <span data-ttu-id="1a180-221">[sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a180-221">[sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span></span>  
 <span data-ttu-id="1a180-222">[Iniciar a pesquisa de texto completo](get-started-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="1a180-222">[Get Started with Full-Text Search](get-started-with-full-text-search.md) </span></span>  
 <span data-ttu-id="1a180-223">[Criar e gerenciar índices de texto completo](create-and-manage-full-text-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="1a180-223">[Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) </span></span>  
 <span data-ttu-id="1a180-224">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a180-224">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="1a180-225">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a180-225">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  
