---
title: Construtor de Relatórios no SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10428"
helpviewer_keywords:
- overview of Report Builder
- getting started
ms.assetid: 55bf4f9c-d037-412f-ae57-3fc39ce32fa5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b2fb8994272eb24594239551d623021f7b87694c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570492"
---
# <a name="report-builder-in-sql-server-2014"></a><span data-ttu-id="c1e56-102">Construtor de Relatórios no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="c1e56-102">Report Builder in SQL Server 2014</span></span>
  <span data-ttu-id="c1e56-103">O Construtor de Relatórios é um ambiente de criação de relatório para usuários comerciais que preferem trabalhar no ambiente do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office.</span><span class="sxs-lookup"><span data-stu-id="c1e56-103">Report Builder is a report authoring environment for business users who prefer to work in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office environment.</span></span> <span data-ttu-id="c1e56-104">Quando você cria um relatório, especifica onde obter os dados, que dados obter e como exibir os dados.</span><span class="sxs-lookup"><span data-stu-id="c1e56-104">When you design a report, you specify where to get the data, which data to get, and how to display the data.</span></span> <span data-ttu-id="c1e56-105">Ao executar o relatório, o processador de relatório obtém todas as informações especificadas, recupera os dados e os combina ao layout de relatório para gerar o relatório.</span><span class="sxs-lookup"><span data-stu-id="c1e56-105">When you run the report, the report processor takes all the information you have specified, retrieves the data, and combines it with the report layout to generate the report.</span></span> <span data-ttu-id="c1e56-106">Você pode visualizar os relatórios no Construtor de Relatórios ou publicá-los em um servidor de relatório ou em um servidor de relatório no modo integrado do SharePoint, onde outras pessoas poderão executá-lo.</span><span class="sxs-lookup"><span data-stu-id="c1e56-106">You can preview your reports in Report Builder, or you can publish your report to a report server or a report server in SharePoint integrated mode, where others can run it.</span></span>  
  
 <span data-ttu-id="c1e56-107">O relatório nesta ilustração caracteriza uma matriz com grupos de linhas e colunas, minigráficos, indicadores e um gráfico de pizza resumido na célula de canto, acompanhada de um mapa com dois conjuntos de dados geográficos representados pela cor e pelo tamanho do círculo.</span><span class="sxs-lookup"><span data-stu-id="c1e56-107">The report in this illustration features a matrix with row and column groups, sparklines, indicators, and a summary pie chart in the corner cell, accompanied by a map with two sets of geographic data represented by color and by circle size.</span></span>  
  
 <span data-ttu-id="c1e56-108">![rs_GettingStartedReport](../media/rs-gettingstartedreport.gif "rs_GettingStartedReport")</span><span class="sxs-lookup"><span data-stu-id="c1e56-108">![rs_GettingStartedReport](../media/rs-gettingstartedreport.gif "rs_GettingStartedReport")</span></span>  
  
##  <a name="jump-start-report-creation"></a><a name="JumpStartReptCreation"></a><span data-ttu-id="c1e56-109">Iniciar a criação de relatório</span><span class="sxs-lookup"><span data-stu-id="c1e56-109">Jump-Start Report Creation</span></span>  
  
-   <span data-ttu-id="c1e56-110">**Inicie seu relatório withreport partes** criadas por outra pessoa na sua equipe.</span><span class="sxs-lookup"><span data-stu-id="c1e56-110">**Start your report withreport parts** created by someone else on your team.</span></span> <span data-ttu-id="c1e56-111">As partes de relatório são itens de relatório que foram publicados separadamente em um servidor de relatório ou em um site do SharePoint integrado a um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c1e56-111">Report parts are report items that have been published separately to a report server or a SharePoint site that is integrated with a report server.</span></span> <span data-ttu-id="c1e56-112">Elas podem ser reutilizadas em outros relatórios.</span><span class="sxs-lookup"><span data-stu-id="c1e56-112">They can be reused in other reports.</span></span> <span data-ttu-id="c1e56-113">Itens de relatório como tabelas, matrizes, gráficos e imagens podem ser publicados como partes de relatório.</span><span class="sxs-lookup"><span data-stu-id="c1e56-113">Report items such as tables, matrices, charts, and images can be published as report parts.</span></span>  
  
