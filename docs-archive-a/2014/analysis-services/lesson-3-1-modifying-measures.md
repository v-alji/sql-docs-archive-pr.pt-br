---
title: Modificando medidas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7bd48810-15ce-45ff-862b-372d08606995
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd352cbca1d21f5842e075d9cb8e5e766aa369b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581582"
---
# <a name="modifying-measures"></a><span data-ttu-id="b607e-102">Modificando medidas</span><span class="sxs-lookup"><span data-stu-id="b607e-102">Modifying Measures</span></span>
  <span data-ttu-id="b607e-103">Você pode usar a propriedade **FormatString** para definir configurações de formatação que controlam como as medidas são exibidas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b607e-103">You can use the **FormatString** property to define formatting settings that control how measures are displayed to users.</span></span> <span data-ttu-id="b607e-104">Nesta tarefa, você especificará propriedades de formatação para as medidas moeda e porcentagem do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b607e-104">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
### <a name="to-modify-the-measures-of-the-cube"></a><span data-ttu-id="b607e-105">Para modificar as medidas do cubo</span><span class="sxs-lookup"><span data-stu-id="b607e-105">To modify the measures of the cube</span></span>  
  
1.  <span data-ttu-id="b607e-106">Mude para a guia **Estrutura do Cubo** do Designer do cubo do Tutorial do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , expanda o grupo de medidas **Vendas pela Internet** no painel **Medidas** , clique com o botão direito do mouse em **Quantidade de Pedidos**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b607e-106">Switch to the **Cube Structure** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, expand the **Internet Sales** measure group in the **Measures** pane, right-click **Order Quantity**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b607e-107">Na janela Propriedades, clique no ícone de pino **Ocultar Automaticamente** para manter a janela Propriedades aberta.</span><span class="sxs-lookup"><span data-stu-id="b607e-107">In the Properties window, click the **Auto Hide** pushpin icon to pin the Properties window open.</span></span>  
  
     <span data-ttu-id="b607e-108">É mais fácil alterar as propriedades de vários itens no cubo quando a janela Propriedades permanece aberta.</span><span class="sxs-lookup"><span data-stu-id="b607e-108">It is easier to change properties for several items in the cube when the Properties window remains open.</span></span>  
  
3.  <span data-ttu-id="b607e-109">Na janela Propriedades, clique na lista **FormatString** e digite **#,#**.</span><span class="sxs-lookup"><span data-stu-id="b607e-109">In the Properties window, click the **FormatString** list, and then type **#,#**.</span></span>  
  
4.  <span data-ttu-id="b607e-110">Na barra de ferramentas da guia **Estrutura do Cubo** , clique no ícone **Mostrar Grade de Medidas** à esquerda.</span><span class="sxs-lookup"><span data-stu-id="b607e-110">On the toolbar of the **Cube Structure** tab, click the **Show Measures Grid** icon on the left.</span></span>  
  
     <span data-ttu-id="b607e-111">A exibição das grades permite que você selecione várias medidas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b607e-111">The grid view lets you select multiple measures at the same time.</span></span>  
  
