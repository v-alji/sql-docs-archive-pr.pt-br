---
title: Modificar um índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], modifying
- modifying indexes
- index changes [SQL Server]
ms.assetid: 97e3110d-fde7-4f5d-9309-dc1697960aeb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af9293966afce8372f5b83a579418c546c82816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684743"
---
# <a name="modify-an-index"></a><span data-ttu-id="ecf73-102">Modificar um índice</span><span class="sxs-lookup"><span data-stu-id="ecf73-102">Modify an Index</span></span>
  <span data-ttu-id="ecf73-103">Este tópico descreve como modificar um índice no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecf73-103">This topic describes how to modify an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ecf73-104">Índices criados em decorrência de uma restrição PRIMARY KEY ou UNIQUE não podem ser modificados usando esse método.</span><span class="sxs-lookup"><span data-stu-id="ecf73-104">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be modified by using this method.</span></span> <span data-ttu-id="ecf73-105">Em vez disso, a restrição deve ser modificada.</span><span class="sxs-lookup"><span data-stu-id="ecf73-105">Instead, the constraint must be modified.</span></span>  
  
 <span data-ttu-id="ecf73-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="ecf73-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ecf73-107">**Para modificar um índice, usando:**</span><span class="sxs-lookup"><span data-stu-id="ecf73-107">**To modify an index, using:**</span></span>  
  
     [<span data-ttu-id="ecf73-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ecf73-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ecf73-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ecf73-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ecf73-110">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ecf73-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="ecf73-111">Para modificar um índice</span><span class="sxs-lookup"><span data-stu-id="ecf73-111">To modify an index</span></span>  
  
1.  <span data-ttu-id="ecf73-112">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="ecf73-112">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ecf73-113">Expanda o **Banco de Dados**, expanda o banco de dados a que pertence a tabela e, depois, expanda **Tabelas**.</span><span class="sxs-lookup"><span data-stu-id="ecf73-113">Expand **Databases**, expand the database in which the table belongs, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="ecf73-114">Expanda a tabela onde se encontra o índice e expanda **Índices**.</span><span class="sxs-lookup"><span data-stu-id="ecf73-114">Expand the table in which the index belongs and then expand **Indexes**.</span></span>  
  
4.  <span data-ttu-id="ecf73-115">Clique com o botão direito do mouse no índice a ser modificado e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ecf73-115">Right-click the index that you want to modify and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="ecf73-116">Na caixa de diálogo **Propriedades de Índice** , faça as alterações desejadas.</span><span class="sxs-lookup"><span data-stu-id="ecf73-116">In the **Index Properties** dialog box, make the desired changes.</span></span> <span data-ttu-id="ecf73-117">Por exemplo, você pode adicionar ou remover uma coluna da chave de índice, ou alterar a configuração de uma opção de índice.</span><span class="sxs-lookup"><span data-stu-id="ecf73-117">For example, you can add or remove a column from the index key, or change the setting of an index option.</span></span>  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="ecf73-118">Para modificar as colunas de um índice</span><span class="sxs-lookup"><span data-stu-id="ecf73-118">To modify index columns</span></span>  
  
1.  <span data-ttu-id="ecf73-119">Para adicionar, remover ou alterar a posição de uma coluna de um índice, selecione a página **Geral** na caixa de diálogo **Propriedades do Índice** .</span><span class="sxs-lookup"><span data-stu-id="ecf73-119">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties** dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ecf73-120">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ecf73-120">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="ecf73-121">Para modificar um índice</span><span class="sxs-lookup"><span data-stu-id="ecf73-121">To modify an index</span></span>  
  
1.  <span data-ttu-id="ecf73-122">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecf73-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ecf73-123">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="ecf73-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ecf73-124">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="ecf73-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ecf73-125">Este exemplo descarta e recria um índice existente na coluna `ProductID` da tabela `Production.WorkOrder` usando a opção `DROP_EXISTING` .</span><span class="sxs-lookup"><span data-stu-id="ecf73-125">This example drops and re-creates an existing index on the `ProductID` column of the `Production.WorkOrder` table by using the `DROP_EXISTING` option.</span></span> <span data-ttu-id="ecf73-126">As opções `FILLFACTOR` e `PAD_INDEX` também são definidas.</span><span class="sxs-lookup"><span data-stu-id="ecf73-126">The options `FILLFACTOR` and `PAD_INDEX` are also set.</span></span>  
  
     [!code-sql[IndexDDL#CreateIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/createindex.sql#createindex4)]  
  
     <span data-ttu-id="ecf73-127">O exemplo a seguir usa ALTER INDEX para definir várias opções no índice `AK_SalesOrderHeader_SalesOrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="ecf73-127">The following example uses ALTER INDEX to set several options on the index `AK_SalesOrderHeader_SalesOrderNumber`.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="ecf73-128">Para modificar as colunas de um índice</span><span class="sxs-lookup"><span data-stu-id="ecf73-128">To modify index columns</span></span>  
  
1.  <span data-ttu-id="ecf73-129">Para adicionar, remover ou alterar a posição de uma coluna de índice, você deve remover e recriar o índice.</span><span class="sxs-lookup"><span data-stu-id="ecf73-129">To add, remove, or change the position of an index column, you must drop and recreate the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf73-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ecf73-130">See Also</span></span>  
 <span data-ttu-id="ecf73-131">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ecf73-131">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="ecf73-132">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ecf73-132">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="ecf73-133">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ecf73-133">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 <span data-ttu-id="ecf73-134">[sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ecf73-134">[sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span></span>  
 <span data-ttu-id="ecf73-135">[sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ecf73-135">[sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span></span>  
 <span data-ttu-id="ecf73-136">[Opções Set Index](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="ecf73-136">[Set Index Options](set-index-options.md) </span></span>  
 [<span data-ttu-id="ecf73-137">Renomear índices</span><span class="sxs-lookup"><span data-stu-id="ecf73-137">Rename Indexes</span></span>](indexes.md)  
  
  
