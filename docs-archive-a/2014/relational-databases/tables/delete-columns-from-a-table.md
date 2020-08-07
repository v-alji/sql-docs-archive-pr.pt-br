---
title: Excluir colunas de uma tabela | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], deleting
- removing columns
- deleting columns
- dropping columns
ms.assetid: 0d8f6e4f-bc71-4fa3-8615-74249c8e072d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 62f9bca8ee53ae97bb1ac7f37e597b7814a0c370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575036"
---
# <a name="delete-columns-from-a-table"></a><span data-ttu-id="96f28-102">Excluir colunas de uma tabela</span><span class="sxs-lookup"><span data-stu-id="96f28-102">Delete Columns from a Table</span></span>
  <span data-ttu-id="96f28-103">Este tópico descreve como excluir colunas de tabelas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96f28-103">This topic describes how to delete table columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="96f28-104">Ao excluir uma coluna de uma tabela, ela e todos os dados que ela contém serão excluídos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="96f28-104">When you delete a column from a table, it and all the data it contains are deleted from the database.</span></span> <span data-ttu-id="96f28-105">Essa ação não pode ser desfeita.</span><span class="sxs-lookup"><span data-stu-id="96f28-105">This action cannot be undone.</span></span>  
  
 <span data-ttu-id="96f28-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="96f28-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="96f28-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="96f28-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="96f28-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="96f28-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="96f28-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="96f28-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="96f28-110">**Para excluir uma coluna de uma tabela usando:**</span><span class="sxs-lookup"><span data-stu-id="96f28-110">**To delete a column from a table, using:**</span></span>  
  
     [<span data-ttu-id="96f28-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96f28-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="96f28-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96f28-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="96f28-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="96f28-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="96f28-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="96f28-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="96f28-115">Você não pode excluir uma coluna que tenha uma restrição CHECK.</span><span class="sxs-lookup"><span data-stu-id="96f28-115">You cannot delete a column that has a CHECK constraint.</span></span> <span data-ttu-id="96f28-116">Você deve excluir primeiramente a restrição.</span><span class="sxs-lookup"><span data-stu-id="96f28-116">You must first delete the constraint.</span></span>  
  
 <span data-ttu-id="96f28-117">Você não pode excluir uma coluna que tenha restrições PRIMARY KEY ou FOREIGN KEY ou outras dependências, exceto quando estiver usando o Designer de Tabela.</span><span class="sxs-lookup"><span data-stu-id="96f28-117">You cannot delete a column that has PRIMARY KEY or FOREIGN KEY constraints or other dependencies except when using the Table Designer.</span></span> <span data-ttu-id="96f28-118">No Pesquisador de Objetos ou no [!INCLUDE[tsql](../../includes/tsql-md.md)], você deve primeiramente remover todas as dependências da coluna.</span><span class="sxs-lookup"><span data-stu-id="96f28-118">When using Object Explorer or [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first remove all dependencies on the column.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="96f28-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="96f28-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="96f28-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="96f28-120">Permissions</span></span>  
 <span data-ttu-id="96f28-121">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="96f28-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="96f28-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96f28-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-columns-by-using-object-explorer"></a><span data-ttu-id="96f28-123">Para excluir colunas usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="96f28-123">To delete columns by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="96f28-124">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96f28-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="96f28-125">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela da qual você deseja excluir colunas e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="96f28-125">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Delete**.</span></span>  
  
3.  <span data-ttu-id="96f28-126">Na caixa de diálogo **Excluir Objeto** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="96f28-126">In **Delete Object** dialog box, click **OK**.</span></span>  
  
 <span data-ttu-id="96f28-127">Se a coluna contiver restrições ou outras dependências, uma mensagem de erro será exibida na caixa de diálogo **Excluir Objeto** .</span><span class="sxs-lookup"><span data-stu-id="96f28-127">If the column contains constraints or other dependencies, an error message will display in the **Delete Object** dialog box.</span></span> <span data-ttu-id="96f28-128">Resolva o erro excluindo as restrições referenciadas.</span><span class="sxs-lookup"><span data-stu-id="96f28-128">Resolve the error by deleting the referenced constraints.</span></span>  
  
#### <a name="to-delete-columns-by-using-table-designer"></a><span data-ttu-id="96f28-129">Para excluir colunas usando o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="96f28-129">To delete columns by using Table Designer</span></span>  
  
1.  <span data-ttu-id="96f28-130">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela da qual você deseja excluir colunas e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="96f28-130">In **Object Explorer**, right-click the table from which you want to delete columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="96f28-131">Clique com o botão direito do mouse na coluna que deseja excluir e escolha **Excluir Coluna** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="96f28-131">Right-click the column you want to delete and choose **Delete Column** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="96f28-132">Se a coluna participar de uma relação (FOREIGN KEY ou PRIMARY KEY), uma mensagem solicitará que você confirme a exclusão das colunas selecionadas e suas relações.</span><span class="sxs-lookup"><span data-stu-id="96f28-132">If the column participates in a relationship (FOREIGN KEY or PRIMARY KEY), a message prompts you to confirm the deletion of the selected columns and their relationships.</span></span> <span data-ttu-id="96f28-133">Escolha **Sim**.</span><span class="sxs-lookup"><span data-stu-id="96f28-133">Choose **Yes**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="96f28-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96f28-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-columns"></a><span data-ttu-id="96f28-135">Para excluir colunas</span><span class="sxs-lookup"><span data-stu-id="96f28-135">To delete columns</span></span>  
  
1.  <span data-ttu-id="96f28-136">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96f28-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="96f28-137">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="96f28-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="96f28-138">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="96f28-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.doc_exb DROP COLUMN column_b ;  
    ```  
  
 <span data-ttu-id="96f28-139">Se a coluna contiver restrições ou outras dependências, uma mensagem de erro será retornada.</span><span class="sxs-lookup"><span data-stu-id="96f28-139">If the column contains constraints or other dependencies, an error message will be returned.</span></span> <span data-ttu-id="96f28-140">Resolva o erro excluindo as restrições referenciadas.</span><span class="sxs-lookup"><span data-stu-id="96f28-140">Resolve the error by deleting the referenced constraints.</span></span>  
  
 <span data-ttu-id="96f28-141">Para obter exemplos adicionais, consulte [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="96f28-141">For additional examples, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
##  <a name="FollowUp"></a>  
