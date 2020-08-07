---
title: Alterar legendas de mapa, escala de cores e regras associadas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.maprulesdistribution.f1
- "10512"
- "10539"
- "10533"
- sql12.rtp.rptdesigner.mappointlayerproperties.typerules.f1
- "10534"
- sql12.rtp.rptdesigner.maplegendproperties.general.f1
- sql12.rtp.rptdesigner.mapdistancescaleproperties.general.f1
- "10516"
- sql12.rtp.rptdesigner.mapcolorscaleproperties.labels.f1
- sql12.rtp.rptdesigner.maplegendtitleproperties.general.f1
- "10514"
- sql12.rtp.rptdesigner.shared.mapruleslegend.f1
- sql12.rtp.rptdesigner.mapcolorscaleproperties.general.f1
- sql12.rtp.rptdesigner.shared.embeddedlabels.f1
- "10513"
- sql12.rtp.rptdesigner.mappointlayerproperties.sizerules.f1
- sql12.rtp.rptdesigner.mapcolorscaletitleproperties.general.f1
- "10510"
- "10509"
- "10540"
- "10517"
ms.assetid: a1d691b2-c5ae-420f-af60-b7c54a7385a4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 17220c12e672ce49d3c5b1023f2a00db04e7613e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571807"
---
# <a name="change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs"></a><span data-ttu-id="ff3a4-102">Alterar legendas de mapa, escala de cores e regras associadas (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="ff3a4-102">Change Map Legends, Color Scale, and Associated Rules (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ff3a4-103">Um mapa pode conter legendas de mapa, uma escala de cores e uma escala de distância.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-103">A map can contain map legends, a color scale, and a distance scale.</span></span> <span data-ttu-id="ff3a4-104">Essas partes de um mapa ajudam os usuários a interpretar a visualização de dados no mapa.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-104">These parts of a map help users interpret the data visualization on the map.</span></span>  
  
 <span data-ttu-id="ff3a4-105">As legendas incluem as seguintes partes de um mapa:</span><span class="sxs-lookup"><span data-stu-id="ff3a4-105">Legends include the following parts of a map:</span></span>  
  
-   <span data-ttu-id="ff3a4-106">**Legenda de mapa** Exibe um guia para ajudar a interpretar os dados analíticos que variam na exibição de elementos de mapas em uma camada do mapa.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-106">**Map legend** Displays a guide to help interpret the analytical data that varies the display of a map elements on a map layer.</span></span> <span data-ttu-id="ff3a4-107">Um mapa pode ter várias legendas.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-107">A map can have multiple legends.</span></span> <span data-ttu-id="ff3a4-108">Para cada camada do mapa, especifique qual legenda deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-108">For each map layer, you A specify which legend to use.</span></span> <span data-ttu-id="ff3a4-109">Uma legenda pode fornecer um guia para mais de uma camada do mapa.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-109">A legend can provide a guide to more than one map layer.</span></span>  
  
-   <span data-ttu-id="ff3a4-110">**Escala de cores** Exibe um guia para ajudar a interpretar as cores no mapa.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-110">**Color scale** Displays a guide to help interpret colors on the map.</span></span> <span data-ttu-id="ff3a4-111">Um mapa tem uma escala de cores.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-111">A map has one color scale.</span></span> <span data-ttu-id="ff3a4-112">Várias camadas podem fornecer os dados para a escala de cores.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-112">Multiple layers can provide the data for the color scale.</span></span>  
  
