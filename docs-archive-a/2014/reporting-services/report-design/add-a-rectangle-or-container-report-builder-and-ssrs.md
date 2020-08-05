---
title: Adicionar um retângulo ou um contêiner (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10061"
- sql12.rtp.rptdesigner.rectangleproperties.general.f1
ms.assetid: f905c35f-754d-4d02-80f3-85e29ddda826
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5fddda2f02b9f370d9742ae6add5bae444f8f55f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569095"
---
# <a name="add-a-rectangle-or-container-report-builder-and-ssrs"></a><span data-ttu-id="5bbb8-102">Adicionar um retângulo ou um contêiner (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="5bbb8-102">Add a Rectangle or Container (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5bbb8-103">Adicione um retângulo a seu relatório quando quiser que um elemento gráfico separe áreas do relatório, enfatize áreas de um relatório ou forneça um plano de fundo para um ou mais itens de relatório.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-103">Add a rectangle to your report when you want a graphical element to separate areas of the report, emphasize areas of a report, or provide a background for one or more report items.</span></span> <span data-ttu-id="5bbb8-104">Os retângulos também são usados como contêineres para ajudar a controlar a maneira como as regiões de dados são renderizadas em um relatório.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-104">Rectangles are also used as containers to help control the way data regions render in a report.</span></span> <span data-ttu-id="5bbb8-105">Você pode personalizar a aparência de um retângulo editando suas propriedades, como plano de fundo e cores da borda.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-105">You can customize the appearance of a rectangle by editing rectangle properties such as the background and border colors.</span></span> <span data-ttu-id="5bbb8-106">Para obter mais informações sobre como usar um retângulo como um contêiner, consulte [Retângulos e linhas &#40;Construtor de Relatórios e SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) e [Exibir os mesmos dados em uma matriz e um gráfico &#40;Construtor de Relatórios&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="5bbb8-106">For more information about using a rectangle as a container, see [Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-rectangle"></a><span data-ttu-id="5bbb8-107">Para adicionar um retângulo</span><span class="sxs-lookup"><span data-stu-id="5bbb8-107">To add a rectangle</span></span>  
  
1.  <span data-ttu-id="5bbb8-108">Na guia **Inserir** , no grupo **Itens de Relatório** , clique em **Retângulo**.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-108">On the **Insert** tab, in the **Report Items** group, click **Rectangle.**</span></span>  
  
2.  <span data-ttu-id="5bbb8-109">Na superfície de design, clique no local onde deseja exibir o canto superior esquerdo do retângulo e arraste até onde deseja colocar o canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-109">On the design surface, click the location where you want the upper left corner of the rectangle, and drag to where you want the lower-right corner.</span></span>  
  
     <span data-ttu-id="5bbb8-110">À medida que você move o cursor, “linhas de ajuste” aparecem como as linhas do cursor junto com outros objetos na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-110">Note that as you move the cursor, "snap lines" appear as the cursor lines up with other objects on the design surface.</span></span> <span data-ttu-id="5bbb8-111">Isso será útil se você desejar alinhar os objetos.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-111">These help you if you want objects to be aligned.</span></span>  
  
### <a name="to-create-a-container"></a><span data-ttu-id="5bbb8-112">Para criar um contêiner</span><span class="sxs-lookup"><span data-stu-id="5bbb8-112">To create a container</span></span>  
  
1.  <span data-ttu-id="5bbb8-113">Adicione um item de relatório retângulo ao relatório.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-113">Add a rectangle report item to the report.</span></span>  
  
2.  <span data-ttu-id="5bbb8-114">Arraste outros itens de relatório para o retângulo.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-114">Drag other report items into the rectangle.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5bbb8-115">Um retângulo é um contêiner apenas para itens que você cria no retângulo ou arrasta para dentro dele.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="5bbb8-116">Se você desenhar um retângulo ao redor de um item que já existe na superfície de design, o retângulo não funcionará como seu contêiner.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span>  
  
### <a name="to-change-rectangle-properties-such-as-color-style-or-weight"></a><span data-ttu-id="5bbb8-117">Para alterar propriedades de retângulo, como cor, estilo ou peso</span><span class="sxs-lookup"><span data-stu-id="5bbb8-117">To change rectangle properties such as color, style, or weight</span></span>  
  
1.  <span data-ttu-id="5bbb8-118">Selecione o retângulo e clique nas opções de cor, estilo ou peso de linha na seção **Borda** da guia Página Inicial.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-118">Select the rectangle, and then click the line color, style, or weight options in the **Border** section of the Home tab.</span></span>  
  
2.  <span data-ttu-id="5bbb8-119">Clique na seta próxima ao botão **Borda** para determinar quais lados do retângulo devem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-119">Click the arrow next to the **Border** button to determine which sides of the rectangle to change.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5bbb8-120">Se você definir o estilo de linha como **duplo** e a largura da linha for de 1 1/2 pt ou mais estreita, a linha poderá não aparecer dupla quando você executar o relatório em Construtor de Relatórios, Report Designer ou Report Manager.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-120">If you set the line style to **Double** and the line width is 1 1/2 pt or narrower, the line may not appear double when you run the report in Report Builder, Report Designer, or Report Manager.</span></span> <span data-ttu-id="5bbb8-121">Ela parecerá dupla quando você exportar o relatório para outros formatos, como Microsoft Word e Acrobat PDF.</span><span class="sxs-lookup"><span data-stu-id="5bbb8-121">It will appear double when you export the report to other formats such as Microsoft Word and Acrobat PDF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bbb8-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5bbb8-122">See Also</span></span>  
 <span data-ttu-id="5bbb8-123">[Retângulos e linhas &#40;Construtor de Relatórios e SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5bbb8-123">[Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5bbb8-124">Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5bbb8-124">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
