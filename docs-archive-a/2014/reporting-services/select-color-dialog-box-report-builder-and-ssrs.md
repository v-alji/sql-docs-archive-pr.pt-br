---
title: Caixa de diálogo Selecionar cor (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.selectcolor.f1
- "10090"
helpviewer_keywords:
- Select Color dialog box
ms.assetid: ac7089a3-5c7b-4f53-8348-180610e86da2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a2526b755fd4e08faf79998d351e824371fac2f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684468"
---
# <a name="select-color-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="8dc4f-102">Caixa de diálogo Selecionar Cor (Construtor de Relatórios SSRS)</span><span class="sxs-lookup"><span data-stu-id="8dc4f-102">Select Color Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8dc4f-103">Use a caixa de diálogo **Selecionar Cor** para especificar as opções de cor da tela de fundo de uma única ou de várias células em uma região de dados ou de uma caixa de texto, ou para um gráfico.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-103">Use the **Select Color** dialog box to specify color options for the background of a single cell or multiple cells within a data region or a text box, or for a chart.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8dc4f-104">Opções</span><span class="sxs-lookup"><span data-stu-id="8dc4f-104">Options</span></span>  
 <span data-ttu-id="8dc4f-105">**Seletor de cores**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-105">**Color selector**</span></span>  
 <span data-ttu-id="8dc4f-106">Escolha três opções que especificam como você quer selecionar as cores:</span><span class="sxs-lookup"><span data-stu-id="8dc4f-106">Choose from three options that specify how you want to select colors:</span></span>  
  
-   <span data-ttu-id="8dc4f-107">**Selecionador – Círculo de cor** Escolha uma cor que use valores de cores HSB (Matiz/Saturação/Brilho).</span><span class="sxs-lookup"><span data-stu-id="8dc4f-107">**Picker - Color circle** Choose a color using Hue/Saturation/Brightness (HSB) color values.</span></span>  
  
-   <span data-ttu-id="8dc4f-108">**Selecionador – Quadrado de cores** Escolha uma cor que usa valores de cor RGB (Vermelho/Verde/Azul).</span><span class="sxs-lookup"><span data-stu-id="8dc4f-108">**Picker - Color square** Choose a color using Red/Green/Blue (RGB) color values.</span></span>  
  
-   <span data-ttu-id="8dc4f-109">**Paleta – Cores padrão** Escolha uma cor de uma lista predefinida de valores de cor.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-109">**Palette - Standard colors** Choose a color from a predefined list of color values.</span></span>  
  
 <span data-ttu-id="8dc4f-110">**Círculo de cores**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-110">**Color circle**</span></span>  
 <span data-ttu-id="8dc4f-111">Use para as cores HSB pois são valores mapeados em um sistema cilíndrico coordenado.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-111">Use for HSB colors because HSB values are mapped onto a cylindrical coordinate system.</span></span> <span data-ttu-id="8dc4f-112">O matiz é a cor real, a saturação é a pureza da cor, e o brilho é o brilho ou escuridão relativa.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-112">Hue is the actual color, saturation is purity of color, brightness is relative brightness or darkness.</span></span>  
  
 <span data-ttu-id="8dc4f-113">Ao selecionar uma cor, o centro do círculo determina a cor.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-113">When you pick a color, the center of the circle determines the color.</span></span> <span data-ttu-id="8dc4f-114">Use o controle deslizante de cor para alterar o matiz.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-114">Use the color slider to change the hue.</span></span> <span data-ttu-id="8dc4f-115">As coordenadas x e y representam respectivamente os valores da saturação e do brilho.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-115">The x and y coordinates represent saturation and brightness values respectively.</span></span>  
  
 <span data-ttu-id="8dc4f-116">**Quadrado de cores**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-116">**Color square**</span></span>  
 <span data-ttu-id="8dc4f-117">Use para as cores RGB pois os valores do RGB são mapeados em um sistema Cartesiano coordenado.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-117">Use for RGB colors because RGB values are mapped to a Cartesian coordinate system.</span></span> <span data-ttu-id="8dc4f-118">R é o valor para Red (Vermelho), G é o valor para Green (Verde), B é o valor para Blue (Azul).</span><span class="sxs-lookup"><span data-stu-id="8dc4f-118">R is the value for Red, G is the value for Green, B is the value for Blue.</span></span>  
  
 <span data-ttu-id="8dc4f-119">Quando você escolhe uma cor, o centro do quadrado determina a cor.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-119">When you pick a color, the center of the square determines the color.</span></span> <span data-ttu-id="8dc4f-120">Use o controle deslizante de cor para alterar o faixa da cor escolhida.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-120">Use the color slider to change the range of the chosen color.</span></span> <span data-ttu-id="8dc4f-121">As coordenadas x e y representam as outras duas cores.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-121">The x and y coordinates represent the other two colors.</span></span> <span data-ttu-id="8dc4f-122">Por exemplo, se selecionar o verde, o controle deslizando mostra a faixas dos valores do verde, e as coordenadas x e y representam respectivamente os valores do vermelho e do azul.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-122">For example, if you pick green, the slider shows the range of green values, the x and y coordinates represent red and blue values respectively.</span></span>  
  
 <span data-ttu-id="8dc4f-123">**Cor da paleta padrão**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-123">**Standard palette color**</span></span>  
 <span data-ttu-id="8dc4f-124">Use para cores nomeadas da [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] `KnownColor` enumeração.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-124">Use for named colors from the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] `KnownColor` enumeration.</span></span>  
  
 <span data-ttu-id="8dc4f-125">**Sistema de cores**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-125">**Color system**</span></span>  
 <span data-ttu-id="8dc4f-126">Especifique as cores RGB ou HSB.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-126">Specify RGB or HSB colors.</span></span> <span data-ttu-id="8dc4f-127">Esta escolha altera a exibição para mostrar os valores de RGB ou HSB, que são atualizados interativamente ao usar um circulo de cores ou um quadrado de cores para o **Selecionador de cores**.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-127">This choice changes the display to show RGB or HSB values, which are updated interactively when you use a color circle or color square for the **Color selector**.</span></span>  
  
 <span data-ttu-id="8dc4f-128">O valor **Alpha** é exibido para algumas propriedades quando uma cor é incluída em um valor de transparência.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-128">The **Alpha** value displays for some properties when a color can include a transparency value.</span></span> <span data-ttu-id="8dc4f-129">Por exemplo, preenchimento das séries do gráfico.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-129">For example, Chart series fill.</span></span> <span data-ttu-id="8dc4f-130">Para propriedades que não dão suporte transparência, este valor é desabilitado.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-130">For properties that do not support transparency, this value is disabled.</span></span>  
  
 <span data-ttu-id="8dc4f-131">**Vermelho**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-131">**Red**</span></span>  
 <span data-ttu-id="8dc4f-132">O valor decimal para a parte vermelha da cor de RGB.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-132">The decimal value for the red part of the RGB color.</span></span> <span data-ttu-id="8dc4f-133">Use a caixa de rotação para alterar o valor ou digitar um valor entre 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-133">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="8dc4f-134">**Verde**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-134">**Green**</span></span>  
 <span data-ttu-id="8dc4f-135">O valor decimal para a parte verde da cor de RGB.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-135">The decimal value for the green part of the RGB color.</span></span> <span data-ttu-id="8dc4f-136">Use a caixa de rotação para alterar o valor ou digitar um valor entre 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-136">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="8dc4f-137">**Azul**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-137">**Blue**</span></span>  
 <span data-ttu-id="8dc4f-138">O valor decimal para a parte azul da cor de RGB.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-138">The decimal value for the blue part of the RGB color.</span></span> <span data-ttu-id="8dc4f-139">Use a caixa de rotação para alterar o valor ou digitar um valor entre 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-139">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="8dc4f-140">**Alfa**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-140">**Alpha**</span></span>  
 <span data-ttu-id="8dc4f-141">O valor decimal para o alfa ou parte de transparência da cor.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-141">The decimal value for the alpha or transparency part of the color.</span></span> <span data-ttu-id="8dc4f-142">Quando este valor é ativado, você pode usar a opção de controle deslizante para ajustar o grau de transparência desejado.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-142">When this value is enabled, you can use the slider switch to adjust the degree of transparency you want.</span></span>  
  
 <span data-ttu-id="8dc4f-143">**Matiz**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-143">**Hue**</span></span>  
 <span data-ttu-id="8dc4f-144">O valor decimal para o matiz da cor HSB.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-144">The decimal value for the hue of the HSB color.</span></span> <span data-ttu-id="8dc4f-145">Use a caixa de rotação para alterar o valor ou digitar um valor entre 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-145">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="8dc4f-146">**Saturação**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-146">**Saturation**</span></span>  
 <span data-ttu-id="8dc4f-147">O valor decimal para a saturação da cor HSB.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-147">The decimal value for the saturation of the HSB color.</span></span> <span data-ttu-id="8dc4f-148">Use a caixa de rotação para alterar o valor ou digitar um valor entre 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-148">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="8dc4f-149">**Brilho**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-149">**Brightness**</span></span>  
 <span data-ttu-id="8dc4f-150">O valor decimal para o brilho da cor HSB.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-150">The decimal value for the brightness of the HSB color.</span></span> <span data-ttu-id="8dc4f-151">Use a caixa de rotação para alterar o valor ou digitar um valor entre 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-151">Use the spin box to change the value or type in a value between 0 and 255.</span></span>  
  
 <span data-ttu-id="8dc4f-152">**Amostra de cor**</span><span class="sxs-lookup"><span data-stu-id="8dc4f-152">**Color sample**</span></span>  
 <span data-ttu-id="8dc4f-153">Mostra o cor atual na metade esquerda do painel e mostra interativamente a nova cor que está sendo selecionada na metade direita do painel.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-153">Shows the current color on the left half of the pane and interactively shows the new color you are choosing on the right half of the pane.</span></span> <span data-ttu-id="8dc4f-154">Se não houver nenhuma cor padrão, a metade esquerda do painel será branca.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-154">If there is no default color, the left half of the pane is white.</span></span> <span data-ttu-id="8dc4f-155">A maioria das propriedades de RDL não tem nenhuma cor padrão.</span><span class="sxs-lookup"><span data-stu-id="8dc4f-155">Most RDL properties have no default color.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc4f-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8dc4f-156">See Also</span></span>  
 <span data-ttu-id="8dc4f-157">[Formatando itens de relatório &#40;Construtor de Relatórios e SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8dc4f-157">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8dc4f-158">Formatando texto e espaços reservados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8dc4f-158">Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;</span></span>](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md)  
  
  
