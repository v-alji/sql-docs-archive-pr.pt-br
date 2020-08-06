---
title: Guia matriz de classificação (exibição de gráfico de precisão de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.confusionmatrix.f1
ms.assetid: 85d5a047-d656-41e0-8a31-400271c2a620
author: minewiskan
ms.author: owend
ms.openlocfilehash: d202d552b25095d0d0845ff64f9c0e289f7bba0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571077"
---
# <a name="classification-matrix-tab-mining-accuracy-chart-view"></a><span data-ttu-id="89f4b-102">Guia Matriz de Classificação (Exibição do Gráfico de Precisão de Mineração)</span><span class="sxs-lookup"><span data-stu-id="89f4b-102">Classification Matrix Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="89f4b-103">A guia **matriz de classificação** exibe uma matriz de classificação para cada modelo selecionado na grade modelos na guia mapeamento de **coluna** . A matriz de classificação só estará disponível se a coluna previsível selecionada na guia **mapeamento de coluna** não for contínua.</span><span class="sxs-lookup"><span data-stu-id="89f4b-103">The **Classification Matrix** tab displays a classification matrix for each model selected in the models grid on the **Column Mapping** tab. The classification matrix is only available if the predictable column that is selected in the **Column Mapping** tab is not continuous.</span></span> <span data-ttu-id="89f4b-104">Para obter uma descrição mais detalhada da guia **Matriz de Classificação** , consulte [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="89f4b-104">For a more detailed description of the **Classification Matrix** tab, see [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="89f4b-105">Opções</span><span class="sxs-lookup"><span data-stu-id="89f4b-105">Options</span></span>  
 <span data-ttu-id="89f4b-106">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="89f4b-106">**Copy**</span></span>  
 <span data-ttu-id="89f4b-107">Copia o conteúdo de cada matriz de classificação para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="89f4b-107">Copies the content of each classification matrix to the clipboard.</span></span>  
  
 <span data-ttu-id="89f4b-108">**Contagens para \<model> on\< predictable column>**</span><span class="sxs-lookup"><span data-stu-id="89f4b-108">**Counts for \<model> on \< predictable column>**</span></span>  
 <span data-ttu-id="89f4b-109">Exibe uma matriz de classificação para cada modelo de mineração na estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="89f4b-109">Displays a classification matrix for each mining model in the mining structure.</span></span> <span data-ttu-id="89f4b-110">A matriz contém as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="89f4b-110">The matrix contains the following columns:</span></span>  
  
|<span data-ttu-id="89f4b-111">Valor</span><span class="sxs-lookup"><span data-stu-id="89f4b-111">Value</span></span>|<span data-ttu-id="89f4b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="89f4b-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="89f4b-113">**Previsto**</span><span class="sxs-lookup"><span data-stu-id="89f4b-113">**Predicted**</span></span>|<span data-ttu-id="89f4b-114">Contém uma linha para cada estado da coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="89f4b-114">Contains a row for each state of the predictable column.</span></span>|  
|<span data-ttu-id="89f4b-115">**\<states>fato**</span><span class="sxs-lookup"><span data-stu-id="89f4b-115">**\<states> (actual)**</span></span>|<span data-ttu-id="89f4b-116">Uma coluna para cada estado da coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="89f4b-116">A column for each state in the predictable column.</span></span> <span data-ttu-id="89f4b-117">Se o estado da linha e da coluna forem correspondentes, a célula representará o número real de vezes em que o estado aparece no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="89f4b-117">If the state of the row and the column correspond, the cell represents the actual number of times the state exists in the database.</span></span> <span data-ttu-id="89f4b-118">Se não corresponderem, a célula representará o erro da previsão.</span><span class="sxs-lookup"><span data-stu-id="89f4b-118">If they do not correspond, the cell represents the error of the prediction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89f4b-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="89f4b-119">See Also</span></span>  
 <span data-ttu-id="89f4b-120">[Designer de gráfico de precisão de mineração &#40;mineração de dados&#41;](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="89f4b-120">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="89f4b-121">[Tarefas de teste e validação e instruções &#40;mineração de dados&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="89f4b-121">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="89f4b-122">Teste e validação &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="89f4b-122">Testing and Validation &#40;Data Mining&#41;</span></span>](data-mining/testing-and-validation-data-mining.md)  
  
  
