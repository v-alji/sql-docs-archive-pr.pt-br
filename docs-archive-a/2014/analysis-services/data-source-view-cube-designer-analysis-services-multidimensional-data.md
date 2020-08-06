---
title: Exibição da fonte de dados (guia estrutura do cubo, designer de cubo) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.cubebuilder.datasourcepane.f1
ms.assetid: 1e39c910-5c10-4624-be27-ca02a461b46b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c949eaa17ec9d8bf585a5d595f31779382c41ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681269"
---
# <a name="data-source-view-cube-structure-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="8e797-102">Exibição da Fonte de Dados (guia Estrutura do Cubo, Designer de Cubo) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="8e797-102">Data Source View (Cube Structure Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="8e797-103">Use o painel **Exibição da Fonte de Dados** para exibir tabelas e colunas da exibição da fonte de dados associada ao cubo selecionado.</span><span class="sxs-lookup"><span data-stu-id="8e797-103">Use the **Data Source View** pane to view tables and columns from the data source view associated with the selected cube.</span></span> <span data-ttu-id="8e797-104">Esse painel é usado para criar grupos de medidas e medidas, arrastando colunas do painel **Exibição da Fonte de Dados** para o painel **Medidas** .</span><span class="sxs-lookup"><span data-stu-id="8e797-104">This pane is used to create measure groups and measures by dragging columns from the **Data Source View** pane to the **Measures** pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8e797-105">Opções</span><span class="sxs-lookup"><span data-stu-id="8e797-105">Options</span></span>  
 <span data-ttu-id="8e797-106">**Exibição da Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="8e797-106">**Data Source View**</span></span>  
 <span data-ttu-id="8e797-107">Exibe a exibição da fonte de dados associada ao cubo selecionado.</span><span class="sxs-lookup"><span data-stu-id="8e797-107">Displays the data source view associated with the selected cube.</span></span>  
  
 <span data-ttu-id="8e797-108">**(Mover ponto de vista)**</span><span class="sxs-lookup"><span data-stu-id="8e797-108">**(Move viewpoint)**</span></span>  
 <span data-ttu-id="8e797-109">Clique no canto inferior direito do painel, entre as barras de rolagem, para selecionar uma área do painel **Exibição da Fonte de Dados** para exibição.</span><span class="sxs-lookup"><span data-stu-id="8e797-109">Click the lower right corner of the pane, between the scrollbars, to select an area of the **Data Source View** pane to view.</span></span>  
  
