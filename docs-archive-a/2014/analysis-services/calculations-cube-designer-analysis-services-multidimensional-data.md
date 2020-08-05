---
title: Cálculos (Designer de cubo) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationsview.f1
ms.assetid: 46e2fbe2-bb41-4eaa-91f8-eb2bd3b8d00d
author: minewiskan
ms.author: owend
ms.openlocfilehash: fdbc35a8e47557923b90cda4e72280c3cca940dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571713"
---
# <a name="calculations-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="2f1dc-102">Cálculos (Designer de Cubo) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="2f1dc-102">Calculations (Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="2f1dc-103">Use a guia **Cálculos** no Designer de Cubo para exibir e editar cálculos, incluindo membros calculados, conjuntos nomeados e comandos de script MDX para o cubo selecionado.</span><span class="sxs-lookup"><span data-stu-id="2f1dc-103">Use the **Calculations** tab in Cube Designer to view and edit calculations, including calculated members, named sets, and Multidimensional Expressions (MDX) script commands for the selected cube.</span></span>  
  
## <a name="form-view-and-script-view"></a><span data-ttu-id="2f1dc-104">Exibição de Formulário e Exibição de Script</span><span class="sxs-lookup"><span data-stu-id="2f1dc-104">Form View and Script View</span></span>  
 <span data-ttu-id="2f1dc-105">A guia **Cálculos** oferece suporte a duas exibições diferentes ao exibir ou editar cálculos:</span><span class="sxs-lookup"><span data-stu-id="2f1dc-105">The **Calculations** tab supports two different views when viewing or editing calculations:</span></span>  
  
-   <span data-ttu-id="2f1dc-106">Exibição de formulário</span><span class="sxs-lookup"><span data-stu-id="2f1dc-106">Form view</span></span>  
  
     <span data-ttu-id="2f1dc-107">Esta exibição exibe uma exibição organizada dos membros calculados, conjuntos nomeados e comandos de script contidos no script MDX associado ao cubo e fornece editores de formulários para exibir e editar membros calculados e conjuntos nomeados, bem como exibir os metadados, funções e ferramentas disponíveis para o cubo.</span><span class="sxs-lookup"><span data-stu-id="2f1dc-107">This view displays an organized view of the calculated members, named sets, and script commands contained in the MDX script associated with the cube and provides form editors to view and edit calculated members and named sets, as well as displaying the metadata, functions, and tools available to the cube.</span></span>  
  
-   <span data-ttu-id="2f1dc-108">Exibição de script</span><span class="sxs-lookup"><span data-stu-id="2f1dc-108">Script view</span></span>  
  
     <span data-ttu-id="2f1dc-109">Para usuários avançados, esta exibição exibe todo o script MDX associado ao cubo, bem como os metadados, funções e ferramentas disponíveis para o cubo.</span><span class="sxs-lookup"><span data-stu-id="2f1dc-109">For advanced users, this view displays the entire MDX script associated with the cube, as well as displaying the metadata, functions, and tools available to the cube.</span></span>  
  
