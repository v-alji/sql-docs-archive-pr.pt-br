---
title: Editor de formulário de ação de detalhamento (guia ações, designer de cubo) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.actionexpression.drillthroughaction.f1
ms.assetid: 225fd818-b5ea-494f-b67b-66e09798274a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 546448bd05f3af45b7093acb2dbb9d1e1a8f1bd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582192"
---
# <a name="drillthrough-action-form-editor-actions-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="73822-102">Editor de Formulário de Ação de Extração de Detalhes (guia Ações, Designer de Cubo) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="73822-102">Drillthrough Action Form Editor (Actions Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="73822-103">Use o painel **Editor de Formulário de Ação de Extração de Detalhes** na guia **Ações** no Designer de Cubo para modificar a ação de extração de detalhes selecionada no painel **Organizador de Ações** .</span><span class="sxs-lookup"><span data-stu-id="73822-103">Use the **Drillthrough Action Form Editor** pane on the **Actions** tab in Cube Designer to modify the drillthrough action selected in the **Action Organizer** pane.</span></span> <span data-ttu-id="73822-104">Para obter mais informações sobre ações de detalhamento, consulte [Ações &#40;Analysis Services – Dados Multidimensionais&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="73822-104">For more information about drillthrough actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73822-105">Ações de extração de detalhes não fazem mais busca detalhada no repositório de dados subjacente.</span><span class="sxs-lookup"><span data-stu-id="73822-105">Drillthrough actions no longer drill down to the underlying data store.</span></span> <span data-ttu-id="73822-106">A informações acessadas por ações de extração de detalhes devem ser modeladas dentro do cubo usando membros de dimensão ou de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="73822-106">The information that drillthrough actions access must be modeled within the cube by using dimension or hierarchy members.</span></span>  
  
## <a name="options"></a><span data-ttu-id="73822-107">Opções</span><span class="sxs-lookup"><span data-stu-id="73822-107">Options</span></span>  
 <span data-ttu-id="73822-108">**name**</span><span class="sxs-lookup"><span data-stu-id="73822-108">**name**</span></span>  
 <span data-ttu-id="73822-109">Digite o nome da ação.</span><span class="sxs-lookup"><span data-stu-id="73822-109">Type the name of the action.</span></span>  
  
 <span data-ttu-id="73822-110">**Destino da Ação**</span><span class="sxs-lookup"><span data-stu-id="73822-110">**Action Target**</span></span>  
 <span data-ttu-id="73822-111">Expanda para exibir a opção **Membros de grupos de medidas** .</span><span class="sxs-lookup"><span data-stu-id="73822-111">Expand to view the **Measure group members** option.</span></span>  
  
 <span data-ttu-id="73822-112">**Membros de grupos de medidas**</span><span class="sxs-lookup"><span data-stu-id="73822-112">**Measure group members**</span></span>  
 <span data-ttu-id="73822-113">Selecione o grupo de medidas ao qual a ação de extração de detalhes deve ser associada.</span><span class="sxs-lookup"><span data-stu-id="73822-113">Select the measure group to which the drillthrough action is to be associated.</span></span>  
  
 <span data-ttu-id="73822-114">**Condição (Opcional)**</span><span class="sxs-lookup"><span data-stu-id="73822-114">**Condition (Optional)**</span></span>  
 <span data-ttu-id="73822-115">Digite a expressão MDX que descreve uma condição opcional usada em conjunto com **Membros de grupos de medidas**que restringe ainda mais quando a ação está disponível.</span><span class="sxs-lookup"><span data-stu-id="73822-115">Enter the Multidimensional Expressions (MDX) expression that describes an optional condition, used in conjunction with **Measure group members**, which further restricts when the action is available.</span></span> <span data-ttu-id="73822-116">A expressão deve retornar um valor booliano que, se verdadeiro, indicará que a ação está disponível.</span><span class="sxs-lookup"><span data-stu-id="73822-116">The expression must return a Boolean value that, if true, indicates the action is available.</span></span>  
  
 <span data-ttu-id="73822-117">Arraste elementos selecionados do painel **Ferramentas de Cálculo** para esta opção para incluir a sintaxe MDX para o elemento selecionado.</span><span class="sxs-lookup"><span data-stu-id="73822-117">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="73822-118">**Colunas de Extração de Detalhes**</span><span class="sxs-lookup"><span data-stu-id="73822-118">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="73822-119">Expanda para exibir uma grade na qual indicar os atributos retornados quando o usuário executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="73822-119">Expand to display a grid in which to indicate the attributes that are returned when the user runs this action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73822-120">É possível selecionar mais do que uma dimensão, mas nenhuma dimensão pode ser usada mais de uma vez em uma ação de extração de detalhes.</span><span class="sxs-lookup"><span data-stu-id="73822-120">You can select more than one dimension, but no dimension can be used more than once in a drillthrough action.</span></span>  
  
 <span data-ttu-id="73822-121">A grade contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="73822-121">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="73822-122">Column</span><span class="sxs-lookup"><span data-stu-id="73822-122">Column</span></span>|<span data-ttu-id="73822-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="73822-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="73822-124">**Dimensões**</span><span class="sxs-lookup"><span data-stu-id="73822-124">**Dimensions**</span></span>|<span data-ttu-id="73822-125">Selecione a dimensão da qual o atributo retornado é derivado.</span><span class="sxs-lookup"><span data-stu-id="73822-125">Select the dimension from which the returned attribute is derived.</span></span> <span data-ttu-id="73822-126">Selecione MEDIDAS para extração de detalhes em medidas.</span><span class="sxs-lookup"><span data-stu-id="73822-126">Select MEASURES to drillthrough on measures.</span></span>|  
