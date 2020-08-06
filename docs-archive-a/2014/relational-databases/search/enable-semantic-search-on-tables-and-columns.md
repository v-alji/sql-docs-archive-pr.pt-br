---
title: Habilitar a pesquisa semântica em tabelas e colunas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], enabling
ms.assetid: 895d220c-6749-4954-9dd3-2ea4c6a321ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f11ba654f7cc34f521990e8c420d41885d3c55b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681522"
---
# <a name="enable-semantic-search-on-tables-and-columns"></a><span data-ttu-id="a0c70-102">Habilitar a pesquisa semântica em tabelas e colunas</span><span class="sxs-lookup"><span data-stu-id="a0c70-102">Enable Semantic Search on Tables and Columns</span></span>
  <span data-ttu-id="a0c70-103">Descreve como habilitar ou desabilitar a indexação semântica estatística em colunas selecionadas que contêm documentos ou texto.</span><span class="sxs-lookup"><span data-stu-id="a0c70-103">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 <span data-ttu-id="a0c70-104">A pesquisa semântica estatística usa os índices que são criados pela Pesquisa de Texto Completo e cria índices adicionais.</span><span class="sxs-lookup"><span data-stu-id="a0c70-104">Statistical Semantic Search uses the indexes that are created by Full-Text Search, and creates additional indexes.</span></span> <span data-ttu-id="a0c70-105">Como resultado dessa dependência na pesquisa de texto completo, você cria um novo índice semântico ao definir um novo índice de texto completo ou ao alterar um índice de texto completo existente.</span><span class="sxs-lookup"><span data-stu-id="a0c70-105">As a result of this dependency on full-text search, you create a new semantic index when you define a new full-text index, or when you alter an existing full-text index.</span></span> <span data-ttu-id="a0c70-106">Você pode criar um novo índice semântico usando instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] , ou usando o Assistente para Indexação de Texto Completo e outras caixas de diálogo no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conforme descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a0c70-106">You can create a new semantic index by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or by using the Full-Text Indexing Wizard and other dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as described in this topic.</span></span>  
  
##  <a name="creating-a-semantic-index"></a><a name="BasicEnabling"></a><span data-ttu-id="a0c70-107">Criando um índice semântico</span><span class="sxs-lookup"><span data-stu-id="a0c70-107">Creating a Semantic Index</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-semantic-index"></a><a name="reqenable"></a><span data-ttu-id="a0c70-108">Requisitos e restrições para a criação de um índice semântico</span><span class="sxs-lookup"><span data-stu-id="a0c70-108">Requirements and Restrictions for Creating a Semantic Index</span></span>  
  
-   <span data-ttu-id="a0c70-109">Você pode criar um índice em qualquer um dos objetos de banco de dados com suporte para indexação de texto completo, inclusive tabelas e exibições indexadas.</span><span class="sxs-lookup"><span data-stu-id="a0c70-109">You can create an index on any of the database objects that are supported for full-text indexing, including tables and indexed views.</span></span>  
  
-   <span data-ttu-id="a0c70-110">Antes de habilitar a indexação semântica para colunas específicas, verifique se existem os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="a0c70-110">Before you can enable semantic indexing for specific columns, the following prerequisites must exist:</span></span>  
  
    -   <span data-ttu-id="a0c70-111">Um catálogo de texto completo deve existir para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a0c70-111">A full-text catalog must exist for the database.</span></span>  
  
    -   <span data-ttu-id="a0c70-112">A tabela deve ter um índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-112">The table must have a full-text index.</span></span>  
  
    -   <span data-ttu-id="a0c70-113">As colunas selecionadas devem participar do índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-113">The selected columns must participate in the full-text index.</span></span>  
  
     <span data-ttu-id="a0c70-114">É possível criar e habilitar todos esses requisitos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-114">You can create and enable all these requirements at the same time.</span></span>  
  
-   <span data-ttu-id="a0c70-115">Você pode criar um índice semântico em colunas que tenham qualquer um dos tipos de dados com suporte para indexação de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-115">You can create a semantic index on columns that have any of the data types that are supported for full-text indexing.</span></span> <span data-ttu-id="a0c70-116">Para obter mais informações, veja [Criar e gerenciar índices de texto completo](create-and-manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="a0c70-116">For more information, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md).</span></span>  
  
