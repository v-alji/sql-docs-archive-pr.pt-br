---
title: Excluir tabelas (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table deletions [SQL Server]
- deleting tables
- removing tables
- dropping tables
ms.assetid: ca6aa3e9-9885-44c3-bafc-aec441fd97ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1e361456534f565f854d348bbef5751c7d66c0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684140"
---
# <a name="delete-tables-database-engine"></a><span data-ttu-id="fd91f-102">Excluir tabelas (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="fd91f-102">Delete Tables (Database Engine)</span></span>
  <span data-ttu-id="fd91f-103">Você pode excluir (descartar) uma tabela de seu banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd91f-103">You can delete (drop) a table from your database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="fd91f-104">Pense cuidadosamente antes de excluir uma tabela.</span><span class="sxs-lookup"><span data-stu-id="fd91f-104">Think carefully before you delete a table.</span></span> <span data-ttu-id="fd91f-105">Se as consultas, as exibições, as funções definidas pelo usuário, os procedimentos armazenados ou os programas existentes se referirem a essa tabela, a exclusão do nome tornará esses objetivos inválidos.</span><span class="sxs-lookup"><span data-stu-id="fd91f-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the deletion will make these objects invalid.</span></span>  
  
 <span data-ttu-id="fd91f-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="fd91f-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fd91f-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="fd91f-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fd91f-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="fd91f-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fd91f-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="fd91f-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fd91f-110">**Para excluir uma tabela usando:**</span><span class="sxs-lookup"><span data-stu-id="fd91f-110">**To Delete a Table, using:**</span></span>  
  
     [<span data-ttu-id="fd91f-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fd91f-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fd91f-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fd91f-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fd91f-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fd91f-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fd91f-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="fd91f-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fd91f-115">Você não pode descartar uma tabela que é referenciada por uma restrição FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="fd91f-115">You cannot drop a table that is referenced by a FOREIGN KEY constraint.</span></span> <span data-ttu-id="fd91f-116">A restrição FOREIGN KEY que faz referência ou a tabela de referência deve ser primeiramente descartada.</span><span class="sxs-lookup"><span data-stu-id="fd91f-116">The referencing FOREIGN KEY constraint or the referencing table must first be dropped.</span></span> <span data-ttu-id="fd91f-117">Se a tabela de referência e a tabela que contém a chave primária forem descartadas na mesma instrução DROP TABLE, a tabela de referência deverá ser listada em primeiro lugar.</span><span class="sxs-lookup"><span data-stu-id="fd91f-117">If both the referencing table and the table that holds the primary key are being dropped in the same DROP TABLE statement, the referencing table must be listed first.</span></span>  
  
-   <span data-ttu-id="fd91f-118">Quando uma tabela for descartada, as regras ou os padrões da tabela perderão sua associação e quaisquer restrições ou gatilhos associados à tabela serão descartados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fd91f-118">When a table is dropped, rules or defaults on the table lose their binding, and any constraints or triggers associated with the table are automatically dropped.</span></span> <span data-ttu-id="fd91f-119">Se você recriar uma tabela, deverá associar novamente as regras e padrões apropriados, recriar quaisquer gatilhos e adicionar todas as restrições necessárias.</span><span class="sxs-lookup"><span data-stu-id="fd91f-119">If you re-create a table, you must rebind the appropriate rules and defaults, re-create any triggers, and add all required constraints.</span></span>  
  
-   <span data-ttu-id="fd91f-120">Se você descartar uma tabela que contém uma coluna `varbinary (max)` com o atributo FILESTREAM, os dados armazenados no sistema de arquivos não serão removidos.</span><span class="sxs-lookup"><span data-stu-id="fd91f-120">If you drop a table that contains a `varbinary (max)` column with the FILESTREAM attribute, any data stored in the file system will not be removed.</span></span>  
  
-   <span data-ttu-id="fd91f-121">DROP TABLE e CREATE TABLE não devem ser executados na mesma tabela no mesmo lote.</span><span class="sxs-lookup"><span data-stu-id="fd91f-121">DROP TABLE and CREATE TABLE should not be executed on the same table in the same batch.</span></span> <span data-ttu-id="fd91f-122">Caso contrário, poderá ocorrer um erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="fd91f-122">Otherwise an unexpected error may occur.</span></span>  
  
-   <span data-ttu-id="fd91f-123">Qualquer exibição ou procedimento armazenado que faça referência à tabela descartada deverá ser excluído ou modificado explicitamente para remover a referência à tabela.</span><span class="sxs-lookup"><span data-stu-id="fd91f-123">Any view or stored procedure that references the dropped table must be explicitly deleted or modified to remove the reference to the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fd91f-124">Segurança</span><span class="sxs-lookup"><span data-stu-id="fd91f-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fd91f-125">Permissões</span><span class="sxs-lookup"><span data-stu-id="fd91f-125">Permissions</span></span>  
 <span data-ttu-id="fd91f-126">Exige a permissão ALTER no esquema ao qual a tabela pertence, permissão CONTROL na tabela ou associação na função de banco de dados fixa **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="fd91f-126">Requires ALTER permission on the schema to which the table belongs, CONTROL permission on the table, or membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fd91f-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fd91f-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-table-from-the-database"></a><span data-ttu-id="fd91f-128">Para excluir uma tabela do banco de dados</span><span class="sxs-lookup"><span data-stu-id="fd91f-128">To delete a table from the database</span></span>  
  
1.  <span data-ttu-id="fd91f-129">No Pesquisador de Objetos, selecione a tabela que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="fd91f-129">In Object Explorer, select the table you want to delete.</span></span>  
  
2.  <span data-ttu-id="fd91f-130">Clique com o botão direito do mouse na tabela e escolha **Excluir** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="fd91f-130">Right-click the table and choose **Delete** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="fd91f-131">Uma caixa de mensagem solicitará que você confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="fd91f-131">A message box prompts you to confirm the deletion.</span></span> <span data-ttu-id="fd91f-132">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fd91f-132">Click **Yes**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fd91f-133">A exclusão de uma tabela automaticamente remove qualquer relação associada a ela.</span><span class="sxs-lookup"><span data-stu-id="fd91f-133">Deleting a table automatically removes any relationships to it.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fd91f-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fd91f-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-table-in-query-editor"></a><span data-ttu-id="fd91f-135">Para excluir uma tabela no Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="fd91f-135">To delete a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="fd91f-136">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd91f-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fd91f-137">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="fd91f-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fd91f-138">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="fd91f-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    DROP TABLE dbo.PurchaseOrderDetail;  
  
    ```  
  
 <span data-ttu-id="fd91f-139">Para obter mais informações, veja [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="fd91f-139">For more information, see [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql)</span></span>  
  
  
