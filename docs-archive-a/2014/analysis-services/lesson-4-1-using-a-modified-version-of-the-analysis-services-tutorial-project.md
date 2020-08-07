---
title: Usando uma versão modificada do projeto Analysis Services tutorial | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 685aa217-de1b-4df2-bf22-095228c40775
author: minewiskan
ms.author: owend
ms.openlocfilehash: b833a05a567f37443cf89f7356a0855e0827ea73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575428"
---
# <a name="using-a-modified-version-of-the-analysis-services-tutorial-project"></a><span data-ttu-id="3201c-102">Usando uma versão modificada do projeto do Tutorial do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3201c-102">Using a Modified Version of the Analysis Services Tutorial Project</span></span>
  <span data-ttu-id="3201c-103">As demais lições neste tutorial tem como base uma versão aprimorada do projeto do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que você concluiu nas três primeiras lições.</span><span class="sxs-lookup"><span data-stu-id="3201c-103">The remaining lessons in this tutorial are based on an enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons.</span></span> <span data-ttu-id="3201c-104">Foram adicionadas outras tabelas e cálculos nomeados à exibição da fonte de dados **Adventure Works DW 2012** e outras dimensões ao projeto. Essas novas dimensões foram adicionadas ao cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3201c-104">Additional tables and named calculations have been added to the **Adventure Works DW 2012** data source view, additional dimensions have been added to the project, and these new dimensions have been added to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="3201c-105">Além disso, um segundo grupo de medidas foi adicionado; ele contém medidas de uma segunda tabela de fatos.</span><span class="sxs-lookup"><span data-stu-id="3201c-105">In addition, a second measure group has been added, which contains measures from a second fact table.</span></span> <span data-ttu-id="3201c-106">Esse projeto aprimorado permitirá que você continue a aprender como adicionar funcionalidades ao seu aplicativo de inteligência empresarial sem ter que repetir as ações já aprendidas.</span><span class="sxs-lookup"><span data-stu-id="3201c-106">This enhanced project will enable you to continue learning how to add functionality to your business intelligence application without having to repeat the skills you have already learned.</span></span>  
  
 <span data-ttu-id="3201c-107">Antes de continuar com o tutorial, você deve baixar, extrair, carregar e processar a versão aprimorada do projeto do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3201c-107">Before you can continue with the tutorial, you must download, extract, load and process the enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span>  <span data-ttu-id="3201c-108">Use as instruções nesta lição para verificar se você realizou todas as etapas.</span><span class="sxs-lookup"><span data-stu-id="3201c-108">Use the instructions in this lesson to ensure you have performed all the steps.</span></span>  
  
## <a name="downloading-and-extracting-the-project-file"></a><span data-ttu-id="3201c-109">Baixando e extraindo o Arquivo do Projeto</span><span class="sxs-lookup"><span data-stu-id="3201c-109">Downloading and Extracting the Project File</span></span>  
  
