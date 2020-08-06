---
title: Detalhes da tradução (guia Traduções, designer de dimensão) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.translations.translationpane.tranlationdetails.f1
ms.assetid: 0aa61df3-f2b0-4703-a63b-124da672dcc3
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7cbe4a3c69111d0f82f96ff5125f80fe0c2c57f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684343"
---
# <a name="translation-details-translations-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="c3f69-102">Detalhes de conversão (guia Conversões, Designer de Dimensão) (Analysis Services - Dados multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="c3f69-102">Translation Details (Translations Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="c3f69-103">Use o painel **Detalhes da conversão** na guia **Conversões** do Designer de Dimensão para definir e gerenciar conversões da dimensão atualmente selecionada.</span><span class="sxs-lookup"><span data-stu-id="c3f69-103">Use the **Translation Details** pane on the **Translations** tab of Dimension Designer to define and manage translations for the currently selected dimension.</span></span>  
  
 <span data-ttu-id="c3f69-104">**Para exibir o painel Detalhes da conversão**</span><span class="sxs-lookup"><span data-stu-id="c3f69-104">**To display the Translations Details pane**</span></span>  
  
1.  <span data-ttu-id="c3f69-105">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e então abra a dimensão desejada.</span><span class="sxs-lookup"><span data-stu-id="c3f69-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then open the dimension that you want.</span></span>  
  
2.  <span data-ttu-id="c3f69-106">Clique na guia **Conversões** .</span><span class="sxs-lookup"><span data-stu-id="c3f69-106">Click the **Translations** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c3f69-107">Opções</span><span class="sxs-lookup"><span data-stu-id="c3f69-107">Options</span></span>  
 <span data-ttu-id="c3f69-108">**Idioma Padrão**</span><span class="sxs-lookup"><span data-stu-id="c3f69-108">**Default Language**</span></span>  
 <span data-ttu-id="c3f69-109">Define os nomes dos objetos de dimensão no idioma padrão.</span><span class="sxs-lookup"><span data-stu-id="c3f69-109">Sets the names of the dimension objects in the default language.</span></span>  
  
 <span data-ttu-id="c3f69-110">**Tipo de Objeto**</span><span class="sxs-lookup"><span data-stu-id="c3f69-110">**Object Type**</span></span>  
 <span data-ttu-id="c3f69-111">Exibe a propriedade que será traduzida.</span><span class="sxs-lookup"><span data-stu-id="c3f69-111">Displays the property that will be translated.</span></span> <span data-ttu-id="c3f69-112">Só podem ser convertidos objetos e propriedades para os quais foram especificados valores.</span><span class="sxs-lookup"><span data-stu-id="c3f69-112">Only objects and properties for which values have been specified can be translated.</span></span> <span data-ttu-id="c3f69-113">As seguintes propriedades podem ser traduzidas:</span><span class="sxs-lookup"><span data-stu-id="c3f69-113">The following properties can be translated:</span></span>  
  
-   <span data-ttu-id="c3f69-114">Dimensão</span><span class="sxs-lookup"><span data-stu-id="c3f69-114">Dimension</span></span>  
  
     <span data-ttu-id="c3f69-115">Propriedades `Caption` e `AttributeAllMember`</span><span class="sxs-lookup"><span data-stu-id="c3f69-115">`Caption` and `AttributeAllMember` properties</span></span>  
  
-   <span data-ttu-id="c3f69-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="c3f69-116">Attribute</span></span>  
  
     <span data-ttu-id="c3f69-117">Propriedades `Caption`, `AttributeHierarchyDisplayFolder` e `NamingTemplate`</span><span class="sxs-lookup"><span data-stu-id="c3f69-117">`Caption`, `AttributeHierarchyDisplayFolder`, and `NamingTemplate` properties</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c3f69-118">A propriedade `NamingTemplate` só está disponível para atributos pai.</span><span class="sxs-lookup"><span data-stu-id="c3f69-118">The `NamingTemplate` property is available only for parent attributes.</span></span>  
  
