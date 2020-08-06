---
title: Adicionar ou remover margens de um gráfico (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91c43f58-5771-4d33-a54d-0e802d2f5cba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d8bad99591964540bcd14fc5609560a3d324515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682135"
---
# <a name="add-or-remove-margins-from-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="16301-102">Adicionar ou remover margens de um gráfico (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="16301-102">Add or Remove Margins from a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="16301-103">Nos tipos de gráfico de Colunas e Dispersão, o gráfico adiciona automaticamente margens laterais nas extremidades do eixo x.</span><span class="sxs-lookup"><span data-stu-id="16301-103">In Column and Scatter chart types, the chart automatically adds side margins on the ends of the x-axis.</span></span> <span data-ttu-id="16301-104">Nos tipos de gráfico de Barras, o gráfico adiciona automaticamente margens laterais nas extremidades do eixo y.</span><span class="sxs-lookup"><span data-stu-id="16301-104">In Bar chart types, the chart automatically adds side margins on the ends of the y-axis.</span></span> <span data-ttu-id="16301-105">Em todos os outros tipos de gráfico, as margens laterais não são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="16301-105">In all other chart types, the chart does not add side margins.</span></span> <span data-ttu-id="16301-106">Não é possível alterar o tamanho da margem.</span><span class="sxs-lookup"><span data-stu-id="16301-106">You cannot change the size of the margin.</span></span>  
  
 <span data-ttu-id="16301-107">Este tópico não se aplica aos tipos de gráfico de pizza, anel, funil ou pirâmide.</span><span class="sxs-lookup"><span data-stu-id="16301-107">This topic does not apply to pie, doughnut, funnel, or pyramid chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-enable-or-disable-side-margins"></a><span data-ttu-id="16301-108">Para habilitar ou desabilitar as margens laterais</span><span class="sxs-lookup"><span data-stu-id="16301-108">To enable or disable side margins</span></span>  
  
1.  <span data-ttu-id="16301-109">Clique com o botão direito do mouse no eixo e selecione **Propriedades do Eixo**.</span><span class="sxs-lookup"><span data-stu-id="16301-109">Right-click the axis and select **Axis Properties**.</span></span> <span data-ttu-id="16301-110">A caixa de diálogo **Propriedades do Eixo Vertical** ou **Horizontal** é exibida.</span><span class="sxs-lookup"><span data-stu-id="16301-110">The **Vertical** or **HorizontalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="16301-111">Na página **Opções do Eixo** , defina a propriedade **Margens laterais** :</span><span class="sxs-lookup"><span data-stu-id="16301-111">On the **Axis Options** page, set the **Side margins** property:</span></span>  
  
    -   <span data-ttu-id="16301-112">**Automático** O gráfico determinará se deve ser adicionada uma margem lateral com base no tipo de gráfico.</span><span class="sxs-lookup"><span data-stu-id="16301-112">**Auto** The chart will determine whether to add a side margin based on the chart type.</span></span>  
  
    -   <span data-ttu-id="16301-113">**Desabilitado** Os gráficos de barra, coluna e dispersão não terão nenhuma margem lateral.</span><span class="sxs-lookup"><span data-stu-id="16301-113">**Disabled** Bar, column, and scatter charts will have no side margins.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="16301-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16301-114">See Also</span></span>  
 <span data-ttu-id="16301-115">[Formatando rótulos dos eixos de um gráfico &#40;Construtor de Relatórios e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="16301-115">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="16301-116">[Caixa de diálogo Propriedades do Eixo, Opções de Eixo &#40;Construtor de Relatórios e SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="16301-116">[Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="16301-117">[Especificar um intervalo do eixo &#40;Construtor de Relatórios e SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="16301-117">[Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="16301-118">[Formatar rótulos de eixo como datas ou moedas &#40;Construtor de Relatórios e SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="16301-118">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="16301-119">Gráficos &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="16301-119">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
