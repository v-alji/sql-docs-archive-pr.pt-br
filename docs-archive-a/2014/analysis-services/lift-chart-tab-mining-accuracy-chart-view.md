---
title: Guia gráfico de comparação de precisão (exibição de gráfico de exatidão de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.liftchart.f1
ms.assetid: f1674e2e-d38e-40c7-b8d1-5585ce9a0168
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7cdad01ff3549140bf4fed606b1e8f9eaed10dac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686434"
---
# <a name="lift-chart-tab-mining-accuracy-chart-view"></a><span data-ttu-id="b16bb-102">Guia do gráfico de comparação de precisão (Exibição de gráfico de precisão de mineração)</span><span class="sxs-lookup"><span data-stu-id="b16bb-102">Lift Chart Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="b16bb-103">Use o painel **Gráfico de Comparação de Precisão** para exibir um gráfico que compara todos os modelos de mineração selecionados na estrutura de mineração selecionada.</span><span class="sxs-lookup"><span data-stu-id="b16bb-103">Use the **Lift Chart** pane to view a chart that compares all the selected mining models in the selected mining structure.</span></span>  
  
 <span data-ttu-id="b16bb-104">Se o modelo previr um atributo discreto, o painel poderá exibir um gráfico de comparação de precisão ou um gráfico de ganho.</span><span class="sxs-lookup"><span data-stu-id="b16bb-104">If the model predicts a discrete attribute, the pane can display either a lift chart or a profit chart.</span></span> <span data-ttu-id="b16bb-105">Para obter mais informações sobre gráficos de comparação de precisão, consulte [Gráfico de comparação de precisão &#40;Analysis Services – Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b16bb-105">For information about lift charts, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="b16bb-106">Para criar um gráfico de ganho, você deve fornecer informações adicionais sobre o custo da implementação das recomendações do modelo de mineração, assim como o retorno esperado.</span><span class="sxs-lookup"><span data-stu-id="b16bb-106">To create a profit chart, you must provide additional information about the cost of implementing the recommendations of the mining model, as well as the expected return.</span></span> <span data-ttu-id="b16bb-107">Para obter mais informações, consulte [Gráfico de ganho &#40;Analysis Services – Data Mining&#41;](data-mining/profit-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b16bb-107">For more information, see [Profit Chart &#40;Analysis Services - Data Mining&#41;](data-mining/profit-chart-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="b16bb-108">Se o modelo previr um atributo contínuo, o painel exibirá um gráfico de dispersão.</span><span class="sxs-lookup"><span data-stu-id="b16bb-108">If the model predicts a continuous attribute, the pane will display a scatter plot graph.</span></span>  
  
 <span data-ttu-id="b16bb-109">Para obter informações gerais sobre métodos de medir a precisão de um modelo de mineração, veja [Gráfico de comparação de precisão &#40;Analysis Services – Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b16bb-109">For general information about methods of measuring the accuracy of a mining model, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b16bb-110">Opções</span><span class="sxs-lookup"><span data-stu-id="b16bb-110">Options</span></span>  
 <span data-ttu-id="b16bb-111">**Tipo de Gráfico**</span><span class="sxs-lookup"><span data-stu-id="b16bb-111">**Chart Type**</span></span>  
 <span data-ttu-id="b16bb-112">Defina o tipo de gráfico para exibir no visualizador.</span><span class="sxs-lookup"><span data-stu-id="b16bb-112">Sets the type of chart to display in the viewer.</span></span> <span data-ttu-id="b16bb-113">É possível selecionar **Gráfico de Comparação de Precisão** ou **Gráfico de Ganho**.</span><span class="sxs-lookup"><span data-stu-id="b16bb-113">You can select either **Lift Chart** or **Profit Chart**.</span></span>  
  
 <span data-ttu-id="b16bb-114">**Configurações**</span><span class="sxs-lookup"><span data-stu-id="b16bb-114">**Settings**</span></span>  
 <span data-ttu-id="b16bb-115">Abra a caixa de diálogo **Configurações do Gráfico de Ganho** que você pode usar para configurar um gráfico de ganho.</span><span class="sxs-lookup"><span data-stu-id="b16bb-115">Opens the **Profit Chart Settings** dialog box, which you can use to configure a profit chart.</span></span>  
  
 <span data-ttu-id="b16bb-116">O gráfico de ganho não estará disponível se uma coluna previsível contínua for selecionada na guia **Mapeamento de Coluna** .</span><span class="sxs-lookup"><span data-stu-id="b16bb-116">The profit chart is not available if a continuous predictable column was selected in the **Column Mapping** tab.</span></span>  
  
 <span data-ttu-id="b16bb-117">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="b16bb-117">**Copy**</span></span>  
 <span data-ttu-id="b16bb-118">Copiar o gráfico para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b16bb-118">Copies the chart to the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b16bb-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b16bb-119">See Also</span></span>  
 <span data-ttu-id="b16bb-120">[Designer de gráfico de precisão de mineração &#40;mineração de dados&#41;](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b16bb-120">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="b16bb-121">[Tarefas de teste e validação e instruções &#40;mineração de dados&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b16bb-121">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="b16bb-122">Teste e validação &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="b16bb-122">Testing and Validation &#40;Data Mining&#41;</span></span>](data-mining/testing-and-validation-data-mining.md)  
  
  
