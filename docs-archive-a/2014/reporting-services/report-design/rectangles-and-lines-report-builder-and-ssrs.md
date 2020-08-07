---
title: Retângulos e linhas (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d6226b0c-0398-4185-8565-96099876fc21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 96b795c3edeabb938e836be3486e28e08737a8e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582297"
---
# <a name="rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="e3563-102">Retângulos e linhas (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="e3563-102">Rectangles and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e3563-103">Os retângulos e as linhas podem criar efeitos visuais em um relatório.</span><span class="sxs-lookup"><span data-stu-id="e3563-103">Rectangles and lines can create visual effects within a report.</span></span> <span data-ttu-id="e3563-104">É possível definir propriedades de exibição nesses itens de relatório na seção Borda da guia Página inicial e definir outras propriedades usando o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="e3563-104">You can set display properties on these report items from the Border section of the Home tab, and set other properties by using the Properties pane.</span></span> <span data-ttu-id="e3563-105">É possível adicionar recursos como uma cor ou imagem de plano de fundo, uma dica de ferramenta ou um indicador a um retângulo.</span><span class="sxs-lookup"><span data-stu-id="e3563-105">You can add features like a background color or image, a tooltip, or a bookmark to a rectangle.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="rectangles-and-lines-as-report-parts"></a><a name="RectanglesLinesReportParts"></a> <span data-ttu-id="e3563-106">Retângulos e linhas como partes de relatório</span><span class="sxs-lookup"><span data-stu-id="e3563-106">Rectangles and Lines as Report Parts</span></span>  
 <span data-ttu-id="e3563-107">Você pode publicar retângulos com os itens que eles contêm separadamente do relatório como partes do relatório.</span><span class="sxs-lookup"><span data-stu-id="e3563-107">You can publish rectangles with the items that they contain separately from the report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 <span data-ttu-id="e3563-108">Não é possível publicar os itens de relatório dentro do retângulo como partes de relatório.</span><span class="sxs-lookup"><span data-stu-id="e3563-108">You cannot publish the report items within the rectangle as report parts.</span></span> <span data-ttu-id="e3563-109">Quando as pessoas adicionam o retângulo a um relatório, adicionam também os itens que ele contém.</span><span class="sxs-lookup"><span data-stu-id="e3563-109">When people add the rectangle to a report, they get the rectangle and the items it contains.</span></span>  
  

  
##  <a name="using-a-rectangle-as-a-container"></a><a name="RectangleAsContainer"></a><span data-ttu-id="e3563-110">Usando um retângulo como um contêiner</span><span class="sxs-lookup"><span data-stu-id="e3563-110">Using a Rectangle as a Container</span></span>  
 <span data-ttu-id="e3563-111">É possível usar um retângulo como um contêiner para outros itens.</span><span class="sxs-lookup"><span data-stu-id="e3563-111">You can use a rectangle as a container for other items.</span></span> <span data-ttu-id="e3563-112">Quando o retângulo é movido, os itens que estão contidos nele também são movidos.</span><span class="sxs-lookup"><span data-stu-id="e3563-112">When you move the rectangle, the items that are contained within the rectangle move along with it.</span></span> <span data-ttu-id="e3563-113">Um item dentro do retângulo mostra o nome do retângulo em sua propriedade **Parent** .</span><span class="sxs-lookup"><span data-stu-id="e3563-113">An item within the rectangle shows the name of the rectangle in its **Parent** property.</span></span> <span data-ttu-id="e3563-114">Para obter mais informações sobre como usar um retângulo como um contêiner, consulte [Adicionar um retângulo ou contêiner &#40;Construtor de Relatórios e SSRS&#41;](add-a-rectangle-or-container-report-builder-and-ssrs.md) e [Exibir os mesmos dados em uma matriz e um gráfico &#40;Construtor de Relatórios&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e3563-114">For more information about using a rectangle as a container, see [Add a Rectangle or Container &#40;Report Builder and SSRS&#41;](add-a-rectangle-or-container-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3563-115">Um retângulo é um contêiner apenas para itens que você cria no retângulo ou arrasta para dentro dele.</span><span class="sxs-lookup"><span data-stu-id="e3563-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="e3563-116">Se você desenhar um retângulo ao redor de um item que já existe na superfície de design, o retângulo não funcionará como seu contêiner.</span><span class="sxs-lookup"><span data-stu-id="e3563-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span> <span data-ttu-id="e3563-117">O retângulo não será listado na propriedade Pai do item.</span><span class="sxs-lookup"><span data-stu-id="e3563-117">The rectangle will not be listed in the item's Parent property.</span></span>  
  
 <span data-ttu-id="e3563-118">Ao usar retângulos para conter itens de relatório, considere a maneira como os itens serão afetados como um todo durante a renderização do relatório.</span><span class="sxs-lookup"><span data-stu-id="e3563-118">When using rectangles to contain report items, consider how the items will be affected as a whole during report rendering.</span></span> <span data-ttu-id="e3563-119">Os itens de relatório que contêm linhas de dados repetidas (por exemplo, tabelas) serão expandidos para acomodar os dados retornados por uma consulta, e isso afeta o posicionamento de outros itens no retângulo.</span><span class="sxs-lookup"><span data-stu-id="e3563-119">Report items that contain repeated rows of data (for example, tables) will expand to accommodate the data that is returned by a query, and this affects the positioning of other items in the rectangle.</span></span> <span data-ttu-id="e3563-120">A tabela empurrará os itens para baixo, se eles estiverem posicionados abaixo da região de dados.</span><span class="sxs-lookup"><span data-stu-id="e3563-120">A table will push items down if they are positioned below the data region.</span></span> <span data-ttu-id="e3563-121">Para fixar um item no lugar, coloque o item de relatório dentro de um retângulo que tenha uma borda superior acima da borda inferior da tabela.</span><span class="sxs-lookup"><span data-stu-id="e3563-121">To anchor an item in place, you can place the report item inside of a rectangle that has an upper edge above the lower edge of the table.</span></span> <span data-ttu-id="e3563-122">Para obter mais informações, consulte [Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e3563-122">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="adding-a-report-border"></a><a name="ReportBorder"></a><span data-ttu-id="e3563-123">Adicionando uma borda de relatório</span><span class="sxs-lookup"><span data-stu-id="e3563-123">Adding a Report Border</span></span>  
 <span data-ttu-id="e3563-124">É possível adicionar uma borda a um relatório adicionando bordas aos próprios cabeçalhos, rodapés e corpo do relatório, sem adicionar linhas ou retângulos.</span><span class="sxs-lookup"><span data-stu-id="e3563-124">You can add a border to a report by adding borders to the headers, footers, and report body themselves, without adding lines or rectangles.</span></span> <span data-ttu-id="e3563-125">Para obter mais informações, consulte [Adicionar uma borda a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e3563-125">For more information, see [Add a Border to a Report &#40;Report Builder and SSRS&#41;](add-a-border-to-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="e3563-126">Tópicos de instruções</span><span class="sxs-lookup"><span data-stu-id="e3563-126">How-To Topics</span></span>  
 [<span data-ttu-id="e3563-127">Adicionar uma borda a um relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e3563-127">Add a Border to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-to-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e3563-128">Adicionar um retângulo ou um contêiner &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e3563-128">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e3563-129">Adicionar e modificar uma linha &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e3563-129">Add and Modify a Line &#40;Report Builder and SSRS&#41;</span></span>](add-and-modify-a-line-report-builder-and-ssrs.md)  
  
## <a name="see-also"></a><span data-ttu-id="e3563-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e3563-130">See Also</span></span>  
 [<span data-ttu-id="e3563-131">Adicionar um retângulo ou um contêiner &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e3563-131">Add a Rectangle or Container &#40;Report Builder and SSRS&#41;</span></span>](add-a-rectangle-or-container-report-builder-and-ssrs.md)  
  
  