-   <span data-ttu-id="c1e56-114">**Comece com um conjunto de um DataSet compartilhado** criado por outra pessoa na sua equipe.</span><span class="sxs-lookup"><span data-stu-id="c1e56-114">**Start with a shared dataset** created by someone else on your team.</span></span> <span data-ttu-id="c1e56-115">Os conjuntos de dados compartilhados são consultas baseadas em uma fonte de dados compartilhados salvos em um servidor de relatório ou em um site do SharePoint integrado a um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c1e56-115">Shared datasets are queries based on a shared data source that are saved to a report server or a SharePoint site that is integrated with a report server.</span></span>  
  
-   <span data-ttu-id="c1e56-116">**Comece com o Assistente de tabela, matriz ou gráfico**.</span><span class="sxs-lookup"><span data-stu-id="c1e56-116">**Start with the Table, Matrix, or Chart wizard**.</span></span> <span data-ttu-id="c1e56-117">Escolha uma conexão de fonte de dados, arraste e solte campos para criar uma consulta de conjunto de dados, selecione um layout e um estilo e personalize seu relatório.</span><span class="sxs-lookup"><span data-stu-id="c1e56-117">Choose a data source connection, drag and drop fields to create a dataset query, select a layout and style, and customize your report.</span></span>  
  
-   <span data-ttu-id="c1e56-118">**Comece com o Assistente de mapa** para criar relatórios que exibem dados agregados em uma tela de fundo geográfica ou geométrica.</span><span class="sxs-lookup"><span data-stu-id="c1e56-118">**Start with the Map wizard** to create reports that display aggregated data against a geographic or geometric background.</span></span> <span data-ttu-id="c1e56-119">Os dados de mapa podem ser dados espaciais de uma consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] ou um arquivo de forma ESRI (Environmental Systems Research Institute, Inc.).</span><span class="sxs-lookup"><span data-stu-id="c1e56-119">Map data can be spatial data from a [!INCLUDE[tsql](../../includes/tsql-md.md)] query or an Environmental Systems Research Institute, Inc. (ESRI) shapefile.</span></span> <span data-ttu-id="c1e56-120">Também é possível adicionar um plano de fundo de peça de mapa do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Bing.</span><span class="sxs-lookup"><span data-stu-id="c1e56-120">You can also add a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Bing map tile background.</span></span>  
  

  
##  <a name="design-your-report"></a><a name="DesignRept"></a><span data-ttu-id="c1e56-121">Criar seu relatório</span><span class="sxs-lookup"><span data-stu-id="c1e56-121">Design Your Report</span></span>  
  
-   <span data-ttu-id="c1e56-122">**Crie relatórios com tabela, matriz, gráfico e layouts de relatório de forma livre.**</span><span class="sxs-lookup"><span data-stu-id="c1e56-122">**Create reports with table, matrix, chart, and free-form report layouts.**</span></span> <span data-ttu-id="c1e56-123">Crie relatórios de tabela para dados baseados em coluna, relatórios de matriz (como relatórios de Tabela Dinâmica ou referência cruzada) para dados resumidos, relatórios de gráfico para dados gráficos e relatórios de forma livre para qualquer outra coisa.</span><span class="sxs-lookup"><span data-stu-id="c1e56-123">Create table reports for column-based data, matrix reports (like cross-tab or PivotTable reports) for summarized data, chart reports for graphical data, and free-form reports for anything else.</span></span> <span data-ttu-id="c1e56-124">Os relatórios podem inserir outros relatórios e gráficos, junto com listas, gráficos e controles para aplicativos dinâmicos baseados na Web.</span><span class="sxs-lookup"><span data-stu-id="c1e56-124">Reports can embed other reports and charts, together with lists, graphics, and controls for dynamic Web-based applications.</span></span>  
  