-   <span data-ttu-id="c3f69-119">Hierarquia</span><span class="sxs-lookup"><span data-stu-id="c3f69-119">Hierarchy</span></span>  
  
     <span data-ttu-id="c3f69-120">Propriedades `Caption` e `AllMemberName`</span><span class="sxs-lookup"><span data-stu-id="c3f69-120">`Caption` and `AllMemberName` properties</span></span>  
  
-   <span data-ttu-id="c3f69-121">Nível</span><span class="sxs-lookup"><span data-stu-id="c3f69-121">Level</span></span>  
  
     <span data-ttu-id="c3f69-122">Propriedade `Caption`</span><span class="sxs-lookup"><span data-stu-id="c3f69-122">`Caption` property</span></span>  
  
 **\<Language>**  
 <span data-ttu-id="c3f69-123">Digite ou selecione o valor de propriedade do objeto de dimensão na linguagem selecionada.</span><span class="sxs-lookup"><span data-stu-id="c3f69-123">Type or select the property value of the dimension object in the selected language.</span></span> <span data-ttu-id="c3f69-124">Clicar no botão de reticências (**...**) abre caixas de diálogo adicionais, dependendo da propriedade que está sendo editada:</span><span class="sxs-lookup"><span data-stu-id="c3f69-124">Clicking the ellipsis button (**...**) opens additional dialog boxes, depending on the property being edited:</span></span>  
  
