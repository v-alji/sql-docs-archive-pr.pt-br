---
title: Editor de formulário de membro calculado (guia cálculos, designer de cubo) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationexpression.calculatedmember.f1
ms.assetid: f7719b9e-b1e6-4792-90a6-30d9d8eb1196
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dd45ece03fd81e0e7356e7bdcd0ec8dc53287bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571095"
---
# <a name="calculated-member-form-editor-calculations-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="7a944-102">Editor de Formulário de Membro Calculado (guia Cálculos, Designer de Cubo) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="7a944-102">Calculated Member Form Editor (Calculations Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="7a944-103">Use o painel **Editor de Formulário de Membro Calculado** na guia **Cálculos** do Designer de Cubo para criar ou modificar um membro calculado.</span><span class="sxs-lookup"><span data-stu-id="7a944-103">Use the **Calculated Member Form Editor** pane on the **Calculations** tab in Cube Designer to create or modify a calculated member.</span></span>  
  
 <span data-ttu-id="7a944-104">**Observação** este painel é exibido apenas na exibição de formulário.</span><span class="sxs-lookup"><span data-stu-id="7a944-104">**Note** This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7a944-105">Opções</span><span class="sxs-lookup"><span data-stu-id="7a944-105">Options</span></span>  
 <span data-ttu-id="7a944-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="7a944-106">**Name**</span></span>  
 <span data-ttu-id="7a944-107">Digite o nome do membro calculado.</span><span class="sxs-lookup"><span data-stu-id="7a944-107">Type the name of the calculated member.</span></span>  
  
 <span data-ttu-id="7a944-108">**Propriedades Pai**</span><span class="sxs-lookup"><span data-stu-id="7a944-108">**Parent Properties**</span></span>  
 <span data-ttu-id="7a944-109">Expanda para exibir as opções **Hierarquia pai**, **Membro pai**e **Alterar** .</span><span class="sxs-lookup"><span data-stu-id="7a944-109">Expand to view the **Parent hierarchy**, **Parent member**, and **Change** options.</span></span>  
  
 <span data-ttu-id="7a944-110">**Hierarquia pai**</span><span class="sxs-lookup"><span data-stu-id="7a944-110">**Parent hierarchy**</span></span>  
 <span data-ttu-id="7a944-111">Selecione a dimensão e a hierarquia no cubo selecionado que deve incluir o membro calculado.</span><span class="sxs-lookup"><span data-stu-id="7a944-111">Select the dimension and hierarchy in the selected cube that is to include the calculated member.</span></span> <span data-ttu-id="7a944-112">Selecione MEASURES para definir uma medida calculada.</span><span class="sxs-lookup"><span data-stu-id="7a944-112">Select MEASURES to define a calculated measure.</span></span>  
  
 <span data-ttu-id="7a944-113">**Membro pai**</span><span class="sxs-lookup"><span data-stu-id="7a944-113">**Parent member**</span></span>  
 <span data-ttu-id="7a944-114">Selecione o membro abaixo do qual o membro calculado deve ser exibido.</span><span class="sxs-lookup"><span data-stu-id="7a944-114">Select the member beneath which the calculated member is to appear.</span></span>  
  
 <span data-ttu-id="7a944-115">**Observação** esta opção estará disponível se **Hierarquia pai** especificar uma hierarquia diferente de MEASURES.</span><span class="sxs-lookup"><span data-stu-id="7a944-115">**Note** This option is available if **Parent hierarchy** specifies a hierarchy other than MEASURES.</span></span>  
  
 <span data-ttu-id="7a944-116">**Alteração**</span><span class="sxs-lookup"><span data-stu-id="7a944-116">**Change**</span></span>  
 <span data-ttu-id="7a944-117">Selecione para exibir a caixa de diálogo **Selecionar Membro Pai** e escolher um membro para **Membro pai**.</span><span class="sxs-lookup"><span data-stu-id="7a944-117">Select to display the **Select Parent Member** dialog box and choose a member for **Parent member**.</span></span> <span data-ttu-id="7a944-118">Para obter mais informações sobre a caixa de diálogo **Selecionar Membro Pai**, consulte [Caixa de diálogo Selecionar Membro Pai &#40;Analysis Services – Dados Multidimensionais&#41;](select-parent-member-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="7a944-118">For more information about the **Select Parent Member** dialog box, see [Select Parent Member Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](select-parent-member-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="7a944-119">**Expression**</span><span class="sxs-lookup"><span data-stu-id="7a944-119">**Expression**</span></span>  
 <span data-ttu-id="7a944-120">Expanda para exibir ou editar a expressão MDX do membro calculado.</span><span class="sxs-lookup"><span data-stu-id="7a944-120">Expand to view or edit the Multidimensional Expressions (MDX) expression for the calculated member.</span></span>  
  
 <span data-ttu-id="7a944-121">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="7a944-121">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a944-122">É recomendável que essa expressão avalie para uma cadeia de caracteres ou para um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="7a944-122">It is recommended that this expression evaluate to a string or to a numeric value.</span></span>  
  
 <span data-ttu-id="7a944-123">**Propriedades Adicionais**</span><span class="sxs-lookup"><span data-stu-id="7a944-123">**Additional Properties**</span></span>  
 <span data-ttu-id="7a944-124">Expanda para exibir as opções **Cadeia de formato**, **Visível**, **Comportamento não vazio**, **Expressões de Cores**e **Expressões de Fonte** .</span><span class="sxs-lookup"><span data-stu-id="7a944-124">Expand to view the **Format string**, **Visible**, **Non-empty behavior**, **Color Expressions**, and **Font Expressions** options.</span></span>  
  
 <span data-ttu-id="7a944-125">**Cadeia de formato**</span><span class="sxs-lookup"><span data-stu-id="7a944-125">**Format string**</span></span>  
 <span data-ttu-id="7a944-126">Digite a cadeia de formato MDX usada para formatar o valor retornado pelo membro calculado ou selecione uma cadeia de formato predefinida.</span><span class="sxs-lookup"><span data-stu-id="7a944-126">Type the MDX format string used to format the value returned by the calculated member, or select a predefined format string.</span></span>  
  
 <span data-ttu-id="7a944-127">Para obter mais informações sobre cadeias de formato MDX, consulte [Conteúdo FORMAT_STRING &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-format-string-contents.md).</span><span class="sxs-lookup"><span data-stu-id="7a944-127">For more information about MDX format strings, see [FORMAT_STRING Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-format-string-contents.md).</span></span>  
  
 <span data-ttu-id="7a944-128">**Visível**</span><span class="sxs-lookup"><span data-stu-id="7a944-128">**Visible**</span></span>  
 <span data-ttu-id="7a944-129">Selecione **Verdadeiro** para permitir que o membro calculado seja visível para aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="7a944-129">Select **True** to allow the calculated member to be visible to client applications.</span></span>  
  
 <span data-ttu-id="7a944-130">**Comportamento não vazio**</span><span class="sxs-lookup"><span data-stu-id="7a944-130">**Non-empty behavior**</span></span>  
 <span data-ttu-id="7a944-131">Selecione o nome da medida usada para resolver consultas NÃO VAZIAS em MDX para o membro calculado.</span><span class="sxs-lookup"><span data-stu-id="7a944-131">Select the name of the measure used to resolve NON EMPTY queries in MDX for the calculated member.</span></span> <span data-ttu-id="7a944-132">Se a propriedade **Comportamento Não Vazio** estiver em branco, o membro calculado deverá ser avaliado repetidamente para determinar se um membro está vazio.</span><span class="sxs-lookup"><span data-stu-id="7a944-132">If the **Non Empty Behavior** property is blank, the calculated member must be evaluated repeatedly to determine if a member is empty.</span></span> <span data-ttu-id="7a944-133">Se a propriedade **Comportamento Não Vazio** contiver o nome de uma medida, o membro calculado será tratado como vazio se a medida especificada estiver vazia.</span><span class="sxs-lookup"><span data-stu-id="7a944-133">If the **Non Empty Behavior** property contains the name of a measure, the calculated member is treated as empty if the specified measure is empty.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="7a944-134">Essa propriedade é preterida.</span><span class="sxs-lookup"><span data-stu-id="7a944-134">This property is deprecated.</span></span> <span data-ttu-id="7a944-135">Evite configurá-la.</span><span class="sxs-lookup"><span data-stu-id="7a944-135">Avoid setting it.</span></span> <span data-ttu-id="7a944-136">Consulte [recursos de Analysis Services preteridos no SQL Server 2014](deprecated-analysis-services-features-in-sql-server-2014.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="7a944-136">See [Deprecated Analysis Services Features in SQL Server 2014](deprecated-analysis-services-features-in-sql-server-2014.md) for details.</span></span>  
  
 <span data-ttu-id="7a944-137">**Expressões de Cores**</span><span class="sxs-lookup"><span data-stu-id="7a944-137">**Color Expressions**</span></span>  
 <span data-ttu-id="7a944-138">Expanda para exibir as opções **Cor de primeiro plano** e **Cor de fundo** .</span><span class="sxs-lookup"><span data-stu-id="7a944-138">Expand to view the **Fore color** and **Back color** options.</span></span>  
  
 <span data-ttu-id="7a944-139">**Cor de primeiro plano**</span><span class="sxs-lookup"><span data-stu-id="7a944-139">**Fore color**</span></span>  
 <span data-ttu-id="7a944-140">Digite a expressão MDX que fornece a cor de primeiro plano do membro calculado.</span><span class="sxs-lookup"><span data-stu-id="7a944-140">Type the MDX expression that provides the foreground color of the calculated member.</span></span>  
  
 <span data-ttu-id="7a944-141">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="7a944-141">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="7a944-142">Clique no botão de seleção de cor para exibir a caixa de diálogo **Cor** e inserir o valor de RGB (Vermelho-Verde-Azul) para uma cor especificada na expressão MDX.</span><span class="sxs-lookup"><span data-stu-id="7a944-142">Click the color selection button to display the **Color** dialog box and insert the RGB (Red-Green-Blue) value for a specified color into the MDX expression.</span></span> <span data-ttu-id="7a944-143">Para obter mais informações sobre valores RGB, consulte [Conteúdo de FORE_COLOR e BACK_COLOR &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span><span class="sxs-lookup"><span data-stu-id="7a944-143">For more information about RGB values, see [FORE_COLOR and BACK_COLOR Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span></span>  
  
 <span data-ttu-id="7a944-144">**Cor de fundo**</span><span class="sxs-lookup"><span data-stu-id="7a944-144">**Back color**</span></span>  
 <span data-ttu-id="7a944-145">Digite a expressão MDX que fornece a cor de fundo do membro calculado.</span><span class="sxs-lookup"><span data-stu-id="7a944-145">Type the MDX expression that provides the background color of the calculated member.</span></span>  
  
 <span data-ttu-id="7a944-146">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="7a944-146">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="7a944-147">Clique no botão de seleção de cor para exibir a caixa de diálogo **Cor** e inserir o valor de RGB (Vermelho-Verde-Azul) para uma cor especificada na expressão MDX.</span><span class="sxs-lookup"><span data-stu-id="7a944-147">Click the color selection button to display the **Color** dialog box and insert the RGB (Red-Green-Blue) value for a specified color into the MDX expression.</span></span> <span data-ttu-id="7a944-148">Para obter mais informações sobre valores RGB, consulte [Conteúdo de FORE_COLOR e BACK_COLOR &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span><span class="sxs-lookup"><span data-stu-id="7a944-148">For more information about RGB values, see [FORE_COLOR and BACK_COLOR Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span></span>  
  
 <span data-ttu-id="7a944-149">**Expressões de Fonte**</span><span class="sxs-lookup"><span data-stu-id="7a944-149">**Font Expressions**</span></span>  
 <span data-ttu-id="7a944-150">Expanda para exibir as opções **Nome da fonte**, **Tamanho da fonte**e **Sinalizadores de fonte** .</span><span class="sxs-lookup"><span data-stu-id="7a944-150">Expand to view the **Font name**, **Font size**, and **Font flags** options.</span></span>  
  
 <span data-ttu-id="7a944-151">**Nome da fonte**</span><span class="sxs-lookup"><span data-stu-id="7a944-151">**Font name**</span></span>  
 <span data-ttu-id="7a944-152">Digite a expressão MDX que fornece o nome da fonte usada para o membro calculado.</span><span class="sxs-lookup"><span data-stu-id="7a944-152">Type the MDX expression that provides the name of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="7a944-153">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="7a944-153">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="7a944-154">Clique no botão de seleção de fonte para exibir a caixa de diálogo **Fonte** e inserir os valores de propriedades para uma fonte especificada na expressão MDX.</span><span class="sxs-lookup"><span data-stu-id="7a944-154">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="7a944-155">Para obter mais informações sobre valores de propriedades, consulte [Criando e usando valores de propriedade &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="7a944-155">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
 <span data-ttu-id="7a944-156">**Tamanho da fonte**</span><span class="sxs-lookup"><span data-stu-id="7a944-156">**Font size**</span></span>  
 <span data-ttu-id="7a944-157">Digite a expressão MDX que fornece o tamanho da fonte usada para o membro calculado.</span><span class="sxs-lookup"><span data-stu-id="7a944-157">Type the MDX expression that provides the size of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="7a944-158">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="7a944-158">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="7a944-159">Clique no botão de seleção de fonte para exibir a caixa de diálogo **Fonte** e inserir os valores de propriedades para uma fonte especificada na expressão MDX.</span><span class="sxs-lookup"><span data-stu-id="7a944-159">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="7a944-160">Para obter mais informações sobre valores de propriedades, consulte [Criando e usando valores de propriedade &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="7a944-160">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
 <span data-ttu-id="7a944-161">**Sinalizadores de fonte**</span><span class="sxs-lookup"><span data-stu-id="7a944-161">**Font flags**</span></span>  
 <span data-ttu-id="7a944-162">Digite a expressão MDX que fornece o valor de bitmap que contém os sinalizadores de fonte, como sublinhado ou negrito, da fonte usada para o membro calculado.</span><span class="sxs-lookup"><span data-stu-id="7a944-162">Type the MDX expression that provides the bitmapped value containing the font flags, such as underline or bold, of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="7a944-163">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="7a944-163">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="7a944-164">Clique no botão de seleção de fonte para exibir a caixa de diálogo **Fonte** e inserir os valores de propriedades para uma fonte especificada na expressão MDX.</span><span class="sxs-lookup"><span data-stu-id="7a944-164">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="7a944-165">Para obter mais informações sobre valores de propriedades, consulte [Criando e usando valores de propriedade &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="7a944-165">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a944-166">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7a944-166">See Also</span></span>  
 <span data-ttu-id="7a944-167">[Cálculos](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="7a944-167">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="7a944-168">[Criar membros calculados](multidimensional-models/create-calculated-members.md) </span><span class="sxs-lookup"><span data-stu-id="7a944-168">[Create Calculated Members](multidimensional-models/create-calculated-members.md) </span></span>  
 <span data-ttu-id="7a944-169">[O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7a944-169">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="7a944-170">[Cálculos &#40;designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](calculations-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7a944-170">[Calculations &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculations-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="7a944-171">[Barra de ferramentas &#40;guia cálculos, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7a944-171">[Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="7a944-172">[Guia cálculos do organizador de script &#40;, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7a944-172">[Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="7a944-173">[Ferramentas de cálculo &#40;guia cálculos, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7a944-173">[Calculation Tools &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="7a944-174">[Editor de formulário de conjunto nomeado &#40;guia cálculos, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7a944-174">[Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="7a944-175">Editor de script &#40;guia cálculos, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="7a944-175">Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md)  
  
  
