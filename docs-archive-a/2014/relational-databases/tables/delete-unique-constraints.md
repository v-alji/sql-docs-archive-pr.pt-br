---
title: Excluir restrições exclusivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- UNIQUE constraints [SQL Server], deleting
- constraints [SQL Server], deleting
- deleting constraints
- constraints [SQL Server], unique
ms.assetid: 71e563fc-f5d7-4c2e-a42f-f0695a831f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2fe2264aed4eb2f292a6bd1e4e565cebe2a833f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575704"
---
# <a name="delete-unique-constraints"></a><span data-ttu-id="fff1c-102">Excluir restrições exclusivas</span><span class="sxs-lookup"><span data-stu-id="fff1c-102">Delete Unique Constraints</span></span>
  <span data-ttu-id="fff1c-103">Você pode excluir uma restrição exclusiva no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fff1c-103">You can delete a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fff1c-104">Excluir uma restrição exclusiva remove o requisito de exclusividade dos valores inseridos na coluna ou da combinação de colunas incluídas na expressão de restrição e exclui o índice exclusivo correspondente.</span><span class="sxs-lookup"><span data-stu-id="fff1c-104">Deleting a unique constraint removes the requirement for uniqueness for values entered in the column or combination of columns included in the constraint expression and deletes the corresponding unique index.</span></span>  
  
 <span data-ttu-id="fff1c-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="fff1c-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fff1c-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="fff1c-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fff1c-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="fff1c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fff1c-108">**Para excluir uma restrição exclusiva usando:**</span><span class="sxs-lookup"><span data-stu-id="fff1c-108">**To delete a unique constraint, using:**</span></span>  
  
     [<span data-ttu-id="fff1c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fff1c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fff1c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fff1c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fff1c-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fff1c-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fff1c-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="fff1c-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fff1c-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="fff1c-113">Permissions</span></span>  
 <span data-ttu-id="fff1c-114">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="fff1c-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fff1c-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fff1c-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-object-explorer"></a><span data-ttu-id="fff1c-116">Para excluir uma restrição exclusiva usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="fff1c-116">To delete a unique constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="fff1c-117">No Pesquisador de Objetos, expanda a tabela que contém a restrição exclusiva e expanda **Restrições**.</span><span class="sxs-lookup"><span data-stu-id="fff1c-117">In Object Explorer, expand the table that contains the unique constraint and then expand **Constraints**.</span></span>  
  
2.  <span data-ttu-id="fff1c-118">Clique com o botão direito do mouse na chave e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="fff1c-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="fff1c-119">Na caixa de diálogo **Excluir Objeto** , verifique se a chave correta foi especificada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fff1c-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-table-designer"></a><span data-ttu-id="fff1c-120">Para excluir uma restrição exclusiva usando o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="fff1c-120">To delete a unique constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="fff1c-121">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela com a restrição exclusiva e clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="fff1c-121">In **Object Explorer**, right-click the table with the unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="fff1c-122">No menu **Designer de Tabela** , clique em **Índices/Chaves**.</span><span class="sxs-lookup"><span data-stu-id="fff1c-122">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
3.  <span data-ttu-id="fff1c-123">Na caixa de diálogo **Índices/Chaves** , selecione a chave exclusiva na lista **Índice e Chave Primária / Exclusiva Selecionada** .</span><span class="sxs-lookup"><span data-stu-id="fff1c-123">In the **Indexes/Keys** dialog box, select the unique key in the **Selected Primary/Unique Key and Index** list.</span></span>  
  
4.  <span data-ttu-id="fff1c-124">Clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="fff1c-124">Click **Delete**.</span></span>  
  
5.  <span data-ttu-id="fff1c-125">No menu **Arquivo**, clique em **Salvar** _nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="fff1c-125">On the **File** menu, click **Save** _table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fff1c-126">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fff1c-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-unique-constraint"></a><span data-ttu-id="fff1c-127">Para excluir uma restrição exclusiva</span><span class="sxs-lookup"><span data-stu-id="fff1c-127">To delete a unique constraint</span></span>  
  
1.  <span data-ttu-id="fff1c-128">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fff1c-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fff1c-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="fff1c-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fff1c-130">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="fff1c-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Return the name of unique constraint.  
    SELECT name  
    FROM sys.objects  
    WHERE type = 'UQ' AND OBJECT_NAME(parent_object_id) = N' DocExc';  
    GO  
    -- Delete the unique constraint.  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT UNQ_ColumnB_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="fff1c-131">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) e [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fff1c-131">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