-   <span data-ttu-id="c3f69-125">Propriedade `NamingTemplate`</span><span class="sxs-lookup"><span data-stu-id="c3f69-125">`NamingTemplate` property</span></span>  
  
     <span data-ttu-id="c3f69-126">Exibe a [Caixa de diálogo Modelo de Nomeação de Nível &#40;Analysis Services - Dados Multidimensionais&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="c3f69-126">Displays the [Level Naming Template Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
-   <span data-ttu-id="c3f69-127">Propriedade `Caption` (para atributos)</span><span class="sxs-lookup"><span data-stu-id="c3f69-127">`Caption` property (for attributes)</span></span>  
  
     <span data-ttu-id="c3f69-128">Exibe a [Caixa de diálogo Tradução de Dados de Atributo &#40;Analysis Services - Dados Multidimensionais&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="c3f69-128">Displays the [Attribute Data Translation Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="shortcut-menu"></a><span data-ttu-id="c3f69-129">Menu de atalho</span><span class="sxs-lookup"><span data-stu-id="c3f69-129">Shortcut Menu</span></span>  
 <span data-ttu-id="c3f69-130">As opções seguintes estão disponíveis no menu de atalho exibido ao clicar com o botão direito do mouse em uma conversão no painel **Detalhes de Conversão** :</span><span class="sxs-lookup"><span data-stu-id="c3f69-130">The following options are available in the shortcut menu displayed by right-clicking a translation in the **Translation Details** pane:</span></span>  
  
 <span data-ttu-id="c3f69-131">**Nova Tradução**</span><span class="sxs-lookup"><span data-stu-id="c3f69-131">**New Translation**</span></span>  
 <span data-ttu-id="c3f69-132">Selecione para exibir a caixa de diálogo **Selecionar Idioma** e criar uma nova tradução.</span><span class="sxs-lookup"><span data-stu-id="c3f69-132">Select to display the **Select Language** dialog box and create a new translation.</span></span> <span data-ttu-id="c3f69-133">A conversão aparecerá como uma coluna nova na grade **Detalhes de Conversão** .</span><span class="sxs-lookup"><span data-stu-id="c3f69-133">The translation will appear as a new column in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="c3f69-134">**Excluir Tradução**</span><span class="sxs-lookup"><span data-stu-id="c3f69-134">**Delete Translation**</span></span>  
 <span data-ttu-id="c3f69-135">Selecione para excluir a tradução selecionada.</span><span class="sxs-lookup"><span data-stu-id="c3f69-135">Select to delete the selected translation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3f69-136">A opção só está habilitada se você clicou com o botão direito do mouse em uma célula para excluir a conversão.</span><span class="sxs-lookup"><span data-stu-id="c3f69-136">The option is enabled only if you right-clicked a cell to delete the translation.</span></span>  
  
 <span data-ttu-id="c3f69-137">**Nova Coluna de Legendas**</span><span class="sxs-lookup"><span data-stu-id="c3f69-137">**New Caption Column**</span></span>  
 <span data-ttu-id="c3f69-138">Selecione para exibir a caixa de diálogo **Conversão de Dados de Atributo** e definir uma nova coluna de legendas quando você modificar um atributo na grade **Detalhes de Conversão** .</span><span class="sxs-lookup"><span data-stu-id="c3f69-138">Select to display the **Attribute Data Translation** dialog box and define a new caption column when you modify an attribute in the **Translation Details** grid.</span></span> <span data-ttu-id="c3f69-139">Para habilitar esta opção, é preciso selecionar uma célula na coluna de conversão de um atributo na grade **Detalhes de Conversão** .</span><span class="sxs-lookup"><span data-stu-id="c3f69-139">To enable this option, a cell in a translation column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3f69-140">A opção só está habilitada se você clicou com o botão direito do mouse em uma célula para excluir a coluna de conversão de um atributo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-140">The option is enabled only if you right-clicked a cell to delete the translation column of an attribute.</span></span>  
  
 <span data-ttu-id="c3f69-141">**Editar Coluna de Legendas**</span><span class="sxs-lookup"><span data-stu-id="c3f69-141">**Edit Caption Column**</span></span>  
 <span data-ttu-id="c3f69-142">Selecione para exibir a caixa de diálogo **Conversão de Dados de Atributo** e modificar uma coluna de legendas existente quando você modificar um atributo na grade **Detalhes de Conversão** .</span><span class="sxs-lookup"><span data-stu-id="c3f69-142">Select to display the **Attribute Data Translation** dialog box and modify an existing caption column when you modify an attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3f69-143"> A opção só é habilitada se uma célula em uma coluna de conversão que contém a coluna de legendas de um atributo tiver que ser selecionada na grade **Detalhes de Conversão** .</span><span class="sxs-lookup"><span data-stu-id="c3f69-143">The option is enabled only if a cell in a translation column that contains a caption column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="c3f69-144">**Excluir Coluna de Legendas**</span><span class="sxs-lookup"><span data-stu-id="c3f69-144">**Delete Caption Column**</span></span>  
 <span data-ttu-id="c3f69-145">Selecione para excluir a coluna de legendas para o atributo selecionado na grade **Detalhes de Conversão** .</span><span class="sxs-lookup"><span data-stu-id="c3f69-145">Select to delete the caption column for the selected attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3f69-146">A opção só está habilitada se você clicou com o botão direito em uma célula em uma coluna de conversão que contém uma coluna de legendas para um atributo.</span><span class="sxs-lookup"><span data-stu-id="c3f69-146">The option is enabled only if you right-clicked a cell in a translation column that contains a caption column for an attribute.</span></span>  
  
 <span data-ttu-id="c3f69-147">**Mostrar Todos os Atributos**</span><span class="sxs-lookup"><span data-stu-id="c3f69-147">**Show All Attributes**</span></span>  
 <span data-ttu-id="c3f69-148">Selecione para alternar a exibição de todos os atributos definidos para a dimensão selecionada, inclusive atributos para os quais as hierarquias de atributo estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="c3f69-148">Select to toggle the display of all attributes defined for the selected dimension, including attributes for which attribute hierarchies are disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3f69-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3f69-149">See Also</span></span>  
 [<span data-ttu-id="c3f69-150">Traduções &#40;o designer de dimensão&#41; &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="c3f69-150">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
