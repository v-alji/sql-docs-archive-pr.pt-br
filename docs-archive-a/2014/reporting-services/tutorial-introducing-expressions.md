---
title: 'Tutorial: Apresentação de expressões | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d05ef4c-5f91-48b2-8795-f0a201a0b3cc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62a815800dba0730052eb812124d4561d031d0e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684019"
---
# <a name="tutorial-introducing-expressions"></a><span data-ttu-id="dfc3a-102">Tutorial: Apresentando expressões</span><span class="sxs-lookup"><span data-stu-id="dfc3a-102">Tutorial: Introducing Expressions</span></span>
  <span data-ttu-id="dfc3a-103">As expressões o ajudam a criar relatórios avançados e flexíveis.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-103">Expressions help you create powerful and flexible reports.</span></span> <span data-ttu-id="dfc3a-104">Este tutorial ensina a criar e implementar expressões que utilizam funções e operadores comuns.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-104">This tutorial teaches you to create and implement expressions that use common functions and operators.</span></span> <span data-ttu-id="dfc3a-105">Você usará a caixa de diálogo **expressão** para escrever expressões que concatenam valores de nome, pesquisam valores em um conjunto de um DataSet separado, exibem imagens diferentes com base em valores de campo e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-105">You will use the **Expression** dialog box to write expressions that concatenate name values, look up values in a separate dataset, display different pictures based on field values, and so on.</span></span>  
  
 <span data-ttu-id="dfc3a-106">O relatório é um relatório de barras com cores de linhas alternadas em branco e uma cor.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-106">The report is a barred report with alternating row colors in white and a color.</span></span> <span data-ttu-id="dfc3a-107">O relatório inclui um parâmetro para selecionar a cor das linhas que não são brancas.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-107">The report includes a parameter for selecting the color of the non-white rows.</span></span>  
  
 <span data-ttu-id="dfc3a-108">A ilustração a seguir mostra um relatório semelhante ao que você criará.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-108">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="dfc3a-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span><span class="sxs-lookup"><span data-stu-id="dfc3a-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="dfc3a-110">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="dfc3a-110">What You Will Learn</span></span>  
 <span data-ttu-id="dfc3a-111">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="dfc3a-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="dfc3a-112">Criar um relatório de tabela e conjunto de dados no Assistente de Tabela ou Matriz</span><span class="sxs-lookup"><span data-stu-id="dfc3a-112">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="dfc3a-113">Atualizar nomes padrão da fonte de dados ou do conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="dfc3a-113">Update Default Names of the Data Source and Dataset</span></span>](#UpdateNames)  
  
