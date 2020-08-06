---
title: Caixa de diálogo Propriedades do visor do mapa, geral | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.general.f1
- "10505"
ms.assetid: 6c9c773e-5c56-4571-95ed-8a157cfdfe52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d760d6a0572cbbd1bd948eab382c0727eb276c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569186"
---
# <a name="map-viewport-properties-dialog-box-general"></a><span data-ttu-id="9d2e6-102">Caixa de diálogo Propriedades do Visor do Mapa, Geral</span><span class="sxs-lookup"><span data-stu-id="9d2e6-102">Map Viewport Properties Dialog Box, General</span></span>
  <span data-ttu-id="9d2e6-103">Selecione **Geral** na caixa de diálogo **Propriedades do Visor do Mapa** para alterar o sistema de coordenadas, a projeção e as opções de limite.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-103">Select **General** on the **Map Viewport Properties** dialog box to change the coordinate system, the projection, and the boundary options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9d2e6-104">Opções</span><span class="sxs-lookup"><span data-stu-id="9d2e6-104">Options</span></span>  
 <span data-ttu-id="9d2e6-105">**Sistema de coordenadas**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-105">**Coordinate system**</span></span>  
 <span data-ttu-id="9d2e6-106">Indique o tipo de sistema de coordenadas usado pelos dados do mapa.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-106">Indicate the type of coordinate system that the map data uses.</span></span>  
  
-   <span data-ttu-id="9d2e6-107">**Planar** Escolha esta opção quando os dados do mapa estiverem em coordenadas X e Y, por exemplo, para criar planos.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-107">**Planar** Choose this option when map data is in X and Y coordinates, for example, for building plans.</span></span>  
  
-   <span data-ttu-id="9d2e6-108">**Geográfico** Escolha esta opção quando os dados do mapa estiverem em coordenadas de longitude e latitude, por exemplo, para locais de cidade.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-108">**Geographic** Choose this option when map data is in longitude and latitude coordinates, for example, for city locations.</span></span>  
  
 <span data-ttu-id="9d2e6-109">**Projeção**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-109">**Projection**</span></span>  
 <span data-ttu-id="9d2e6-110">Especifique o método a ser usado para coordenadas geográficas de projeto em uma superfície bidimensional.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-110">Specify the method to use to project geographic coordinates onto a two-dimensional surface.</span></span> <span data-ttu-id="9d2e6-111">Escolha uma projeção compatível com os dados visualizados.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-111">Choose a projection that is compatible with the data that you are visualizing.</span></span> <span data-ttu-id="9d2e6-112">As quatro propriedades espaciais afetadas pela projeção são área, forma, distância e direção.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-112">The four spatial properties that are affected by projection are area, shape, distance, and direction.</span></span> <span data-ttu-id="9d2e6-113">Para exibições da terra, uma boa escolha de projeção depende da exibição central, dos limites de mapa e do fator de zoom.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-113">For views of the earth, a good choice of projection depends on the center view, the map boundaries, and the zoom factor.</span></span>  
  
 <span data-ttu-id="9d2e6-114">Cada uma das seguintes projeções preserva uma ou mais dessas propriedades espaciais:</span><span class="sxs-lookup"><span data-stu-id="9d2e6-114">Each of the following projections preserves one or more of these spatial properties:</span></span>  
  
-   <span data-ttu-id="9d2e6-115">**Equirretangular** Escolha esta opção para usar longitude e latitude como coordenadas retangulares.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-115">**Equirectangular** Choose this option to use longitude and latitude as rectangular coordinates.</span></span>  
  
-   <span data-ttu-id="9d2e6-116">**Mercator** Escolha esta projeção popular para áreas pequenas, para obter menos distorção ao redor do equador, ou quando você quiser adicionar uma camada do mapa com uma camada lado a lado existente que use a projeção Mercator.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-116">**Mercator** Choose this popular projection for smaller areas, for less distortion around the equator, or when you want to add a map layer with an existing tile layer that uses the Mercator projection.</span></span>  
  
-   <span data-ttu-id="9d2e6-117">**Robinson** Escolha esta opção para obter menos distorção de áreas grandes que vão do equador até os polos.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-117">**Robinson** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="9d2e6-118">Desenvolvida por Arthur H. Robinson em 1963.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-118">Developed by Arthur H. Robinson in 1963.</span></span>  
  
-   <span data-ttu-id="9d2e6-119">**Fahey** Escolha esta opção para obter menos distorção de áreas grandes que vão do equador até os polos.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-119">**Fahey** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="9d2e6-120">Desenvolvida por Lawrence Fahey em 1975.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-120">Developed by Lawrence Fahey in 1975.</span></span>  
  
