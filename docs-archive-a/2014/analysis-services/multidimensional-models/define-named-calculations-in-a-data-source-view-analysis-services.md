---
title: Definir cálculos nomeados em uma exibição da fonte de dados (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying named calculations
- data source views [Analysis Services], named calculations
- named calculations [Analysis Services]
ms.assetid: 729e7b12-6185-4b73-8bcb-cfe459b15355
author: minewiskan
ms.author: owend
ms.openlocfilehash: ae901c340fe29c042430d928a4abaea8e8cfe84b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574383"
---
# <a name="define-named-calculations-in-a-data-source-view-analysis-services"></a><span data-ttu-id="5471e-102">Definir cálculos nomeados em uma exibição da fonte de dados (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="5471e-102">Define Named Calculations in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="5471e-103">Um cálculo nomeado é uma expressão SQL representada como uma coluna calculada.</span><span class="sxs-lookup"><span data-stu-id="5471e-103">A named calculation is a SQL expression represented as a calculated column.</span></span> <span data-ttu-id="5471e-104">Essa expressão aparece e se comporta como uma coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="5471e-104">This expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="5471e-105">Um cálculo nomeado permite que você estenda o esquema relacional das tabelas ou exibições existentes sem modificar as tabelas ou exibições da fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="5471e-105">A named calculation lets you extend the relational schema of existing tables or views in a data source view without modifying the tables or views in the underlying data source.</span></span> <span data-ttu-id="5471e-106">Considere os seguintes exemplos:</span><span class="sxs-lookup"><span data-stu-id="5471e-106">Consider the following examples:</span></span>

-   <span data-ttu-id="5471e-107">Crie um único cálculo nomeado que é derivado de várias colunas em uma tabela de fato (por exemplo, criando Quantidade de Imposto multiplicando uma taxa de imposto por um preço de venda).</span><span class="sxs-lookup"><span data-stu-id="5471e-107">Create a single named calculation that is derived from multiple columns in a fact table (for example, creating Tax Amount by multiplying a tax rate by a sales price).</span></span>

-   <span data-ttu-id="5471e-108">Construa um nome amigável de usuário para um membro de dimensão.</span><span class="sxs-lookup"><span data-stu-id="5471e-108">Construct a user friendly name for a dimension member.</span></span>

-   <span data-ttu-id="5471e-109">Como um aprimoramento de desempenho de consulta, crie um cálculo nomeado no DSV em vez de criar um membro calculado em um cubo.</span><span class="sxs-lookup"><span data-stu-id="5471e-109">As a query performance enhancement, create a named calculation in the DSV instead of creating a calculated member in a cube.</span></span> <span data-ttu-id="5471e-110">Cálculos nomeados são calculados durante o processamento, enquanto os membros calculados são calculados no momento da consulta.</span><span class="sxs-lookup"><span data-stu-id="5471e-110">Named calculations are calculated during processing whereas calculated members are calculated at query time.</span></span>

## <a name="creating-named-calculations"></a><span data-ttu-id="5471e-111">Criando cálculos nomeados</span><span class="sxs-lookup"><span data-stu-id="5471e-111">Creating Named Calculations</span></span>

> [!NOTE]
>  <span data-ttu-id="5471e-112">Não é possível adicionar um cálculo nomeado a uma consulta nomeada nem usar como base de uma consulta nomeada uma tabela que contém um cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="5471e-112">You cannot add a named calculation to a named query, nor can you base a named query on a table that contains a named calculation.</span></span>

 <span data-ttu-id="5471e-113">Ao criar um cálculo nomeado, você especifica uma expressão SQL e, opcionalmente, uma descrição do cálculo.</span><span class="sxs-lookup"><span data-stu-id="5471e-113">When you create a named calculation, you specify a name, the SQL expression, and, optionally, a description of the calculation.</span></span> <span data-ttu-id="5471e-114">A expressão SQL pode fazer referência a outras tabelas da exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="5471e-114">The SQL expression can refer to other tables in the data source view.</span></span> <span data-ttu-id="5471e-115">Depois de definido o cálculo nomeado, a expressão é um cálculo nomeado enviado ao provedor da fonte de dados e validado como a instrução SQL a seguir, na qual `<Expression>` contém a expressão que define o cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="5471e-115">After the named calculation is defined, the expression in a named calculation is sent to the provider for the data source and validated as the following SQL statement in which `<Expression>` contains the expression that defines the named calculation.</span></span>

```
SELECT 
   <Table Name in Data Source>.*, 
   <Expression> AS <Column Name> 
FROM 
   <Table Name in Data Source> AS <Table Name in Data Source View>
```

 <span data-ttu-id="5471e-116">O tipo de dados da coluna é determinado pelo tipo de dados do valor escalar retornado pela expressão.</span><span class="sxs-lookup"><span data-stu-id="5471e-116">The data type of the column is determined by the data type of the scalar value returned by the expression.</span></span> <span data-ttu-id="5471e-117">Se o provedor não encontrar erros na expressão, a coluna será adicionada à tabela.</span><span class="sxs-lookup"><span data-stu-id="5471e-117">If the provider does not find any errors in the expression, the column is added to the table.</span></span>

 <span data-ttu-id="5471e-118">Colunas às quais a expressão faz referência não devem ser qualificadas ou devem ser qualificadas somente pelo nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="5471e-118">Columns referenced in the expression should not be qualified or should be qualified by the table name only.</span></span> <span data-ttu-id="5471e-119">Por exemplo, para fazer referência à coluna SaleAmount em uma tabela, o valor `SaleAmount` ou `Sales.SaleAmount` é válido, mas `dbo.Sales.SaleAmount` produzirá um erro.</span><span class="sxs-lookup"><span data-stu-id="5471e-119">For example, to refer to the SaleAmount column in a table, `SaleAmount` or `Sales.SaleAmount` is valid, but `dbo.Sales.SaleAmount` generates an error.</span></span>

 <span data-ttu-id="5471e-120">A expressão não é encerrada entre parênteses automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5471e-120">The expression is not automatically enclosed between parentheses.</span></span> <span data-ttu-id="5471e-121">Portanto, se uma expressão, como uma instrução SELECT, exigir parênteses, digite-os na caixa **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="5471e-121">Therefore, if an expression, such as a SELECT statement, requires parentheses, you must type the parentheses in the **Expression** box.</span></span> <span data-ttu-id="5471e-122">Por exemplo, a expressão a seguir será válida somente se você digitar os parênteses.</span><span class="sxs-lookup"><span data-stu-id="5471e-122">For example, the following expression is valid only if you type the parentheses.</span></span>

```
(SELECT Description FROM Categories WHERE Categories.CategoryID = CategoryID)
```

## <a name="add-or-edit-a-named-calculation"></a><span data-ttu-id="5471e-123">Adicionar ou editar um cálculo nomeado</span><span class="sxs-lookup"><span data-stu-id="5471e-123">Add or Edit a Named Calculation</span></span>

1.  <span data-ttu-id="5471e-124">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto ou conecte-se ao banco de dados que contém a exibição da fonte de dados na qual você deseja definir um cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="5471e-124">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to define a named calculation.</span></span>

2.  <span data-ttu-id="5471e-125">No Gerenciador de Soluções, expanda a pasta **Exibições da Fonte de Dados** e clique duas vezes na exibição da fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="5471e-125">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>

3.  <span data-ttu-id="5471e-126">No painel **Tabelas** ou **Diagrama** , clique com o botão direito do mouse na tabela na qual você deseja definir o cálculo nomeado e, em seguida, clique em **Novo Cálculo Nomeado**.</span><span class="sxs-lookup"><span data-stu-id="5471e-126">Right-click the table in which you wish to define the named calculation in either the **Tables** or the **Diagram** pane, and then click **New Named Calculation**.</span></span> <span data-ttu-id="5471e-127">Clique com o botão direito do mouse no nome de tabela, e não em um atributo.</span><span class="sxs-lookup"><span data-stu-id="5471e-127">Be sure to right-click on the table name, and not on an attribute.</span></span> <span data-ttu-id="5471e-128">O menu deverá ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="5471e-128">The menu should look like the following:</span></span>

     <span data-ttu-id="5471e-129">![Instantâneo do workspace de diagrama, menu de atalho](../media/ssas-olapdsv-diagram.gif "Instantâneo do workspace de diagrama, menu de atalho")</span><span class="sxs-lookup"><span data-stu-id="5471e-129">![Screenshot of diagram workspace, right-click menu](../media/ssas-olapdsv-diagram.gif "Screenshot of diagram workspace, right-click menu")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="5471e-130">Para localizar uma tabela ou exibição, use a opção **Localizar Tabela** clicando no menu **Exibição da Fonte de Dados** ou clicando com o botão direito do mouse em uma área livre dos painéis **Tabelas** ou **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="5471e-130">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>

4.  <span data-ttu-id="5471e-131">Na caixa de diálogo **Criar Cálculo Nomeado** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5471e-131">In the **Create Named Calculations** dialog box, do the following:</span></span>

    -   <span data-ttu-id="5471e-132">Na caixa de texto **Nome da coluna** , digite o nome da nova coluna.</span><span class="sxs-lookup"><span data-stu-id="5471e-132">In the **Column name** text box, type the name of the new column.</span></span>

    -   <span data-ttu-id="5471e-133">Na caixa de texto **Descrição** , digite uma descrição para a nova coluna.</span><span class="sxs-lookup"><span data-stu-id="5471e-133">In the **Description** text box type a description for the new column.</span></span>

    -   <span data-ttu-id="5471e-134">Na caixa de texto **Expressão** , digite a expressão que produz o conteúdo da nova coluna no dialeto SQL apropriado para o provedor de dados.</span><span class="sxs-lookup"><span data-stu-id="5471e-134">In the **Expression** text box, type the expression that yields the content of the new column in the SQL dialect appropriate for the data provider.</span></span>

5.  <span data-ttu-id="5471e-135">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5471e-135">Click **OK**.</span></span>

     <span data-ttu-id="5471e-136">A coluna de cálculo nomeado aparece como a última coluna na tabela de exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="5471e-136">The named calculation column appears as the last column in the data source view table.</span></span> <span data-ttu-id="5471e-137">Um símbolo de calculadora indica que a coluna contém um cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="5471e-137">A calculator symbol indicates that the column contains a named calculation.</span></span>

## <a name="delete-a-named-calculation"></a><span data-ttu-id="5471e-138">Excluir um cálculo nomeado</span><span class="sxs-lookup"><span data-stu-id="5471e-138">Delete a Named Calculation</span></span>
 <span data-ttu-id="5471e-139">Quando você tenta excluir um cálculo nomeado, recebe uma lista de objetos definidos no projeto ou no banco de dados que serão invalidados pela exclusão.</span><span class="sxs-lookup"><span data-stu-id="5471e-139">When you attempt to delete a named calculation, you are prompted with a list of the objects defined in the project or database that will be invalidated by the deletion.</span></span> <span data-ttu-id="5471e-140">Revise a lista com cuidado antes de excluir o cálculo.</span><span class="sxs-lookup"><span data-stu-id="5471e-140">Review the list carefully before deleting the calculation.</span></span>

## <a name="see-also"></a><span data-ttu-id="5471e-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5471e-141">See Also</span></span>
 [<span data-ttu-id="5471e-142">Definir consultas nomeadas em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5471e-142">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)


