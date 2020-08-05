---
title: Adicionar, alterar ou excluir um mapa ou uma camada do mapa (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10526"
- sql12.rtp.rptdesigner.maptilelayerproperties.general.f1
- "10529"
- "10525"
- "10535"
- sql12.rtp.rptdesigner.mappolygonlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layervisibility.f1
- sql12.rtp.rptdesigner.mappointlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layerfilters.f1
- "10524"
- sql12.rtp.rptdesigner.maplayerproperties.general.f1
- sql12.rtp.rptdesigner.maplinelayerproperties.general.f1
- "10532"
- "10528"
- "10527"
- sql12.rtp.rptdesigner.maplayerproperties.analyticaldata.f1
ms.assetid: 6e89815e-187e-45bf-bf63-3d5c4a246360
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4e9fd178d36ee3322c0bd94dd44d621439139b71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573770"
---
# <a name="add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs"></a><span data-ttu-id="e8c15-102">Adicionar, alterar ou excluir um mapa ou uma camada do mapa (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e8c15-102">Add, Change, or Delete a Map or Map Layer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e8c15-103">Um mapa é uma coleção de camadas.</span><span class="sxs-lookup"><span data-stu-id="e8c15-103">A map is a collection of layers.</span></span> <span data-ttu-id="e8c15-104">Quando você adiciona um mapa a um relatório, define a primeira camada.</span><span class="sxs-lookup"><span data-stu-id="e8c15-104">When you add a map to a report, you define the first layer.</span></span> <span data-ttu-id="e8c15-105">Você pode criar mais camadas usando o assistente de camada do mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-105">You can create additional layers by using the map layer wizard.</span></span>  
  
 <span data-ttu-id="e8c15-106">A maneira mais fácil para adicionar, remover ou alterar as opções de uma camada é usar o assistente de camada do mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-106">The easiest way to add, remove, or change options for a layer is to use the map layer wizard.</span></span> <span data-ttu-id="e8c15-107">Você também pode alterar manualmente as opções do painel Mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-107">You can also change options manually from the Map pane.</span></span> <span data-ttu-id="e8c15-108">Para exibir o painel **Mapa** , clique no mapa na superfície de design do relatório.</span><span class="sxs-lookup"><span data-stu-id="e8c15-108">To display the **Map** pane, click in the map on the report design surface.</span></span> <span data-ttu-id="e8c15-109">A figura seguinte exibe as partes do painel:</span><span class="sxs-lookup"><span data-stu-id="e8c15-109">The following figure displays the parts of the pane:</span></span>  
  
 <span data-ttu-id="e8c15-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span><span class="sxs-lookup"><span data-stu-id="e8c15-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span></span>  
  
 <span data-ttu-id="e8c15-111">As camadas do mapa são desenhadas de baixo para cima para que apareçam no painel Mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-111">Map layers are drawn from bottom to top in the order that they appear in the Map pane.</span></span> <span data-ttu-id="e8c15-112">Na figura anterior, a camada da peça é desenhada primeiro e a camada de polígono é desenhada por último.</span><span class="sxs-lookup"><span data-stu-id="e8c15-112">In the previous figure, the tile layer is drawn first and the polygon layer is drawn last.</span></span> <span data-ttu-id="e8c15-113">As camadas desenhadas posteriormente podem ocultar elementos do mapa nas camadas desenhadas antes.</span><span class="sxs-lookup"><span data-stu-id="e8c15-113">Layers that are drawn later might hide map elements on layers that are drawn earlier.</span></span> <span data-ttu-id="e8c15-114">Você pode alterar a ordem das camadas usando as teclas de direção na barra de ferramentas do painel Mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-114">You can change the order of layers by using the arrow keys on the Map pane toolbar.</span></span> <span data-ttu-id="e8c15-115">Para mostrar ou ocultar camadas, alterne o ícone de visibilidade.</span><span class="sxs-lookup"><span data-stu-id="e8c15-115">To show or hide layers, toggle the visibility icon.</span></span> <span data-ttu-id="e8c15-116">Você pode alterar a transparência de uma camada na `Visibility` página da caixa de diálogo Propriedades de **dados da camada** .</span><span class="sxs-lookup"><span data-stu-id="e8c15-116">You can change the transparency of a layer on the `Visibility` page of the **Layer Data** properties dialog box.</span></span>  
  
 <span data-ttu-id="e8c15-117">A tabela a seguir exibe os ícones da barra de ferramentas do painel **Mapa** .</span><span class="sxs-lookup"><span data-stu-id="e8c15-117">The following table displays the toolbar icons for the **Map** pane.</span></span>  
  
|<span data-ttu-id="e8c15-118">Símbolo</span><span class="sxs-lookup"><span data-stu-id="e8c15-118">Symbol</span></span>|<span data-ttu-id="e8c15-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8c15-119">Description</span></span>|<span data-ttu-id="e8c15-120">Quando usar</span><span class="sxs-lookup"><span data-stu-id="e8c15-120">When to use</span></span>|  
|------------|-----------------|-----------------|  
|<span data-ttu-id="e8c15-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span><span class="sxs-lookup"><span data-stu-id="e8c15-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span></span>|<span data-ttu-id="e8c15-122">Assistente de Camada do Mapa</span><span class="sxs-lookup"><span data-stu-id="e8c15-122">Map Layer Wizard</span></span>|<span data-ttu-id="e8c15-123">Para adicionar uma camada usando um assistente, clique em **Assistente de nova camada**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-123">To add a layer by using a wizard, click **New layer wizard**.</span></span>|  
|<span data-ttu-id="e8c15-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span><span class="sxs-lookup"><span data-stu-id="e8c15-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span></span>|<span data-ttu-id="e8c15-125">Adicionar Camada</span><span class="sxs-lookup"><span data-stu-id="e8c15-125">Add Layer</span></span>|<span data-ttu-id="e8c15-126">Para adicionar uma camada manualmente, clique em **Adicionar Camada**e clique no tipo de camada do mapa a ser adicionada.</span><span class="sxs-lookup"><span data-stu-id="e8c15-126">To manually add a layer, click **Add Layer**, and then click the type of map layer to add.</span></span>|  
|<span data-ttu-id="e8c15-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span><span class="sxs-lookup"><span data-stu-id="e8c15-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span></span>|<span data-ttu-id="e8c15-128">Camada de Polígono</span><span class="sxs-lookup"><span data-stu-id="e8c15-128">Polygon Layer</span></span>|<span data-ttu-id="e8c15-129">Adicione uma camada do mapa que exiba áreas ou formas com base em conjuntos de coordenadas de polígonos.</span><span class="sxs-lookup"><span data-stu-id="e8c15-129">Add a map layer that displays areas or shapes that are based sets of polygon coordinates.</span></span>|  
|<span data-ttu-id="e8c15-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span><span class="sxs-lookup"><span data-stu-id="e8c15-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span></span>|<span data-ttu-id="e8c15-131">Camada de Linha</span><span class="sxs-lookup"><span data-stu-id="e8c15-131">Line Layer</span></span>|<span data-ttu-id="e8c15-132">Adicione uma camada do mapa que exiba caminhos ou rotas com base em conjuntos de coordenadas de linha.</span><span class="sxs-lookup"><span data-stu-id="e8c15-132">Add a map layer that displays paths or routes that are based on sets of line coordinates.</span></span>|  
|<span data-ttu-id="e8c15-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span><span class="sxs-lookup"><span data-stu-id="e8c15-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span></span>|<span data-ttu-id="e8c15-134">Camada de Ponto</span><span class="sxs-lookup"><span data-stu-id="e8c15-134">Point Layer</span></span>|<span data-ttu-id="e8c15-135">Adicione uma camada do mapa que exiba locais com base em conjuntos de coordenadas de ponto.</span><span class="sxs-lookup"><span data-stu-id="e8c15-135">Add a map layer that displays locations that are based on sets of point coordinates.</span></span>|  
|<span data-ttu-id="e8c15-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span><span class="sxs-lookup"><span data-stu-id="e8c15-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span></span>|<span data-ttu-id="e8c15-137">Camada de Peça</span><span class="sxs-lookup"><span data-stu-id="e8c15-137">Tile Layer</span></span>|<span data-ttu-id="e8c15-138">Adicione uma camada do mapa que exiba peças de Mapa do Bing que correspondam à área de exibição do mapa atual definida pelo visor.</span><span class="sxs-lookup"><span data-stu-id="e8c15-138">Add a map layer that displays Bing Map tiles that correspond to the current map view area that is defined by the viewport.</span></span>|  
  
 <span data-ttu-id="e8c15-139">Na parte inferior do painel Mapa fica a área de exibição de Mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-139">At the bottom of the Map pane is the Map view area.</span></span> <span data-ttu-id="e8c15-140">Para alterar o centro ou as opções de zoom do mapa, use as teclas de direção para ajustar o centro do visor e o controle deslizante para ajustar o nível de zoom.</span><span class="sxs-lookup"><span data-stu-id="e8c15-140">To change the center or zoom options for the map, use the arrow keys to adjust the view center and the slider to adjust the zoom level.</span></span>  
  
 <span data-ttu-id="e8c15-141">Para obter mais informações sobre camadas, consulte [Mapas &#40;Construtor de Relatórios e SSRS&#41;](maps-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e8c15-141">For more information about layers, see [Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-add-a-layer-from-the-map-layer-wizard"></a><a name="AddLayer"></a> <span data-ttu-id="e8c15-142">Para adicionar uma camada com o assistente de camada do mapa</span><span class="sxs-lookup"><span data-stu-id="e8c15-142">To add a layer from the map layer wizard</span></span>  
  
-   <span data-ttu-id="e8c15-143">Na Faixa de Opções, no menu **Inserir** , clique em **Mapa**e em **Mapa Wizard.**</span><span class="sxs-lookup"><span data-stu-id="e8c15-143">From the Ribbon, on the **Insert** menu, click **Map**, and then click **Map Wizard.**</span></span> <span data-ttu-id="e8c15-144">. O assistente o permite a adição de uma camada ao mapa existente.</span><span class="sxs-lookup"><span data-stu-id="e8c15-144">The wizard enables you to add a layer to the existing map.</span></span> <span data-ttu-id="e8c15-145">A maioria das páginas de assistente são idênticas entre o assistente de mapa e o assistente de camada do mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-145">Most wizard pages are identical between the map wizard and the map layer wizard.</span></span>  
  
     <span data-ttu-id="e8c15-146">Para obter mais informações, consulte [Assistente de Mapa e Assistente de Camada do Mapa &#40;Construtor de Relatórios e SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e8c15-146">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-change-options-for-a-layer-by-using-the-map-layer-wizard"></a><a name="ChangeLayer"></a> <span data-ttu-id="e8c15-147">Para alterar opções para uma camada usando o assistente de camada do mapa</span><span class="sxs-lookup"><span data-stu-id="e8c15-147">To change options for a layer by using the map layer wizard</span></span>  
  
-   <span data-ttu-id="e8c15-148">Execute o assistente de camada do mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-148">Run the map layer wizard.</span></span> <span data-ttu-id="e8c15-149">Este assistente permite alterar opções para uma camada que você criou usando o assistente de camada do mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-149">This wizard enables you to change options for a layer that you created by using the map layer wizard.</span></span> <span data-ttu-id="e8c15-150">No painel Mapa, clique com o botão direito do mouse na camada e, na barra de ferramentas, clique no botão do assistente de camada (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="e8c15-150">In the Map pane, right-click the layer, and on the toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
     <span data-ttu-id="e8c15-151">Para obter mais informações, consulte [Assistente de Mapa e Assistente de Camada do Mapa &#40;Construtor de Relatórios e SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e8c15-151">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-add-a-point-line-or-polygon-layer-from-the-map-pane-toolbar"></a><a name="AddVectorLayer"></a> <span data-ttu-id="e8c15-152">Para adicionar uma camada de pontos, linhas ou polígonos da barra de ferramentas do painel Mapa</span><span class="sxs-lookup"><span data-stu-id="e8c15-152">To add a point, line, or polygon layer from the Map pane toolbar</span></span>  
  
1.  <span data-ttu-id="e8c15-153">Clique no mapa até que o painel Mapa apareça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-153">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="e8c15-154">Na barra de ferramentas, clique no botão **Adicionar Camada** e, na lista suspensa, clique no tipo de camada que você deseja adicionar: **ponto**, **linha** ou **polígono**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-154">On the toolbar, click the **Add Layer** button, and from the drop-down list, click the type of layer that you want to add: **Point**, **Line**, or **Polygon**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8c15-155">Embora seja possível adicionar uma camada do mapa e configurá-la manualmente, é recomendável usar o assistente de camada do mapa para adicionar novas camadas.</span><span class="sxs-lookup"><span data-stu-id="e8c15-155">Although you can add a map layer and configure it manually, we recommend that you use the map layer wizard to add new layers.</span></span> <span data-ttu-id="e8c15-156">Para iniciar o assistente por meio da barra de ferramentas do painel Mapa, clique no botão do assistente de camada (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="e8c15-156">To launch the wizard from the Map pane toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
3.  <span data-ttu-id="e8c15-157">Clique com o botão direito do mouse na camada e clique em **Dados da Camada**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-157">Right-click the layer, and then click **Layer Data**.</span></span>  
  
4.  <span data-ttu-id="e8c15-158">Em **Usar dados espaciais de**, selecione a fonte de dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="e8c15-158">In **Use spatial data from**, select the source of spatial data.</span></span> <span data-ttu-id="e8c15-159">As opções variam com base na seleção.</span><span class="sxs-lookup"><span data-stu-id="e8c15-159">Options vary based on your selection.</span></span>  
  
     <span data-ttu-id="e8c15-160">Para visualizar dados analíticos de seu relatório nesta camada, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e8c15-160">If you want to visualize analytical from your report on this layer, do the following:</span></span>  
  
    1.  <span data-ttu-id="e8c15-161">Clique em **Dados Analíticos**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-161">Click **Analytical data**.</span></span>  
  
    2.  <span data-ttu-id="e8c15-162">Em **Conjunto de dados analítico**, clique no nome do conjunto de dados que contém os dados analíticos e os campos de correspondência para criar uma relação entre dados analíticos e espaciais.</span><span class="sxs-lookup"><span data-stu-id="e8c15-162">In **Analytical dataset**, click the name of the dataset that contains analytical data and the match fields to build a relationship between analytical and spatial data.</span></span>  
  
    3.  <span data-ttu-id="e8c15-163">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-163">Click **Add**.</span></span>  
  
    4.  <span data-ttu-id="e8c15-164">Digite o nome do campo de correspondência do conjunto de dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="e8c15-164">Type the name of the match field from the spatial dataset.</span></span>  
  
    5.  <span data-ttu-id="e8c15-165">Digite o nome do campo de correspondência do conjunto de dados analíticos.</span><span class="sxs-lookup"><span data-stu-id="e8c15-165">Type the name of the match field from the analytical dataset.</span></span>  
  
     <span data-ttu-id="e8c15-166">Para obter mais informações sobre como vincular dados espaciais e analíticos, veja [Personalizar os dados e a exibição de um mapa ou de uma camada do mapa &#40;Construtor de Relatórios e SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e8c15-166">For more information about linking spatial and analytical data, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-filter-analytical-data-for-the-layer"></a><a name="FilterAnalyticalData"></a> <span data-ttu-id="e8c15-167">Para filtrar dados analíticos para a camada</span><span class="sxs-lookup"><span data-stu-id="e8c15-167">To filter analytical data for the layer</span></span>  
  
1.  <span data-ttu-id="e8c15-168">Clique no mapa até que o painel Mapa apareça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-168">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="e8c15-169">Clique com o botão direito do mouse na camada do painel Mapa e clique em  **Dados da Camada**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-169">Right-click the layer in the Map pane, and then click  **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="e8c15-170">Clique em **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-170">Click **Filters**.</span></span>  
  
4.  <span data-ttu-id="e8c15-171">Defina uma equação de filtro para limitar os dados analíticos que são usados na exibição de mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-171">Define a filter equation to limit the analytical data that is used in the map display.</span></span> <span data-ttu-id="e8c15-172">Para obter mais informações, consulte [Exemplos de equações de filtro &#40;Construtor de Relatórios e SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e8c15-172">For more information, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-control-point-properties-for-a-point-layer-or-for-polygon-center-points"></a><a name="PointProperties"></a> <span data-ttu-id="e8c15-173">Para controlar propriedades de ponto para uma camada de ponto ou para pontos centrais de polígono</span><span class="sxs-lookup"><span data-stu-id="e8c15-173">To control point properties for a point layer or for polygon center points</span></span>  
  
1.  <span data-ttu-id="e8c15-174">Selecione **Geral** na caixa de diálogo **Propriedades do Ponto do Mapa** para alterar as opções de rótulo, dica de ferramenta e tipo de marcador dos seguintes elementos do mapa:</span><span class="sxs-lookup"><span data-stu-id="e8c15-174">Select **General** on the **Map Point Properties** dialog box to change label, tooltip, and marker type options for the following map elements:</span></span>  
  
    -   <span data-ttu-id="e8c15-175">Todos os pontos dinâmicos ou inseridos em uma camada de ponto.</span><span class="sxs-lookup"><span data-stu-id="e8c15-175">All dynamic or embedded points on a point layer.</span></span> <span data-ttu-id="e8c15-176">As regras de cores, as regras de tamanho e as regras de tipo de marcador para pontos substituem essas opções.</span><span class="sxs-lookup"><span data-stu-id="e8c15-176">Color rules, size rules, and marker type rules for points override these options.</span></span> <span data-ttu-id="e8c15-177">Para substituir as opções de um ponto inserido específico, use a página [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) .</span><span class="sxs-lookup"><span data-stu-id="e8c15-177">To override options for a specific embedded point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  
  
    -   <span data-ttu-id="e8c15-178">O ponto central de todos os polígonos dinâmicos ou inseridos em uma camada de polígono.</span><span class="sxs-lookup"><span data-stu-id="e8c15-178">The center point for all dynamic or embedded polygons on a polygon layer.</span></span> <span data-ttu-id="e8c15-179">As regras de cores, as regras de tamanho e as regras de tipo de marcador para pontos centrais substituem essas opções.</span><span class="sxs-lookup"><span data-stu-id="e8c15-179">Color rules, size rules, and marker type rules for center points override these options.</span></span> <span data-ttu-id="e8c15-180">Para substituir as opções de um ponto central específico, use a página [Caixa de diálogo Mapear Propriedades de Ponto Inserido, Marcador](../map-embedded-point-properties-dialog-box-marker.md) .</span><span class="sxs-lookup"><span data-stu-id="e8c15-180">To override options for a specific center point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  

##  <a name="to-specify-embedded-data-as-a-source-of-spatial-data"></a><a name="Embedded"></a> <span data-ttu-id="e8c15-181">Para especificar dados inseridos como uma fonte de dados espaciais</span><span class="sxs-lookup"><span data-stu-id="e8c15-181">To specify embedded data as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="e8c15-182">Clique no mapa até que o painel Mapa apareça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-182">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="e8c15-183">Clique com o botão direito do mouse na camada e clique em **Dados da Camada**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-183">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="e8c15-184">Em **Usar dados espaciais de**, selecione **Dados inseridos no relatório**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-184">In **Use spatial data from**, select **Data embedded in report**.</span></span>  
  
4.  <span data-ttu-id="e8c15-185">Para carregar elementos do mapa de um relatório existente ou criar elementos do mapa com base em um arquivo ESRI, clique em **Procurar**, aponte para o arquivo e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-185">To load map elements from an existing report or to create map elements based on an ESRI file, click **Browse**, point to the file, and then click **Open**.</span></span> <span data-ttu-id="e8c15-186">Os elementos do mapa são inseridos nesta definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="e8c15-186">The map elements are embedded in this report definition.</span></span> <span data-ttu-id="e8c15-187">Os dados espaciais para os quais você aponta devem corresponder ao tipo da camada.</span><span class="sxs-lookup"><span data-stu-id="e8c15-187">The spatial data that you point to must match the layer type.</span></span> <span data-ttu-id="e8c15-188">Por exemplo, para uma camada de ponto, você deve apontar para dados espaciais que especifiquem conjuntos de coordenadas de ponto.</span><span class="sxs-lookup"><span data-stu-id="e8c15-188">For example, for a point layer, you must point to spatial data that specifies sets of point coordinates.</span></span>  
  
5.  <span data-ttu-id="e8c15-189">Em **Campo espacial**, especifique o nome do campo que contém dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="e8c15-189">In **Spatial field**, specify the name of the field that contains spatial data.</span></span> <span data-ttu-id="e8c15-190">Talvez seja necessário determinar esse nome com base na fonte de dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="e8c15-190">You might need to determine this name from the source of spatial data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8c15-191">Se você não souber o nome do campo e navegou para um Arquivo de Forma ESRI, use a opção **Link para arquivo de forma ESRI** , em vez desta opção.</span><span class="sxs-lookup"><span data-stu-id="e8c15-191">If you do not know the name of the field and you browsed to an ESRI Shapefile, use the **Link to ESRI shape file option** instead of this option.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-an-esri-shapefile-as-a-source-of-spatial-data"></a><a name="ESRI"></a> <span data-ttu-id="e8c15-192">Para especificar um Arquivo de Forma ESRI como uma fonte de dados espaciais</span><span class="sxs-lookup"><span data-stu-id="e8c15-192">To specify an ESRI Shapefile as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="e8c15-193">Clique no mapa até que o painel Mapa apareça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-193">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="e8c15-194">Clique com o botão direito do mouse na camada e clique em **Dados da Camada**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-194">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="e8c15-195">Em **Usar dados espaciais de**, selecione **Link para Arquivo de Forma ESRI**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-195">In **Use spatial data from**, select **Link to ESRI Shapefile**.</span></span>  
  
4.  <span data-ttu-id="e8c15-196">Em **Nome do arquivo**, digite o local de um Arquivo de Forma ou clique em **Procurar** para selecionar um Arquivo de Forma ESRI.</span><span class="sxs-lookup"><span data-stu-id="e8c15-196">In **File name**, type the location of an ESRI Shapefile, or click **Browse** to select an ESRI Shapefile.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8c15-197">Se o Arquivo de Forma estiver em seu computador local, os dados espaciais serão inseridos na definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="e8c15-197">If the Shapefile is on your local computer, the spatial data is embedded in the report definition.</span></span> <span data-ttu-id="e8c15-198">Para recuperar os dados dinamicamente quando o relatório for processado, carregue o arquivo ESRI .shp e seu arquivo de suporte .dbf no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e8c15-198">To retrieve the data dynamically when the report is processed, you must upload the ESRI .shp file and its .dbf support file to the report server.</span></span> <span data-ttu-id="e8c15-199">Para obter mais informações, consulte "Como carregar um arquivo ou relatório (Gerenciador de Relatórios)" na [documentação do Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8c15-199">For more information, see " How to: Upload a File or Report (Report Manager)" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-report-dataset-field-as-a-source-of-spatial-data"></a><a name="DatasetField"></a> <span data-ttu-id="e8c15-200">Para especificar um campo de conjunto de dados de relatório como uma fonte de dados espaciais</span><span class="sxs-lookup"><span data-stu-id="e8c15-200">To specify a report dataset field as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="e8c15-201">Clique no mapa até que o painel Mapa apareça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-201">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="e8c15-202">Clique com o botão direito do mouse na camada e clique em **Dados da Camada**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-202">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="e8c15-203">Em **Usar dados espaciais de**, selecione **Campo espacial em um conjunto de dados**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-203">In **Use spatial data from**, select **Spatial field in a dataset**.</span></span>  
  
4.  <span data-ttu-id="e8c15-204">Em **Nome de conjunto de dados**, clique no nome de um conjunto de dados no relatório que contém os dados espaciais desejados.</span><span class="sxs-lookup"><span data-stu-id="e8c15-204">In **Dataset name**, click the name of a dataset in the report that contains that spatial data that you want.</span></span>  
  
5.  <span data-ttu-id="e8c15-205">Em **Nome do campo espacial**, clique no nome do campo no conjunto de dados que contém dados espaciais.</span><span class="sxs-lookup"><span data-stu-id="e8c15-205">In **Spatial field name**, click the name of the field in the dataset that contains spatial data.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-add-a-tile-layer"></a><a name="TileLayer"></a> <span data-ttu-id="e8c15-206">Para adicionar uma camada de peça</span><span class="sxs-lookup"><span data-stu-id="e8c15-206">To add a tile layer</span></span>  
  
1.  <span data-ttu-id="e8c15-207">Clique no mapa até que o painel Mapa apareça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-207">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="e8c15-208">Na barra de ferramentas, clique no botão **Adicionar Camada** e, na lista suspensa, clique em **Camada Lado a Lado**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-208">On the toolbar, click the **Add Layer** button, and from the drop-down list, click **Tile Layer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8c15-209"> Para obter mais informações sobre o uso de peças de mapa do Bing no seu relatório, consulte [termos de uso adicionais](https://go.microsoft.com/fwlink/?LinkId=151371) e a [Política de Privacidade](https://go.microsoft.com/fwlink/?LinkId=151372).</span><span class="sxs-lookup"><span data-stu-id="e8c15-209">For more information about the use of Bing map tiles in your report, see [Additional Terms of Use](https://go.microsoft.com/fwlink/?LinkId=151371) and [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=151372).</span></span>  
  
3.  <span data-ttu-id="e8c15-210">Clique com o botão direito do mouse na camada lado a lado no painel Mapa e clique em **Propriedades da Peça**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-210">Right-click the tile layer in the Map pane, and then click **Tile Properties**.</span></span>  
  
4.  <span data-ttu-id="e8c15-211">Em **Opções da peça**, selecione um estilo de peça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-211">In **Tile options**, select a tile style.</span></span> <span data-ttu-id="e8c15-212">Se as peças de mapas do Bing estiverem disponíveis, a camada na superfície de design será atualizada com o estilo selecionado.</span><span class="sxs-lookup"><span data-stu-id="e8c15-212">If the Bing map tiles are available, the layer on the design surface updates with the style that you select.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8c15-213">Também é possível adicionar uma camada de peça quando você adiciona uma camada de polígonos, linhas ou pontos no assistente de Mapa ou de Camada do Mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-213">A tile layer can also be added when you add a polygon, line, or point layer in the Map or Map Layer wizard.</span></span> <span data-ttu-id="e8c15-214">Na página **Escolher as opções de dados espaciais e de exibição do mapa** , selecione a opção **Adicionar um plano de fundo do Bing Maps a esta exibição do mapa**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-214">On the **Choose spatial data and map view options** page, select the option **Add a Bing Maps background for this map view**.</span></span>  

##  <a name="to-change-the-drawing-order-of-a-layer"></a><a name="DrawingOrder"></a> <span data-ttu-id="e8c15-215">Para alterar a ordem de desenho de uma camada</span><span class="sxs-lookup"><span data-stu-id="e8c15-215">To change the drawing order of a layer</span></span>  
  
1.  <span data-ttu-id="e8c15-216">Clique no mapa até que o painel Mapa apareça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-216">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="e8c15-217">Clique na camada no painel Mapa para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="e8c15-217">Click the layer in the Map pane to select it.</span></span>  
  
3.  <span data-ttu-id="e8c15-218">Na barra de ferramentas do painel Mapa, clique na seta para cima ou para baixo para alterar a ordem de desenho de cada camada.</span><span class="sxs-lookup"><span data-stu-id="e8c15-218">On the Map pane toolbar, click the up or down arrow to change the drawing order of each layer.</span></span>  

##  <a name="to-change-the-transparency-of-a-polygon-line-or-point-layer"></a><a name="Transparency"></a> <span data-ttu-id="e8c15-219">Para alterar a transparência de um polígono, linha ou camada de ponto</span><span class="sxs-lookup"><span data-stu-id="e8c15-219">To change the transparency of a polygon, line, or point layer</span></span>  
  
1.  <span data-ttu-id="e8c15-220">Clique no mapa até que o painel Mapa apareça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-220">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="e8c15-221">Clique com o botão direito do mouse na camada e clique em **Dados da Camada**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-221">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="e8c15-222">Clique em `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="e8c15-222">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="e8c15-223">Em **Opções de Transparência**, digite um valor que represente a transparência percentual, por exemplo, **40**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-223">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span> <span data-ttu-id="e8c15-224">A transparência zero (0)% significa que a camada é opaca.</span><span class="sxs-lookup"><span data-stu-id="e8c15-224">Zero (0) % transparency means that the layer is opaque.</span></span> <span data-ttu-id="e8c15-225">Uma transparência de 100% significa que você não visualizará a camada no relatório.</span><span class="sxs-lookup"><span data-stu-id="e8c15-225">100% transparency means that you will not see the layer in the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-change-the-transparency-of-a-tile-layer"></a><a name="TileTransparency"></a> <span data-ttu-id="e8c15-226">Para alterar a transparência de uma camada de peça</span><span class="sxs-lookup"><span data-stu-id="e8c15-226">To change the transparency of a tile layer</span></span>  
  
1.  <span data-ttu-id="e8c15-227">Clique no mapa até que o painel Mapa apareça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-227">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="e8c15-228">Clique com o botão direito do mouse na camada e clique em **Propriedades da Peça**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-228">Right-click the layer, and then click **Tile Properties**.</span></span>  
  
3.  <span data-ttu-id="e8c15-229">Clique em `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="e8c15-229">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="e8c15-230">Em **Opções de Transparência**, digite um valor que represente a transparência percentual, por exemplo, **40**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-230">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-secure-connection-for-a-tile-layer"></a><a name="Secure"></a> <span data-ttu-id="e8c15-231">Para especificar uma conexão segura para uma camada de peça</span><span class="sxs-lookup"><span data-stu-id="e8c15-231">To specify a secure connection for a tile layer</span></span>  
  
1.  <span data-ttu-id="e8c15-232">Clique no mapa até que o painel Mapa apareça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-232">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="e8c15-233">No painel Mapa, clique na camada da peça para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="e8c15-233">In the Map pane, click the tile layer to select it.</span></span> <span data-ttu-id="e8c15-234">O painel Propriedades exibe as propriedades da camada da peça.</span><span class="sxs-lookup"><span data-stu-id="e8c15-234">The Properties pane displays the tile layer properties.</span></span>  
  
3.  <span data-ttu-id="e8c15-235">No painel Propriedades, defina UseSecureConnection como **True**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-235">In the Properties pane, set UseSecureConnection to **True**.</span></span>  
  
 <span data-ttu-id="e8c15-236">A conexão para o serviço Web Bing Maps usará o serviço HTTP SSL para recuperar peças de mapas para essa camada.</span><span class="sxs-lookup"><span data-stu-id="e8c15-236">The connection for the Bing Maps Web service will use the HTTP SSL (Secure Sockets Layer) service to retrieve Bing map tiles for this layer.</span></span>  

##  <a name="to-specify-the-language-for-tile-labels"></a><a name="Language"></a> <span data-ttu-id="e8c15-237">Para especificar o idioma para rótulos de peças</span><span class="sxs-lookup"><span data-stu-id="e8c15-237">To specify the language for tile labels</span></span>  
  
1.  <span data-ttu-id="e8c15-238">Por padrão, para estilos de peças que exibem rótulos, o idioma é determinado a partir da localidade padrão do Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="e8c15-238">By default, for tile styles that display labels, the language is determined from the default locale for Report Builder.</span></span> <span data-ttu-id="e8c15-239">Você pode personalizar a configuração de idioma para rótulos de peças das maneiras a seguir.</span><span class="sxs-lookup"><span data-stu-id="e8c15-239">You can customize the language setting for tile labels in the following ways.</span></span>  
  
    -   <span data-ttu-id="e8c15-240">Clique no mapa fora do visor para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="e8c15-240">Click the map outside the viewport to select the map.</span></span> <span data-ttu-id="e8c15-241">No painel Propriedades, para a propriedade TileLanguage, selecione um valor de cultura na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-241">In the Properties pane, for the TileLanguage property, select a culture value from the drop-down list.</span></span>  
  
    -   <span data-ttu-id="e8c15-242">Clique no plano de fundo do relatório para selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="e8c15-242">Click the report background to select the report.</span></span> <span data-ttu-id="e8c15-243">No painel Propriedades, para a propriedade Language, selecione um valor de cultura na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-243">In the Properties pane, from for the Language property, select a culture value from the drop-down list.</span></span>  
  
     <span data-ttu-id="e8c15-244">A ordem de precedência para configurar o idioma do rótulo do ladrilho é: propriedade do relatório Language, localidade padrão para o Construtor de Relatórios e propriedade de mapa TileLanguage.</span><span class="sxs-lookup"><span data-stu-id="e8c15-244">The order of precedence for setting the tile label language is: report property Language, default locale for Report Builder, and map property TileLanguage.</span></span>  

##  <a name="to-conditionally-hide-a-layer-based-on-viewport-zoom-level"></a><a name="ConditionalHide"></a> <span data-ttu-id="e8c15-245">Para ocultar uma camada condicionalmente com base no nível de zoom do visor</span><span class="sxs-lookup"><span data-stu-id="e8c15-245">To conditionally hide a layer based on viewport zoom level</span></span>  
  
1.  <span data-ttu-id="e8c15-246">Definir `Visibility` opções para controlar a exibição de uma camada do mapa.</span><span class="sxs-lookup"><span data-stu-id="e8c15-246">Set `Visibility` options to control the display for a map layer.</span></span>  
  
    -   <span data-ttu-id="e8c15-247">No painel de Camadas do Mapa, clique com o botão direito do mouse em uma camada para selecioná-la e, na barra de ferramentas de Camadas do Mapa, clique nas Propriedades para abrir as **Propriedades da Camada do Mapa**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-247">In the Map Layers pane, right-click a layer to select it, and on the Map Layers toolbar, click Properties to open **Map Layer Properties**.</span></span>  
  
    -   <span data-ttu-id="e8c15-248">Clique em `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="e8c15-248">Click `Visibility`.</span></span>  
  
    -   <span data-ttu-id="e8c15-249">Na visibilidade de camada, selecione **Mostrar ou ocultar com base no valor de zoom**.</span><span class="sxs-lookup"><span data-stu-id="e8c15-249">In Layer visibility, select **Show or hide based on zoom value**.</span></span>  
  
    -   <span data-ttu-id="e8c15-250">Insira os valores de zoom mínimo e máximo para quando exibir a camada.</span><span class="sxs-lookup"><span data-stu-id="e8c15-250">Enter minimum and maximum zoom values for when display the layer.</span></span>  
  
    -   <span data-ttu-id="e8c15-251">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e8c15-251">Optional.</span></span> <span data-ttu-id="e8c15-252">Insira um valor para a transparência.</span><span class="sxs-lookup"><span data-stu-id="e8c15-252">Enter a value for transparency.</span></span>  
  
     <span data-ttu-id="e8c15-253">Você também pode ocultar condicionalmente a camada.</span><span class="sxs-lookup"><span data-stu-id="e8c15-253">You can also conditionally hide the layer.</span></span> <span data-ttu-id="e8c15-254">Para obter mais informações, consulte [Ocultar um item &#40;Construtor de Relatórios e SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e8c15-254">For more information, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="e8c15-255">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e8c15-255">See Also</span></span>  
 <span data-ttu-id="e8c15-256">[Mapas &#40;Construtor de Relatórios e SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8c15-256">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e8c15-257">Solucionar problemas de relatórios: Mapear relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e8c15-257">Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;</span></span>](troubleshoot-reports-map-reports-report-builder-and-ssrs.md)  
