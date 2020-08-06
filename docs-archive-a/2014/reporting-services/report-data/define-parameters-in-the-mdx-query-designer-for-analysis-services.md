---
title: Definir parâmetros no designer de consulta MDX para Analysis Services (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- parameters [Reporting Services], MDX
- Multidimensional Expressions [Reporting Services]
- Data Mining Prediction [Reporting Services]
- MDX [Reporting Services], defining parameters
- DMX [Reporting Services]
ms.assetid: 4ad1e5bc-f510-4752-b4f6-589e55317a90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6b2b05fc0122eb25a7a0799f7b47b1b99486a28c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686090"
---
# <a name="define-parameters-in-the-mdx-query-designer-for-analysis-services-report-builder-and-ssrs"></a><span data-ttu-id="6f7a4-102">Definir parâmetros no Designer de Consulta MDX do Analysis Services (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="6f7a4-102">Define Parameters in the MDX Query Designer for Analysis Services (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6f7a4-103">Para parametrizar uma consulta MDX referente a uma fonte de dados do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , é necessário adicionar um parâmetro de consulta à consulta.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-103">To parameterize an MDX query for an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, you must add a query parameter to the query.</span></span> <span data-ttu-id="6f7a4-104">No designer de consulta MDX, você pode adicionar um parâmetro de consulta nos modos de Design e de Consulta especificando um filtro.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-104">In the MDX query designer, you can add a query parameter in both Design mode and Query mode by specifying a filter.</span></span> <span data-ttu-id="6f7a4-105">Depois de definir a consulta com um parâmetro de consulta, o Reporting Services cria automaticamente um parâmetro de relatório e um conjunto de dados para fornecer a lista de valores válidos.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-105">After you define the query with a query parameter, Reporting Services automatically creates a report parameter and a dataset to provide the list of valid values.</span></span> <span data-ttu-id="6f7a4-106">Dessa forma, o usuário pode especificar um valor que é passado diretamente para a consulta.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-106">This enables a user to specify a value that is passed directly to the query.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-define-a-query-parameter-in-mdx-in-design-mode"></a><span data-ttu-id="6f7a4-107">Para definir um parâmetro de consulta em MDX no modo de Design</span><span class="sxs-lookup"><span data-stu-id="6f7a4-107">To define a query parameter in MDX in Design mode</span></span>

1.  <span data-ttu-id="6f7a4-108">No painel de dados do relatório, clique com o botão direito do mouse em um conjunto de dados criado com base em um tipo de fonte de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] e clique em **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-108">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="6f7a4-109">O designer de consulta MDX abre no modo de Design.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-109">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="6f7a4-110">Arraste uma dimensão até a área de filtro e solte-a na primeira célula da coluna **Dimensão** .</span><span class="sxs-lookup"><span data-stu-id="6f7a4-110">Drag a dimension to the filter area and drop it on the first cell in the **Dimension** column.</span></span>

3.  <span data-ttu-id="6f7a4-111">Na coluna **Hierarquia** , escolha um valor na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-111">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

4.  <span data-ttu-id="6f7a4-112">Na coluna **Operador** , escolha um operador na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-112">In the **Operator** column, choose an operator for the drop-down list.</span></span>

5.  <span data-ttu-id="6f7a4-113">Na coluna **Expressão de Filtro** , selecione valores individuais na lista suspensa ou clique no membro **Todos** para escolher todos os valores.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-113">In the **Filter Expression** column, select individual values from the drop-down list, or click the **All** member to choose all values.</span></span>

6.  <span data-ttu-id="6f7a4-114">Na coluna **Parâmetros** , marque a caixa de seleção para criar um parâmetro de relatório.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-114">In the **Parameters** column, select the check box to create a report parameter.</span></span>

7.  <span data-ttu-id="6f7a4-115">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-115">Click **Run**.</span></span>

     <span data-ttu-id="6f7a4-116">Depois de executar a consulta, clique em **Design** , na barra de ferramentas, para alternar para o modo de Consulta e exibir a consulta MDX que foi criada.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-116">After you run the query, click **Design** on the toolbar to toggle to Query mode to view the MDX query that was created.</span></span> <span data-ttu-id="6f7a4-117">Não altere o texto da consulta no modo de Consulta se deseja continuar usando o modo de Design para desenvolver a consulta.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-117">Do not change the query text in Query mode if you want to continue to use Design mode to develop the query.</span></span> <span data-ttu-id="6f7a4-118">Clique em **Design** para voltar ao modo de Design.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-118">Click **Design** to toggle back to Design mode.</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="6f7a4-119">No painel de dados do relatório, expanda o nó Parâmetros para exibir o parâmetro de relatório que foi criado automaticamente para o filtro.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-119">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="6f7a4-120">Para exibir o conjunto de dados que fornece os valores disponíveis para o parâmetro de relatório, clique com o botão direito do mouse em qualquer área em branco do painel de dados do relatório e clique em **Mostrar Conjuntos de Dados Ocultos**.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-120">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="6f7a4-121">O painel de dados do relatório exibe todos os conjuntos de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-121">The Report Data pane displays all datasets in the report.</span></span>

