---
title: Excluir chaves primárias | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing primary keys
- deleting primary keys
- primary keys [SQL Server], deleting
ms.assetid: c472e465-7bdd-4d74-8fc9-e47fca007ccb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 44fa1271143f813364bfd2109f8147f1d04294a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584076"
---
# <a name="delete-primary-keys"></a><span data-ttu-id="e32b0-102">Excluir chaves primárias</span><span class="sxs-lookup"><span data-stu-id="e32b0-102">Delete Primary Keys</span></span>
  <span data-ttu-id="e32b0-103">Você pode excluir (descartar) uma chave primária no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e32b0-103">You can delete (drop) a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e32b0-104">Quando a chave primária é excluída, o índice correspondente é excluído.</span><span class="sxs-lookup"><span data-stu-id="e32b0-104">When the primary key is deleted, the corresponding index is deleted.</span></span>  
  
 <span data-ttu-id="e32b0-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="e32b0-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e32b0-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="e32b0-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e32b0-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="e32b0-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e32b0-108">**Para excluir uma chave primária usando:**</span><span class="sxs-lookup"><span data-stu-id="e32b0-108">**To delete a primary key using:**</span></span>  
  
     [<span data-ttu-id="e32b0-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e32b0-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e32b0-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e32b0-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e32b0-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e32b0-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e32b0-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="e32b0-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e32b0-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="e32b0-113">Permissions</span></span>  
 <span data-ttu-id="e32b0-114">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="e32b0-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e32b0-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e32b0-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-object-explorer"></a><span data-ttu-id="e32b0-116">Para excluir uma restrição de chave primária usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="e32b0-116">To delete a primary key constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="e32b0-117">No Pesquisador de Objetos, expanda a tabela que contém a chave primária e expanda **Chaves**.</span><span class="sxs-lookup"><span data-stu-id="e32b0-117">In Object Explorer, expand the table that contains the primary key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="e32b0-118">Clique com o botão direito do mouse na chave e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="e32b0-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="e32b0-119">Na caixa de diálogo **Excluir Objeto** , verifique se a chave correta foi especificada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e32b0-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-table-designer"></a><span data-ttu-id="e32b0-120">Para excluir uma restrição de chave primária usando o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="e32b0-120">To delete a primary key constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="e32b0-121">No Pesquisador de Objetos, clique com o botão direito do mouse na tabela com a chave primária e clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="e32b0-121">In Object Explorer, right-click the table with the primary key, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="e32b0-122">Na grade de tabela, clique com o botão direito do mouse na linha com a chave primária e escolha **Remover Chave Primária** para alternar a configuração de ativado para desativado.</span><span class="sxs-lookup"><span data-stu-id="e32b0-122">In the table grid, right-click the row with the primary key and choose **Remove Primary Key** to toggle the setting from on to off.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e32b0-123">Para desfazer essa ação, feche a tabela sem salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="e32b0-123">To undo this action, close the table without saving the changes.</span></span> <span data-ttu-id="e32b0-124">A exclusão de uma chave primária não pode ser desfeita sem perder todas as outras alterações feitas na tabela.</span><span class="sxs-lookup"><span data-stu-id="e32b0-124">Deleting a primary key cannot be undone without losing all other changes made to the table.</span></span>  
  
3.  <span data-ttu-id="e32b0-125">No menu **Arquivo**, clique em **Salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="e32b0-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e32b0-126">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e32b0-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint"></a><span data-ttu-id="e32b0-127">Para excluir uma restrição de chave primária</span><span class="sxs-lookup"><span data-stu-id="e32b0-127">To delete a primary key constraint</span></span>  
  
1.  <span data-ttu-id="e32b0-128">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e32b0-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e32b0-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="e32b0-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e32b0-130">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e32b0-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e32b0-131">O exemplo identifica primeiramente o nome da restrição de chave primária e depois exclui a restrição.</span><span class="sxs-lookup"><span data-stu-id="e32b0-131">The example first identifies the name of the primary key constraint and then deletes the constraint.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Return the name of primary key.  
    SELECT name  
    FROM sys.key_constraints  
    WHERE type = 'PK' AND OBJECT_NAME(parent_object_id) = N'TransactionHistoryArchive';  
    GO  
    -- Delete the primary key constraint.  
    ALTER TABLE Production.TransactionHistoryArchive  
    DROP CONSTRAINT PK_TransactionHistoryArchive_TransactionID;   
    GO  
    ```  
  
 <span data-ttu-id="e32b0-132">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) e [sys.key_constraints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="e32b0-132">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.key_constraints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql)</span></span>  
  
###  <a name="TsqlExample"></a>  
