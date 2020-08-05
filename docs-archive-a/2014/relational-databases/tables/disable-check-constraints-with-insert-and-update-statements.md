---
title: Desabilitar restrições de verificação com instruções INSERT e UPDATE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, disabling
- constraints [SQL Server], disabling
- disabling constraints
- constraints [SQL Server], check
ms.assetid: c7287ad1-50d2-4e80-bc0c-b5570f7e5f69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 780a2c1bfd9f21c71367ad61f200ec19ab44a608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573871"
---
# <a name="disable-check-constraints-with-insert-and-update-statements"></a><span data-ttu-id="bdae4-102">Desabilitar restrições de verificação com instruções INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="bdae4-102">Disable Check Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="bdae4-103">Você pode desabilitar uma restrição de verificação para transações INSERT e UPDATE no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdae4-103">You can disable a check constraint for INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bdae4-104">Depois de desabilitar as restrições de verificação, as inserções ou atualizações futuras na coluna não serão validadas em relação às condições de restrição.</span><span class="sxs-lookup"><span data-stu-id="bdae4-104">After you disable the check constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span> <span data-ttu-id="bdae4-105">Use esta opção se você souber que novos dados violarão a restrição existente ou se a restrição se aplicar somente aos dados que já estão no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bdae4-105">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="bdae4-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="bdae4-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bdae4-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="bdae4-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bdae4-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="bdae4-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bdae4-109">**Para desabilitar uma restrição de verificação para instruções INSERT e UPDATE usando:**</span><span class="sxs-lookup"><span data-stu-id="bdae4-109">**To disable a check constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="bdae4-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bdae4-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bdae4-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bdae4-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bdae4-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="bdae4-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bdae4-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="bdae4-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bdae4-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="bdae4-114">Permissions</span></span>  
 <span data-ttu-id="bdae4-115">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="bdae4-115">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bdae4-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bdae4-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="bdae4-117">Para desabilitar uma restrição de verificação para instruções INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="bdae4-117">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="bdae4-118">No **Pesquisador de Objetos**, expanda a tabela com a restrição e expanda a pasta **Restrições** .</span><span class="sxs-lookup"><span data-stu-id="bdae4-118">In **Object Explorer**, expand the table with the constraint and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="bdae4-119">Clique com o botão direito do mouse na restrição e selecione **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="bdae4-119">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="bdae4-120">Na grade, em **Designer de Tabela**, clique em **Impor para INSERTs e UPDATEs** e selecione **Não** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="bdae4-120">In the grid under **Table Designer**, click **Enforce For INSERTs And UPDATEs** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="bdae4-121">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="bdae4-121">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bdae4-122">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bdae4-122">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="bdae4-123">Para desabilitar uma restrição de verificação para instruções INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="bdae4-123">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="bdae4-124">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdae4-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bdae4-125">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="bdae4-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bdae4-126">Copie e cole os exemplos a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="bdae4-126">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT CK_PurchaseOrderHeader_Freight;   
    GO  
    ```  
  
 <span data-ttu-id="bdae4-127">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bdae4-127">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
