---
title: Caixa de diálogo Construtor de membros calculados (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.calculatedmemberbuilderdialog.f1
ms.assetid: 73b89a9f-f403-4ab8-99f7-e3ceb870c260
author: minewiskan
ms.author: owend
ms.openlocfilehash: 240e2f2471bf77c403119fd51278a975badc8358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571097"
---
# <a name="calculated-member-builder-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="2bb63-102">Caixa de diálogo Construtor de Membro Calculado (Analysis Services - Dados multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="2bb63-102">Calculated Member Builder Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="2bb63-103">Use a caixa de diálogo **Construtor de Membro Calculado** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para criar um membro calculado.</span><span class="sxs-lookup"><span data-stu-id="2bb63-103">Use the **Calculated Member Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to build a calculated member.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2bb63-104">Opções</span><span class="sxs-lookup"><span data-stu-id="2bb63-104">Options</span></span>  
  
|<span data-ttu-id="2bb63-105">Termo</span><span class="sxs-lookup"><span data-stu-id="2bb63-105">Term</span></span>|<span data-ttu-id="2bb63-106">Definição</span><span class="sxs-lookup"><span data-stu-id="2bb63-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="2bb63-107">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2bb63-107">**Name**</span></span>|<span data-ttu-id="2bb63-108">Digite o nome do membro calculado.</span><span class="sxs-lookup"><span data-stu-id="2bb63-108">Type the name of the calculated member.</span></span>|  
|<span data-ttu-id="2bb63-109">**Hierarquia pai**</span><span class="sxs-lookup"><span data-stu-id="2bb63-109">**Parent Hierarchy**</span></span>|<span data-ttu-id="2bb63-110">Selecione a hierarquia na qual o membro calculado será criado.</span><span class="sxs-lookup"><span data-stu-id="2bb63-110">Select the hierarchy in which to create the calculated member.</span></span>|  
|<span data-ttu-id="2bb63-111">**Membro pai**</span><span class="sxs-lookup"><span data-stu-id="2bb63-111">**Parent Member**</span></span>|<span data-ttu-id="2bb63-112">Essa opção estará habilitada se você selecionar uma hierarquia pai (diferente da dimensão `Measures`) que tem mais de um nível.</span><span class="sxs-lookup"><span data-stu-id="2bb63-112">This option is enabled if you select a parent hierarchy (other than the `Measures` dimension) that has more than one level.</span></span> <span data-ttu-id="2bb63-113">Clique no botão de reticências (**...**) para selecionar um membro pai.</span><span class="sxs-lookup"><span data-stu-id="2bb63-113">Click the ellipsis (**...**) button to select a parent member.</span></span> <span data-ttu-id="2bb63-114">O membro pai determina o local do membro calculado na estrutura de dimensão.</span><span class="sxs-lookup"><span data-stu-id="2bb63-114">The parent member determines the location of the calculated member in the dimension structure.</span></span>|  
|<span data-ttu-id="2bb63-115">**Expression**</span><span class="sxs-lookup"><span data-stu-id="2bb63-115">**Expression**</span></span>|<span data-ttu-id="2bb63-116">Digite a expressão MDX que será usada.</span><span class="sxs-lookup"><span data-stu-id="2bb63-116">Type the MDX expression that will be used.</span></span>|  
|<span data-ttu-id="2bb63-117">**Verificação**</span><span class="sxs-lookup"><span data-stu-id="2bb63-117">**Check**</span></span>|<span data-ttu-id="2bb63-118">Clique em **Verificar** para testar a expressão MDX definida em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="2bb63-118">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="2bb63-119">**Metadados**</span><span class="sxs-lookup"><span data-stu-id="2bb63-119">**Metadata**</span></span>|<span data-ttu-id="2bb63-120">Exibe metadados para o objeto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] atual que pode ser incluído na expressão MDX definida em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="2bb63-120">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="2bb63-121">É possível copiar a sintaxe MDX do item selecionado clicando com o botão direito do mouse no item e selecionando **Copiar**ou arrastando o item selecionado para **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="2bb63-121">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="2bb63-122">**Funções**</span><span class="sxs-lookup"><span data-stu-id="2bb63-122">**Functions**</span></span>|<span data-ttu-id="2bb63-123">Exibe as funções MDX disponíveis para a instância atual do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2bb63-123">Displays the available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="2bb63-124">Os itens listados são recuperados do conjunto de linhas do esquema MDSCHEMA_FUNCTIONS.</span><span class="sxs-lookup"><span data-stu-id="2bb63-124">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="2bb63-125">É possível copiar a sintaxe MDX do item selecionado clicando com o botão direito do mouse no item e selecionando **Copiar**ou arrastando o item selecionado para **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="2bb63-125">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2bb63-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2bb63-126">See Also</span></span>  
 [<span data-ttu-id="2bb63-127">Referência de expressões multidimensionais &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="2bb63-127">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