## <a name="diagram-context-menu"></a><span data-ttu-id="8e797-110">Menu de Contexto de Diagrama</span><span class="sxs-lookup"><span data-stu-id="8e797-110">Diagram Context Menu</span></span>  
 <span data-ttu-id="8e797-111">As seguintes opções estão disponíveis no menu de contexto exibido ao clicar com o botão direito do mouse na tela de fundo do diagrama do painel **Exibição da Fonte de Dados** :</span><span class="sxs-lookup"><span data-stu-id="8e797-111">The following options are available in the context menu displayed by right-clicking the diagram background of the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="8e797-112">**Mostrar tabelas**</span><span class="sxs-lookup"><span data-stu-id="8e797-112">**Show Tables**</span></span>  
 <span data-ttu-id="8e797-113">Exibe a caixa de diálogo **Mostrar Tabelas**.</span><span class="sxs-lookup"><span data-stu-id="8e797-113">Displays the **Show Table** dialog box.</span></span> <span data-ttu-id="8e797-114">Para obter mais informações sobre a caixa de diálogo **Mostrar Tabela**, consulte [Caixa de diálogo Mostrar Tabela &#40;Analysis Services – Dados Multidimensionais&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="8e797-114">For more information about the **Show Table** dialog box, see [Show Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="8e797-115">**Mostrar Todas as Tabelas**</span><span class="sxs-lookup"><span data-stu-id="8e797-115">**Show All Tables**</span></span>  
 <span data-ttu-id="8e797-116">Exibe no painel todas as tabelas incluídas na exibição da fonte de dados associada ao cubo.</span><span class="sxs-lookup"><span data-stu-id="8e797-116">Displays in the pane all tables included in the data source view associated with the cube.</span></span>  
  
 <span data-ttu-id="8e797-117">**Mostrar Somente Tabelas Usadas**</span><span class="sxs-lookup"><span data-stu-id="8e797-117">**Show Only Used Tables**</span></span>  
 <span data-ttu-id="8e797-118">Exibe no painel somente as tabelas usadas pelo cubo na exibição da fonte de dados associada ao cubo.</span><span class="sxs-lookup"><span data-stu-id="8e797-118">Displays in the pane only those tables used by the cube from the associated data source view.</span></span>  
  
 <span data-ttu-id="8e797-119">**Mostrar nomes amigáveis**</span><span class="sxs-lookup"><span data-stu-id="8e797-119">**Show Friendly Names**</span></span>  
 <span data-ttu-id="8e797-120">Seleciona mostrar nomes amigáveis dos objetos no painel.</span><span class="sxs-lookup"><span data-stu-id="8e797-120">Selects to show friendly names for the objects in the pane.</span></span>  
  
 <span data-ttu-id="8e797-121">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="8e797-121">**Select All**</span></span>  
 <span data-ttu-id="8e797-122">Seleciona todos os objetos no painel.</span><span class="sxs-lookup"><span data-stu-id="8e797-122">Selects all of the objects in the pane.</span></span>  
  
 <span data-ttu-id="8e797-123">**Localizar Tabela**</span><span class="sxs-lookup"><span data-stu-id="8e797-123">**Find Table**</span></span>  
 <span data-ttu-id="8e797-124">Exibe a caixa de diálogo **Localizar Tabela**.</span><span class="sxs-lookup"><span data-stu-id="8e797-124">Displays the **Find Table** dialog box.</span></span> <span data-ttu-id="8e797-125">Para obter mais informações sobre a caixa de diálogo **Localizar Tabela**, consulte [Caixa de diálogo Localizar Tabela &#40;Analysis Services – Dados Multidimensionais&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="8e797-125">For more information about the **Find Table** dialog box, see [Find Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="8e797-126">**Organizar Tabelas**</span><span class="sxs-lookup"><span data-stu-id="8e797-126">**Arrange Tables**</span></span>  
 <span data-ttu-id="8e797-127">Organiza os objetos no painel de acordo com o layout especificado selecionando **Alternar para Layout Diagonal** ou **Alternar para Layout Retangular**.</span><span class="sxs-lookup"><span data-stu-id="8e797-127">Arranges the objects in the pane according to the layout specified by selecting either **Switch to Diagonal Layout** or **Switch to Rectangular Layout**.</span></span>  
  
 <span data-ttu-id="8e797-128">**Alternar para Layout Diagonal**</span><span class="sxs-lookup"><span data-stu-id="8e797-128">**Switch to Diagonal Layout**</span></span>  
 <span data-ttu-id="8e797-129">Selecione para organizar objetos em um padrão diagonal.</span><span class="sxs-lookup"><span data-stu-id="8e797-129">Select to arrange objects in a diagonal pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e797-130"> Esta opção será exibida somente se a opção **Alternar para Layout Retangular** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-130">This option is displayed only if **Switch to Rectangular Layout** is selected.</span></span>  
  
 <span data-ttu-id="8e797-131">**Alternar para Layout Retangular**</span><span class="sxs-lookup"><span data-stu-id="8e797-131">**Switch to Rectangular Layout**</span></span>  
 <span data-ttu-id="8e797-132">Selecione para organizar objetos em um padrão retangular.</span><span class="sxs-lookup"><span data-stu-id="8e797-132">Select to arrange objects in a rectangular pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e797-133"> Esta opção será exibida somente se a opção **Alternar para Layout Diagonal** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-133">This option is displayed only if **Switch to Diagonal Layout** is selected.</span></span>  
  
 <span data-ttu-id="8e797-134">**Editar Exibição da Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="8e797-134">**Edit Data Source View**</span></span>  
 <span data-ttu-id="8e797-135">Exibe o Designer da Exibição da Fonte de Dados associada ao objeto.</span><span class="sxs-lookup"><span data-stu-id="8e797-135">Displays Data Source View Designer for the data source view associated with the object.</span></span> <span data-ttu-id="8e797-136">Para obter mais informações sobre o Designer de Exibição da Fonte de Dados, consulte [Designer de Exibição da Fonte de Dados &#40;Analysis Services – Dados Multidimensionais&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="8e797-136">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="8e797-137">**Mostrar Exibição da Fonte de Dados em**</span><span class="sxs-lookup"><span data-stu-id="8e797-137">**Show Data Source View In**</span></span>  
 <span data-ttu-id="8e797-138">Selecione uma das seguintes opções para ativar/desativar a exibição do painel **Exibição da Fonte de Dados** nos seguintes modos:</span><span class="sxs-lookup"><span data-stu-id="8e797-138">Select one of the following options to toggle between viewing the **Data Source View** pane in the following modes:</span></span>  
  
-   <span data-ttu-id="8e797-139">Diagrama</span><span class="sxs-lookup"><span data-stu-id="8e797-139">Diagram</span></span>  
  
     <span data-ttu-id="8e797-140">Exibe um diagrama das tabelas e colunas associadas ao cubo atual.</span><span class="sxs-lookup"><span data-stu-id="8e797-140">Displays a diagram of the tables and columns associated with the current cube.</span></span>  
  
-   <span data-ttu-id="8e797-141">Árvore</span><span class="sxs-lookup"><span data-stu-id="8e797-141">Tree</span></span>  
  
     <span data-ttu-id="8e797-142">Exibe uma exibição de árvore contendo as tabelas e colunas associadas ao cubo atual.</span><span class="sxs-lookup"><span data-stu-id="8e797-142">Displays a tree view containing the tables and columns associated with the current cube.</span></span>  
  
 <span data-ttu-id="8e797-143">**Copiar Diagrama de**</span><span class="sxs-lookup"><span data-stu-id="8e797-143">**Copy Diagram From**</span></span>  
 <span data-ttu-id="8e797-144">Selecione um dos diagramas incluídos na exibição da fonte de dados associada ao cubo para exibi-lo no painel **Exibição da Fonte de Dados** .</span><span class="sxs-lookup"><span data-stu-id="8e797-144">Select one of the diagrams included in the data source view associated with the cube to display it in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="8e797-145">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="8e797-145">**Zoom**</span></span>  
 <span data-ttu-id="8e797-146">Selecione uma opção de zoom disponível.</span><span class="sxs-lookup"><span data-stu-id="8e797-146">Select an available zoom option.</span></span>  
  
 <span data-ttu-id="8e797-147">**Propriedades**</span><span class="sxs-lookup"><span data-stu-id="8e797-147">**Properties**</span></span>  
 <span data-ttu-id="8e797-148">Exibe a janela **Propriedades** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] da exibição da fonte de dados associada ao cubo.</span><span class="sxs-lookup"><span data-stu-id="8e797-148">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the data source view associated with the cube.</span></span>  
  
## <a name="table-context-menu"></a><span data-ttu-id="8e797-149">Menu de Contexto da Tabela</span><span class="sxs-lookup"><span data-stu-id="8e797-149">Table Context Menu</span></span>  
 <span data-ttu-id="8e797-150">As seguintes opções estão disponíveis no menu de contexto exibido quando você clica com o botão direito do mouse no nome de uma tabela ou exibição no painel **Exibição da Fonte de Dados** :</span><span class="sxs-lookup"><span data-stu-id="8e797-150">The following options are available in the context menu displayed by right-clicking the name of a table or view in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="8e797-151">**Mostrar Tabelas Relacionadas**</span><span class="sxs-lookup"><span data-stu-id="8e797-151">**Show Related Tables**</span></span>  
 <span data-ttu-id="8e797-152">Exibe no painel as tabelas relacionadas à tabela selecionada na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="8e797-152">Displays in the pane the tables related to the selected table in the data source view.</span></span>  
  
 <span data-ttu-id="8e797-153">**Ocultar Tabela**</span><span class="sxs-lookup"><span data-stu-id="8e797-153">**Hide Table**</span></span>  
 <span data-ttu-id="8e797-154">Remove a tabela do painel.</span><span class="sxs-lookup"><span data-stu-id="8e797-154">Removes the table from the pane.</span></span>  
  
 <span data-ttu-id="8e797-155">**Explorar dados**</span><span class="sxs-lookup"><span data-stu-id="8e797-155">**Explore Data**</span></span>  
 <span data-ttu-id="8e797-156">Exibe a caixa de diálogo **Explorar Dados** da tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-156">Display the **Explore Data** dialog box for the selected table.</span></span>  
  
 <span data-ttu-id="8e797-157">**Editar Exibição da Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="8e797-157">**Edit Data Source View**</span></span>  
 <span data-ttu-id="8e797-158">Exibe o Designer de Exibição da Fonte de Dados da exibição da fonte de dados que contém a tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-158">Displays Data Source View Designer for the data source view that contains the selected table.</span></span> <span data-ttu-id="8e797-159">Para obter mais informações sobre o Designer de Exibição da Fonte de Dados, consulte [Designer de Exibição da Fonte de Dados &#40;Analysis Services – Dados Multidimensionais&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="8e797-159">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="8e797-160">**Novo Grupo de Medidas da Tabela**</span><span class="sxs-lookup"><span data-stu-id="8e797-160">**New Measure Group from Table**</span></span>  
 <span data-ttu-id="8e797-161">Define um novo grupo de medidas no painel **Medidas** baseado na tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-161">Defines a new measure group in the **Measures** pane based on the selected table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e797-162">Essa opção será habilitada apenas se a tabela não for referenciada por um grupo de medidas no painel **Medidas** .</span><span class="sxs-lookup"><span data-stu-id="8e797-162">This option is enabled only if the table is not yet referenced by a measure group in the **Measures** pane.</span></span>  
  
 <span data-ttu-id="8e797-163">**Propriedades**</span><span class="sxs-lookup"><span data-stu-id="8e797-163">**Properties**</span></span>  
 <span data-ttu-id="8e797-164">Exibe a janela **Propriedades** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] da tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-164">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected table.</span></span>  
  
## <a name="column-context-menu"></a><span data-ttu-id="8e797-165">Menu de Contexto da Coluna</span><span class="sxs-lookup"><span data-stu-id="8e797-165">Column Context Menu</span></span>  
 <span data-ttu-id="8e797-166">As seguintes opções estão disponíveis no menu de contexto exibido quando você clica com o botão direito do mouse no nome de uma coluna em uma tabela ou exibição no painel **Exibição da Fonte de Dados** :</span><span class="sxs-lookup"><span data-stu-id="8e797-166">The following options are available in the context menu displayed by right-clicking the name of a column in a table or view in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="8e797-167">**Nova Medida da Coluna**</span><span class="sxs-lookup"><span data-stu-id="8e797-167">**New Measure from Column**</span></span>  
 <span data-ttu-id="8e797-168">Define uma nova medida no painel **Medidas** baseado na coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-168">Defines a new measure in the **Measures** pane based on the selected column.</span></span>  
  
 <span data-ttu-id="8e797-169">**Explorar dados**</span><span class="sxs-lookup"><span data-stu-id="8e797-169">**Explore Data**</span></span>  
 <span data-ttu-id="8e797-170">Exiba a caixa de diálogo **Explorar Dados** da tabela que contém a coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-170">Display the **Explore Data** dialog box for the table that contains the selected column.</span></span>  
  
 <span data-ttu-id="8e797-171">**Editar Exibição da Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="8e797-171">**Edit Data Source View**</span></span>  
 <span data-ttu-id="8e797-172">Exibe o Designer de Exibição da Fonte de Dados da exibição da fonte de dados que contém a coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-172">Displays Data Source View Designer for the data source view that contains the selected column.</span></span> <span data-ttu-id="8e797-173">Para obter mais informações sobre o Designer de Exibição da Fonte de Dados, consulte [Designer de Exibição da Fonte de Dados &#40;Analysis Services – Dados Multidimensionais&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="8e797-173">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="8e797-174">**Propriedades**</span><span class="sxs-lookup"><span data-stu-id="8e797-174">**Properties**</span></span>  
 <span data-ttu-id="8e797-175">Exibe a janela **Propriedades** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-175">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected column.</span></span>  
  
## <a name="relationship-context-menu"></a><span data-ttu-id="8e797-176">Menu de Contexto da Relação</span><span class="sxs-lookup"><span data-stu-id="8e797-176">Relationship Context Menu</span></span>  
 <span data-ttu-id="8e797-177">As seguintes opções estão disponíveis no menu de contexto exibido quando você clica com o botão direito do mouse em uma relação no painel **Exibição da Fonte de Dados** :</span><span class="sxs-lookup"><span data-stu-id="8e797-177">The following options are available in the context menu displayed by right-clicking a relationship in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="8e797-178">**Editar Exibição da Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="8e797-178">**Edit Data Source View**</span></span>  
 <span data-ttu-id="8e797-179">Exibe o Designer de Exibição da Fonte de Dados que contém a relação selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-179">Displays Data Source View Designer for the data source view that contains the selected relationship.</span></span> <span data-ttu-id="8e797-180">Para obter mais informações sobre o Designer de Exibição da Fonte de Dados, consulte [Designer de Exibição da Fonte de Dados &#40;Analysis Services – Dados Multidimensionais&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="8e797-180">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="8e797-181">**Propriedades**</span><span class="sxs-lookup"><span data-stu-id="8e797-181">**Properties**</span></span>  
 <span data-ttu-id="8e797-182">Exibe a janela **Propriedades** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] da relação selecionada.</span><span class="sxs-lookup"><span data-stu-id="8e797-182">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e797-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e797-183">See Also</span></span>  
 <span data-ttu-id="8e797-184">[Barra de ferramentas &#40;guia estrutura do cubo, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](toolbar-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="8e797-184">[Toolbar &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="8e797-185">[Medidas &#40;guia estrutura do cubo, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](measures-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="8e797-185">[Measures &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](measures-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="8e797-186">[Dimensões &#40;guia estrutura do cubo, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](dimensions-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="8e797-186">[Dimensions &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](dimensions-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="8e797-187">Estrutura de cubo &#40;designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="8e797-187">Cube Structure &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-structure-cube-designer-analysis-services-multidimensional-data.md)  
  
  
