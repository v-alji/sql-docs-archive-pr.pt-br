---
title: Excluir restrições de verificação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- CHECK constraints, deleting
- constraints [SQL Server], deleting
- constraints [SQL Server], check
- deleting constraints
ms.assetid: 5f86c1a6-f5fa-4e77-a892-f6ae96fc0ab3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28a7f72993cbf2ed0a8cc76534380090ef0d0a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573880"
---
# <a name="delete-check-constraints"></a><span data-ttu-id="05af9-102">Excluir restrições de verificação</span><span class="sxs-lookup"><span data-stu-id="05af9-102">Delete Check Constraints</span></span>
  <span data-ttu-id="05af9-103">Você pode excluir uma restrição de verificação no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05af9-103">You can delete a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="05af9-104">Excluir restrições de verificação remove as limitações sobre os valores de dados aceitos na coluna ou nas colunas incluídas na expressão de restrição.</span><span class="sxs-lookup"><span data-stu-id="05af9-104">Deleting check constraints removes the limitations on data values that are accepted in the column or columns included in the constraint expression.</span></span>  
  
 <span data-ttu-id="05af9-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="05af9-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="05af9-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="05af9-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="05af9-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="05af9-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="05af9-108">**Para excluir uma restrição de verificação usando:**</span><span class="sxs-lookup"><span data-stu-id="05af9-108">**To delete a check constraint, using:**</span></span>  
  
     [<span data-ttu-id="05af9-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="05af9-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="05af9-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="05af9-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="05af9-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="05af9-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="05af9-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="05af9-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="05af9-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="05af9-113">Permissions</span></span>  
 <span data-ttu-id="05af9-114">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="05af9-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="05af9-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="05af9-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="05af9-116">Para excluir uma restrição de verificação</span><span class="sxs-lookup"><span data-stu-id="05af9-116">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="05af9-117">No **Pesquisador de Objetos**, expanda a tabela com a restrição de verificação.</span><span class="sxs-lookup"><span data-stu-id="05af9-117">In **Object Explorer**, expand the table with the check constraint.</span></span>  
  
2.  <span data-ttu-id="05af9-118">Expanda  **Restrições**.</span><span class="sxs-lookup"><span data-stu-id="05af9-118">Expand  **Constraints**.</span></span>  
  
3.  <span data-ttu-id="05af9-119">Clique com o botão direito do mouse na restrição e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="05af9-119">Right-click the constraint and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="05af9-120">Na caixa de diálogo **Excluir Objeto** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="05af9-120">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="05af9-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="05af9-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="05af9-122">Para excluir uma restrição de verificação</span><span class="sxs-lookup"><span data-stu-id="05af9-122">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="05af9-123">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05af9-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="05af9-124">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="05af9-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="05af9-125">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="05af9-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT CHK_ColumnD_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="05af9-126">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="05af9-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