1.  <span data-ttu-id="3201c-110">[Clique aqui](https://go.microsoft.com/fwlink/?LinkID=221866) para ir para a página de download que fornece os projetos de exemplo fornecidos neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="3201c-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to go to the download page that provides the sample projects that go with this tutorial.</span></span> <span data-ttu-id="3201c-111">Os projetos do tutorial estão incluídos no download do **Tutorial do Analysis Services do SQL Server 2012** .</span><span class="sxs-lookup"><span data-stu-id="3201c-111">The tutorial projects are included in the **Analysis Services Tutorial SQL Server 2012** download.</span></span>  
  
2.  <span data-ttu-id="3201c-112">Clique em **Tutorial do Analysis Services do SQL Server 2012** para baixar o pacote que contém os projetos para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3201c-112">Click **Analysis Services Tutorial SQL Server 2012** to download the package that contains the projects for this tutorial.</span></span>  
  
     <span data-ttu-id="3201c-113">Por padrão, um arquivo .zip é salvo na pasta de Downloads.</span><span class="sxs-lookup"><span data-stu-id="3201c-113">By default, a .zip file is saved to the Downloads folder.</span></span> <span data-ttu-id="3201c-114">Você deve mover o arquivo .zip para um local que tem um caminho mais curto (por exemplo, crie uma pasta C:\Tutoriais para armazenar os arquivos).</span><span class="sxs-lookup"><span data-stu-id="3201c-114">You must move the .zip file to a location that has a shorter path (for example, create a C:\Tutorials folder to store the files).</span></span>  <span data-ttu-id="3201c-115">Você pode então extrair os arquivos contidos no arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="3201c-115">You can then extract the files contained in the .zip file.</span></span> <span data-ttu-id="3201c-116">Se você tentar descompactar os arquivos da pasta de Downloads, que tem um caminho mais longo, só obterá a Lição 1.</span><span class="sxs-lookup"><span data-stu-id="3201c-116">If you attempt to unzip the files from the Downloads folder, which has a longer path, you will only get Lesson 1.</span></span>  
  
3.  <span data-ttu-id="3201c-117">Crie uma subpasta na unidade de raiz ou perto dela, por exemplo, C:\Tutorial.</span><span class="sxs-lookup"><span data-stu-id="3201c-117">Create a subfolder at or near the root drive, for example, C:\Tutorial.</span></span>  
  
4.  <span data-ttu-id="3201c-118">Mova o arquivo **Analysis Services Tutorial SQL Server 2012.zip** para a subpasta.</span><span class="sxs-lookup"><span data-stu-id="3201c-118">Move the **Analysis Services Tutorial SQL Server 2012.zip** file to the subfolder.</span></span>  
  
5.  <span data-ttu-id="3201c-119">Clique com o botão direito do mouse no arquivo e selecione **Extrair Tudo**.</span><span class="sxs-lookup"><span data-stu-id="3201c-119">Right-click the file and select **Extract All**.</span></span>  
  
6.  <span data-ttu-id="3201c-120">Navegue até a pasta **Início da Lição 4** para localizar o arquivo **Analysis Services Tutorial.sln** .</span><span class="sxs-lookup"><span data-stu-id="3201c-120">Browse to the **Lesson 4 Start** folder to find the **Analysis Services Tutorial.sln** file.</span></span>  
  
## <a name="loading-and-processing-the-enhanced-project"></a><span data-ttu-id="3201c-121">Carregando e processando o projeto aprimorado</span><span class="sxs-lookup"><span data-stu-id="3201c-121">Loading and Processing the Enhanced Project</span></span>  
  
1.  <span data-ttu-id="3201c-122">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , no menu **arquivo** , clique em **fechar solução** para fechar os arquivos que você não usará.</span><span class="sxs-lookup"><span data-stu-id="3201c-122">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **File** menu, click **Close Solution** to close files you won't be using.</span></span>  
  
2.  <span data-ttu-id="3201c-123">No menu **Arquivo** , aponte para **Abrir**e clique em **Projeto/Solução**.</span><span class="sxs-lookup"><span data-stu-id="3201c-123">On the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="3201c-124">Navegue até o local onde você extraiu os arquivos de projeto do tutorial.</span><span class="sxs-lookup"><span data-stu-id="3201c-124">Browse to the location where you extracted the tutorial project files.</span></span>  
  
     <span data-ttu-id="3201c-125">Localize a pasta chamada **Início da Lição 4**e clique duas vezes em Analysis Services Tutorial.sln.</span><span class="sxs-lookup"><span data-stu-id="3201c-125">Find the folder named **Lesson 4 Start**, and then double-click Analysis Services Tutorial.sln.</span></span>  
  
4.  <span data-ttu-id="3201c-126">Implante a versão aprimorada do projeto do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] na instância local do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]ou em outra instância, e verifique se o processamento é concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="3201c-126">Deploy the enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project to the local instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], or to another instance, and verify that processing completes successfully.</span></span>  
  
