---
title: Definir opções de índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- ALLOW_ROW_LOCKS option
- SORT_IN_TEMPDB option
- DROP_EXISTING clause
- large data, indexes
- PAD_INDEX
- STATISTICS_NORECOMPUTE
- MAXDOP index option, setting
- index options [SQL Server]
- MAXDOP index option
- IGNORE_DUP_KEY option
- ALLOW_PAGE_LOCKS option
- ONLINE
ms.assetid: 7969af33-e94c-41f7-ab89-9d9a2747cd5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9f2d7f0bbbf0d152d3f510ae9ddbe3168634ef96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684741"
---
# <a name="set-index-options"></a><span data-ttu-id="7e797-102">Opções Set Index</span><span class="sxs-lookup"><span data-stu-id="7e797-102">Set Index Options</span></span>
  <span data-ttu-id="7e797-103">Este tópico descreve como modificar as propriedades de um índice no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e797-103">This topic describes how to modify the properties of an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7e797-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="7e797-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7e797-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="7e797-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7e797-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="7e797-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7e797-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="7e797-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7e797-108">**Para modificar as propriedades de um índice usando:**</span><span class="sxs-lookup"><span data-stu-id="7e797-108">**To modify the properties of an index, using:**</span></span>  
  
     [<span data-ttu-id="7e797-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e797-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7e797-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e797-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7e797-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7e797-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7e797-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="7e797-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7e797-113">As opções a seguir são se aplicadas imediatamente ao índice usando a cláusula SET na instrução ALTER INDEX: ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY e STATISTICS_NORECOMPUTE.</span><span class="sxs-lookup"><span data-stu-id="7e797-113">The following options are immediately applied to the index by using the SET clause in the ALTER INDEX statement: ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY, and STATISTICS_NORECOMPUTE.</span></span>  
  
-   <span data-ttu-id="7e797-114">As seguintes opções podem ser definidas quando você recompila um índice usando ALTER INDEX REBUILD ou CREATE INDEX WITH DROP_EXISTING: PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP e DROP_EXISTING (somente CREATE INDEX).</span><span class="sxs-lookup"><span data-stu-id="7e797-114">The following options can be set when you rebuild an index by using either ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING: PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP, and DROP_EXISTING (CREATE INDEX only).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7e797-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="7e797-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7e797-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="7e797-116">Permissions</span></span>  
 <span data-ttu-id="7e797-117">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="7e797-117">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7e797-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e797-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-table-designer"></a><span data-ttu-id="7e797-119">Para modificar as propriedades de um índice no Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="7e797-119">To modify the properties of an index in Table Designer</span></span>  
  
1.  <span data-ttu-id="7e797-120">No Pesquisador de Objetos, clique no sinal de adição ao lado do banco de dados que contém a tabela na qual você modificar as propriedades de um índice.</span><span class="sxs-lookup"><span data-stu-id="7e797-120">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="7e797-121">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="7e797-121">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="7e797-122">Clique com o botão direito do mouse na tabela em que você deseja modificar as propriedades de um índice e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="7e797-122">Right-click the table on which you want to modify an index's properties and select **Design**.</span></span>  
  
4.  <span data-ttu-id="7e797-123">No menu **Designer de Tabela** , clique em **Índices/Chaves**.</span><span class="sxs-lookup"><span data-stu-id="7e797-123">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="7e797-124">Selecione o índice a ser modificado.</span><span class="sxs-lookup"><span data-stu-id="7e797-124">Select the index that you want to modify.</span></span> <span data-ttu-id="7e797-125">Suas propriedades aparecerão na grade principal.</span><span class="sxs-lookup"><span data-stu-id="7e797-125">Its properties will show up in the main grid.</span></span>  
  
6.  <span data-ttu-id="7e797-126">Altere as configurações de alguma ou de todas as propriedades para personalizar o índice.</span><span class="sxs-lookup"><span data-stu-id="7e797-126">Change the settings of any and all properties to customize the index.</span></span>  
  
7.  <span data-ttu-id="7e797-127">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="7e797-127">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="7e797-128">No menu **Arquivo** , selecione **Salvar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="7e797-128">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-object-explorer"></a><span data-ttu-id="7e797-129">Para modificar as propriedades de um índice no Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="7e797-129">To modify the properties of an index in Object Explorer</span></span>  
  
1.  <span data-ttu-id="7e797-130">No Pesquisador de Objetos, clique no sinal de adição ao lado do banco de dados que contém a tabela na qual você modificar as propriedades de um índice.</span><span class="sxs-lookup"><span data-stu-id="7e797-130">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="7e797-131">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="7e797-131">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="7e797-132">Clique no sinal de adição para expandir a tabela na qual você deseja modificar as propriedades do índice.</span><span class="sxs-lookup"><span data-stu-id="7e797-132">Click the plus sign to expand the table on which you want to modify an index's properties.</span></span>  
  
4.  <span data-ttu-id="7e797-133">Clique no sinal de adição para expandir a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="7e797-133">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="7e797-134">Clique com o botão direito do mouse no índice cujas propriedades serão modificadas e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7e797-134">Right-click the index of which you want to modify the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="7e797-135">Em **Selecione uma página**, selecione **Opções**.</span><span class="sxs-lookup"><span data-stu-id="7e797-135">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="7e797-136">Altere as configurações de alguma ou de todas as propriedades para personalizar o índice.</span><span class="sxs-lookup"><span data-stu-id="7e797-136">Change the settings of any and all properties to customize the index.</span></span>  
  
8.  <span data-ttu-id="7e797-137">Para adicionar, remover ou alterar a posição de uma coluna de índice, selecione a página **Geral** na caixa de diálogo **Propriedades do Índice –** _nome_do_índice_.</span><span class="sxs-lookup"><span data-stu-id="7e797-137">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties -** _index_name_ dialog box.</span></span> <span data-ttu-id="7e797-138">Para obter mais informações, consulte [Index Properties F1 Help](index-properties-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="7e797-138">For more information, see [Index Properties F1 Help](index-properties-f1-help.md)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7e797-139">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e797-139">Using Transact-SQL</span></span>  
  
#### <a name="to-see-the-properties-of-all-the-indexes-in-a-table"></a><span data-ttu-id="7e797-140">Para ver as propriedades de todos os índices em uma tabela</span><span class="sxs-lookup"><span data-stu-id="7e797-140">To see the properties of all the indexes in a table</span></span>  
  
1.  <span data-ttu-id="7e797-141">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e797-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7e797-142">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="7e797-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7e797-143">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7e797-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT i.name AS index_name,   
        i.type_desc,   
        i.is_unique,   
        ds.type_desc AS filegroup_or_partition_scheme,   
        ds.name AS filegroup_or_partition_scheme_name,   
        i.ignore_dup_key,   
        i.is_primary_key,   
        i.is_unique_constraint,   
        i.fill_factor,   
        i.is_padded,   
        i.is_disabled,   
        i.allow_row_locks,   
        i.allow_page_locks,   
        i.has_filter,   
        i.filter_definition  
    FROM sys.indexes AS i  
       INNER JOIN sys.data_spaces AS ds ON i.data_space_id = ds.data_space_id  
    WHERE is_hypothetical = 0 AND i.index_id <> 0   
       AND i.object_id = OBJECT_ID('HumanResources.Employee');   
    GO  
  
    ```  
  
#### <a name="to-set-the-properties-of-an-index"></a><span data-ttu-id="7e797-144">Para definir as propriedades de um índice</span><span class="sxs-lookup"><span data-stu-id="7e797-144">To set the properties of an index</span></span>  
  
1.  <span data-ttu-id="7e797-145">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e797-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7e797-146">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="7e797-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7e797-147">Copie e cole os exemplos a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7e797-147">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="7e797-148">Para obter mais informações, consulte [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7e797-148">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