-   <span data-ttu-id="c1e56-125">**Gere relatórios de uma variedade de fontes de dados.**</span><span class="sxs-lookup"><span data-stu-id="c1e56-125">**Report from a variety of data sources.**</span></span> <span data-ttu-id="c1e56-126">Crie relatórios usando dados de qualquer tipo de fonte de dados que tenha um [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provedor de dados gerenciado, provedor de OLE DB ou fonte de dados ODBC.</span><span class="sxs-lookup"><span data-stu-id="c1e56-126">Build reports using data from any data source type that has a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-managed data provider, OLE DB provider, or ODBC data source.</span></span> <span data-ttu-id="c1e56-127">Você pode criar relatórios que usam dados relacionais e multidimensionais do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], Oracle, Hyperion e outros bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="c1e56-127">You can create reports that use relational and multidimensional data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], Oracle, Hyperion, and other databases.</span></span> <span data-ttu-id="c1e56-128">Você pode usar uma extensão de processamento de dados XML para recuperar dados de qualquer fonte de dados XML.</span><span class="sxs-lookup"><span data-stu-id="c1e56-128">You can use an XML data processing extension to retrieve data from any XML data source.</span></span> <span data-ttu-id="c1e56-129">Também é possível usar funções com valor de tabela para projetar fontes de dados personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c1e56-129">You can use table-valued functions to design custom data sources.</span></span>  
  
-   <span data-ttu-id="c1e56-130">**Modifique relatórios existentes.**</span><span class="sxs-lookup"><span data-stu-id="c1e56-130">**Modify existing reports.**</span></span> <span data-ttu-id="c1e56-131">Usando Construtor de Relatórios, você pode personalizar e atualizar relatórios que foram criados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] Report Designer.</span><span class="sxs-lookup"><span data-stu-id="c1e56-131">By using Report Builder, you can customize and update reports that were created in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Report Designer.</span></span>  
  
-   <span data-ttu-id="c1e56-132">**Modifique seus dados** filtrando, agrupando e classificando dados ou adicionando fórmulas ou expressões.</span><span class="sxs-lookup"><span data-stu-id="c1e56-132">**Modify your data** by filtering, grouping and sorting data, or by adding formulas or expressions.</span></span>  
  
-   <span data-ttu-id="c1e56-133">**Adicione gráficos, medidores, minigráficos e indicadores** para resumir dados em um formato visual e apresentar grandes volumes de informações agregadas de forma concisa.</span><span class="sxs-lookup"><span data-stu-id="c1e56-133">**Add charts, gauges, sparklines, and indicators** to summarize data in a visual format, and present large volumes of aggregated information at a glance.</span></span>  
  
-   <span data-ttu-id="c1e56-134">**Adicione recursos interativos**, como mapas do documento, botões para mostrar/ocultar e links de detalhamento para sub-relatórios e relatórios detalhados.</span><span class="sxs-lookup"><span data-stu-id="c1e56-134">**Add interactive features** such as document maps, show/hide buttons, and drillthrough links to subreports and drillthrough reports.</span></span> <span data-ttu-id="c1e56-135">Use parâmetros e filtros para filtrar dados para exibições personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c1e56-135">Use parameters and filters to filter data for customized views.</span></span>  
  
-   <span data-ttu-id="c1e56-136">**Insira ou referencie imagens** e outros recursos, incluindo conteúdo externo.</span><span class="sxs-lookup"><span data-stu-id="c1e56-136">**Embed or reference images** and other resources, including external content.</span></span>  
  

  
##  <a name="manage-your-report"></a><a name="ManageRpt"></a><span data-ttu-id="c1e56-137">Gerenciar seu relatório</span><span class="sxs-lookup"><span data-stu-id="c1e56-137">Manage Your Report</span></span>  
  
