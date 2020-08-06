---
title: Caixa de diálogo Propriedades do visor do mapa, centro e zoom | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.centerandzoom.f1
- "10506"
ms.assetid: 642a06f5-293f-48e0-97a6-1489dbefa719
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 913c00773abf71ca627b8cc2a94a873484e8ab30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571858"
---
# <a name="map-viewport-properties-dialog-box-center-and-zoom"></a><span data-ttu-id="ffcea-102">Caixa de diálogo Propriedades do Visor do Mapa, Centro e Zoom</span><span class="sxs-lookup"><span data-stu-id="ffcea-102">Map Viewport Properties Dialog Box, Center and Zoom</span></span>
  <span data-ttu-id="ffcea-103">Selecione **Centralizar e Aplicar Zoom** para a caixa de diálogo **Propriedades do Visor do Mapa** para definir a exibição central e o fator de zoom de um mapa.</span><span class="sxs-lookup"><span data-stu-id="ffcea-103">Select **Center and Zoom** for the **Map Viewport Properties** dialog box to set the center view and zoom factor for a map.</span></span> <span data-ttu-id="ffcea-104">Depois que você especificar uma fonte de dados do mapa e os limites do mapa a serem incluídos em seu relatório, poderá especificar o centro de exibição e o fator de zoom para controlar ainda mais a exibição do mapa.</span><span class="sxs-lookup"><span data-stu-id="ffcea-104">After you specify a map data source and the boundaries of the map that you want to include in your report, you can specify the view center and the zoom factor to further control the map display.</span></span> <span data-ttu-id="ffcea-105">As opções são alteradas de acordo com o método usado para especificar os valores de centro e zoom.</span><span class="sxs-lookup"><span data-stu-id="ffcea-105">Options change depending on which method you use to specify the center and zoom values.</span></span> <span data-ttu-id="ffcea-106">Clique no botão **Expressão** (*fx*) para editar uma expressão que define o valor da opção.</span><span class="sxs-lookup"><span data-stu-id="ffcea-106">Click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ffcea-107">Opções</span><span class="sxs-lookup"><span data-stu-id="ffcea-107">Options</span></span>  
 <span data-ttu-id="ffcea-108">**Definir um centro de exibição e um nível de zoom**</span><span class="sxs-lookup"><span data-stu-id="ffcea-108">**Set a view center and zoom level**</span></span>  
 <span data-ttu-id="ffcea-109">Escolha esta opção para especificar valores personalizados para o centro de exibição e o nível de zoom.</span><span class="sxs-lookup"><span data-stu-id="ffcea-109">Choose this option to specify custom values for the view center and the zoom level.</span></span>  
  
 <span data-ttu-id="ffcea-110">**Centralizar mapa para mostrar uma camada do mapa**</span><span class="sxs-lookup"><span data-stu-id="ffcea-110">**Center map to show a map layer**</span></span>  
 <span data-ttu-id="ffcea-111">Escolha esta opção para especificar uma camada e centralizar automaticamente a exibição em seus dados de mapa.</span><span class="sxs-lookup"><span data-stu-id="ffcea-111">Choose this option to specify a layer and automatically center the view on its map data.</span></span> <span data-ttu-id="ffcea-112">Por exemplo, centralize a exibição em LineLayer1.</span><span class="sxs-lookup"><span data-stu-id="ffcea-112">For example, center the view on LineLayer1.</span></span>  
  
 <span data-ttu-id="ffcea-113">**Centralize mapa para mostrar um elemento de mapa inserido**</span><span class="sxs-lookup"><span data-stu-id="ffcea-113">**Center map to show an embedded map element**</span></span>  
 <span data-ttu-id="ffcea-114">Escolha esta opção para centralizar a exibição em um elemento do mapa com ligação de dados específico.</span><span class="sxs-lookup"><span data-stu-id="ffcea-114">Choose this option to center the view on a specific data-bound map element.</span></span> <span data-ttu-id="ffcea-115">Os dados espaciais devem ter uma relação com os dados analíticos para especificar essa opção.</span><span class="sxs-lookup"><span data-stu-id="ffcea-115">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="ffcea-116">Por exemplo, centralize a exibição no elemento do mapa em que o nome do campo de correspondência é [Cidade] e o valor de correspondência é "Seattle".</span><span class="sxs-lookup"><span data-stu-id="ffcea-116">For example, center the view on the map element where the name of the match field is [City] and the match value is "Seattle".</span></span>  
  
 <span data-ttu-id="ffcea-117">**Centralizar mapa para mostrar todos os elementos do mapa com ligação de dados**</span><span class="sxs-lookup"><span data-stu-id="ffcea-117">**Center map to show all data-bound map elements**</span></span>  
 <span data-ttu-id="ffcea-118">Escolha esta opção para centralizar a exibição em todos os elementos do mapa na camada.</span><span class="sxs-lookup"><span data-stu-id="ffcea-118">Choose this option to center the view on all map elements in the layer.</span></span> <span data-ttu-id="ffcea-119">Os dados espaciais devem ter uma relação com os dados analíticos para especificar essa opção.</span><span class="sxs-lookup"><span data-stu-id="ffcea-119">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="ffcea-120">Por exemplo, centralize a exibição na camada de bolha do polígono que mostra cidades e o tamanho da bolha está relacionado a população.</span><span class="sxs-lookup"><span data-stu-id="ffcea-120">For example, center the view on the polygon bubble layer that shows cities and the bubble size is related to population.</span></span> <span data-ttu-id="ffcea-121">Somente as cidades com um valor de população correspondente são incluídos durante o cálculo do centro para o visor.</span><span class="sxs-lookup"><span data-stu-id="ffcea-121">Only those cities with a matching population value are included when calculating the center for the viewport.</span></span>  
  
 <span data-ttu-id="ffcea-122">**Opções de centralização e zoom**</span><span class="sxs-lookup"><span data-stu-id="ffcea-122">**Center and zoom options**</span></span>  
 <span data-ttu-id="ffcea-123">Selecione uma opção para especificar o centro de exibição e o nível de zoom.</span><span class="sxs-lookup"><span data-stu-id="ffcea-123">Select an option to specify the view center and zoom level.</span></span>  
  
 <span data-ttu-id="ffcea-124">**Exibir X central (%)**</span><span class="sxs-lookup"><span data-stu-id="ffcea-124">**View center (X) %**</span></span>  
 <span data-ttu-id="ffcea-125">A coordenada horizontal.</span><span class="sxs-lookup"><span data-stu-id="ffcea-125">The horizontal coordinate.</span></span> <span data-ttu-id="ffcea-126">O valor padrão, 50%.</span><span class="sxs-lookup"><span data-stu-id="ffcea-126">The default value, 50%.</span></span> <span data-ttu-id="ffcea-127">centraliza a exibição no ponto médio entre os valores mínimo e máximo.</span><span class="sxs-lookup"><span data-stu-id="ffcea-127">centers the view at the midpoint between the minimum and maximum horizontal values.</span></span>  
  
 <span data-ttu-id="ffcea-128">**Exibir Y central (%)**</span><span class="sxs-lookup"><span data-stu-id="ffcea-128">**View center (Y) %**</span></span>  
 <span data-ttu-id="ffcea-129">A coordenada vertical.</span><span class="sxs-lookup"><span data-stu-id="ffcea-129">The vertical coordinate.</span></span> <span data-ttu-id="ffcea-130">O valor padrão, 50%. centraliza a exibição no ponto médio entre os valores verticais mínimo e máximo.</span><span class="sxs-lookup"><span data-stu-id="ffcea-130">The default value, 50%, centers the view at the midpoint between the minimum and maximum vertical values.</span></span>  
  
 <span data-ttu-id="ffcea-131">**Nível de zoom (%)**</span><span class="sxs-lookup"><span data-stu-id="ffcea-131">**Zoom level (%)**</span></span>  
 <span data-ttu-id="ffcea-132">O fator de zoom.</span><span class="sxs-lookup"><span data-stu-id="ffcea-132">The zoom factor.</span></span> <span data-ttu-id="ffcea-133">O valor padrão, 100%, indica que não há nenhuma ampliação.</span><span class="sxs-lookup"><span data-stu-id="ffcea-133">The default value, 100%, indicates no magnification.</span></span>  
  
 <span data-ttu-id="ffcea-134">**Centralizar exibição nesta camada**</span><span class="sxs-lookup"><span data-stu-id="ffcea-134">**Center view on this layer**</span></span>  
 <span data-ttu-id="ffcea-135">Especifique o nome da camada.</span><span class="sxs-lookup"><span data-stu-id="ffcea-135">Specify the name of the layer.</span></span>  
  
 <span data-ttu-id="ffcea-136">**Centralizar exibição no elemento do mapa que corresponde a esta condição**</span><span class="sxs-lookup"><span data-stu-id="ffcea-136">**Center view on the map element that matches this condition**</span></span>  
 <span data-ttu-id="ffcea-137">O campo somente leitura exibido é usado para corresponder a dados do mapa e dados analíticos.</span><span class="sxs-lookup"><span data-stu-id="ffcea-137">The read-only field that is displayed is used to match map data and analytical data.</span></span> <span data-ttu-id="ffcea-138">Especifique o valor que você deseja corresponder.</span><span class="sxs-lookup"><span data-stu-id="ffcea-138">Specify the value that you want to match on.</span></span> <span data-ttu-id="ffcea-139">A exibição é centralizada automaticamente neste elemento do mapa.</span><span class="sxs-lookup"><span data-stu-id="ffcea-139">The view automatically centers on this map element.</span></span> <span data-ttu-id="ffcea-140">Por exemplo, NAME = TEXAS.</span><span class="sxs-lookup"><span data-stu-id="ffcea-140">For example, NAME = TEXAS.</span></span> <span data-ttu-id="ffcea-141">Por padrão, o tipo de dados para a condição é String e a correspondência faz distinção entre maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ffcea-141">By default, the data type for the condition is String and the match is case-sensitive.</span></span>  
  
 <span data-ttu-id="ffcea-142">Para corresponder em um campo que tenha um tipo de dados diferente, você deve escrever uma expressão que seja avaliada para esse tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="ffcea-142">To match on a field that has a different data type, you must write an expression that evaluates to that data type.</span></span> <span data-ttu-id="ffcea-143">Por exemplo, se o campo de correspondência for um código postal de 5 dígitos armazenado como um número inteiro, para especificar o código postal 98053, você deve usar a expressão = 98053.</span><span class="sxs-lookup"><span data-stu-id="ffcea-143">For example, if the match field is a 5 digit postal code that is stored as an integer, then to specify the postal code 98053, you must use the expression =98053.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffcea-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ffcea-144">See Also</span></span>  
 [<span data-ttu-id="ffcea-145">Mapas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ffcea-145">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
