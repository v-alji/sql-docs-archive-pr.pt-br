---
title: Adicionar, mover ou excluir uma tabela, matriz ou lista (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b97c470-cde0-4bb1-a46e-5f5f5553feaa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 43941639a41c897a49cd34662b74de26a27e3f07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684538"
---
# <a name="add-move-or-delete-a-table-matrix-or-list-report-builder-and-ssrs"></a><span data-ttu-id="b356b-102">Adicionar, mover ou excluir uma tabela, matriz ou lista (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="b356b-102">Add, Move, or Delete a Table, Matrix, or List (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b356b-103">Uma região de dados exibe dados a partir de um conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="b356b-103">A data region displays data from a report dataset.</span></span> <span data-ttu-id="b356b-104">As regiões de dados incluem tabela, matriz, gráfico e medidor.</span><span class="sxs-lookup"><span data-stu-id="b356b-104">Data regions include table, matrix, list, chart, and gauge.</span></span> <span data-ttu-id="b356b-105">Para aninhar uma região de dados dentro de outra, adicione cada uma separadamente e arraste a região de dados filho para a região de dados pai.</span><span class="sxs-lookup"><span data-stu-id="b356b-105">To nest one data region inside another, add each data region separately, and then drag the child data region onto the parent data region.</span></span>  
  
 <span data-ttu-id="b356b-106">A maneira mais simples de adicionar uma região de dados de tabela ou matriz a seu relatório é executar o Assistente de Nova Tabela ou Nova Matriz.</span><span class="sxs-lookup"><span data-stu-id="b356b-106">The simplest way to add a table or matrix data region to your report is to run the New Table or New Matrix Wizard.</span></span> <span data-ttu-id="b356b-107">Esses assistentes o orientarão pelo processo de escolher uma conexão com uma fonte de dados, organizar campos e escolher o layout e o estilo.</span><span class="sxs-lookup"><span data-stu-id="b356b-107">These wizards will guide you through the process of choosing a connection to a data source, arranging fields, and choosing the layout and style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b356b-108">O assistente só está disponível no Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="b356b-108">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-table-or-matrix-to-a-report-by-using-the-new-table-or-new-matrix-wizard"></a><span data-ttu-id="b356b-109">Para adicionar uma tabela ou matriz a um relatório usando o Assistente de Nova Tabela ou Nova Matriz</span><span class="sxs-lookup"><span data-stu-id="b356b-109">To add a table or matrix to a report by using the New Table or New Matrix Wizard</span></span>  
  
1.  <span data-ttu-id="b356b-110">Na guia **Inserir** , clique em **Tabela** ou **Matriz**e clique em **Assistente de Tabela** ou **Assistente de Matriz**.</span><span class="sxs-lookup"><span data-stu-id="b356b-110">On the **Insert** tab, click **Table** or **Matrix**, and then click **Table Wizard** or **Matrix Wizard**.</span></span>  
  
2.  <span data-ttu-id="b356b-111">Siga as etapas no assistente de **NewTable** ou **nova matriz** .</span><span class="sxs-lookup"><span data-stu-id="b356b-111">Follow the steps in the **NewTable** or **New Matrix** wizard.</span></span>  
  
3.  <span data-ttu-id="b356b-112">Na guia **Página Inicial** , clique em **Executar** para visualizar o relatório renderizado.</span><span class="sxs-lookup"><span data-stu-id="b356b-112">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="b356b-113">Na guia **Executar** , clique em **Design** para continuar trabalhando no relatório.</span><span class="sxs-lookup"><span data-stu-id="b356b-113">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-data-region"></a><span data-ttu-id="b356b-114">Para adicionar uma região de dados</span><span class="sxs-lookup"><span data-stu-id="b356b-114">To add a data region</span></span>  
  
1.  <span data-ttu-id="b356b-115">Na **Faixa de Opções**, no grupo **Regiões de Dados** , clique na região de dados que será adicionada.</span><span class="sxs-lookup"><span data-stu-id="b356b-115">On the **Ribbon**, in the **Data Regions** group, click the data region to add.</span></span>  
  
2.  <span data-ttu-id="b356b-116">Clique na superfície de design e a arraste para criar uma caixa com o tamanho desejado da região de dados.</span><span class="sxs-lookup"><span data-stu-id="b356b-116">Click the design surface, and then drag to create a box that is the desired size of the data region.</span></span>  
  
3.  <span data-ttu-id="b356b-117">Arraste um campo do conjunto de dados do relatório do painel de dados do relatório para a célula da região de dados.</span><span class="sxs-lookup"><span data-stu-id="b356b-117">Drag a report dataset field from the Report Data pane onto a data region cell.</span></span> <span data-ttu-id="b356b-118">A região de dados agora está associada aos dados de um conjunto de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="b356b-118">The data region is now bound to data from the report dataset.</span></span>  
  
### <a name="to-select-a-data-region"></a><span data-ttu-id="b356b-119">Para selecionar uma região de dados</span><span class="sxs-lookup"><span data-stu-id="b356b-119">To select a data region</span></span>  
  
-   <span data-ttu-id="b356b-120">Para uma região de dados de tablix, clique com o botão direito na alça de canto.</span><span class="sxs-lookup"><span data-stu-id="b356b-120">For a tablix data region, right-click the corner handle.</span></span> <span data-ttu-id="b356b-121">Em uma região de dados de gráfico ou medidor, clique na região de dados.</span><span class="sxs-lookup"><span data-stu-id="b356b-121">For a chart or gauge data region, click in the data region.</span></span>  
  
     <span data-ttu-id="b356b-122">Uma alça de seleção e oito alças de redimensionamento são exibidas.</span><span class="sxs-lookup"><span data-stu-id="b356b-122">A selection handle and eight resizing handles appear.</span></span>  
  
     <span data-ttu-id="b356b-123">Para regiões de dados aninhadas, clique com o botão direito do mouse na região de dados aninhada, clique em **Selecionar**e, em seguida, selecione o item de relatório desejado.</span><span class="sxs-lookup"><span data-stu-id="b356b-123">For nested data regions, right-click in the nested data region, click **Select**, and then select the report item you want.</span></span> <span data-ttu-id="b356b-124">Para verificar qual item de relatório está selecionado, use o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="b356b-124">To verify which report item is selected, use the Properties pane.</span></span> <span data-ttu-id="b356b-125">O nome do item selecionado na superfície de design aparece na barra de ferramentas do painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="b356b-125">The name of the selected item on the design surface appears in the toolbar of the Properties pane.</span></span>  
  
### <a name="to-move-a-data-region"></a><span data-ttu-id="b356b-126">Para mover uma região de dados</span><span class="sxs-lookup"><span data-stu-id="b356b-126">To move a data region</span></span>  
  
-   <span data-ttu-id="b356b-127">Para mover uma região de dados, clique na alça de seleção da região de dados e arraste-a.</span><span class="sxs-lookup"><span data-stu-id="b356b-127">To move a data region, click the selection handle of the data region and drag it.</span></span> <span data-ttu-id="b356b-128">Use linhas ajustadas para alinhá-las aos itens de relatório existentes.</span><span class="sxs-lookup"><span data-stu-id="b356b-128">Use snaplines to align it to existing report items.</span></span>  
  
     <span data-ttu-id="b356b-129">Se a régua não estiver visível, clique na guia Exibir e selecione a opção **Régua** .</span><span class="sxs-lookup"><span data-stu-id="b356b-129">If the ruler is not visible, click the View tab and select the **Ruler** option.</span></span>  
  
     <span data-ttu-id="b356b-130">Como alternativa, use as teclas de seta para mover a região de dados selecionada na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="b356b-130">Alternatively, use the arrow keys to move the selected data region on the design surface.</span></span>  
  
### <a name="to-delete-a-data-region"></a><span data-ttu-id="b356b-131">Para excluir uma região de dados</span><span class="sxs-lookup"><span data-stu-id="b356b-131">To delete a data region</span></span>  
  
-   <span data-ttu-id="b356b-132">Selecione a região de dados, clique nela com o botão direito do mouse e, em seguida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b356b-132">Select the data region, right-click in the data region, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b356b-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b356b-133">See Also</span></span>  
 <span data-ttu-id="b356b-134">[Região de dados Tablix &#40;Construtor de Relatórios e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b356b-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b356b-135">[Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b356b-135">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b356b-136">[Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b356b-136">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b356b-137">[Lista &#40;Construtor de Relatórios e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b356b-137">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b356b-138">Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b356b-138">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