-   <span data-ttu-id="c1e56-138">**Salve a definição do relatório** no computador ou no servidor de relatório, no qual você pode gerenciá-lo e compartilhá-lo com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="c1e56-138">**Save the definition of the report** to your computer or to the report server, where you can manage it and share it with others.</span></span>  
  
-   <span data-ttu-id="c1e56-139">**Escolha um formato de apresentação** ao abrir o relatório ou depois de abri-lo.</span><span class="sxs-lookup"><span data-stu-id="c1e56-139">**Choose a presentation format** when you open the report, or after you open the report.</span></span> <span data-ttu-id="c1e56-140">Selecione formatos orientados à Web, orientados à página e de aplicativo da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c1e56-140">You can select Web-oriented, page-oriented, and desktop application formats.</span></span> <span data-ttu-id="c1e56-141">Os formatos incluem HTML, MHTML, PDF, XML, CSV, TIFF, Word e Excel.</span><span class="sxs-lookup"><span data-stu-id="c1e56-141">Formats include HTML, MHTML, PDF, XML, CSV, TIFF, Word, and Excel.</span></span>  
  
-   <span data-ttu-id="c1e56-142">**Configure assinaturas.**</span><span class="sxs-lookup"><span data-stu-id="c1e56-142">**Set up subscriptions.**</span></span> <span data-ttu-id="c1e56-143">Depois de publicar o relatório no servidor de relatório ou em um servidor de relatório no modo integrado do SharePoint, você poderá configurá-lo para ser executado em um determinado horário, criar um histórico do relatório e configurar assinaturas de email.</span><span class="sxs-lookup"><span data-stu-id="c1e56-143">After you publish the report to the report server or a report server in SharePoint integrated mode, you can configure your report to run at a specific time, create a report history, and set up e-mail subscriptions.</span></span>  
  
