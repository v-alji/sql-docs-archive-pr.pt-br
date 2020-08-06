---
title: Excluir estatísticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], deleting
- deleting statistics
ms.assetid: eccce0aa-591e-4a1d-bd10-373b022f8749
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 36b74d7e1465c0742cda4fef9f34fb4b3930719c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582364"
---
# <a name="delete-statistics"></a><span data-ttu-id="1c2b7-102">Excluir estatísticas</span><span class="sxs-lookup"><span data-stu-id="1c2b7-102">Delete Statistics</span></span>
  <span data-ttu-id="1c2b7-103">Você pode excluir (remover) estatísticas de tabelas e exibições no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c2b7-103">You can delete (drop) statistics from tables and views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="1c2b7-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="1c2b7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1c2b7-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="1c2b7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1c2b7-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="1c2b7-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1c2b7-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="1c2b7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1c2b7-108">**Para remover estatísticas de uma tabela ou exibição usando:**</span><span class="sxs-lookup"><span data-stu-id="1c2b7-108">**To drop statistics from a table or view, using:**</span></span>  
  
     [<span data-ttu-id="1c2b7-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1c2b7-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1c2b7-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1c2b7-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1c2b7-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1c2b7-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1c2b7-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="1c2b7-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1c2b7-113">Tenha cuidado ao cancelar estatísticas.</span><span class="sxs-lookup"><span data-stu-id="1c2b7-113">Be careful when you drop statistics.</span></span> <span data-ttu-id="1c2b7-114">Essa ação pode afetar o plano de execução escolhido pelo otimizador de consulta.</span><span class="sxs-lookup"><span data-stu-id="1c2b7-114">Doing so may affect the execution plan chosen by the query optimizer.</span></span>  
  
-   <span data-ttu-id="1c2b7-115">Estatísticas em índices não podem ser canceladas usando DROP STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="1c2b7-115">Statistics on indexes cannot be dropped by using DROP STATISTICS.</span></span> <span data-ttu-id="1c2b7-116">As estatísticas permanecerão enquanto o índice existir.</span><span class="sxs-lookup"><span data-stu-id="1c2b7-116">Statistics remain as long as the index exists.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1c2b7-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="1c2b7-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1c2b7-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="1c2b7-118">Permissions</span></span>  
 <span data-ttu-id="1c2b7-119">Requer a permissão ALTER na tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="1c2b7-119">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1c2b7-120">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1c2b7-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="1c2b7-121">Para remover estatísticas de uma tabela ou exibição</span><span class="sxs-lookup"><span data-stu-id="1c2b7-121">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="1c2b7-122">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o banco de dados no qual você deseja excluir uma estatística.</span><span class="sxs-lookup"><span data-stu-id="1c2b7-122">In **Object Explorer**, click the plus sign to expand the database in which you want to delete a statistic.</span></span>  
  
2.  <span data-ttu-id="1c2b7-123">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="1c2b7-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="1c2b7-124">Clique no sinal de adição para expandir a tabela na qual você deseja excluir uma estatística.</span><span class="sxs-lookup"><span data-stu-id="1c2b7-124">Click the plus sign to expand the table in which you want to delete a statistic.</span></span>  
  
4.  <span data-ttu-id="1c2b7-125">Clique no sinal de adição para expandir a pasta **Estatísticas** .</span><span class="sxs-lookup"><span data-stu-id="1c2b7-125">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="1c2b7-126">Clique com o botão direito do mouse no objeto de estatísticas que deseja excluir e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="1c2b7-126">Right-click the statistics object that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="1c2b7-127">Na caixa de diálogo **Excluir Objeto** , verifique se a estatística correta foi selecionada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c2b7-127">In the **Delete Object** dialog box, ensure that the correct statistic has been selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1c2b7-128">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1c2b7-128">Using Transact-SQL</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="1c2b7-129">Para remover estatísticas de uma tabela ou exibição</span><span class="sxs-lookup"><span data-stu-id="1c2b7-129">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="1c2b7-130">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c2b7-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1c2b7-131">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="1c2b7-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1c2b7-132">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1c2b7-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- First, create two statistics named VendorCredit and CustomerTotal  
    -- The first statistic uses a random 50% sample of information provided from the Name and CreditRating columns in the Purchasing.Vendor table.  
    CREATE STATISTICS VendorCredit  
        ON Purchasing.Vendor (Name, CreditRating)  
        WITH SAMPLE 50 PERCENT  
    -- The second statistic uses all of the information from the CustomerID and TotalDue columns in the Sales.SalesOrderHeader table  
    CREATE STATISTICS CustomerTotal  
        ON Sales.SalesOrderHeader (CustomerID, TotalDue)  
        WITH FULLSCAN;  
    GO  
    -- This next statement drops both of the statistics created above. Note that the naming convention is [table_name].[statistics_name].  
    DROP STATISTICS Purchasing.Vendor.VendorCredit, Sales.SalesOrderHeader.CustomerTotal;  
    GO  
    ```  
  
 <span data-ttu-id="1c2b7-133">Para obter mais informações, veja [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1c2b7-133">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql).</span></span>  
  
  