-   <span data-ttu-id="ff3a4-113">**Escala de distância** Exibe um guia para ajudar a interpretar a escala do mapa.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-113">**Distance scale** Displays a guide to help interpret the scale of the map.</span></span> <span data-ttu-id="ff3a4-114">Um mapa tem uma escala de distância.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-114">A map has one distance scale.</span></span> <span data-ttu-id="ff3a4-115">O valor de zoom do visor do mapa atual determina a escala de distância.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-115">The current map viewport zoom value determines the distance scale.</span></span>  
  
 <span data-ttu-id="ff3a4-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span><span class="sxs-lookup"><span data-stu-id="ff3a4-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><a name="Viewport"></a> <span data-ttu-id="ff3a4-117">Para alterar a posição de uma legenda em relação ao visor</span><span class="sxs-lookup"><span data-stu-id="ff3a4-117">To change the position of a legend relative to the viewport</span></span>  
  
#### <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><span data-ttu-id="ff3a4-118">Para alterar a posição de uma legenda em relação ao visor</span><span class="sxs-lookup"><span data-stu-id="ff3a4-118">To change the position of a legend relative to the viewport</span></span>  
  
1.  <span data-ttu-id="ff3a4-119">Em modo de exibição de Design, clique com o botão direito do mouse na legenda e abra a _\<report item->_ página **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="ff3a4-119">In Design view, right-click the legend and open the _\<report item->_**Properties** page.</span></span>  
  
2.  <span data-ttu-id="ff3a4-120">Em **Posição**, clique no local que especifica onde exibir a legenda em relação ao visor.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-120">In **Position**, click the location that specifies where to display the legend relative to the viewport.</span></span>  
  
3.  <span data-ttu-id="ff3a4-121">Para exibir a legenda fora do visor, selecione **Mostrar \<report item> visor externo**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-121">To display the legend outside the viewport, select **Show \<report item> outside viewport**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff3a4-122">Na visualização, as legendas de mapa e a escala de cores aparecem somente quando há resultados de regras relacionadas a essa legenda.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-122">In preview, map legends and the color scale appear only when there are results from the rules related to that legend.</span></span> <span data-ttu-id="ff3a4-123">Se não houver nenhum item para exibição, a legenda não aparecerá no relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-123">If there are no items to display, the legend does not appear in the rendered report.</span></span>  
  
  
  
##  <a name="to-change-the-layout-of-a-map-legend"></a><a name="MapLegend"></a> <span data-ttu-id="ff3a4-124">Para alterar o layout de uma legenda de mapa</span><span class="sxs-lookup"><span data-stu-id="ff3a4-124">To change the layout of a map legend</span></span>  
  
#### <a name="to-change-the-layout-of-a-map-legend"></a><span data-ttu-id="ff3a4-125">Para alterar o layout de uma legenda de mapa</span><span class="sxs-lookup"><span data-stu-id="ff3a4-125">To change the layout of a map legend</span></span>  
  
1.  <span data-ttu-id="ff3a4-126">No modo de exibição de Design, clique com o botão direito do mouse na legenda e abra a página **Propriedades da Legenda** .</span><span class="sxs-lookup"><span data-stu-id="ff3a4-126">In Design view, right-click the legend and open the **Legend Properties** page.</span></span>  
  
2.  <span data-ttu-id="ff3a4-127">Em **Layout da legenda**, clique no layout de tabela que você deseja usar para a legenda.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-127">In **Legend layout**, click the table layout that you want to use for the legend.</span></span> <span data-ttu-id="ff3a4-128">À medida que você clica em opções diferentes, o layout na superfície de design é alterado.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-128">As you click different options, the layout on the design surface changes.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-show-or-hide-a-map-legend-title"></a><a name="MapLegendTitle"></a> <span data-ttu-id="ff3a4-129">Para mostrar ou ocultar um título de legenda de mapa</span><span class="sxs-lookup"><span data-stu-id="ff3a4-129">To show or hide a map legend title</span></span>  
  
#### <a name="to-show-or-hide-a-map-legend-title"></a><span data-ttu-id="ff3a4-130">Para mostrar ou ocultar um título de legenda de mapa</span><span class="sxs-lookup"><span data-stu-id="ff3a4-130">To show or hide a map legend title</span></span>  
  