-   <span data-ttu-id="9d2e6-121">**Eckert1** Escolha esta opção para usar paralelos com espaçamento uniforme na latitude e linhas retas para os meridianos na longitude.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-121">**Eckert1** Choose this option to use equally spaced parallels in latitude and straight lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="9d2e6-122">**Eckert3** Escolha esta opção para usar paralelos com espaçamento uniforme na latitude e linhas curvas para os meridianos na longitude.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-122">**Eckert3** Choose this option to use equally spaced parallels in latitude and curved lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="9d2e6-123">**HammerAitoff** Escolha esta opção para mapas polares ou mundiais.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-123">**HammerAitoff** Choose this option for polar maps or world maps.</span></span>  
  
-   <span data-ttu-id="9d2e6-124">**Wagner3** Escolha esta opção para mapas mundiais.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-124">**Wagner3** Choose this option for world maps.</span></span>  
  
-   <span data-ttu-id="9d2e6-125">**Bonne** Escolha esta opção para exibir o mundo da mesma forma que em um atlas.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-125">**Bonne** Choose this option to view the world as it appears in an atlas.</span></span>  
  
 <span data-ttu-id="9d2e6-126">**Opções de quebra de página**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-126">**Page break options**</span></span>  
 <span data-ttu-id="9d2e6-127">Selecione as opções para indicar como o conteúdo se ajusta a uma página de relatório.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-127">Select options to indicate how content is fitted to a report page.</span></span>  
  
 <span data-ttu-id="9d2e6-128">**Opções de limite**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-128">**Boundary options**</span></span>  
 <span data-ttu-id="9d2e6-129">Especifique os limites inferiores e superiores das coordenadas para controlar qual parte do mapa aparece no relatório.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-129">Specify the lower and upper boundaries for coordinates to control which part of the map appears in the report.</span></span>  
  
 <span data-ttu-id="9d2e6-130">**X Mínimo**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-130">**Minimum X**</span></span>  
 <span data-ttu-id="9d2e6-131">Valor de X mais baixo.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-131">Lowest X value.</span></span> <span data-ttu-id="9d2e6-132">Disponível somente para **Planar** .</span><span class="sxs-lookup"><span data-stu-id="9d2e6-132">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="9d2e6-133">**X Máximo**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-133">**Maximum X**</span></span>  
 <span data-ttu-id="9d2e6-134">Valor de X mais alto.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-134">Highest X value.</span></span> <span data-ttu-id="9d2e6-135">Disponível somente para **Planar** .</span><span class="sxs-lookup"><span data-stu-id="9d2e6-135">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="9d2e6-136">**Y Mínimo**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-136">**Minimum Y**</span></span>  
 <span data-ttu-id="9d2e6-137">Valor de Y mais baixo.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-137">Lowest Y value.</span></span> <span data-ttu-id="9d2e6-138">Disponível somente para **Planar** .</span><span class="sxs-lookup"><span data-stu-id="9d2e6-138">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="9d2e6-139">**Y Máximo**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-139">**Maximum Y**</span></span>  
 <span data-ttu-id="9d2e6-140">Valor de Y mais alto.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-140">Highest Y value.</span></span> <span data-ttu-id="9d2e6-141">Disponível somente para **Planar** .</span><span class="sxs-lookup"><span data-stu-id="9d2e6-141">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="9d2e6-142">**Longitude Mínima**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-142">**Minimum Longitude**</span></span>  
 <span data-ttu-id="9d2e6-143">Valor de longitude mais baixo.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-143">Lowest longitude value.</span></span> <span data-ttu-id="9d2e6-144">Disponível somente para **Geográfico** .</span><span class="sxs-lookup"><span data-stu-id="9d2e6-144">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="9d2e6-145">**Longitude Máxima**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-145">**Maximum Longitude**</span></span>  
 <span data-ttu-id="9d2e6-146">Valor de longitude mais alto.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-146">Highest longitude value.</span></span> <span data-ttu-id="9d2e6-147">Disponível somente para **Geográfico** .</span><span class="sxs-lookup"><span data-stu-id="9d2e6-147">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="9d2e6-148">**Latitude Mínima**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-148">**Minimum Latitude**</span></span>  
 <span data-ttu-id="9d2e6-149">Valor de latitude mais baixo.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-149">Lowest latitude value.</span></span> <span data-ttu-id="9d2e6-150">Disponível somente para **Geográfico** .</span><span class="sxs-lookup"><span data-stu-id="9d2e6-150">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="9d2e6-151">**Latitude Máxima**</span><span class="sxs-lookup"><span data-stu-id="9d2e6-151">**Maximum Latitude**</span></span>  
 <span data-ttu-id="9d2e6-152">Valor de latitude mais alto.</span><span class="sxs-lookup"><span data-stu-id="9d2e6-152">Highest latitude value.</span></span> <span data-ttu-id="9d2e6-153">Disponível somente para **Geográfico** .</span><span class="sxs-lookup"><span data-stu-id="9d2e6-153">Available for **Geographic** only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d2e6-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9d2e6-154">See Also</span></span>  
 [<span data-ttu-id="9d2e6-155">Mapas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9d2e6-155">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
