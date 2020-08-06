---
title: 'Lição 3: Definindo um conjunto de dados para o relatório de tabela (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ee93dfcb-8f52-4d63-b4f6-0d38e00fd350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 33fe48a60db2e7d15d205a4bff6205347f95c61c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571860"
---
# <a name="lesson-3-defining-a-dataset-for-the-table-report-reporting-services"></a><span data-ttu-id="3b2e7-102">Lição 3: Definindo um conjunto de dados para o relatório de tabela (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="3b2e7-102">Lesson 3: Defining a Dataset for the Table Report (Reporting Services)</span></span>
  <span data-ttu-id="3b2e7-103">Depois de definir a fonte de dados, é necessário definir um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-103">After you define the data source, you need to define a dataset.</span></span> <span data-ttu-id="3b2e7-104">No [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], os dados usados em relatórios são contidos em um *conjunto de dados*.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-104">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], data that you use in reports is contained in a *dataset*.</span></span> <span data-ttu-id="3b2e7-105">Um conjunto de dados inclui um ponteiro para uma fonte de dados e uma consulta a ser usada pelo relatório, bem como variáveis e campos calculados.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-105">A dataset includes a pointer to a data source and a query to be used by the report, as well as calculated fields and variables.</span></span>  
  
 <span data-ttu-id="3b2e7-106">Você pode usar o designer de consulta em Designer de Relatórios para criar a consulta.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-106">You can use the query designer in Report Designer to design the query.</span></span> <span data-ttu-id="3b2e7-107">Para este tutorial, você criará uma consulta que recupera informações de pedidos de vendas do [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] banco de dados **2008** .</span><span class="sxs-lookup"><span data-stu-id="3b2e7-107">For this tutorial, you will create a query that retrieves sales order information from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]**2008** database.</span></span>  
  
### <a name="to-define-a-transact-sql-query-for-report-data"></a><span data-ttu-id="3b2e7-108">Para definir uma consulta Transact-SQL a fim de obter dados de relatório</span><span class="sxs-lookup"><span data-stu-id="3b2e7-108">To define a Transact-SQL query for report data</span></span>  
  
1.  <span data-ttu-id="3b2e7-109">No painel **dados do relatório** , clique em **novo**e, em seguida, clique em **DataSet...**. A caixa de diálogo **Propriedades do conjunto** de os é aberta.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-109">In the **Report Data** pane, click **New**, and then click **Dataset...**. The **Dataset Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="3b2e7-110">Na caixa **Nome** , digite **AdventureWorksDataset**.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-110">In the **Name** box, type **AdventureWorksDataset**.</span></span>  
  
3.  <span data-ttu-id="3b2e7-111">Clique em **Usar um conjunto de dados inserido no meu relatório**.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-111">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="3b2e7-112">Verifique se o nome da fonte de dados, AdventureWorks2012, está na caixa de texto **fonte de dados** e se o **tipo de consulta** é **texto**.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-112">Make sure the name of your data source, AdventureWorks2012, is in the **Data source** text box, and that the **Query type** is **Text**.</span></span>  
  
5.  <span data-ttu-id="3b2e7-113">Digite, ou copie e cole, a consulta Transact-SQL a seguir na caixa **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="3b2e7-113">Type, or copy and paste, the following Transact-SQL query into the **Query** box.</span></span>  
  
    ```  
    SELECT   
       soh.OrderDate AS [Date],   
       soh.SalesOrderNumber AS [Order],   
       pps.Name AS Subcat, pp.Name as Product,    
       SUM(sd.OrderQty) AS Qty,  
       SUM(sd.LineTotal) AS LineTotal  
    FROM Sales.SalesPerson sp   
       INNER JOIN Sales.SalesOrderHeader AS soh   
          ON sp.BusinessEntityID = soh.SalesPersonID  
       INNER JOIN Sales.SalesOrderDetail AS sd   
          ON sd.SalesOrderID = soh.SalesOrderID  
       INNER JOIN Production.Product AS pp   
          ON sd.ProductID = pp.ProductID  
       INNER JOIN Production.ProductSubcategory AS pps   
          ON pp.ProductSubcategoryID = pps.ProductSubcategoryID  
       INNER JOIN Production.ProductCategory AS ppc   
          ON ppc.ProductCategoryID = pps.ProductCategoryID  
    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name,   
       soh.SalesPersonID  
    HAVING ppc.Name = 'Clothing'  
    ```  
  
