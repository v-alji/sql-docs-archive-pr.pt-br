---
title: Renomear índices | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- renaming indexes
- index names [SQL Server]
- indexes [SQL Server], renaming
ms.assetid: d3d612a1-ea1b-4d99-85d2-0a2ad54f4b0e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 184d6e20f7857c5ea3535e77e21a0630ffc7b678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583035"
---
# <a name="rename-indexes"></a><span data-ttu-id="65f47-102">Renomear índices</span><span class="sxs-lookup"><span data-stu-id="65f47-102">Rename Indexes</span></span>
  <span data-ttu-id="65f47-103">Este tópico descreve como renomear um índice no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65f47-103">This topic describes how to rename an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="65f47-104">Renomear um índice substitui o nome do índice atual pelo novo nome que você fornece.</span><span class="sxs-lookup"><span data-stu-id="65f47-104">Renaming an index replaces the current index name with the new name that you provide.</span></span> <span data-ttu-id="65f47-105">O nome especificado deve ser exclusivo dentro da tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="65f47-105">The specified name must be unique within the table or view.</span></span> <span data-ttu-id="65f47-106">Por exemplo, duas tabelas podem ter um índice nomeado **XPK_1**, mas a mesma tabela não pode ter dois índices nomeados **XPK_1**.</span><span class="sxs-lookup"><span data-stu-id="65f47-106">For example, two tables can have an index named **XPK_1**, but the same table cannot have two indexes named **XPK_1**.</span></span> <span data-ttu-id="65f47-107">Você não pode criar um índice com o mesmo nome que um índice desabilitado existente.</span><span class="sxs-lookup"><span data-stu-id="65f47-107">You cannot create an index with the same name as an existing disabled index.</span></span> <span data-ttu-id="65f47-108">Renomear um índice não faz com que o índice seja reconstruído.</span><span class="sxs-lookup"><span data-stu-id="65f47-108">Renaming an index does not cause the index to be rebuilt.</span></span>  
  
 <span data-ttu-id="65f47-109">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="65f47-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="65f47-110">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="65f47-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="65f47-111">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="65f47-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="65f47-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="65f47-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="65f47-113">**Para renomear um índice, usando:**</span><span class="sxs-lookup"><span data-stu-id="65f47-113">**To rename an index, using:**</span></span>  
  
     [<span data-ttu-id="65f47-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65f47-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="65f47-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65f47-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="65f47-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="65f47-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="65f47-117">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="65f47-117">Limitations and Restrictions</span></span>  
 <span data-ttu-id="65f47-118">Quando você cria uma restrição PRIMARY KEY ou UNIQUE em uma tabela, um índice com o mesmo nome da restrição é automaticamente criado para a tabela.</span><span class="sxs-lookup"><span data-stu-id="65f47-118">When you create a PRIMARY KEY or UNIQUE constraint on a table, an index with the same name as the constraint is automatically created for the table.</span></span> <span data-ttu-id="65f47-119">Como os nomes de índice devem ser exclusivos dentro de uma tabela, você não pode criar ou renomear um índice com o mesmo nome de uma restrição PRIMARY KEY ou UNIQUE existente na tabela.</span><span class="sxs-lookup"><span data-stu-id="65f47-119">Because index names must be unique within the table, you cannot create or rename an index to have the same name as an existing PRIMARY KEY or UNIQUE constraint on the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="65f47-120">Segurança</span><span class="sxs-lookup"><span data-stu-id="65f47-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="65f47-121">Permissões</span><span class="sxs-lookup"><span data-stu-id="65f47-121">Permissions</span></span>  
 <span data-ttu-id="65f47-122">Requer a permissão ALTER no índice.</span><span class="sxs-lookup"><span data-stu-id="65f47-122">Requires ALTER permission on the index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="65f47-123">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65f47-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-an-index-by-using-the-table-designer"></a><span data-ttu-id="65f47-124">Para renomear um índice usando o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="65f47-124">To rename an index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="65f47-125">No Pesquisador de Objetos, clique no sinal de adição para expandir o banco de dados que contém a tabela na qual você deseja renomear um índice.</span><span class="sxs-lookup"><span data-stu-id="65f47-125">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="65f47-126">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="65f47-126">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="65f47-127">Clique com o botão direito do mouse na tabela na qual você deseja renomear um índice e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="65f47-127">Right-click the table on which you want to rename an index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="65f47-128">No menu **Designer de Tabela** , clique em **Índices/Chaves**.</span><span class="sxs-lookup"><span data-stu-id="65f47-128">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="65f47-129">Selecione o índice a ser renomeado na caixa de texto **Índice ou Chave Exclusiva/Primária Selecionada** .</span><span class="sxs-lookup"><span data-stu-id="65f47-129">Select the index you want to rename in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
6.  <span data-ttu-id="65f47-130">Na grade, clique em **Nome** e digite um nome novo na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="65f47-130">In the grid, click **Name** and type a new name into the text box.</span></span>  
  
7.  <span data-ttu-id="65f47-131">Clique em **fechar**</span><span class="sxs-lookup"><span data-stu-id="65f47-131">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="65f47-132">No menu **Arquivo** , clique em **Salvar**_table_name_.</span><span class="sxs-lookup"><span data-stu-id="65f47-132">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-rename-an-index-by-using-object-explorer"></a><span data-ttu-id="65f47-133">Para renomear um índice usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="65f47-133">To rename an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="65f47-134">No Pesquisador de Objetos, clique no sinal de adição para expandir o banco de dados que contém a tabela na qual você deseja renomear um índice.</span><span class="sxs-lookup"><span data-stu-id="65f47-134">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="65f47-135">Clique no sinal de adição para expandir a pasta **Tabelas** .</span><span class="sxs-lookup"><span data-stu-id="65f47-135">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="65f47-136">Clique no sinal de adição para expandir a tabela na qual você deseja renomear um índice.</span><span class="sxs-lookup"><span data-stu-id="65f47-136">Click the plus sign to expand the table on which you want to rename an index.</span></span>  
  
4.  <span data-ttu-id="65f47-137">Clique no sinal de adição para expandir a pasta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="65f47-137">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="65f47-138">Clique com o botão direito do mouse no índice a ser renomeado e selecione **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="65f47-138">Right-click the index you want to rename and select **Rename**.</span></span>  
  
6.  <span data-ttu-id="65f47-139">Digite o novo nome do índice e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="65f47-139">Type the index's new name and press Enter.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="65f47-140">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65f47-140">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-an-index"></a><span data-ttu-id="65f47-141">Para renomear um índice</span><span class="sxs-lookup"><span data-stu-id="65f47-141">To rename an index</span></span>  
  
1.  <span data-ttu-id="65f47-142">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65f47-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="65f47-143">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="65f47-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="65f47-144">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="65f47-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    --Renames the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table to IX_VendorID.   
  
    EXEC sp_rename N'Purchasing.ProductVendor.IX_ProductVendor_VendorID', N'IX_VendorID', N'INDEX';   
    GO  
    ```  
  
 <span data-ttu-id="65f47-145">Para obter mais informações, veja [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="65f47-145">For more information, see  [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
