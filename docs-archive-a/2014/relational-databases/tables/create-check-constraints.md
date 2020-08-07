---
title: Criar restrições de verificação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table constraints [SQL Server]
- attaching check constraints
- columns [SQL Server], constraints
- constraints [SQL Server], check
- CHECK constraints, attaching
ms.assetid: b8756304-9454-4d39-996a-64516831b7df
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7795ee6eca85a22bdd4e84c90ce49a9449ddff28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584088"
---
# <a name="create-check-constraints"></a><span data-ttu-id="2bede-102">Criar restrições de verificação</span><span class="sxs-lookup"><span data-stu-id="2bede-102">Create Check Constraints</span></span>
  <span data-ttu-id="2bede-103">Você pode criar uma restrição de verificação em uma tabela para especificar quais valores de dados são aceitáveis em uma ou mais colunas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bede-103">You can create a check constraint in a table to specify the data values that are acceptable in one or more columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2bede-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="2bede-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2bede-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="2bede-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2bede-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="2bede-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2bede-107">**Para criar uma nova restrição de verificação usando:**</span><span class="sxs-lookup"><span data-stu-id="2bede-107">**To create a new check constraint using:**</span></span>  
  
     [<span data-ttu-id="2bede-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2bede-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2bede-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2bede-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2bede-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2bede-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2bede-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="2bede-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2bede-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="2bede-112">Permissions</span></span>  
 <span data-ttu-id="2bede-113">Requer a permissões ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="2bede-113">Requires ALTER permissions on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2bede-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2bede-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="2bede-115">Para criar uma nova restrição de verificação</span><span class="sxs-lookup"><span data-stu-id="2bede-115">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="2bede-116">No **Pesquisador de Objetos**, expanda a tabela à qual você deseja adicionar uma restrição de verificação, clique com o botão direito do mouse em **Restrições** e clique em **Nova Restrição**.</span><span class="sxs-lookup"><span data-stu-id="2bede-116">In **Object Explorer**, expand the table to which you want to add a check constraint, right-click **Constraints** and click **New Constraint**.</span></span>  
  
2.  <span data-ttu-id="2bede-117">Na caixa de diálogo **Restrições de Verificação**, clique no campo **Expressão** e clique nas reticências **(…)** .</span><span class="sxs-lookup"><span data-stu-id="2bede-117">In the **Check Constraints** dialog box, click in the **Expression** field and then click the ellipses **(...)**.</span></span>  
  
3.  <span data-ttu-id="2bede-118">Na caixa de diálogo **Expressão de Restrição de Verificação** , digite as expressões SQL da restrição de verificação.</span><span class="sxs-lookup"><span data-stu-id="2bede-118">In the **Check Constraint Expression** dialog box, type the SQL expressions for the check constraint.</span></span> <span data-ttu-id="2bede-119">Por exemplo, para limitar as entradas na coluna `SellEndDate` da tabela `Product` a um valor maior ou igual à data na coluna `SellStartDate` ou a um valor NULL, digite:</span><span class="sxs-lookup"><span data-stu-id="2bede-119">For example, to limit the entries in the `SellEndDate` column of the `Product` table to a value that is either greater than or equal to the date in the `SellStartDate` column or is a NULL value, type:</span></span>  
  
    ```  
    SellEndDate >= SellStartDate OR SellEndDate IS NULL  
    ```  
  
     <span data-ttu-id="2bede-120">Ou, para solicitar que as entradas na coluna `zip` sejam de 5 algarismos, digite:</span><span class="sxs-lookup"><span data-stu-id="2bede-120">Or, to require entries in the `zip` column to be 5 digits, type:</span></span>  
  
    ```  
    zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="2bede-121">Certifique-se de colocar os valores de restrição não numéricos entre aspas simples (').</span><span class="sxs-lookup"><span data-stu-id="2bede-121">Make sure to enclose any non-numeric constraint values in single quotation marks (').</span></span>  
  
4.  <span data-ttu-id="2bede-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bede-122">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="2bede-123">Na categoria **Identidade** , você pode alterar o nome da restrição de verificação e adicionar uma descrição (propriedade estendida) para a restrição.</span><span class="sxs-lookup"><span data-stu-id="2bede-123">In the **Identity** category, you can change the name of the check constraint and add a description (extended property) for the constraint.</span></span>  
  
6.  <span data-ttu-id="2bede-124">Na categoria **Designer de Tabela** , você pode definir quando a restrição será imposta.</span><span class="sxs-lookup"><span data-stu-id="2bede-124">In the **Table Designer** category, you can set when the constraint is enforced.</span></span>  
  
    |<span data-ttu-id="2bede-125">**Para:**</span><span class="sxs-lookup"><span data-stu-id="2bede-125">**To:**</span></span>|<span data-ttu-id="2bede-126">**Selecione Sim nos seguintes campos:**</span><span class="sxs-lookup"><span data-stu-id="2bede-126">**Select Yes in the Following Fields:**</span></span>|  
    |-------------|---------------------------------------------|  
    |<span data-ttu-id="2bede-127">Testar a restrição dos dados que existiam antes da criação da restrição</span><span class="sxs-lookup"><span data-stu-id="2bede-127">Test the constraint on data that existed before you created the constraint</span></span>|<span data-ttu-id="2bede-128">**Verificar Dados Existentes ao Criar ou Habilitar**</span><span class="sxs-lookup"><span data-stu-id="2bede-128">**Check Existing Data On Creation Or Enabling**</span></span>|  
    |<span data-ttu-id="2bede-129">Impor a restrição sempre que uma operação de replicação ocorrer nesta tabela</span><span class="sxs-lookup"><span data-stu-id="2bede-129">Enforce the constraint whenever a replication operation occurs on this table</span></span>|<span data-ttu-id="2bede-130">**Impor para Replicação**</span><span class="sxs-lookup"><span data-stu-id="2bede-130">**Enforce For Replication**</span></span>|  
    |<span data-ttu-id="2bede-131">Impor a restrição sempre que uma linha desta tabela for inserida ou atualizada</span><span class="sxs-lookup"><span data-stu-id="2bede-131">Enforce the constraint whenever a row of this table is inserted or updated</span></span>|<span data-ttu-id="2bede-132">**Impor para INSERTs e UPDATEs**</span><span class="sxs-lookup"><span data-stu-id="2bede-132">**Enforce For INSERTs And UPDATEs**</span></span>|  
  
7.  <span data-ttu-id="2bede-133">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="2bede-133">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2bede-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2bede-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="2bede-135">Para criar uma nova restrição de verificação</span><span class="sxs-lookup"><span data-stu-id="2bede-135">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="2bede-136">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bede-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2bede-137">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2bede-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2bede-138">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2bede-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
       ADD ColumnD int NULL   
       CONSTRAINT CHK_ColumnD_DocExc   
       CHECK (ColumnD > 10 AND ColumnD < 50);  
    GO  
    -- Adding values that will pass the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (49);  
    GO  
    -- Adding values that will fail the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (55);  
    GO  
  
    ```  
  
 <span data-ttu-id="2bede-139">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2bede-139">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