3.  [<span data-ttu-id="dfc3a-114">Exibir nome, inicial e sobrenome</span><span class="sxs-lookup"><span data-stu-id="dfc3a-114">Display First Name, Initial, and Last Name</span></span>](#Concatenate)  
  
4.  [<span data-ttu-id="dfc3a-115">Usar imagens para exibir sexo</span><span class="sxs-lookup"><span data-stu-id="dfc3a-115">Use Images to Display Gender</span></span>](#Gender)  
  
5.  [<span data-ttu-id="dfc3a-116">Pesquisar nome de CountryRegion</span><span class="sxs-lookup"><span data-stu-id="dfc3a-116">Look Up CountryRegion Name</span></span>](#Lookup)  
  
6.  [<span data-ttu-id="dfc3a-117">Contar dias desde a última compra</span><span class="sxs-lookup"><span data-stu-id="dfc3a-117">Count Days Since Last Purchase</span></span>](#Count)  
  
7.  [<span data-ttu-id="dfc3a-118">Usar um indicador para mostrar comparação de vendas</span><span class="sxs-lookup"><span data-stu-id="dfc3a-118">Use an Indicator to Show Sales Comparison</span></span>](#Indicator)  
  
8.  [<span data-ttu-id="dfc3a-119">Tornar o relatório um relatório de "barra verde"</span><span class="sxs-lookup"><span data-stu-id="dfc3a-119">Make the Report a "Green Bar" Report</span></span>](#GreenBar)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="dfc3a-120">Outras etapas opcionais</span><span class="sxs-lookup"><span data-stu-id="dfc3a-120">Other Optional Steps</span></span>  
  
-   [<span data-ttu-id="dfc3a-121">Formatar coluna de data</span><span class="sxs-lookup"><span data-stu-id="dfc3a-121">Format Date Column</span></span>](#DateFormat)  
  
-   [<span data-ttu-id="dfc3a-122">Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="dfc3a-122">Add a Report Title</span></span>](#Title)  
  
-   [<span data-ttu-id="dfc3a-123">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="dfc3a-123">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="dfc3a-124">Tempo estimado para concluir este tutorial: 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-124">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfc3a-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dfc3a-125">Requirements</span></span>  
 <span data-ttu-id="dfc3a-126">Para obter informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="dfc3a-126">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="dfc3a-127">1. criar um relatório de tabela e um conjunto de relatórios do assistente de tabela ou matriz</span><span class="sxs-lookup"><span data-stu-id="dfc3a-127">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="dfc3a-128">Crie um relatório de tabela, uma fonte de dados e um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-128">Create a table report, a data source, and a dataset.</span></span> <span data-ttu-id="dfc3a-129">Ao criar o layout da tabela, você incluirá apenas alguns campos.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-129">When you lay out the table, you will include only a few fields.</span></span> <span data-ttu-id="dfc3a-130">Depois de concluir o assistente, você adicionará manualmente colunas.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-130">After you complete the wizard you will manually add columns.</span></span> <span data-ttu-id="dfc3a-131">O assistente facilita a criação de layout da tabela e a aplicação de um estilo.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-131">The wizard makes it easy for you to lay out the table and apply a style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfc3a-132">Neste tutorial, a consulta contém os valores de dados para que não precise de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-132">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="dfc3a-133">Isso torna a consulta bastante longa.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-133">This makes the query quite long.</span></span> <span data-ttu-id="dfc3a-134">Em um ambiente empresarial, uma consulta não conteria os dados.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-134">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="dfc3a-135">Isso é apenas para fins de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-135">This is for learning purposes only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfc3a-136">Neste tutorial, as etapas do assistente são consolidadas em um procedimento.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-136">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="dfc3a-137">Para obter instruções passo a passo sobre como procurar um servidor de relatório, escolher uma fonte de dados e criar um conjunto de dados, consulte o primeiro tutorial desta série: [Tutorial: Criação de um relatório de tabela básico &#40;Construtor de Relatórios&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="dfc3a-137">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
#### <a name="to-create-a-new-table-report"></a><span data-ttu-id="dfc3a-138">Para criar um novo relatório de tabela</span><span class="sxs-lookup"><span data-stu-id="dfc3a-138">To create a new table report</span></span>  
  
1.  <span data-ttu-id="dfc3a-139">Clique em **Iniciar**, aponte para **programas**, clique em [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Construtor de relatórios**e, em seguida, clique em **Construtor de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-139">Click **Start**, point to **Programs**, click [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="dfc3a-140">A caixa de diálogo **introdução** é exibida.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-140">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dfc3a-141">Se a caixa de diálogo **introdução** não for exibida, no botão **Construtor de relatórios** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-141">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dfc3a-142">Se preferir usar a versão do ClickOnce do Construtor de Relatórios, abra Report Manager e clique em **Construtor de relatórios**ou vá para um site do SharePoint no qual Reporting Services tipos de conteúdo como relatórios estão habilitados e clique em **Construtor de relatórios relatório** no menu **novo documento** na guia **documentos** de uma biblioteca de documentos compartilhados.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-142">If you prefer using the ClickOnce version of Report Builder, open Report Manager and click **Report Builder**, or go to a SharePoint site on which Reporting Services content types such as reports are enabled and click **Report Builder Report** on the **New Document** menu on the **Documents** tab of a shared documents library.</span></span>  
  
2.  <span data-ttu-id="dfc3a-143">No painel esquerdo, verifique se **Novo Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-143">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="dfc3a-144">No painel direito, clique em **Assistente de Tabela ou Matriz**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-144">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="dfc3a-145">Na página **Escolher um conjunto de dados** , clique em **Criar um conjunto de dados**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-145">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="dfc3a-146">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="dfc3a-147">Na página **Escolher uma conexão com uma fonte de dados** , selecione uma fonte de dados do tipo **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-147">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="dfc3a-148">Selecione uma fonte de dados na lista ou navegue até o servidor de relatório para selecionar uma.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-148">Select a data source from the list or browse to the report server to select one.</span></span>  
  
7.  <span data-ttu-id="dfc3a-149">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-149">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="dfc3a-150">Na página **Crie uma consulta** , clique em **Editar como Texto**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-150">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="dfc3a-151">Cole a seguinte consulta no painel de consulta:</span><span class="sxs-lookup"><span data-stu-id="dfc3a-151">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Lauren' AS FirstName,'Johnson' AS LastName, 'American Samoa' AS StateProvince, 1 AS CountryRegionID,'Unknown' AS Gender, CAST(9996.60 AS money) AS YTDPurchase, CAST('2010-6-10' AS date) AS LastPurchase  
    UNION SELECT'Warren' AS FirstName, 'Pal' AS LastName, 'New South Wales' AS StateProvince, 2 AS CountryRegionID, 'Male' AS Gender, CAST(5747.25 AS money) AS YTDPurchase, CAST('2010-7-3' AS date) AS LastPurchase  
    UNION SELECT 'Fernando' AS FirstName, 'Ross' AS LastName, 'Alberta' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(9248.15 AS money) AS YTDPurchase, CAST('2010-10-17' AS date) AS LastPurchase  
    UNION SELECT 'Rob' AS FirstName, 'Caron' AS LastName, 'Northwest Territories' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(742.50 AS money) AS YTDPurchase, CAST('2010-4-29' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Bailey' AS LastName, 'British Columbia' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(1147.50 AS money) AS YTDPurchase, CAST('2010-6-15' AS date) AS LastPurchase  
    UNION SELECT  'Bridget' AS FirstName, 'She' AS LastName, 'Hamburg' AS StateProvince, 4 AS CountryRegionID, 'Female' AS Gender, CAST(7497.30 AS money) AS YTDPurchase, CAST('2010-5-10' AS date) AS LastPurchase  
    UNION SELECT 'Alexander' AS FirstName, 'Martin' AS LastName, 'Saxony' AS StateProvince, 4 AS CountryRegionID, 'Male' AS Gender, CAST(2997.60 AS money) AS YTDPurchase, CAST('2010-11-19' AS date) AS LastPurchase  
    UNION SELECT 'Yolanda' AS FirstName, 'Sharma' AS LastName ,'Micronesia' AS StateProvince, 5 AS CountryRegionID, 'Female' AS Gender, CAST(3247.95 AS money) AS YTDPurchase, CAST('2010-8-23' AS date) AS LastPurchase  
    UNION SELECT 'Marc' AS FirstName, 'Zimmerman' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1200.00 AS money) AS YTDPurchase, CAST('2010-11-16' AS date) AS LastPurchase  
    UNION SELECT 'Katherine' AS FirstName, 'Abel' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Female' AS Gender, CAST(2025.00 AS money) AS YTDPurchase, CAST('2010-12-1' AS date) AS LastPurchase  
    UNION SELECT 'Nicolas' as FirstName, 'Anand' AS LastName, 'Seine (Paris)' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1425.00 AS money) AS YTDPurchase, CAST('2010-12-11' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Peters' AS LastName, 'England' AS StateProvince, 12 AS CountryRegionID, 'Male' AS Gender, CAST(887.50 AS money) AS YTDPurchase, CAST('2010-8-15' AS date) AS LastPurchase  
    UNION SELECT 'Alison' AS FirstName, 'Nath' AS LastName, 'Alaska' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(607.50 AS money) AS YTDPurchase, CAST('2010-10-13' AS date) AS LastPurchase  
    UNION SELECT 'Grace' AS FirstName, 'Patterson' AS LastName, 'Kansas' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(1215.00 AS money) AS YTDPurchase, CAST('2010-10-18' AS date) AS LastPurchase  
    UNION SELECT 'Bobby' AS FirstName, 'Sanchez' AS LastName, 'North Dakota' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(6191.00 AS money) AS YTDPurchase, CAST('2010-9-17' AS date) AS LastPurchase  
    UNION SELECT 'Charles' AS FirstName, 'Reed' AS LastName, 'Nebraska' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8772.00 AS money) AS YTDPurchase, CAST('2010-8-27' AS date) AS LastPurchase  
    UNION SELECT 'Orlando' AS FirstName, 'Romeo' AS LastName, 'Texas' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8578.00 AS money) AS YTDPurchase, CAST('2010-7-29' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    ```  
  
     <span data-ttu-id="dfc3a-152">A consulta especifica nomes de colunas que incluem data de nascimento, nome, sobrenome, estado ou província, identificador de país/região, sexo e compras desde o início do ano.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-152">The query specifies column names that include a birth date, first name, last name, state or province, country/region identifier, gender, and year-to-date purchases.</span></span>  
  
10. <span data-ttu-id="dfc3a-153">Na barra de ferramentas do designer de consultas, clique em **executar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="dfc3a-153">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="dfc3a-154">O conjunto de resultados exibe 20 linhas de dados e inclui as seguintes colunas: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase e LastPurchase.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-154">The result set displays 20 rows of data and includes the following columns: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase, and LastPurchase.</span></span>  
  
11. <span data-ttu-id="dfc3a-155">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-155">Click **Next**.</span></span>  
  
12. <span data-ttu-id="dfc3a-156">Na página **Organizar campos** , arraste os campos a seguir, na ordem especificada, da lista **Campos Disponíveis** para a lista **Valores** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-156">On the **Arrange fields** page, drag the following fields, in the specified order, from the **Available Fields** list to the **Values** list.</span></span>  
  
    -   <span data-ttu-id="dfc3a-157">StateProvince</span><span class="sxs-lookup"><span data-stu-id="dfc3a-157">StateProvince</span></span>  
  
    -   <span data-ttu-id="dfc3a-158">CountryRegionID</span><span class="sxs-lookup"><span data-stu-id="dfc3a-158">CountryRegionID</span></span>  
  
    -   <span data-ttu-id="dfc3a-159">LastPurchase</span><span class="sxs-lookup"><span data-stu-id="dfc3a-159">LastPurchase</span></span>  
  
    -   <span data-ttu-id="dfc3a-160">YTDPurchase</span><span class="sxs-lookup"><span data-stu-id="dfc3a-160">YTDPurchase</span></span>  
  
     <span data-ttu-id="dfc3a-161">Como CountryRegionID e YTDPurchase contêm dados numéricos, a agregação SUM é aplicada a eles por padrão.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-161">Because the CountryRegionID and YTDPurchase contain numeric data, the SUM aggregate is applied to them by default.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dfc3a-162">Os campos FirstName e LastName não estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-162">The FirstName and LastName fields are not included.</span></span> <span data-ttu-id="dfc3a-163">Você irá adicioná-los em uma etapa posterior.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-163">You will add them in a later step.</span></span>  
  
13. <span data-ttu-id="dfc3a-164">Na lista **valores** , clique com o botão direito do mouse `CountryRegionID` e clique na opção **soma** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-164">In the **Values** list, right-click `CountryRegionID` and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="dfc3a-165">A Soma não é mais aplicada a CountryRegionID.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-165">Sum is no longer applied to CountryRegionID.</span></span>  
  
14. <span data-ttu-id="dfc3a-166">Na lista **Valores** , clique com o botão direito do mouse em **YTDPurchase** e clique na opção **Soma** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-166">In the **Values** list, right-click **YTDPurchase** and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="dfc3a-167">A Soma não é mais aplicada a YTDPurchase.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-167">Sum is no longer applied to YTDPurchase.</span></span>  
  
15. <span data-ttu-id="dfc3a-168">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-168">Click **Next**.</span></span>  
  
16. <span data-ttu-id="dfc3a-169">Na página **Escolher o layout**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-169">On the **Choose the layout** page, click **Next**.</span></span>  
  
17. <span data-ttu-id="dfc3a-170">Na página **escolher um estilo** , clique em **Tablet**e em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-170">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
##  <a name="2-update-default-names-of-the-data-source-and-dataset"></a><a name="UpdateNames"></a><span data-ttu-id="dfc3a-171">2. atualizar os nomes padrão da fonte de dados e do DataSet</span><span class="sxs-lookup"><span data-stu-id="dfc3a-171">2. Update Default Names of the Data Source and Dataset</span></span>  
  
#### <a name="to-update-the-default-name-of-the-data-source"></a><span data-ttu-id="dfc3a-172">Para atualizar o nome padrão da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="dfc3a-172">To update the default name of the data source</span></span>  
  
1.  <span data-ttu-id="dfc3a-173">No painel Dados do Relatório, expanda **Fontes de Dados**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-173">In the Report Data pane, expand **Data Sources**.</span></span>  
  
2.  <span data-ttu-id="dfc3a-174">Clique com o botão direito do mouse em **DataSource1** e clique em **Propriedades da Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-174">Right-click **DataSource1** and click **Data Source Properties.**</span></span>  
  
3.  <span data-ttu-id="dfc3a-175">Na caixa **Nome** , digite **ExpressionsDataSource**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-175">In the **Name** box, type **ExpressionsDataSource**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-update-the-default-name-of-the-dataset"></a><span data-ttu-id="dfc3a-176">Para atualizar o nome padrão do conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="dfc3a-176">To update the default name of the dataset</span></span>  
  
1.  <span data-ttu-id="dfc3a-177">No painel Dados do Relatório, expanda **Conjuntos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-177">In the Report Data pane, expand **Datasets**.</span></span>  
  
2.  <span data-ttu-id="dfc3a-178">Clique com o botão direito do mouse em **DataSet1** e clique em **Propriedades do Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-178">Right-click **DataSet1** and click **Dataset Properties.**</span></span>  
  
3.  <span data-ttu-id="dfc3a-179">Na caixa **Nome** , digite **Expressions**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-179">In the **Name** box, type **Expressions**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="3-display-first-name-initial-and-last-name"></a><a name="Concatenate"></a><span data-ttu-id="dfc3a-180">3. exibir nome, inicial e sobrenome</span><span class="sxs-lookup"><span data-stu-id="dfc3a-180">3. Display First Name, Initial, and Last Name</span></span>  
 <span data-ttu-id="dfc3a-181">Use a função **Left** e o operador **Concatenate** (**&**) em uma expressão avaliada com um nome que inclui uma inicial e um sobrenome.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-181">Use the **Left** function and the **Concatenate** (**&**) operator in an expression that evaluates to a name that includes an initial and a last name.</span></span> <span data-ttu-id="dfc3a-182">Você pode criar a expressão passo a passo ou ignorá-la no procedimento e copiar/colar a expressão do tutorial na caixa de diálogo **Expressão** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-182">You can build the expression step by step or skip ahead in the procedure and copy/paste the expression from the tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the-name-column"></a><span data-ttu-id="dfc3a-183">Para adicionar a coluna Nome</span><span class="sxs-lookup"><span data-stu-id="dfc3a-183">To add the Name column</span></span>  
  
1.  <span data-ttu-id="dfc3a-184">Clique com o botão direito do mouse na coluna **StateProvince** , aponte para **Inserir Coluna**e clique em **Esquerda**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-184">Right-click the **StateProvince** column, point to **Insert Column**, and then click **Left**.</span></span>  
  
     <span data-ttu-id="dfc3a-185">Uma nova coluna é adicionada à esquerda da coluna **StateProvince** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-185">A new column is added to the left of the **StateProvince** column.</span></span>  
  
2.  <span data-ttu-id="dfc3a-186">Clique no título da nova coluna e digite **Name**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-186">Click the title of the new column and type **Name**</span></span>  
  
3.  <span data-ttu-id="dfc3a-187">Clique com o botão direito do mouse na célula de dados da coluna **Name** e clique em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-187">Right-click the data cell for the **Name** column and click **Expression**.</span></span>  
  
4.  <span data-ttu-id="dfc3a-188">Na caixa de diálogo **Expressão** , expanda **Funções Comuns**e clique em **Texto**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-188">In the **Expression** dialog box, expand **Common Functions**, and then click **Text**.</span></span>  
  
5.  <span data-ttu-id="dfc3a-189">Na lista **Item** , clique duas vezes em **Left**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-189">In the **Item** list, double-click **Left**.</span></span>  
  
     <span data-ttu-id="dfc3a-190">A função **Left** é adicionada à expressão.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-190">The **Left** function is added to the expression.</span></span>  
  
6.  <span data-ttu-id="dfc3a-191">Na lista **Categoria** , clique em **Campos (Expressões)**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-191">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="dfc3a-192">Na lista **Valores** , clique duas vezes em **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-192">In the **Values** list, double-click **FirstName**.</span></span>  
  
8.  <span data-ttu-id="dfc3a-193">Digite **, 1)**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-193">Type **, 1)**</span></span>  
  
     <span data-ttu-id="dfc3a-194">Essa expressão extrai um caractere do valor **FirstName** , contando a partir da esquerda.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-194">This expression extracts one character from the **FirstName** value, counting from the left.</span></span>  
  
9. <span data-ttu-id="dfc3a-195">Digite **& "" &**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-195">Type **&" "&**</span></span>  
  
10. <span data-ttu-id="dfc3a-196">Na lista **Valores** , clique duas vezes em **LastName**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-196">In the **Values** list, double-click **LastName**.</span></span>  
  
     <span data-ttu-id="dfc3a-197">A expressão completa é: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span><span class="sxs-lookup"><span data-stu-id="dfc3a-197">The completed expression: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="dfc3a-198">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-198">Click **Run** to preview the report.</span></span>  
  
##  <a name="4-use-images-to-display-gender"></a><a name="Gender"></a><span data-ttu-id="dfc3a-199">4. usar imagens para exibir o gênero</span><span class="sxs-lookup"><span data-stu-id="dfc3a-199">4. Use Images to Display Gender</span></span>  
 <span data-ttu-id="dfc3a-200">Use imagens para mostrar o sexo de uma pessoa e identificar valores de sexo desconhecidos, usando uma terceira imagem.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-200">Use images to show the gender of a person, and identify unknown gender values by using a third image.</span></span> <span data-ttu-id="dfc3a-201">Você adicionará ao relatório três imagens ocultas e uma nova coluna para exibir as imagens. Em seguida, determine a imagem que aparece na coluna, com base no valor do campo Sexo.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-201">You will add to the report three hidden images and a new column to display the images, and then determine the image that appears in the column based on the value of the Gender field.</span></span>  
  
 <span data-ttu-id="dfc3a-202">Para aplicar uma cor à célula da tabela que contém a imagem quando você transforma o relatório em um relatório de barras, adicione um retângulo e, depois, adicione a imagem ao retângulo.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-202">To apply a color to the table cell that contains the image when you make the report a barred report, you will add a rectangle and then add the image to the rectangle.</span></span> <span data-ttu-id="dfc3a-203">Você precisa usar um retângulo porque pode aplicar uma cor do plano de fundo a um retângulo, mas não a uma imagem.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-203">You need to use a rectangle because you can apply a background color to a rectangle, but not to an image.</span></span>  
  
 <span data-ttu-id="dfc3a-204">O tutorial usa imagens que são instaladas com o Windows, mas você pode usar quaisquer imagens disponíveis.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-204">The tutorial uses images that are installed with Windows, but you can use any images available to you.</span></span> <span data-ttu-id="dfc3a-205">Você usará imagens inseridas e elas não precisam ser instaladas no computador local nem no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-205">You will use embedded images, and they do not need to be installed on your local computer or the report server.</span></span>  
  
#### <a name="to-add-images-to-the-report-body"></a><span data-ttu-id="dfc3a-206">Para adicionar imagens ao corpo do relatório</span><span class="sxs-lookup"><span data-stu-id="dfc3a-206">To add images to the report body</span></span>  
  
1.  <span data-ttu-id="dfc3a-207">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-207">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="dfc3a-208">Na guia **Inserir** da faixa de opções, clique em **Imagem** e no corpo do relatório, abaixo da tabela.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-208">On the **Insert** tab of the ribbon, click **Image** and then click in the report body, below the table.</span></span>  
  
     <span data-ttu-id="dfc3a-209">A caixa de diálogo **Propriedades da Imagem** será aberta.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-209">The **Image Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="dfc3a-210">Clique em **Importar** e procure C:\Users\Public\Public Pictures\Sample Pictures.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-210">Click **Import** and navigate to C:\Users\Public\Public Pictures\Sample Pictures.</span></span>  
  
4.  <span data-ttu-id="dfc3a-211">Clique em Penguins.JPG e em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-211">Click Penguins.JPG and click **Open**.</span></span>  
  
     <span data-ttu-id="dfc3a-212">Na caixa de diálogo **Propriedades da Imagem**, clique em **Visibilidade** e na opção **Ocultar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-212">In the **Image Properties** dialog box, click **Visibility** and then click the **Hide** option.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="dfc3a-213">Repita as etapas 2 a 5, mas escolha Koala.JPG.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-213">Repeat steps 2 through 5, but choose Koala.JPG.</span></span>  
  
7.  <span data-ttu-id="dfc3a-214">Repita as etapas 2 a 5, mas escolha Tulips.JPG.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-214">Repeat steps 2 through 5, but choose Tulips.JPG.</span></span>  
  
#### <a name="to-add-the-gender-column"></a><span data-ttu-id="dfc3a-215">Para adicionar a coluna Sexo</span><span class="sxs-lookup"><span data-stu-id="dfc3a-215">To add the Gender column</span></span>  
  
1.  <span data-ttu-id="dfc3a-216">Clique com o botão direito do mouse na coluna **Name**, aponte para **Inserir Coluna** e clique em **Direita**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-216">Right-click the **Name** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="dfc3a-217">Uma nova coluna é adicionada à direita da coluna **Name**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-217">A new column is added to the right of the **Name** column.</span></span>  
  
2.  <span data-ttu-id="dfc3a-218">Clique no título da nova coluna e digite **Gênero**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-218">Click the title of the new column and type **Gender**</span></span>  
  
#### <a name="to-add-a-rectangle"></a><span data-ttu-id="dfc3a-219">Para adicionar um retângulo</span><span class="sxs-lookup"><span data-stu-id="dfc3a-219">To add a rectangle</span></span>  
  
-   <span data-ttu-id="dfc3a-220">Na guia **Inserir** da faixa de opções, clique em **Retângulo** e na célula de dados da coluna **Gênero**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-220">On the **Insert** tab of the ribbon, click **Rectangle** and then click in the data cell of the **Gender** column.</span></span>  
  
     <span data-ttu-id="dfc3a-221">Um retângulo é adicionado à célula.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-221">A rectangle is added to the cell.</span></span>  
  
#### <a name="to-add-an-image-to-the-rectangle"></a><span data-ttu-id="dfc3a-222">Para adicionar uma imagem ao retângulo</span><span class="sxs-lookup"><span data-stu-id="dfc3a-222">To add an image to the rectangle</span></span>  
  
1.  <span data-ttu-id="dfc3a-223">Clique com o botão direito do mouse no retângulo, aponte para **Inserir** e clique em **Imagem**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-223">Right-click in the rectangle, point to **Insert**, and then click **Image**.</span></span>  
  
2.  <span data-ttu-id="dfc3a-224">Na caixa de diálogo **Propriedades da Imagem**, clique na seta para baixo, ao lado de **Usar esta imagem**, e selecione uma das imagens adicionadas; por exemplo, Penguins.JPG.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-224">In the **Image Properties** dialog box, click the down arrow beside **Use this image**, and select one of the images you added, for example, Penguins.JPG.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-use-images-to-show-gender"></a><span data-ttu-id="dfc3a-225">Para usar imagens para mostrar o sexo</span><span class="sxs-lookup"><span data-stu-id="dfc3a-225">To use images to show gender</span></span>  
  
1.  <span data-ttu-id="dfc3a-226">Clique com o botão direito do mouse na imagem na célula de dados na coluna **Gênero** e clique em **Propriedades da Imagem**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-226">Right-click the image in the data cell in the **Gender** column and click **Image Properties**.</span></span>  
  
2.  <span data-ttu-id="dfc3a-227">Na caixa de diálogo **Propriedades da Imagem**, clique no botão de expressão **fx** ao lado da caixa de texto **Usar esta imagem**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-227">In the **Image Properties** dialog box, click the expression **fx** button next to the **Use this image** text box.</span></span>  
  
3.  <span data-ttu-id="dfc3a-228">Na caixa de diálogo **Expressão** , expanda **Funções Comuns** e clique em **Fluxo do Programa**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-228">In the **Expression** dialog box, expand **Common Functions** and click **Program Flow**.</span></span>  
  
4.  <span data-ttu-id="dfc3a-229">Na lista **Item** , clique duas vezes em **Mudar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-229">In the **Item** list, double-click **Switch**.</span></span>  
  
5.  <span data-ttu-id="dfc3a-230">Na lista **Categoria** , clique em **Campos (Expressões)**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-230">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="dfc3a-231">Na lista **Valores** , clique duas vezes em **Gênero**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-231">In the **Values** list, double-click **Gender**.</span></span>  
  
7.  <span data-ttu-id="dfc3a-232">Digite **="Male", "Koala",**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-232">Type **="Male", "Koala",**</span></span>  
  
8.  <span data-ttu-id="dfc3a-233">Na lista **Valores** , clique duas vezes em **Gênero**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-233">In the **Values** list, double-click **Gender**.</span></span>  
  
9. <span data-ttu-id="dfc3a-234">Digite **="Female", "Penguins",**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-234">Type **="Female", "Penguins",**</span></span>  
  
10. <span data-ttu-id="dfc3a-235">Na lista **Valores** , clique duas vezes em **Gênero**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-235">In the **Values** list, double-click **Gender**.</span></span>  
  
11. <span data-ttu-id="dfc3a-236">Digite **="Unknown", "Tulips")**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-236">Type **="Unknown", "Tulips")**</span></span>  
  
     <span data-ttu-id="dfc3a-237">A expressão completa é: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span><span class="sxs-lookup"><span data-stu-id="dfc3a-237">The completed expression: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="dfc3a-238">Clique novamente em **OK** para fechar a caixa de diálogo **Propriedades da Imagem**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-238">Click **OK** again to close the **Image Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="dfc3a-239">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-239">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-look-up-countryregion-name"></a><a name="Lookup"></a><span data-ttu-id="dfc3a-240">5. Pesquisar nome do CountryRegion</span><span class="sxs-lookup"><span data-stu-id="dfc3a-240">5. Look Up CountryRegion Name</span></span>  
 <span data-ttu-id="dfc3a-241">Crie o conjunto de dados CountryRegion e use a função **Lookup** para exibir o nome de um país/região, em vez do identificador do país/região.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-241">Create the CountryRegion dataset and use the **Lookup** function to display the name of a country/region instead of the identifier of the country/region.</span></span>  
  
#### <a name="to-create-the-countryregion-dataset"></a><span data-ttu-id="dfc3a-242">Para criar o conjunto de dados CountryRegion</span><span class="sxs-lookup"><span data-stu-id="dfc3a-242">To create the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="dfc3a-243">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="dfc3a-244">No painel dados do relatório, clique em **novo** e, em seguida, clique em **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-244">In the Report Data pane, click **New** and then click **Dataset**.</span></span>  
  
3.  <span data-ttu-id="dfc3a-245">Clique em **Usar um conjunto de dados inserido no meu relatório**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-245">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="dfc3a-246">Na lista **Fonte de dados** , selecione ExpressionsDataSource.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-246">In the **Data source** list, select ExpressionsDataSource.</span></span>  
  
5.  <span data-ttu-id="dfc3a-247">Na caixa **Nome** , digite **CountryRegion**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-247">In the **Name** box, type **CountryRegion**</span></span>  
  
6.  <span data-ttu-id="dfc3a-248">Verifique se o tipo de consulta **Texto** está selecionado e clique em **Designer de Consultas**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-248">Verify that the **Text** query type is selected and click **Query Designer**.</span></span>  
  
7.  <span data-ttu-id="dfc3a-249">Clique em **Editar como Texto**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-249">Click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="dfc3a-250">Copie e cole a seguinte consulta no painel de consulta:</span><span class="sxs-lookup"><span data-stu-id="dfc3a-250">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 1 AS ID, 'American Samoa' AS CountryRegion  
    UNION SELECT 2 AS CountryRegionID, 'Australia' AS CountryRegion  
    UNION SELECT 3 AS ID, 'Canada' AS CountryRegion  
    UNION SELECT 4 AS ID, 'Germany' AS CountryRegion  
    UNION SELECT 5 AS ID, 'Micronesia' AS CountryRegion  
    UNION SELECT 6 AS ID, 'France' AS CountryRegion  
    UNION SELECT 7 AS ID, 'United States' AS CountryRegion  
    UNION SELECT 8 AS ID, 'Brazil' AS CountryRegion  
    UNION SELECT 9 AS ID, 'Mexico' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Japan' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Australia' AS CountryRegion  
    UNION SELECT 12 AS ID, 'United Kingdom' AS CountryRegion  
    ```  
  
9. <span data-ttu-id="dfc3a-251">Clique em **executar** (**!**) para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-251">Click **Run** (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="dfc3a-252">Os resultados da consulta são os identificadores e nomes de país/região.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-252">The query results are the country/region identifiers and names.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="dfc3a-253">Clique novamente em **OK** para fechar a caixa de diálogo **Propriedades do Conjunto de Dados** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-253">Click **OK** again to close the **Dataset Properties** dialog box.</span></span>  
  
#### <a name="to-look-up-values-in-the-countryregion-dataset"></a><span data-ttu-id="dfc3a-254">Para pesquisar valores no conjunto de dados CountryRegion</span><span class="sxs-lookup"><span data-stu-id="dfc3a-254">To look up values in the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="dfc3a-255">Clique no título da coluna **Identificação de país ou região** e exclua o texto: Identificação.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-255">Click the **Country Region ID** column title and delete the text: ID.</span></span>  
  
2.  <span data-ttu-id="dfc3a-256">Clique com o botão direito do mouse na célula de dados da coluna **Country Region** e clique em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-256">Right-click the data cell for the **Country Region** column and click **Expression**.</span></span>  
  
3.  <span data-ttu-id="dfc3a-257">Exclua a expressão, exceto o sinal de igual (=) inicial.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-257">Delete the expression except the initial equal (=) sign.</span></span>  
  
     <span data-ttu-id="dfc3a-258">A expressão restante é: `=`</span><span class="sxs-lookup"><span data-stu-id="dfc3a-258">The remaining expression is: `=`</span></span>  
  
4.  <span data-ttu-id="dfc3a-259">Na caixa de diálogo **Expressão**, expanda **Funções Comuns** e clique em **Diversos**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-259">In the **Expression** dialog box, expand **Common Functions** and click **Miscellaneous**.</span></span>  
  
5.  <span data-ttu-id="dfc3a-260">Na lista **Item**, clique duas vezes em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-260">In the **Item** list, double-click **Lookup**.</span></span>  
  
6.  <span data-ttu-id="dfc3a-261">Na lista **Categoria** , clique em **Campos (Expressões)**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-261">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="dfc3a-262">Na lista **valores** , clique duas vezes em `CountryRegionID` .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-262">In the **Values** list, double-click `CountryRegionID`.</span></span>  
  
8.  <span data-ttu-id="dfc3a-263">Se o cursor não estiver logo após `CountryRegionID.Value`, posicione-o lá.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-263">If the cursor is not already immediately after `CountryRegionID.Value`, place it there.</span></span>  
  
9. <span data-ttu-id="dfc3a-264">Exclua o parêntese à direita e digite **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-264">Delete the right parenthesis and then type **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**</span></span>  
  
     <span data-ttu-id="dfc3a-265">A expressão completa é: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span><span class="sxs-lookup"><span data-stu-id="dfc3a-265">The completed expression: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span></span>  
  
     <span data-ttu-id="dfc3a-266">A sintaxe da função **Lookup** especifica uma pesquisa entre CountryRegionID e ID no conjunto de dados CountryRegion que retorna o valor CountryRegion, que também se encontra no conjunto de dados CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-266">The syntax of the **Lookup** function specifies a lookup between CountryRegionID and ID in the CountryRegion dataset that returns the CountryRegion value, which is also in the CountryRegion dataset.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="dfc3a-267">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-267">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-count-days-since-last-purchase"></a><a name="Count"></a><span data-ttu-id="dfc3a-268">6. contagem de dias desde a última compra</span><span class="sxs-lookup"><span data-stu-id="dfc3a-268">6. Count Days Since Last Purchase</span></span>  
 <span data-ttu-id="dfc3a-269">Adicione uma coluna e, em seguida, use a função **Now** ou a `ExecutionTime` variável global interna para calcular o número de dias a partir de hoje desde a última compra de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-269">Add a column and then use the **Now** function or the `ExecutionTime` built-in global variable to calculate the number of days from today since a person's last purchases.</span></span>  
  
#### <a name="to-add-the-days-ago-column"></a><span data-ttu-id="dfc3a-270">Para adicionar a coluna Days Ago</span><span class="sxs-lookup"><span data-stu-id="dfc3a-270">To add the Days Ago column</span></span>  
  
1.  <span data-ttu-id="dfc3a-271">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-271">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="dfc3a-272">Clique com o botão direito do mouse na coluna **Last Purchase** , aponte para **Inserir Coluna**e clique em **Direita**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-272">Right-click the **Last Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="dfc3a-273">Uma nova coluna é adicionada à direita da coluna **Last Purchase** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-273">A new column is added to the right of the **Last Purchase** column.</span></span>  
  
3.  <span data-ttu-id="dfc3a-274">No cabeçalho de coluna, digite **Dias Atrás**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-274">In the column header, type **Days Ago**</span></span>  
  
4.  <span data-ttu-id="dfc3a-275">Clique com o botão direito do mouse na célula de dados da coluna **Dias Atrás** e clique em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-275">Right-click the data cell for the **Days Ago** column and click **Expression**.</span></span>  
  
5.  <span data-ttu-id="dfc3a-276">Na caixa de diálogo **Expressão**, expanda **Funções Comuns** e clique em **Data e Hora**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-276">In the **Expression** dialog box, expand **Common Functions**, and then click **Date & Time**.</span></span>  
  
6.  <span data-ttu-id="dfc3a-277">Na lista **Item** , clique duas vezes em **DateDiff**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-277">In the **Item** list, double-click **DateDiff**.</span></span>  
  
7.  <span data-ttu-id="dfc3a-278">Se o cursor não estiver logo após `DateDiff(`, posicione-o lá.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-278">If the cursor is not already immediately after `DateDiff(`, place it there.</span></span>  
  
8.  <span data-ttu-id="dfc3a-279">Digite **"d",**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-279">Type **"d",**</span></span>  
  
9. <span data-ttu-id="dfc3a-280">Na lista **Categoria** , clique em **Campos (Expressões)**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-280">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
10. <span data-ttu-id="dfc3a-281">Na lista **Valores**, clique duas vezes em **LastPurchase**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-281">In the **Values** list, double-click **LastPurchase**.</span></span>  
  
11. <span data-ttu-id="dfc3a-282">Se o cursor não estiver logo após `Fields!LastPurchase.Value`, posicione-o lá.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-282">If the cursor is not already immediately after `Fields!LastPurchase.Value`, place it there.</span></span>  
  
12. <span data-ttu-id="dfc3a-283">Tipo **,**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-283">Type **,**</span></span>  
  
13. <span data-ttu-id="dfc3a-284">Na lista **Categoria**, clique em **Data e Hora** novamente.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-284">In the **Category** list, click **Date & Time** again.</span></span>  
  
14. <span data-ttu-id="dfc3a-285">Na lista **Item**, clique duas vezes em **Agora**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-285">In the **Item** list, double-click **Now**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="dfc3a-286">Em relatórios de produção, não use a função **Now** em expressões que são avaliadas diversas vezes como os renderizadores de relatório (por exemplo, nas linhas de detalhes de um relatório).</span><span class="sxs-lookup"><span data-stu-id="dfc3a-286">In production reports you should not use the **Now** function in expressions that are evaluated multiple times as the report renders (for example, in the detail rows of a report).</span></span> <span data-ttu-id="dfc3a-287">O valor de **Now** muda de acordo com a linha e valores diferentes afetam os resultados de avaliação de expressões, o que leva a resultados um pouco inconsistentes.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-287">The value of **Now** changes from row to row and the different values affect the evaluation results of expressions, which leads to results that are subtly inconsistent.</span></span> <span data-ttu-id="dfc3a-288">Procure utilizar a variável global `ExecutionTime` fornecida por [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfc3a-288">Instead, you should use the `ExecutionTime` global variable that [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides.</span></span>  
  
15. <span data-ttu-id="dfc3a-289">Se o cursor não estiver logo após `Now(`, posicione-o lá.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-289">If the cursor is not already immediately after `Now(`, place it there.</span></span>  
  
16. <span data-ttu-id="dfc3a-290">Exclua o parêntese à esquerda e digite **)**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-290">Delete the left parenthesis and then type **)**</span></span>  
  
     <span data-ttu-id="dfc3a-291">A expressão completa é: `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span><span class="sxs-lookup"><span data-stu-id="dfc3a-291">The completed expression: `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span></span>  
  
17. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="7-use-an-indicator-to-show-sales-comparison"></a><a name="Indicator"></a><span data-ttu-id="dfc3a-292">7. Use um indicador para mostrar a comparação de vendas</span><span class="sxs-lookup"><span data-stu-id="dfc3a-292">7. Use an Indicator to Show Sales Comparison</span></span>  
 <span data-ttu-id="dfc3a-293">Adicione uma nova coluna e use um indicador para mostrar se as compras ACUMULAdas no ano de uma pessoa (no ano) estão acima ou abaixo das compras médias no ano.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-293">Add a new column and use an indicator to show whether a person's year-to-date (YTD) purchases are above or below the average YTD purchases.</span></span> <span data-ttu-id="dfc3a-294">A função **Round** remove os decimais dos valores.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-294">The **Round** function removes decimals from values.</span></span>  
  
 <span data-ttu-id="dfc3a-295">A configuração do indicador e seus estados exige várias etapas.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-295">The configuration of the indicator and its states requires many steps.</span></span> <span data-ttu-id="dfc3a-296">Se desejar, no procedimento "para configurar o indicador", você poderá ignorar e copiar/colar as expressões concluídas deste tutorial na caixa de diálogo **expressão** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-296">If you want to, in the "To configure the indicator" procedure, you can skip ahead and copy/paste the completed expressions from this tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the--or---avg-sales-column"></a><span data-ttu-id="dfc3a-297">Para adicionar a coluna + ou - AVG Sales</span><span class="sxs-lookup"><span data-stu-id="dfc3a-297">To add the + or - AVG Sales column</span></span>  
  
1.  <span data-ttu-id="dfc3a-298">Clique com o botão direito do mouse na coluna **YTD Purchase** , aponte para **Inserir Coluna**e clique em **Direita**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-298">Right-click the **YTD Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="dfc3a-299">Uma nova coluna é adicionada à direita da coluna **YTD Purchase** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-299">A new column is added to the right of the **YTD Purchase** column.</span></span>  
  
2.  <span data-ttu-id="dfc3a-300">Clique no título da coluna e digite **+ or - AVG Sales**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-300">Click the title of the column and type **+ or - AVG Sales**</span></span>  
  
#### <a name="to-add-an-indicator"></a><span data-ttu-id="dfc3a-301">Para adicionar um indicador</span><span class="sxs-lookup"><span data-stu-id="dfc3a-301">To add an indicator</span></span>  
  
1.  <span data-ttu-id="dfc3a-302">Na guia **Inserir** da faixa de opções, clique em **Indicador** e na célula de dados da coluna **+ or - AVG Sales**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-302">On the **Insert** tab of the ribbon, click **Indicator**, and then click the data cell for the **+ or - AVG Sales** column.</span></span>  
  
     <span data-ttu-id="dfc3a-303">A caixa de diálogo **Selecionar Tipo de Indicador** será aberta.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-303">The **Select Indicator Type** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="dfc3a-304">No grupo **Direcional** dos conjuntos de ícones, clique no conjunto de três setas cinza.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-304">In the **Directional** group of icon sets, click the set of three gray arrows.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-configure-the-indicator"></a><span data-ttu-id="dfc3a-305">Para configurar o indicador</span><span class="sxs-lookup"><span data-stu-id="dfc3a-305">To configure the indicator</span></span>  
  
1.  <span data-ttu-id="dfc3a-306">Clique com o botão direito do mouse no indicador, clique em **Propriedades do Indicador**e em **Valores e Estados**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-306">Right-click the indicator, click **Indicator Properties**, and then click **Value and States**.</span></span>  
  
2.  <span data-ttu-id="dfc3a-307">Clique no botão de expressão **fx** ao lado da caixa de texto **Valor** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-307">Click the expression **fx** button next to the **Value** text box.</span></span>  
  
3.  <span data-ttu-id="dfc3a-308">Na caixa de diálogo **Expressão** , expanda **Funções Comuns**e clique em **Matemática**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-308">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
4.  <span data-ttu-id="dfc3a-309">Na lista **Item** , clique duas vezes em **Arredondar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-309">In the **Item** list, double-click **Round**.</span></span>  
  
5.  <span data-ttu-id="dfc3a-310">Na lista **Categoria** , clique em **Campos (Expressões)**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-310">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="dfc3a-311">Na lista **Valores**, clique duas vezes em **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-311">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
7.  <span data-ttu-id="dfc3a-312">Se o cursor não estiver logo após `Fields!YTDPurchase.Value`, posicione-o lá.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-312">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
8.  <span data-ttu-id="dfc3a-313">Escreva**-**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-313">Type  **-**</span></span>  
  
9. <span data-ttu-id="dfc3a-314">Expanda novamente **Funções Comuns** e clique em **Agregação**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-314">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
10. <span data-ttu-id="dfc3a-315">Na lista **Item**, clique duas vezes em **Média**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-315">In the **Item** list, double-click **Avg**.</span></span>  
  
11. <span data-ttu-id="dfc3a-316">Na lista **Categoria** , clique em **Campos (Expressões)**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-316">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
12. <span data-ttu-id="dfc3a-317">Na lista **Valores**, clique duas vezes em **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-317">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
13. <span data-ttu-id="dfc3a-318">Se o cursor não estiver logo após `Fields!YTDPurchase.Value`, posicione-o lá.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-318">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
14. <span data-ttu-id="dfc3a-319">Digite **, "Expressions"))**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-319">Type **, "Expressions"))**</span></span>  
  
     <span data-ttu-id="dfc3a-320">A expressão completa é: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span><span class="sxs-lookup"><span data-stu-id="dfc3a-320">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span></span>  
  
15. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
16. <span data-ttu-id="dfc3a-321">Na caixa **Unidade de Medida dos Estados** , selecione **Numérica**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-321">In the **States Measurement Unit** box, select **Numeric**.</span></span>  
  
17. <span data-ttu-id="dfc3a-322">Na linha com a seta apontando para baixo, clique no botão **fx** à direita da caixa de texto do valor **Start** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-322">In the row with the down-pointing arrow, click the **fx** button to the right of the text box for the **Start** value.</span></span>  
  
18. <span data-ttu-id="dfc3a-323">Na caixa de diálogo **Expressão** , expanda **Funções Comuns**e clique em **Matemática**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-323">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
19. <span data-ttu-id="dfc3a-324">Na lista **Item** , clique duas vezes em **Arredondar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-324">In the **Item** list, double-click **Round**.</span></span>  
  
20. <span data-ttu-id="dfc3a-325">Na lista **Categoria** , clique em **Campos (Expressões)**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-325">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
21. <span data-ttu-id="dfc3a-326">Na lista **Valores**, clique duas vezes em **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-326">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
22. <span data-ttu-id="dfc3a-327">Se o cursor não estiver logo após `Fields!YTDPurchase.Value`, posicione-o lá.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-327">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="dfc3a-328">Escreva**-**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-328">Type  **-**</span></span>  
  
24. <span data-ttu-id="dfc3a-329">Expanda novamente **Funções Comuns** e clique em **Agregação**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-329">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
25. <span data-ttu-id="dfc3a-330">Na lista **Item**, clique duas vezes em **Média**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-330">In the **Item** list, double-click **Avg**.</span></span>  
  
26. <span data-ttu-id="dfc3a-331">Na lista **Categoria** , clique em **Campos (Expressões)**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-331">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
27. <span data-ttu-id="dfc3a-332">Na lista **Valores**, clique duas vezes em **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-332">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
28. <span data-ttu-id="dfc3a-333">Se o cursor não estiver logo após `Fields!YTDPurchase.Value`, posicione-o lá.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-333">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
29. <span data-ttu-id="dfc3a-334">Digite **, "Expressions")) < 0**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-334">Type **, "Expressions")) < 0**</span></span>  
  
     <span data-ttu-id="dfc3a-335">A expressão completa é: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span><span class="sxs-lookup"><span data-stu-id="dfc3a-335">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span></span>  
  
30. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
31. <span data-ttu-id="dfc3a-336">Na caixa de texto do valor **End** , digite **0**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-336">In the text box for the **End** value, type **0**</span></span>  
  
32. <span data-ttu-id="dfc3a-337">Clique na linha com a seta apontando para a horizontal e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-337">Click the row with the horizontal-pointing arrow and click **Delete**.</span></span>  
  
33. <span data-ttu-id="dfc3a-338">Na linha com a seta apontando para cima, na caixa **Iniciar** , digite **0**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-338">In the row with the up-pointing arrow, in the **Start** box, type **0**</span></span>  
  
34. <span data-ttu-id="dfc3a-339">Clique no botão **fx** à direita da caixa de texto do valor **End** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-339">Click the **fx** button to the right of the text box for the **End** value.</span></span>  
  
35. <span data-ttu-id="dfc3a-340">Na caixa de diálogo **expressão** , crie a expressão:`=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span><span class="sxs-lookup"><span data-stu-id="dfc3a-340">In the **Expression** dialog box, create the expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span></span>  
  
36. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
37. <span data-ttu-id="dfc3a-341">Clique novamente em **OK** para fechar a caixa de diálogo **Propriedades do indicador** .</span><span class="sxs-lookup"><span data-stu-id="dfc3a-341">Click **OK** again to close the **Indicator properties** dialog box.</span></span>  
  
38. <span data-ttu-id="dfc3a-342">Clique em **Executar** para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-342">Click **Run** to preview the report.</span></span>  
  
##  <a name="8-make-the-report-a-green-bar-report"></a><a name="GreenBar"></a><span data-ttu-id="dfc3a-343">8. tornar o relatório um relatório de "barra verde"</span><span class="sxs-lookup"><span data-stu-id="dfc3a-343">8. Make the Report a "Green Bar" Report</span></span>  
 <span data-ttu-id="dfc3a-344">Use um parâmetro para especificar a cor a ser aplicada para alternar linhas no relatório, transformando-o em um relatório de barras.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-344">Use a parameter to specify the color to apply to alternating rows in the report, making it a barred report.</span></span>  
  
#### <a name="to-add-a-parameter"></a><span data-ttu-id="dfc3a-345">Para adicionar um parâmetro</span><span class="sxs-lookup"><span data-stu-id="dfc3a-345">To add a parameter</span></span>  
  
1.  <span data-ttu-id="dfc3a-346">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-346">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="dfc3a-347">No painel **Dados do Relatório** , clique com o botão direito do mouse em **Parâmetros** e clique em **Adicionar Parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-347">In the **Report Data** pane, right-click **Parameters** and click **Add Parameter**.</span></span>  
  
     <span data-ttu-id="dfc3a-348">A caixa de diálogo **Propriedades do Parâmetro do Relatório** é aberta.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-348">The **Report Parameter Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="dfc3a-349">Em **Prompt**, digite **Escolher cor**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-349">In **Prompt**, type **Choose color**</span></span>  
  
4.  <span data-ttu-id="dfc3a-350">Em **Nome**, digite **RowColor**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-350">In **Name**, type **RowColor**</span></span>  
  
5.  <span data-ttu-id="dfc3a-351">No painel esquerdo, clique em **Valores Disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-351">In the left pane, click **Available Values**.</span></span>  
  
6.  <span data-ttu-id="dfc3a-352">Clique em **Especificar valores**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-352">Click **Specify values**.</span></span>  
  
7.  <span data-ttu-id="dfc3a-353">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-353">Click **Add**.</span></span>  
  
8.  <span data-ttu-id="dfc3a-354">Na caixa **rótulo** , digite: **amarelo**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-354">In the **Label** box, type: **Yellow**</span></span>  
  
9. <span data-ttu-id="dfc3a-355">Na caixa **Valor** , digite **Amarelo**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-355">In the **Value** box, type **Yellow**</span></span>  
  
10. <span data-ttu-id="dfc3a-356">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-356">Click **Add**.</span></span>  
  
11. <span data-ttu-id="dfc3a-357">Na caixa **Rótulo** , digite **Verde**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-357">In the **Label** box, type **Green**</span></span>  
  
12. <span data-ttu-id="dfc3a-358">Na caixa **Valor** , digite **PaleGreen**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-358">In the **Value** box, type **PaleGreen**</span></span>  
  
13. <span data-ttu-id="dfc3a-359">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-359">Click **Add**.</span></span>  
  
14. <span data-ttu-id="dfc3a-360">Na caixa **Rótulo** , digite **Azul**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-360">In the **Label** box, type **Blue**</span></span>  
  
15. <span data-ttu-id="dfc3a-361">Na caixa **Valor** , digite **LightBlue**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-361">In the **Value** box, type **LightBlue**</span></span>  
  
16. <span data-ttu-id="dfc3a-362">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-362">Click **Add**.</span></span>  
  
17. <span data-ttu-id="dfc3a-363">Na caixa **Rótulo** , digite **Rosa**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-363">In the **Label** box, type **Pink**</span></span>  
  
18. <span data-ttu-id="dfc3a-364">Na caixa **Valor** , digite **Rosa**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-364">In the **Value** box, type **Pink**</span></span>  
  
19. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-apply-alternating-colors-to-detail-rows"></a><span data-ttu-id="dfc3a-365">Para aplicar cores alternativas a linhas de detalhes</span><span class="sxs-lookup"><span data-stu-id="dfc3a-365">To apply alternating colors to detail rows</span></span>  
  
1.  <span data-ttu-id="dfc3a-366">Clique na guia **Exibir** na faixa de opções e verifique se **Propriedades** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-366">Click the **View** tab on the ribbon and verify that **Properties** is selected.</span></span>  
  
2.  <span data-ttu-id="dfc3a-367">Clique na célula de dados da coluna **Name** e pressione a tecla Shift.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-367">Click the data cell for the **Name** column and press the Shift key.</span></span>  
  
3.  <span data-ttu-id="dfc3a-368">Uma a uma, clique nas outras células na linha.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-368">One by one, click the other cells in the row.</span></span>  
  
4.  <span data-ttu-id="dfc3a-369">No painel Propriedades, clique em **BackgroundColor**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-369">In the Properties pane, click **BackgroundColor**.</span></span>  
  
     <span data-ttu-id="dfc3a-370">Se o painel Propriedades listar propriedades por categoria, você encontrará **BackgroundColor** na categoria **Preenchimento**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-370">If your Properties pane lists properties by category, you will find the **BackgroundColor** under the **Fill** category.</span></span>  
  
5.  <span data-ttu-id="dfc3a-371">Clique na seta para baixo e em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-371">Click the down arrow and then click **Expression**.</span></span>  
  
6.  <span data-ttu-id="dfc3a-372">Na caixa de diálogo **Expressão** , expanda **Funções Comuns**e clique em **Fluxo do Programa**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-372">In the **Expression** dialog box, expand **Common Functions**, and then click **Program Flow**.</span></span>  
  
7.  <span data-ttu-id="dfc3a-373">Na lista **Item** , clique duas vezes em **IIf**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-373">In the **Item** list, double-click **IIf**.</span></span>  
  
8.  <span data-ttu-id="dfc3a-374">Expanda **Funções Comuns** e clique em **Agregação**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-374">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
9. <span data-ttu-id="dfc3a-375">Na lista **Item**, clique duas vezes em **RunningValue**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-375">In the **Item** list, double-click **RunningValue**.</span></span>  
  
10. <span data-ttu-id="dfc3a-376">Na lista **Categoria** , clique em **Campos (Expressões)**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-376">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
11. <span data-ttu-id="dfc3a-377">Na lista **Valores** , clique duas vezes em **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-377">In the **Values** list, double-click **FirstName**.</span></span>  
  
12. <span data-ttu-id="dfc3a-378">Se o cursor não estiver logo após `Fields!FirstName.Value`, coloque-o nesse local e digite **,**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-378">If the cursor is not already immediately after `Fields!FirstName.Value`, place it there and type **,**</span></span>  
  
13. <span data-ttu-id="dfc3a-379">Expanda **Funções Comuns** e clique em **Agregação**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-379">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
14. <span data-ttu-id="dfc3a-380">Na lista **Item**, clique duas vezes em **Contagem**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-380">In the **Item** list, double-click **Count**.</span></span>  
  
15. <span data-ttu-id="dfc3a-381">Se o cursor não estiver logo após `Count(`, posicione-o lá.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-381">If the cursor is not already immediately after `Count(`, place it there.</span></span>  
  
16. <span data-ttu-id="dfc3a-382">Exclua o parêntese esquerdo e, em seguida **, digite "expressões")**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-382">Delete the left parenthesis and then type **,"Expressions")**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dfc3a-383">Expressions é o nome do conjunto de dados no qual as linhas de dados serão contadas.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-383">Expressions is the name of the dataset in which to count data rows.</span></span>  
  
17. <span data-ttu-id="dfc3a-384">Expanda **Operadores** e clique em **Aritmético**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-384">Expand **Operators** and click **Arithmetic**.</span></span>  
  
18. <span data-ttu-id="dfc3a-385">Na lista **Item**, clique duas vezes em **Mod**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-385">In the **Item** list, double-click **Mod**.</span></span>  
  
19. <span data-ttu-id="dfc3a-386">Se o cursor não estiver logo após `Mod`, posicione-o lá.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-386">If the cursor is not already immediately after `Mod`, place it there.</span></span>  
  
20. <span data-ttu-id="dfc3a-387">Digite **2 =0,**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-387">Type  **2 =0,**</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="dfc3a-388">Inclua um espaço antes de digitar o número 2.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-388">Be sure you include a space before you type the number 2.</span></span>  
  
21. <span data-ttu-id="dfc3a-389">Clique em **Parâmetros** e, na lista **Valores** , clique duas vezes em **RowColor**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-389">Click **Parameters** and in the **Values** list, double-click **RowColor**.</span></span>  
  
22. <span data-ttu-id="dfc3a-390">Se o cursor não estiver logo após `Parameters!RowColor.Value`, posicione-o lá.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-390">If the cursor is not already immediately after `Parameters!RowColor.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="dfc3a-391">Digite **, "White")**</span><span class="sxs-lookup"><span data-stu-id="dfc3a-391">Type **, "White")**</span></span>  
  
     <span data-ttu-id="dfc3a-392">A expressão completa é: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span><span class="sxs-lookup"><span data-stu-id="dfc3a-392">The completed expression: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span></span>  
  
24. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="run-the-report"></a><span data-ttu-id="dfc3a-393">Executar o relatório</span><span class="sxs-lookup"><span data-stu-id="dfc3a-393">Run the Report</span></span>  
  
1.  <span data-ttu-id="dfc3a-394">Se não estiver na guia **Início**, clique em **Início** para retornar ao modo Design.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-394">If not on the **Home** tab, click **Home** to return to design view.</span></span>  
  
2.  <span data-ttu-id="dfc3a-395">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-395">Click **Run**.</span></span>  
  
3.  <span data-ttu-id="dfc3a-396">Na lista suspensa **Escolher cor**, selecione a cor das barras que não são brancas no relatório.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-396">In the **Choose color** drop-down list, select the color of the non-white bars on the report.</span></span>  
  
4.  <span data-ttu-id="dfc3a-397">Clique em **Exibir Relatório**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-397">Click **View Report**.</span></span>  
  
     <span data-ttu-id="dfc3a-398">O relatório é renderizado e linhas alternativas têm o plano de fundo escolhido por você.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-398">The report renders and alternating rows have the background that you chose.</span></span>  
  
##  <a name="optional-format-date-column"></a><a name="DateFormat"></a><span data-ttu-id="dfc3a-399">adicional Formatar coluna de data</span><span class="sxs-lookup"><span data-stu-id="dfc3a-399">(optional) Format Date Column</span></span>  
 <span data-ttu-id="dfc3a-400">Formate a coluna **Last Purchase**, que contém datas.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-400">Format the **Last Purchase** column, which contains dates.</span></span>  
  
#### <a name="to-format-date-column"></a><span data-ttu-id="dfc3a-401">Para formatar coluna de dados</span><span class="sxs-lookup"><span data-stu-id="dfc3a-401">To format date column</span></span>  
  
1.  <span data-ttu-id="dfc3a-402">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-402">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="dfc3a-403">Clique com o botão direito do mouse na célula de dados da coluna **Last Purchase** e clique em **Propriedades de Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-403">Right-click the data cell for the **Last Purchase** column and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="dfc3a-404">Na caixa de diálogo **Propriedades da Caixa de Texto**, clique em **Número**, em **Data** e no tipo **\*1/31/2000**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-404">In the **Text Box Properties** dialog box, click **Number**, click **Date**, and then click the type **\*1/31/2000**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="dfc3a-405">adicional Adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="dfc3a-405">(optional) Add a Report Title</span></span>  
 <span data-ttu-id="dfc3a-406">Adicione um título ao relatório.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-406">Add a title to the report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="dfc3a-407">Para adicionar um título de relatório</span><span class="sxs-lookup"><span data-stu-id="dfc3a-407">To add a report title</span></span>  
  
1.  <span data-ttu-id="dfc3a-408">Na superfície de design, clique em **Clique para adicionar título**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-408">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="dfc3a-409">Digite **Resumo de Comparação de Vendas** e clique fora da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-409">Type **Sales Comparison Summary**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="dfc3a-410">Clique com o botão direito do mouse na caixa de texto que contém **Resumo de Comparação de Vendas** e clique em **Propriedades da Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-410">Right-click the text box that contains **Sales Comparison Summary** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="dfc3a-411">Na caixa de diálogo **Propriedades da Caixa de Texto** , clique em **Fonte**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-411">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="dfc3a-412">Na lista **Tamanho** , selecione **18pt**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-412">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="dfc3a-413">Na lista **Cor**, selecione **Cinza**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-413">In the **Color** list, select **Gray**.</span></span>  
  
7.  <span data-ttu-id="dfc3a-414">Selecione **Negrito** e **Itálico**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-414">Select  **Bold** and  **Italic**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-save-the-report"></a><a name="Save"></a><span data-ttu-id="dfc3a-415">adicional Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="dfc3a-415">(optional) Save the Report</span></span>  
 <span data-ttu-id="dfc3a-416">É possível salvar relatórios em um servidor de relatório, em uma biblioteca do SharePoint ou no computador.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-416">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="dfc3a-417">Para obter mais informações, consulte [Salvando relatórios &#40;Construtor de Relatórios&#41;](report-builder/saving-reports-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="dfc3a-417">For more information, see [Saving Reports &#40;Report Builder&#41;](report-builder/saving-reports-report-builder.md).</span></span>  
  
 <span data-ttu-id="dfc3a-418">Neste tutorial, salve o relatório em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-418">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="dfc3a-419">Se você não tiver acesso ao servidor de relatório, salve o relatório no computador.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-419">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-to-a-report-server"></a><span data-ttu-id="dfc3a-420">Para salvar o relatório em um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="dfc3a-420">To save the report to a report server</span></span>  
  
1.  <span data-ttu-id="dfc3a-421">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-421">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="dfc3a-422">Clique em **Sites e Servidores Recentes**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-422">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="dfc3a-423">Selecione ou digite o nome do servidor de relatório no qual você tem permissão para salvar relatórios.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-423">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="dfc3a-424">A mensagem "Conectando-se a um servidor de relatório" é exibida.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-424">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="dfc3a-425">Quando a conexão for estabelecida, você verá o conteúdo da pasta de relatório que o administrador do servidor de relatório especificou como o local de relatório padrão.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-425">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="dfc3a-426">Em **Nome**, substitua o nome padrão por **Resumo de Comparação de Vendas**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-426">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
5.  <span data-ttu-id="dfc3a-427">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-427">Click **Save**.</span></span>  
  
 <span data-ttu-id="dfc3a-428">O relatório será salvo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-428">The report is saved to the report server.</span></span> <span data-ttu-id="dfc3a-429">O nome do servidor de relatório ao qual você está conectado é exibido na barra de status da parte inferior da janela.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-429">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-to-your-computer"></a><span data-ttu-id="dfc3a-430">Para salvar o relatório no computador</span><span class="sxs-lookup"><span data-stu-id="dfc3a-430">To save the report to your computer</span></span>  
  
1.  <span data-ttu-id="dfc3a-431">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-431">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="dfc3a-432">Clique em **Área de Trabalho**, **Meus Documentos**ou **Meu Computador**e, em seguida, navegue até a pasta na qual você deseja salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-432">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="dfc3a-433">Em **Nome**, substitua o nome padrão por **Resumo de Comparação de Vendas**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-433">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
4.  <span data-ttu-id="dfc3a-434">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dfc3a-434">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc3a-435">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dfc3a-435">See Also</span></span>  
 <span data-ttu-id="dfc3a-436">[Expressões &#40;Construtor de Relatórios e SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dfc3a-436">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dfc3a-437">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dfc3a-437">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dfc3a-438">[Indicadores &#40;Construtor de Relatórios e SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dfc3a-438">[Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dfc3a-439">[Imagens, caixas de texto, retângulos e linhas &#40;Construtor de Relatórios e SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dfc3a-439">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dfc3a-440">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dfc3a-440">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="dfc3a-441">Adicionar dados a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dfc3a-441">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