6.  <span data-ttu-id="3b2e7-114">(Opcional) Clique no botão **Designer de Consultas** .</span><span class="sxs-lookup"><span data-stu-id="3b2e7-114">(Optional) Click the **Query Designer** button.</span></span> <span data-ttu-id="3b2e7-115">A consulta é exibida no designer de consulta baseado em texto.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-115">The query is displayed in the text-based query designer.</span></span> <span data-ttu-id="3b2e7-116">Você pode ativar/desativar o designer de consultas gráficas clicando em **Editar Como Texto**.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-116">You can toggle to the graphical query designer by clicking **Edit As Text**.</span></span> <span data-ttu-id="3b2e7-117">Exiba os resultados da consulta clicando no botão executar **(!)** na barra de ferramentas do designer de consulta.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-117">View the results of the query by clicking the run **(!)** button on the query designer toolbar.</span></span>  
  
     <span data-ttu-id="3b2e7-118">É possível ver os dados em seis campos de quatro tabelas diferentes no banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b2e7-118">You see the data from six fields from four different tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="3b2e7-119">A consulta utiliza a funcionalidade Transact-SQL como aliases.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-119">The query makes use of Transact-SQL functionality such as aliases.</span></span> <span data-ttu-id="3b2e7-120">Por exemplo, a tabela SalesOrderHeader é chamada de soh.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-120">For example, the SalesOrderHeader table is called soh.</span></span>  
  
     <span data-ttu-id="3b2e7-121">Clique em **OK** para sair do designer de consultas.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-121">Click **OK** to exit the query designer.</span></span>  
  
7.  <span data-ttu-id="3b2e7-122">Clique em **OK** para sair da caixa de diálogo **Propriedades Conjunto de Dados** .</span><span class="sxs-lookup"><span data-stu-id="3b2e7-122">Click **OK** to exit the **Dataset Properties** dialog box.</span></span>  
  
     <span data-ttu-id="3b2e7-123">O conjunto de dados **AdventureWorksDataset** e os campos são exibidos no painel Dados do Relatório.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-123">Your **AdventureWorksDataset** dataset and fields appear in the Report Data pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="3b2e7-124">Próxima tarefa</span><span class="sxs-lookup"><span data-stu-id="3b2e7-124">Next Task</span></span>  
 <span data-ttu-id="3b2e7-125">Você especificou uma consulta que recupera dados para o relatório com êxito.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-125">You have successfully specified a query that retrieves data for your report.</span></span> <span data-ttu-id="3b2e7-126">A seguir, você criará o layout de relatório.</span><span class="sxs-lookup"><span data-stu-id="3b2e7-126">Next, you will create the report layout.</span></span> <span data-ttu-id="3b2e7-127">Consulte [Lição 4: Adicionando uma tabela ao relatório &#40;Reporting Services&#41;](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3b2e7-127">See [Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b2e7-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b2e7-128">See Also</span></span>  
 <span data-ttu-id="3b2e7-129">[Ferramentas de design de consulta no Report Designer SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3b2e7-129">[Query Design Tools in Report Designer SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span></span>  
 <span data-ttu-id="3b2e7-130">[SQL Server tipo de conexão &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3b2e7-130">[SQL Server Connection Type &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="3b2e7-131">Tutorial: Gravando instruções Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3b2e7-131">Tutorial: Writing Transact-SQL Statements</span></span>](../t-sql/tutorial-writing-transact-sql-statements.md)  
  
  