## <a name="panes"></a><span data-ttu-id="2f1dc-110">Painéis</span><span class="sxs-lookup"><span data-stu-id="2f1dc-110">Panes</span></span>  
 <span data-ttu-id="2f1dc-111">**Barra de ferramentas**</span><span class="sxs-lookup"><span data-stu-id="2f1dc-111">**Toolbar**</span></span>  
 <span data-ttu-id="2f1dc-112">Use a barra de ferramentas na exibição de formulário e no modo de exibição de script para executar operações comuns nessa guia. Para obter mais informações sobre esse painel, consulte a [barra de ferramentas &#40;guia cálculos, designer de cubo&#41; &#40;Analysis Services-&#41;de dados multidimensionais ](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="2f1dc-112">Use the toolbar in both form view and script view to perform common operations on this tab. For more information about this pane, see [Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="2f1dc-113">**Organizador de Script**</span><span class="sxs-lookup"><span data-stu-id="2f1dc-113">**Script Organizer**</span></span>  
 <span data-ttu-id="2f1dc-114">Use o painel **Organizador de Script** na exibição de formulário para exibir o conteúdo do script do cubo em um formato ordenado.</span><span class="sxs-lookup"><span data-stu-id="2f1dc-114">Use the **Script Organizer** pane in form view to display the contents of the cube script in an ordered format.</span></span> <span data-ttu-id="2f1dc-115">Para obter mais informações sobre esse painel, consulte [Organizador de Script &#40;guia Cálculos, Designer de Cubo&#41; &#40;Analysis Services – Dados Multidimensionais&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="2f1dc-115">For more information about this pane, see [Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="2f1dc-116">**Ferramentas de Cálculo**</span><span class="sxs-lookup"><span data-stu-id="2f1dc-116">**Calculation Tools**</span></span>  
 <span data-ttu-id="2f1dc-117">Use o painel **Ferramentas de Cálculo** na exibição de formulário e na exibição de script para exibir os metadados, as funções e as ferramentas disponíveis para o cubo.</span><span class="sxs-lookup"><span data-stu-id="2f1dc-117">Use the **Calculation Tools** pane in both form view and script view to display metadata, functions, and tools available to the cube.</span></span> <span data-ttu-id="2f1dc-118">Para obter mais informações sobre esse painel, consulte [Ferramentas de Cálculo &#40;guia Cálculos, Designer de Cubo&#41; &#40;Analysis Services – Dados Multidimensionais&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="2f1dc-118">For more information about this pane, see [Calculation Tools &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="2f1dc-119">**Editor de Scripts**</span><span class="sxs-lookup"><span data-stu-id="2f1dc-119">**Script Editor**</span></span>  
 <span data-ttu-id="2f1dc-120">Use o painel **Editor de Scripts** na exibição de script para editar todo o cubo de script e na exibição de formulário para editar comandos de script contidos no script de cubo.</span><span class="sxs-lookup"><span data-stu-id="2f1dc-120">Use the **Script Editor** pane in script view to edit the entire cube script and in form view to edit script commands contained in the cube script.</span></span> <span data-ttu-id="2f1dc-121">Para obter mais informações sobre esse painel, consulte [Editor de Scripts &#40;guia Cálculos, Designer de Cubo&#41; &#40;Analysis Services – Dados Multidimensionais&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="2f1dc-121">For more information about this pane, see [Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="2f1dc-122">**Editor de Formulário de Membro Calculado**</span><span class="sxs-lookup"><span data-stu-id="2f1dc-122">**Calculated Member Form Editor**</span></span>  
 <span data-ttu-id="2f1dc-123">Use o painel **Editor de Formulário de Membro Calculado** na exibição de formulário para editar membros calculados no script de cubo.</span><span class="sxs-lookup"><span data-stu-id="2f1dc-123">Use the **Calculated Member Form Editor** pane in form view to edit calculated members in the cube script.</span></span> <span data-ttu-id="2f1dc-124">Para obter mais informações sobre esse painel, consulte [Editor de Formulário de Membro Calculado &#40;guia Cálculos, Designer de Cubo&#41; &#40;Analysis Services – Dados Multidimensionais&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="2f1dc-124">For more information about this pane, see [Calculated Member Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="2f1dc-125">**Editor de Formulário de Conjunto Nomeado**</span><span class="sxs-lookup"><span data-stu-id="2f1dc-125">**Named Set Form Editor**</span></span>  
 <span data-ttu-id="2f1dc-126">Use o painel **Editor de Formulário de Conjunto Nomeado** na exibição de formulário para editar conjuntos nomeados no script de cubo.</span><span class="sxs-lookup"><span data-stu-id="2f1dc-126">Use the **Named Set Form Editor** pane in form view to edit named sets in the cube script.</span></span> <span data-ttu-id="2f1dc-127">Para obter mais informações sobre esse painel, consulte [Editor de Formulário de Conjunto Nomeado &#40;guia Cálculo, Designer de Cubo&#41; &#40;Analysis Services – Dados Multidimensionais&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="2f1dc-127">For more information about this pane, see [Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f1dc-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f1dc-128">See Also</span></span>  
 <span data-ttu-id="2f1dc-129">[Objetos de cubo &#40;Analysis Services de dados multidimensionais&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2f1dc-129">[Cube Objects &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="2f1dc-130">[Cálculos](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="2f1dc-130">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="2f1dc-131">[Conceitos básicos de script MDX &#40;Analysis Services&#41;](multidimensional-models/mdx/mdx-scripting-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="2f1dc-131">[MDX Scripting Fundamentals &#40;Analysis Services&#41;](multidimensional-models/mdx/mdx-scripting-fundamentals-analysis-services.md) </span></span>  
 <span data-ttu-id="2f1dc-132">[O designer de cubo &#40;Analysis Services-dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2f1dc-132">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="2f1dc-133">Criar conjuntos nomeados</span><span class="sxs-lookup"><span data-stu-id="2f1dc-133">Create Named Sets</span></span>](multidimensional-models/create-named-sets.md)  
  
  
