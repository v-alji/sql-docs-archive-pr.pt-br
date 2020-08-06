---
title: Caixa de diálogo visibilidade da linha | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.rowvisibility.f1
- "10126"
ms.assetid: 557ecf70-62b1-47f5-9322-0ebdc809d018
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 21977982cfe58a5b096b249b012a59aa9363f56c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571284"
---
# <a name="row-visibility-dialog-box"></a><span data-ttu-id="f482f-102">Caixa de diálogo Visibilidade da Linha</span><span class="sxs-lookup"><span data-stu-id="f482f-102">Row Visibility Dialog Box</span></span>
  <span data-ttu-id="f482f-103">Use a caixa de diálogo **Visibilidade da Linha** para mostrar ou ocultar a linha selecionada quando o relatório for executado pela primeira vez ou para usar outro item de relatório para alternar a visibilidade da linha.</span><span class="sxs-lookup"><span data-stu-id="f482f-103">Use the **Row Visibility** dialog box to show or hide the selected row when the report is first run or to use another report item to toggle the visibility of the row.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f482f-104">Opções</span><span class="sxs-lookup"><span data-stu-id="f482f-104">Options</span></span>  
 <span data-ttu-id="f482f-105">**Quando o relatório for executado inicialmente**</span><span class="sxs-lookup"><span data-stu-id="f482f-105">**When the report is initially run**</span></span>  
 <span data-ttu-id="f482f-106">Selecione uma opção para indicar como o item de relatório é exibido inicialmente no relatório.</span><span class="sxs-lookup"><span data-stu-id="f482f-106">Select an option to indicate how the report item is initially displayed in the report.</span></span>  
  
 <span data-ttu-id="f482f-107">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="f482f-107">**Show**</span></span>  
 <span data-ttu-id="f482f-108">Selecione esta opção para mostrar o item de relatório.</span><span class="sxs-lookup"><span data-stu-id="f482f-108">Select this option to show the report item.</span></span>  
  
 <span data-ttu-id="f482f-109">**Ocultar**</span><span class="sxs-lookup"><span data-stu-id="f482f-109">**Hide**</span></span>  
 <span data-ttu-id="f482f-110">Selecione esta opção para ocultar o item de relatório.</span><span class="sxs-lookup"><span data-stu-id="f482f-110">Select this option to hide the report item.</span></span>  
  
 <span data-ttu-id="f482f-111">**Mostrar ou ocultar com base em uma expressão**</span><span class="sxs-lookup"><span data-stu-id="f482f-111">**Show or hide based on an expression**</span></span>  
 <span data-ttu-id="f482f-112">Escolha esta opção para variar a visibilidade inicial usando uma expressão.</span><span class="sxs-lookup"><span data-stu-id="f482f-112">Select this option to vary the initial visibility using an expression.</span></span>  
  
 <span data-ttu-id="f482f-113">Digite uma expressão que seja avaliada como um valor `Boolean``True` para ocultar o item e `False` para mostrar o item.</span><span class="sxs-lookup"><span data-stu-id="f482f-113">Type an expression that evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span> <span data-ttu-id="f482f-114">Clique no botão expressão (**FX**) para editar a expressão.</span><span class="sxs-lookup"><span data-stu-id="f482f-114">Click the Expression (**fx**) button to edit the expression.</span></span>  
  
 <span data-ttu-id="f482f-115">**A exibição pode ser alternada por este item de relatório**</span><span class="sxs-lookup"><span data-stu-id="f482f-115">**Display can be toggled by this report item**</span></span>  
 <span data-ttu-id="f482f-116">Escolha esta opção para exibir uma imagem de alternância que permite que o usuário mostre ou oculte este item de relatório em um visualizador de relatórios HTML.</span><span class="sxs-lookup"><span data-stu-id="f482f-116">Choose this option to display a toggle image that enables the user to show or hide this report item in an HTML report viewer.</span></span>  
  
 <span data-ttu-id="f482f-117">Digite ou selecione o nome de uma caixa de texto no relatório no qual exibir a imagem de alternância, por exemplo, Textbox1.</span><span class="sxs-lookup"><span data-stu-id="f482f-117">Type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span> <span data-ttu-id="f482f-118">A caixa de texto escolhida deve estar no escopo atual ou no escopo de contenção desse item de relatório.</span><span class="sxs-lookup"><span data-stu-id="f482f-118">The text box that you choose must be in the current or containing scope for this report item.</span></span> <span data-ttu-id="f482f-119">Por exemplo, para alternar a visibilidade de linhas associadas a um grupo filho, selecione uma caixa de texto em uma linha associada ao grupo pai.</span><span class="sxs-lookup"><span data-stu-id="f482f-119">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span> <span data-ttu-id="f482f-120">Para alternar a visibilidade de um gráfico, selecione uma caixa de texto que esteja no mesmo escopo de contenção que o gráfico. Por exemplo, o corpo do relatório ou um retângulo.</span><span class="sxs-lookup"><span data-stu-id="f482f-120">To toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f482f-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f482f-121">See Also</span></span>  
 <span data-ttu-id="f482f-122">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f482f-122">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f482f-123">[Adicionar uma ação de expandir ou recolher a um item &#40;Construtor de Relatórios e SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f482f-123">[Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f482f-124">[Imagens &#40;Construtor de Relatórios e SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f482f-124">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f482f-125">Ajuda F1 do Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="f482f-125">Report Designer F1 Help</span></span>](tools/report-designer-f1-help.md)  
  
  
