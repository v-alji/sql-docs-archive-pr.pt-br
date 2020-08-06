---
title: 'Tutorial: Formatar texto (Construtor de Relatórios) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 67d8513e-8a70-464b-b87f-e91d010cfd82
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c96b500f8aa30b77c78f75ccd1342398fd44eb2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684022"
---
# <a name="tutorial-format-text-report-builder"></a><span data-ttu-id="8c8e2-102">Tutorial: Formatar texto (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="8c8e2-102">Tutorial: Format Text (Report Builder)</span></span>
  <span data-ttu-id="8c8e2-103">Neste tutorial, você pode praticar a formatação de texto de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-103">In this tutorial, you can practice formatting text in various ways.</span></span> <span data-ttu-id="8c8e2-104">Depois de configurar o relatório em branco com a fonte de dados e o conjunto de dados, é possível escolher e selecionar as etapas que você deseja explorar.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-104">After you set up the blank report with the data source and dataset, you can pick and choose the steps that you want to explore.</span></span>  
  
 <span data-ttu-id="8c8e2-105">A ilustração a seguir mostra um relatório semelhante ao que você criará.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-105">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="8c8e2-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span><span class="sxs-lookup"><span data-stu-id="8c8e2-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span></span>  
  
 <span data-ttu-id="8c8e2-107">Em uma etapa, você comete um erro de propósito, para poder ver o porquê do erro.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-107">In one step, you make a mistake on purpose so you can see why it is a mistake.</span></span> <span data-ttu-id="8c8e2-108">Em seguida, você corrige o erro para obter o efeito desejado.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-108">Then you correct the mistake to achieve the desired effect.</span></span>  
  
 <span data-ttu-id="8c8e2-109">Uma versão aprimorada do relatório criado por você neste tutorial está disponível como um relatório de exemplo do Construtor de Relatórios da [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c8e2-109">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="8c8e2-110">Para obter mais informações sobre como baixar este relatório de exemplo e outros, consulte [Construtor de relatórios relatórios de exemplo](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="8c8e2-110">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="8c8e2-111">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="8c8e2-111">What You Will Learn</span></span>  
  
### <a name="set-up-the-report"></a><span data-ttu-id="8c8e2-112">Configurar o relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-112">Set Up the Report</span></span>  
 1. [<span data-ttu-id="8c8e2-113">Criar um relatório em branco com uma fonte de dados e um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="8c8e2-113">Create a Blank Report with a Data Source and Dataset</span></span>](#CreateReport)  
  
 2. [<span data-ttu-id="8c8e2-114">Adicionar um campo à superfície de design do relatório (incorretamente e, em seguida, corretamente)</span><span class="sxs-lookup"><span data-stu-id="8c8e2-114">Add a Field to the Report Design Surface (Incorrectly, then Correctly)</span></span>](#AddField)  
  
 3. [<span data-ttu-id="8c8e2-115">Adicionar uma tabela ao Design Surface do relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-115">Add a Table to the Report Design Surface</span></span>](#AddTable)  
  
### <a name="pick-and-choose"></a><span data-ttu-id="8c8e2-116">Escolher e selecionar</span><span class="sxs-lookup"><span data-stu-id="8c8e2-116">Pick and Choose</span></span>  
 [<span data-ttu-id="8c8e2-117">Adicionar um hiperlink ao relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-117">Add a Hyperlink to the Report</span></span>](#AddHyperlink)  
  
 [<span data-ttu-id="8c8e2-118">Girar texto no relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-118">Rotate Text in the Report</span></span>](#RotateText)  
  
 [<span data-ttu-id="8c8e2-119">Exibindo texto com formatação HTML</span><span class="sxs-lookup"><span data-stu-id="8c8e2-119">Displaying Text with HTML Formatting</span></span>](#FormatHTML)  
  
 [<span data-ttu-id="8c8e2-120">Formatar moeda</span><span class="sxs-lookup"><span data-stu-id="8c8e2-120">Format Currency</span></span>](#FormatCurrency)  
  
 [<span data-ttu-id="8c8e2-121">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-121">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="8c8e2-122">Tempo estimado para concluir este tutorial: 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c8e2-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c8e2-123">Requirements</span></span>  
 <span data-ttu-id="8c8e2-124">Para obter mais informações sobre os requisitos, consulte [Pré-requisitos para tutoriais &#40;Construtor de Relatórios&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="8c8e2-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="create-a-blank-report-with-a-data-source-and-dataset"></a><a name="CreateReport"></a><span data-ttu-id="8c8e2-125">Criar um relatório em branco com uma fonte de dados e um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="8c8e2-125">Create a Blank Report with a Data Source and Dataset</span></span>  
  
#### <a name="to-create-a-blank-report"></a><span data-ttu-id="8c8e2-126">Para criar um relatório em branco</span><span class="sxs-lookup"><span data-stu-id="8c8e2-126">To create a blank report</span></span>  
  
1.  <span data-ttu-id="8c8e2-127">Clique em **Iniciar**, aponte para **programas**, aponte para [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Construtor de relatórios**e, em seguida, clique em **Construtor de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-127">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8c8e2-128">A caixa de diálogo **Guia de Introdução** deve ser exibida.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-128">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="8c8e2-129">Se ela não for exibida, usando o botão do Construtor de Relatórios, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-129">If it does not, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="8c8e2-130">No painel esquerdo da caixa de diálogo **Guia de Introdução** , verifique se **Novo Relatório** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-130">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="8c8e2-131">No painel direito, clique em **Relatório em Branco**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-131">In the right pane, click **Blank Report**.</span></span>  
  
#### <a name="to-create-a-data-source"></a><span data-ttu-id="8c8e2-132">Para criar uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="8c8e2-132">To create a data source</span></span>  
  
1.  <span data-ttu-id="8c8e2-133">No painel dados do relatório, clique em **novo**e em **fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-133">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>  
  
2.  <span data-ttu-id="8c8e2-134">Na caixa **Nome** , digite: **TextDataSource**</span><span class="sxs-lookup"><span data-stu-id="8c8e2-134">In the **Name** box, type: **TextDataSource**</span></span>  
  
3.  <span data-ttu-id="8c8e2-135">Clique em **Usar uma conexão inserida no meu relatório**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-135">Click **Use a connection embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="8c8e2-136">Verifique se o tipo de conexão é Microsoft SQL Server e, em seguida, na caixa **cadeia de conexão** , digite: \*\*fonte de dados = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="8c8e2-136">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8c8e2-137">A expressão \<servername>, por exemplo, Report001, especifica um computador no qual há uma instância do Mecanismo de Banco de Dados do SQL Server instalada.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-137">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="8c8e2-138">Este tutorial não precisa de dados específicos; ele só precisa de uma conexão com um banco de dados [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8c8e2-138">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="8c8e2-139">Se você já tiver uma conexão de fonte de dados listada em **Conexões de Fonte de Dados**, será possível selecioná-la e ir para o próximo procedimento, “Para criar uma fonte de dados”.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-139">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to the next procedure, "To create a dataset."</span></span> <span data-ttu-id="8c8e2-140">Para obter mais informações, consulte [Formas alternativas de obter uma conexão de dados &#40;Construtor de Relatórios&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="8c8e2-140">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-create-a-dataset"></a><span data-ttu-id="8c8e2-141">Para criar um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="8c8e2-141">To create a dataset</span></span>  
  
1.  <span data-ttu-id="8c8e2-142">No painel de dados do relatório, clique em **Novo**e em **Conjunto de Dados**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-142">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>  
  
2.  <span data-ttu-id="8c8e2-143">Verifique se a fonte de dados é **TextDataSource**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-143">Verify that the data source is **TextDataSource**.</span></span>  
  
3.  <span data-ttu-id="8c8e2-144">Na caixa **Nome** , digite: **TextDataset.**</span><span class="sxs-lookup"><span data-stu-id="8c8e2-144">In the **Name** box, type: **TextDataset.**</span></span>  
  
4.  <span data-ttu-id="8c8e2-145">Verifique se o tipo de consulta **Texto** está selecionado e, em seguida, clique em **Designer de Consulta**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-145">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>  
  
5.  <span data-ttu-id="8c8e2-146">Clique em **Editar como Texto**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-146">Click **Edit as Text**.</span></span>  
  
6.  <span data-ttu-id="8c8e2-147">Cole a seguinte consulta no painel de consulta:</span><span class="sxs-lookup"><span data-stu-id="8c8e2-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    ```  
  
7.  <span data-ttu-id="8c8e2-148">Clique em Executar (**!**) para executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-148">Click Run (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="8c8e2-149">Os resultados da consulta são os dados disponíveis a serem exibidos no relatório.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-149">The query results are the data available to display in your report.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="add-a-field-to-the-report-design-surface"></a><a name="AddField"></a><span data-ttu-id="8c8e2-150">Adicionar um campo ao Design Surface do relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-150">Add a Field to the Report Design Surface</span></span>  
 <span data-ttu-id="8c8e2-151">Se você quiser que um campo do conjunto de dados seja exibido em um relatório, seu primeiro impulso poderá ser de arrastá-lo diretamente para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-151">If you want a field from your dataset to appear in a report, your first impulse may be to drag it directly to the design surface.</span></span> <span data-ttu-id="8c8e2-152">Este exercício aponta por que isso não funciona e o que fazer em vez disso.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-152">This exercise points out why that doesn't work and what to do instead.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-wrong-result"></a><span data-ttu-id="8c8e2-153">Para adicionar um campo ao relatório (e obter o resultado errado)</span><span class="sxs-lookup"><span data-stu-id="8c8e2-153">To add a field to the report (and get the wrong result)</span></span>  
  
1.  <span data-ttu-id="8c8e2-154">Arraste o campo **FullName** do painel Dados do Relatório até a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-154">Drag the **FullName** field from the Report Data pane to the design surface.</span></span>  
  
     <span data-ttu-id="8c8e2-155">O Construtor de Relatórios cria uma caixa de texto com uma expressão, representada como \<Expr>.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-155">Report Builder creates a text box with an expression in it, represented as \<Expr>.</span></span>  
  
2.  <span data-ttu-id="8c8e2-156">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-156">Click **Run**.</span></span>  
  
     <span data-ttu-id="8c8e2-157">Observe que há apenas um registro, **Fernando Ross**, que é, em ordem alfabética, o primeiro registro na consulta.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-157">Note that there is just one record, **Fernando Ross**, which is alphabetically the first record in the query.</span></span> <span data-ttu-id="8c8e2-158">O campo não se repete para mostrar os outros registros nesse campo.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-158">The field does not repeat to show the other records in that field.</span></span>  
  
3.  <span data-ttu-id="8c8e2-159">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-159">Click **Design** to return to design view.</span></span>  
  
4.  <span data-ttu-id="8c8e2-160">Selecione a expressão \<Expr> na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-160">Select the expression \<Expr> in the text box.</span></span>  
  
5.  <span data-ttu-id="8c8e2-161">No painel Propriedades, na propriedade **Valor** , você vê o seguinte (se o painel Propriedades não estiver visível, na guia **Exibir** , marque **Propriedades**):</span><span class="sxs-lookup"><span data-stu-id="8c8e2-161">In the Properties pane, for the **Value** property, you see the following (if you don't see the Properties pane, on the **View** tab, check **Properties**):</span></span>  
  
    ```  
    =First(Fields!FullName.Value, "TextDataSet")  
    ```  
  
     <span data-ttu-id="8c8e2-162">A função `First` foi projetada para recuperar apenas o primeiro valor em um campo, e foi isso o que ela fez.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-162">The `First` function is designed to retrieve only the first value in a field, and that is what it has done.</span></span>  
  
     <span data-ttu-id="8c8e2-163">Arrastar o campo diretamente para a superfície de design criou uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-163">Dragging the field directly to the design surface created a text box.</span></span> <span data-ttu-id="8c8e2-164">Por si, as caixas de texto não são regiões de dados, logo, elas não exibem dados de um conjunto de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-164">Text boxes by themselves are not data regions, so they do not display data from a report dataset.</span></span> <span data-ttu-id="8c8e2-165">As caixas de texto em regiões de dados, como tabelas, matrizes e listas, exibem dados.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-165">Text boxes in data regions, such as tables, matrices, and lists, do display data.</span></span>  
  
6.  <span data-ttu-id="8c8e2-166">Selecione a caixa de texto (se a expressão estiver selecionada, pressione ESC para marcar a caixa de texto) e pressione a tecla DEL.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-166">Select the text box (if you have the expression selected, press ESC to select the text box), and press the DELETE key.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-right-result"></a><span data-ttu-id="8c8e2-167">Para adicionar um campo ao relatório (e obter o resultado certo)</span><span class="sxs-lookup"><span data-stu-id="8c8e2-167">To add a field to the report (and get the right result)</span></span>  
  
1.  <span data-ttu-id="8c8e2-168">Na guia **Inserir** da faixa de opções, na área **Regiões de Dados** , clique em **Lista**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-168">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List**.</span></span> <span data-ttu-id="8c8e2-169">Clique na superfície de design e, em seguida, arraste-a para criar uma caixa com aproximadamente 5,08 centímetros de largura e 2,54 centímetros de altura.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-169">Click the design surface, and then drag to create a box that about two inches wide and one inch tall.</span></span>  
  
2.  <span data-ttu-id="8c8e2-170">Arraste o campo **FullName** do painel Dados do Relatório até a caixa de listagem.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-170">Drag the **FullName** field from the Report Data pane to the list box.</span></span>  
  
     <span data-ttu-id="8c8e2-171">Desta vez, o Construtor de Relatórios cria uma caixa de texto com a expressão `[FullName]` .</span><span class="sxs-lookup"><span data-stu-id="8c8e2-171">This time Report Builder creates a text box with the expression `[FullName]` in it.</span></span>  
  
3.  <span data-ttu-id="8c8e2-172">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-172">Click **Run**.</span></span>  
  
     <span data-ttu-id="8c8e2-173">Observe que, desta vez, a caixa se repete para mostrar todos os registros na consulta.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-173">Note that this time the box repeats to show all the records in the query.</span></span>  
  
4.  <span data-ttu-id="8c8e2-174">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-174">Click **Design** to return to design view.</span></span>  
  
5.  <span data-ttu-id="8c8e2-175">Selecione a expressão na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-175">Select the expression in the text box.</span></span>  
  
6.  <span data-ttu-id="8c8e2-176">No painel Propriedades, na propriedade **Valor** , o seguinte é exibido:</span><span class="sxs-lookup"><span data-stu-id="8c8e2-176">In the Properties pane, for the **Value** property, you see the following:</span></span>  
  
    ```  
    =Fields!FullName.Value  
    ```  
  
     <span data-ttu-id="8c8e2-177">Arrastando a caixa de texto até a região de dados da lista, você exibe os dados presentes no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-177">By dragging the text box to the list data region, you display the data that is in the dataset.</span></span>  
  
7.  <span data-ttu-id="8c8e2-178">Selecione a caixa de listagem e pressione a tecla DEL.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-178">Select the list box and press the DELETE key.</span></span>  
  
##  <a name="add-a-table-to-the-report-design-surface"></a><a name="AddTable"></a><span data-ttu-id="8c8e2-179">Adicionar uma tabela ao Design Surface do relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-179">Add a Table to the Report Design Surface</span></span>  
 <span data-ttu-id="8c8e2-180">Crie essa tabela para que você tenha um lugar para colocar hiperlinks e texto girado.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-180">Create this table so that you'll have a place to put hyperlinks and rotated text.</span></span>  
  
#### <a name="to-add-a-table-to-the-report"></a><span data-ttu-id="8c8e2-181">Para adicionar uma tabela ao relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-181">To add a table to the report</span></span>  
  
1.  <span data-ttu-id="8c8e2-182">No menu **Inserir** , clique em **tabela**e, em seguida, clique em **Assistente de tabela**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-182">On the **Insert** menu, click **Table**, and then click **Table Wizard**.</span></span>  
  
2.  <span data-ttu-id="8c8e2-183">Na página **escolher um conjunto** de dados do assistente de nova tabela ou matriz, clique em **escolher um conjunto de dados existente neste relatório ou em um conjunto**de dados compartilhado e clique em **TextDataset (neste relatório)** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-183">On the **Choose a dataset** page of the New Table or Matrix wizard, click **Choose an existing dataset in this report or a shared dataset**, and click **TextDataset (in this Report)**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="8c8e2-184">Na página **organizar campos** , arraste os campos **território**, **linkText**e **produto** para grupos de **linhas**, arraste o campo **vendas** para **valores**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-184">On the **Arrange fields** page, drag the **Territory**, **LinkText**, and **Product** fields to **Row groups**, drag the **Sales** field to **Values**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="8c8e2-185">Na página **escolher o layout** , desmarque a caixa de seleção **expandir/recolher grupos** para que você possa ver a tabela inteira e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-185">On the **Choose the layout** page, clear the **Expand/collapse groups** check box so you can see the whole table, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="8c8e2-186">Na página **escolher um estilo** , clique em **Tablet**e em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-186">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="8c8e2-187">Arraste a tabela para que ela esteja abaixo do bloco de título.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-187">Drag the table so it is below the title block.</span></span>  
  
7.  <span data-ttu-id="8c8e2-188">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-188">Click **Run**.</span></span>  
  
     <span data-ttu-id="8c8e2-189">A tabela parece correta, mas tem duas linhas totais.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-189">The table looks OK, but it has two Total rows.</span></span> <span data-ttu-id="8c8e2-190">O campo **linkText** não precisa de uma linha total.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-190">The **LinkText** field doesn't need a Total row.</span></span>  
  
8.  <span data-ttu-id="8c8e2-191">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-191">Click **Design** to return to design view.</span></span>  
  
9. <span data-ttu-id="8c8e2-192">Clique com o botão direito do mouse na caixa de texto que contém `[LinkText]` e clique em **dividir células**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-192">Right-click the text box that contains `[LinkText]`, and click **Split Cells**.</span></span>  
  
10. <span data-ttu-id="8c8e2-193">Selecione a célula vazia abaixo da `[LinkText]` célula e mantenha pressionada a tecla Shift e selecione as duas células à direita: a célula **total** na coluna **Product** e a `[Sum(Sales)]` célula na coluna **Sales** .</span><span class="sxs-lookup"><span data-stu-id="8c8e2-193">Select the empty cell below the `[LinkText]` cell, and then hold down the SHIFT key and select the two cells to its right: the **Total** cell in the **Product** column and the `[Sum(Sales)]` cell in the **Sales** column.</span></span>  
  
11. <span data-ttu-id="8c8e2-194">Com essas três células selecionadas, clique com o botão direito do mouse em uma dessas células e clique em **Excluir linha**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-194">With those three cells selected, right-click one of those cells and click **Delete Row**.</span></span>  
  
12. <span data-ttu-id="8c8e2-195">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-195">Click **Run**.</span></span>  
  
##  <a name="add-a-hyperlink-to-the-report"></a><a name="AddHyperlink"></a><span data-ttu-id="8c8e2-196">Adicionar um hiperlink ao relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-196">Add a Hyperlink to the Report</span></span>  
 <span data-ttu-id="8c8e2-197">Nesta seção, você adiciona um hiperlink ao texto na tabela da seção anterior.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-197">In this section, you add a hyperlink to text in the table from the previous section.</span></span>  
  
#### <a name="to-add-a-hyperlink-to-the-report"></a><span data-ttu-id="8c8e2-198">Para adicionar um hiperlink ao relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-198">To add a hyperlink to the report</span></span>  
  
1.  <span data-ttu-id="8c8e2-199">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-199">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="8c8e2-200">Clique com o botão direito do mouse na célula que contém `[LinkText]`e clique em **Propriedades da Caixa de Texto**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-200">Right-click in the cell containing `[LinkText]`, and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="8c8e2-201">Na caixa **Propriedades da caixa de texto** , clique em **ação**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-201">In the **Text Box Properties** box, click **Action**.</span></span>  
  
4.  <span data-ttu-id="8c8e2-202">Clique em **ir para URL**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-202">Click **Go to URL**.</span></span>  
  
5.  <span data-ttu-id="8c8e2-203">Na caixa **selecionar URL** , clique em **[url]** e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-203">In the **Select URL** box, click **[URL]**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="8c8e2-204">Observe que o texto não parece diferente.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-204">Note that the text does not look any different.</span></span> <span data-ttu-id="8c8e2-205">Você precisa fazê-lo parecer um texto de link.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-205">You need to make it look like link text.</span></span>  
  
7.  <span data-ttu-id="8c8e2-206">Selecione `[LinkText]`.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-206">Select `[LinkText]`.</span></span>  
  
8.  <span data-ttu-id="8c8e2-207">Na seção **fonte** da guia **início** , clique no botão **sublinhado** e, em seguida, clique na seta suspensa ao lado do botão **cor** e clique em **azul**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-207">In the **Font** section of the **Home** tab, click the **Underline** button, and then click the drop-down arrow next to the **Color** button, and click **Blue**.</span></span>  
  
9. <span data-ttu-id="8c8e2-208">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-208">Click **Run**.</span></span>  
  
     <span data-ttu-id="8c8e2-209">O texto agora se parece com um link.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-209">The text now looks like a link.</span></span>  
  
10. <span data-ttu-id="8c8e2-210">Clique em um link.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-210">Click a link.</span></span> <span data-ttu-id="8c8e2-211">Se o computador estiver conectado à Internet, um navegador abrirá um tópico da Ajuda do Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-211">If the computer is connected to the Internet, a browser will open to a Report Builder Help topic.</span></span>  
  
##  <a name="rotate-text-in-the-report"></a><a name="RotateText"></a><span data-ttu-id="8c8e2-212">Girar texto no relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-212">Rotate Text in the Report</span></span>  
 <span data-ttu-id="8c8e2-213">Nesta seção, você gira um texto na tabela das seções anteriores.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-213">In this section, you rotate some of the text in the table from the previous sections.</span></span>  
  
#### <a name="to-rotate-text"></a><span data-ttu-id="8c8e2-214">Para girar texto</span><span class="sxs-lookup"><span data-stu-id="8c8e2-214">To rotate text</span></span>  
  
1.  <span data-ttu-id="8c8e2-215">Clique em **Design** para retornar à exibição de design.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-215">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="8c8e2-216">Clique na célula que contém `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="8c8e2-216">Click in the cell containing `[Territory].`</span></span>  
  
3.  <span data-ttu-id="8c8e2-217">Na guia **Início** , na seção **Fonte** , clique no botão **Negrito** .</span><span class="sxs-lookup"><span data-stu-id="8c8e2-217">On the **Home** tab in the **Font** section, click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="8c8e2-218">Se o painel Propriedades não estiver aberto, na guia **Exibir** , marque a caixa de seleção **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="8c8e2-218">If the Properties pane is not open, on the **View** tab, select the **Properties** check box.</span></span>  
  
5.  <span data-ttu-id="8c8e2-219">Localize a propriedade WritingMode no painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-219">Locate the WritingMode property in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8c8e2-220">Quando as propriedades no painel Propriedades estiverem organizadas em categorias, WritingMode estará na categoria **Localização** .</span><span class="sxs-lookup"><span data-stu-id="8c8e2-220">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span> <span data-ttu-id="8c8e2-221">Verifique se você selecionou a célula, e não o texto</span><span class="sxs-lookup"><span data-stu-id="8c8e2-221">Be sure you have selected the cell and not the text.</span></span> <span data-ttu-id="8c8e2-222">WritingMode é uma propriedade da caixa de texto, não do texto.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-222">WritingMode is a property of the text box, not of the text.</span></span>  
  
6.  <span data-ttu-id="8c8e2-223">Na caixa de listagem, clique em **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-223">In the list box, click **Rotate270**.</span></span>  
  
7.  <span data-ttu-id="8c8e2-224">Na guia **início** da seção **parágrafo** , **clique nos botões central e** **Centro** para localizar o texto no centro da célula, verticalmente e horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-224">On the **Home** tab in the **Paragraph** section, click the **Middle** and **Center** buttons to locate the text in the center of the cell both vertically and horizontally.</span></span>  
  
8.  <span data-ttu-id="8c8e2-225">Clique em Executar (**!**).</span><span class="sxs-lookup"><span data-stu-id="8c8e2-225">Click Run (**!**).</span></span>  
  
 <span data-ttu-id="8c8e2-226">Agora o texto na célula `[Territory]` é executado verticalmente da parte inferior para a parte superior das células.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-226">Now the text in the `[Territory]` cell runs vertically from the bottom to the top of the cells.</span></span>  
  
##  <a name="displaying-text-with-html-formatting"></a><a name="FormatHTML"></a><span data-ttu-id="8c8e2-227">Exibindo texto com formatação HTML</span><span class="sxs-lookup"><span data-stu-id="8c8e2-227">Displaying Text with HTML Formatting</span></span>  
  
#### <a name="to-display-text-formatted-as-html"></a><span data-ttu-id="8c8e2-228">Para exibir texto formatado como HTML</span><span class="sxs-lookup"><span data-stu-id="8c8e2-228">To display text formatted as HTML</span></span>  
  
1.  <span data-ttu-id="8c8e2-229">Clique em **Design** a fim de alternar para a exibição de design.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-229">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="8c8e2-230">Na guia **Inserir** , clique em **Caixa de Texto**e, na superfície de design, clique e arraste para criar uma caixa de texto abaixo da tabela, com cerca de 10 centímetros de largura e 8 centímetros de altura.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-230">On the **Insert** tab, click **Text Box**, and then on the design surface, click and drag to create a text box under the table, about four inches wide and three inches tall.</span></span>  
  
3.  <span data-ttu-id="8c8e2-231">Copiar esse texto e cole-o na caixa de texto:</span><span class="sxs-lookup"><span data-stu-id="8c8e2-231">Copy this text and paste it into the text box:</span></span>  
  
    ```  
    <h4>Limitations of cascading style sheet attributes</h4>  
          <p>Only a basic set of <b>cascading style sheet (CSS)</b> attributes are defined:</p>  
          <ul><li>  
              text-align, text-indent  
            </li><li>  
              font-family, font-size  
            </li><li>  
              color  
            </li><li>  
              padding, padding-bottom, padding-top, padding-right, padding-left  
            </li><li>  
              font-weight  
            </li></ul>  
    ```  
  
4.  <span data-ttu-id="8c8e2-232">Selecione todo o texto na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-232">Select all of the text in the text box.</span></span>  
  
     <span data-ttu-id="8c8e2-233">Essa é uma propriedade do texto, não da caixa de texto, portanto, em uma caixa de texto você pode ter uma mistura de texto sem formatação e texto que usa marcas HTML como estilos.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-233">This is a property of the text, not the text box, so in one text box you could have a mixture of plain text and text that uses HTML tags as styles.</span></span>  
  
5.  <span data-ttu-id="8c8e2-234">Clique com o botão direito do mouse em todo o texto selecionado e clique em **Propriedades do Texto**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-234">Right-click all of the selected text and click **Text Properties**.</span></span>  
  
6.  <span data-ttu-id="8c8e2-235">Na página **geral** , em **tipo de marcação**, clique em **HTML-interpretar marcas HTML como estilos**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-235">On the **General** page, under **Markup type**, click **HTML - Interpret HTML tags as styles**.</span></span>  
  
7.  <span data-ttu-id="8c8e2-236">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-236">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="8c8e2-237">Clique em Executar (**!**) para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-237">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="8c8e2-238">O texto na caixa de texto é exibido como um título, um parágrafo e uma lista com marcadores.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-238">The text in the text box is displayed as a heading, paragraph, and bulleted list.</span></span>  
  
##  <a name="format-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="8c8e2-239">Formatar moeda</span><span class="sxs-lookup"><span data-stu-id="8c8e2-239">Format Currency</span></span>  
  
#### <a name="to-format-numbers-as-currency"></a><span data-ttu-id="8c8e2-240">Para formatar números como moeda</span><span class="sxs-lookup"><span data-stu-id="8c8e2-240">To format numbers as currency</span></span>  
  
1.  <span data-ttu-id="8c8e2-241">Clique em **Design** a fim de alternar para a exibição de design.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-241">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="8c8e2-242">Clique na célula da tabela superior que contenha `[Sum(Sales)]`, mantenha a tecla SHIFT pressionada e clique na célula da tabela inferior que contenha `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-242">Click the top table cell that contains `[Sum(Sales)]`, hold down the SHIFT key, and click the bottom table cell that contains `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="8c8e2-243">Na guia **Início** , no grupo **Número** , clique no botão **Moeda** .</span><span class="sxs-lookup"><span data-stu-id="8c8e2-243">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>  
  
4.  <span data-ttu-id="8c8e2-244">Adicional Na guia **início** , no grupo **número** , clique no botão **estilos de espaço reservado** e clique em **valores de exemplo** para ver como os números serão formatados.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-244">(Optional) On the **Home** tab, in the **Number** group, click the **Placeholder Styles** button and click **Sample Values** to see how the numbers will be formatted.</span></span>  
  
5.  <span data-ttu-id="8c8e2-245">(Opcional) Na guia **Início** , no grupo **Número** , clique no botão **Diminuir Decimais** duas vezes para exibir valores em dólares sem centavos.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-245">(Optional) On the **Home** tab, in the **Number** group, click the **Decrease Decimals** button twice to display dollar figures with no cents.</span></span>  
  
6.  <span data-ttu-id="8c8e2-246">Clique em Executar (**!**) para visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-246">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="8c8e2-247">O relatório agora exibe dados formatados e é mais fácil de ler.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-247">The report now displays formatted data and is easier to read.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="8c8e2-248">Salvar o relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-248">Save the Report</span></span>  
 <span data-ttu-id="8c8e2-249">É possível salvar relatórios em um servidor de relatório, em uma biblioteca do SharePoint ou no computador.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-249">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="8c8e2-250">Neste tutorial, salve o relatório em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-250">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="8c8e2-251">Se você não tiver acesso ao servidor de relatório, salve o relatório no computador.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-251">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="8c8e2-252">Para salvar o relatório em um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="8c8e2-252">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="8c8e2-253">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-253">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="8c8e2-254">Clique em **Sites e Servidores Recentes**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-254">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="8c8e2-255">Selecione ou digite o nome do servidor de relatório no qual você tem permissão para salvar relatórios.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-255">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="8c8e2-256">A mensagem "Conectando-se a um servidor de relatório" é exibida.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-256">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="8c8e2-257">Quando a conexão for concluída, você verá o conteúdo da pasta do relatório que o administrador do servidor de relatório especificou como o local padrão para relatórios.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-257">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="8c8e2-258">Em **Nome**, substitua o nome padrão por um nome de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-258">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
5.  <span data-ttu-id="8c8e2-259">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-259">Click **Save**.</span></span>  
  
 <span data-ttu-id="8c8e2-260">O relatório será salvo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-260">The report is saved to the report server.</span></span> <span data-ttu-id="8c8e2-261">O nome do servidor de relatório ao qual você está conectado é exibido na barra de status da parte inferior da janela.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-261">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="8c8e2-262">Para salvar o relatório no computador</span><span class="sxs-lookup"><span data-stu-id="8c8e2-262">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="8c8e2-263">No botão **Construtor de Relatórios** , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-263">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="8c8e2-264">Clique em **Área de Trabalho**, **Meus Documentos**ou **Meu Computador**e, em seguida, navegue até a pasta na qual você deseja salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-264">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="8c8e2-265">Em **Nome**, substitua o nome padrão por um nome de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-265">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
4.  <span data-ttu-id="8c8e2-266">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-266">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8c8e2-267">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="8c8e2-267">Next Steps</span></span>  
 <span data-ttu-id="8c8e2-268">Há várias maneiras de Formatar texto em Construtor de Relatórios [tutorial: Criando um relatório de formato livre &#40;Construtor de Relatórios&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) contém mais exemplos.</span><span class="sxs-lookup"><span data-stu-id="8c8e2-268">There are many ways to format text in Report Builder [Tutorial: Creating a Free Form Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) contains more examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c8e2-269">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8c8e2-269">See Also</span></span>  
 <span data-ttu-id="8c8e2-270">[TUTORIAIS &#40;Construtor de Relatórios&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="8c8e2-270">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="8c8e2-271">[Formatando itens de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8c8e2-271">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8c8e2-272">Construtor de Relatórios no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="8c8e2-272">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
