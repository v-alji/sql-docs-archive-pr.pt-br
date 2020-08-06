---
title: Adicionar locais personalizados a um mapa (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- MICROSOFT.REPORTDESIGNER.MAPPOINT.POINTTEMPLATE
ms.assetid: 7d36faae-5bcc-446a-9eba-f42349cafacb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 167558534280f08d576205b5ff1b94d0588fcb78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684088"
---
# <a name="add-custom-locations-to-a-map-report-builder-and-ssrs"></a><span data-ttu-id="f123a-102">Adicionar locais personalizados a um mapa (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="f123a-102">Add Custom Locations to a Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f123a-103">Depois que adicionar um mapa a um relatório, você poderá adicionar seus próprios locais de ponto.</span><span class="sxs-lookup"><span data-stu-id="f123a-103">After you add a map to a report, you can add your own point locations.</span></span>  
  
 <span data-ttu-id="f123a-104">As propriedades de exibição de todos os pontos em uma camada são controladas pela definição de opções para as propriedades de ponto da camada.</span><span class="sxs-lookup"><span data-stu-id="f123a-104">Display properties for all points on a layer are controlled by setting options for the point properties for the layer.</span></span> <span data-ttu-id="f123a-105">Para um ponto inserido selecionado, você pode substituir as propriedades de exibição.</span><span class="sxs-lookup"><span data-stu-id="f123a-105">For a selected embedded point, you can override the display properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f123a-106">Quando você substituir as propriedades de exibição da camada para o ponto inserido, as alterações feitas não serão reversíveis.</span><span class="sxs-lookup"><span data-stu-id="f123a-106">When you override the layer display properties for the embedded point, the changes that you make are not reversible.</span></span>  
  
 <span data-ttu-id="f123a-107">Para obter mais informações, consulte [Variar a exibição de polígono, linha e ponto por regras e dados analíticos &#40;Construtor de Relatórios e SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="f123a-107">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-point-layer"></a><span data-ttu-id="f123a-108">Para adicionar uma camada de ponto</span><span class="sxs-lookup"><span data-stu-id="f123a-108">To add a point layer</span></span>  
  
1.  <span data-ttu-id="f123a-109">Na superfície de design de relatório, clique no mapa para selecioná-lo e exibir o painel Mapa.</span><span class="sxs-lookup"><span data-stu-id="f123a-109">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="f123a-110">Na barra de ferramentas, clique em **Adicionar Camada**.</span><span class="sxs-lookup"><span data-stu-id="f123a-110">On the toolbar, click **Add Layer**.</span></span>  
  
3.  <span data-ttu-id="f123a-111">Na lista suspensa, clique em **Adicionar Camada de Ponto**.</span><span class="sxs-lookup"><span data-stu-id="f123a-111">From the drop-down list, click **Add Point Layer**.</span></span> <span data-ttu-id="f123a-112">Uma camada de ponto sem pontos é adicionada ao mapa.</span><span class="sxs-lookup"><span data-stu-id="f123a-112">A point layer with no points is added to the map.</span></span> <span data-ttu-id="f123a-113">Por padrão, a camada de ponto está pronta para pontos inseridos.</span><span class="sxs-lookup"><span data-stu-id="f123a-113">By default, the point layer is ready for embedded points.</span></span>  
  
### <a name="to-add-a-custom-point"></a><span data-ttu-id="f123a-114">Para adicionar um ponto personalizado</span><span class="sxs-lookup"><span data-stu-id="f123a-114">To add a custom point</span></span>  
  
1.  <span data-ttu-id="f123a-115">Na superfície de design de relatório, clique no mapa para selecioná-lo e exibir o painel Mapa.</span><span class="sxs-lookup"><span data-stu-id="f123a-115">On the report design surface, click the map to select it and display the Map pane.</span></span>  
  
2.  <span data-ttu-id="f123a-116">No painel Mapa, clique com o botão direito do mouse em uma camada de ponto que tenha o tipo **Inserido**e clique em **Adicionar Ponto**.</span><span class="sxs-lookup"><span data-stu-id="f123a-116">In the Map pane, right-click a point layer that has type **Embedded**, and then click **Add Point**.</span></span> <span data-ttu-id="f123a-117">O cursor se transforma em uma cruz.</span><span class="sxs-lookup"><span data-stu-id="f123a-117">The cursor changes to crosshairs.</span></span>  
  
3.  <span data-ttu-id="f123a-118">Para adicionar um ponto, clique em um local no mapa.</span><span class="sxs-lookup"><span data-stu-id="f123a-118">To add a point, click a location on the map.</span></span> <span data-ttu-id="f123a-119">Um ponto inserido é adicionado à camada selecionada no local em que você clica.</span><span class="sxs-lookup"><span data-stu-id="f123a-119">An embedded point is added to the selected layer at the location where you click.</span></span>  
  
### <a name="to-customize-the-display-for-an-embedded-point"></a><span data-ttu-id="f123a-120">Para personalizar a exibição para um ponto inserido</span><span class="sxs-lookup"><span data-stu-id="f123a-120">To customize the display for an embedded point</span></span>  
  
1.  <span data-ttu-id="f123a-121">Clique com o botão direito do mouse no ponto e clique em **Propriedades de Ponto**.</span><span class="sxs-lookup"><span data-stu-id="f123a-121">Right-click the point, and then click **Point Properties**.</span></span> <span data-ttu-id="f123a-122">A caixa de diálogo **Propriedades do Ponto Inserido do Mapa** aparece.</span><span class="sxs-lookup"><span data-stu-id="f123a-122">The **Map Embedded Point Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="f123a-123">Clique em **Substituir opções de ponto para esta camada**.</span><span class="sxs-lookup"><span data-stu-id="f123a-123">Click **Override point options for this layer**.</span></span> <span data-ttu-id="f123a-124">Várias páginas de propriedades aparecem no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="f123a-124">Multiple property pages appear in the left pane.</span></span>  
  
3.  <span data-ttu-id="f123a-125">Clique nas páginas e defina as propriedades de exibição que você deseja aplicar a esse ponto.</span><span class="sxs-lookup"><span data-stu-id="f123a-125">Click the pages and set the display properties that you want to apply to this point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f123a-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f123a-126">See Also</span></span>  
 <span data-ttu-id="f123a-127">[Mapas &#40;Construtor de Relatórios e SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f123a-127">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f123a-128">Variar a exibição de polígono, linha e ponto por regras e dados analíticos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f123a-128">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
