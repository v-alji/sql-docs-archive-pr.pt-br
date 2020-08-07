---
title: Renomear colunas (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], names
- renaming columns
- column names [SQL Server]
ms.assetid: 7c71ec9f-0180-4398-b32a-4bfb7592e75d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6871ab82eaa17aa5e392e6b2bb3f5c60058f9af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581707"
---
# <a name="rename-columns-database-engine"></a><span data-ttu-id="b6626-102">Renomear colunas (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="b6626-102">Rename Columns (Database Engine)</span></span>
  <span data-ttu-id="b6626-103">Você pode renomear uma coluna de tabela no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6626-103">You can rename a table column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b6626-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="b6626-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b6626-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b6626-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b6626-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b6626-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b6626-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="b6626-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b6626-108">**Para renomear colunas, usando:**</span><span class="sxs-lookup"><span data-stu-id="b6626-108">**To rename columns, using:**</span></span>  
  
     [<span data-ttu-id="b6626-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b6626-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b6626-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b6626-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b6626-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b6626-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b6626-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b6626-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b6626-113">Renomear uma coluna não renomeia automaticamente as referências a essa coluna.</span><span class="sxs-lookup"><span data-stu-id="b6626-113">Renaming a column will not automatically rename references to that column.</span></span> <span data-ttu-id="b6626-114">É necessário modificar manualmente todos os objetos que fazem referência à coluna renomeada.</span><span class="sxs-lookup"><span data-stu-id="b6626-114">You must modify any objects that reference the renamed column manually.</span></span> <span data-ttu-id="b6626-115">Por exemplo, se você renomear uma coluna de tabela e aquela coluna for referenciada em um gatilho, será necessário modificar o gatilho para que ele reflita o nome novo da coluna.</span><span class="sxs-lookup"><span data-stu-id="b6626-115">For example, if you rename a table column and that column is referenced in a trigger, you must modify the trigger to reflect the new column name.</span></span> <span data-ttu-id="b6626-116">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) para listar as dependências do objeto antes de renomeá-lo.</span><span class="sxs-lookup"><span data-stu-id="b6626-116">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the object before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b6626-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="b6626-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b6626-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="b6626-118">Permissions</span></span>  
 <span data-ttu-id="b6626-119">Requer a permissão ALTER no objeto.</span><span class="sxs-lookup"><span data-stu-id="b6626-119">Requires ALTER permission on the object.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b6626-120">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b6626-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-column-using-object-explorer"></a><span data-ttu-id="b6626-121">Para renomear uma coluna usando o Pesquisador de Objetos</span><span class="sxs-lookup"><span data-stu-id="b6626-121">To rename a column using Object Explorer</span></span>  
  
1.  <span data-ttu-id="b6626-122">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6626-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6626-123">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela na qual você deseja renomear colunas e selecione **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="b6626-123">In **Object Explorer**, right-click the table in which you want to rename columns and choose **Rename**.</span></span>  
  
3.  <span data-ttu-id="b6626-124">Digite um novo nome para a coluna.</span><span class="sxs-lookup"><span data-stu-id="b6626-124">Type a new column name.</span></span>  
  
#### <a name="to-rename-a-column-using-table-designer"></a><span data-ttu-id="b6626-125">Para renomear uma coluna usando o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="b6626-125">To rename a column using Table Designer</span></span>  
  
1.  <span data-ttu-id="b6626-126">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela na qual você deseja renomear colunas e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="b6626-126">In **Object Explorer**, right-click the table to which you want to rename columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="b6626-127">Em **Nome da Coluna**, selecione o nome que você deseja alterar e digite um nome novo.</span><span class="sxs-lookup"><span data-stu-id="b6626-127">Under **Column Name**, select the name you want to change and type a new one.</span></span>  
  
3.  <span data-ttu-id="b6626-128">No menu **Arquivo**, clique em **Salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="b6626-128">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6626-129">Você também pode alterar o nome de uma coluna na guia **Propriedades da Coluna** . Selecione a coluna cujo nome você deseja alterar e digite um novo valor para **Nome**.</span><span class="sxs-lookup"><span data-stu-id="b6626-129">You can also change the name of a column in the **Column Properties** tab. Select the column whose name you want to change and type a new value for **Name**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b6626-130">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b6626-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="b6626-131">**Para renomear uma coluna**</span><span class="sxs-lookup"><span data-stu-id="b6626-131">**To rename a column**</span></span>  
  
#### <a name="to-rename-a-column"></a><span data-ttu-id="b6626-132">Para renomear uma coluna</span><span class="sxs-lookup"><span data-stu-id="b6626-132">To rename a column</span></span>  
  
1.  <span data-ttu-id="b6626-133">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6626-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6626-134">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b6626-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b6626-135">O exemplo a seguir renomeia a coluna `TerritoryID` na tabela `Sales.SalesTerritory` como `TerrID`.</span><span class="sxs-lookup"><span data-stu-id="b6626-135">The following example renames the column `TerritoryID` in the table `Sales.SalesTerritory` to `TerrID`.</span></span> <span data-ttu-id="b6626-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b6626-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename 'Sales.SalesTerritory.TerritoryID', 'TerrID', 'COLUMN';  
    GO  
    ```  
  
 <span data-ttu-id="b6626-137">Para obter mais informações, veja [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b6626-137">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
