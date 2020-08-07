---
title: Criar tabelas (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table creation [SQL Server], Visual Database Tools
ms.assetid: 6f7c6ac5-e6d3-4dca-831e-b28442ba535b
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8d84a4da6a10fbcbae311fe1bf738c03b85a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584077"
---
# <a name="create-tables-database-engine"></a><span data-ttu-id="a8db1-102">Criar tabelas (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="a8db1-102">Create Tables (Database Engine)</span></span>
  <span data-ttu-id="a8db1-103">Você pode criar uma nova tabela, nomeá-la e adicioná-la a um banco de dados existente no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8db1-103">You can create a new table, name it, and add it to an existing database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>

> [!NOTE]
>  <span data-ttu-id="a8db1-104">Se você estiver conectado a um banco de dados SQL Azure, a nova opção de tabela iniciará um script de modelo de criação de tabela.</span><span class="sxs-lookup"><span data-stu-id="a8db1-104">If you are connected to a SQL Azure database, the new table option launches a create table template script.</span></span> <span data-ttu-id="a8db1-105">Edite os parâmetros e execute o script para criar uma nova tabela.</span><span class="sxs-lookup"><span data-stu-id="a8db1-105">Edit the parameters, then run the script to create a new table.</span></span> <span data-ttu-id="a8db1-106">Para obter mais informações, consulte [SQL Azure Overview](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="a8db1-106">For more information, see [SQL Azure Overview](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx).</span></span>

 <span data-ttu-id="a8db1-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="a8db1-107">**In This Topic**</span></span>

-   <span data-ttu-id="a8db1-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="a8db1-108">**Before you begin:**</span></span>

     [<span data-ttu-id="a8db1-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="a8db1-109">Security</span></span>](#Security)

-   <span data-ttu-id="a8db1-110">**Para criar uma tabela usando:**</span><span class="sxs-lookup"><span data-stu-id="a8db1-110">**To create a table, using:**</span></span>

     [<span data-ttu-id="a8db1-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8db1-111">SQL Server Management Studio</span></span>](#SSMSProcedure)

     [<span data-ttu-id="a8db1-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8db1-112">Transact-SQL</span></span>](#TsqlProcedure)

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a8db1-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a8db1-113">Before You Begin</span></span>

###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a8db1-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="a8db1-114">Security</span></span>

####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a8db1-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="a8db1-115">Permissions</span></span>
 <span data-ttu-id="a8db1-116">Requer a permissão CREATE TABLE no banco de dados e a permissão ALTER no esquema no qual a tabela está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="a8db1-116">Requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>

 <span data-ttu-id="a8db1-117">Se alguma coluna da instrução CREATE TABLE for definida como um tipo de dados CLR definido pelo usuário, a propriedade do tipo ou a permissão REFERENCES será necessária.</span><span class="sxs-lookup"><span data-stu-id="a8db1-117">If any columns in the CREATE TABLE statement are defined as a CLR user-defined type, either ownership of the type or REFERENCES permission on it is required.</span></span>

 <span data-ttu-id="a8db1-118">Se alguma coluna da instrução CREATE TABLE tiver uma coleção de esquemas XML associada a ela, a propriedade da coleção de esquemas XML ou a permissão REFERENCES é necessária.</span><span class="sxs-lookup"><span data-stu-id="a8db1-118">If any columns in the CREATE TABLE statement have an XML schema collection associated with them, either ownership of the XML schema collection or REFERENCES permission on it is required.</span></span>

##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a8db1-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8db1-119">Using SQL Server Management Studio</span></span>

#### <a name="to-create-a-table-with-table-designer"></a><span data-ttu-id="a8db1-120">Para criar uma tabela com o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="a8db1-120">To create a table with Table Designer</span></span>

1.  <span data-ttu-id="a8db1-121">No **Pesquisador de Objetos**, conecte-se à instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] que contém o banco de dados a ser modificado.</span><span class="sxs-lookup"><span data-stu-id="a8db1-121">In **Object Explorer**, connect to the instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] that contains the database to be modified.</span></span>

2.  <span data-ttu-id="a8db1-122">No **Pesquisador de Objetos**, expanda o nó **Bancos de Dados** e, em seguida, expanda o banco de dados que conterá a nova tabela.</span><span class="sxs-lookup"><span data-stu-id="a8db1-122">In **Object Explorer**, expand the **Databases** node and then expand the database that will contain the new table.</span></span>

3.  <span data-ttu-id="a8db1-123">No Pesquisador de Objetos, clique com o botão direito do mouse no nó **Tabelas** do banco de dados e clique em **Nova Tabela**.</span><span class="sxs-lookup"><span data-stu-id="a8db1-123">In Object Explorer, right-click the **Tables** node of your database and then click **New Table**.</span></span>

4.  <span data-ttu-id="a8db1-124">Digite nomes de coluna, escolha tipos de dados e opte por permitir ou não nulos para cada coluna, conforme ilustrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="a8db1-124">Type column names, choose data types, and choose whether to allow nulls for each column as shown in the following illustration.</span></span>

     <span data-ttu-id="a8db1-125">![AddColumnsinTableDesigner](../../database-engine/media/addcolumnsintabledesigner.gif "AddColumnsinTableDesigner")</span><span class="sxs-lookup"><span data-stu-id="a8db1-125">![AddColumnsinTableDesigner](../../database-engine/media/addcolumnsintabledesigner.gif "AddColumnsinTableDesigner")</span></span>

5.  <span data-ttu-id="a8db1-126">Para especificar mais propriedades para uma coluna, como valores de identidade ou de coluna computada, clique na coluna e na guia propriedades de coluna, escolha as propriedades adequadas.</span><span class="sxs-lookup"><span data-stu-id="a8db1-126">To specify more properties for a column, such as identity or computed column values, click the column and in the column properties tab, choose the appropriate properties.</span></span> <span data-ttu-id="a8db1-127">Para obter mais informações sobre as propriedades de coluna, veja [Propriedades de coluna da tabela &#40;SQL Server Management Studio&#41;](table-column-properties-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="a8db1-127">For more information about column properties, see [Table Column Properties &#40;SQL Server Management Studio&#41;](table-column-properties-sql-server-management-studio.md).</span></span>

6.  <span data-ttu-id="a8db1-128">Para especificar uma coluna como chave primária, clique com o botão direito do mouse na coluna e selecione **Definir Chave Primária**.</span><span class="sxs-lookup"><span data-stu-id="a8db1-128">To specify a column as a primary key, right-click the column and select **Set Primary Key**.</span></span> <span data-ttu-id="a8db1-129">Para obter mais informações, consulte [Create Primary Keys](../tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="a8db1-129">For more information, see [Create Primary Keys](../tables/create-primary-keys.md).</span></span>

7.  <span data-ttu-id="a8db1-130">Para criar relações de chave estrangeira, restrições de verificação ou índices, clique com o botão direito do mouse no painel Designer de Tabela e selecione um objeto da lista, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="a8db1-130">To create foreign key relationships, check constraints, or indexes, right-click in the Table Designer pane and select an object from the list as shown in the following illustration.</span></span>

     <span data-ttu-id="a8db1-131">![AddTableObjects](../../database-engine/media/addtableobjects.gif "AddTableObjects")</span><span class="sxs-lookup"><span data-stu-id="a8db1-131">![AddTableObjects](../../database-engine/media/addtableobjects.gif "AddTableObjects")</span></span>

     <span data-ttu-id="a8db1-132">Para obter mais informações sobre esses objetos, consulte [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) e [Indexes](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="a8db1-132">For more information about these objects, see [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) and [Indexes](../indexes/indexes.md).</span></span>

8.  <span data-ttu-id="a8db1-133">Por padrão, a tabela está contida no esquema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="a8db1-133">By default, the table is contained in the **dbo** schema.</span></span> <span data-ttu-id="a8db1-134">Para especificar um esquema diferente para a tabela, clique com o botão direito do mouse no painel Designer de Tabela e selecione **Propriedades** , conforme ilustrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="a8db1-134">To specify a different schema for the table, right-click in the Table Designer pane and select **Properties** as shown in the following illustration.</span></span> <span data-ttu-id="a8db1-135">Na lista suspensa **Esquema** , selecione o esquema apropriado.</span><span class="sxs-lookup"><span data-stu-id="a8db1-135">From the **Schema** drop-down list, select the appropriate schema.</span></span>

     <span data-ttu-id="a8db1-136">![Specifyatableschema](../../database-engine/media/specifyatableschema.gif "Specifyatableschema")</span><span class="sxs-lookup"><span data-stu-id="a8db1-136">![Specifyatableschema](../../database-engine/media/specifyatableschema.gif "Specifyatableschema")</span></span>

     <span data-ttu-id="a8db1-137">Para obter mais informações sobre esquemas, consulte [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span><span class="sxs-lookup"><span data-stu-id="a8db1-137">For more information about schemas, see [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span></span>

9. <span data-ttu-id="a8db1-138">No menu **Arquivo**, escolha **Salvar** *nome da tabela*.</span><span class="sxs-lookup"><span data-stu-id="a8db1-138">From the **File** menu, choose **Save** *table name*.</span></span>

10. <span data-ttu-id="a8db1-139">Na caixa de diálogo **Escolher Nome** , digite um nome para a tabela e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8db1-139">In the **Choose Name** dialog box, type a name for the table and click **OK**.</span></span>

11. <span data-ttu-id="a8db1-140">Para exibir a nova tabela, em **Pesquisador de Objetos**, expanda o nó **Tabelas** e pressione **F5** para atualizar a lista de objetos.</span><span class="sxs-lookup"><span data-stu-id="a8db1-140">To view the new table, in **Object Explorer**, expand the **Tables** node and press **F5** to refresh the list of objects.</span></span> <span data-ttu-id="a8db1-141">A nova tabela é exibida na lista de tabelas.</span><span class="sxs-lookup"><span data-stu-id="a8db1-141">The new table is displayed in the list of tables.</span></span>

##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a8db1-142">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8db1-142">Using Transact-SQL</span></span>

#### <a name="to-create-a-table-in-the-query-editor"></a><span data-ttu-id="a8db1-143">Para criar uma tabela no Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="a8db1-143">To create a table in the Query Editor</span></span>

1.  <span data-ttu-id="a8db1-144">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8db1-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>

2.  <span data-ttu-id="a8db1-145">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="a8db1-145">On the Standard bar, click **New Query**.</span></span>

3.  <span data-ttu-id="a8db1-146">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a8db1-146">Copy and paste the following example into the query window and click **Execute**.</span></span>

    ```
    CREATE TABLE dbo.PurchaseOrderDetail
    (
        PurchaseOrderID int NOT NULL
        ,LineNumber smallint NOT NULL
        ,ProductID int NULL
        ,UnitPrice money NULL
        ,OrderQty smallint NULL
        ,ReceivedQty float NULL
        ,RejectedQty float NULL
        ,DueDate datetime NULL
    );
    ```

 <span data-ttu-id="a8db1-147">Para obter mais exemplos, veja [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a8db1-147">For more examples, see [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span>


