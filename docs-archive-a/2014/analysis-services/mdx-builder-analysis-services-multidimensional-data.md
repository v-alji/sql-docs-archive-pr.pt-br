---
title: Construtor MDX (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.mdxbuilderdialof.f1
helpviewer_keywords:
- MDX Builder dialog box
ms.assetid: fecbf093-65ea-4e1b-b637-f04876f1cb0f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 391f4abe953184470be60cca41d53ee20e965423
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574946"
---
# <a name="mdx-builder-analysis-services---multidimensional-data"></a><span data-ttu-id="4b888-102">Construtor MDX (Analysis Services – Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="4b888-102">MDX Builder (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="4b888-103">Use a caixa de diálogo **Construtor MDX** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ou no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para criar uma expressão em linguagem MDX.</span><span class="sxs-lookup"><span data-stu-id="4b888-103">Use the **MDX Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to build a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="4b888-104">Você pode exibir a caixa de diálogo **Construtor MDX** clicando no botão Editar reticências **MDX** (**...**) para a opção **permitir leitura de conteúdo de cubo** , a opção **permitir leitura de conteúdo de célula contingente na segurança** da célula ou a opção **permitir leitura e gravação do conteúdo do cubo** na página **dados da célula** do **Designer de função**.</span><span class="sxs-lookup"><span data-stu-id="4b888-104">You can display the **MDX Builder** dialog box by clicking the **Edit MDX** ellipsis button (**...**) for the **Allow reading of cube content** option, the **Allow reading of cell content contingent on cell security** option, or the **Allow reading and writing of cube content** option on the **Cell Data** page of **Role Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4b888-105">Opções</span><span class="sxs-lookup"><span data-stu-id="4b888-105">Options</span></span>  
  
|<span data-ttu-id="4b888-106">Termo</span><span class="sxs-lookup"><span data-stu-id="4b888-106">Term</span></span>|<span data-ttu-id="4b888-107">Definição</span><span class="sxs-lookup"><span data-stu-id="4b888-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="4b888-108">**Expression**</span><span class="sxs-lookup"><span data-stu-id="4b888-108">**Expression**</span></span>|<span data-ttu-id="4b888-109">Digite a expressão MDX a ser usada.</span><span class="sxs-lookup"><span data-stu-id="4b888-109">Type the MDX expression to be used.</span></span>|  
|<span data-ttu-id="4b888-110">**Verificação**</span><span class="sxs-lookup"><span data-stu-id="4b888-110">**Check**</span></span>|<span data-ttu-id="4b888-111">Clique em **Verificar** para testar a expressão MDX definida em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="4b888-111">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="4b888-112">**Metadados**</span><span class="sxs-lookup"><span data-stu-id="4b888-112">**Metadata**</span></span>|<span data-ttu-id="4b888-113">Exibe metadados para o objeto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] atual que pode ser incluído na expressão MDX definida em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="4b888-113">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="4b888-114">É possível copiar a sintaxe MDX do item selecionado clicando com o botão direito do mouse no item e selecionando **Copiar** no menu de contexto ou arrastando o item selecionado para **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="4b888-114">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="4b888-115">**Funções**</span><span class="sxs-lookup"><span data-stu-id="4b888-115">**Functions**</span></span>|<span data-ttu-id="4b888-116">Exibe funções MDX disponíveis para a instância atual do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b888-116">Displays available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="4b888-117">Os itens listados são recuperados do conjunto de linhas do esquema MDSCHEMA_FUNCTIONS.</span><span class="sxs-lookup"><span data-stu-id="4b888-117">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="4b888-118">É possível copiar a sintaxe MDX do item selecionado clicando com o botão direito do mouse no item e selecionando **Copiar** no menu de contexto ou arrastando o item selecionado para **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="4b888-118">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b888-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4b888-119">See Also</span></span>  
 <span data-ttu-id="4b888-120">[Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="4b888-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 <span data-ttu-id="4b888-121">[Dados de célula &#40;designer de função&#41; &#40;Analysis Services de dados multidimensionais&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="4b888-121">[Cell Data &#40;Role Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span></span>  
  
  