-   <span data-ttu-id="a0c70-117">Você pode especificar qualquer tipo de documento com suporte para indexação de texto completo para colunas `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="a0c70-117">You can specify any document type that is supported for full-text indexing for `varbinary(max)` columns.</span></span> <span data-ttu-id="a0c70-118">Para obter mais informações, consulte [Como determinar os tipos de documento que podem ser indexados](#doctypes) neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a0c70-118">For more information, see [How To: Determine Which Document Types Can Be Indexed](#doctypes) in this topic.</span></span>  
  
-   <span data-ttu-id="a0c70-119">A indexação semântica cria dois tipos de índices para as colunas que você seleciona – um índice de frases-chave e um índice de similaridade de documento.</span><span class="sxs-lookup"><span data-stu-id="a0c70-119">Semantic indexing creates two types of indexes for the columns that you select - an index of key phrases, and an index of document similarity.</span></span> <span data-ttu-id="a0c70-120">Você não pode selecionar somente um tipo de índice ou o outro quando habilita a indexação semântica.</span><span class="sxs-lookup"><span data-stu-id="a0c70-120">You cannot select only one type of index or the other when you enable semantic indexing.</span></span> <span data-ttu-id="a0c70-121">Entretanto, você pode consultar esses dois índices separadamente.</span><span class="sxs-lookup"><span data-stu-id="a0c70-121">However you can query these two indexes independently.</span></span> <span data-ttu-id="a0c70-122">Para obter mais informações, veja [Localizar frases-chave em documentos com a pesquisa semântica](find-key-phrases-in-documents-with-semantic-search.md) e [Localizar documentos semelhantes e relacionados com a pesquisa semântica](find-similar-and-related-documents-with-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="a0c70-122">For more information, see [Find Key Phrases in Documents with Semantic Search](find-key-phrases-in-documents-with-semantic-search.md) and [Find Similar and Related Documents with Semantic Search](find-similar-and-related-documents-with-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="a0c70-123">Se você não especificar explicitamente um LCID para um índice semântico, somente o idioma principal e suas estatísticas de idioma associadas serão usados para a indexação semântica.</span><span class="sxs-lookup"><span data-stu-id="a0c70-123">If you do not explicitly specify an LCID for a semantic index, then only the primary language and its associated language statistics are used for semantic indexing.</span></span>  
  
-   <span data-ttu-id="a0c70-124">Se você criar um idioma para uma coluna para a qual o modelo de idioma não está disponível, a criação do índice falhará e retornará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="a0c70-124">If you specify a language for a column for which the language model is not available, the creation of the index fails and returns an error message.</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-no-full-text-index"></a><a name="HowToEnableCreate"></a><span data-ttu-id="a0c70-125">Como: criar um índice semântico quando não há nenhum índice de texto completo</span><span class="sxs-lookup"><span data-stu-id="a0c70-125">How To: Create a Semantic Index When There Is No Full-Text Index</span></span>  
 <span data-ttu-id="a0c70-126">Quando você criar um novo índice de texto completo com a instrução **CREATE FULLTEXT INDEX** , poderá habilitar a indexação semântica no nível de coluna especificando a palavra-chave **STATISTICAL_SEMANTICS** como parte da definição de coluna.</span><span class="sxs-lookup"><span data-stu-id="a0c70-126">When you create a new full-text index with the **CREATE FULLTEXT INDEX** statement, you can enable semantic indexing at the column level by specifying the keyword **STATISTICAL_SEMANTICS** as part of the column definition.</span></span> <span data-ttu-id="a0c70-127">Você também poderá habilitar a indexação semântica ao usar o Assistente para Indexação de Texto Completo para criar um novo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-127">You can also enable semantic indexing when you use the Full-Text Indexing Wizard to create a new full-text index.</span></span>  
  
 <span data-ttu-id="a0c70-128">**Criar um novo índice semântico usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="a0c70-128">**Create a new semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="a0c70-129">Chame a instrução **CREATE FULLTEXT INDEX** e especifique **STATISTICAL_SEMANTICS** para cada coluna na qual você queira criar um índice semântico.</span><span class="sxs-lookup"><span data-stu-id="a0c70-129">Call the **CREATE FULLTEXT INDEX** statement and specify **STATISTICAL_SEMANTICS** for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="a0c70-130">Para obter mais informações sobre todas as opções para esta instrução, veja [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0c70-130">For more information about all the options for this statement, see [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="a0c70-131">**Exemplo 1: criar um índice exclusivo, um índice de texto completo e um índice semântico**</span><span class="sxs-lookup"><span data-stu-id="a0c70-131">**Example 1: Create a unique index, full-text index, and semantic index**</span></span>  
  
 <span data-ttu-id="a0c70-132">O exemplo a seguir cria um catálogo de texto completo padrão, **ft**. O exemplo cria um índice exclusivo na coluna **JobCandidateID** da tabela **HumanResources.JobCandidate** do banco de dados de exemplo AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="a0c70-132">The following example creates a default full-text catalog, **ft**. The example then creates a unique index on the **JobCandidateID** column of the **HumanResources.JobCandidate** table of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="a0c70-133">Este índice exclusivo é necessário como a coluna de chave de um índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-133">This unique index is required as the key column for a full-text index.</span></span> <span data-ttu-id="a0c70-134">O exemplo cria um índice de texto completo um índice semântico na coluna **Retomar** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-134">The example then creates a full-text index and a semantic index on the **Resume** column.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG ft AS DEFAULT  
GO  
  
CREATE UNIQUE INDEX ui_ukJobCand  
    ON HumanResources.JobCandidate(JobCandidateID)  
GO  
  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate  
    (Resume  
        Language 1033  
        Statistical_Semantics  
    )   
    KEY INDEX JobCandidateID   
    WITH STOPLIST = SYSTEM  
GO  
```  
  
 <span data-ttu-id="a0c70-135">**Exemplo 2: criar um índice de texto completo e um índice semântico em várias colunas com população de índice atrasada**</span><span class="sxs-lookup"><span data-stu-id="a0c70-135">**Example 2: Create a full-text and semantic index on several columns with delayed index population**</span></span>  
  
 <span data-ttu-id="a0c70-136">O exemplo a seguir cria um catálogo de texto completo, **documents_catalog**, no banco de dados de exemplo AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="a0c70-136">The following example creates a full-text catalog, **documents_catalog**, in the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="a0c70-137">Em seguida, o exemplo cria um índice de texto completo que usa esse novo catálogo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-137">The example then creates a full-text index that uses this new catalog.</span></span> <span data-ttu-id="a0c70-138">O índice de texto completo criado nas colunas **Title**, **DocumentSummary**e **Document** da tabela **Production.Document** , enquanto o índice semântico está apenas na coluna **Document** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-138">The full-text index is created on the **Title**, **DocumentSummary**, and **Document** columns of the **Production.Document** table, while the semantic index is only created on the **Document** column.</span></span> <span data-ttu-id="a0c70-139">Esse índice de texto completo usa o catálogo de texto completo padrão e um índice de chave exclusiva existente, **PK_Document_DocumentID**.</span><span class="sxs-lookup"><span data-stu-id="a0c70-139">This full-text index uses the newly-created full-text catalog and an existing unique key index, **PK_Document_DocumentID**.</span></span> <span data-ttu-id="a0c70-140">Conforme recomendado, essa chave de índice é criada em uma coluna de inteiros, **DocumentID**.</span><span class="sxs-lookup"><span data-stu-id="a0c70-140">As recommended, this index key is created on an integer column, **DocumentID**.</span></span> <span data-ttu-id="a0c70-141">O exemplo especifica o LCID para inglês, 1033, que é o idioma dos dados nas colunas.</span><span class="sxs-lookup"><span data-stu-id="a0c70-141">The example specifies the LCID for English, 1033, which is the language of the data in the columns.</span></span>  
  
 <span data-ttu-id="a0c70-142">Este exemplo também especifica que o controle de alterações está desativado sem nenhuma população.</span><span class="sxs-lookup"><span data-stu-id="a0c70-142">This example also specifies that change tracking is off with no population.</span></span> <span data-ttu-id="a0c70-143">Posteriormente, fora do horário de pico, o exemplo usa uma instrução **ALTER FULLTEXT INDEX** para iniciar uma população completa no novo índice e habilitar o controle de alterações automático.</span><span class="sxs-lookup"><span data-stu-id="a0c70-143">Later, during off-peak hours, the example uses an **ALTER FULLTEXT INDEX** statement to start a full population on the new index and enable automatic change tracking.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG documents_catalog  
