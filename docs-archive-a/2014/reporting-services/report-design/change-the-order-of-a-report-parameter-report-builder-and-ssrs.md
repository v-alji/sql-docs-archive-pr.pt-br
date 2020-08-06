---
title: Alterar a ordem de um parâmetro de relatório (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: abd61e19-dba3-423c-a26c-e8bc43197d3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad9dd25be7a87fee089a48849fcc716e682e4c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684065"
---
# <a name="change-the-order-of-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="a76ee-102">Alterar a ordem de um parâmetro de relatório (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a76ee-102">Change the Order of a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a76ee-103">Altere a ordem dos parâmetros de relatório quando você tiver um parâmetro dependente que tenha sido listado antes de o parâmetro ser dependente.</span><span class="sxs-lookup"><span data-stu-id="a76ee-103">Change the order of report parameters when you have a dependent parameter that is listed before the parameter it is dependent on.</span></span> <span data-ttu-id="a76ee-104">A ordem do parâmetro é importante quando você tem parâmetros em cascata ou quando você deseja mostrar aos usuários o valor padrão de um parâmetro antes que eles escolham os valores para outros parâmetros.</span><span class="sxs-lookup"><span data-stu-id="a76ee-104">Parameter order is important when you have cascading parameters, or when you want to show users the default value for one parameter before they choose values for other parameters.</span></span> <span data-ttu-id="a76ee-105">Um parâmetro de relatório dependente contém uma referência, seja a consulta de valores padrão ou na consulta de valores válidos, a um parâmetro de consulta que aponta para um parâmetro de relatório que está depois dele na lista de parâmetros no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="a76ee-105">A dependent report parameter contains a reference, in either its default values query or valid values query, to a query parameter that points to a report parameter that is after it in the parameter list in the Report Data pane.</span></span>  
  
 <span data-ttu-id="a76ee-106">A ordem em que você vê os parâmetros exibidos na barra de ferramentas do visualizador de relatórios é determinada pela ordem dos parâmetros no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="a76ee-106">The order that you see parameters display on the report viewer toolbar is determined by the order of the parameters in the Report Data pane.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-order-of-report-parameters"></a><span data-ttu-id="a76ee-107">Para alterar a ordem dos parâmetros de relatório</span><span class="sxs-lookup"><span data-stu-id="a76ee-107">To change the order of report parameters</span></span>  
  
1.  <span data-ttu-id="a76ee-108">No painel de dados do relatório, expanda o nó Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="a76ee-108">In the Report Data pane, expand the Parameters node.</span></span>  
  
2.  <span data-ttu-id="a76ee-109">Clique em um parâmetro e use os botões de seta para cima e para baixo da barra de ferramentas do painel de dados do relatório para movê-lo para cima ou para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="a76ee-109">Click a parameter and use the up and down arrow buttons on the Report Data pane toolbar to move the parameter higher or lower in the list.</span></span> <span data-ttu-id="a76ee-110">A imagem a seguir mostra o painel Dados do Relatório no Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="a76ee-110">The following image shows the Report Data pane in Report Builder.</span></span>  
  
     <span data-ttu-id="a76ee-111">![painel Dados do Relatório](../media/reportdatapane.png "painel Dados do Relatório")</span><span class="sxs-lookup"><span data-stu-id="a76ee-111">![Report Data Pane](../media/reportdatapane.png "Report Data Pane")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76ee-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a76ee-112">See Also</span></span>  
 <span data-ttu-id="a76ee-113">[Parâmetros de relatório &#40;Construtor de Relatórios e Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="a76ee-113">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="a76ee-114">[Construtor de Relatórios ajuda para caixas de diálogo, painéis e assistentes](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="a76ee-114">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="a76ee-115">[Adicionar parâmetros em cascata a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a76ee-115">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a76ee-116">[Tutorial: adicionar um parâmetro ao seu relatório &#40;Construtor de Relatórios&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="a76ee-116">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="a76ee-117">[Adicionar filtros de conjunto de dados, filtros de região e filtros de grupo &#40;Construtor de Relatórios e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="a76ee-117">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 [<span data-ttu-id="a76ee-118">Referências de coleções de parâmetros &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a76ee-118">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
