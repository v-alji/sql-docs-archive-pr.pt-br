---
title: Caixa de diálogo visibilidade da coluna (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10127"
ms.assetid: 0c030cab-6087-45a5-99f0-c7bd693f20a1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4c775734a4dbba2120a2af86e35a3872f5fff718
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679727"
---
# <a name="column-visibility-dialog-box-report-builder"></a><span data-ttu-id="97a0a-102">Caixa de diálogo Visibilidade da Coluna (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="97a0a-102">Column Visibility Dialog Box (Report Builder)</span></span>
  <span data-ttu-id="97a0a-103">Use a caixa de diálogo **Visibilidade da Coluna** para mostrar ou ocultar a coluna selecionada quando o relatório for executado pela primeira vez ou para usar outro item de relatório para alternar a visibilidade da coluna.</span><span class="sxs-lookup"><span data-stu-id="97a0a-103">Use the **Column Visibility** dialog box to show or hide the selected column when the report is first run or to use another report item to toggle the visibility of the column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="97a0a-104">Opções</span><span class="sxs-lookup"><span data-stu-id="97a0a-104">Options</span></span>  
 <span data-ttu-id="97a0a-105">**Quando o relatório for executado inicialmente**</span><span class="sxs-lookup"><span data-stu-id="97a0a-105">**When the report is initially run**</span></span>  
 <span data-ttu-id="97a0a-106">Selecione uma opção para indicar como o item de relatório é exibido inicialmente no relatório.</span><span class="sxs-lookup"><span data-stu-id="97a0a-106">Select an option to indicate how the report item is initially displayed in the report.</span></span>  
  
 <span data-ttu-id="97a0a-107">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="97a0a-107">**Show**</span></span>  
 <span data-ttu-id="97a0a-108">Escolha esta opção para mostrar a coluna.</span><span class="sxs-lookup"><span data-stu-id="97a0a-108">Choose this option to show the column.</span></span>  
  
 <span data-ttu-id="97a0a-109">**Ocultar**</span><span class="sxs-lookup"><span data-stu-id="97a0a-109">**Hide**</span></span>  
 <span data-ttu-id="97a0a-110">Escolha esta opção para ocultar a Coluna.</span><span class="sxs-lookup"><span data-stu-id="97a0a-110">Choose this option to hide the Column.</span></span>  
  
 <span data-ttu-id="97a0a-111">**Mostrar ou ocultar com base em uma expressão**</span><span class="sxs-lookup"><span data-stu-id="97a0a-111">**Show or hide based on an expression**</span></span>  
 <span data-ttu-id="97a0a-112">Escolha esta opção para variar a visibilidade inicial usando uma expressão.</span><span class="sxs-lookup"><span data-stu-id="97a0a-112">Choose this option to vary the initial visibility using an expression.</span></span>  
  
 <span data-ttu-id="97a0a-113">Digite uma expressão que seja avaliada como um valor `Boolean``True` para ocultar o item e `False` para mostrar o item.</span><span class="sxs-lookup"><span data-stu-id="97a0a-113">Type an expression that evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span> <span data-ttu-id="97a0a-114">Clique no botão expressão (*FX*) para editar a expressão.</span><span class="sxs-lookup"><span data-stu-id="97a0a-114">Click the Expression (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="97a0a-115">**A exibição pode ser alternada por este item de relatório**</span><span class="sxs-lookup"><span data-stu-id="97a0a-115">**Display can be toggled by this report item**</span></span>  
 <span data-ttu-id="97a0a-116">Escolha esta opção para exibir uma imagem de alternância que permite que o usuário mostre ou oculte essa coluna em um visualizador de relatórios HTML.</span><span class="sxs-lookup"><span data-stu-id="97a0a-116">Choose this option to display a toggle image that enables the user to show or hide this column in an HTML report viewer.</span></span>  
  
 <span data-ttu-id="97a0a-117">Digite ou selecione o nome de uma caixa de texto no relatório no qual exibir a imagem de alternância, por exemplo, Textbox1.</span><span class="sxs-lookup"><span data-stu-id="97a0a-117">Type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span> <span data-ttu-id="97a0a-118">A caixa de texto escolhida deve estar no escopo atual ou no escopo de contenção desse item de relatório.</span><span class="sxs-lookup"><span data-stu-id="97a0a-118">The text box that you choose must be in the current or containing scope for this report item.</span></span> <span data-ttu-id="97a0a-119">Por exemplo, para alternar a visibilidade de linhas associadas a um grupo filho, selecione uma caixa de texto em uma linha associada ao grupo pai.</span><span class="sxs-lookup"><span data-stu-id="97a0a-119">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span> <span data-ttu-id="97a0a-120">Para alternar a visibilidade de um gráfico, selecione uma caixa de texto que esteja no mesmo escopo de contenção que o gráfico. Por exemplo, o corpo do relatório ou um retângulo.</span><span class="sxs-lookup"><span data-stu-id="97a0a-120">To toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a0a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="97a0a-121">See Also</span></span>  
 <span data-ttu-id="97a0a-122">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="97a0a-122">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="97a0a-123">[Adicionar uma ação de expandir ou recolher a um item &#40;Construtor de Relatórios e SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="97a0a-123">[Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="97a0a-124">[Imagens &#40;Construtor de Relatórios e SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="97a0a-124">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="97a0a-125">[Construtor de Relatórios ajuda para caixas de diálogo, painéis e assistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="97a0a-125">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="97a0a-126">Caixa de diálogo Propriedades da Imagem, Geral &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="97a0a-126">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
