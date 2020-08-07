---
title: Exibição da fonte de dados (guia estrutura da dimensão, designer de dimensão) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.datasourcepane.f1
ms.assetid: c4bd3c5e-8986-448f-b9db-3551f50f0696
author: minewiskan
ms.author: owend
ms.openlocfilehash: fb2529e1835829bc84eec77c18b7ec05da5c4220
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583232"
---
# <a name="data-source-view-dimension-structure-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="ae9ec-102">Exibição da Fonte de Dados (guia Estrutura da Dimensão, Designer de Dimensão) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="ae9ec-102">Data Source View (Dimension Structure Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ae9ec-103">Use o painel **Exibição da Fonte de Dados** para exibir tabelas e colunas da exibição da fonte de dados associada à dimensão selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-103">Use the **Data Source View** pane to view tables and columns from the data source view associated with the selected dimension.</span></span> <span data-ttu-id="ae9ec-104">Esse painel é usado para criar atributos, propriedades de membros, hierarquias e níveis arrastando colunas do painel **Exibição da Fonte de Dados** para o painel **Atributos** ou **Hierarquias e Níveis** .</span><span class="sxs-lookup"><span data-stu-id="ae9ec-104">This pane is used to create attributes, member properties, hierarchies, and levels, by dragging columns from the **Data Source View** pane to the **Attributes** or **Hierarchies and Levels** pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae9ec-105">Opções</span><span class="sxs-lookup"><span data-stu-id="ae9ec-105">Options</span></span>  
 <span data-ttu-id="ae9ec-106">**Exibição da Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-106">**Data Source View**</span></span>  
 <span data-ttu-id="ae9ec-107">Mostra a exibição da fonte de dados associada à dimensão selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-107">Displays the data source view associated with the selected dimension.</span></span>  
  
 <span data-ttu-id="ae9ec-108">**(Mover ponto de vista)**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-108">**(Move viewpoint)**</span></span>  
 <span data-ttu-id="ae9ec-109">Clique no canto inferior direito do painel, entre as barras de rolagem, para selecionar uma área do painel **Exibição da Fonte de Dados** para exibição.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-109">Click the lower right corner of the pane, between the scrollbars, to select an area of the **Data Source View** pane to view.</span></span>  
  
