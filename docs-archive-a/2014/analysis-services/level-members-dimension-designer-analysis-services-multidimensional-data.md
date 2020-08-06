---
title: Nível e Membros (guia navegador, designer de dimensão) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.browsertab.levelsandmembers.f1
ms.assetid: 3f61e384-5b4e-4480-a7ed-b408de2fdea7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 21680f00b82b5410e2c7a67122fdcfeb78c999dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686438"
---
# <a name="level-and-members-browser-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="59b46-102">Nível e Membros (guia Navegador, Designer de Dimensão) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="59b46-102">Level and Members (Browser Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="59b46-103">Use este painel para procurar os membros da hierarquia e linguagem atualmente selecionadas.</span><span class="sxs-lookup"><span data-stu-id="59b46-103">Use this pane to browse the members of the currently selected hierarchy and language.</span></span> <span data-ttu-id="59b46-104">Para selecionar uma hierarquia ou linguagem para navegar, use as opções **Hierarquia** e **Linguagem** no painel **Barra de Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="59b46-104">To select a hierarchy or language to browse, use the **Hierarchy** and **Language** options on the **Toolbar** pane.</span></span> <span data-ttu-id="59b46-105">Para obter mais informações sobre o painel Barra de Ferramentas, consulte [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="59b46-105">For more information about the Toolbar pane, see [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="writeback-mode"></a><span data-ttu-id="59b46-106">Modo Write-back</span><span class="sxs-lookup"><span data-stu-id="59b46-106">Writeback Mode</span></span>  
 <span data-ttu-id="59b46-107">A funcionalidade deste painel alterará se o modo write-back estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="59b46-107">The functionality of this pane changes if writeback mode is enabled.</span></span> <span data-ttu-id="59b46-108">A dimensão selecionada deverá ser habilitada para gravação (isto é, a propriedade `WriteEnabled` da dimensão deverá ser definida como verdadeira) e a dimensão deverá ser implantada em uma instância de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para habilitar o modo write-back.</span><span class="sxs-lookup"><span data-stu-id="59b46-108">The selected dimension must be write-enabled (in other words, the `WriteEnabled` property of the dimension must be set to true) and the dimension must be deployed to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance in order to enable writeback mode.</span></span>  
  
 <span data-ttu-id="59b46-109">Para habilitar o modo write-back, você poderá selecionar **Write-back** no painel **Barra de Ferramentas** ou clicar com o botão direito do mouse no painel **Nível e Membros** e selecionar **Write-back** no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="59b46-109">To enable writeback mode, you can either select **Writeback** from the **Toolbar** pane, or right-click the **Level and Members** pane and select **Writeback** from the context menu.</span></span>  
  
 <span data-ttu-id="59b46-110">Se o modo write-back estiver habilitado, você poderá executar as seguintes ações adicionais no painel **Nível e Membros** :</span><span class="sxs-lookup"><span data-stu-id="59b46-110">If writeback mode is enabled, you can perform the following additional actions in the **Level and Members** pane:</span></span>  
  