-   <span data-ttu-id="ff3a4-131">Clique com o botão direito do mouse na legenda do mapa na superfície de design e clique em **Mostrar Título da Legenda**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-131">Right-click the map legend on the design surface, and then click **Show Legend Title**.</span></span>  
  
  
  
##  <a name="to-show-or-hide-a-color-scale-title"></a><a name="ColorScaleTitle"></a> <span data-ttu-id="ff3a4-132">Para mostrar ou ocultar um título de escala de cores</span><span class="sxs-lookup"><span data-stu-id="ff3a4-132">To show or hide a color scale title</span></span>  
  
#### <a name="to-show-or-hide-a-color-scale-title"></a><span data-ttu-id="ff3a4-133">Para mostrar ou ocultar um título de escala de cores</span><span class="sxs-lookup"><span data-stu-id="ff3a4-133">To show or hide a color scale title</span></span>  
  
-   <span data-ttu-id="ff3a4-134">Clique com o botão direito do mouse na escala de cores na superfície de design e clique em **Mostrar Título da Escala de Cores**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-134">Right-click the color scale on the design surface, and then click **Show Color Scale Title**.</span></span>  
  
  
  
##  <a name="to-move-items-out-of-the-first-legend"></a><a name="MoveItems"></a> <span data-ttu-id="ff3a4-135">Para remover itens da primeira legenda</span><span class="sxs-lookup"><span data-stu-id="ff3a4-135">To move items out of the first legend</span></span>  
 <span data-ttu-id="ff3a4-136">Crie quantas legendas adicionais forem necessárias e atualize as regras de cada camada do mapa, especificando em qual legenda devem ser exibidos os resultados de regras.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-136">Create as many additional legends as you need and then update the rules for each map layer specify which legend to display the rule results in.</span></span>  
  
#### <a name="to-create-a-new-legend"></a><span data-ttu-id="ff3a4-137">Para criar uma nova legenda</span><span class="sxs-lookup"><span data-stu-id="ff3a4-137">To create a new legend</span></span>  
  
-   <span data-ttu-id="ff3a4-138">No modo de exibição de Design, clique com o botão direito do mouse no mapa fora do visor do mapa e clique em **Adicionar Legenda**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-138">In Design view, right-click the map outside the map viewport, and then click **Add Legend**.</span></span>  
  
     <span data-ttu-id="ff3a4-139">Uma nova legenda será exibida no mapa.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-139">A new legend appears on the map.</span></span>  
  
#### <a name="to-display-rule-results-in-a-legend"></a><span data-ttu-id="ff3a4-140">Para exibir resultados de regra em uma legenda</span><span class="sxs-lookup"><span data-stu-id="ff3a4-140">To display rule results in a legend</span></span>  
  
1.  <span data-ttu-id="ff3a4-141">No modo Design, clique no mapa até que o painel Mapa seja exibido.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-141">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="ff3a4-142">Clique com o botão direito do mouse na camada que tem os dados desejados e clique em _\<map element type\>_ **regra de cores**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-142">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="ff3a4-143">Clique em **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-143">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="ff3a4-144">Na lista suspensa **Mostrar nesta legenda** , clique no nome da legenda na qual devem ser exibidos os resultados da regra.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-144">In the **Show in this legend** drop-down list, click the name of the legend to display the rule results in.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-a-template-style"></a><a name="TemplateStyle"></a> <span data-ttu-id="ff3a4-145">Para variar cores do elemento do mapa com base em um estilo de modelo</span><span class="sxs-lookup"><span data-stu-id="ff3a4-145">To vary map element colors based on a template style</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-a-template-style"></a><span data-ttu-id="ff3a4-146">Para variar cores do elemento do mapa com base em um estilo de modelo</span><span class="sxs-lookup"><span data-stu-id="ff3a4-146">To vary map element colors based on a template style</span></span>  
  
