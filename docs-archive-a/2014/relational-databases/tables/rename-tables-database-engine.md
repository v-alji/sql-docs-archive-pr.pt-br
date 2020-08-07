---
title: Renomear tabelas (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table renaming [SQL Server]
- table names [SQL Server]
- tables [SQL Server], Visual Database Tools
- renaming tables
ms.assetid: 2f5c922d-4d71-4694-9fca-28dd99375799
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e73bbb92d8fd3fdcaa7756ce1dcb74d8cd598b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581704"
---
# <a name="rename-tables-database-engine"></a><span data-ttu-id="22ea5-102">Renomear tabelas (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="22ea5-102">Rename Tables (Database Engine)</span></span>
  <span data-ttu-id="22ea5-103">Você pode renomear uma tabela no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22ea5-103">You can rename a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="22ea5-104">Pense cuidadosamente antes de renomear uma tabela.</span><span class="sxs-lookup"><span data-stu-id="22ea5-104">Think carefully before you rename a table.</span></span> <span data-ttu-id="22ea5-105">Se as consultas, as exibições, as funções definidas pelo usuário, os procedimentos armazenados ou os programas existentes se referirem à tabela, a modificação do nome tornará esses objetivos inválidos.</span><span class="sxs-lookup"><span data-stu-id="22ea5-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="22ea5-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="22ea5-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="22ea5-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="22ea5-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="22ea5-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="22ea5-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="22ea5-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="22ea5-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="22ea5-110">**Para renomear uma tabela usando:**</span><span class="sxs-lookup"><span data-stu-id="22ea5-110">**To rename a table, using:**</span></span>  
  
     [<span data-ttu-id="22ea5-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="22ea5-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="22ea5-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="22ea5-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="22ea5-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="22ea5-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="22ea5-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="22ea5-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="22ea5-115">Renomear uma tabela não renomeia automaticamente as referências a essa tabela.</span><span class="sxs-lookup"><span data-stu-id="22ea5-115">Renaming a table will not automatically rename references to that table.</span></span> <span data-ttu-id="22ea5-116">É necessário modificar manualmente todos os objetos que fazem referência à tabela renomeada.</span><span class="sxs-lookup"><span data-stu-id="22ea5-116">You must manually modify any objects that reference the renamed table.</span></span> <span data-ttu-id="22ea5-117">Por exemplo, se você renomear uma tabela e essa tabela for referenciada em um gatilho, será necessário modificar o gatilho para que ele reflita o novo nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="22ea5-117">For example, if you rename a table and that table is referenced in a trigger, you must modify the trigger to reflect the new table name.</span></span> <span data-ttu-id="22ea5-118">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) para listar as dependências dessa tabela antes de renomeá-la.</span><span class="sxs-lookup"><span data-stu-id="22ea5-118">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the table before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="22ea5-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="22ea5-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="22ea5-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="22ea5-120">Permissions</span></span>  
 <span data-ttu-id="22ea5-121">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="22ea5-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="22ea5-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="22ea5-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="22ea5-123">Para renomear uma tabela</span><span class="sxs-lookup"><span data-stu-id="22ea5-123">To rename a table</span></span>  
  
1.  <span data-ttu-id="22ea5-124">No Pesquisador de Objetos, clique com o botão direito do mouse na tabela que você deseja renomear e escolha **Design** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="22ea5-124">In Object Explorer, right-click the table you want to rename and choose **Design** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="22ea5-125">No menu **Exibir** , escolha **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="22ea5-125">From the **View** menu, choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="22ea5-126">No campo do valor **Nome** , na janela **Propriedades** , digite um novo nome para a tabela.</span><span class="sxs-lookup"><span data-stu-id="22ea5-126">In the field for the **Name** value in the **Properties** window, type a new name for the table.</span></span>  
  
4.  <span data-ttu-id="22ea5-127">Para cancelar essa ação, pressione a tecla ESC antes de deixar o campo.</span><span class="sxs-lookup"><span data-stu-id="22ea5-127">To cancel this action, press the ESC key before leaving this field.</span></span>  
  
5.  <span data-ttu-id="22ea5-128">No menu **arquivo** , escolha **salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="22ea5-128">From the **File** menu choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="22ea5-129">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="22ea5-129">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="22ea5-130">Para renomear uma tabela</span><span class="sxs-lookup"><span data-stu-id="22ea5-130">To rename a table</span></span>  
  
1.  <span data-ttu-id="22ea5-131">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22ea5-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="22ea5-132">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="22ea5-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="22ea5-133">O exemplo a seguir renomeia a tabela `SalesTerritory` como `SalesTerr` no esquema `Sales` .</span><span class="sxs-lookup"><span data-stu-id="22ea5-133">The following example renames the `SalesTerritory` table to `SalesTerr` in the `Sales` schema.</span></span> <span data-ttu-id="22ea5-134">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="22ea5-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    EXEC sp_rename 'Sales.SalesTerritory', 'SalesTerr';  
    ```  
  
 <span data-ttu-id="22ea5-135">Para obter exemplos adicionais, consulte [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="22ea5-135">For additional examples, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
