---
title: Adicionar colunas a uma tabela (mecanismo de banco de dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- adding columns
ms.assetid: abeb8d52-d562-4e29-9e1e-2923ae874859
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7e9294de10be0df9ef470c75d0934e9f8787b55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573884"
---
# <a name="add-columns-to-a-table-database-engine"></a><span data-ttu-id="b6fe3-102">Adicionar colunas a uma tabela (Mecanismo de Banco de Dados)</span><span class="sxs-lookup"><span data-stu-id="b6fe3-102">Add Columns to a Table (Database Engine)</span></span>
  <span data-ttu-id="b6fe3-103">Este tópico descreve como adicionar novas colunas a uma tabela no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6fe3-103">This topic describes how to add new columns to a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b6fe3-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="b6fe3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b6fe3-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b6fe3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b6fe3-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b6fe3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b6fe3-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="b6fe3-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b6fe3-108">**Para inserir colunas usando:**</span><span class="sxs-lookup"><span data-stu-id="b6fe3-108">**To insert columns, using:**</span></span>  
  
     [<span data-ttu-id="b6fe3-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b6fe3-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b6fe3-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b6fe3-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b6fe3-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b6fe3-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b6fe3-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b6fe3-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b6fe3-113">Usar a instrução ALTER TABLE para adicionar colunas a uma tabela automaticamente adiciona essas colunas ao final da tabela.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-113">Using the ALTER TABLE statement to add columns to a table automatically adds those columns to the end of the table.</span></span> <span data-ttu-id="b6fe3-114">Se você desejar que as colunas fiquem em uma ordem específica na tabela, use o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6fe3-114">If you want the columns in a specific order in the table, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b6fe3-115">No entanto, observe que esta não é uma prática recomendada de design de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-115">However, note that this is not a database design best practice.</span></span> <span data-ttu-id="b6fe3-116">A prática recomendada é especificar a ordem em que as colunas serão retornadas nos níveis de aplicativo e de consulta.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-116">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="b6fe3-117">Você não deve confiar no uso de SELECT \* para retornar todas as colunas na ordem esperada com base na ordem em que são definidas na tabela.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-117">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="b6fe3-118">Sempre especifique as colunas por nome em suas consultas e aplicativos na ordem em que você gostaria que elas aparecessem.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-118">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b6fe3-119">Segurança</span><span class="sxs-lookup"><span data-stu-id="b6fe3-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b6fe3-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="b6fe3-120">Permissions</span></span>  
 <span data-ttu-id="b6fe3-121">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b6fe3-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b6fe3-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-insert-columns-into-a-table-with-table-designer"></a><span data-ttu-id="b6fe3-123">Para inserir colunas em uma tabela com o Designer de Tabela</span><span class="sxs-lookup"><span data-stu-id="b6fe3-123">To insert columns into a table with Table Designer</span></span>  
  
1.  <span data-ttu-id="b6fe3-124">No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela à qual você deseja adicionar colunas e selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-124">In **Object Explorer**, right-click the table to which you want to add columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="b6fe3-125">Clique na primeira célula vazia da coluna **Nome da Coluna** .</span><span class="sxs-lookup"><span data-stu-id="b6fe3-125">Click in the first blank cell in the **Column Name** column.</span></span>  
  
3.  <span data-ttu-id="b6fe3-126">Digite o nome de coluna na célula.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-126">Type the column name in the cell.</span></span> <span data-ttu-id="b6fe3-127">O nome da coluna é um valor obrigatório.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-127">The column name is a required value.</span></span>  
  
4.  <span data-ttu-id="b6fe3-128">Pressione a tecla TAB para ir para a célula **Tipo de Dados** e selecione um tipo de dados no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-128">Press the TAB key to go to the **Data Type** cell and select a data type from the dropdown.</span></span> <span data-ttu-id="b6fe3-129">Trata-se também de um valor obrigatório, e será atribuído o valor padrão caso você não selecione um.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-129">This too is a required value, and will be assigned the default value if you don't choose one.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b6fe3-130"> O valor padrão de **Opções** pode ser alterado na caixa de diálogo de **Ferramentas do Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-130">You can change the default value in the **Options** dialog box under **Database Tools**.</span></span>  
  
5.  <span data-ttu-id="b6fe3-131">Prossiga com a definição de outras propriedades de coluna na guia **Propriedades da Coluna** .</span><span class="sxs-lookup"><span data-stu-id="b6fe3-131">Continue to define any other column properties in the **Column Properties** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b6fe3-132"> Valores padrão de propriedades de coluna são adicionados quando uma nova coluna é criada. Contudo, é possível alterá-los na guia **Propriedades da Coluna** .</span><span class="sxs-lookup"><span data-stu-id="b6fe3-132">The default values for your column properties are added when you create a new column, but you can change them in the **Column Properties** tab.</span></span>  
  
6.  <span data-ttu-id="b6fe3-133">Quando você terminar de adicionar as colunas, no menu **Arquivo**, escolha **Salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-133">When you are finished adding columns, from the **File** menu, choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b6fe3-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b6fe3-134">Using Transact-SQL</span></span>  
  
#### <a name="to-insert-columns-into-a-table"></a><span data-ttu-id="b6fe3-135">Para inserir colunas em uma tabela</span><span class="sxs-lookup"><span data-stu-id="b6fe3-135">To insert columns into a table</span></span>  
  
1.  <span data-ttu-id="b6fe3-136">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6fe3-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6fe3-137">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b6fe3-138">O exemplo a seguir adiciona duas colunas à tabela `dbo.doc_exa`.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-138">The following example adds two columns to the table `dbo.doc_exa`.</span></span> <span data-ttu-id="b6fe3-139">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b6fe3-139">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
```  
ALTER TABLE dbo.doc_exa ADD column_b VARCHAR(20) NULL, column_c INT NULL ;  
```  
  
##  <a name="for-more-information-see-alter-table-40transact-sql41"></a><a name="FollowUp"></a><span data-ttu-id="b6fe3-140">Para obter mais informações, consulte [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="b6fe3-140">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
