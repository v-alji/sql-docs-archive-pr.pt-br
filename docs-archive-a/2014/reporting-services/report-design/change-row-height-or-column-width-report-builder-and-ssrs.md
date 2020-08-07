---
title: Alterar a altura da linha ou a largura da coluna (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f061c204-5cd5-4467-9a9c-8a12803d93ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5d75a8101d07d7d6e81c624d08cd951277936eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576218"
---
# <a name="change-row-height-or-column-width-report-builder-and-ssrs"></a><span data-ttu-id="9ebfd-102">Alterar a altura da linha ou a largura da coluna (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="9ebfd-102">Change Row Height or Column Width (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9ebfd-103">Quando você define a altura de uma linha, você está especificando a altura máxima da linha no relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-103">When you set a row height, you are specifying the maximum height for the row in the rendered report.</span></span> <span data-ttu-id="9ebfd-104">No entanto, por padrão, as caixas de texto na linha são definidas para crescer na vertical para acomodar seus dados em tempo de execução e isso pode fazer com que uma linha seja expandida além da altura especificada.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-104">However, by default, text boxes in the row are set to grow vertically to accommodate their data at run-time, and this can cause a row to expand beyond the height that you specify.</span></span> <span data-ttu-id="9ebfd-105">Para definir uma altura de linha fixa, você deve alterar as propriedades da caixa de texto para que elas não se expandam automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-105">To set a fixed row height, you must change the text box properties so they do not automatically expand.</span></span>  
  
 <span data-ttu-id="9ebfd-106">Quando você define a largura de coluna, você está especificando a largura máxima da coluna no relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-106">When you set a column width, you are specifying the maximum width for the column in the rendered report.</span></span> <span data-ttu-id="9ebfd-107">As colunas não se ajustam automaticamente na horizontal para acomodar o texto.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-107">Columns do not automatically adjust horizontally to accommodate text.</span></span>  
  
 <span data-ttu-id="9ebfd-108">Se uma célula em uma linha ou coluna contém um retângulo ou uma região de dados, a altura e largura mínimas da célula são determinadas pela altura e largura do item contido.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-108">If a cell in a row or column contains a rectangle or data region, the minimum height and width of the cell is determined by the height and width of the contained item.</span></span> <span data-ttu-id="9ebfd-109">Para obter mais informações, consulte [Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9ebfd-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-row-height-by-moving-row-handles"></a><span data-ttu-id="9ebfd-110">Para alterar a altura da linha movendo os indicadores de linha</span><span class="sxs-lookup"><span data-stu-id="9ebfd-110">To change row height by moving row handles</span></span>  
  
1.  <span data-ttu-id="9ebfd-111">No modo Design, clique em qualquer parte da região de dados tablix para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-111">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="9ebfd-112">As alças de linha cinzas são exibidas na borda externa dessa região.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-112">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="9ebfd-113">Focalize a borda da alça da linha que deseja expandir.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-113">Hover over the row handle edge that you want to expand.</span></span> <span data-ttu-id="9ebfd-114">Será exibida uma seta com duas pontas.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-114">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="9ebfd-115">Clique para prender a borda da linha e movê-la para cima ou para baixo para ajustar a altura da linha.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-115">Click to grab the edge of the row and move it higher or lower to adjust the row height.</span></span>  
  
### <a name="to-change-row-height-by-setting-cell-properties"></a><span data-ttu-id="9ebfd-116">Para alterar a altura da linha definindo as propriedades de célula</span><span class="sxs-lookup"><span data-stu-id="9ebfd-116">To change row height by setting cell properties</span></span>  
  
1.  <span data-ttu-id="9ebfd-117">Na exibição Design, clique em uma célula na linha da tabela.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-117">In Design view, click a cell in the table row.</span></span>  
  
     <span data-ttu-id="9ebfd-118">![Célula selecionada em uma tabela](../media/table-selectcell.png "Célula selecionada em uma tabela")</span><span class="sxs-lookup"><span data-stu-id="9ebfd-118">![Selected Cell in a Table](../media/table-selectcell.png "Selected Cell in a Table")</span></span>  
  
2.  <span data-ttu-id="9ebfd-119">No painel **Propriedades** exibido, modifique a propriedade **Altura** , e clique em qualquer lugar fora do painel **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="9ebfd-119">In the **Properties** pane that displays, modify the **Height** property, and then click anywhere outside the **Properties** pane.</span></span>  
  
     <span data-ttu-id="9ebfd-120">![Painel de propriedades para a célula de tabela selecionada](../media/cell-propertiespane.png "Painel de propriedades para a célula de tabela selecionada")</span><span class="sxs-lookup"><span data-stu-id="9ebfd-120">![Properties Pane for selected table cell](../media/cell-propertiespane.png "Properties Pane for selected table cell")</span></span>  
  
### <a name="to-prevent-a-row-from-automatically-expanding-vertically"></a><span data-ttu-id="9ebfd-121">Para impedir que uma linha se expanda automaticamente na vertical</span><span class="sxs-lookup"><span data-stu-id="9ebfd-121">To prevent a row from automatically expanding vertically</span></span>  
  
1.  <span data-ttu-id="9ebfd-122">No modo Design, clique em qualquer parte da região de dados tablix para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-122">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="9ebfd-123">As alças de linha cinzas são exibidas na borda externa dessa região.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-123">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="9ebfd-124">Clique na alça da linha para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-124">Click the row handle to select the row.</span></span>  
  
3.  <span data-ttu-id="9ebfd-125">No painel Propriedades, defina CanGrow como **False**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-125">In the Properties pane, set CanGrow to **False**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9ebfd-126">Se você não puder ver o painel Propriedades, no menu **Exibir** , clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-126">If you cannot see the Properties pane, from the **View** menu, click **Properties**.</span></span>  
  
### <a name="to-change-column-width"></a><span data-ttu-id="9ebfd-127">Para alterar a largura da coluna</span><span class="sxs-lookup"><span data-stu-id="9ebfd-127">To change column width</span></span>  
  
1.  <span data-ttu-id="9ebfd-128">No modo Design, clique em qualquer parte da região de dados tablix para selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-128">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="9ebfd-129">As alças de coluna cinzas são exibidas na borda externa dessa região.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-129">Gray column handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="9ebfd-130">Focalize a borda da alça da coluna que deseja expandir.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-130">Hover over the column handle edge that you want to expand.</span></span> <span data-ttu-id="9ebfd-131">Será exibida uma seta com duas pontas.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-131">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="9ebfd-132">Clique para prender a borda da coluna e movê-la para a esquerda ou direita para ajustar a largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="9ebfd-132">Click to grab the edge of the column and move it left or right to adjust the column width.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ebfd-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9ebfd-133">See Also</span></span>  
 <span data-ttu-id="9ebfd-134">[Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9ebfd-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9ebfd-135">[Células, linhas e colunas da região de dados Tablix &#40;Construtor de Relatórios&#41; e SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9ebfd-135">[Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9ebfd-136">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9ebfd-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9ebfd-137">[Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9ebfd-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9ebfd-138">[Lista &#40;Construtor de Relatórios e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9ebfd-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9ebfd-139">Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9ebfd-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
