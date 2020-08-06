---
title: Caixa de diálogo origem da partição (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionsourcedialog.f1
ms.assetid: c414dabe-9bad-49b7-9a3c-dfca87fef92b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6732e8f00dc0d01e0d3b708794a1d9c497ae4cf5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678309"
---
# <a name="partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="016f7-102">Caixa de diálogo Origem da Partição (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="016f7-102">Partition Source Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="016f7-103">Use a caixa de diálogo **Origem da Partição** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para especificar a origem dos dados da tabela de fatos para uma partição.</span><span class="sxs-lookup"><span data-stu-id="016f7-103">Use the **Partition Source** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to specify the source of fact table data for a partition.</span></span> <span data-ttu-id="016f7-104">É possível exibir a caixa de diálogo **Origem da Partição** das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="016f7-104">You can display the **Partition Source** dialog box by:</span></span>  
  
-   <span data-ttu-id="016f7-105">Clicando no botão **...** em uma célula da grade **Partições** de um grupo de medidas selecionado no painel **Grupos de Medidas** na guia **Partições** do Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="016f7-105">Clicking the **...** button on a cell from the **Partitions** grid of a selected measure group in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="016f7-106">Clicando no botão **...** no valor da propriedade **Origem** de um objeto **Partição** na janela **Propriedades** do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="016f7-106">Clicking the **...** button on the **Source** property value of a **Partition** object in the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="016f7-107">Opções</span><span class="sxs-lookup"><span data-stu-id="016f7-107">Options</span></span>  
  
|<span data-ttu-id="016f7-108">Opção</span><span class="sxs-lookup"><span data-stu-id="016f7-108">Option</span></span>|<span data-ttu-id="016f7-109">Definição</span><span class="sxs-lookup"><span data-stu-id="016f7-109">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="016f7-110">**Tipo de associação**</span><span class="sxs-lookup"><span data-stu-id="016f7-110">**Binding type**</span></span>|<span data-ttu-id="016f7-111">Selecione o tipo de associação a ser usado para a origem da partição especificada.</span><span class="sxs-lookup"><span data-stu-id="016f7-111">Select the binding type to use for the source of the specified partition.</span></span> <span data-ttu-id="016f7-112">As seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="016f7-112">The following options are available:</span></span><br /><br /> <span data-ttu-id="016f7-113">**Associação de tabela**: Selecione para exibir o painel **detalhes da Associação de tabela** e indicar que a partição está associada ao conteúdo de uma tabela em uma fonte de dados ou exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="016f7-113">**Table binding**: Select to display the **Table Binding Detail** pane and indicate that the partition is bound to the contents of a table in a data source or data source view.</span></span> <span data-ttu-id="016f7-114">Para obter mais informações sobre o painel **Detalhes de Associação de Tabela**, consulte [Detalhes de Associação de Tabela &#40;Caixa de diálogo Fonte da Partição&#41; &#40;Analysis Services – Dados Multidimensionais&#41;](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="016f7-114">For more information about the **Table Binding Detail** pane, see [Table Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span><br /><br /> <span data-ttu-id="016f7-115">**Detalhe**: Selecione para exibir o painel **detalhes da Associação de consulta** e indicar que a partição está associada ao conteúdo de uma consulta executada em uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="016f7-115">**Detail**: Select to display the **Query Binding Detail** pane and indicate that the partition is bound to the contents of a query executed on a data source.</span></span> <span data-ttu-id="016f7-116">Para obter mais informações sobre o painel **Detalhes de Associação de Consulta**, consulte [Detalhes de Associação de Consulta &#40;Caixa de diálogo Fonte da Partição&#41; &#40;Analysis Services – Dados Multidimensionais&#41;](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="016f7-116">For more information about the **Query Binding Detail** pane, see [Query Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span>|  
|<span data-ttu-id="016f7-117">**Detalhe**</span><span class="sxs-lookup"><span data-stu-id="016f7-117">**Detail**</span></span>|<span data-ttu-id="016f7-118">Exibe a caixa de diálogo **Detalhes de Associação de Tabela** ou **Detalhes de Associação de Consulta** , dependendo do valor da opção **Tipo de Associação** .</span><span class="sxs-lookup"><span data-stu-id="016f7-118">Displays either the **Table Binding Detail** dialog box or the **Query Binding Detail** dialog box, depending on the value of the **Binding type** option.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="016f7-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="016f7-119">See Also</span></span>  
 <span data-ttu-id="016f7-120">[Partições &#40;designer de cubo&#41; &#40;Analysis Services de dados multidimensionais&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="016f7-120">[Partitions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="016f7-121">Analysis Services designers e caixas de diálogo &#40;dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="016f7-121">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