## <a name="understanding-the-enhancements-to-the-project"></a><span data-ttu-id="3201c-127">Entendendo os aprimoramentos do projeto</span><span class="sxs-lookup"><span data-stu-id="3201c-127">Understanding the Enhancements to the Project</span></span>  
 <span data-ttu-id="3201c-128">A versão aprimorada do projeto é diferente da versão do projeto do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que você concluiu nas três primeiras lições.</span><span class="sxs-lookup"><span data-stu-id="3201c-128">The enhanced version of the project is different from the version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons.</span></span> <span data-ttu-id="3201c-129">As diferenças são descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="3201c-129">The differences are described in the following sections.</span></span> <span data-ttu-id="3201c-130">Revise estas informações antes de continuar com as demais lições do tutorial.</span><span class="sxs-lookup"><span data-stu-id="3201c-130">Review this information before continuing with the remaining lessons in the tutorial.</span></span>  
  
### <a name="data-source-view"></a><span data-ttu-id="3201c-131">Exibição da Fonte de Dados</span><span class="sxs-lookup"><span data-stu-id="3201c-131">Data Source View</span></span>  
 <span data-ttu-id="3201c-132">A exibição da fonte de dados no projeto aprimorado contém uma tabela de fatos adicional e quatro tabelas de dimensão adicionais do banco de dados [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3201c-132">The data source view in the enhanced project contains one additional fact table and four additional dimension tables from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="3201c-133">Observe que, com dez tabelas na exibição da fonte de dados, o diagrama \<All Tables> está ficando muito cheio.</span><span class="sxs-lookup"><span data-stu-id="3201c-133">Notice that with ten tables in the data source view, the \<All Tables> diagram is becoming crowded.</span></span> <span data-ttu-id="3201c-134">Isso dificulta a compreensão das relações entre as tabelas e a localização de tabelas específicas.</span><span class="sxs-lookup"><span data-stu-id="3201c-134">This makes it difficult to easily understand the relationships between the tables and to locate specific tables.</span></span> <span data-ttu-id="3201c-135">Para solucionar esse problema, as tabelas são organizadas em dois diagramas lógicos: **Vendas pela Internet** e **Vendas do Revendedor** .</span><span class="sxs-lookup"><span data-stu-id="3201c-135">To solve this problem, the tables are organized into two logical diagrams, the **Internet Sales** diagram and the **Reseller Sales** diagram.</span></span> <span data-ttu-id="3201c-136">Esses diagramas são organizados com base em uma única tabela de fato.</span><span class="sxs-lookup"><span data-stu-id="3201c-136">These diagrams are each organized around a single fact table.</span></span> <span data-ttu-id="3201c-137">Criar diagramas lógicos permite que você exiba e trabalhe com um subconjunto específico de tabelas em uma exibição de fonte de dado em vez de ter que exibir sempre todas as tabelas e suas relações em um único diagrama.</span><span class="sxs-lookup"><span data-stu-id="3201c-137">Creating logical diagrams lets you view and work with a specific subset of the tables in a data source view instead of always viewing all the tables and their relationships in a single diagram.</span></span>  
  
#### <a name="internet-sales-diagram"></a><span data-ttu-id="3201c-138">Diagrama Vendas pela Internet</span><span class="sxs-lookup"><span data-stu-id="3201c-138">Internet Sales Diagram</span></span>  
 <span data-ttu-id="3201c-139">O diagrama **Vendas pela Internet** contém as tabelas relacionadas à venda de produtos do [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] diretamente aos clientes pela Internet.</span><span class="sxs-lookup"><span data-stu-id="3201c-139">The **Internet Sales** diagram contains the tables that are related to the sale of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] products directly to customers through the Internet.</span></span> <span data-ttu-id="3201c-140">As tabelas do diagrama são as quatro tabelas de dimensão e a tabela de fatos que você adicionou à exibição da fonte de dados **Adventure Works DW 2012** na Lição 1.</span><span class="sxs-lookup"><span data-stu-id="3201c-140">The tables in the diagram are the four dimension tables and one fact table that you added to the **Adventure Works DW 2012** data source view in Lesson 1.</span></span> <span data-ttu-id="3201c-141">Essas tabelas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="3201c-141">These tables are as follows:</span></span>  
  