|<span data-ttu-id="73822-127">**Colunas de Retorno**</span><span class="sxs-lookup"><span data-stu-id="73822-127">**Return Columns**</span></span>|<span data-ttu-id="73822-128">Selecione o atributo ou medida da dimensão selecionada a ser retornada quando a ação for executada.</span><span class="sxs-lookup"><span data-stu-id="73822-128">Select the attribute or measure from the selected dimension to be returned when the action is run.</span></span>|  
  
 <span data-ttu-id="73822-129">**Propriedades Adicionais**</span><span class="sxs-lookup"><span data-stu-id="73822-129">**Additional Properties**</span></span>  
 <span data-ttu-id="73822-130">Expanda para exibir as opções **Padrão**, **Máximo de linhas**, **Invocação**, **Aplicativo**, **Descrição**, **Legenda**e **A legenda é MDX** .</span><span class="sxs-lookup"><span data-stu-id="73822-130">Expand to view the **Default**, **Maximum rows**, **Invocation**, **Application**, **Description**, **Caption**, and **Caption Is MDX** options.</span></span>  
  
 <span data-ttu-id="73822-131">**Default**</span><span class="sxs-lookup"><span data-stu-id="73822-131">**Default**</span></span>  
 <span data-ttu-id="73822-132">Selecione **True** para incluir esta como uma ação de detalhamento padrão; caso contrário, selecione **False**.</span><span class="sxs-lookup"><span data-stu-id="73822-132">Select **True** to include this drillthrough action as a default drillthrough action, otherwise, select **False**.</span></span>  
  
 <span data-ttu-id="73822-133">Se a `RETURN` cláusula for omitida de uma `DRILLTHROUGH` instrução MDX executada por um aplicativo cliente, a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instância avaliará todas as ações de detalhamento padrão e executará a primeira ação de detalhamento padrão que retorna um conjunto não vazio.</span><span class="sxs-lookup"><span data-stu-id="73822-133">If the `RETURN` clause is omitted from an MDX `DRILLTHROUGH` statement executed by a client application, the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance evaluates all default drillthrough actions and runs the first default drillthrough action that returns a non-empty set.</span></span> <span data-ttu-id="73822-134">Para obter mais informações sobre a `DRILLTHROUGH` instrução MDX, consulte [instrução de detalhamento &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-drillthrough).</span><span class="sxs-lookup"><span data-stu-id="73822-134">For more information about the MDX `DRILLTHROUGH` statement, see [DRILLTHROUGH Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-drillthrough).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73822-135">Esta opção é usada para fins de compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="73822-135">This option is used for backwards compatibility purposes.</span></span>  
  
 <span data-ttu-id="73822-136">**Máximo de linhas**</span><span class="sxs-lookup"><span data-stu-id="73822-136">**Maximum rows**</span></span>  
 <span data-ttu-id="73822-137">Digite o número máximo de linhas a serem retornadas pela ação de extração de detalhes.</span><span class="sxs-lookup"><span data-stu-id="73822-137">Type the maximum number of rows to be returned by the drillthrough action.</span></span> <span data-ttu-id="73822-138">A configuração desta opção como zero ou como um valor vazio indica que a ação de extração de detalhes retorna todas as linhas recuperadas pela ação ao aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="73822-138">Setting this option to zero or an empty value indicates that the drillthrough action returns all rows retrieved by the action to the client application.</span></span>  
  
 <span data-ttu-id="73822-139">**Invocação**</span><span class="sxs-lookup"><span data-stu-id="73822-139">**Invocation**</span></span>  
 <span data-ttu-id="73822-140">Selecione a configuração que indica quando a ação deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="73822-140">Select the setting that indicates when the action should be carried out.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73822-141">Essa opção fornece apenas uma recomendação a um aplicativo cliente em relação a quando executar uma ação e não controla diretamente a invocação da ação.</span><span class="sxs-lookup"><span data-stu-id="73822-141">This option only provides a recommendation to a client application as to when to execute an action, and does not directly control the invocation of the action.</span></span>  
  
 <span data-ttu-id="73822-142">A tabela a seguir descreve as configurações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="73822-142">The following table describes the available settings.</span></span>  
  