1.  <span data-ttu-id="ff3a4-147">No modo Design, clique no mapa até que o painel Mapa seja exibido.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-147">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="ff3a4-148">Clique com o botão direito do mouse na camada que tem os dados desejados e clique em _\<map element type\>_ **regra de cores**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-148">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="ff3a4-149">Clique em **Aplicar estilo do modelo**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-149">Click **Apply template style**.</span></span>  
  
     <span data-ttu-id="ff3a4-150">Um estilo de modelo especifica uma fonte, um estilo de borda e uma paleta de cores.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-150">A template style specifies font, border style, and color palette.</span></span> <span data-ttu-id="ff3a4-151">Cada elemento do mapa recebe uma cor diferente da paleta de cores para o tema que foi especificado no Assistente de Mapa ou no Assistente de Camada do Mapa.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-151">Each map element is assigned a different color from the color palette for the theme that was specified in the Map Wizard or Map Layer Wizard.</span></span> <span data-ttu-id="ff3a4-152">Essa é a única opção que se aplica a camadas que não têm dados analíticos associados.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-152">This is the only option that applies to layers that do not have associated analytical data.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-palette"></a><a name="ColorPalette"></a> <span data-ttu-id="ff3a4-153">Para variar as cores do elemento do mapa com base em uma paleta de cores</span><span class="sxs-lookup"><span data-stu-id="ff3a4-153">To vary map element colors based on color palette</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-palette"></a><span data-ttu-id="ff3a4-154">Para variar as cores do elemento do mapa com base em uma paleta de cores</span><span class="sxs-lookup"><span data-stu-id="ff3a4-154">To vary map element colors based on color palette</span></span>  
  
1.  <span data-ttu-id="ff3a4-155">No modo Design, clique no mapa até que o painel Mapa seja exibido.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-155">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="ff3a4-156">Clique com o botão direito do mouse na camada que tem os dados desejados e clique em _\<map element type\>_ **regra de cores**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-156">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="ff3a4-157">Clique em **Visualizar dados usando a paleta de cores**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-157">Click **Visualize data by using color palette**.</span></span>  
  
     <span data-ttu-id="ff3a4-158">Essa opção usa uma paleta interna ou personalizada que você especifica.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-158">This option uses a built-in or custom palette that you specify.</span></span> <span data-ttu-id="ff3a4-159">Com base nos dados analíticos relacionados, cada elemento do mapa recebe uma cor diferente ou tom de cor da paleta.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-159">Based on related analytical data, each map element is assigned a different color or shade of color from the palette.</span></span>  
  
4.  <span data-ttu-id="ff3a4-160">Em **Campo de dados**, digite o nome do campo que contém os dados analíticos que você deseja visualizar por cor.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-160">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="ff3a4-161">Em **Paleta**, na lista suspensa, selecione o nome da paleta a ser usada.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-161">In **Palette**, from the drop-down list, select the name of the palette to use.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-ranges"></a><a name="ColorRanges"></a> <span data-ttu-id="ff3a4-162">Para variar as cores do elemento do mapa com base em intervalos de cores</span><span class="sxs-lookup"><span data-stu-id="ff3a4-162">To vary map element colors based on color ranges</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-ranges"></a><span data-ttu-id="ff3a4-163">Para variar as cores do elemento do mapa com base em intervalos de cores</span><span class="sxs-lookup"><span data-stu-id="ff3a4-163">To vary map element colors based on color ranges</span></span>  
  
1.  <span data-ttu-id="ff3a4-164">No modo Design, clique no mapa até que o painel Mapa seja exibido.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-164">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="ff3a4-165">Clique com o botão direito do mouse na camada que tem os dados desejados e clique em _\<map element type\>_ **regra de cores**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-165">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="ff3a4-166">Clique em **Visualizar dados usando intervalos de cores**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-166">Click **Visualize data by using color ranges**.</span></span>  
  
     <span data-ttu-id="ff3a4-167">Essa opção, aliada às cores inicial, intermediária e final que você especifica nessa página e as opções especificadas na página **Distribuição** , divide os dados analíticos relacionados em intervalos.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-167">This option, combined with the start, middle, and end colors that you specify on this page and the options that you specify on the **Distribution** page, divide the related analytical data into ranges.</span></span> <span data-ttu-id="ff3a4-168">O processador de relatório atribui a cor apropriada a cada elemento do mapa com base nos dados associados e no intervalo em que se enquadra.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-168">The report processor assigns the appropriate color to each map element based on the its associated data and the range that it falls into.</span></span>  
  
