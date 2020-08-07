---
title: Modificar colunas (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying data types
- column data types [SQL Server]
- data types [SQL Server], columns
ms.assetid: b67b95c5-61ef-4bd8-9a3e-1640eb7583ac
author: stevestein
ms.author: sstein
ms.openlocfilehash: a73c25d91b742f1cc1f7edcc8a95cdf226b2683c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575034"
---
# <a name="modify-columns-database-engine"></a><span data-ttu-id="6b7b5-102">Modificar colunas (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="6b7b5-102">Modify Columns (Database Engine)</span></span>
  <span data-ttu-id="6b7b5-103">Você pode modificar o tipo de dados de uma coluna no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b7b5-103">You can modify the data type of a column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="6b7b5-104">Modificar o tipo de dados de uma coluna que já contenha dados pode resultar na perda permanente de dados quando os dados existentes forem convertidos para o novo tipo.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-104">Modifying the data type of a column that already contains data can result in the permanent loss of data when the existing data is converted to the new type.</span></span> <span data-ttu-id="6b7b5-105">Além disso, códigos e aplicativos que dependem da coluna modificada podem falhar.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-105">In addition, code and applications that depend on the modified column may fail.</span></span> <span data-ttu-id="6b7b5-106">Isso inclui consultas, exibições, procedimentos armazenados, funções definidas pelo usuário e aplicativos clientes.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-106">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="6b7b5-107">Observe que essas falhas ocorrerão em cascata.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-107">Note that these failures will cascade.</span></span> <span data-ttu-id="6b7b5-108">Por exemplo, um procedimento armazenado que chama uma função definida pelo usuário que dependa da coluna modificada pode falhar.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-108">For example, a stored procedure that calls a user-defined function that depends on the modified column may fail.</span></span> <span data-ttu-id="6b7b5-109">Considere cuidadosamente todas as alterações que você pretende realizar em uma coluna antes fazê-las.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-109">Carefully consider any changes you want to make to a column before making it.</span></span>  
  
 <span data-ttu-id="6b7b5-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="6b7b5-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6b7b5-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="6b7b5-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6b7b5-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="6b7b5-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6b7b5-113">**Para modificar o tipo de dados de uma coluna usando:**</span><span class="sxs-lookup"><span data-stu-id="6b7b5-113">**To modify the data type of a column, using:**</span></span>  
  
     [<span data-ttu-id="6b7b5-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6b7b5-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6b7b5-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6b7b5-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6b7b5-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6b7b5-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6b7b5-117">Segurança</span><span class="sxs-lookup"><span data-stu-id="6b7b5-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6b7b5-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="6b7b5-118">Permissions</span></span>  
 <span data-ttu-id="6b7b5-119">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-119">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6b7b5-120">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6b7b5-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="6b7b5-121">Para modificar o tipo de dados de uma coluna</span><span class="sxs-lookup"><span data-stu-id="6b7b5-121">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="6b7b5-122">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela com as colunas cuja escala você deseja alterar e clique em **Design**.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-122">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="6b7b5-123">Selecione a coluna cujo tipo de dados você pretende modificar.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-123">Select the column for which you want to modify the data type.</span></span>  
  
3.  <span data-ttu-id="6b7b5-124">Na guia **Propriedades da Coluna** , clique na célula de grade da propriedade **Tipo de Dados** e selecione o novo tipo de dados na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-124">In the **Column Properties** tab, click the grid cell for the **Data Type** property and choose a new data type from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="6b7b5-125">No menu **Arquivo**, clique em **Salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b7b5-126">Quando o tipo de dados de uma coluna é modificado, o Designer de Tabela aplica o comprimento padrão do tipo de dados que foi selecionado, até mesmo quando outro já tiver sido especificado.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-126">When you modify the data type of a column, Table Designer applies the default length of the data type you selected, even if you have already specified another.</span></span> <span data-ttu-id="6b7b5-127">Defina sempre o comprimento do tipo de dados do valor desejado após especificar o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-127">Always set the data type length for to the desired value after specifying the data type.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="6b7b5-128">Se você tentar modificar o tipo de dados de uma coluna relacionada a outras tabelas, o Designer de Tabela solicitará que você confirme se a alteração deve ser feita nas colunas das outras tabelas também.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-128">If you attempt to modify the data type of a column that relates to other tables, Table Designer asks you to confirm that the change should be made to the columns in the other tables as well.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6b7b5-129">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6b7b5-129">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="6b7b5-130">Para modificar o tipo de dados de uma coluna</span><span class="sxs-lookup"><span data-stu-id="6b7b5-130">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="6b7b5-131">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b7b5-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6b7b5-132">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6b7b5-133">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6b7b5-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exy (column_a INT ) ;  
    GO  
    INSERT INTO dbo.doc_exy (column_a) VALUES (10) ;  
    GO  
    ALTER TABLE dbo.doc_exy ALTER COLUMN column_a DECIMAL (5, 2) ;  
    GO  
  
    ```  
  
 <span data-ttu-id="6b7b5-134">Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="6b7b5-134">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
