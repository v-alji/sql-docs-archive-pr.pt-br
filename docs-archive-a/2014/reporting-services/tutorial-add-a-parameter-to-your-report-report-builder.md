---
title: 'Tutorial: Adicionar um parâmetro ao relatório (construtor de relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eab34ec4-b3ad-4a76-95cc-07b2f75ee6d7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dff41066a2d505ab53b17a10fb3da9b6cb17130f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683358"
---
# <a name="tutorial-add-a-parameter-to-your-report-report-builder"></a><span data-ttu-id="c15c5-102">Tutorial: Adicionar um parâmetro ao relatório (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="c15c5-102">Tutorial: Add a Parameter to Your Report (Report Builder)</span></span>
  <span data-ttu-id="c15c5-103">Adicione um parâmetro ao relatório para permitir que os usuários filtrem dados do relatório na fonte de dados ou no relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-103">Add a parameter to your report to let users filter report data from the data source or in the report.</span></span> <span data-ttu-id="c15c5-104">Os parâmetros de relatório são criados automaticamente para cada parâmetro de consulta incluído em uma consulta de conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="c15c5-104">Report parameters are created automatically for each query parameter that you include in a dataset query.</span></span> <span data-ttu-id="c15c5-105">O tipo de dados do parâmetro determina como ele aparece na barra de ferramentas de exibição de relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-105">The parameter data type determines how it appears on the report view toolbar.</span></span>  
  
 <span data-ttu-id="c15c5-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span><span class="sxs-lookup"><span data-stu-id="c15c5-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="c15c5-107">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="c15c5-107">What You Will Learn</span></span>  
 <span data-ttu-id="c15c5-108">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="c15c5-108">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="c15c5-109">Criar um relatório de matriz e um conjunto de dados no Assistente de Tabela ou Matriz</span><span class="sxs-lookup"><span data-stu-id="c15c5-109">Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="c15c5-110">Organizar dados, escolher layout e estilo no Assistente de Tabela ou Matriz</span><span class="sxs-lookup"><span data-stu-id="c15c5-110">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="c15c5-111">Adicionar um parâmetro de consulta para criar um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-111">Add a Query Parameter to Create a Report Parameter</span></span>](#Query)  
  