|<span data-ttu-id="59b46-111">Para fazer</span><span class="sxs-lookup"><span data-stu-id="59b46-111">To do</span></span>|<span data-ttu-id="59b46-112">Executar</span><span class="sxs-lookup"><span data-stu-id="59b46-112">Perform</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="59b46-113">Criar membros irmão e filho dentro da hierarquia selecionada.</span><span class="sxs-lookup"><span data-stu-id="59b46-113">Create sibling and child members within the selected hierarchy.</span></span>|<span data-ttu-id="59b46-114">Clique com o botão direito do mouse no membro selecionado e selecione **Criar irmão**para criar um membro irmão ou **Criar Filho**para criar um membro irmão, no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="59b46-114">Right-click the selected member and select either **Create Sibling**, to create a sibling member, or **Create Child**, to create a child member, from the context menu.</span></span>|  
|<span data-ttu-id="59b46-115">Mova um membro selecionado para cima ou para baixo na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="59b46-115">Move a selected member up or down the hierarchy.</span></span>|<span data-ttu-id="59b46-116">Arraste o membro selecionado até o membro pai ou filho apropriado ou clique em **Aumentar Recuo** ou **Diminuir Recuo** no painel **Barra de Ferramentas** para mover o membro selecionado para cima ou para baixo nos níveis da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="59b46-116">Either drag the selected member to the appropriate parent or child member, or click **Increase Indent** or **Decrease Indent** on the **Toolbar** pane to move the selected member up or down the levels of the hierarchy.</span></span>|  
|<span data-ttu-id="59b46-117">Renomeie um membro selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-117">Rename a selected member.</span></span>|<span data-ttu-id="59b46-118">Clique com o botão direito do mouse no membro selecionado e selecione **Renomear**ou clique em um membro já selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-118">Either right-click the selected member and select **Rename**, or click an already-selected member.</span></span>|  
|<span data-ttu-id="59b46-119">Edite valores de propriedade dos membros</span><span class="sxs-lookup"><span data-stu-id="59b46-119">Edit member property values</span></span>|<span data-ttu-id="59b46-120">Clique duas vezes no valor na propriedade do membro selecionado para que o membro selecionado edite</span><span class="sxs-lookup"><span data-stu-id="59b46-120">Double-click the value in the selected member property for the selected member to edit the value.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="59b46-121">Opções</span><span class="sxs-lookup"><span data-stu-id="59b46-121">Options</span></span>  
 <span data-ttu-id="59b46-122">**Nível atual**</span><span class="sxs-lookup"><span data-stu-id="59b46-122">**Current level**</span></span>  
 <span data-ttu-id="59b46-123">Exibe o nível ao qual pertence o membro atualmente selecionado em **Árvore** .</span><span class="sxs-lookup"><span data-stu-id="59b46-123">Displays the level to which the currently selected member in **Tree** belongs.</span></span>  
  
 <span data-ttu-id="59b46-124">**Três**</span><span class="sxs-lookup"><span data-stu-id="59b46-124">**Tree**</span></span>  
 <span data-ttu-id="59b46-125">Exibe os membros da hierarquia e linguagem atualmente selecionadas.</span><span class="sxs-lookup"><span data-stu-id="59b46-125">Displays the members of the currently selected hierarchy and language.</span></span>  
  
 <span data-ttu-id="59b46-126">Se as propriedades dos membros forem selecionadas da opção **Propriedades do Membro** do painel Barra de Ferramentas, cada propriedade de membro será exibida como uma coluna.</span><span class="sxs-lookup"><span data-stu-id="59b46-126">If member properties are selected from the **Member Properties** option of the Toolbar pane, each member property is displayed as a column.</span></span>  
  
 <span data-ttu-id="59b46-127">Se o modo write-back estiver habilitado, uma coluna para cada coluna de chave associada com o atributo chave na dimensão será exibida.</span><span class="sxs-lookup"><span data-stu-id="59b46-127">If writeback mode is enabled, one column for each key column associated with the key attribute in the dimension is displayed.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="59b46-128">Menu de contexto</span><span class="sxs-lookup"><span data-stu-id="59b46-128">Context Menu</span></span>  
 <span data-ttu-id="59b46-129">As seguintes opções estarão disponíveis no menu de contexto exibido ao clicar com o botão direito do mouse em qualquer parte do painel **Nível e Membros** do membro selecionado:</span><span class="sxs-lookup"><span data-stu-id="59b46-129">The following options are available in the context menu displayed by right-clicking any part of the **Level and Members** pane for the selected member:</span></span>  
  
 <span data-ttu-id="59b46-130">**Criar irmão**</span><span class="sxs-lookup"><span data-stu-id="59b46-130">**Create sibling**</span></span>  
 <span data-ttu-id="59b46-131">Cria um membro novo no mesmo nível do membro selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-131">Creates a new member at the same level as the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-132">Esta opção só será habilitada se um membro em um nível diferente do nível (Tudo) estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-132">This option is enabled only if a member at a level other than the (All) level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-133">Esta opção será exibida somente se o modo write-back for habilitado.</span><span class="sxs-lookup"><span data-stu-id="59b46-133">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="59b46-134">**Criar Filho**</span><span class="sxs-lookup"><span data-stu-id="59b46-134">**Create child**</span></span>  
 <span data-ttu-id="59b46-135">Cria um membro novo no nível inferior próximo do membro selecionado, como um filho do membro selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-135">Creates a new member at the next lower level as the selected member, as a child of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-136">Esta opção só será habilitada se um membro em um nível diferente do nível inferior estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-136">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-137">Esta opção será exibida somente se o modo write-back for habilitado.</span><span class="sxs-lookup"><span data-stu-id="59b46-137">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="59b46-138">**Recortar**</span><span class="sxs-lookup"><span data-stu-id="59b46-138">**Cut**</span></span>  
 <span data-ttu-id="59b46-139">Copia os membros selecionados à área de transferência e os remove da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="59b46-139">Copies the selected members to the clipboard and removes them from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-140">Esta opção só será habilitada se um membro diferente do Todos estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-140">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-141">Esta opção será exibida somente se o modo write-back for habilitado.</span><span class="sxs-lookup"><span data-stu-id="59b46-141">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="59b46-142">**Colar**</span><span class="sxs-lookup"><span data-stu-id="59b46-142">**Paste**</span></span>  
 <span data-ttu-id="59b46-143">Cola membros anteriormente removidos usando **Recortar** imediatamente após o membro selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-143">Pastes members previously removed using **Cut** immediately after the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-144">Esta opção será exibida somente se o modo write-back for habilitado.</span><span class="sxs-lookup"><span data-stu-id="59b46-144">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="59b46-145">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="59b46-145">**Delete**</span></span>  
 <span data-ttu-id="59b46-146">Remove os membros selecionados da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="59b46-146">Removes the selected members from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-147">Esta opção só será habilitada se um membro diferente do Todos estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-147">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-148">Esta opção será exibida somente se o modo write-back for habilitado.</span><span class="sxs-lookup"><span data-stu-id="59b46-148">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="59b46-149">**Renomear**</span><span class="sxs-lookup"><span data-stu-id="59b46-149">**Rename**</span></span>  
 <span data-ttu-id="59b46-150">Selecione para editar o nome do membro selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-150">Select to edit the name of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-151">Esta opção só será habilitada se um membro diferente do Todos estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-151">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-152">Esta opção será exibida somente se o modo write-back for habilitado.</span><span class="sxs-lookup"><span data-stu-id="59b46-152">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="59b46-153">**Filtrar Membros**</span><span class="sxs-lookup"><span data-stu-id="59b46-153">**Filter Members**</span></span>  
 <span data-ttu-id="59b46-154">Exibe a caixa de diálogo **Filtrar Membros** para filtrar membros exibidos em **Nível e Membros** da hierarquia selecionada.</span><span class="sxs-lookup"><span data-stu-id="59b46-154">Displays the **Filter Members** dialog box to filter members displayed in **Level and Members** for the selected hierarchy.</span></span> <span data-ttu-id="59b46-155">Para obter mais informações sobre a caixa de diálogo **Filtrar Membros**, consulte [Caixa de diálogo Filtrar Membros &#40;Analysis Services – Dados Multidimensionais&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="59b46-155">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="59b46-156">**Expandir Tudo**</span><span class="sxs-lookup"><span data-stu-id="59b46-156">**Expand All**</span></span>  
 <span data-ttu-id="59b46-157">Expande todos os membros em **Árvore**.</span><span class="sxs-lookup"><span data-stu-id="59b46-157">Expands all members in **Tree**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b46-158">Esta opção só será habilitada se um membro em um nível diferente do nível inferior estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="59b46-158">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
 <span data-ttu-id="59b46-159">**Recolher Tudo**</span><span class="sxs-lookup"><span data-stu-id="59b46-159">**Collapse All**</span></span>  
 <span data-ttu-id="59b46-160">Recolhe todos os membros em **Árvore**.</span><span class="sxs-lookup"><span data-stu-id="59b46-160">Collapse all members in **Tree**.</span></span>  
  
 <span data-ttu-id="59b46-161">**Expandir Membros**</span><span class="sxs-lookup"><span data-stu-id="59b46-161">**Expand Member**</span></span>  
 <span data-ttu-id="59b46-162">Expande o membro selecionado em **Árvore**.</span><span class="sxs-lookup"><span data-stu-id="59b46-162">Expand the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="59b46-163">**Recolher Membro**</span><span class="sxs-lookup"><span data-stu-id="59b46-163">**Collapse Member**</span></span>  
 <span data-ttu-id="59b46-164">Recolhe o membro selecionado em **Árvore**.</span><span class="sxs-lookup"><span data-stu-id="59b46-164">Collapse the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="59b46-165">**Write-back**</span><span class="sxs-lookup"><span data-stu-id="59b46-165">**Writeback**</span></span>  
 <span data-ttu-id="59b46-166">Selecione para habilitar o modo write-back.</span><span class="sxs-lookup"><span data-stu-id="59b46-166">Select to enable writeback mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b46-167">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="59b46-167">See Also</span></span>  
 <span data-ttu-id="59b46-168">[Barra de ferramentas &#40;guia navegador, designer de dimensão&#41; &#40;Analysis Services de dados multidimensionais&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="59b46-168">[Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="59b46-169">Navegador &#40;designer de dimensão&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="59b46-169">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