|<span data-ttu-id="73822-143">Valor</span><span class="sxs-lookup"><span data-stu-id="73822-143">Value</span></span>|<span data-ttu-id="73822-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="73822-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="73822-145">Lote</span><span class="sxs-lookup"><span data-stu-id="73822-145">Batch</span></span>|<span data-ttu-id="73822-146">A ação deve ser executada como parte de uma operação em lote ou de uma tarefa do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73822-146">The action should run as part of a batch operation or an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] task.</span></span>|  
|<span data-ttu-id="73822-147">Interativo</span><span class="sxs-lookup"><span data-stu-id="73822-147">Interactive</span></span>|<span data-ttu-id="73822-148">A ação é executada quando o usuário a invoca.</span><span class="sxs-lookup"><span data-stu-id="73822-148">The action runs when the user invokes the action.</span></span>|  
|<span data-ttu-id="73822-149">Em Aberto</span><span class="sxs-lookup"><span data-stu-id="73822-149">On Open</span></span>|<span data-ttu-id="73822-150">A ação é executada quando o cubo é aberto pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="73822-150">The action runs when the cube is first opened.</span></span>|  
  
 <span data-ttu-id="73822-151">**Aplicativo**</span><span class="sxs-lookup"><span data-stu-id="73822-151">**Application**</span></span>  
 <span data-ttu-id="73822-152">Digite o nome do aplicativo que pode executar a ação de extração de detalhes.</span><span class="sxs-lookup"><span data-stu-id="73822-152">Type the name of the application that can execute the drillthrough action.</span></span>  
  
 <span data-ttu-id="73822-153">Também é possível usar essa opção para identificar qual aplicativo cliente usa essa ação mais comumente, bem como para exibir ícones adequados ao lado da ação em um menu pop-up.</span><span class="sxs-lookup"><span data-stu-id="73822-153">You can also use this option to identify which client application most commonly uses this action, as well as to display appropriate icons next to the action in a pop-up menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73822-154">Essa opção fornece apenas uma recomendação a um aplicativo cliente quanto a qual aplicativo cliente deve executar uma ação e não controla diretamente o acesso à ação.</span><span class="sxs-lookup"><span data-stu-id="73822-154">This option only provides a recommendation to a client application as to what client application should execute an action, and does not directly control access to the action.</span></span> <span data-ttu-id="73822-155">Aplicativos cliente devem ocultar todas as ações associadas a outros aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="73822-155">Client applications should hide any actions that are associated with other client applications.</span></span>  
  
 <span data-ttu-id="73822-156">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="73822-156">**Description**</span></span>  
 <span data-ttu-id="73822-157">Digite a descrição opcional da ação.</span><span class="sxs-lookup"><span data-stu-id="73822-157">Type the optional description of the action.</span></span>  
  
 <span data-ttu-id="73822-158">**Legenda**</span><span class="sxs-lookup"><span data-stu-id="73822-158">**Caption**</span></span>  
 <span data-ttu-id="73822-159">Digite a legenda a ser exibida para a ação no aplicativo cliente, se a opção **A legenda é MDX** estiver configurada como **Falso**.</span><span class="sxs-lookup"><span data-stu-id="73822-159">Type the caption to be displayed for the action in the client application if **Caption Is MDX** is set to **False**.</span></span>  
  
 <span data-ttu-id="73822-160">Digite a expressão MDX que retornará uma cadeia de caracteres para a legenda se a opção **A legenda é MDX** estiver configurada como **True**.</span><span class="sxs-lookup"><span data-stu-id="73822-160">Type the Multidimensional Expressions (MDX) expression that returns a string for the caption if **Caption Is MDX** is set to **True**.</span></span>  
  
 <span data-ttu-id="73822-161">**Legenda é MDX**</span><span class="sxs-lookup"><span data-stu-id="73822-161">**Caption Is MDX**</span></span>  
 <span data-ttu-id="73822-162">Selecione **Falso** para indicar que a **Legenda** contém uma cadeia de caracteres literal que representa uma legenda a ser exibida para a ação no aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="73822-162">Select **False** to indicate that **Caption** contains a literal string representing a caption to be displayed for the action in the client application.</span></span>  
  
 <span data-ttu-id="73822-163">Selecione **Verdadeiro** para indicar que a **Legenda** contém uma expressão MDX que retorna uma cadeia de caracteres que representa uma legenda a ser exibida para a ação no aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="73822-163">Select **True** to indicate that **Caption** contains an MDX expression that returns a string representing a caption to be displayed for the action in the client application.</span></span> <span data-ttu-id="73822-164">A expressão MDX deve ser resolvida antes da ação ser retornada ao aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="73822-164">The MDX expression must be resolved before the action is returned to the client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73822-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="73822-165">See Also</span></span>  
 <span data-ttu-id="73822-166">[Expressões multidimensionais &#40;referência de&#41; MDX](/sql/mdx/multidimensional-expressions-mdx-reference) </span><span class="sxs-lookup"><span data-stu-id="73822-166">[Multidimensional Expressions &#40;MDX&#41; Reference](/sql/mdx/multidimensional-expressions-mdx-reference) </span></span>  
 <span data-ttu-id="73822-167">[Ações &#40;designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="73822-167">[Actions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="73822-168">[Barra de ferramentas &#40;guia ações, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="73822-168">[Toolbar &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="73822-169">[Guia ações do organizador de ação &#40;, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="73822-169">[Action Organizer &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="73822-170">[Ferramentas de cálculo &#40;guia ações, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="73822-170">[Calculation Tools &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="73822-171">[Editor de formulário de ação &#40;guia ações, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="73822-171">[Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="73822-172">Editor de formulário de ação de relatório &#40;guia ações, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="73822-172">Report Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](report-action-form-editor-cube-designer-analysis-services-multidimensional-data.md)  
  
  