## <a name="diagram-context-menu"></a><span data-ttu-id="ae9ec-110">Menu de Contexto de Diagrama</span><span class="sxs-lookup"><span data-stu-id="ae9ec-110">Diagram Context Menu</span></span>  
 <span data-ttu-id="ae9ec-111">As opções listadas na tabela a seguir estão disponíveis no menu de contexto que é exibido quando você clica com o botão direito do mouse na tela de fundo do diagrama do painel **Exibição da Fonte de Dados** .</span><span class="sxs-lookup"><span data-stu-id="ae9ec-111">The options listed in the following table are available in the context menu displayed by right-clicking the diagram background of the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="ae9ec-112">**Mostrar tabelas**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-112">**Show Tables**</span></span>  
 <span data-ttu-id="ae9ec-113">Exibe a caixa de diálogo **Mostrar Tabelas**.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-113">Displays the **Show Table** dialog box.</span></span> <span data-ttu-id="ae9ec-114">Para obter mais informações sobre a caixa de diálogo **Mostrar Tabela**, consulte [Caixa de diálogo Mostrar Tabela &#40;Analysis Services – Dados Multidimensionais&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae9ec-114">For more information about the **Show Table** dialog box, see [Show Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae9ec-115">**Mostrar Todas as Tabelas**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-115">**Show All Tables**</span></span>  
 <span data-ttu-id="ae9ec-116">Exibe no painel todas as tabelas incluídas na exibição da fonte de dados associada à dimensão.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-116">Displays in the pane all tables included in the data source view associated with the dimension.</span></span>  
  
 <span data-ttu-id="ae9ec-117">**Mostrar Somente Tabelas Usadas**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-117">**Show Only Used Tables**</span></span>  
 <span data-ttu-id="ae9ec-118">Exibe no painel somente as tabelas usadas pela dimensão da exibição da fonte de dados associada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-118">Displays in the pane only those tables used by the dimension from the associated data source view.</span></span>  
  
 <span data-ttu-id="ae9ec-119">**Mostrar nomes amigáveis**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-119">**Show Friendly Names**</span></span>  
 <span data-ttu-id="ae9ec-120">Selecione para mostrar nomes amigáveis dos objetos no painel.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-120">Select to show friendly names for the objects in the pane.</span></span>  
  
 <span data-ttu-id="ae9ec-121">**Selecionar tudo**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-121">**Select All**</span></span>  
 <span data-ttu-id="ae9ec-122">Seleciona todos os objetos no painel.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-122">Selects all of the objects in the pane.</span></span>  
  
 <span data-ttu-id="ae9ec-123">**Localizar Tabela**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-123">**Find Table**</span></span>  
 <span data-ttu-id="ae9ec-124">Exibe a caixa de diálogo **Localizar Tabela**.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-124">Displays the **Find Table** dialog box.</span></span> <span data-ttu-id="ae9ec-125">Para obter mais informações sobre a caixa de diálogo **Localizar Tabela**, consulte [Caixa de diálogo Localizar Tabela &#40;Analysis Services – Dados Multidimensionais&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae9ec-125">For more information about the **Find Table** dialog box, see [Find Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae9ec-126">**Organizar Tabelas**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-126">**Arrange Tables**</span></span>  
 <span data-ttu-id="ae9ec-127">Organiza os objetos no painel de acordo com o layout especificado selecionando **Alternar para Layout Diagonal** ou **Alternar para Layout Retangular**.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-127">Arranges the objects in the pane according to the layout specified by selecting either **Switch to Diagonal Layout** or **Switch to Rectangular Layout**.</span></span>  
  
 <span data-ttu-id="ae9ec-128">**Alternar para Layout Diagonal**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-128">**Switch to Diagonal Layout**</span></span>  
 <span data-ttu-id="ae9ec-129">Selecione para organizar objetos em um padrão diagonal.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-129">Select to arrange objects in a diagonal pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae9ec-130"> Esta opção será exibida somente se a opção **Alternar para Layout Retangular** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-130">This option is displayed only if **Switch to Rectangular Layout** is selected.</span></span>  
  
 <span data-ttu-id="ae9ec-131">**Alternar para Layout Retangular**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-131">**Switch to Rectangular Layout**</span></span>  
 <span data-ttu-id="ae9ec-132">Selecione para organizar objetos em um padrão retangular.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-132">Select to arrange objects in a rectangular pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae9ec-133"> Esta opção será exibida somente se a opção **Alternar para Layout Diagonal** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-133">This option is displayed only if **Switch to Diagonal Layout** is selected.</span></span>  
  
 <span data-ttu-id="ae9ec-134">**Editar Exibição da Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-134">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ae9ec-135">Exibe o **Designer da Exibição da Fonte de Dados** da exibição da fonte de dados associada à dimensão.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-135">Displays **Data Source View Designer** for the data source view associated with the dimension.</span></span> <span data-ttu-id="ae9ec-136">Para obter mais informações sobre o **Designer de Exibição da Fonte de Dados**, consulte [Designer de Exibição da Fonte de Dados &#40;Analysis Services – Dados Multidimensionais&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae9ec-136">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae9ec-137">**Mostrar Exibição da Fonte de Dados em**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-137">**Show Data Source View In**</span></span>  
 <span data-ttu-id="ae9ec-138">Selecione uma das seguintes opções para ativar/desativar a exibição do painel **Exibição da Fonte de Dados** nos seguintes modos:</span><span class="sxs-lookup"><span data-stu-id="ae9ec-138">Select one of the following options to toggle between viewing the **Data Source View** pane in the following modes:</span></span>  
  
-   <span data-ttu-id="ae9ec-139">Diagrama</span><span class="sxs-lookup"><span data-stu-id="ae9ec-139">Diagram</span></span>  
  
     <span data-ttu-id="ae9ec-140">Exibe um diagrama das tabelas e colunas associadas à dimensão atual.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-140">Displays a diagram of the tables and columns associated with the current dimension.</span></span>  
  
-   <span data-ttu-id="ae9ec-141">Árvore</span><span class="sxs-lookup"><span data-stu-id="ae9ec-141">Tree</span></span>  
  
     <span data-ttu-id="ae9ec-142">Exibe uma árvore que contém tabelas e colunas associadas à dimensão atual.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-142">Displays a tree view that contains the tables and columns associated with the current dimension.</span></span>  
  
 <span data-ttu-id="ae9ec-143">**Copiar Diagrama de**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-143">**Copy Diagram From**</span></span>  
 <span data-ttu-id="ae9ec-144">Selecione um dos diagramas incluídos na exibição da fonte de dados associada à dimensão para exibi-lo no painel **Exibição da Fonte de Dados** .</span><span class="sxs-lookup"><span data-stu-id="ae9ec-144">Select one of the diagrams included in the data source view associated with the dimension to display it in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="ae9ec-145">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-145">**Zoom**</span></span>  
 <span data-ttu-id="ae9ec-146">Selecione uma opção de zoom disponível.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-146">Select an available zoom option.</span></span>  
  
 <span data-ttu-id="ae9ec-147">**Propriedades**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-147">**Properties**</span></span>  
 <span data-ttu-id="ae9ec-148">Exibe a janela **Propriedades** no **SQL Server Data Tools** para a exibição da fonte de dados associada à dimensão.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-148">Displays the **Properties** window in **SQL Server Data Tools** for the data source view associated with the dimension.</span></span>  
  
## <a name="table-context-menu"></a><span data-ttu-id="ae9ec-149">Menu de Contexto da Tabela</span><span class="sxs-lookup"><span data-stu-id="ae9ec-149">Table Context Menu</span></span>  
 <span data-ttu-id="ae9ec-150">As opções listadas na tabela a seguir estão disponíveis no menu de contexto exibido quando você clica com o botão direito do mouse no nome de uma tabela ou exibição no painel **Exibição da Fonte de Dados** .</span><span class="sxs-lookup"><span data-stu-id="ae9ec-150">The options listed in the following table are available in the context menu displayed by right-clicking the name of a table or view in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="ae9ec-151">**Mostrar Tabelas Relacionadas**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-151">**Show Related Tables**</span></span>  
 <span data-ttu-id="ae9ec-152">Exibe no painel as tabelas relacionadas à tabela selecionada na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-152">Displays in the pane the tables related to the selected table in the data source view.</span></span>  
  
 <span data-ttu-id="ae9ec-153">**Ocultar Tabela**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-153">**Hide Table**</span></span>  
 <span data-ttu-id="ae9ec-154">Remove a tabela do painel.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-154">Removes the table from the pane.</span></span>  
  
 <span data-ttu-id="ae9ec-155">**Explorar dados**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-155">**Explore Data**</span></span>  
 <span data-ttu-id="ae9ec-156">Exibe a caixa de diálogo **Explorar Dados** para a tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-156">Displays the **Explore Data** dialog box for the selected table.</span></span>  
  
 <span data-ttu-id="ae9ec-157">**Editar Exibição da Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-157">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ae9ec-158">Exibe o **Designer de exibição da fonte** de dados da exibição da fonte de dados que contém a tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-158">Displays **Data Source View Designer** for the data source view that contains the selected table.</span></span> <span data-ttu-id="ae9ec-159">Para obter mais informações sobre o **Designer de Exibição da Fonte de Dados**, consulte [Designer de Exibição da Fonte de Dados &#40;Analysis Services – Dados Multidimensionais&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae9ec-159">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae9ec-160">**Propriedades**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-160">**Properties**</span></span>  
 <span data-ttu-id="ae9ec-161">Exibe a janela **Propriedades** no **SQL Server Data Tools** da tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-161">Displays the **Properties** window in **SQL Server Data Tools** for the selected table.</span></span>  
  
## <a name="column-context-menu"></a><span data-ttu-id="ae9ec-162">Menu de Contexto da Coluna</span><span class="sxs-lookup"><span data-stu-id="ae9ec-162">Column Context Menu</span></span>  
 <span data-ttu-id="ae9ec-163">As opções listadas na tabela a seguir estão disponíveis no menu de contexto exibido quando você clica com o botão direito do mouse no nome de uma coluna em uma tabela ou exibição no painel **Exibição da Fonte de Dados** .</span><span class="sxs-lookup"><span data-stu-id="ae9ec-163">The options listed in the following table are available in the context menu displayed by right-clicking the name of a column in a table or view in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="ae9ec-164">**Novo Atributo da Coluna**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-164">**New Attribute from Column**</span></span>  
 <span data-ttu-id="ae9ec-165">Exibe no painel as tabelas relacionadas à tabela selecionada na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-165">Displays in the pane the tables related to the selected table in the data source view.</span></span>  
  
 <span data-ttu-id="ae9ec-166">**Explorar dados**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-166">**Explore Data**</span></span>  
 <span data-ttu-id="ae9ec-167">Exiba a caixa de diálogo **Explorar Dados** da tabela que contém a coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-167">Display the **Explore Data** dialog box for the table that contains the selected column.</span></span>  
  
 <span data-ttu-id="ae9ec-168">**Editar Exibição da Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-168">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ae9ec-169">Exibe o **Designer de exibição da fonte** de dados da exibição da fonte de dados que contém a coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-169">Displays **Data Source View Designer** for the data source view that contains the selected column.</span></span> <span data-ttu-id="ae9ec-170">Para obter mais informações sobre o **Designer de Exibição da Fonte de Dados**, consulte [Designer de Exibição da Fonte de Dados &#40;Analysis Services – Dados Multidimensionais&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae9ec-170">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae9ec-171">**Propriedades**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-171">**Properties**</span></span>  
 <span data-ttu-id="ae9ec-172">Exibe a janela **Propriedades** no **SQL Server Data Tools** da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-172">Displays the **Properties** window in **SQL Server Data Tools** for the selected column.</span></span>  
  
## <a name="relationship-context-menu"></a><span data-ttu-id="ae9ec-173">Menu de Contexto da Relação</span><span class="sxs-lookup"><span data-stu-id="ae9ec-173">Relationship Context Menu</span></span>  
 <span data-ttu-id="ae9ec-174">As opções listadas na tabela a seguir são disponíveis no menu de contexto que é exibido quando você clica com o botão direito do mouse em uma relação no painel **Exibição da Fonte de Dados** .</span><span class="sxs-lookup"><span data-stu-id="ae9ec-174">The options listed in the following table are available in the context menu displayed by right-clicking a relationship in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="ae9ec-175">**Editar Exibição da Fonte de Dados**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-175">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ae9ec-176">Exibe o **Designer de exibição da fonte** de dados da exibição da fonte de dados que contém a relação selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-176">Displays **Data Source View Designer** for the data source view that contains the selected relationship.</span></span> <span data-ttu-id="ae9ec-177">Para obter mais informações sobre o **Designer de Exibição da Fonte de Dados**, consulte [Designer de Exibição da Fonte de Dados &#40;Analysis Services – Dados Multidimensionais&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae9ec-177">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae9ec-178">**Propriedades**</span><span class="sxs-lookup"><span data-stu-id="ae9ec-178">**Properties**</span></span>  
 <span data-ttu-id="ae9ec-179">Exibe a janela **Propriedades** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] da relação selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ec-179">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9ec-180">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ae9ec-180">See Also</span></span>  
 <span data-ttu-id="ae9ec-181">[Estrutura de dimensão &#40;designer de dimensão&#41; &#40;Analysis Services de dados multidimensionais&#41;](dimension-structure-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ae9ec-181">[Dimension Structure &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](dimension-structure-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="ae9ec-182">[Barra de ferramentas &#40;guia estrutura da dimensão, designer de dimensão&#41; &#40;Analysis Services de dados multidimensionais&#41;](toolbar-dimension-structure-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ae9ec-182">[Toolbar &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-dimension-structure-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="ae9ec-183">[Atributos &#40;guia estrutura da dimensão, designer de dimensão&#41; &#40;Analysis Services de dados multidimensionais&#41;](attributes-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ae9ec-183">[Attributes &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](attributes-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="ae9ec-184">Hierarquias &#40;guia estrutura da dimensão, designer de dimensão&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="ae9ec-184">Hierarchies &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](hierarchies-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
