---
title: Ferramentas de cálculo (guia cálculos, designer de cubo) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationsview.calculationtoolspane.f1
ms.assetid: b1aa8a1a-6532-45d2-8f53-d3e211d7197a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6701a15a7d773a90e48ec39dc976b9ef579c9ec8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571085"
---
# <a name="calculation-tools-calculations-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="3280d-102">Ferramentas de Cálculo (guia Cálculos, Designer de Cubo) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="3280d-102">Calculation Tools (Calculations Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="3280d-103">Use o painel **Ferramentas de Cálculo** da guia **Cálculos** no Designer de Cubo para explorar metadados, funções e modelos disponíveis para uso em cálculos.</span><span class="sxs-lookup"><span data-stu-id="3280d-103">Use the **Calculation Tools** pane on the **Calculations** tab in Cube Designer to explore metadata, functions, and templates available for use in calculations.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3280d-104">Opções</span><span class="sxs-lookup"><span data-stu-id="3280d-104">Options</span></span>  
 <span data-ttu-id="3280d-105">**Metadados**</span><span class="sxs-lookup"><span data-stu-id="3280d-105">**Metadata**</span></span>  
 <span data-ttu-id="3280d-106">Exibe os metadados do cubo selecionado.</span><span class="sxs-lookup"><span data-stu-id="3280d-106">Displays the metadata for the selected cube.</span></span>  
  
 <span data-ttu-id="3280d-107">Arraste um elemento selecionado para o painel Editor de Scripts, Editor de Formulário de Membro Calculado ou Editor de Formulário de Conjunto Nomeado para incluir a sintaxe MDX daquele elemento no local selecionado no painel.</span><span class="sxs-lookup"><span data-stu-id="3280d-107">Drag a selected element to the Script Editor, Calculated Member Form Editor, or Named Set Form Editor pane to include the Multidimensional Expressions (MDX) syntax for that element at the selected location in the pane.</span></span>  
  
 <span data-ttu-id="3280d-108">**Funções**</span><span class="sxs-lookup"><span data-stu-id="3280d-108">**Functions**</span></span>  
 <span data-ttu-id="3280d-109">Exibe as funções disponíveis para expressões e condições.</span><span class="sxs-lookup"><span data-stu-id="3280d-109">Displays the functions available for expressions and conditions.</span></span>  
  
 <span data-ttu-id="3280d-110">Arraste um elemento selecionado para o painel **Editor de Scripts**, **Editor de Formulário de Membro Calculado**ou **Editor de Formulário de Conjunto Nomeado** para incluir a sintaxe MDX daquele elemento no local selecionado no painel.</span><span class="sxs-lookup"><span data-stu-id="3280d-110">Drag a selected element to the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3280d-111">No modo de projeto, a caixa de diálogo **Ferramentas de Cálculo** lê as informações desta opção em um arquivo XML denominado MDXFunctions.xml fornecido com o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3280d-111">In project mode, the **Calculation Tools** dialog box reads information for this option from an XML file named MDXFunctions.xml, included with [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="3280d-112">Em modo online, informações para esta opção são recuperadas do conjunto de linhas de esquema de MDSCHEMA_FUNCTIONS da instância.</span><span class="sxs-lookup"><span data-stu-id="3280d-112">In online mode, information for this option is retrieved from the MDSCHEMA_FUNCTIONS schema rowset for the instance.</span></span>  
  
 <span data-ttu-id="3280d-113">**Modelos**</span><span class="sxs-lookup"><span data-stu-id="3280d-113">**Templates**</span></span>  
 <span data-ttu-id="3280d-114">Exibe os modelos predefinidos disponíveis para membros calculados, conjuntos nomeados e comandos de script.</span><span class="sxs-lookup"><span data-stu-id="3280d-114">Displays the predefined templates available for calculated members, named sets, and script commands.</span></span>  
  
 <span data-ttu-id="3280d-115">Arraste um elemento selecionado para o painel **Editor de Scripts**, **Editor de Formulário de Membro Calculado**ou **Editor de Formulário de Conjunto Nomeado** para incluir a sintaxe MDX daquele elemento no local selecionado no painel.</span><span class="sxs-lookup"><span data-stu-id="3280d-115">Drag a selected element to the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="3280d-116">Menu de contexto</span><span class="sxs-lookup"><span data-stu-id="3280d-116">Context Menu</span></span>  
 <span data-ttu-id="3280d-117">As seguintes opções estão disponíveis no menu de contexto exibido ao clicar com o botão direito do mouse em um elemento exibido no painel **Ferramentas de Cálculo** :</span><span class="sxs-lookup"><span data-stu-id="3280d-117">The following options are available in the context menu displayed by right-clicking an element in the **Calculation Tools** pane:</span></span>  
  
 <span data-ttu-id="3280d-118">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="3280d-118">**Copy**</span></span>  
 <span data-ttu-id="3280d-119">Selecione para copiar o elemento selecionado em **Metadados** ou **Funções** na Área de Transferência.</span><span class="sxs-lookup"><span data-stu-id="3280d-119">Select to copy the selected element in **Metadata** or **Functions** to the Clipboard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3280d-120"> Esta opção não será exibida se a opção **Modelos** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="3280d-120">This option is not displayed if **Templates** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3280d-121"> Esta opção será desabilitada se o membro selecionado não puder ser copiado, como a pasta **Conjuntos** de uma dimensão exibida em **Metadados** ou a pasta de grupo de funções de uma função exibida em **Funções**.</span><span class="sxs-lookup"><span data-stu-id="3280d-121">This option is disabled if the selected member cannot be copied, such as the **Sets** folder of a dimension displayed in **Metadata** or the function group folder for a function displayed in **Functions**.</span></span>  
  
 <span data-ttu-id="3280d-122">**Filtrar Membros**</span><span class="sxs-lookup"><span data-stu-id="3280d-122">**Filter Members**</span></span>  
 <span data-ttu-id="3280d-123">Clique para exibir a caixa de diálogo **Filtrar Membros** e filtrar os membros exibidos para o elemento selecionado em **Metadados**.</span><span class="sxs-lookup"><span data-stu-id="3280d-123">Select to display the **Filter Members** dialog box and filter members displayed for the selected element in **Metadata**.</span></span> <span data-ttu-id="3280d-124">Para obter mais informações sobre a caixa de diálogo **Filtrar Membros**, consulte [Caixa de diálogo Filtrar Membros &#40;Analysis Services – Dados Multidimensionais&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="3280d-124">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3280d-125"> Esta opção será exibida apenas se a opção **Metadados** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="3280d-125">This option is displayed only if **Metadata** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3280d-126"> Esta opção estará habilitada apenas se um nível de um atributo estiver selecionado em **Metadados**.</span><span class="sxs-lookup"><span data-stu-id="3280d-126">This option is enabled only if a level for an attribute is selected in **Metadata**.</span></span>  
  
 <span data-ttu-id="3280d-127">**Adicionar Modelo**</span><span class="sxs-lookup"><span data-stu-id="3280d-127">**Add Template**</span></span>  
 <span data-ttu-id="3280d-128">Selecione para adicionar um novo membro calculado, conjunto nomeado ou comando de script baseado no modelo selecionado para o script do cubo e exibir o **Editor de Scripts**, **Editor de Formulário de Membro Calculado**ou **Editor de Formulário de Conjunto Nomeado** conforme apropriado para o comando (na exibição do formulário) ou para rolar o conteúdo do painel **Editor de Scripts** para o local do comando no script do cubo (na exibição de script).</span><span class="sxs-lookup"><span data-stu-id="3280d-128">Select to add a new calculated member, named set, or script command based on the selected template to the cube script and display the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** as appropriate for that command (in form view) or to scroll the contents of the **Script Editor** pane to the location of the command in the cube script (in script view).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3280d-129"> Esta opção será exibida apenas se a opção **Metadados** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="3280d-129">This option is displayed only if **Metadata** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3280d-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3280d-130">See Also</span></span>  
 <span data-ttu-id="3280d-131">[O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3280d-131">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="3280d-132">[Barra de ferramentas &#40;guia cálculos, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3280d-132">[Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="3280d-133">[Guia cálculos do organizador de script &#40;, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3280d-133">[Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="3280d-134">[Editor de formulário de membro calculado &#40;guia cálculos, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3280d-134">[Calculated Member Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="3280d-135">[Editor de formulário de conjunto nomeado &#40;guia cálculos, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3280d-135">[Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="3280d-136">[Editor de script &#40;guia cálculos, designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3280d-136">[Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3280d-137">Cálculos &#40;designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="3280d-137">Calculations &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](calculations-cube-designer-analysis-services-multidimensional-data.md)  
  
  
