---
title: Caixa de diálogo Drill-through (Visualizador do modelo de mineração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.drillthrough.f1
ms.assetid: 42b78399-143d-4f44-90e0-b545ffb79e10
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1b00c62017de5a26c4507a04aeaf59aba7522146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582194"
---
# <a name="drill-through-dialog-box-mining-model-viewer"></a><span data-ttu-id="b9512-102">Caixa de diálogo Extrair Detalhes (Visualizador do modelo de mineração)</span><span class="sxs-lookup"><span data-stu-id="b9512-102">Drill Through Dialog Box (Mining Model Viewer)</span></span>
  <span data-ttu-id="b9512-103">Ao exibir um modelo de mineração usando a guia **Visualizador do Modelo de Mineração** do Designer de Mineração de Dados, é possível detalhar os dados de caso, contanto que o modelo tenha o detalhamento habilitado.</span><span class="sxs-lookup"><span data-stu-id="b9512-103">When you view a mining model by using the **Mining Model Viewer** tab of Data Mining Designer, you can drill through into details about the case data, provided the model has drillthrough enabled.</span></span> <span data-ttu-id="b9512-104">Além disso, se a estrutura de mineração subjacente tiver o detalhamento habilitado, também será possível ver colunas na estrutura de mineração, mesmo se essas colunas não tiverem sido incluídas no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="b9512-104">Moreover, if the underlying mining structure has drillthrough enabled, you can also see columns in the mining structure, even if those columns were not included in the mining model.</span></span> <span data-ttu-id="b9512-105">Na lista de colunas, as colunas da estrutura têm o rótulo “Structure.” como</span><span class="sxs-lookup"><span data-stu-id="b9512-105">In the column list, the structure columns are prefixed by the "Structure."</span></span> <span data-ttu-id="b9512-106">prefixo.</span><span class="sxs-lookup"><span data-stu-id="b9512-106">label.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9512-107">Não é possível habilitar o detalhamento em uma estrutura de mineração existente.</span><span class="sxs-lookup"><span data-stu-id="b9512-107">You cannot enable drillthrough on an existing mining structure.</span></span> <span data-ttu-id="b9512-108">Em vez disso, você deve recriar a estrutura de mineração e habilitar o detalhamento durante o processo de criação.</span><span class="sxs-lookup"><span data-stu-id="b9512-108">Instead, you must re-create the mining structure and enable drillthrough during the creation process.</span></span>  
  
 <span data-ttu-id="b9512-109">Para obter informações sobre como acessar os dados de caso de cada visualizador de modelo de mineração que dá suporte ao detalhamento, **consulte** [Detalhar dados do caso com base em um modelo de mineração](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="b9512-109">For information about how to access case data from each of the mining model viewers that support drillthrough, **see** [Drill Through to Case Data from a Mining Model](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b9512-110">Opções</span><span class="sxs-lookup"><span data-stu-id="b9512-110">Options</span></span>  
 <span data-ttu-id="b9512-111">**Casos Classificados em**</span><span class="sxs-lookup"><span data-stu-id="b9512-111">**Cases Classified To**</span></span>  
 <span data-ttu-id="b9512-112">Exibe a definição da regra, o conjunto de itens e o cluster contidos no nó selecionado.</span><span class="sxs-lookup"><span data-stu-id="b9512-112">Displays the definition of the rule, itemset, and cluster that are contained in the selected node.</span></span>  
  
 <span data-ttu-id="b9512-113">**Lista de colunas**</span><span class="sxs-lookup"><span data-stu-id="b9512-113">**Column list**</span></span>  
 <span data-ttu-id="b9512-114">Exibe as colunas no modelo, seguida pelas colunas da estrutura.</span><span class="sxs-lookup"><span data-stu-id="b9512-114">Displays the columns in the model, followed by the structure columns.</span></span>  
  
 <span data-ttu-id="b9512-115">**Observação** As colunas da estrutura são exibidas somente se o detalhamento estiver habilitado na estrutura de mineração e se você tiver selecionado a opção **Colunas do Modelo e da Estrutura**.</span><span class="sxs-lookup"><span data-stu-id="b9512-115">**Note** Structure columns are displayed only if drillthrough is enabled on the mining structure, and if you selected the option, **Model and Structure Columns**.</span></span> <span data-ttu-id="b9512-116">Além disso, você deve ter permissões de detalhamento no modelo de mineração e na estrutura de mineração para exibir as colunas.</span><span class="sxs-lookup"><span data-stu-id="b9512-116">Moreover, you must have drillthrough permissions on both the mining model and the mining structure to view the columns.</span></span>  
  
 <span data-ttu-id="b9512-117">As colunas de estrutura que não estão incluídas no modelo aparecem como **estrutura \<column name> .**.</span><span class="sxs-lookup"><span data-stu-id="b9512-117">Structure columns that are not included in the model appear as **Structure.\<column name>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9512-118">É possível clicar com o botão direito do mouse em qualquer lugar da grade da coluna e selecionar **Copiar Tudo** para copiar os dados do detalhamento, no formato delimitado por tabulação, para a Área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b9512-118">You can right-click anywhere in the column grid and select **Copy All** to copy the drillthrough data, in tab-delimited format, to the Clipboard.</span></span> <span data-ttu-id="b9512-119">Os dados copiados incluem apenas os dados de caso, não a definição de nó.</span><span class="sxs-lookup"><span data-stu-id="b9512-119">The copied data includes only the case data, not the node definition.</span></span>  
  
 <span data-ttu-id="b9512-120">**Reproduzir**</span><span class="sxs-lookup"><span data-stu-id="b9512-120">**Play**</span></span>  
 <span data-ttu-id="b9512-121">Clique no botão de seta verde para atualizar os dados.</span><span class="sxs-lookup"><span data-stu-id="b9512-121">Click the green arrow button to refresh the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9512-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b9512-122">See Also</span></span>  
 <span data-ttu-id="b9512-123">[Consultas de detalhamento &#40;mineração de dados&#41;](data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b9512-123">[Drillthrough Queries &#40;Data Mining&#41;](data-mining/drillthrough-queries-data-mining.md) </span></span>  
 <span data-ttu-id="b9512-124">[Visualizadores de modelo de mineração &#40;designer de modelo de mineração de dados&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="b9512-124">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="b9512-125">Tarefas e instruções do visualizador do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="b9512-125">Mining Model Viewer Tasks and How-tos</span></span>](data-mining/mining-model-viewer-tasks-and-how-tos.md)  
  
  
