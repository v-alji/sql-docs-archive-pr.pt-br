---
title: Excluir um índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- deleting indexes
- dropping indexes
- indexes [SQL Server], dropping
- index deletions [SQL Server]
ms.assetid: fd38a0ed-26c4-4c76-9ef7-e0a16147329d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4552ba701782e5790f95f54c0c1c66f82573f1e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685112"
---
# <a name="delete-an-index"></a><span data-ttu-id="082c1-102">Excluir um índice</span><span class="sxs-lookup"><span data-stu-id="082c1-102">Delete an Index</span></span>
  <span data-ttu-id="082c1-103">Este tópico descreve como excluir (descartar) um índice no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="082c1-103">This topic describes how to delete (drop) an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="082c1-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="082c1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="082c1-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="082c1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="082c1-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="082c1-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="082c1-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="082c1-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="082c1-108">**Para excluir um índice, usando:**</span><span class="sxs-lookup"><span data-stu-id="082c1-108">**To delete an index, using:**</span></span>  
  
     [<span data-ttu-id="082c1-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="082c1-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="082c1-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="082c1-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="082c1-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="082c1-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="082c1-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="082c1-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="082c1-113">Índices criados em decorrência de uma restrição PRIMARY KEY ou UNIQUE não podem ser excluídos com esse método.</span><span class="sxs-lookup"><span data-stu-id="082c1-113">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be deleted by using this method.</span></span> <span data-ttu-id="082c1-114">Em vez disso, a restrição deve ser excluída.</span><span class="sxs-lookup"><span data-stu-id="082c1-114">Instead, the constraint must be deleted.</span></span> <span data-ttu-id="082c1-115">Para remover a restrição e o índice correspondente, use [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) com a cláusula DROP CONSTRAINT em [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="082c1-115">To remove the constraint and corresponding index, use [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) with the DROP CONSTRAINT clause in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="082c1-116">Para obter mais informações, consulte [Delete Primary Keys](../tables/delete-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="082c1-116">For more information, see [Delete Primary Keys](../tables/delete-primary-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="082c1-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="082c1-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="082c1-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="082c1-118">Permissions</span></span>  
 <span data-ttu-id="082c1-119">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="082c1-119">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="082c1-120">Essa permissão é concedida por padrão à função de servidor fixa **sysadmin** e às funções de banco de dados fixas **db_ddladmin** e **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="082c1-120">This permission is granted by default to the **sysadmin** fixed server role and the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="082c1-121">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="082c1-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-index-by-using-object-explorer"></a><span data-ttu-id="082c1-122">Para excluir um índice usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="082c1-122">To delete an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="082c1-123">No Pesquisador de Objetos, expanda o banco de dados que contém a tabela da qual você deseja excluir um índice.</span><span class="sxs-lookup"><span data-stu-id="082c1-123">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="082c1-124">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="082c1-124">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="082c1-125">Expanda a tabela que contém o índice que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="082c1-125">Expand the table that contains the index you want to delete.</span></span>  
  
4.  <span data-ttu-id="082c1-126">Expanda a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="082c1-126">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="082c1-127">Clique com o botão direito do mouse no índice a ser excluído e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="082c1-127">Right-click the index you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="082c1-128">Na caixa de diálogo **Excluir Objeto** , verifique se o índice correto está na grade **Objeto a ser excluído** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="082c1-128">In the **Delete Object** dialog box, verify that the correct index is in the **Object to be deleted** grid and click **OK**.</span></span>  
  
#### <a name="to-delete-an-index-using-table-designer"></a><span data-ttu-id="082c1-129">Para excluir um índice usando o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="082c1-129">To delete an index using Table Designer</span></span>  
  
1.  <span data-ttu-id="082c1-130">No Pesquisador de Objetos, expanda o banco de dados que contém a tabela da qual você deseja excluir um índice.</span><span class="sxs-lookup"><span data-stu-id="082c1-130">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="082c1-131">Expanda a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="082c1-131">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="082c1-132">Clique com o botão direito do mouse na tabela que contém o índice a ser excluído e clique em Design.</span><span class="sxs-lookup"><span data-stu-id="082c1-132">Right-click the table that contains the index you want to delete and click Design.</span></span>  
  
4.  <span data-ttu-id="082c1-133">No menu **Designer de Tabela** , clique em **Índices/Chaves**.</span><span class="sxs-lookup"><span data-stu-id="082c1-133">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="082c1-134">Na caixa de diálogo **Índices/Chaves** , selecione o índice que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="082c1-134">In the **Indexes/Keys** dialog box, select the index you want to delete.</span></span>  
  
6.  <span data-ttu-id="082c1-135">Clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="082c1-135">Click **Delete**.</span></span>  
  
7.  <span data-ttu-id="082c1-136">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="082c1-136">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="082c1-137">No menu **Arquivo** , selecione **Salvar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="082c1-137">On the **File** menu, select **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="082c1-138">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="082c1-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-index"></a><span data-ttu-id="082c1-139">Para excluir um índice</span><span class="sxs-lookup"><span data-stu-id="082c1-139">To delete an index</span></span>  
  
1.  <span data-ttu-id="082c1-140">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="082c1-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="082c1-141">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="082c1-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="082c1-142">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="082c1-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- delete the IX_ProductVendor_BusinessEntityID index  
    -- from the Purchasing.ProductVendor table  
    DROP INDEX IX_ProductVendor_BusinessEntityID   
        ON Purchasing.ProductVendor;  
    GO  
    ```  
  
 <span data-ttu-id="082c1-143">Para obter mais informações, veja [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="082c1-143">For more information, see [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql).</span></span>  
  
  