4.  <span data-ttu-id="ff3a4-169">Em **Campo de dados**, digite o nome do campo que contém os dados analíticos que você deseja visualizar por cor.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-169">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="ff3a4-170">Em **Cor inicial**, especifique a cor a ser usada para o intervalo mais baixo.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-170">In **Start color**, specify the color to use for the lowest range.</span></span>  
  
6.  <span data-ttu-id="ff3a4-171">Em **Cor Intermediária**, especifique a cor a ser usada para o intervalo intermediário.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-171">In **Middle color**, specify the color to use for the middle range.</span></span>  
  
7.  <span data-ttu-id="ff3a4-172">Em **Cor final**, especifique a cor a ser usada para o intervalo mais alto.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-172">In **End color**, specify the color to use for the highest range.</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-custom-colors"></a><a name="CustomColors"></a> <span data-ttu-id="ff3a4-173">Para variar as cores do elemento do mapa com base em cores personalizadas</span><span class="sxs-lookup"><span data-stu-id="ff3a4-173">To vary map element colors based on custom colors</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-custom-colors"></a><span data-ttu-id="ff3a4-174">Para variar as cores do elemento do mapa com base em cores personalizadas</span><span class="sxs-lookup"><span data-stu-id="ff3a4-174">To vary map element colors based on custom colors</span></span>  
  
1.  <span data-ttu-id="ff3a4-175">No modo Design, clique no mapa até que o painel Mapa seja exibido.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-175">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="ff3a4-176">Clique com o botão direito do mouse na camada que tem os dados desejados e clique em _\<map element type\>_ **regra de cores**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-176">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="ff3a4-177">Clique em **Visualizar dados usando cores personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-177">Click **Visualize data by using custom colors**.</span></span>  
  
     <span data-ttu-id="ff3a4-178">Essa opção usa a lista de cores especificada por você.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-178">This option uses the list of colors that you specify.</span></span> <span data-ttu-id="ff3a4-179">Com base nos dados analíticos relacionados, cada elemento do mapa recebe uma cor da lista.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-179">Based on related analytical data, each map element is assigned a color from the list.</span></span> <span data-ttu-id="ff3a4-180">Se houver mais elementos do mapa do que cores, nenhuma cor será atribuída.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-180">If there are more map elements than colors, no color is assigned.</span></span>  
  
4.  <span data-ttu-id="ff3a4-181">Em **Campo de dados**, digite o nome do campo que contém os dados analíticos que você deseja visualizar por cor.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-181">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="ff3a4-182">Em **Cores personalizadas**, clique em **Adicionar** para especificar cada cor personalizada.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-182">In **Custom colors**, click **Add** to specify each custom color.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-set-distribution-options-for-a-legend"></a><a name="DistributionOptions"></a> <span data-ttu-id="ff3a4-183">Para definir as opções de distribuição de uma legenda</span><span class="sxs-lookup"><span data-stu-id="ff3a4-183">To set distribution options for a legend</span></span>  
  
#### <a name="to-set-distribution-options-for-a-legend"></a><span data-ttu-id="ff3a4-184">Para definir as opções de distribuição de uma legenda</span><span class="sxs-lookup"><span data-stu-id="ff3a4-184">To set distribution options for a legend</span></span>  
  
