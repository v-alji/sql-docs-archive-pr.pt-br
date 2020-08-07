---
title: Alinhar os dados de um gráfico em uma tabela ou matriz (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 75137575-d1bf-46d6-8527-5afc85eea5e1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3e4278cd9f0dd5526770b43d2c6d94a8b87158cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582328"
---
# <a name="align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs"></a><span data-ttu-id="66831-102">Alinhar os dados de um gráfico em uma tabela ou matriz (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="66831-102">Align the Data in a Chart in a Table or Matrix (Report Builder and SSRS)</span></span>
  <span data-ttu-id="66831-103">Minigráficos e barras de dados são gráficos simples que transmitem muitas informações com poucos detalhes externos.</span><span class="sxs-lookup"><span data-stu-id="66831-103">Sparklines and data bars are small, simple charts that convey a lot of information with little extraneous detail.</span></span> <span data-ttu-id="66831-104">Quando você marca essa opção, os valores nos minigráficos e nas barras de dados são alinhados nas diferentes células da tabela ou matriz, mesmo que valores estejam faltando nos dados nos quais eles se baseiam.</span><span class="sxs-lookup"><span data-stu-id="66831-104">When you check this option, the values in your sparklines and data bars will align across the different cells in the table or matrix, even if there are missing values in the data they are based on.</span></span>  
  
 <span data-ttu-id="66831-105">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span><span class="sxs-lookup"><span data-stu-id="66831-105">![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")</span></span>  
  
 <span data-ttu-id="66831-106">Nesta imagem, o gráfico de coluna mostra vendas diárias para cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="66831-106">In this image, the column chart shows daily sales for each employee.</span></span> <span data-ttu-id="66831-107">Observe que para os dias em que um funcionário não tem vendas, o gráfico deixa um espaço em branco e alinha os dias seguintes horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="66831-107">Note that for days that an employee has no sales, the chart leaves a blank and aligns subsequent days horizontally.</span></span> <span data-ttu-id="66831-108">Também alinha os gráficos verticalmente tornando os tamanhos dos diferentes gráficos relativos uns aos outros.</span><span class="sxs-lookup"><span data-stu-id="66831-108">It also aligns the charts vertically by making the sizes of the different charts relative to each other.</span></span> <span data-ttu-id="66831-109">Para obter mais informações, consulte [Minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="66831-109">For more information, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="align-the-data-in-a-sparkline-or-data-bar"></a><span data-ttu-id="66831-110">Alinhar os dados em um minigráfico ou barra de dados</span><span class="sxs-lookup"><span data-stu-id="66831-110">Align the data in a sparkline or data bar</span></span>  
  
1.  <span data-ttu-id="66831-111">Clique no minigráfico ou na barra de dados e clique em **Propriedades do Eixo Horizontal** ou **Propriedades do Eixo Vertical**.</span><span class="sxs-lookup"><span data-stu-id="66831-111">Click in the sparkline or data bar, and then click **Horizontal Axis Properties** or **Vertical Axis Properties**.</span></span>  
  
2.  <span data-ttu-id="66831-112">Na guia **Opções do Eixo** , marque a caixa **Alinhar eixos em** e, na caixa suspensa, selecione o grupo no qual alinhar o eixo.</span><span class="sxs-lookup"><span data-stu-id="66831-112">On the **Axis Options** tab, check the **Align axes in** box, and then in the dropdown box, select the group on which to align the axis.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66831-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="66831-113">See Also</span></span>  
 <span data-ttu-id="66831-114">[Gráficos &#40;Construtor de Relatórios e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="66831-114">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="66831-115">Adicionar minigráficos e barras de dados &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="66831-115">Add Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](add-sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
  