GO  
  
CREATE FULLTEXT INDEX ON Production.Document  
    (   
    Title  
        Language 1033,   
    DocumentSummary  
        Language 1033,   
    Document   
        TYPE COLUMN FileExtension  
        Language 1033  
        Statistical_Semantics  
    )  
    KEY INDEX PK_Document_DocumentID  
        ON documents_catalog  
        WITH CHANGE_TRACKING OFF, NO POPULATION  
GO  
```  
  
 <span data-ttu-id="a0c70-144">Posteriormente, fora do horário de pico, o índice é populado:</span><span class="sxs-lookup"><span data-stu-id="a0c70-144">Later, at an off-peak time, the index is populated:</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document SET CHANGE_TRACKING AUTO  
GO  
```  
  
 <span data-ttu-id="a0c70-145">**Criar um novo índice semântico usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="a0c70-145">**Create a new semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="a0c70-146">Execute o Assistente para Indexação de Texto Completo e habilite **Semântica Estatística** na página **Selecionar Colunas da Tabela** para cada coluna na qual você queira criar um índice semântico.</span><span class="sxs-lookup"><span data-stu-id="a0c70-146">Run the Full-Text Indexing Wizard and enable **Statistical Semantics** on the **Select Table Columns** page for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="a0c70-147">Para obter mais informações, inclusive sobre como iniciar o Assistente de Indexação de Texto Completo, veja [Usar o Assistente de Indexação de Texto Completo](use-the-full-text-indexing-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a0c70-147">For more information, including information about how to start the Full-Text Indexing Wizard, see [Use the Full-Text Indexing Wizard](use-the-full-text-indexing-wizard.md).</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-an-existing-full-text-index"></a><a name="HowToEnableAlter"></a><span data-ttu-id="a0c70-148">Como: criar um índice semântico quando há um índice de texto completo existente</span><span class="sxs-lookup"><span data-stu-id="a0c70-148">How To: Create a Semantic Index When There Is an Existing Full-Text Index</span></span>  
 <span data-ttu-id="a0c70-149">Você pode adicionar a indexação semântica ao alterar um índice de texto completo existente com a instrução **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-149">You can add semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="a0c70-150">Você também pode adicionar indexação semântica usando várias caixas de diálogo no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0c70-150">You can also add semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a0c70-151">**Adicionar um novo índice semântico usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="a0c70-151">**Add a semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="a0c70-152">Chame a instrução **ALTER FULLTEXT INDEX** com as opções descritas abaixo para cada coluna na qual você queira adicionar um índice semântico.</span><span class="sxs-lookup"><span data-stu-id="a0c70-152">Call the **ALTER FULLTEXT INDEX** statement with the options described below for each column on which you want to add a semantic index.</span></span> <span data-ttu-id="a0c70-153">Para obter mais informações sobre todas as opções para esta instrução, veja [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0c70-153">For more information about all the options for this statement, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="a0c70-154">Os índices de texto completo e semântico são ambos repopulados após uma chamada a **ALTER**, a menos que você especifique de outra forma.</span><span class="sxs-lookup"><span data-stu-id="a0c70-154">Both full-text and semantic indexes are repopulated after a call to **ALTER**, unless you specify otherwise.</span></span>  
  
-   <span data-ttu-id="a0c70-155">Para adicionar somente a indexação de texto completo a uma coluna, use a sintaxe **ADD** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-155">To add full-text indexing only to a column, use the **ADD** syntax.</span></span>  
  
-   <span data-ttu-id="a0c70-156">Para adicionar indexação de texto completo e semântica a uma coluna, use a sintaxe **ADD** com a opção **STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-156">To add both full-text and semantic indexing to a column, use the **ADD** syntax with the **STATISTICAL_SEMANTICS** option.</span></span>  
  
-   <span data-ttu-id="a0c70-157">Para adicionar indexação de texto completo a uma coluna já habilitada para indexação de texto completo, use a opção **ADD STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-157">To add semantic indexing to a column that is already enabled for full-text indexing, use the **ADD STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="a0c70-158">Você só pode adicionar indexação semântica a uma coluna em uma única instrução **ALTER** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-158">You can only add semantic indexing to one column in a single **ALTER** statement.</span></span>  
  
 <span data-ttu-id="a0c70-159">**Exemplo: adicionar a indexação semântica a uma coluna que já tenha a indexação de texto completo**</span><span class="sxs-lookup"><span data-stu-id="a0c70-159">**Example: Add semantic indexing to a column that already has full-text indexing**</span></span>  
  
 <span data-ttu-id="a0c70-160">O exemplo a seguir altera um índice de texto completo existente na tabela **Production.Document** no banco de dados de exemplo AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="a0c70-160">The following example alters an existing full-text index on **Production.Document** table in AdventureWorks2012 sample database.</span></span> <span data-ttu-id="a0c70-161">O exemplo adiciona um índice semântico na coluna **Document** da tabela **Production.Document** , que já tem um índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-161">The example adds a semantic index on the **Document** column of the **Production.Document** table, which already has a full-text index.</span></span> <span data-ttu-id="a0c70-162">O exemplo especifica que o índice não será repopulado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a0c70-162">The example specifies that the index will not be repopulated automatically.</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document  
    ALTER COLUMN Document  
        ADD Statistical_Semantics  
    WITH NO POPULATION  
GO  
```  
  
 <span data-ttu-id="a0c70-163">**Adicionar um índice semântico usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="a0c70-163">**Add a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="a0c70-164">Você pode alterar as colunas que são habilitadas para indexação semântica e de texto completo na página **Colunas de Índice de Texto Completo** da caixa de diálogo **Propriedades do Índice de Texto Completo** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-164">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="a0c70-165">Para obter mais informações, veja [Gerenciar índices de texto completo](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="a0c70-165">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-an-existing-index"></a><a name="addreq"></a><span data-ttu-id="a0c70-166">Requisitos e restrições para alterar um índice existente</span><span class="sxs-lookup"><span data-stu-id="a0c70-166">Requirements and Restrictions for Altering an Existing Index</span></span>  
  
-   <span data-ttu-id="a0c70-167">Você não pode alterar um índice existente enquanto a população do índice está em andamento.</span><span class="sxs-lookup"><span data-stu-id="a0c70-167">You cannot alter an existing index while population of the index is in progress.</span></span> <span data-ttu-id="a0c70-168">Para obter mais informações sobre como monitorar o progresso da população de índice, veja [Gerenciar e monitorar a pesquisa semântica](manage-and-monitor-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="a0c70-168">For more information on monitoring the progress of index population, see [Manage and Monitor Semantic Search](manage-and-monitor-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="a0c70-169">Você não pode adicionar indexação a uma coluna, nem alterar ou remover a indexação para a mesma coluna, em uma única chamada à instrução **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-169">You cannot add indexing to a column, and alter or drop indexing for the same column, in a single call to the **ALTER FULLTEXT INDEX** statement.</span></span>  
  
##  <a name="dropping-a-semantic-index"></a><a name="dropping"></a><span data-ttu-id="a0c70-170">Descartando um índice semântico</span><span class="sxs-lookup"><span data-stu-id="a0c70-170">Dropping a Semantic Index</span></span>  
  
###  <a name="how-to-drop-a-semantic-index"></a><a name="drophow"></a><span data-ttu-id="a0c70-171">Como: descartar um índice semântico</span><span class="sxs-lookup"><span data-stu-id="a0c70-171">How to: Drop a Semantic Index</span></span>  
 <span data-ttu-id="a0c70-172">Você pode remover a indexação semântica ao alterar um índice de texto completo existente com a instrução **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-172">You can drop semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="a0c70-173">Você também pode descartar a indexação semântica usando várias caixas de diálogo no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0c70-173">You can also drop semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a0c70-174">**Descartar um novo índice semântico usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="a0c70-174">**Drop a semantic index by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="a0c70-175">Para remover apenas a indexação semântica de uma ou mais colunas, chame a instrução **ALTER FULLTEXT INDEX** com a opção **ALTER COLUMN***column_name***DROP STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-175">To drop semantic indexing only from a column or columns, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="a0c70-176">Você pode remover a indexação de várias colunas em uma única instrução **ALTER** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-176">You can drop the indexing from multiple columns in a single **ALTER** statement.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP STATISTICAL_SEMANTICS  
    GO  
    ```  
  
-   <span data-ttu-id="a0c70-177">Para descartar a indexação semântica e de texto completo de uma coluna, chame a instrução **ALTER FULLTEXT INDEX** com a opção **ALTER COLUMN***column_name***drop** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-177">To drop both full-text and semantic indexing from a column, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP** option.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP  
    GO  
    ```  
  
 <span data-ttu-id="a0c70-178">**Descartar um índice semântico usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="a0c70-178">**Drop a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="a0c70-179">Você pode alterar as colunas que são habilitadas para indexação semântica e de texto completo na página **Colunas de Índice de Texto Completo** da caixa de diálogo **Propriedades do Índice de Texto Completo** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-179">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="a0c70-180">Para obter mais informações, veja [Gerenciar índices de texto completo](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="a0c70-180">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-dropping-a-semantic-index"></a><a name="dropreq"></a><span data-ttu-id="a0c70-181">Requisitos e restrições para descartar um índice semântico</span><span class="sxs-lookup"><span data-stu-id="a0c70-181">Requirements and Restrictions for Dropping a Semantic Index</span></span>  
  
-   <span data-ttu-id="a0c70-182">Você não pode remover a indexação de texto completo de uma coluna enquanto retém a indexação semântica.</span><span class="sxs-lookup"><span data-stu-id="a0c70-182">You cannot drop full-text indexing from a column while retaining semantic indexing.</span></span> <span data-ttu-id="a0c70-183">A indexação semântica depende da indexação de texto completo para resultados de similaridade de documento.</span><span class="sxs-lookup"><span data-stu-id="a0c70-183">Semantic indexing depends on full-text indexing for document similarity results.</span></span>  
  
-   <span data-ttu-id="a0c70-184">Você não pode especificar a opção **NO POPULATION** ao remover a indexação semântica da última coluna de uma tabela para a qual a indexação semântica foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="a0c70-184">You cannot specify the **NO POPULATION** option when you drop semantic indexing from the last column in a table for which semantic indexing was enabled.</span></span> <span data-ttu-id="a0c70-185">Um ciclo de população é necessário para remover os resultados que foram previamente indexados.</span><span class="sxs-lookup"><span data-stu-id="a0c70-185">A population cycle is required to remove the results that were indexed previously.</span></span>  
  
## <a name="checking-whether-semantic-search-is-enabled-on-database-objects"></a><span data-ttu-id="a0c70-186">Verificando se a pesquisa semântica está habilitada em objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="a0c70-186">Checking Whether Semantic Search Is Enabled on Database Objects</span></span>  
  
###  <a name="how-to-check-whether-semantic-search-is-enabled-on-database-objects"></a><a name="HowToCheckEnabled"></a><span data-ttu-id="a0c70-187">Como verificar se a pesquisa semântica está habilitada em objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="a0c70-187">How To: Check Whether Semantic Search Is Enabled on Database Objects</span></span>  
 <span data-ttu-id="a0c70-188">**A pesquisa semântica está habilitada para um banco de dados?**</span><span class="sxs-lookup"><span data-stu-id="a0c70-188">**Is semantic search enabled for a database?**</span></span>  
 <span data-ttu-id="a0c70-189">Consulte a propriedade **IsFullTextEnabled** da função de metadados [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0c70-189">Query the **IsFullTextEnabled** property of the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="a0c70-190">Um valor de retorno 1 indica a pesquisa de texto completo e a pesquisa semântica estão habilitada para o banco de dados; um valor de retorno 0 indica que não são habilitadas.</span><span class="sxs-lookup"><span data-stu-id="a0c70-190">A return value of 1 indicates that full-text search and semantic search are enabled for the database; a return value of 0 indicates that they are not enabled.</span></span>  
  
```sql  
SELECT DATABASEPROPERTYEX('database_name', 'IsFullTextEnabled')  
GO  
```  
  
 <span data-ttu-id="a0c70-191">**A pesquisa semântica está habilitada para uma tabela?**</span><span class="sxs-lookup"><span data-stu-id="a0c70-191">**Is semantic search enabled for a table?**</span></span>  
 <span data-ttu-id="a0c70-192">Consulte a propriedade **TableFullTextSemanticExtraction** na função de metadados [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0c70-192">Query the **TableFullTextSemanticExtraction** property of the [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="a0c70-193">Um valor de retorno 1 indica a pesquisa semântica está habilitada para a tabela; um valor de retorno 0 indica que ela não está habilitada.</span><span class="sxs-lookup"><span data-stu-id="a0c70-193">A return value of 1 indicates that semantic search is enabled for the table; a return value of 0 indicates that it is not enabled.</span></span>  
  
```scr  
SELECT OBJECTPROPERTYEX(OBJECT_ID('table_name'), 'TableFullTextSemanticExtraction')  
GO  
```  
  
 <span data-ttu-id="a0c70-194">**A pesquisa semântica está habilitada para uma coluna?**</span><span class="sxs-lookup"><span data-stu-id="a0c70-194">**Is semantic search enabled for a column?**</span></span>  
 <span data-ttu-id="a0c70-195">Para determinar se a pesquisa de semântica está habilitada para uma coluna específica:</span><span class="sxs-lookup"><span data-stu-id="a0c70-195">To determine whether semantic search is enabled for a specific column:</span></span>  
  
-   <span data-ttu-id="a0c70-196">Consulte a propriedade **StatisticalSemantics** da função de metadados [COLUMNPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/columnproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0c70-196">Query the **StatisticalSemantics** property of the [COLUMNPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/columnproperty-transact-sql) metadata function.</span></span>  
  
     <span data-ttu-id="a0c70-197">Um valor de retorno 1 indica a pesquisa semântica está habilitada para a coluna; um valor de retorno 0 indica que ela não está habilitada.</span><span class="sxs-lookup"><span data-stu-id="a0c70-197">A return value of 1 indicates that semantic search is enabled for the column; a return value of 0 indicates that it is not enabled.</span></span>  
  
    ```sql  
    SELECT COLUMNPROPERTY(OBJECT_ID('table_name'), 'column_name', 'StatisticalSemantics')  
    GO  
    ```  
  
-   <span data-ttu-id="a0c70-198">Consulte a exibição de catálogo [sys.fulltext_index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) para obter o índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-198">Query the catalog view [sys.fulltext_index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) for the full-text index.</span></span>  
  
     <span data-ttu-id="a0c70-199">Um valor 1 na coluna **statistical_semantics** indica que a coluna especificada está habilitada para a indexação semântica, além da indexação de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-199">A value of 1 in the **statistical_semantics** column indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
    ```sql  
    SELECT * FROM sys.fulltext_index_columns WHERE object_id = OBJECT_ID('table_name')  
    GO  
    ```  
  
-   <span data-ttu-id="a0c70-200">No Pesquisador de Objetos no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], clique com o botão direito do mouse em uma coluna e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a0c70-200">In Object Explorer in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click on a column and select **Properties**.</span></span> <span data-ttu-id="a0c70-201">Na página **Geral** da caixa de diálogo **Propriedades da Coluna** , verifique o valor da propriedade **Semântica Estatística** .</span><span class="sxs-lookup"><span data-stu-id="a0c70-201">On the **General** page of the **Column Properties** dialog box, check the value of the **Statistical Semantics** property.</span></span>  
  
     <span data-ttu-id="a0c70-202">Um valor True indica que a coluna especificada está habilitada para a indexação semântica, além da indexação de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-202">A value of True indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
## <a name="determining-what-can-be-indexed-for-semantic-search"></a><span data-ttu-id="a0c70-203">Determinando o que pode ser indexado para Pesquisa Semântica</span><span class="sxs-lookup"><span data-stu-id="a0c70-203">Determining What Can Be Indexed for Semantic Search</span></span>  
  
###  <a name="how-to-check-which-languages-are-supported-for-semantic-search"></a><a name="HowToCheckLanguages"></a><span data-ttu-id="a0c70-204">Como: verificar quais idiomas têm suporte para pesquisa semântica</span><span class="sxs-lookup"><span data-stu-id="a0c70-204">How To: Check Which Languages Are Supported for Semantic Search</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a0c70-205">Há suporte para menos idiomas na indexação semântica do que na indexação de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-205">Fewer languages are supported for semantic indexing than for full-text indexing.</span></span> <span data-ttu-id="a0c70-206">Como resultado, pode haver colunas que permitam a indexação para pesquisa de texto completo, mas não para pesquisa semântica.</span><span class="sxs-lookup"><span data-stu-id="a0c70-206">As a result, there may be columns that you can index for full-text search, but not for semantic search.</span></span>  
  
 <span data-ttu-id="a0c70-207">Consulte a exibição de catálogo [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0c70-207">Query the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.fulltext_semantic_languages  
GO  
```  
  
 <span data-ttu-id="a0c70-208">Há suporte para os seguintes idiomas na indexação semântica.</span><span class="sxs-lookup"><span data-stu-id="a0c70-208">The following languages are supported for semantic indexing.</span></span> <span data-ttu-id="a0c70-209">Esta lista representa a saída da exibição de catálogo [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql), ordenada por LCID.</span><span class="sxs-lookup"><span data-stu-id="a0c70-209">This list represents the output of the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql), ordered by LCID.</span></span>  
  