### <a name="to-define-a-query-parameter-in-mdx-in-query-mode"></a><span data-ttu-id="6f7a4-122">Para definir um parâmetro de consulta em MDX no modo de Consulta</span><span class="sxs-lookup"><span data-stu-id="6f7a4-122">To define a query parameter in MDX in Query mode</span></span>

1.  <span data-ttu-id="6f7a4-123">No painel de dados do relatório, clique com o botão direito do mouse em um conjunto de dados criado com base em um tipo de fonte de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] e clique em **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-123">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="6f7a4-124">O designer de consulta MDX abre no modo de Design.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-124">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="6f7a4-125">Na barra de ferramentas, clique em **Design** para alternar para o modo de Consulta.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-125">On the toolbar, click **Design** to toggle to Query mode.</span></span>

3.  <span data-ttu-id="6f7a4-126">Na barra de ferramentas do designer de consultas MDX, clique em **Parâmetros de Consulta** (![Ícone da caixa de diálogo Parâmetros de Consulta](../../analysis-services/media/iconqueryparameter.gif "Ícone da caixa de diálogo Parâmetros de Consulta")).</span><span class="sxs-lookup"><span data-stu-id="6f7a4-126">On the MDX query designer toolbar, click **Query Parameters** (![Icon for the Query Parameters dialog box](../../analysis-services/media/iconqueryparameter.gif "Icon for the Query Parameters dialog box")).</span></span> <span data-ttu-id="6f7a4-127">A caixa de diálogo Parâmetros de Consulta é exibida.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-127">The Query Parameters dialog box opens.</span></span>

4.  <span data-ttu-id="6f7a4-128">Na coluna **parâmetro** , clique em **\<Enter Parameter>** e digite o nome de um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-128">In the **Parameter** column, click **\<Enter Parameter>**, and then type the name of a parameter.</span></span>

5.  <span data-ttu-id="6f7a4-129">Na coluna **Dimensão** , escolha um valor na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-129">In the **Dimension** column, choose a value from the drop-down list.</span></span>

6.  <span data-ttu-id="6f7a4-130">Na coluna **Hierarquia** , escolha um valor na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-130">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

7.  <span data-ttu-id="6f7a4-131">Na coluna **Vários valores** , marque a caixa de seleção para criar um parâmetro de vários valores.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-131">In the **Multiple values** column, select the check box to create a multivalue parameter.</span></span>

8.  <span data-ttu-id="6f7a4-132">Na coluna **Padrão** , selecione um único valor ou vários valores na lista suspensa, conforme sua escolha na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-132">In the **Default** column, from the drop-down list, select a single value or multiple values depending on your choice in step 5.</span></span>

9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

10. <span data-ttu-id="6f7a4-133">Na barra de ferramentas do designer de consulta, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-133">On the query designer toolbar, click **Run**.</span></span>

11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="6f7a4-134">No painel de dados do relatório, expanda o nó Parâmetros para exibir o parâmetro de relatório que foi criado automaticamente para o filtro.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-134">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="6f7a4-135">Para exibir o conjunto de dados que fornece os valores disponíveis para o parâmetro de relatório, clique com o botão direito do mouse em qualquer área em branco do painel de dados do relatório e clique em **Mostrar Conjuntos de Dados Ocultos**.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-135">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="6f7a4-136">O painel de dados do relatório exibe todos os conjuntos de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="6f7a4-136">The Report Data pane displays all datasets in the report.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f7a4-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f7a4-137">See Also</span></span>
 <span data-ttu-id="6f7a4-138">[Analysis Services tipo de conexão para MDX &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services interface do usuário do designer de consulta MDX](analysis-services-mdx-query-designer-user-interface.md)</span><span class="sxs-lookup"><span data-stu-id="6f7a4-138">[Analysis Services Connection Type for MDX &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services MDX Query Designer User Interface](analysis-services-mdx-query-designer-user-interface.md)</span></span>


