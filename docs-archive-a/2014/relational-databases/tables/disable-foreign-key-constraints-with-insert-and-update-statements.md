---
title: Desabilitar restrições Foreign Key com instruções INSERT e UPDATE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
- UPDATE statement [SQL Server], foreign key constraints
- INSERT statement [SQL Server], foreign key constraints
ms.assetid: 029168d7-085e-4b13-9b86-5644b67c6e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: e91328f4f12f2a0a27f397c7bd95390a505f3998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572965"
---
# <a name="disable-foreign-key-constraints-with-insert-and-update-statements"></a><span data-ttu-id="9834e-102">Desabilitar restrições FOREIGN KEY com instruções INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="9834e-102">Disable Foreign Key Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="9834e-103">Você pode desabilitar uma restrição de chave estrangeira durante transações INSERT e UPDATE no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9834e-103">You can disable a foreign key constraint during INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9834e-104">Use esta opção se você souber que novos dados violarão a restrição existente ou se a restrição se aplicar somente aos dados que já estão no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9834e-104">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="9834e-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="9834e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9834e-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="9834e-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9834e-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="9834e-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9834e-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="9834e-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9834e-109">**Para desabilitar uma restrição de chave estrangeira para instruções INSERT e UPDATE usando:**</span><span class="sxs-lookup"><span data-stu-id="9834e-109">**To disable a foreign key constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="9834e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9834e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9834e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9834e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9834e-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9834e-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9834e-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="9834e-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="9834e-114">Depois de desabilitar essas restrições, as inserções ou atualizações futuras na coluna não serão validadas em relação às condições de restrição.</span><span class="sxs-lookup"><span data-stu-id="9834e-114">After you disable these constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9834e-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="9834e-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9834e-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="9834e-116">Permissions</span></span>  
 <span data-ttu-id="9834e-117">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="9834e-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9834e-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9834e-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="9834e-119">Para desabilitar uma restrição de chave estrangeira para instruções INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="9834e-119">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="9834e-120">No **Pesquisador de Objetos**, expanda a tabela com a restrição e expanda a pasta **Chaves** .</span><span class="sxs-lookup"><span data-stu-id="9834e-120">In **Object Explorer**, expand the table with the constraint and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="9834e-121">Clique com o botão direito do mouse na restrição e selecione **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="9834e-121">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="9834e-122">Na grade em **Designer de Tabela**, clique em **Impor Restrição de Chave Estrangeira** e selecione **Não** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="9834e-122">In the grid under **Table Designer**, click **Enforce Foreign Key Constraint** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="9834e-123">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="9834e-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9834e-124">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9834e-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="9834e-125">Para desabilitar uma restrição de chave estrangeira para instruções INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="9834e-125">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="9834e-126">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9834e-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9834e-127">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="9834e-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9834e-128">Copie e cole os exemplos a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9834e-128">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT FK_PurchaseOrderHeader_Employee_EmployeeID;  
    GO  
    ```  
  
 <span data-ttu-id="9834e-129">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9834e-129">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