|<span data-ttu-id="a0c70-210">Idioma</span><span class="sxs-lookup"><span data-stu-id="a0c70-210">Language</span></span>|<span data-ttu-id="a0c70-211">LCID</span><span class="sxs-lookup"><span data-stu-id="a0c70-211">LCID</span></span>|  
|--------------|----------|  
|<span data-ttu-id="a0c70-212">Alemão</span><span class="sxs-lookup"><span data-stu-id="a0c70-212">German</span></span>|<span data-ttu-id="a0c70-213">1031</span><span class="sxs-lookup"><span data-stu-id="a0c70-213">1031</span></span>|  
|<span data-ttu-id="a0c70-214">Inglês (EUA)</span><span class="sxs-lookup"><span data-stu-id="a0c70-214">English (US)</span></span>|<span data-ttu-id="a0c70-215">1046</span><span class="sxs-lookup"><span data-stu-id="a0c70-215">1033</span></span>|  
|<span data-ttu-id="a0c70-216">Francês</span><span class="sxs-lookup"><span data-stu-id="a0c70-216">French</span></span>|<span data-ttu-id="a0c70-217">1036</span><span class="sxs-lookup"><span data-stu-id="a0c70-217">1036</span></span>|  
|<span data-ttu-id="a0c70-218">Italiano</span><span class="sxs-lookup"><span data-stu-id="a0c70-218">Italian</span></span>|<span data-ttu-id="a0c70-219">1040</span><span class="sxs-lookup"><span data-stu-id="a0c70-219">1040</span></span>|  
|<span data-ttu-id="a0c70-220">Português (Brasil)</span><span class="sxs-lookup"><span data-stu-id="a0c70-220">Portuguese (Brazil)</span></span>|<span data-ttu-id="a0c70-221">1046</span><span class="sxs-lookup"><span data-stu-id="a0c70-221">1046</span></span>|  
|<span data-ttu-id="a0c70-222">Russo</span><span class="sxs-lookup"><span data-stu-id="a0c70-222">Russian</span></span>|<span data-ttu-id="a0c70-223">1049</span><span class="sxs-lookup"><span data-stu-id="a0c70-223">1049</span></span>|  
|<span data-ttu-id="a0c70-224">Sueco</span><span class="sxs-lookup"><span data-stu-id="a0c70-224">Swedish</span></span>|<span data-ttu-id="a0c70-225">1053</span><span class="sxs-lookup"><span data-stu-id="a0c70-225">1053</span></span>|  
|<span data-ttu-id="a0c70-226">Inglês (Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="a0c70-226">English (UK)</span></span>|<span data-ttu-id="a0c70-227">2057</span><span class="sxs-lookup"><span data-stu-id="a0c70-227">2057</span></span>|  
|<span data-ttu-id="a0c70-228">Português (Portugal)</span><span class="sxs-lookup"><span data-stu-id="a0c70-228">Portuguese (Portugal)</span></span>|<span data-ttu-id="a0c70-229">2070</span><span class="sxs-lookup"><span data-stu-id="a0c70-229">2070</span></span>|  
|<span data-ttu-id="a0c70-230">Espanhol</span><span class="sxs-lookup"><span data-stu-id="a0c70-230">Spanish</span></span>|<span data-ttu-id="a0c70-231">3082</span><span class="sxs-lookup"><span data-stu-id="a0c70-231">3082</span></span>|  
  
###  <a name="how-to-determine-which-document-types-can-be-indexed"></a><a name="doctypes"></a><span data-ttu-id="a0c70-232">Como determinar quais tipos de documento podem ser indexados</span><span class="sxs-lookup"><span data-stu-id="a0c70-232">How To: Determine Which Document Types Can Be Indexed</span></span>  
 <span data-ttu-id="a0c70-233">Consulte a exibição de catálogo [sys.fulltext_document_types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0c70-233">Query the catalog view [sys.fulltext_document_types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql).</span></span>  
  
 <span data-ttu-id="a0c70-234">Se o tipo de documento que você deseja indexar não estiver na lista de tipos com suporte, talvez seja preciso localizar, baixar e instalar filtros adicionais.</span><span class="sxs-lookup"><span data-stu-id="a0c70-234">If the document type that you want to index is not in the list of supported types, then you may have to locate, download, and install additional filters.</span></span> <span data-ttu-id="a0c70-235">Para obter mais informações, consulte [Exibir ou alterar filtros registrados e separadores de palavras](view-or-change-registered-filters-and-word-breakers.md).</span><span class="sxs-lookup"><span data-stu-id="a0c70-235">For more information, see [View or Change Registered Filters and Word Breakers](view-or-change-registered-filters-and-word-breakers.md).</span></span>  
  
##  <a name="best-practice-consider-creating-a-separate-filegroup-for-the-full-text-and-semantic-indexes"></a><a name="BestPracticeFilegroup"></a><span data-ttu-id="a0c70-236">Prática recomendada: considere criar um grupo de arquivos separado para os índices de texto completo e semântico</span><span class="sxs-lookup"><span data-stu-id="a0c70-236">Best Practice: Consider Creating a Separate Filegroup for the Full-Text and Semantic Indexes</span></span>  
 <span data-ttu-id="a0c70-237">Considere criar um grupo de arquivos separado para os índices de texto completo e semântico se a alocação de espaço em disco for um problema.</span><span class="sxs-lookup"><span data-stu-id="a0c70-237">Consider creating a separate filegroup for the full-text and semantic indexes if disk space allocation is a concern.</span></span> <span data-ttu-id="a0c70-238">Os índices semânticos são criados no mesmo grupo de arquivos que o índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-238">The semantic indexes are created in the same filegroup as the full-text index.</span></span> <span data-ttu-id="a0c70-239">Um índice semântico totalmente populado pode conter uma grande quantidade de dados.</span><span class="sxs-lookup"><span data-stu-id="a0c70-239">A fully populated semantic index may contain large amount of data.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-searching-on-specific-column-returns-no-results"></a><a name="IssueNoResults"></a><span data-ttu-id="a0c70-240">Problema: a pesquisa em uma coluna específica não retorna nenhum resultado</span><span class="sxs-lookup"><span data-stu-id="a0c70-240">Problem: Searching on Specific Column Returns No Results</span></span>  
 <span data-ttu-id="a0c70-241">**Um LCID não Unicode foi especificado para um idioma Unicode?**</span><span class="sxs-lookup"><span data-stu-id="a0c70-241">**Was a non-Unicode LCID specified for a Unicode language?**</span></span>  
 <span data-ttu-id="a0c70-242">É possível habilitar a indexação semântica em um tipo de coluna não Unicode com um LCID para um idioma que tenha apenas palavras Unicode, como o LCID 1049 para russo.</span><span class="sxs-lookup"><span data-stu-id="a0c70-242">It is possible to enable semantic indexing on a non-Unicode column type with an LCID for a language that only has Unicode words, such as LCID 1049 for Russian.</span></span> <span data-ttu-id="a0c70-243">Neste caso, nenhum resultado será retornado dos índices semânticos nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="a0c70-243">In this case, no results will ever be returned from the semantic indexes on this column.</span></span>  
  
  
