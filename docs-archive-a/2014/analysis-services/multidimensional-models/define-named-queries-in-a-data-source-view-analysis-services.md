---
title: Definir consultas nomeadas em uma exibição da fonte de dados (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- named queries [Analysis Services], creating
- modifying named queries
- data source views [Analysis Services], named queries
ms.assetid: f09ba8aa-950e-4c0d-961e-970de13200be
author: minewiskan
ms.author: owend
ms.openlocfilehash: dfe2dbc6081e0c33f681ba894b16057c8890e0b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571660"
---
# <a name="define-named-queries-in-a-data-source-view-analysis-services"></a><span data-ttu-id="fb019-102">Definir consultas nomeadas em uma exibição da fonte de dados (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="fb019-102">Define Named Queries in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="fb019-103">Uma consulta nomeada é uma expressão SQL representada como uma tabela.</span><span class="sxs-lookup"><span data-stu-id="fb019-103">A named query is a SQL expression represented as a table.</span></span> <span data-ttu-id="fb019-104">Em uma consulta nomeada, você pode especificar uma expressão SQL para selecionar linhas e colunas retornadas de uma ou mais tabelas em uma ou mais fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="fb019-104">In a named query, you can specify an SQL expression to select rows and columns returned from one or more tables in one or more data sources.</span></span> <span data-ttu-id="fb019-105">Uma consulta nomeada é como qualquer outra tabela em uma DSV (exibição da fonte de dados) com linhas e relações, exceto que a consulta nomeada baseia-se em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="fb019-105">A named query is like any other table in a data source view (DSV) with rows and relationships, except that the named query is based on an expression.</span></span>  
  
 <span data-ttu-id="fb019-106">Uma consulta nomeada permite que você estenda o esquema relacional das tabelas existentes em uma DSV sem modificar as tabelas ou exibições da fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="fb019-106">A named query lets you extend the relational schema of existing tables in DSV without modifying the underlying data source.</span></span> <span data-ttu-id="fb019-107">Por exemplo, uma série de consultas nomeadas pode ser usada para dividir uma tabela de dimensões complexa em tabelas de dimensões menores e mais simples para uso nas dimensões do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fb019-107">For example, a series of named queries can be used to split up a complex dimension table into smaller, simpler dimension tables for use in database dimensions.</span></span> <span data-ttu-id="fb019-108">A consulta nomeada também pode ser usada para unir várias tabelas do banco de dados de uma ou mais fontes de dados em uma única tabela de exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fb019-108">A named query can also be used to join multiple database tables from one or more data sources into a single data source view table.</span></span>  
  
## <a name="creating-a-named-query"></a><span data-ttu-id="fb019-109">Criando uma consulta nomeada</span><span class="sxs-lookup"><span data-stu-id="fb019-109">Creating a Named Query</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb019-110">Não é possível adicionar um cálculo nomeado a uma consulta nomeada nem usar como base de uma consulta nomeada uma tabela que contém um cálculo nomeado.</span><span class="sxs-lookup"><span data-stu-id="fb019-110">You cannot add a named calculation to a named query, nor can you base a named query on a table that contains a named calculation.</span></span>  
  
 <span data-ttu-id="fb019-111">Ao criar uma consulta nomeada, você especifica uma expressão SQL que retorna colunas e dados para a tabela e, opcionalmente, uma descrição da consulta nomeada.</span><span class="sxs-lookup"><span data-stu-id="fb019-111">When you create a named query, you specify a name, the SQL query returning the columns and data for the table, and optionally, a description of the named query.</span></span> <span data-ttu-id="fb019-112">A expressão SQL pode fazer referência a outras tabelas da exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fb019-112">The SQL expression can refer to other tables in the data source view.</span></span> <span data-ttu-id="fb019-113">Definida a consulta nomeada, a consulta SQL em uma consulta nomeada é enviada ao provedor da fonte de dados e validada por inteiro.</span><span class="sxs-lookup"><span data-stu-id="fb019-113">After the named query is defined, the SQL query in a named query is sent to the provider for the data source and validated as a whole.</span></span> <span data-ttu-id="fb019-114">Se o provedor não encontrar erros na consulta SQL, a coluna será adicionada à tabela.</span><span class="sxs-lookup"><span data-stu-id="fb019-114">If the provider does not find any errors in the SQL query, the column is added to the table.</span></span>  
  
 <span data-ttu-id="fb019-115">Tabelas e colunas às quais a consulta SQL faz referência não devem ser qualificadas ou devem ser qualificadas somente pelo nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="fb019-115">Tables and columns referenced in the SQL query should not be qualified or should be qualified by the table name only.</span></span> <span data-ttu-id="fb019-116">Por exemplo, para fazer referência à coluna SaleAmount em uma tabela, o valor `SaleAmount` ou `Sales.SaleAmount` é válido, mas `dbo.Sales.SaleAmount` produzirá um erro.</span><span class="sxs-lookup"><span data-stu-id="fb019-116">For example, to refer to the SaleAmount column in a table, `SaleAmount` or `Sales.SaleAmount` is valid, but `dbo.Sales.SaleAmount` generates an error.</span></span>  
  
 <span data-ttu-id="fb019-117">**Observação** Ao definir uma consulta nomeada que consulta uma fonte de dados do [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] ou do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0, a consulta nomeada que contiver uma subconsulta correlacionada e uma cláusula GROUP BY falhará.</span><span class="sxs-lookup"><span data-stu-id="fb019-117">**Note** When defining a named query that queries a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 data source, a named query that contains a correlated subquery and a GROUP BY clause will fail.</span></span> <span data-ttu-id="fb019-118">Para obter mais informações, consulte [Erro interno com a instrução SELECT contendo a subconsulta correlacionada e GROUP BY](https://support.microsoft.com/kb/274729) na Base de Dados de Conhecimento [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb019-118">For more information, see [Internal Error with SELECT Statement Containing Correlated Subquery and GROUP BY](https://support.microsoft.com/kb/274729) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base.</span></span>  
  
## <a name="add-or-edit-a-named-query"></a><span data-ttu-id="fb019-119">Adicionar ou editar uma consulta nomeada</span><span class="sxs-lookup"><span data-stu-id="fb019-119">Add or Edit a Named Query</span></span>  
  
1.  <span data-ttu-id="fb019-120">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto ou conecte-se ao banco de dados que contém a exibição da fonte de dados à qual você deseja adicionar uma consulta nomeada.</span><span class="sxs-lookup"><span data-stu-id="fb019-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to add a named query.</span></span>  
  
2.  <span data-ttu-id="fb019-121">No Gerenciador de Soluções, expanda a pasta **Exibições da Fonte de Dados** e clique duas vezes na exibição da fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="fb019-121">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="fb019-122">Clique com o botão direito do mouse em uma área livre do painel **Tabelas** ou **Diagrama** e clique em **Nova Consulta Nomeada**.</span><span class="sxs-lookup"><span data-stu-id="fb019-122">In the **Tables** or **Diagram** pane, right-click an open area and then click **New Named Query**.</span></span>  
  
4.  <span data-ttu-id="fb019-123">Na caixa de diálogo **Criar Consulta Nomeada** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb019-123">In the **Create Named Query** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="fb019-124">Na caixa de texto **Nome** , digite o nome da consulta.</span><span class="sxs-lookup"><span data-stu-id="fb019-124">In the **Name** text box, type a query name.</span></span>  
  
    2.  <span data-ttu-id="fb019-125">Opcionalmente, na caixa de texto **Descrição** , digite uma descrição para a consulta.</span><span class="sxs-lookup"><span data-stu-id="fb019-125">Optionally, in the **Description** text box, type a description for the query.</span></span>  
  
    3.  <span data-ttu-id="fb019-126">Na caixa de listagem **Fonte de Dados** , selecione a fonte de dados na qual a consulta nomeada será executada.</span><span class="sxs-lookup"><span data-stu-id="fb019-126">In the **Data Source** list box, select the data source against which the named query will execute.</span></span>  
  
    4.  <span data-ttu-id="fb019-127">Digite a consulta no painel inferior ou use as ferramentas gráficas de criação de consulta para criar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="fb019-127">Type the query in the bottom pane, or use the graphical query building tools to create a query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb019-128">A interface de usuário para criação de consultas varia de acordo com a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fb019-128">The query-building user interface (UI) depends on the data source.</span></span> <span data-ttu-id="fb019-129">Em vez de obter uma interface de usuário gráfica, você poderá obter uma interface genérica baseada em texto.</span><span class="sxs-lookup"><span data-stu-id="fb019-129">Instead of getting a graphical UI, you can get a generic UI, which is text-based.</span></span> <span data-ttu-id="fb019-130">Você pode realizar as mesmas coisas com essas interfaces de usuário diferentes, mas deve fazê-las de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="fb019-130">You can accomplish the same things with these different UIs, but you must do so in different ways.</span></span> <span data-ttu-id="fb019-131">Para obter mais informações, consulte [Caixa de diálogo Criar ou Editar Consulta Nomeada &#40;Analysis Services – Dados Multidimensionais&#41;](../create-or-edit-named-query-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="fb019-131">For more information, see [Create or Edit Named Query Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../create-or-edit-named-query-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
5.  <span data-ttu-id="fb019-132">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb019-132">Click **OK**.</span></span> <span data-ttu-id="fb019-133">Um ícone mostrando duas tabelas sobrepostas aparece no título da tabela para indicar que a tabela foi substituída por uma consulta nomeada.</span><span class="sxs-lookup"><span data-stu-id="fb019-133">An icon showing two overlapping tables appears in the table header to indicate that the table has been replaced by a named query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb019-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb019-134">See Also</span></span>  
 <span data-ttu-id="fb019-135">[Exibições da fonte de dados em modelos multidimensionais](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="fb019-135">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="fb019-136">Definir cálculos nomeados em uma exibição da fonte de dados &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fb019-136">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