-   <span data-ttu-id="c1e56-144">**Gere feeds de dados** de seu relatório usando a extensão de renderização Atom do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c1e56-144">**Generate data feeds** from your report by using the Reporting Services Atom rendering extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1e56-145">Os relatórios publicados são gerenciados em um servidor de relatório ou um servidor de relatório no modo integrado do SharePoint por um administrador do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c1e56-145">Published reports are managed on a report server or a report server in SharePoint integrated mode by a report server administrator.</span></span> <span data-ttu-id="c1e56-146">Os administradores de servidor de relatório podem definir a segurança, estabelecer as propriedades e agendar operações, como histórico de relatório e entrega de relatório de email.</span><span class="sxs-lookup"><span data-stu-id="c1e56-146">Report server administrators can define security, set properties, and schedule operations such as report history and e-mail report delivery.</span></span> <span data-ttu-id="c1e56-147">Também podem criar agendas e fontes de dados compartilhadas e disponibilizá-las para uso geral.</span><span class="sxs-lookup"><span data-stu-id="c1e56-147">They can create shared schedules and shared data sources and make them available for general use.</span></span> <span data-ttu-id="c1e56-148">Os administradores também gerenciam todas as pastas de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c1e56-148">Administrators also manage all of the report server folders.</span></span> <span data-ttu-id="c1e56-149">A possibilidade de executar tarefas de gerenciamento depende das permissões de usuário.</span><span class="sxs-lookup"><span data-stu-id="c1e56-149">The ability to perform management tasks depends on user permissions.</span></span>  
  

  
##  <a name="in-this-section"></a><a name="InThisSection"></a> <span data-ttu-id="c1e56-150">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c1e56-150">In This Section</span></span>  
 [<span data-ttu-id="c1e56-151">Novidades no Construtor de Relatórios para SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="c1e56-151">What's New in Report Builder for SQL Server 2014</span></span>](../what-s-new-in-report-builder-for-sql-server-2014.md)  
 <span data-ttu-id="c1e56-152">Descreve os novos recursos nesta versão do Construtor de Relatórios, inclusive mapas.</span><span class="sxs-lookup"><span data-stu-id="c1e56-152">Describes the new features in this version of Report Builder, including maps.</span></span>  
  
 [<span data-ttu-id="c1e56-153">Tutorial: Criando um relatório de gráfico rápido offline</span><span class="sxs-lookup"><span data-stu-id="c1e56-153">Tutorial: Creating a Quick Chart Report Offline</span></span>](tutorial-create-a-quick-chart-report-offline-report-builder.md)  
 <span data-ttu-id="c1e56-154">Apresenta o Construtor de Relatórios e os assistentes disponíveis para ajudá-lo a criar relatórios.</span><span class="sxs-lookup"><span data-stu-id="c1e56-154">Introduces Report Builder and the wizards available to help you create reports.</span></span> <span data-ttu-id="c1e56-155">O tutorial fornece um conjunto de dados com o qual trabalhar, de modo que você não precise se conectar a uma fonte de dados para começar.</span><span class="sxs-lookup"><span data-stu-id="c1e56-155">The tutorial provides a set of data for you to work with so you do not need to connect to a data source to get started.</span></span>  
  
 [<span data-ttu-id="c1e56-156">Planejando um relatório &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="c1e56-156">Planning a Report &#40;Report Builder&#41;</span></span>](../report-design/planning-a-report-report-builder.md)  
 <span data-ttu-id="c1e56-157">Fornece informações sobre o que você deve considerar antes de começar a criar seu relatório.</span><span class="sxs-lookup"><span data-stu-id="c1e56-157">Provides information on what you should consider before you start to build your report.</span></span>  
  
 [<span data-ttu-id="c1e56-158">Conceitos de criação de relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c1e56-158">Report Authoring Concepts &#40;Report Builder and SSRS&#41;</span></span>](../report-design/report-authoring-concepts-report-builder-and-ssrs.md)  
 <span data-ttu-id="c1e56-159">Define os conceitos-chave usados em toda a documentação do Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="c1e56-159">Defines key concepts used in throughout Report Builder documentation.</span></span>  
  
 [<span data-ttu-id="c1e56-160">Modo de exibição de Design de relatório &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="c1e56-160">Report Design View &#40;Report Builder&#41;</span></span>](report-design-view-report-builder.md)  
 <span data-ttu-id="c1e56-161">Explica os diferentes painéis e regiões da exibição de design de relatório.</span><span class="sxs-lookup"><span data-stu-id="c1e56-161">Explains the different panes and regions of report design view.</span></span>  
  
 [<span data-ttu-id="c1e56-162">Modo de exibição de design de conjunto de &#40;compartilhado Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="c1e56-162">Shared Dataset Design View &#40;Report Builder&#41;</span></span>](shared-dataset-design-view-report-builder.md)  
 <span data-ttu-id="c1e56-163">Explica os diferentes painéis e regiões da exibição de design do conjunto de dados compartilhados.</span><span class="sxs-lookup"><span data-stu-id="c1e56-163">Explains the different panes and regions of shared dataset design view.</span></span>  
  
 [<span data-ttu-id="c1e56-164">Atalhos de teclado &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="c1e56-164">Keyboard Shortcuts &#40;Report Builder&#41;</span></span>](keyboard-shortcuts-report-builder.md)  
 <span data-ttu-id="c1e56-165">Descreve as teclas de atalho disponíveis para navegar e criar relatórios no Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="c1e56-165">Outlines the shortcut keys available for navigating and designing reports in Report Builder.</span></span>  
  
 [<span data-ttu-id="c1e56-166">Iniciar Construtor de Relatórios &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="c1e56-166">Start Report Builder &#40;Report Builder&#41;</span></span>](start-report-builder.md)  
 <span data-ttu-id="c1e56-167">Explica como iniciar as duas versões diferentes do Construtor de Relatórios: autônoma e [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1e56-167">Explains how to start the two different versions of Report Builder: stand-alone and [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)].</span></span>  
  
  