---
title: Modificar dados por meio de uma exibição | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- data modifications [SQL Server], views
- views [SQL Server], modifying data through
- modifying data [SQL Server], views
ms.assetid: 410e2812-4ebe-48b2-b95f-c7784f1c4336
author: stevestein
ms.author: sstein
ms.openlocfilehash: df1eb4a33d1d10e63363e52760dad805b20c0a8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569261"
---
# <a name="modify-data-through-a-view"></a><span data-ttu-id="934de-102">Modificar dados por meio de uma exibição</span><span class="sxs-lookup"><span data-stu-id="934de-102">Modify Data Through a View</span></span>
  <span data-ttu-id="934de-103">Você pode modificar os dados de uma tabela base subjacente no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="934de-103">You can modify the data of an underlying base table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="934de-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="934de-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="934de-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="934de-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="934de-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="934de-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="934de-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="934de-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="934de-108">**Para modificar os dados da tabela por uma exibição usando:**</span><span class="sxs-lookup"><span data-stu-id="934de-108">**To modify table data through a view, using:**</span></span>  
  
     [<span data-ttu-id="934de-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="934de-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="934de-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="934de-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="934de-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="934de-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="934de-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="934de-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="934de-113">Consulte a seção “Exibições atualizáveis” em [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="934de-113">See the section 'Updatable Views' in [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="934de-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="934de-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="934de-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="934de-115">Permissions</span></span>  
 <span data-ttu-id="934de-116">Exige a permissão UPDATE, INSERT ou DELETE na tabela de destino, dependendo da ação em execução.</span><span class="sxs-lookup"><span data-stu-id="934de-116">Requires UPDATE, INSERT, or DELETE permissions on the target table, depending on the action being performed.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="934de-117">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="934de-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-table-data-through-a-view"></a><span data-ttu-id="934de-118">Para modificar os dados da tabela por uma exibição</span><span class="sxs-lookup"><span data-stu-id="934de-118">To modify table data through a view</span></span>  
  
1.  <span data-ttu-id="934de-119">No **Pesquisador de Objetos**, expanda o banco de dados que contém a exibição e expanda **Exibições**.</span><span class="sxs-lookup"><span data-stu-id="934de-119">In **Object Explorer**, expand the database that contains the view and then expand **Views**.</span></span>  
  
2.  <span data-ttu-id="934de-120">Clique com o botão direito do mouse na exibição e selecione **Editar 200 Linhas Superiores**.</span><span class="sxs-lookup"><span data-stu-id="934de-120">Right-click the view and select **Edit Top 200 Rows**.</span></span>  
  
3.  <span data-ttu-id="934de-121">Você pode precisar modificar a instrução SELECT no painel **SQL** para retornar as linhas a serem modificadas.</span><span class="sxs-lookup"><span data-stu-id="934de-121">You may need to modify the SELECT statement in the **SQL** pane to return the rows to be modified.</span></span>  
  
4.  <span data-ttu-id="934de-122">No painel **Resultados** , localize a linha a ser alterada ou excluída.</span><span class="sxs-lookup"><span data-stu-id="934de-122">In the **Results** pane, locate the row to be changed or deleted.</span></span> <span data-ttu-id="934de-123">Para excluir a linha, clique com o botão direito do mouse na linha e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="934de-123">To delete the row, right-click the row and select **Delete**.</span></span> <span data-ttu-id="934de-124">Para alterar dados em uma ou mais colunas, modifique os dados na coluna.</span><span class="sxs-lookup"><span data-stu-id="934de-124">To change data in one or more columns, modify the data in the column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="934de-125">Você não poderá excluir uma linha se a exibição referenciar mais de uma tabela base.</span><span class="sxs-lookup"><span data-stu-id="934de-125">You cannot delete a row if the view references more than one base table.</span></span> <span data-ttu-id="934de-126">Você pode atualizar somente colunas que pertencem a uma única tabela base.</span><span class="sxs-lookup"><span data-stu-id="934de-126">You can only update columns that belong to a single base table.</span></span>  
  
5.  <span data-ttu-id="934de-127">Para inserir uma linha, role até o fim das linhas e insira os novos valores.</span><span class="sxs-lookup"><span data-stu-id="934de-127">To insert a row, scroll down to the end of the rows and insert the new values.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="934de-128">Você não poderá inserir uma linha se a exibição referenciar mais de uma tabela base.</span><span class="sxs-lookup"><span data-stu-id="934de-128">You cannot insert a row if the view references more than one base table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="934de-129">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="934de-129">Using Transact-SQL</span></span>  
  
#### <a name="to-update-table-data-through-a-view"></a><span data-ttu-id="934de-130">Para atualizar os dados da tabela por uma exibição</span><span class="sxs-lookup"><span data-stu-id="934de-130">To update table data through a view</span></span>  
  
1.  <span data-ttu-id="934de-131">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="934de-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="934de-132">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="934de-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="934de-133">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="934de-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="934de-134">Este exemplo altera o valor nas colunas `StartDate` e `EndDate` para um funcionário específico referenciando colunas na exibição `HumanResources.vEmployeeDepartmentHistory`.</span><span class="sxs-lookup"><span data-stu-id="934de-134">This example changes the value in the `StartDate` and `EndDate` columns for a specific employee by referencing columns in the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="934de-135">Esta exibição retorna valores de duas tabelas.</span><span class="sxs-lookup"><span data-stu-id="934de-135">This view returns values from two tables.</span></span> <span data-ttu-id="934de-136">Esta instrução tem sucesso porque as colunas modificadas são apenas de uma das tabelas base.</span><span class="sxs-lookup"><span data-stu-id="934de-136">This statement succeeds because the columns being modified are from only one of the base tables.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    UPDATE HumanResources.vEmployeeDepartmentHistory  
    SET StartDate = '20110203', EndDate = GETDATE()   
    WHERE LastName = N'Smith' AND FirstName = 'Samantha';   
    GO  
    ```  
  
 <span data-ttu-id="934de-137">Para obter mais informações, consulte [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="934de-137">For more information, see [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).</span></span>  
  
#### <a name="to-insert-table-data-through-a-view"></a><span data-ttu-id="934de-138">Para inserir os dados da tabela por uma exibição</span><span class="sxs-lookup"><span data-stu-id="934de-138">To insert table data through a view</span></span>  
  
1.  <span data-ttu-id="934de-139">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="934de-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="934de-140">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="934de-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="934de-141">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="934de-141">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="934de-142">O exemplo insere uma nova linha na tabela base `HumanResouces.Department` especificando as colunas pertinentes da exibição `HumanResources.vEmployeeDepartmentHistory`.</span><span class="sxs-lookup"><span data-stu-id="934de-142">The example inserts a new row into the base table `HumanResouces.Department` by specifying the relevant columns from the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="934de-143">A instrução tem sucesso porque somente as colunas de uma tabela base são especificadas e as outras colunas na tabela base têm valores padrão.</span><span class="sxs-lookup"><span data-stu-id="934de-143">The statement succeeds because only columns from a single base table are specified and the other columns in the base table have default values.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    INSERT INTO HumanResources.vEmployeeDepartmentHistory (Department, GroupName)   
    VALUES ('MyDepartment', 'MyGroup');   
    GO  
    ```  
  
 <span data-ttu-id="934de-144">Para obter mais informações, consulte [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="934de-144">For more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).</span></span>  
  
  
