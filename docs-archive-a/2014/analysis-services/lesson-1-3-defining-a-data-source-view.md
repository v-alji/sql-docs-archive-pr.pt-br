---
title: Definindo uma exibição da fonte de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af00938a-5a06-4fae-b2fc-f3fb0ca3cea5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d59c5fbe5fd4a07596745447567a72499ddabd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568855"
---
# <a name="defining-a-data-source-view"></a><span data-ttu-id="9eb20-102">Definindo uma exibição da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="9eb20-102">Defining a Data Source View</span></span>
  <span data-ttu-id="9eb20-103">Depois de definir as fontes de dados que serão usadas em um projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , você normalmente define uma exibição da fonte de dados para o projeto.</span><span class="sxs-lookup"><span data-stu-id="9eb20-103">After you define the data sources that you will use in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, the next step is generally to define a data source view for the project.</span></span> <span data-ttu-id="9eb20-104">Uma exibição da fonte de dados é uma exibição unificada exclusiva dos metadados das tabelas e exibições especificadas que a fonte de dados define no projeto.</span><span class="sxs-lookup"><span data-stu-id="9eb20-104">A data source view is a single, unified view of the metadata from the specified tables and views that the data source defines in the project.</span></span> <span data-ttu-id="9eb20-105">Armazenar os metadados na exibição da fonte de dados permite que você trabalhe com os metadados durante o desenvolvimento sem ter uma conexão aberta com qualquer fonte de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="9eb20-105">Storing the metadata in the data source view enables you to work with the metadata during development without an open connection to any underlying data source.</span></span> <span data-ttu-id="9eb20-106">Para obter mais informações, consulte [Exibições de fontes de dados em modelos multidimensionais](multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="9eb20-106">For more information, see [Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="9eb20-107">Na tarefa a seguir, você define uma exibição da fonte de dados que inclui cinco tabelas da fonte de dados **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="9eb20-107">In the following task, you define a data source view that includes five tables from the **AdventureWorksDW2012** data source.</span></span>  
  
### <a name="to-define-a-new-data-source-view"></a><span data-ttu-id="9eb20-108">Para definir uma nova exibição da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="9eb20-108">To define a new data source view</span></span>  
  
1.  <span data-ttu-id="9eb20-109">No Gerenciador de Soluções (à direita da janela do Microsoft Visual Studio), clique com o botão direito do mouse em **Exibições da Fonte de Dados**e clique em **Nova Exibição da Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="9eb20-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Source Views**, and then click **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="9eb20-110">Na página **Bem-vindo ao Assistente de Exibição da Fonte de Dados** , clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="9eb20-110">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span> <span data-ttu-id="9eb20-111">A página **Selecionar uma Fonte de Dados** é exibida.</span><span class="sxs-lookup"><span data-stu-id="9eb20-111">The **Select a Data Source** page appears.</span></span>  
  
3.  <span data-ttu-id="9eb20-112">Em **Fontes de dados relacionais**, a fonte de dados **Adventure Works DW 2012** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="9eb20-112">Under **Relational data sources**, the **Adventure Works DW 2012** data source is selected.</span></span> <span data-ttu-id="9eb20-113">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9eb20-113">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9eb20-114">Para criar uma exibição de fonte de dados com base em várias fontes de dados, primeiro defina uma exibição da fonte de dados com base em uma única fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9eb20-114">To create a data source view that is based on multiple data sources, first define a data source view that is based on a single data source.</span></span> <span data-ttu-id="9eb20-115">Essa fonte de dados é, então, chamada a fonte de dados primária.</span><span class="sxs-lookup"><span data-stu-id="9eb20-115">This data source is then called the primary data source.</span></span> <span data-ttu-id="9eb20-116">Depois, você poderá adicionar tabelas e exibições de uma fonte de dados secundária.</span><span class="sxs-lookup"><span data-stu-id="9eb20-116">You can then add tables and views from a secondary data source.</span></span> <span data-ttu-id="9eb20-117">Ao projetar dimensões que contêm atributos baseados em tabelas relacionadas em várias fontes de dados, talvez seja necessário definir uma fonte de dados do [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] como a fonte de dados primária para usar suas funcionalidades de mecanismo de consulta distribuída.</span><span class="sxs-lookup"><span data-stu-id="9eb20-117">When designing dimensions that contain attributes based on related tables in multiple data sources, you might need to define a [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] data source as the primary data source to use its distributed query engine capabilities.</span></span>  
  
4.  <span data-ttu-id="9eb20-118">Na página **Selecionar Tabelas e Exibições** , selecione tabelas e exibições na lista de objetos disponíveis da fonte de dados selecionada.</span><span class="sxs-lookup"><span data-stu-id="9eb20-118">On the **Select Tables and Views** page, select tables and views from the list of objects that are available from the selected data source.</span></span> <span data-ttu-id="9eb20-119">Você pode filtrar essa lista para facilitar a seleção de tabelas e exibições.</span><span class="sxs-lookup"><span data-stu-id="9eb20-119">You can filter this list to help you select tables and views.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9eb20-120">Clique no botão maximizar no canto direito superior para que a janela ocupe toda a tela.</span><span class="sxs-lookup"><span data-stu-id="9eb20-120">Click the maximize button in the upper-right corner so that the window covers the full screen.</span></span> <span data-ttu-id="9eb20-121">Isso facilitará a visualização da lista completa de objetos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9eb20-121">This makes it easier to see the complete list of available objects.</span></span>  
  
     <span data-ttu-id="9eb20-122">Na lista **Objetos disponíveis** , selecione os objetos a seguir.</span><span class="sxs-lookup"><span data-stu-id="9eb20-122">In the **Available objects** list, select the following objects.</span></span> <span data-ttu-id="9eb20-123">Você pode selecionar várias tabelas clicando em cada uma enquanto mantém pressionada a tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="9eb20-123">You can select multiple tables by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="9eb20-124">**DimCustomer (dbo)**</span><span class="sxs-lookup"><span data-stu-id="9eb20-124">**DimCustomer (dbo)**</span></span>  
  
    -   <span data-ttu-id="9eb20-125">**DimDate (dbo)**</span><span class="sxs-lookup"><span data-stu-id="9eb20-125">**DimDate (dbo)**</span></span>  
  
    -   <span data-ttu-id="9eb20-126">**DimGeography (dbo)**</span><span class="sxs-lookup"><span data-stu-id="9eb20-126">**DimGeography (dbo)**</span></span>  
  
    -   <span data-ttu-id="9eb20-127">**DimProduct (dbo)**</span><span class="sxs-lookup"><span data-stu-id="9eb20-127">**DimProduct (dbo)**</span></span>  
  
    -   <span data-ttu-id="9eb20-128">**FactInternetSales (dbo)**</span><span class="sxs-lookup"><span data-stu-id="9eb20-128">**FactInternetSales (dbo)**</span></span>  
  
5.  <span data-ttu-id="9eb20-129">Clique **>** para adicionar as tabelas selecionadas à lista **objetos incluídos** .</span><span class="sxs-lookup"><span data-stu-id="9eb20-129">Click **>** to add the selected tables to the **Included objects** list.</span></span>  
  
6.  <span data-ttu-id="9eb20-130">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9eb20-130">Click **Next.**</span></span>  
  
7.  <span data-ttu-id="9eb20-131">No campo Nome, garanta que **Adventure Works DW 2012** é exibido e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="9eb20-131">In the Name field, make sure **Adventure Works DW 2012** displays, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="9eb20-132">A exibição da fonte de dados **Adventure Works DW 2012** é exibida na pasta **Exibições da Fonte de Dados** do Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="9eb20-132">The **Adventure Works DW 2012** data source view appears in the **Data Source Views** folder in Solution Explorer.</span></span> <span data-ttu-id="9eb20-133">O conteúdo da exibição da fonte de dados também é exibido no Designer de Exibição da Fonte de Dados no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9eb20-133">The content of the data source view is also displayed in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="9eb20-134">Esse designer contém os seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="9eb20-134">This designer contains the following elements:</span></span>  
  
    -   <span data-ttu-id="9eb20-135">Um painel **Diagrama** no qual as tabelas e suas relações são representadas de forma gráfica.</span><span class="sxs-lookup"><span data-stu-id="9eb20-135">A **Diagram** pane in which the tables and their relationships are represented graphically.</span></span>  
  
    -   <span data-ttu-id="9eb20-136">Um painel **Tabelas** no qual as tabelas e seus elementos de esquema são exibidos em um modo de exibição de árvore.</span><span class="sxs-lookup"><span data-stu-id="9eb20-136">A **Tables** pane in which the tables and their schema elements are displayed in a tree view.</span></span>  
  
    -   <span data-ttu-id="9eb20-137">Um painel **Organizador de Diagramas** no qual você pode criar subdiagramas para exibir subconjuntos da exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9eb20-137">A **Diagram Organizer** pane in which you can create subdiagrams so that you can view subsets of the data source view.</span></span>  
  
    -   <span data-ttu-id="9eb20-138">Há uma barra de ferramentas específica para o Designer de Exibição da Fonte de Dados.</span><span class="sxs-lookup"><span data-stu-id="9eb20-138">A toolbar that is specific to Data Source View Designer.</span></span>  
  
8.  <span data-ttu-id="9eb20-139">Para maximizar o ambiente de desenvolvimento do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , clique no botão **Maximizar** .</span><span class="sxs-lookup"><span data-stu-id="9eb20-139">To maximize the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment, click the **Maximize** button.</span></span>  
  
9. <span data-ttu-id="9eb20-140">Para exibir as tabelas no painel **Diagrama** a 50%, clique no ícone **Zoom** na barra de ferramentas do Designer de Exibição da Fonte de Dados.</span><span class="sxs-lookup"><span data-stu-id="9eb20-140">To view the tables in the **Diagram** pane at 50 percent, click the **Zoom** icon on the Data Source View Designer toolbar.</span></span> <span data-ttu-id="9eb20-141">Isso ocultará os detalhes da coluna de cada tabela.</span><span class="sxs-lookup"><span data-stu-id="9eb20-141">This will hide the column details of each table.</span></span>  
  
10. <span data-ttu-id="9eb20-142">Para ocultar o Gerenciador de Soluções, clique no botão **Ocultar Automaticamente** , que é o ícone de pino na barra de título.</span><span class="sxs-lookup"><span data-stu-id="9eb20-142">To hide Solution Explorer, click the **Auto Hide** button, which is the pushpin icon on the title bar.</span></span> <span data-ttu-id="9eb20-143">Para exibir o Gerenciador de Soluções novamente, aponte para a guia do Gerenciador de Soluções à direito do ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="9eb20-143">To view Solution Explorer again, position your pointer over the Solution Explorer tab along the right side of the development environment.</span></span> <span data-ttu-id="9eb20-144">Para exibir o Gerenciador de Soluções novamente, clique no botão **Ocultar Automaticamente** mais uma vez.</span><span class="sxs-lookup"><span data-stu-id="9eb20-144">To unhide Solution Explorer, click the **Auto Hide** button again.</span></span>  
  
11. <span data-ttu-id="9eb20-145">Se as janelas não estiverem ocultas por padrão, clique em **Ocultar Automaticamente** na barra de título das janelas Propriedades e Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="9eb20-145">If the windows are not hidden by default, click **Auto Hide** on the title bar of the Properties and Solution Explorer windows.</span></span>  
  
     <span data-ttu-id="9eb20-146">Agora, você pode exibir todas as tabelas e suas relações no painel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="9eb20-146">You can now view all the tables and their relationships in the **Diagram** pane.</span></span> <span data-ttu-id="9eb20-147">Observe que há três relações entre as tabelas tabelas FactInternetSales e a tabela DimDate.</span><span class="sxs-lookup"><span data-stu-id="9eb20-147">Notice that there are three relationships between the FactInternetSales table and the DimDate table.</span></span> <span data-ttu-id="9eb20-148">Cada venda tem três datas associadas: uma data de ordem, uma data de vencimento e uma data de remessa.</span><span class="sxs-lookup"><span data-stu-id="9eb20-148">Each sale has three dates associated with the sale: an order date, a due date, and a ship date.</span></span> <span data-ttu-id="9eb20-149">Para exibir os detalhes de qualquer relação, clique duas vezes na seta da relação no painel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="9eb20-149">To view the details of any relationship, double-click the relationship arrow in the **Diagram** pane.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9eb20-150">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="9eb20-150">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9eb20-151">Modificando nomes de tabela padrão</span><span class="sxs-lookup"><span data-stu-id="9eb20-151">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
  
## <a name="see-also"></a><span data-ttu-id="9eb20-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9eb20-152">See Also</span></span>  
 [<span data-ttu-id="9eb20-153">Exibições de fontes de dados em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="9eb20-153">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
