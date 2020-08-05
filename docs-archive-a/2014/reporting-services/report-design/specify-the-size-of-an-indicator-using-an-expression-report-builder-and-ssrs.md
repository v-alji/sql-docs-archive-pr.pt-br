---
title: Especificar o tamanho de um indicador usando uma expressão (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ab0b86f1-4882-4258-a2b6-c612faecfa4b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b450abb957329b8dbaa4f7f0e4c963c5f63f06b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569066"
---
# <a name="specify-the-size-of-an-indicator-using-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="47484-102">Especificar o tamanho de um indicador usando uma expressão (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="47484-102">Specify the Size of an Indicator Using an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="47484-103">Além de cor, direção e forma, você pode usar tamanho para maximizar o impacto visual de indicadores.</span><span class="sxs-lookup"><span data-stu-id="47484-103">In addition to color, direction, and shape, you can use size to maximize the visual impact of indicators.</span></span>  
  
 <span data-ttu-id="47484-104">Um indicador tem uma coleção de estados de indicador denominados IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="47484-104">An indicator has a collection of indicator states named IndicatorStates.</span></span> <span data-ttu-id="47484-105">A coleção IndicatorStates normalmente tem vários estados.</span><span class="sxs-lookup"><span data-stu-id="47484-105">The IndicatorStates collection typically have multiple states.</span></span> <span data-ttu-id="47484-106">Cada estado é um membro da coleção e é representado por um ícone.</span><span class="sxs-lookup"><span data-stu-id="47484-106">Each state is a member of the collection and is represented by an icon.</span></span> <span data-ttu-id="47484-107">Juntos, os estados constituem a coleção IndicatorsStates.</span><span class="sxs-lookup"><span data-stu-id="47484-107">Together the states constitute the IndicatorsStates collection.</span></span>  
  
 <span data-ttu-id="47484-108">Para configurar dinamicamente os tamanhos de ícones, você define propriedades de membros da coleção IndicatorsStates no painel Propriedades do Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="47484-108">To dynamically configure the sizes of icons, you set properties of members of the IndicatorsStates collection in the Properties pane of Report Builder.</span></span> <span data-ttu-id="47484-109">Se o painel **Propriedades** não estiver visível, clique na guia **Exibir** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="47484-109">If the **Properties** pane is not visible, click the **View** tab and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47484-110">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], você usa a janela **Propriedades** para definir propriedades do membro.</span><span class="sxs-lookup"><span data-stu-id="47484-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you use the **Properties** window to set the member properties.</span></span> <span data-ttu-id="47484-111">Se a janela **Propriedades** não estiver aberta, pressione a tecla F4.</span><span class="sxs-lookup"><span data-stu-id="47484-111">If the **Properties** window is not open, press the F4 key.</span></span>  
  
 <span data-ttu-id="47484-112">O painel **Propriedades** fornece acesso às propriedades da coleção IndicatorStates de um indicador.</span><span class="sxs-lookup"><span data-stu-id="47484-112">The **Properties** pane provides access to the properties of the IndicatorStates collection of an indicator.</span></span> <span data-ttu-id="47484-113">Você configura os ícones para terem tamanhos diferentes definindo a propriedade ScaleFactor dos membros da coleção IndicatorStates usando uma expressão.</span><span class="sxs-lookup"><span data-stu-id="47484-113">You configure the icons to be different sizes by setting the ScaleFactor property of the IndicatorStates collection members using an expression.</span></span> <span data-ttu-id="47484-114">Para obter mais informações, consulte [Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="47484-114">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="47484-115">A expressão usada neste procedimento também foi usada para gerar o relatório com tamanhos diferentes de indicadores, mostrada em [Indicadores &#40;Construtor de Relatórios e SSRS&#41;](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="47484-115">The expression used in this procedure was also used to generate the report with different sizes of indicators, shown in [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-the-indicator-icon-size-using-an-expression"></a><span data-ttu-id="47484-116">Para especificar o tamanho do ícone de indicador usando uma expressão</span><span class="sxs-lookup"><span data-stu-id="47484-116">To specify the indicator icon size using an expression</span></span>  
  
1.  <span data-ttu-id="47484-117">Clique no indicador que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="47484-117">Click the indicator you want to change.</span></span>  
  
2.  <span data-ttu-id="47484-118">No painel Propriedades, localize a propriedade IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="47484-118">In the Properties pane, locate the IndicatorStates property.</span></span>  
  
     <span data-ttu-id="47484-119">Se o painel Propriedades for organizado por categoria, você localizará IndicatorStates na categoria **Estados** .</span><span class="sxs-lookup"><span data-stu-id="47484-119">If the Properties pane is organized by category, you will find IndicatorStates in the **States** category.</span></span>  
  
3.  <span data-ttu-id="47484-120">Clique no botão de reticências **(...)** ao lado de IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="47484-120">Click the ellipsis **(...)** button next to IndicatorStates.</span></span> <span data-ttu-id="47484-121">A caixa de diálogo **Editor de Coleções IndicatorState** será aberta.</span><span class="sxs-lookup"><span data-stu-id="47484-121">The **IndicatorState Collection Editor** dialog box opens.</span></span>  
  
     <span data-ttu-id="47484-122">Selecione todos os membros da coleção.</span><span class="sxs-lookup"><span data-stu-id="47484-122">Select all members of the collection.</span></span>  
  
4.  <span data-ttu-id="47484-123">Na lista **Propriedades de Multisseleção** , clique na seta para baixo ao lado de ScaleFactor e clique em **Expressão**.</span><span class="sxs-lookup"><span data-stu-id="47484-123">In the **Multi-Select Properties** list, click the down arrow next to ScaleFactor and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="47484-124">Na caixa de diálogo **Expressão** , escreva a expressão.</span><span class="sxs-lookup"><span data-stu-id="47484-124">In the **Expression** dialog box write the expression.</span></span>  
  
     <span data-ttu-id="47484-125">A expressão de exemplo a seguir cria o ícone de um tamanho diferente com base no valor do campo **SalesYTD** .</span><span class="sxs-lookup"><span data-stu-id="47484-125">The following sample expression makes the icon a different size based on the value of the **SalesYTD** field.</span></span>  
  
     `=IIF(Fields!SalesYTD.value = 0,0,Fields!SalesYTD.value/Max(Fields!SalesYTD.value,"Indicator"))`  
  
     <span data-ttu-id="47484-126">Para obter mais informações, consulte [Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="47484-126">For more information, see [Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="47484-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="47484-127">See Also</span></span>  
 [<span data-ttu-id="47484-128">Indicadores &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="47484-128">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