-   <span data-ttu-id="3201c-142">**Geografia**</span><span class="sxs-lookup"><span data-stu-id="3201c-142">**Geography**</span></span>  
  
-   <span data-ttu-id="3201c-143">**Cliente**</span><span class="sxs-lookup"><span data-stu-id="3201c-143">**Customer**</span></span>  
  
-   <span data-ttu-id="3201c-144">**Data**</span><span class="sxs-lookup"><span data-stu-id="3201c-144">**Date**</span></span>  
  
-   <span data-ttu-id="3201c-145">**Product**</span><span class="sxs-lookup"><span data-stu-id="3201c-145">**Product**</span></span>  
  
-   <span data-ttu-id="3201c-146">**InternetSales**</span><span class="sxs-lookup"><span data-stu-id="3201c-146">**InternetSales**</span></span>  
  
#### <a name="reseller-sales-diagram"></a><span data-ttu-id="3201c-147">Reseller Sales Diagram</span><span class="sxs-lookup"><span data-stu-id="3201c-147">Reseller Sales Diagram</span></span>  
 <span data-ttu-id="3201c-148">O diagrama **Vendas do Revendedor** contém as tabelas relacionadas à venda de produtos do [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] por revendedores.</span><span class="sxs-lookup"><span data-stu-id="3201c-148">The **Reseller Sales** diagram contains the tables that are related to the sale of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] products by resellers.</span></span> <span data-ttu-id="3201c-149">Esse diagrama contém as sete tabelas de dimensão e uma tabela de fatos do banco de dados [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="3201c-149">This diagram contains the following seven dimension tables and one fact table from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database:</span></span>  
  
-   <span data-ttu-id="3201c-150">**Reseller**</span><span class="sxs-lookup"><span data-stu-id="3201c-150">**Reseller**</span></span>  
  
-   <span data-ttu-id="3201c-151">**Promoção**</span><span class="sxs-lookup"><span data-stu-id="3201c-151">**Promotion**</span></span>  
  
-   <span data-ttu-id="3201c-152">**SalesTerritory**</span><span class="sxs-lookup"><span data-stu-id="3201c-152">**SalesTerritory**</span></span>  
  
-   <span data-ttu-id="3201c-153">**Geografia**</span><span class="sxs-lookup"><span data-stu-id="3201c-153">**Geography**</span></span>  
  
-   <span data-ttu-id="3201c-154">**Data**</span><span class="sxs-lookup"><span data-stu-id="3201c-154">**Date**</span></span>  
  
-   <span data-ttu-id="3201c-155">**Product**</span><span class="sxs-lookup"><span data-stu-id="3201c-155">**Product**</span></span>  
  
-   <span data-ttu-id="3201c-156">**Employee**</span><span class="sxs-lookup"><span data-stu-id="3201c-156">**Employee**</span></span>  
  
-   <span data-ttu-id="3201c-157">**ResellerSales**</span><span class="sxs-lookup"><span data-stu-id="3201c-157">**ResellerSales**</span></span>  
  
 <span data-ttu-id="3201c-158">Observe que as tabelas **DimGeography**, **DimDate**e **DimProduct** são usadas nos diagramas **Vendas pela Internet** e **Vendas do Revendedor** .</span><span class="sxs-lookup"><span data-stu-id="3201c-158">Notice that the **DimGeography**, **DimDate**, and **DimProduct** tables are used in both the **Internet Sales** diagram and the **Reseller Sales** diagram.</span></span> <span data-ttu-id="3201c-159">As tabelas de dimensão podem ser vinculadas a várias tabelas de fatos.</span><span class="sxs-lookup"><span data-stu-id="3201c-159">Dimension tables can be linked to multiple fact tables.</span></span>  
  
### <a name="database-and-cube-dimensions"></a><span data-ttu-id="3201c-160">Banco de dados e dimensões de cubo</span><span class="sxs-lookup"><span data-stu-id="3201c-160">Database and Cube Dimensions</span></span>  
 <span data-ttu-id="3201c-161">O projeto do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] contém cinco novas dimensões de bancos de dados, e o cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] contém as mesmas cinco dimensões como dimensões de cubo.</span><span class="sxs-lookup"><span data-stu-id="3201c-161">The [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project contains five new database dimensions, and the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube contains these same five dimensions as cube dimensions.</span></span> <span data-ttu-id="3201c-162">Essas dimensões foram definidas para terem hierarquias de usuário e atributos que foram modificados usando cálculos nomeados, chaves de membros de composição e pastas de exibição.</span><span class="sxs-lookup"><span data-stu-id="3201c-162">These dimensions have been defined to have user hierarchies and attributes that were modified by using named calculations, composition member keys, and display folders.</span></span> <span data-ttu-id="3201c-163">As novas dimensões são descritas na lista a seguir.</span><span class="sxs-lookup"><span data-stu-id="3201c-163">The new dimensions are described in the following list.</span></span>  
  
 <span data-ttu-id="3201c-164">Dimensão Revendedor</span><span class="sxs-lookup"><span data-stu-id="3201c-164">Reseller Dimension</span></span>  
 <span data-ttu-id="3201c-165">A dimensão Revendedor tem como base a tabela **Revendedor** da exibição da fonte de dados **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="3201c-165">The Reseller dimension is based on the **Reseller** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="3201c-166">Dimensão Promoção</span><span class="sxs-lookup"><span data-stu-id="3201c-166">Promotion Dimension</span></span>  
 <span data-ttu-id="3201c-167">A dimensão Promoção tem como base a tabela **Promoção** da exibição da fonte de dados **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="3201c-167">The Promotion dimension is based on the **Promotion** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="3201c-168">Dimensão Região de Vendas</span><span class="sxs-lookup"><span data-stu-id="3201c-168">Sales Territory Dimension</span></span>  
 <span data-ttu-id="3201c-169">A dimensão Região de Vendas tem como base a tabela **SalesTerritory** da exibição da fonte de dados **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="3201c-169">The Sales Territory dimension is based on the **SalesTerritory** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="3201c-170">Dimensão Funcionário</span><span class="sxs-lookup"><span data-stu-id="3201c-170">Employee Dimension</span></span>  
 <span data-ttu-id="3201c-171">A dimensão Funcionário tem como base a tabela **Funcionário** da exibição da fonte de dados do **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="3201c-171">The Employee dimension is based on the **Employee** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="3201c-172">Dimensão Geografia</span><span class="sxs-lookup"><span data-stu-id="3201c-172">Geography Dimension</span></span>  
 <span data-ttu-id="3201c-173">A dimensão Geografia tem como base a tabela **Geografia** da exibição da fonte de dados **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="3201c-173">The Geography dimension is based on the **Geography** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
#### <a name="analysis-services-cube"></a><span data-ttu-id="3201c-174">Cubo do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3201c-174">Analysis Services Cube</span></span>  
 <span data-ttu-id="3201c-175">O cubo **Tutorial do Analysis Services** agora tem dois grupos de medidas: o grupo de medidas original, baseado na tabela **InternetSales** , e um segundo grupo de medidas, baseado na tabela **ResellerSales** da exibição da fonte de dados **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="3201c-175">The **Analysis Services Tutorial** cube now contains two measure groups, the original measure group based on the **InternetSales** table and a second measure group based on the **ResellerSales** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="3201c-176">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="3201c-176">Next Task in Lesson</span></span>  
 [<span data-ttu-id="3201c-177">Definindo propriedades de atributo pai em uma hierarquia pai-filho</span><span class="sxs-lookup"><span data-stu-id="3201c-177">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>](lesson-4-2-defining-parent-attribute-properties-in-a-parent-child-hierarchy.md) 
  
## <a name="see-also"></a><span data-ttu-id="3201c-178">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3201c-178">See Also</span></span>  
 [<span data-ttu-id="3201c-179">Implantando um projeto do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3201c-179">Deploying an Analysis Services Project</span></span>](lesson-2-5-deploying-an-analysis-services-project.md)  
  
  