1.  <span data-ttu-id="ff3a4-185">No modo Design, clique no mapa até que o painel Mapa seja exibido.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-185">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="ff3a4-186">Clique com o botão direito do mouse na camada que tem os dados desejados e clique em _\<map element type\>_ **regra de cores**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-186">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="ff3a4-187">Selecione a opção **Visualizar dados usando** \<rule type\> .</span><span class="sxs-lookup"><span data-stu-id="ff3a4-187">Select the **Visualize data by using** \<rule type\> option.</span></span> <span data-ttu-id="ff3a4-188">Para usar as opções de distribuição, você deve criar intervalos na página **Distribuição** com base nos dados analíticos associados à camada.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-188">To use distribution options, you must create ranges on the **Distribution** page based on analytical data that is associated with the layer.</span></span>  
  
4.  <span data-ttu-id="ff3a4-189">Clique em **Distribuição**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-189">Click **Distribution**.</span></span>  
  
5.  <span data-ttu-id="ff3a4-190">Selecione um dos seguintes tipos de distribuição:</span><span class="sxs-lookup"><span data-stu-id="ff3a4-190">Select one of the following distribution types:</span></span>  
  
    -   <span data-ttu-id="ff3a4-191">**EqualInterval**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-191">**EqualInterval**.</span></span> <span data-ttu-id="ff3a4-192">Especifica intervalos que dividem os dados em intervalos iguais.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-192">Specifies ranges that divide the data into equal range intervals.</span></span>  
  
    -   <span data-ttu-id="ff3a4-193">**EqualDistribution**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-193">**EqualDistribution**.</span></span> <span data-ttu-id="ff3a4-194">Especifica intervalos que dividem esses dados de forma que cada intervalo tenha um número de itens igual.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-194">Specifies ranges that divide that data so that each range has an equal number of items.</span></span>  
  
    -   <span data-ttu-id="ff3a4-195">**Ideal**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-195">**Optimal**.</span></span> <span data-ttu-id="ff3a4-196">Especifica os intervalos que ajustam automaticamente a distribuição para criar subintervalos equilibrados.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-196">Specifies ranges that automatically adjust distribution to create balanced subranges.</span></span>  
  
    -   <span data-ttu-id="ff3a4-197">**Personalizado**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-197">**Custom**.</span></span> <span data-ttu-id="ff3a4-198">Especifique seu próprio número de intervalos para controlar a distribuição de valores.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-198">Specify your own number of ranges to control the distribution of values.</span></span>  
  
     <span data-ttu-id="ff3a4-199">Para obter mais informações sobre as opções de distribuição, consulte [Variar a exibição de polígono, linha e ponto por regras e dados analíticos &#40;Construtor de Relatórios e SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="ff3a4-199">For more information about distribution options, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
6.  <span data-ttu-id="ff3a4-200">Em **Número de subintervalos**, digite o número de subintervalos a ser usado.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-200">In **Number of subranges**, type the number of subranges to use.</span></span> <span data-ttu-id="ff3a4-201">Quando o tipo de distribuição for **Ideal**, o número de subintervalos será calculado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-201">When the distribution type is **Optimal**, the number of subranges is automatically calculated.</span></span>  
  
7.  <span data-ttu-id="ff3a4-202">Em **Início do intervalo**, digite um valor de intervalo mínimo.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-202">In **Range start**, type a minimum range value.</span></span> <span data-ttu-id="ff3a4-203">Todos os valores menores do que esse número são iguais ao intervalo mínimo.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-203">All values less than this number are the same as the range minimum.</span></span>  
  
8.  <span data-ttu-id="ff3a4-204">Em **Fim do intervalo**, digite um valor de intervalo máximo.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-204">In **Range end**, type a maximum range value.</span></span> <span data-ttu-id="ff3a4-205">Todos os valores maiores do que esse número são iguais ao intervalo máximo.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-205">All values larger than this number are the same as the range maximum.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-a-rule-legend"></a><a name="RuleLegend"></a> <span data-ttu-id="ff3a4-206">Para alterar o conteúdo de uma legenda de regras</span><span class="sxs-lookup"><span data-stu-id="ff3a4-206">To change the contents of a rule legend</span></span>  
  
#### <a name="to-change-the-contents-of-a-color-size-width-or-marker-type-legend"></a><span data-ttu-id="ff3a4-207">Para alterar o conteúdo da legenda de cor, tamanho, largura ou tipo de marcador</span><span class="sxs-lookup"><span data-stu-id="ff3a4-207">To change the contents of a color, size, width, or marker type legend</span></span>  
  
1.  <span data-ttu-id="ff3a4-208">No modo Design, clique no mapa até que o painel Mapa seja exibido.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-208">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="ff3a4-209">Clique com o botão direito do mouse na camada que tem os dados desejados e clique em _\<map element type\>_ **regra**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-209">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="ff3a4-210">Verifique se a **visualização de dados usando** \<*rule type*> está selecionada.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-210">Verify that **Visualize data by using** \<*rule type*> is selected.</span></span>  
  
4.  <span data-ttu-id="ff3a4-211">Em **Campo de dados**, verifique se os dados analíticos visualizados na camada estão selecionados.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-211">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff3a4-212">Se nenhum campo aparecer na lista suspensa, clique com o botão direito do mouse na camada e clique em **Dados da Camada** para abrir a caixa de diálogo Propriedades de Dados da Camada do Mapa, página Dados Analíticos e verificar se você especificou dados analíticos para essa camada.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-212">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="ff3a4-213">Clique em **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-213">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="ff3a4-214">Em **Mostrar nesta legenda**, selecione a legenda do mapa a ser usada para exibir os resultados da regra.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-214">In **Show in this legend**, select the map legend to use to display the rule results.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-the-color-scale"></a><a name="ColorScale"></a> <span data-ttu-id="ff3a4-215">Para alterar o conteúdo da escala de cores</span><span class="sxs-lookup"><span data-stu-id="ff3a4-215">To change the contents of the color scale</span></span>  
  
#### <a name="to-change-the-contents-of-the-color-scale-or-a-color-legend"></a><span data-ttu-id="ff3a4-216">Para alterar o conteúdo da escala de cores ou de uma legenda de cor</span><span class="sxs-lookup"><span data-stu-id="ff3a4-216">To change the contents of the color scale or a color legend</span></span>  
  
1.  <span data-ttu-id="ff3a4-217">No modo Design, clique no mapa até que o painel Mapa seja exibido.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-217">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="ff3a4-218">Clique com o botão direito do mouse na camada que tem os dados desejados e clique em _\<map element type\>_ **regra de cores**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-218">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="ff3a4-219">Selecione a opção de regra de cor a ser usada.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-219">Select the color rule option to use.</span></span> <span data-ttu-id="ff3a4-220">Para exibir itens em uma legenda de mapa ou escala de cores, você deve selecionar um dos **dados de visualização usando** \<rule type> opções.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-220">To display items in a map legend or color scale, you must select one of the **Visualize data by using** \<rule type> options.</span></span>  
  
4.  <span data-ttu-id="ff3a4-221">Em **Campo de dados**, verifique se os dados analíticos visualizados na camada estão selecionados.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-221">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff3a4-222">Se nenhum campo aparecer na lista suspensa, clique com o botão direito do mouse na camada e clique em **Dados da Camada** para abrir a caixa de diálogo Propriedades de Dados da Camada do Mapa, página Dados Analíticos e verificar se você especificou dados analíticos para essa camada.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-222">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="ff3a4-223">Clique em **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-223">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="ff3a4-224">Em **Opções de escala de cores**, selecione **Mostrar na escala de cores** para exibir os resultados da regra na escala de cores.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-224">In **Color scale options**, select **Show in color scale** to display the rule results in the color scale.</span></span> <span data-ttu-id="ff3a4-225">Você pode especificar esta opção para mais de uma regra de cor.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-225">You can specify this option for more than one color rule.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-remove-all-items-from-a-legend"></a><a name="HideItems"></a> <span data-ttu-id="ff3a4-226">Para remover todos os itens de uma legenda</span><span class="sxs-lookup"><span data-stu-id="ff3a4-226">To remove all items from a legend</span></span>  
  
#### <a name="to-hide-items-based-on-a-rule"></a><span data-ttu-id="ff3a4-227">Para ocultar itens com base em uma regra</span><span class="sxs-lookup"><span data-stu-id="ff3a4-227">To hide items based on a rule</span></span>  
  
1.  <span data-ttu-id="ff3a4-228">No modo Design, clique no mapa até que o painel Mapa seja exibido.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-228">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="ff3a4-229">Clique com o botão direito do mouse na camada que tem os dados desejados e clique em _\<map element type\>_ **regra**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-229">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="ff3a4-230">Clique em **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-230">Click **Legend**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-format-of-content-in-a-legend"></a><a name="ChangeFormatItems"></a> <span data-ttu-id="ff3a4-231">Para alterar o formato de conteúdo em uma legenda</span><span class="sxs-lookup"><span data-stu-id="ff3a4-231">To change the format of content in a legend</span></span>  
 <span data-ttu-id="ff3a4-232">Defina as opções de legenda para a regra associada à legenda de mapa.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-232">Set legend options for the rule that is associated with the map legend.</span></span>  
  
#### <a name="to-change-the-format-of-content-in-a-legend"></a><span data-ttu-id="ff3a4-233">Para alterar o formato de conteúdo em uma legenda</span><span class="sxs-lookup"><span data-stu-id="ff3a4-233">To change the format of content in a legend</span></span>  
  
1.  <span data-ttu-id="ff3a4-234">No modo Design, clique no mapa até que o painel Mapa seja exibido.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-234">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="ff3a4-235">Clique com o botão direito do mouse na camada que tem os dados desejados e clique em _\<map element type\>_ **regra**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-235">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="ff3a4-236">Clique em **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-236">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="ff3a4-237">O**Texto de legenda** exibe as palavras-chave que especificam quais dados são exibidos na legenda.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-237">**Legend text** displays keywords that specify which data appears in the legend.</span></span> <span data-ttu-id="ff3a4-238">Use as palavras-chave do mapa e os formatos personalizados para ajudar a controlar o formato do texto da legenda.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-238">Use map keywords and custom formats to help control the format of legend text.</span></span> <span data-ttu-id="ff3a4-239">Por exemplo, #FROMVALUE {C2} especifica um formato de moeda com duas casas decimais.</span><span class="sxs-lookup"><span data-stu-id="ff3a4-239">For example, #FROMVALUE {C2} specifies a currency format with two decimal places.</span></span> <span data-ttu-id="ff3a4-240">Para obter mais informações, consulte [Variar a exibição de polígono, linha e ponto por regras e dados analíticos &#40;Construtor de Relatórios e SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="ff3a4-240">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="ff3a4-241">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ff3a4-241">See Also</span></span>  
 <span data-ttu-id="ff3a4-242">[Mapas &#40;Construtor de Relatórios e SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff3a4-242">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ff3a4-243">[Adicionar, alterar ou excluir um mapa ou uma camada do mapa &#40;Construtor de Relatórios e SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff3a4-243">[Add, Change, or Delete a Map or Map Layer &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ff3a4-244">[Personalizar os dados e a exibição de um mapa ou de uma camada do mapa &#40;Construtor de Relatórios e SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff3a4-244">[Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ff3a4-245">[Solução de problemas de relatórios: relatórios de mapa &#40;Construtor de Relatórios e SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff3a4-245">[Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ff3a4-246">Assistente de Mapa e Assistente de Camada do Mapa &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ff3a4-246">Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;</span></span>](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md)  
  
  
