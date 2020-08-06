---
title: Incluir indicadores e medidores em um painel de medidores (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4dff9b67-b483-4c51-a822-6dbe706a6840
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b1107745f54cd94abd7507a3e9b5a706ca5402de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684543"
---
# <a name="include-indicators-and-gauges-in-a-gauge-panel-report-builder-and-ssrs"></a><span data-ttu-id="9cb51-102">Incluir indicadores e medidores em um painel de medidores (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="9cb51-102">Include Indicators and Gauges in a Gauge Panel (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9cb51-103">O painel de medidores é o contêiner de nível superior que mantém um ou mais medidores e indicadores.</span><span class="sxs-lookup"><span data-stu-id="9cb51-103">The gauge panel is the top-level container that holds one or more gauges and indicators.</span></span> <span data-ttu-id="9cb51-104">Os indicadores podem ser inseridos em medidores ou colocados ao lado deles no painel de medidores.</span><span class="sxs-lookup"><span data-stu-id="9cb51-104">Indicators can be embedded in gauges or placed next to them in the gauge panel.</span></span>  
  
 <span data-ttu-id="9cb51-105">Se o indicador e o medidor forem adjacentes no painel de medidores e mostrarem dados de campos diferentes, talvez você queira adicionar rótulos para esclarecer quais dados são transmitidos pelo medidor e pelo indicador.</span><span class="sxs-lookup"><span data-stu-id="9cb51-105">If the indicator and gauge are adjacent in the gauge panel and show data from different fields, you might want to add labels to make it clear what data the gauge and indicator convey.</span></span>  
  
 <span data-ttu-id="9cb51-106">As opções de indicador e medidor podem ser definidas com o uso de expressões.</span><span class="sxs-lookup"><span data-stu-id="9cb51-106">Gauge and indicator options can be set by using expressions.</span></span> <span data-ttu-id="9cb51-107">Para obter mais informações, consulte [Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9cb51-107">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-indicator-in-a-gauge"></a><span data-ttu-id="9cb51-108">Para inserir um indicador em um medidor</span><span class="sxs-lookup"><span data-stu-id="9cb51-108">To embed an indicator in a gauge</span></span>  
  
1.  <span data-ttu-id="9cb51-109">Abra um relatório existente ou crie um novo relatório que contenha uma tabela e matriz com os dados a serem exibidos.</span><span class="sxs-lookup"><span data-stu-id="9cb51-109">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="9cb51-110">Para obter mais informações, consulte [Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) ou [Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9cb51-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="9cb51-111">Insira uma coluna em sua tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="9cb51-111">Insert a column in your table or matrix.</span></span> <span data-ttu-id="9cb51-112">Para obter mais informações, consulte [Inserir ou excluir uma coluna &#40;Construtor de Relatórios e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9cb51-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="9cb51-113">Na guia **Inserir** , no grupo **Regiões de Dados** , clique em **Medidor**e clique em uma célula na nova coluna.</span><span class="sxs-lookup"><span data-stu-id="9cb51-113">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then, and then click a cell in the new column.</span></span> <span data-ttu-id="9cb51-114">A caixa de diálogo **Selecionar Tipo de Medidor** é exibida.</span><span class="sxs-lookup"><span data-stu-id="9cb51-114">The **Select Gauge Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="9cb51-115">Clique em **Radial**.</span><span class="sxs-lookup"><span data-stu-id="9cb51-115">Click **Radial**.</span></span> <span data-ttu-id="9cb51-116">O primeiro medidor radial é selecionado.</span><span class="sxs-lookup"><span data-stu-id="9cb51-116">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="9cb51-117">Clique no medidor.</span><span class="sxs-lookup"><span data-stu-id="9cb51-117">Click the gauge.</span></span> <span data-ttu-id="9cb51-118">O painel **Dados do Medidor** é exibido.</span><span class="sxs-lookup"><span data-stu-id="9cb51-118">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="9cb51-119">Na área **Valores** , na caixa de listagem **(Não Especificado)** , clique no campo cujos valores você deseja exibir no medidor.</span><span class="sxs-lookup"><span data-stu-id="9cb51-119">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="9cb51-120">Se desejar, arraste o campo a ser usado a partir do conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="9cb51-120">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="9cb51-121">Clique com o botão direito do mouse no medidor, clique em **Adicionar Indicador**e em **Filho**.</span><span class="sxs-lookup"><span data-stu-id="9cb51-121">Right-click the gauge, click **Add Indicator**, and then click **Child**.</span></span> <span data-ttu-id="9cb51-122">A caixa de diálogo **Selecionar Estilo de Indicador** é aberta.</span><span class="sxs-lookup"><span data-stu-id="9cb51-122">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="9cb51-123">Na caixa de diálogo **Selecionar Estilo de Indicador** , no painel esquerdo, clique no tipo de indicador desejado e no conjunto de indicadores.</span><span class="sxs-lookup"><span data-stu-id="9cb51-123">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="9cb51-124">Clique no indicador.</span><span class="sxs-lookup"><span data-stu-id="9cb51-124">Click the indicator.</span></span> <span data-ttu-id="9cb51-125">O painel **Dados do Medidor** é exibido.</span><span class="sxs-lookup"><span data-stu-id="9cb51-125">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="9cb51-126">Na área **Valores** , na caixa de listagem **(Não Especificado)** , clique no campo cujos valores você deseja exibir como indicador.</span><span class="sxs-lookup"><span data-stu-id="9cb51-126">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="9cb51-127">Se desejar, arraste o campo a ser usado a partir do conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="9cb51-127">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="9cb51-128">O campo pode ser o mesmo ou um campo diferente daquele usado no medidor.</span><span class="sxs-lookup"><span data-stu-id="9cb51-128">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-show-an-indicator-and-gauge-side-by-side"></a><span data-ttu-id="9cb51-129">Para mostrar um indicador e um medidor lado a lado</span><span class="sxs-lookup"><span data-stu-id="9cb51-129">To show an indicator and gauge side by side</span></span>  
  
1.  <span data-ttu-id="9cb51-130">Abra um relatório existente ou crie um novo relatório que contenha uma tabela e matriz com os dados a serem exibidos.</span><span class="sxs-lookup"><span data-stu-id="9cb51-130">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="9cb51-131">Para obter mais informações, consulte [Tabelas &#40;Construtor de Relatórios e SSRS&#41;](tables-report-builder-and-ssrs.md) ou [Matrizes &#40;Construtor de Relatórios e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9cb51-131">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="9cb51-132">Insira uma coluna em sua tabela ou matriz.</span><span class="sxs-lookup"><span data-stu-id="9cb51-132">Insert a column in your table or matrix.</span></span> <span data-ttu-id="9cb51-133">Para obter mais informações, consulte [Inserir ou excluir uma coluna &#40;Construtor de Relatórios e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9cb51-133">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="9cb51-134">Na guia **Inserir** , no grupo **Regiões de Dados** , clique em **Medidor**e clique em uma célula na coluna inserida.</span><span class="sxs-lookup"><span data-stu-id="9cb51-134">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click a cell in the column you inserted.</span></span> <span data-ttu-id="9cb51-135">A caixa de diálogo **Selecionar Tipo de Medidor** é exibida.</span><span class="sxs-lookup"><span data-stu-id="9cb51-135">The **Select Gauge Type** dialog appears.</span></span>  
  
4.  <span data-ttu-id="9cb51-136">Clique em **Radial**.</span><span class="sxs-lookup"><span data-stu-id="9cb51-136">Click **Radial**.</span></span> <span data-ttu-id="9cb51-137">O primeiro medidor radial é selecionado.</span><span class="sxs-lookup"><span data-stu-id="9cb51-137">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="9cb51-138">Clique no medidor.</span><span class="sxs-lookup"><span data-stu-id="9cb51-138">Click the gauge.</span></span> <span data-ttu-id="9cb51-139">O painel **Dados do Medidor** é exibido.</span><span class="sxs-lookup"><span data-stu-id="9cb51-139">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="9cb51-140">Na área **Valores** , na caixa de listagem **(Não Especificado)** , clique no campo cujos valores você deseja exibir no medidor.</span><span class="sxs-lookup"><span data-stu-id="9cb51-140">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="9cb51-141">Se desejar, arraste o campo a ser usado a partir do conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="9cb51-141">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="9cb51-142">Clique com o botão direito do mouse no medidor, clique em **Adicionar Indicador**e em **Adjacente**.</span><span class="sxs-lookup"><span data-stu-id="9cb51-142">Right-click the gauge, click **Add Indicator**, and then click **Adjacent**.</span></span> <span data-ttu-id="9cb51-143">A caixa de diálogo **Selecionar Estilo de Indicador** é aberta.</span><span class="sxs-lookup"><span data-stu-id="9cb51-143">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="9cb51-144">Na caixa de diálogo **Selecionar Estilo de Indicador** , no painel esquerdo, clique no tipo de indicador desejado e no conjunto de indicadores.</span><span class="sxs-lookup"><span data-stu-id="9cb51-144">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="9cb51-145">Clique no indicador.</span><span class="sxs-lookup"><span data-stu-id="9cb51-145">Click the indicator.</span></span> <span data-ttu-id="9cb51-146">O painel **Dados do Medidor** é exibido.</span><span class="sxs-lookup"><span data-stu-id="9cb51-146">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="9cb51-147">Na área **Valores** , na caixa de listagem **(Não Especificado)** , clique no campo cujos valores você deseja exibir como indicador.</span><span class="sxs-lookup"><span data-stu-id="9cb51-147">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="9cb51-148">Se desejar, arraste o campo a ser usado a partir do conjunto de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="9cb51-148">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="9cb51-149">O campo pode ser o mesmo ou um campo diferente daquele usado no medidor.</span><span class="sxs-lookup"><span data-stu-id="9cb51-149">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
14. <span data-ttu-id="9cb51-150">Clique com o botão direito do mouse no painel de medidores e clique em **Adicionar Rótulo**.</span><span class="sxs-lookup"><span data-stu-id="9cb51-150">Right-click the gauge panel and click **Add Label**.</span></span> <span data-ttu-id="9cb51-151">Um rótulo é adicionado ao painel de medidores.</span><span class="sxs-lookup"><span data-stu-id="9cb51-151">A label is added to the gauge panel.</span></span> <span data-ttu-id="9cb51-152">Repita uma mais vez.</span><span class="sxs-lookup"><span data-stu-id="9cb51-152">Repeat one more time.</span></span>  
  
     <span data-ttu-id="9cb51-153">O painel de medidores tem dois rótulos.</span><span class="sxs-lookup"><span data-stu-id="9cb51-153">The gauge panel has two labels.</span></span>  
  
15. <span data-ttu-id="9cb51-154">Arraste cada rótulo para um local perto do medidor ou do indicador.</span><span class="sxs-lookup"><span data-stu-id="9cb51-154">Drag each label to a location near the gauge or indicator.</span></span>  
  
16. <span data-ttu-id="9cb51-155">Clique com o botão direito do mouse no rótulo ao lado do medidor, clique em **Propriedades do Rótulo**e digite o texto desejado na caixa **Texto** .</span><span class="sxs-lookup"><span data-stu-id="9cb51-155">Right-click the label near the gauge, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
17. <span data-ttu-id="9cb51-156">Clique com o botão direito do mouse no rótulo ao lado do indicador, clique em **Propriedades do Rótulo**e digite o texto desejado na caixa **Texto** .</span><span class="sxs-lookup"><span data-stu-id="9cb51-156">Right-click the label near the indicator, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
18. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9cb51-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9cb51-157">See Also</span></span>  
 [<span data-ttu-id="9cb51-158">Indicadores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9cb51-158">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
