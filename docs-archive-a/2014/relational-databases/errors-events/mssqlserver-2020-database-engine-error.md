---
title: MSSQLSERVER_2020 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2020 (Database Engine error)
ms.assetid: 4a8bf90f-a083-4c53-84f0-d23c711c8081
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5939267c37e90e7b8456dc01a4af79545e775656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581870"
---
# <a name="mssqlserver_2020"></a><span data-ttu-id="a2a5e-102">MSSQLSERVER_2020</span><span class="sxs-lookup"><span data-stu-id="a2a5e-102">MSSQLSERVER_2020</span></span>
    
## <a name="details"></a><span data-ttu-id="a2a5e-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a2a5e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2a5e-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a2a5e-104">Product Name</span></span>|<span data-ttu-id="a2a5e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a2a5e-105">SQL Server</span></span>|  
|<span data-ttu-id="a2a5e-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a2a5e-106">Event ID</span></span>|<span data-ttu-id="a2a5e-107">2020</span><span class="sxs-lookup"><span data-stu-id="a2a5e-107">2020</span></span>|  
|<span data-ttu-id="a2a5e-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a2a5e-108">Event Source</span></span>|<span data-ttu-id="a2a5e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a2a5e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a2a5e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a2a5e-110">Component</span></span>|<span data-ttu-id="a2a5e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a2a5e-111">SQLEngine</span></span>|  
|<span data-ttu-id="a2a5e-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a2a5e-112">Symbolic Name</span></span>||  
|<span data-ttu-id="a2a5e-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a2a5e-113">Message Text</span></span>|<span data-ttu-id="a2a5e-114">As dependências reportadas para a entidade "%.\*ls" não incluem referências às colunas.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-114">The dependencies reported for entity "%.\*ls" do not include references to columns.</span></span> <span data-ttu-id="a2a5e-115">Isso ocorre porque a entidade faz referência a um objeto que não existe ou devido a um erro em uma ou mais instruções na entidade.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-115">This is either because the entity references an object that does not exist or because of an error in one or more statements in the entity.</span></span>  <span data-ttu-id="a2a5e-116">Antes de executar novamente a consulta, verifique se não há erros na entidade e se todos os objetos referenciados por ela existem.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-116">Before rerunning the query, ensure that there are no errors in the entity and that all objects referenced by the entity exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a2a5e-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="a2a5e-117">Explanation</span></span>  
 <span data-ttu-id="a2a5e-118">A função de sistema **sys.dm_sql_referenced_entities** relatará qualquer dependência em nível de coluna de referências associadas a esquema.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-118">The **sys.dm_sql_referenced_entities** system function will report any column-level dependency for schema-bound references.</span></span> <span data-ttu-id="a2a5e-119">Por exemplo, ela reportará todas as dependências em nível de coluna de uma exibição indexada porque uma exibição indexada exige uma associação de esquema.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-119">For example, the function will report all column-level dependencies for an indexed view because an indexed view requires schema binding.</span></span> <span data-ttu-id="a2a5e-120">No entanto, quando a entidade referenciada não estiver associada a esquema, as dependências de coluna serão reportadas somente se todas as instruções com referência a essas colunas puderem ser associadas.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-120">However, when the referenced entity is not schema-bound, column dependencies are reported only when all statements in which the columns are referenced can be bound.</span></span> <span data-ttu-id="a2a5e-121">Será possível associar as instruções com êxito somente se todos os objetos existirem no momento em que as instruções forem analisadas.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-121">Statements can be successfully bound only if all objects exist at the time the statements are parsed.</span></span> <span data-ttu-id="a2a5e-122">Se uma instrução definida na entidade não for associada com êxito, as dependências de coluna não serão relatadas e a coluna **referenced_minor_id** retornará 0.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-122">If any statement defined in the entity fails to bind, column dependencies will not be reported and the **referenced_minor_id** column will return 0.</span></span> <span data-ttu-id="a2a5e-123">Quando não for possível resolver as dependências de coluna, ocorrerá o erro 2020.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-123">When column dependencies cannot be resolved, error 2020 is raised.</span></span> <span data-ttu-id="a2a5e-124">Esse erro não impede que a consulta retorne dependências no nível do objeto.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-124">This error does not prevent the query from returning object-level dependencies.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a2a5e-125">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a2a5e-125">User Action</span></span>  
 <span data-ttu-id="a2a5e-126">Corrija todos os erros identificados na mensagem antes do erro 2020.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-126">Correct any errors identified in the message before error 2020.</span></span> <span data-ttu-id="a2a5e-127">Por exemplo, no exemplo de código a seguir, a exibição `Production.ApprovedDocuments` é definida nas colunas `Title`, `ChangeNumber` e `Status` da tabela `Production.Document`.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-127">For example, in the following code example the view `Production.ApprovedDocuments` is defined on the columns `Title`, `ChangeNumber`, and `Status` in the `Production.Document` table.</span></span> <span data-ttu-id="a2a5e-128">A função de sistema **sys.dm_sql_referenced_entities** é consultada para verificar se há colunas e objetos dos quais a exibição `ApprovedDocuments` depende.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-128">The **sys.dm_sql_referenced_entities** system function is queried for the objects and columns on which the `ApprovedDocuments` view depends.</span></span> <span data-ttu-id="a2a5e-129">Como a exibição não foi criada com o uso da cláusula WITH SCHEMA_BINDING, as colunas referenciadas na exibição poderão ser modificadas na tabela da referência.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-129">Because the view is not created using the WITH SCHEMA_BINDING clause, the columns referenced in the view can be modified in the referenced table.</span></span> <span data-ttu-id="a2a5e-130">O exemplo altera a coluna `ChangeNumber` da tabela `Production.Document`, renomeando-a para `TrackingNumber`.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-130">The example alters the column `ChangeNumber` in the `Production.Document` table by renaming it to `TrackingNumber`.</span></span> <span data-ttu-id="a2a5e-131">A exibição `ApprovedDocuments` é consultada novamente na exibição do catálogo; contudo, não é possível associar todas as colunas definidas na exibição.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-131">The catalog view is queried again for the `ApprovedDocuments` view; however it cannot bind to all the columns defined in the view.</span></span> <span data-ttu-id="a2a5e-132">São retornados os erros 207 e 2020 que identificam o problema.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-132">Errors 207 and 2020 are returned identifying the problem.</span></span> <span data-ttu-id="a2a5e-133">Para resolver o problema, a exibição deve ser alterada de modo a refletir o novo nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-133">To resolve the problem, the view must be altered to reflect the new name of the column.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `CREATE VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title, ChangeNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 `EXEC sp_rename 'Production.Document.ChangeNumber', 'TrackingNumber', 'COLUMN';`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 <span data-ttu-id="a2a5e-134">A consulta retorna as seguintes mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-134">The query returns the following error messages.</span></span>  
  
 `Msg 207, Level 16, State 1, Procedure ApprovedDocuments, Line 3`  
  
 `Invalid column name 'ChangeNumber'.`  
  
 `Msg 2020, Level 16, State 1, Line 1`  
  
 `The dependencies reported for entity`  
  
 `"Production.ApprovedDocuments" do not include references to`  
  
 `columns. This is either because the entity references an`  
  
 `object that does not exist or because of an error in one or`  
  
 `more statements in the entity. Before rerunning the query,`  
  
 `ensure that there are no errors in the entity and that all`  
  
 `objects referenced by the entity exist.`  
  
 <span data-ttu-id="a2a5e-135">O exemplo a seguir corrige o nome da coluna na exibição.</span><span class="sxs-lookup"><span data-stu-id="a2a5e-135">The following example corrects the column name in the view.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `ALTER VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title,TrackingNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
## <a name="see-also"></a><span data-ttu-id="a2a5e-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2a5e-136">See Also</span></span>  
 [<span data-ttu-id="a2a5e-137">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a2a5e-137">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
  
