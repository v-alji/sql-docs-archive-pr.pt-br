---
title: Ferramentas de cálculo (guia KPIs, designer de cubo) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpisview.calculationtoolspane.f1
ms.assetid: c030c725-7763-4c23-9988-4b274a88fc31
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7bb8470173b0a413795fb7b5e3213bb50aa8ee43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571083"
---
# <a name="calculation-tools-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="5e0ea-102">Ferramentas de Cálculo (guia KPIs, Designer de Cubo) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="5e0ea-102">Calculation Tools (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="5e0ea-103">Use o painel **Ferramentas de Cálculo** da guia **KPIs** no Designer de Cubo para explorar metadados, funções e modelos disponíveis para uso em KPIs (indicadores chave de desempenho).</span><span class="sxs-lookup"><span data-stu-id="5e0ea-103">Use the **Calculation Tools** pane on the **KPIs** tab in Cube Designer to explore metadata, functions, and templates available for use in Key Performance Indicators (KPIs).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e0ea-104">Este painel é exibido apenas na exibição de formulário.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-104">This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5e0ea-105">Opções</span><span class="sxs-lookup"><span data-stu-id="5e0ea-105">Options</span></span>  
 <span data-ttu-id="5e0ea-106">**Metadados**</span><span class="sxs-lookup"><span data-stu-id="5e0ea-106">**Metadata**</span></span>  
 <span data-ttu-id="5e0ea-107">Exibe os metadados do cubo selecionado.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-107">Displays the metadata for the selected cube.</span></span>  
  
 <span data-ttu-id="5e0ea-108">Arraste um elemento selecionado para o painel **Editor de Formulário de KPI** para incluir a sintaxe MDX daquele elemento no local selecionado no painel.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-108">Drag a selected element to the **KPI Form Editor** pane to include the Multidimensional Expressions (MDX) syntax for that element at the selected location in the pane.</span></span>  
  
 <span data-ttu-id="5e0ea-109">**Funções**</span><span class="sxs-lookup"><span data-stu-id="5e0ea-109">**Functions**</span></span>  
 <span data-ttu-id="5e0ea-110">Exibe as funções disponíveis para expressões e condições.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-110">Displays the functions available for expressions and conditions.</span></span>  
  
 <span data-ttu-id="5e0ea-111">Arraste um elemento selecionado para o painel **Editor de Formulário de KPI** para incluir a sintaxe MDX daquele elemento no local selecionado no painel.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-111">Drag a selected element to the **KPI Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e0ea-112">No modo de projeto, a caixa de diálogo **Ferramentas de Cálculo** lê as informações desta opção em um arquivo XML denominado MDXFunctions.xml fornecido com o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e0ea-112">In project mode, the **Calculation Tools** dialog box reads information for this option from an XML file named MDXFunctions.xml, included with [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="5e0ea-113">Em modo online, informações para esta opção são recuperadas do conjunto de linhas de esquema de MDSCHEMA_FUNCTIONS da instância.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-113">In online mode, information for this option is retrieved from the MDSCHEMA_FUNCTIONS schema rowset for the instance.</span></span>  
  
 <span data-ttu-id="5e0ea-114">**Modelos**</span><span class="sxs-lookup"><span data-stu-id="5e0ea-114">**Templates**</span></span>  
 <span data-ttu-id="5e0ea-115">Exibe os modelos predefinidos disponíveis para KPIs.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-115">Displays the predefined templates available for KPIs.</span></span>  
  
 <span data-ttu-id="5e0ea-116">Arraste um elemento selecionado para o painel **Editor de Formulário de KPI** para incluir a sintaxe MDX daquele elemento no local selecionado no painel.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-116">Drag a selected element to the **KPI Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="5e0ea-117">Menu de contexto</span><span class="sxs-lookup"><span data-stu-id="5e0ea-117">Context Menu</span></span>  
 <span data-ttu-id="5e0ea-118">As seguintes opções estão disponíveis no menu de contexto exibido ao clicar com o botão direito do mouse em um elemento exibido no painel **Ferramentas de Cálculo** :</span><span class="sxs-lookup"><span data-stu-id="5e0ea-118">The following options are available in the context menu displayed by right-clicking an element in the **Calculation Tools** pane:</span></span>  
  
 <span data-ttu-id="5e0ea-119">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="5e0ea-119">**Copy**</span></span>  
 <span data-ttu-id="5e0ea-120">Selecione para copiar o elemento selecionado em **Metadados** ou **Funções** na Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-120">Select to copy the selected element in **Metadata** or **Functions** to the Clipboard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e0ea-121"> Esta opção não será exibida se a opção **Modelos** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-121">This option is not displayed if **Templates** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e0ea-122"> Esta opção será desabilitada se o membro selecionado não puder ser copiado, como a pasta **Conjuntos** de uma dimensão exibida em **Metadados** ou a pasta de grupo de funções de uma função exibida em **Funções**.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-122">This option is disabled if the selected member cannot be copied, such as the **Sets** folder of a dimension displayed in **Metadata** or the function group folder for a function displayed in **Functions**.</span></span>  
  
 <span data-ttu-id="5e0ea-123">**Filtrar Membros**</span><span class="sxs-lookup"><span data-stu-id="5e0ea-123">**Filter Members**</span></span>  
 <span data-ttu-id="5e0ea-124">Clique para exibir a caixa de diálogo **Filtrar Membros** e filtrar os membros exibidos para o elemento selecionado em **Metadados**.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-124">Select to display the **Filter Members** dialog box and filter members displayed for the selected element in **Metadata**.</span></span> <span data-ttu-id="5e0ea-125">Para obter mais informações sobre a caixa de diálogo **Filtrar Membros**, consulte [Caixa de diálogo Filtrar Membros &#40;Analysis Services – Dados Multidimensionais&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="5e0ea-125">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e0ea-126"> Esta opção será exibida apenas se a opção **Metadados** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-126">This option is displayed only if **Metadata** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e0ea-127"> Esta opção estará habilitada apenas se um nível de um atributo estiver selecionado em **Metadados**.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-127">This option is enabled only if a level for an attribute is selected in **Metadata**.</span></span>  
  
 <span data-ttu-id="5e0ea-128">**Adicionar Modelo**</span><span class="sxs-lookup"><span data-stu-id="5e0ea-128">**Add Template**</span></span>  
 <span data-ttu-id="5e0ea-129">Selecione para adicionar um novo membro calculado, conjunto nomeado ou comando de script baseado no modelo selecionado ao script do cubo e exibir a exibição de formulário no **Editor de Formulário de KPI** .</span><span class="sxs-lookup"><span data-stu-id="5e0ea-129">Select to add a new calculated member, named set, or script command based on the selected template to the cube script and display the **KPI Form Editor** in form view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e0ea-130"> Esta opção será exibida apenas se a opção **Metadados** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-130">This option is displayed only if **Metadata** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0ea-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5e0ea-131">See Also</span></span>  
 <span data-ttu-id="5e0ea-132">[O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5e0ea-132">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="5e0ea-133">[KPIs &#40;designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5e0ea-133">[KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="5e0ea-134">[Barra de ferramentas &#40;guia KPIs, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](toolbar-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5e0ea-134">[Toolbar &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="5e0ea-135">[Guia KPIs do &#40;Gallery, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](kpi-organizer-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5e0ea-135">[KPI Organizer &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpi-organizer-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="5e0ea-136">[Editor de formulário de KPI &#40;guia KPIs, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](kpi-form-editor-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5e0ea-136">[KPI Form Editor &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpi-form-editor-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="5e0ea-137">Navegador KPI &#40;guia KPIs, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="5e0ea-137">KPI Browser &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpi-browser-kpis-tab-cube-designer-analysis-services-multidimensional-data.md)  
  
  