4.  [<span data-ttu-id="c15c5-112">Alterar o tipo de dados padrão e outras propriedades de um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-112">Change Default Data Type and Other Properties for a Report Parameter</span></span>](#ChangeDefaultProperties)  
  
    1.  [<span data-ttu-id="c15c5-113">Adicionar um conjunto de dados para fornecer valores disponíveis e nomes para exibição</span><span class="sxs-lookup"><span data-stu-id="c15c5-113">Add a Dataset to Provide Available Values and Display Names</span></span>](#AddDataset)  
  
    2.  [<span data-ttu-id="c15c5-114">Especificar os valores disponíveis para criar uma lista suspensa de valores</span><span class="sxs-lookup"><span data-stu-id="c15c5-114">Specify Available Values to Create a Drop-List of Values</span></span>](#AvailableValues)  
  
    3.  [<span data-ttu-id="c15c5-115">Especificar os valores padrão para que o relatório seja executado automaticamente</span><span class="sxs-lookup"><span data-stu-id="c15c5-115">Specify Default Values so the Report Runs Automatically</span></span>](#DefaultValues)  
  
    4.  [<span data-ttu-id="c15c5-116">Pesquisar um valor em um conjunto de dados com pares de nome/valor</span><span class="sxs-lookup"><span data-stu-id="c15c5-116">Look up a Value from a Dataset that has Name/Value Pairs</span></span>](#NameValue)  
  
5.  [<span data-ttu-id="c15c5-117">Exibir o valor selecionado de parâmetro no relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-117">Display the Selected Parameter Value in the Report</span></span>](#Expression)  
  
6.  [<span data-ttu-id="c15c5-118">Usar o parâmetro de relatório em um filtro</span><span class="sxs-lookup"><span data-stu-id="c15c5-118">Use the Report Parameter in a Filter</span></span>](#Filter)  
  
7.  [<span data-ttu-id="c15c5-119">Alterar o parâmetro de relatório para aceitar vários valores</span><span class="sxs-lookup"><span data-stu-id="c15c5-119">Change the Report Parameter to Accept Multiple Values</span></span>](#Multivalued)  
  
8.  [<span data-ttu-id="c15c5-120">Adicionar um parâmetro booliano para visibilidade condicional</span><span class="sxs-lookup"><span data-stu-id="c15c5-120">Add a Boolean Parameter for Conditional Visibility</span></span>](#Boolean)  
  
9. [<span data-ttu-id="c15c5-121">Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-121">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="c15c5-122">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-122">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="c15c5-123">Neste tutorial, as etapas do assistente são consolidadas em um procedimento.</span><span class="sxs-lookup"><span data-stu-id="c15c5-123">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="c15c5-124">Para obter instruções passo a passo sobre como procurar um servidor de relatório, escolher uma fonte de dados e criar um conjunto de dados, consulte o primeiro tutorial desta série: [Tutorial: Criação de um relatório de tabela básico &#40;Construtor de Relatórios&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c15c5-124">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="c15c5-125">Tempo estimado para concluir este tutorial: 25 minutos.</span><span class="sxs-lookup"><span data-stu-id="c15c5-125">Estimated time to complete this tutorial: 25 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c15c5-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c15c5-126">Requirements</span></span>  
 <span data-ttu-id="c15c5-127">Para obter informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="c15c5-127">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="c15c5-128">1. criar um relatório de matriz e um conjunto de relatórios do assistente de tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="c15c5-128">1. Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="c15c5-129">Criar um relatório de matriz, uma fonte de dados e um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="c15c5-129">Create a matrix report, a data source, and a dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c15c5-130">Neste tutorial, a consulta contém os valores de dados para que não precise de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="c15c5-130">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="c15c5-131">Isso torna a consulta bastante longa.</span><span class="sxs-lookup"><span data-stu-id="c15c5-131">This makes the query quite long.</span></span> <span data-ttu-id="c15c5-132">Em um ambiente empresarial, uma consulta não conteria os dados.</span><span class="sxs-lookup"><span data-stu-id="c15c5-132">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="c15c5-133">Isso é apenas para fins de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="c15c5-133">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix-report"></a><span data-ttu-id="c15c5-134">Para criar um novo relatório de matriz</span><span class="sxs-lookup"><span data-stu-id="c15c5-134">To create a new matrix report</span></span>  
  
1.  <span data-ttu-id="c15c5-135">Clique em **Iniciar**, aponte para **programas**, aponte para [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Construtor de relatórios**e, em seguida, clique em **Construtor de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-135">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="c15c5-136">A caixa de diálogo **introdução** é exibida.</span><span class="sxs-lookup"><span data-stu-id="c15c5-136">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c15c5-137">Se a caixa de diálogo **introdução** não for exibida, no botão **Construtor de relatórios** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-137">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="c15c5-138">No painel esquerdo, verifique se **Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="c15c5-138">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="c15c5-139">No painel direito, clique em **Assistente de Tabela ou Matriz**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-139">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="c15c5-140">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-140">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="c15c5-141">Na página **Escolher um conjunto de dados** , clique em **Criar um conjunto de dados**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-141">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
6.  <span data-ttu-id="c15c5-142">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-142">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="c15c5-143">Na página **Escolher uma conexão com uma fonte de dados** , selecione uma fonte de dados do tipo **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-143">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="c15c5-144">Selecione uma fonte de dados na lista ou navegue até o servidor de relatório para selecionar uma.</span><span class="sxs-lookup"><span data-stu-id="c15c5-144">Select a data source from the list or browse to the report server to select one.</span></span>  
  
8.  <span data-ttu-id="c15c5-145">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-145">Click **Next**.</span></span>  
  
9. <span data-ttu-id="c15c5-146">Na página **Crie uma consulta** , clique em **Editar como Texto**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-146">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
10. <span data-ttu-id="c15c5-147">Cole a seguinte consulta no painel de consulta:</span><span class="sxs-lookup"><span data-stu-id="c15c5-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    ;WITH CTE (StoreID, Subcategory, Quantity)   
    AS (  
    SELECT 200 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 2002 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Camcorders' AS Subcategory, 1954 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Accessories' AS Subcategory, 1895 AS Quantity  
    UNION SELECT  199 AS StoreID, 'Digital Cameras' AS Subcategory, 1849 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1579 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Camcorders' AS Subcategory, 1561 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital Cameras' AS Subcategory, 1553 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Accessories' AS Subcategory, 1534 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Accessories' AS Subcategory, 1755 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Camcorders' AS Subcategory, 1631 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1772 AS Quantity)  
    SELECT StoreID, Subcategory, Quantity  
    FROM CTE  
    ```  
  
     <span data-ttu-id="c15c5-148">Esta consulta combina os resultados de várias instruções SELECT [!INCLUDE[tsql](../includes/tsql-md.md)] dentro de uma expressão de tabela comum para especificar valores baseados em dados simplificados do banco de dados de exemplo Contoso.</span><span class="sxs-lookup"><span data-stu-id="c15c5-148">This query combines the results of several [!INCLUDE[tsql](../includes/tsql-md.md)] SELECT statements inside a common table expression to specify values that are based on simplified data from the Contoso sample database.</span></span> <span data-ttu-id="c15c5-149">Os dados de vendas em Contoso representam os dados de vendas internacionais de bens de consumo.</span><span class="sxs-lookup"><span data-stu-id="c15c5-149">The Contoso sales data represents international sales data for consumer goods.</span></span> <span data-ttu-id="c15c5-150">Este tutorial usa dados de vendas de câmeras.</span><span class="sxs-lookup"><span data-stu-id="c15c5-150">This tutorial uses sales data for cameras.</span></span> <span data-ttu-id="c15c5-151">As subcategorias representam câmeras digitais, câmeras digitais SLR (reflex de lente única), filmadoras e acessórios.</span><span class="sxs-lookup"><span data-stu-id="c15c5-151">The subcategories represent digital cameras, digital single lens reflex (SLR) cameras, camcorders, and accessories.</span></span>  
  
     <span data-ttu-id="c15c5-152">A consulta especifica nomes de coluna que incluem um identificador de repositório, uma subcategoria de item de vendas e a quantidade solicitada para ordens de venda de três repositórios.</span><span class="sxs-lookup"><span data-stu-id="c15c5-152">The query specifies column names that include a store identifier, a sales item subcategory, and the quantity ordered for sales orders from three stores.</span></span> <span data-ttu-id="c15c5-153">Nesta consulta, o nome do repositório não faz parte do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="c15c5-153">In this query, the store name is not part of the result set.</span></span> <span data-ttu-id="c15c5-154">Posteriormente neste tutorial, você irá pesquisar o nome do repositório que corresponde ao identificador de repositório de um conjunto de dados separado.</span><span class="sxs-lookup"><span data-stu-id="c15c5-154">Later in this tutorial, you will look up the name of the store that corresponds to the store identifier from a separate dataset.</span></span>  
  
     <span data-ttu-id="c15c5-155">Esta consulta não contém parâmetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="c15c5-155">This query does not contain query parameters.</span></span> <span data-ttu-id="c15c5-156">Você adicionará parâmetros de consulta posteriormente neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="c15c5-156">You will add query parameters later in this tutorial.</span></span>  
  
11. <span data-ttu-id="c15c5-157">Na barra de ferramentas do designer de consultas, clique em **executar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="c15c5-157">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="c15c5-158">O conjunto de resultados exibe 11 linhas de dados que mostram a quantidade de itens vendidos para cada subcategoria de quatro repositórios e inclui as seguintes colunas: StoreID, Subcategory, Quantity.</span><span class="sxs-lookup"><span data-stu-id="c15c5-158">The result set displays 11 rows of data that show the quantity of items sold for each subcategory for four stores, and includes the following columns: StoreID, Subcategory, Quantity.</span></span>  
  
12. <span data-ttu-id="c15c5-159">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-159">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="c15c5-160">2. organizar dados, escolher layout e estilo no assistente de tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="c15c5-160">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="c15c5-161">Use o assistente para fornecer um design inicial no qual exibir dados.</span><span class="sxs-lookup"><span data-stu-id="c15c5-161">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="c15c5-162">O painel de visualização no assistente ajuda a visualizar o resultado do agrupamento de dados antes de concluir o design da tabela ou da matriz.</span><span class="sxs-lookup"><span data-stu-id="c15c5-162">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="c15c5-163">Para organizar dados em grupos</span><span class="sxs-lookup"><span data-stu-id="c15c5-163">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="c15c5-164">Na página **Organizar campos** , arraste Subcategoria até **Grupos de linhas**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-164">On the **Arrange fields** page, drag Subcategory to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="c15c5-165">Arraste StoreID até **Grupos de colunas**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-165">Drag StoreID to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="c15c5-166">Arraste Quantity até **Valores**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-166">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="c15c5-167">Você organizou os valores das quantidades vendidas em linhas agrupadas por subcategoria.</span><span class="sxs-lookup"><span data-stu-id="c15c5-167">You have organized the quantity sold values in rows grouped by subcategory.</span></span> <span data-ttu-id="c15c5-168">Haverá uma coluna para cada repositório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-168">There will be one column for each store.</span></span>  
  
4.  <span data-ttu-id="c15c5-169">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-169">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="c15c5-170">Na página **escolher um layout** , em opções, verifique se a **opção** **Mostrar Subtotais e totais gerais** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="c15c5-170">On the **Choose a Layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="c15c5-171">Quando você executar o relatório, a última coluna mostrará a quantidade total de cada subcategoria para todos os repositórios, e a última linha mostrará a quantidade total para todas as subcategorias de cada repositório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-171">When you run the report, the last column will show the total quantity of each subcategory for all stores, and the last row will show the total quantity for all subcategories for each store.</span></span>  
  
6.  <span data-ttu-id="c15c5-172">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-172">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="c15c5-173">Na página **escolher um estilo** , no painel estilos, selecione um estilo.</span><span class="sxs-lookup"><span data-stu-id="c15c5-173">On the **Choose a Style** page, in the Styles pane, select a style.</span></span>  
  
8.  <span data-ttu-id="c15c5-174">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-174">Click **Finish**.</span></span>  
  
     <span data-ttu-id="c15c5-175">A matriz é adicionada à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="c15c5-175">The matrix is added to the design surface.</span></span> <span data-ttu-id="c15c5-176">A matriz exibe três colunas e três linhas.</span><span class="sxs-lookup"><span data-stu-id="c15c5-176">The matrix displays three columns and three rows.</span></span> <span data-ttu-id="c15c5-177">As células na primeira linha contêm Subcategory, [StoreID] e Total.</span><span class="sxs-lookup"><span data-stu-id="c15c5-177">The contents of the cells in the first row are Subcategory, [StoreID], and Total.</span></span> <span data-ttu-id="c15c5-178">As células na segunda linha contêm expressões que representam a subcategoria, a quantidade de itens vendidos para cada repositório e a quantidade total de cada subcategoria para todos os repositórios.</span><span class="sxs-lookup"><span data-stu-id="c15c5-178">The contents of the cells in the second row contain expressions that represent the subcategory, the quantity of items sold for each store, and the total quantity for each subcategory for all stores.</span></span> <span data-ttu-id="c15c5-179">As células na linha final exibem o total geral de cada repositório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-179">The cells in the final row display the grand total for each store.</span></span>  
  
9. <span data-ttu-id="c15c5-180">Clique na matriz, passe o mouse sobre a borda da primeira coluna e arraste a alça para aumentar a largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="c15c5-180">Click in the matrix, hover over the edge of the first column, grab the handle, and expand the column width.</span></span>  
  
10. <span data-ttu-id="c15c5-181">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-181">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="c15c5-182">O relatório será executado no servidor de relatório e exibirá o título e a hora em que o processamento de relatório ocorreu.</span><span class="sxs-lookup"><span data-stu-id="c15c5-182">The report runs on the report server and displays the title and the time the report processing occurred.</span></span>  
  
 <span data-ttu-id="c15c5-183">Neste cenário, os títulos de coluna exibem o identificador, mas não o nome do repositório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-183">In this scenario, the column headings display the store identifier but not the store name.</span></span> <span data-ttu-id="c15c5-184">Posteriormente, você irá adicionar uma expressão para pesquisar o nome do repositório em um conjunto de dados contendo pares de identificador/nome do repositório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-184">Later, you will add an expression to look up the store name in a dataset that contains store identifier/store name pairs.</span></span>  
  
##  <a name="3-add-a-query-parameter-to-create-a-report-parameter"></a><a name="Query"></a><span data-ttu-id="c15c5-185">3. adicionar um parâmetro de consulta para criar um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-185">3. Add a Query Parameter to Create a Report Parameter</span></span>  
 <span data-ttu-id="c15c5-186">Quando você adicionar um parâmetro de consulta a uma consulta, o Construtor de Relatórios criará automaticamente um parâmetro de relatório de valor único com propriedades padrão para nome, aviso e tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="c15c5-186">When you add a query parameter to a query, Report Builder automatically creates a single-valued report parameter with default properties for name, prompt, and data type.</span></span>  
  
#### <a name="to-add-a-query-parameter"></a><span data-ttu-id="c15c5-187">Para adicionar um parâmetro de consulta</span><span class="sxs-lookup"><span data-stu-id="c15c5-187">To add a query parameter</span></span>  
  
1.  <span data-ttu-id="c15c5-188">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="c15c5-188">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="c15c5-189">No painel Dados do Relatório, expanda a pasta **Conjuntos de Dados** , clique com o botão direito do mouse em **DataSet1**e clique em **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-189">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
3.  <span data-ttu-id="c15c5-190">Adicione a seguinte [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` cláusula como a última linha da consulta:</span><span class="sxs-lookup"><span data-stu-id="c15c5-190">Add the following [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause as the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID = (@StoreID)  
    ```  
  
     <span data-ttu-id="c15c5-191">A `WHERE` cláusula limita os dados recuperados para o identificador de loja especificado pelo parâmetro de consulta *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="c15c5-191">The `WHERE` clause limits the retrieved data to the store identifier that is specified by the query parameter *@StoreID*.</span></span>  
  
4.  <span data-ttu-id="c15c5-192">Na barra de ferramentas do designer de consultas, clique em **executar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="c15c5-192">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="c15c5-193">A caixa de diálogo **Definir Parâmetros de Consulta** é aberta e solicita um valor para o parâmetro de consulta *@StoreID*.</span><span class="sxs-lookup"><span data-stu-id="c15c5-193">The **Define Query Parameters** dialog box opens and prompts for a value for the query parameter *@StoreID*.</span></span>  
  
5.  <span data-ttu-id="c15c5-194">Em **Valor do Parâmetro**, digite **200**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-194">In **Parameter Value**, type **200**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="c15c5-195">O conjunto de resultados exibe as quantidades vendidas de Acessórios, Filmadoras e Câmeras Digitais SLR do identificador de loja **200**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-195">The result set displays the quantities sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="c15c5-196">No painel Dados do Relatório, expanda a pasta **Parâmetros** .</span><span class="sxs-lookup"><span data-stu-id="c15c5-196">In the Report Data pane, expand the **Parameters** folder.</span></span>  
  
 <span data-ttu-id="c15c5-197">Observe que agora há um parâmetro de relatório chamado *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="c15c5-197">Notice that there is now a report parameter named *@StoreID*.</span></span> <span data-ttu-id="c15c5-198">Por padrão, o parâmetro tem o tipo de dados **Text**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-198">By default, the parameter has data type **Text**.</span></span> <span data-ttu-id="c15c5-199">Como o identificador de repositório é um inteiro, você precisará alterar o tipo de dados para Inteiro no próximo procedimento.</span><span class="sxs-lookup"><span data-stu-id="c15c5-199">Because the store identifier is an integer, you will change the data type to Integer in the next procedure.</span></span>  
  
##  <a name="4-change-default-data-type-and-other-properties-for-a-report-parameter"></a><a name="ChangeDefaultProperties"></a><span data-ttu-id="c15c5-200">4. alterar o tipo de dados padrão e outras propriedades para um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-200">4. Change Default Data Type and Other Properties for a Report Parameter</span></span>  
 <span data-ttu-id="c15c5-201">Depois de criar um parâmetro, você pode ajustar os valores padrão de propriedades.</span><span class="sxs-lookup"><span data-stu-id="c15c5-201">After a report parameter is created, you can adjust the default values for properties.</span></span>  
  
#### <a name="to-change-the-default-data-type-for-a-report-parameter"></a><span data-ttu-id="c15c5-202">Para alterar o tipo de dados padrão de um parâmetro de relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-202">To change the default data type for a report parameter</span></span>  
  
1.  <span data-ttu-id="c15c5-203">No painel dados do relatório, no nó **parâmetros** , clique com o botão direito do mouse em *@StoreID* e clique em **Propriedades do parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-203">In the Report Data pane under the **Parameters** node, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="c15c5-204">Em prompt, digite **identificador de repositório?**</span><span class="sxs-lookup"><span data-stu-id="c15c5-204">In Prompt, type **Store identifier?**</span></span> <span data-ttu-id="c15c5-205">Este texto aparece na barra de ferramentas do visualizador de relatórios quando você executa o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-205">This text appears on the report viewer toolbar when you run the report.</span></span>  
  
3.  <span data-ttu-id="c15c5-206">Em **Tipo de dados**, na lista suspensa, selecione **Inteiro**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-206">In **Data type**, from the drop-down list, select **Integer**.</span></span>  
  
4.  <span data-ttu-id="c15c5-207">Aceite os valores padrão restantes na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c15c5-207">Accept the remaining default values in the dialog box.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c15c5-208">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-208">Preview the report.</span></span> <span data-ttu-id="c15c5-209">O Visualizador de relatórios exibe o prompt para *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="c15c5-209">The report viewer displays the prompt for *@StoreID*.</span></span>  
  
7.  <span data-ttu-id="c15c5-210">Na barra de ferramentas do visualizador de relatórios, ao lado de ID da Loja, digite **200**e clique em **Exibir Relatório**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-210">On the report viewer toolbar, next to Store ID, type **200**, and then click **View Report**.</span></span>  
  
##  <a name="4a-add-a-dataset-to-provide-available-values-and-display-names"></a><a name="AddDataset"></a><span data-ttu-id="c15c5-211">4a.</span><span class="sxs-lookup"><span data-stu-id="c15c5-211">4a.</span></span> <span data-ttu-id="c15c5-212">Adicionar um conjunto de dados para fornecer valores disponíveis e nomes para exibição</span><span class="sxs-lookup"><span data-stu-id="c15c5-212">Add a Dataset to Provide Available Values and Display Names</span></span>  
 <span data-ttu-id="c15c5-213">Para garantir que um usuário possa digitar somente valores válidos para um parâmetro, você pode criar uma lista suspensa de valores a serem escolhidos.</span><span class="sxs-lookup"><span data-stu-id="c15c5-213">To ensure a user can type only valid values for a parameter, you can create a drop-down list of values to choose from.</span></span> <span data-ttu-id="c15c5-214">Os valores podem vir de um conjunto de dados ou de uma lista especificada por você.</span><span class="sxs-lookup"><span data-stu-id="c15c5-214">The values can come from a dataset or from a list that you specify.</span></span> <span data-ttu-id="c15c5-215">Devem ser fornecidos valores disponíveis de um conjunto de dados que contenha uma consulta sem referência ao parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c15c5-215">Available values must be supplied from a dataset that has a query that does not contain a reference to the parameter.</span></span>  
  
#### <a name="to-create-a-dataset-for-valid-values-for-a-parameter"></a><span data-ttu-id="c15c5-216">Para criar um conjunto de dados com valores válidos para um parâmetro</span><span class="sxs-lookup"><span data-stu-id="c15c5-216">To create a dataset for valid values for a parameter</span></span>  
  
1.  <span data-ttu-id="c15c5-217">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="c15c5-217">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="c15c5-218">No painel Dados do Relatório, clique com o botão direito do mouse na pasta **Conjuntos de Dados** e clique em **Adicionar Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-218">In the Report Data pane, right-click the **Datasets** folder, and then click **Add Dataset**.</span></span>  
  
3.  <span data-ttu-id="c15c5-219">Em **Nome**, digite **Lojas**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-219">In **Name**, type **Stores**.</span></span>  
  
4.  <span data-ttu-id="c15c5-220">Selecione a opção **usar um conjunto de entrada inserido no meu relatório** .</span><span class="sxs-lookup"><span data-stu-id="c15c5-220">Select the **Use a dataset embedded in my report** option.</span></span>  
  
5.  <span data-ttu-id="c15c5-221">Em **fonte de dados**, na lista suspensa, escolha a fonte de dados que você criou no primeiro procedimento.</span><span class="sxs-lookup"><span data-stu-id="c15c5-221">In **Data source**, from the drop-down list, choose the data source you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="c15c5-222">Em **Tipo de consulta**, verifique se **Texto** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="c15c5-222">In **Query type**, verify that **Text** is selected.</span></span>  
  
7.  <span data-ttu-id="c15c5-223">Em **Consulta**, cole o seguinte texto:</span><span class="sxs-lookup"><span data-stu-id="c15c5-223">In **Query**, paste the following text:</span></span>  
  
    ```  
    SELECT 200 AS StoreID, 'Contoso Catalog Store' as StoreName  
    UNION SELECT 199 AS StoreID, 'Contoso North America Online Store' as StoreName  
    UNION SELECT 307 AS StoreID, 'Contoso Asia Online Store' as StoreName  
    UNION SELECT 306 AS StoreID, 'Contoso Europe Online Store' as StoreName  
    ```  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="c15c5-224">O painel Dados do Relatório exibe os campos StoreID e StoreName no nó de conjunto de dados **Lojas** .</span><span class="sxs-lookup"><span data-stu-id="c15c5-224">The Report Data pane displays the fields StoreID and StoreName under the **Stores** dataset node.</span></span>  
  
##  <a name="4b-specify-available-values-to-create-a-drop-down-list-of-values"></a><a name="AvailableValues"></a><span data-ttu-id="c15c5-225">4B.</span><span class="sxs-lookup"><span data-stu-id="c15c5-225">4b.</span></span> <span data-ttu-id="c15c5-226">Especificar os valores disponíveis para criar uma lista suspensa de valores</span><span class="sxs-lookup"><span data-stu-id="c15c5-226">Specify Available Values to Create a Drop-down List of Values</span></span>  
 <span data-ttu-id="c15c5-227">Depois de criar um conjunto de dados para fornecer valores disponíveis, altere as propriedades do relatório para especificar o conjunto de dados e o campo a serem usados para preencher a lista suspensa de valores válidos na barra de ferramentas do visualizador de relatórios.</span><span class="sxs-lookup"><span data-stu-id="c15c5-227">After you create a dataset to provide available values, you must change the report properties to specify which dataset and which field to use to populate the drop-down list of valid values on the reportviewer toolbar.</span></span>  
  
#### <a name="to-provide-available-values-for-a-parameter-from-a-dataset"></a><span data-ttu-id="c15c5-228">Para fornecer valores disponíveis para um parâmetro a partir de um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="c15c5-228">To provide available values for a parameter from a dataset</span></span>  
  
1.  <span data-ttu-id="c15c5-229">No painel dados do relatório, clique com o botão direito do mouse no parâmetro *@StoreID* e clique em **Propriedades do parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-229">In the Report Data pane, right-click the parameter *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="c15c5-230">Clique em **Valores Disponíveis**e em **Obter valores de uma consulta**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-230">Click **Available Values**, and then click **Get values from a query**.</span></span>  
  
3.  <span data-ttu-id="c15c5-231">Em **Conjunto de Dados**, na lista suspensa, clique em **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-231">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
4.  <span data-ttu-id="c15c5-232">Em **Campo de valor**, na lista suspensa, clique em StoreID.</span><span class="sxs-lookup"><span data-stu-id="c15c5-232">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
5.  <span data-ttu-id="c15c5-233">Em **Campo de rótulo**, na lista suspensa, clique em StoreName.</span><span class="sxs-lookup"><span data-stu-id="c15c5-233">In **Label field**, from the drop-down list, click StoreName.</span></span> <span data-ttu-id="c15c5-234">O campo de rótulo especifica o nome para exibição do valor.</span><span class="sxs-lookup"><span data-stu-id="c15c5-234">The label field specifies the display name for the value.</span></span>  
  
6.  <span data-ttu-id="c15c5-235">Clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-235">Click **General**.</span></span>  
  
7.  <span data-ttu-id="c15c5-236">Em prompt, digite **nome do repositório?**</span><span class="sxs-lookup"><span data-stu-id="c15c5-236">In Prompt, type **Store name?**</span></span>  
  
     <span data-ttu-id="c15c5-237">O usuário selecionará agora em uma lista de nomes de repositório, em vez de identificadores de repositório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-237">The user will now select from a list of store names instead of store identifiers.</span></span> <span data-ttu-id="c15c5-238">Observe que o tipo de dados de parâmetro permanece **Inteiro** porque o parâmetro se baseia no identificador de loja, não no nome de loja.</span><span class="sxs-lookup"><span data-stu-id="c15c5-238">Note that the parameter data type remains **Integer** because the parameter is based on the store identifier, not the store name.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="c15c5-239">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-239">Preview the report.</span></span>  
  
     <span data-ttu-id="c15c5-240">Na barra de ferramentas do Visualizador de relatórios, a caixa de texto parâmetro é agora uma lista suspensa exibida **\<Select a Value>** .</span><span class="sxs-lookup"><span data-stu-id="c15c5-240">In the report viewer toolbar, the parameter text box is now a drop-down list that displays **\<Select a Value>**.</span></span>  
  
10. <span data-ttu-id="c15c5-241">Na lista suspensa, selecione repositório de catálogo contoso e, em seguida, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-241">From the drop-down list, select Contoso Catalog Store, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="c15c5-242">O relatório exibe a quantidade vendida de Acessórios, Filmadoras e Câmeras Digitais SLR para o identificador de repositório **200**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-242">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4c-specify-default-values-so-the-report-runs-automatically"></a><a name="DefaultValues"></a><span data-ttu-id="c15c5-243">4C.</span><span class="sxs-lookup"><span data-stu-id="c15c5-243">4c.</span></span> <span data-ttu-id="c15c5-244">Especificar os valores padrão para que o relatório seja executado automaticamente</span><span class="sxs-lookup"><span data-stu-id="c15c5-244">Specify Default Values so the Report Runs Automatically</span></span>  
 <span data-ttu-id="c15c5-245">Você pode especificar um valor padrão para cada parâmetro, de forma que o relatório seja executado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c15c5-245">You can specify a default value for each parameter so the report runs automatically.</span></span>  
  
#### <a name="to-specify-a-default-value-from-a-dataset"></a><span data-ttu-id="c15c5-246">Para especificar um valor padrão a partir de um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="c15c5-246">To specify a default value from a dataset</span></span>  
  
1.  <span data-ttu-id="c15c5-247">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="c15c5-247">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="c15c5-248">No painel dados do relatório, clique com o botão direito do mouse em *@StoreID* e clique em **Propriedades do parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-248">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="c15c5-249">Clique em **valores padrão**e, em seguida, clique em **obter valores de uma consulta**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-249">Click **Default Values**, and then click **Get values from a query**.</span></span>  
  
4.  <span data-ttu-id="c15c5-250">Em **Conjunto de Dados**, na lista suspensa, clique em **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-250">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
5.  <span data-ttu-id="c15c5-251">Em **Campo de valor**, na lista suspensa, clique em StoreID.</span><span class="sxs-lookup"><span data-stu-id="c15c5-251">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="c15c5-252">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-252">Preview the report.</span></span>  
  
 <span data-ttu-id="c15c5-253">Para *@StoreID* o, o Visualizador de relatórios exibe o valor "Contoso América do Norte Online Store".</span><span class="sxs-lookup"><span data-stu-id="c15c5-253">For *@StoreID*, the report viewer displays the value "Contoso North America Online Store".</span></span> <span data-ttu-id="c15c5-254">Esse é o primeiro valor do conjunto de resultados para os **armazenamentos**do conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="c15c5-254">This is the first value from the result set for the dataset **Stores**.</span></span> <span data-ttu-id="c15c5-255">O relatório exibe a quantidade vendida de Câmeras Digitais do identificador de loja **199**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-255">The report displays the quantity sold for Digital Cameras for store identifier **199**.</span></span>  
  
#### <a name="to-specify-a-custom-default-value"></a><span data-ttu-id="c15c5-256">Para especificar um valor padrão personalizado</span><span class="sxs-lookup"><span data-stu-id="c15c5-256">To specify a custom default value</span></span>  
  
1.  <span data-ttu-id="c15c5-257">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="c15c5-257">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="c15c5-258">No painel dados do relatório, clique com o botão direito do mouse em *@StoreID* e clique em **Propriedades do parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-258">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="c15c5-259">Clique em **valores padrão**e clique em **especificar valores**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-259">Click **Default Values**, and click **Specify values**, and then click **Add**.</span></span> <span data-ttu-id="c15c5-260">Uma nova linha de valor é adicionada.</span><span class="sxs-lookup"><span data-stu-id="c15c5-260">A new value row is added.</span></span>  
  
4.  <span data-ttu-id="c15c5-261">Em **Valor**, digite **200**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-261">In **Value**, type **200**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c15c5-262">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-262">Preview the report.</span></span>  
  
 <span data-ttu-id="c15c5-263">Para *@StoreID* o, o Visualizador de relatórios exibe o valor "repositório de catálogos contoso".</span><span class="sxs-lookup"><span data-stu-id="c15c5-263">For *@StoreID*, the report viewer displays the value "Contoso Catalog Store".</span></span> <span data-ttu-id="c15c5-264">Este é o nome de exibição para o identificador de loja **200**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-264">This is the display name for store identifier **200**.</span></span> <span data-ttu-id="c15c5-265">O relatório exibe a quantidade vendida de Acessórios, Filmadoras e Câmeras Digitais SLR para o identificador de repositório **200**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-265">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4d-look-up-a-value-from-a-dataset-that-has-namevalue-pairs"></a><a name="NameValue"></a><span data-ttu-id="c15c5-266">4D.</span><span class="sxs-lookup"><span data-stu-id="c15c5-266">4d.</span></span> <span data-ttu-id="c15c5-267">Pesquisar um valor em um conjunto de dados com pares de nome/valor</span><span class="sxs-lookup"><span data-stu-id="c15c5-267">Look up a Value from a Dataset that has Name/Value Pairs</span></span>  
 <span data-ttu-id="c15c5-268">Um conjunto de dados pode conter o identificador e o campo de nome correspondente.</span><span class="sxs-lookup"><span data-stu-id="c15c5-268">A dataset might contain both the identifier and the corresponding name field.</span></span> <span data-ttu-id="c15c5-269">Quando você só tiver um identificador, poderá pesquisar o nome correspondente em um conjunto de dados criado por você, incluindo pares de nome/valor.</span><span class="sxs-lookup"><span data-stu-id="c15c5-269">When you only have an identifier, you can look up the corresponding name in a dataset that you created that includes name/value pairs.</span></span>  
  
#### <a name="to-look-up-a-value-from-a-dataset"></a><span data-ttu-id="c15c5-270">Para pesquisar um valor em um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="c15c5-270">To look up a value from a dataset</span></span>  
  
1.  <span data-ttu-id="c15c5-271">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="c15c5-271">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="c15c5-272">Na superfície de design, dentro da matriz, no cabeçalho de coluna da primeira linha, clique com o botão direito do mouse em `[StoreID]` e clique em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-272">On the design surface, in the matrix, in the first row column header, right-click `[StoreID]` and then click **Expression**.</span></span>  
  
3.  <span data-ttu-id="c15c5-273">No painel de expressão, exclua todo o texto exceto o `equals` (=) inicial.</span><span class="sxs-lookup"><span data-stu-id="c15c5-273">In the expression pane, delete all text except the beginning `equals` (=).</span></span>  
  
4.  <span data-ttu-id="c15c5-274">Em **Categoria**, expanda **Funções Comuns**e clique em **Diversos**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-274">In **Category**, expand **Common Functions**, and click **Miscellaneous**.</span></span> <span data-ttu-id="c15c5-275">O painel Item exibe um conjunto de funções.</span><span class="sxs-lookup"><span data-stu-id="c15c5-275">The Item pane displays a set of functions.</span></span>  
  
5.  <span data-ttu-id="c15c5-276">Em Item, clique duas vezes em **Pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-276">In Item, double-click **Lookup**.</span></span> <span data-ttu-id="c15c5-277">O painel de expressão exibe `=Lookup(`.</span><span class="sxs-lookup"><span data-stu-id="c15c5-277">The expression pane displays `=Lookup(`.</span></span> <span data-ttu-id="c15c5-278">O painel Exemplo exibe um exemplo de sintaxe de Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c15c5-278">The Example pane displays an example of Lookup syntax.</span></span>  
  
6.  <span data-ttu-id="c15c5-279">Digite a seguinte expressão: `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span><span class="sxs-lookup"><span data-stu-id="c15c5-279">Type the following expression: `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span></span>  
  
     <span data-ttu-id="c15c5-280">A função Pesquisa irá pesquisar o valor de StoreID no conjunto de dados "Repositórios" e retornar o valor StoreName.</span><span class="sxs-lookup"><span data-stu-id="c15c5-280">The Lookup function takes the value for StoreID, looks it up in the "Stores" dataset, and returns the StoreName value.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="c15c5-281">O cabeçalho da coluna de repositório contém o texto de exibição para uma expressão complexa: **<\<Expr>>** .</span><span class="sxs-lookup"><span data-stu-id="c15c5-281">The store column header contains the display text for a complex expression: **<\<Expr>>**.</span></span>  
  
8.  <span data-ttu-id="c15c5-282">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-282">Preview the report.</span></span>  
  
 <span data-ttu-id="c15c5-283">A caixa de texto na parte superior de cada página exibe o nome do repositório, em vez do identificador do repositório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-283">The text box at the top of each page displays the store name instead of the store identifier.</span></span>  
  
##  <a name="5-display-the-selected-parameter-value-in-the-report"></a><a name="Expression"></a><span data-ttu-id="c15c5-284">5. exibir o valor do parâmetro selecionado no relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-284">5. Display the Selected Parameter Value in the Report</span></span>  
 <span data-ttu-id="c15c5-285">Quando um usuário tem dúvidas sobre um relatório, é útil saber quais foram os valores de parâmetros escolhidos.</span><span class="sxs-lookup"><span data-stu-id="c15c5-285">When a user has questions about a report, it helps to know which parameter values they chose.</span></span> <span data-ttu-id="c15c5-286">Você pode preservar os valores selecionados pelos usuários para cada parâmetro no relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-286">You can preserve user-selected values for each parameter in the report.</span></span> <span data-ttu-id="c15c5-287">Uma forma de fazer isso é exibir os parâmetros em uma caixa de texto no rodapé da página.</span><span class="sxs-lookup"><span data-stu-id="c15c5-287">One way is to display the parameters in a text box in the page footer.</span></span>  
  
#### <a name="to-display-the-selected-parameter-value-and-label-on-a-page-footer"></a><span data-ttu-id="c15c5-288">Para exibir o valor de parâmetro selecionado e o rótulo em um rodapé de página</span><span class="sxs-lookup"><span data-stu-id="c15c5-288">To display the selected parameter value and label on a page footer</span></span>  
  
1.  <span data-ttu-id="c15c5-289">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="c15c5-289">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="c15c5-290">Clique com o botão direito do mouse no rodapé da página, aponte para **Inserir**e clique em **caixa de texto**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-290">Right-click the page footer, point to **Insert**, and then click **Text Box**.</span></span> <span data-ttu-id="c15c5-291">Arraste a caixa de texto para junto da caixa de texto com o carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="c15c5-291">Drag the text box next to the text box with the time stamp.</span></span> <span data-ttu-id="c15c5-292">Arraste a alça lateral da caixa de texto para expandir sua largura.</span><span class="sxs-lookup"><span data-stu-id="c15c5-292">Grab the side handle of the text box and expand the width.</span></span>  
  
3.  <span data-ttu-id="c15c5-293">No painel dados do relatório, arraste o parâmetro *@StoreID* para a caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="c15c5-293">From the Report Data pane, drag the parameter *@StoreID* to the text box.</span></span> <span data-ttu-id="c15c5-294">A caixa de texto exibe `[@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="c15c5-294">The text box displays `[@StoreID]`.</span></span>  
  
4.  <span data-ttu-id="c15c5-295">Para exibir o rótulo de parâmetro, clique na caixa de texto até aparecer o cursor de inserção depois da expressão existente, digite um espaço e arraste outra cópia do parâmetro do painel de dados do relatório para a caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="c15c5-295">To display the parameter label, click in the text box until the insert cursor appears after the existing expression, type a space, and then drag another copy of the parameter from the Report Data pane to the text box.</span></span> <span data-ttu-id="c15c5-296">A caixa de texto exibe `[@StoreID] [@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="c15c5-296">The text box displays `[@StoreID] [@StoreID]`.</span></span>  
  
5.  <span data-ttu-id="c15c5-297">Clique com o botão direito do mouse na primeira expressão e clique em **expressão**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-297">Right-click the first expression and click **Expression**.</span></span> <span data-ttu-id="c15c5-298">A caixa de diálogo **Expressão** é aberta.</span><span class="sxs-lookup"><span data-stu-id="c15c5-298">The **Expression** dialog box opens.</span></span> <span data-ttu-id="c15c5-299">Substitua o texto `Value` por `Label`.</span><span class="sxs-lookup"><span data-stu-id="c15c5-299">Replace the text `Value` by `Label`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="c15c5-300">O texto exibe: `[@StoreID.Label] [@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="c15c5-300">The text displays: `[@StoreID.Label] [@StoreID]`.</span></span>  
  
7.  <span data-ttu-id="c15c5-301">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-301">Preview the report.</span></span>  
  
##  <a name="6-use-the-report-parameter-in-a-filter"></a><a name="Filter"></a><span data-ttu-id="c15c5-302">6. usar o parâmetro de relatório em um filtro</span><span class="sxs-lookup"><span data-stu-id="c15c5-302">6. Use the Report Parameter in a Filter</span></span>  
 <span data-ttu-id="c15c5-303">Os filtros ajudam a controlar os dados a serem usados em um relatório, depois de recuperados em uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="c15c5-303">Filters help control which data to use in a report after it is retrieved from an external data source.</span></span> <span data-ttu-id="c15c5-304">Para permitir que um usuário ajude a controlar os dados que deseja consultar, você pode incluir o parâmetro de relatório em um filtro para a matriz.</span><span class="sxs-lookup"><span data-stu-id="c15c5-304">To let a user help control the data they want to see, you can include the report parameter in a filter for the matrix.</span></span>  
  
#### <a name="to-specify-a-parameter-in-a-matrix-filter"></a><span data-ttu-id="c15c5-305">Para especificar um parâmetro em um filtro de matriz</span><span class="sxs-lookup"><span data-stu-id="c15c5-305">To specify a parameter in a matrix filter</span></span>  
  
1.  <span data-ttu-id="c15c5-306">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="c15c5-306">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="c15c5-307">Clique com o botão direito do mouse em um identificador de cabeçalho de linha ou coluna na matriz e clique em **Propriedades do Tablix**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-307">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="c15c5-308">Clique em **Filtros**e em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-308">Click **Filters**, and then click **Add**.</span></span> <span data-ttu-id="c15c5-309">Uma nova linha de filtro é exibida.</span><span class="sxs-lookup"><span data-stu-id="c15c5-309">A new filter row appears.</span></span>  
  
4.  <span data-ttu-id="c15c5-310">Em **Expressão**, na lista suspensa, selecione o campo de conjunto de dados StoreID.</span><span class="sxs-lookup"><span data-stu-id="c15c5-310">In **Expression**, from the drop-down list, select the dataset field StoreID.</span></span> <span data-ttu-id="c15c5-311">O tipo de dados exibe **Inteiro**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-311">The data type displays **Integer**.</span></span> <span data-ttu-id="c15c5-312">Quando o valor da expressão for um campo de conjunto de dados, o tipo de dados será definido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c15c5-312">When the expression value is a dataset field, the data type is set automatically.</span></span>  
  
5.  <span data-ttu-id="c15c5-313">Em **operador**, verifique se `equals` (=) está selecionado.</span><span class="sxs-lookup"><span data-stu-id="c15c5-313">In **Operator**, verify that `equals` (=) is selected.</span></span>  
  
6.  <span data-ttu-id="c15c5-314">Em **Valor**, digite `[@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="c15c5-314">In **Value**, type `[@StoreID]`.</span></span> <span data-ttu-id="c15c5-315">`[@StoreID]` é a sintaxe de expressão simples que representa `=Parameters!StoreID.Value`.</span><span class="sxs-lookup"><span data-stu-id="c15c5-315">`[@StoreID]` is the simple expression syntax that represents `=Parameters!StoreID.Value`.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="c15c5-316">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-316">Preview the report.</span></span>  
  
     <span data-ttu-id="c15c5-317">A matriz só exibe dados para o "Repositório de Catálogos Contoso".</span><span class="sxs-lookup"><span data-stu-id="c15c5-317">The matrix displays data only for "Contoso Catalog Store".</span></span>  
  
9. <span data-ttu-id="c15c5-318">Na barra de ferramentas do visualizador de relatórios, para **Nome da loja?**, selecione **Loja Online Contoso na Ásia**e clique em **Exibir Relatório**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-318">On the report viewer toolbar, for **Store name?**, select **Contoso Asia Online Store**, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="c15c5-319">A matriz exibe dados correspondentes ao repositório que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="c15c5-319">The matrix displays data that corresponds to the store that you selected.</span></span>  
  
##  <a name="7-change-the-report-parameter-to-accept-multiple-values"></a><a name="Multivalued"></a><span data-ttu-id="c15c5-320">7. alterar o parâmetro de relatório para aceitar vários valores</span><span class="sxs-lookup"><span data-stu-id="c15c5-320">7. Change the Report Parameter to Accept Multiple Values</span></span>  
 <span data-ttu-id="c15c5-321">Para alterar um parâmetro de valor único para vários valores, você deve alterar a consulta e todas as expressões que contêm alguma referência ao parâmetro, inclusive filtros.</span><span class="sxs-lookup"><span data-stu-id="c15c5-321">To change a parameter from single to multivalued, you must change the query, and all expressions that contain a reference to the parameter, including filters.</span></span> <span data-ttu-id="c15c5-322">Um parâmetro de vários valores é uma matriz de valores.</span><span class="sxs-lookup"><span data-stu-id="c15c5-322">A multivalued parameter is an array of values.</span></span> <span data-ttu-id="c15c5-323">Em uma consulta de conjunto de dados, a sintaxe de consulta deve testar a inclusão de um valor em um conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="c15c5-323">In a dataset query, query syntax must test for inclusion of one value in a set of values.</span></span> <span data-ttu-id="c15c5-324">Em uma expressão de relatório, a sintaxe da expressão deve acessar uma matriz de valores, em vez de um valor individual.</span><span class="sxs-lookup"><span data-stu-id="c15c5-324">In a report expression, expression syntax must access an array of values instead of an individual value.</span></span>  
  
#### <a name="to-change-a-parameter-from-single-to-multivalued"></a><span data-ttu-id="c15c5-325">Para alterar um parâmetro de valor único para vários valores</span><span class="sxs-lookup"><span data-stu-id="c15c5-325">To change a parameter from single to multivalued</span></span>  
  
1.  <span data-ttu-id="c15c5-326">Alterne para o modo Design.</span><span class="sxs-lookup"><span data-stu-id="c15c5-326">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="c15c5-327">No painel dados do relatório, clique com o botão direito do mouse em *@StoreID* e clique em **Propriedades do parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-327">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="c15c5-328">Selecione **Permitir vários valores**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-328">Select **Allow multiple values**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="c15c5-329">No painel Dados do Relatório, expanda a pasta **Conjuntos de Dados** , clique com o botão direito do mouse em **DataSet1**e clique em **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-329">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
6.  <span data-ttu-id="c15c5-330">Altere `equals` (=) para `IN` na [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` cláusula na última linha da consulta:</span><span class="sxs-lookup"><span data-stu-id="c15c5-330">Change `equals` (=) to `IN` in the [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause in the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID IN (@StoreID)  
    ```  
  
     <span data-ttu-id="c15c5-331">O operador `IN` testa um valor para inclusão em um conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="c15c5-331">The `IN` operator tests a value for inclusion in a set of values.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="c15c5-332">Clique com o botão direito do mouse em um identificador de cabeçalho de linha ou coluna na matriz e clique em **Propriedades do Tablix**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-332">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
9. <span data-ttu-id="c15c5-333">Clique em **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-333">Click **Filters**.</span></span>  
  
10. <span data-ttu-id="c15c5-334">Em **Operador**, selecione **Dentro**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-334">In **Operator**, select **In**.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="c15c5-335">Na caixa de texto que exibe o parâmetro no rodapé da página, exclua todo o texto.</span><span class="sxs-lookup"><span data-stu-id="c15c5-335">In the text box that displays the parameter in the page footer, delete all text.</span></span>  
  
13. <span data-ttu-id="c15c5-336">Clique com o botão direito do mouse na caixa de texto e clique em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-336">Right-click the text box, and then click **Expression**.</span></span> <span data-ttu-id="c15c5-337">Digite a seguinte expressão: `=Join(Parameters!StoreID.Label, ", ")`</span><span class="sxs-lookup"><span data-stu-id="c15c5-337">Type the following expression: `=Join(Parameters!StoreID.Label, ", ")`</span></span>  
  
     <span data-ttu-id="c15c5-338">Esta expressão concatena todos os nomes de repositório selecionados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="c15c5-338">This expression concatenates all store names that the user selected.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
15. <span data-ttu-id="c15c5-339">Clique na caixa de texto em frente à expressão que você acaba de criar e digite o seguinte: Valores de Parâmetros Selecionados:.</span><span class="sxs-lookup"><span data-stu-id="c15c5-339">Click in the text box in front of the expression that you just created, and then type the following: Parameter Values Selected:.</span></span>  
  
16. <span data-ttu-id="c15c5-340">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-340">Preview the report.</span></span>  
  
17. <span data-ttu-id="c15c5-341">Clique na lista suspensa junto a Nome do Repositório?</span><span class="sxs-lookup"><span data-stu-id="c15c5-341">Click the drop-down list next to Store Name?</span></span>  
  
     <span data-ttu-id="c15c5-342">Cada valor válido aparece junto a uma caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="c15c5-342">Each valid value appears next to a check box.</span></span>  
  
18. <span data-ttu-id="c15c5-343">Clique em **Selecionar Tudo**e em **Exibir Relatório**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-343">Click **Select All**, and then click **View Report**.</span></span>  
  
     <span data-ttu-id="c15c5-344">O relatório exibe a quantidade vendida de todas as subcategorias de todos os repositórios.</span><span class="sxs-lookup"><span data-stu-id="c15c5-344">The report displays the quantity sold for all subcategories for all stores.</span></span>  
  
19. <span data-ttu-id="c15c5-345">Na lista suspensa, clique em **Selecionar Tudo** para limpar a lista, clique em “Loja de Catálogos Contoso” e em “Loja Online Contoso na Ásia” e em **Exibir Relatório**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-345">From the drop-down list, click **Select All** to clear the list, click "Contoso Catalog Store" and "Contoso Asia Online Store", and then click **View Report**.</span></span>  
  
##  <a name="8-add-a-boolean-parameter-for-conditional-visibility"></a><a name="Boolean"></a><span data-ttu-id="c15c5-346">8. adicionar um parâmetro booliano para visibilidade condicional</span><span class="sxs-lookup"><span data-stu-id="c15c5-346">8. Add a Boolean Parameter for Conditional Visibility</span></span>  
  
#### <a name="to-add-a-boolean-parameter"></a><span data-ttu-id="c15c5-347">Para adicionar um parâmetro booliano</span><span class="sxs-lookup"><span data-stu-id="c15c5-347">To add a boolean parameter</span></span>  
  
1.  <span data-ttu-id="c15c5-348">Na superfície de design, no painel Dados do Relatório, clique com o botão direito do mouse em **Parâmetros**e clique em **Adicionar Parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-348">On the design surface, in the Report Data pane, right-click **Parameters**, and click **Add Parameter**.</span></span>  
  
2.  <span data-ttu-id="c15c5-349">Em **Nome**, digite ShowSelections.</span><span class="sxs-lookup"><span data-stu-id="c15c5-349">In **Name**, type ShowSelections.</span></span>  
  
3.  <span data-ttu-id="c15c5-350">Em **Prompt**, digite Mostrar seleções?</span><span class="sxs-lookup"><span data-stu-id="c15c5-350">In **Prompt**, type Show selections?</span></span>  
  
4.  <span data-ttu-id="c15c5-351">Em **tipo de dados**, na lista suspensa, clique em **booliano**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-351">In **Data type**, from the drop-down list, click **Boolean**.</span></span>  
  
5.  <span data-ttu-id="c15c5-352">Clique em **Valores Padrão**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-352">Click **Default Values**.</span></span>  
  
6.  <span data-ttu-id="c15c5-353">Clique em **Especificar valor**e em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-353">Click **Specify value**, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="c15c5-354">Em **Valor**, digite **False**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-354">In **Value**, type **False**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-set-visibility-based-on-a-boolean-parameter"></a><span data-ttu-id="c15c5-355">Para definir a visibilidade com base em um parâmetro booliano</span><span class="sxs-lookup"><span data-stu-id="c15c5-355">To set visibility based on a boolean parameter</span></span>  
  
1.  <span data-ttu-id="c15c5-356">Na superfície de design, clique com o botão direito do mouse na caixa de texto no rodapé de página que exibe os valores de parâmetros e clique em **Propriedades da Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-356">On the design surface, right-click the text box in the page footer that displays the parameter values, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="c15c5-357">Clique em **Visibilidade**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-357">Click **Visibility**.</span></span>  
  
3.  <span data-ttu-id="c15c5-358">Selecione a opção **Mostrar ou ocultar com base em uma expressão**e clique no botão de expressão **Fx**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-358">Select the option **Show or hide based on an expression**, and then click the expression button **Fx**.</span></span>  
  
4.  <span data-ttu-id="c15c5-359">Digite a seguinte expressão: `=Not Parameters!ShowSelections.Value`</span><span class="sxs-lookup"><span data-stu-id="c15c5-359">Type the following expression: `=Not Parameters!ShowSelections.Value`</span></span>  
  
     <span data-ttu-id="c15c5-360">A opção de Visibilidade de caixa de texto é controlada pela propriedade Oculta.</span><span class="sxs-lookup"><span data-stu-id="c15c5-360">The text box Visibility option is controlled by the property Hidden.</span></span> <span data-ttu-id="c15c5-361">Aplique o operador `Not` de forma que, quando o parâmetro for selecionado, a propriedade Oculta seja falsa e a caixa de texto seja exibida.</span><span class="sxs-lookup"><span data-stu-id="c15c5-361">Apply the `Not` operator so that when the parameter is selected, the Hidden property is false, and the text box will be displayed.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="c15c5-362">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-362">Preview the report.</span></span>  
  
     <span data-ttu-id="c15c5-363">A caixa de texto que exibe as escolhas de parâmetro não aparece.</span><span class="sxs-lookup"><span data-stu-id="c15c5-363">The text box that displays the parameter choices does not appear.</span></span>  
  
8.  <span data-ttu-id="c15c5-364">Na barra de ferramentas do Visualizador de relatórios, ao lado de **Mostrar seleções**, clique em `True` .</span><span class="sxs-lookup"><span data-stu-id="c15c5-364">In the report viewer toolbar, next to **Show selections**, click `True`.</span></span>  
  
9. <span data-ttu-id="c15c5-365">Visualize o relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-365">Preview the report.</span></span>  
  
 <span data-ttu-id="c15c5-366">A caixa de texto no rodapé da página exibe todos os nomes de repositório selecionados por você.</span><span class="sxs-lookup"><span data-stu-id="c15c5-366">The text box in the page footer displays all the store names that you selected.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="c15c5-367">9. adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-367">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="c15c5-368">Para adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-368">To add a report title</span></span>  
  
1.  <span data-ttu-id="c15c5-369">Na superfície de design, clique em **Clique para adicionar título**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-369">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="c15c5-370">Digite Vendas de Produto com Parâmetros e clique fora da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="c15c5-370">Type Parameterized Product Sales, and then click outside the text box.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="c15c5-371">10. salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-371">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="c15c5-372">Para salvar o relatório em um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="c15c5-372">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="c15c5-373">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-373">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="c15c5-374">Clique em **Sites e Servidores Recentes**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-374">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="c15c5-375">Selecione ou digite o nome do servidor de relatório no qual você tem permissão para salvar relatórios.</span><span class="sxs-lookup"><span data-stu-id="c15c5-375">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="c15c5-376">A mensagem **Conectando-se a um servidor de relatório**é exibida.</span><span class="sxs-lookup"><span data-stu-id="c15c5-376">The message **Connecting to report server appears**.</span></span> <span data-ttu-id="c15c5-377">Quando a conexão for concluída, você verá o conteúdo da pasta do relatório que o administrador do servidor de relatório especificou como o local padrão para relatórios.</span><span class="sxs-lookup"><span data-stu-id="c15c5-377">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="c15c5-378">Em **Nome**, substitua o nome padrão por Relatório de Vendas com Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="c15c5-378">In **Name**, replace the default name with Parameterized Sales Report.</span></span>  
  
5.  <span data-ttu-id="c15c5-379">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c15c5-379">Click **Save**.</span></span>  
  
 <span data-ttu-id="c15c5-380">O relatório será salvo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-380">The report is saved to the report server.</span></span> <span data-ttu-id="c15c5-381">O servidor de relatório ao qual você está conectado aparece na barra de status na parte inferior da janela.</span><span class="sxs-lookup"><span data-stu-id="c15c5-381">The report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c15c5-382">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c15c5-382">Next Steps</span></span>  
 <span data-ttu-id="c15c5-383">Isso conclui o passo a passo da adição de um parâmetro ao seu relatório.</span><span class="sxs-lookup"><span data-stu-id="c15c5-383">This concludes the walkthrough for how to add a parameter to your report.</span></span> <span data-ttu-id="c15c5-384">Para saber mais sobre parâmetros, consulte [Parâmetros de relatório &#40;Construtor de Relatórios e Designer de Relatórios&#41;](report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c15c5-384">To learn more about parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c15c5-385">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c15c5-385">See Also</span></span>  
 <span data-ttu-id="c15c5-386">[TUTORIAIS &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="c15c5-386">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="c15c5-387">Construtor de Relatórios no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="c15c5-387">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