5.  <span data-ttu-id="b607e-112">Selecione as medidas a seguir.</span><span class="sxs-lookup"><span data-stu-id="b607e-112">Select the following measures.</span></span> <span data-ttu-id="b607e-113">Você pode selecionar várias medidas clicando em cada uma enquanto mantém pressionada a tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="b607e-113">You can select multiple measures by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="b607e-114">**Unit Price**</span><span class="sxs-lookup"><span data-stu-id="b607e-114">**Unit Price**</span></span>  
  
    -   <span data-ttu-id="b607e-115">**Valor Ampliado**</span><span class="sxs-lookup"><span data-stu-id="b607e-115">**Extended Amount**</span></span>  
  
    -   <span data-ttu-id="b607e-116">**Valor de desconto**</span><span class="sxs-lookup"><span data-stu-id="b607e-116">**Discount Amount**</span></span>  
  
    -   <span data-ttu-id="b607e-117">**Custo Padrão do Produto**</span><span class="sxs-lookup"><span data-stu-id="b607e-117">**Product Standard Cost**</span></span>  
  
    -   <span data-ttu-id="b607e-118">**Custo Total do Produto**</span><span class="sxs-lookup"><span data-stu-id="b607e-118">**Total Product Cost**</span></span>  
  
    -   <span data-ttu-id="b607e-119">**Valor das Vendas**</span><span class="sxs-lookup"><span data-stu-id="b607e-119">**Sales Amount**</span></span>  
  
    -   <span data-ttu-id="b607e-120">**Valor dos Impostos**</span><span class="sxs-lookup"><span data-stu-id="b607e-120">**Tax Amt**</span></span>  
  
    -   <span data-ttu-id="b607e-121">**Freight**</span><span class="sxs-lookup"><span data-stu-id="b607e-121">**Freight**</span></span>  
  
6.  <span data-ttu-id="b607e-122">Na janela Propriedades, na lista **FormatString** , selecione **Moeda**.</span><span class="sxs-lookup"><span data-stu-id="b607e-122">In the Properties window, in the **FormatString** list, select **Currency**.</span></span>  
  
7.  <span data-ttu-id="b607e-123">Na lista suspensa na parte superior da janela Propriedades (logo abaixo da barra de título), selecione a medida **Percentual de Desconto no Preço Unitário**e **Percentual** na lista **FormatString** .</span><span class="sxs-lookup"><span data-stu-id="b607e-123">In the drop-down list at the top of the Properties window (right below the title bar), select the measure **Unit Price Discount Pct**, and then select **Percent** in the **FormatString** list.</span></span>  
  
8.  <span data-ttu-id="b607e-124">No janela Propriedades, altere a propriedade **nome** da medida **percentual de desconto de preço unitário** para `Unit Price Discount Percentage` .</span><span class="sxs-lookup"><span data-stu-id="b607e-124">In the Properties window, change the **Name** property for the **Unit Price Discount Pct** measure to `Unit Price Discount Percentage`.</span></span>  
  
9. <span data-ttu-id="b607e-125">No painel **medidas** , clique em **imposto AMT** e altere o nome dessa medida para `Tax Amount` .</span><span class="sxs-lookup"><span data-stu-id="b607e-125">In the **Measures** pane, click **Tax Amt** and change the name of this measure to `Tax Amount`.</span></span>  
  
10. <span data-ttu-id="b607e-126">Na janela Propriedades, clique no ícone **Ocultar Automaticamente** para ocultar a janela Propriedades. Depois, clique em **Mostrar Árvore de Medidas** na barra de ferramentas da guia **Estrutura do Cubo** .</span><span class="sxs-lookup"><span data-stu-id="b607e-126">In the Properties window, click the **Auto Hide** icon to hide the Properties window, and then click **Show Measures Tree** on the toolbar of the **Cube Structure** tab.</span></span>  
  
11. <span data-ttu-id="b607e-127">No menu **Arquivo**, clique em **Salvar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="b607e-127">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b607e-128">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="b607e-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b607e-129">Modificando a dimensão Cliente</span><span class="sxs-lookup"><span data-stu-id="b607e-129">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="b607e-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b607e-130">See Also</span></span>  
 <span data-ttu-id="b607e-131">[Definir dimensões de banco de dados](multidimensional-models/define-database-dimensions.md) </span><span class="sxs-lookup"><span data-stu-id="b607e-131">[Define Database Dimensions](multidimensional-models/define-database-dimensions.md) </span></span>  
 [<span data-ttu-id="b607e-132">Configurar propriedades de medida</span><span class="sxs-lookup"><span data-stu-id="b607e-132">Configure Measure Properties</span></span>](multidimensional-models/configure-measure-properties.md)  
  
  
