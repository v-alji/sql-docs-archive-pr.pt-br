---
title: Alterar o discretização de uma coluna em um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discretization [Analysis Services]
- mining structures [Analysis Services], how-to topics
- discretized columns [data mining]
- bucketing problems [Analysis Services]
ms.assetid: 3c49862b-595d-4fa4-b890-e2e1bde1d74f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b20d6428afac5c1492fdc74aafd4d0c010159d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582222"
---
# <a name="change-the-discretization-of-a-column-in-a-mining-model"></a><span data-ttu-id="7499e-102">Alterar a diferenciação de uma coluna em um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="7499e-102">Change the Discretization of a Column in a Mining Model</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="7499e-103">discretiza valores automaticamente – ou seja, ele faz a trificação de dados em uma coluna numérica em determinados cenários.</span><span class="sxs-lookup"><span data-stu-id="7499e-103">automatically discretizes values-that is to say, it bins data in numeric column-in certain scenarios.</span></span> <span data-ttu-id="7499e-104">Por exemplo, se seus dados contêm dados numéricos contínuos e você cria um modelo de árvore de decisão, cada coluna de dados contínuos é compartimentalizada automaticamente, dependendo da distribuição dos dados.</span><span class="sxs-lookup"><span data-stu-id="7499e-104">For example, if your data contains continuous numeric data and you create a decision tree model, each column of continuous data will be automatically binned, depending on the distribution of the data.</span></span> <span data-ttu-id="7499e-105">Para controlar o modo como os dados são diferenciados, altere as propriedades na coluna da estrutura de mineração que controla como os dados são usados no modelo.</span><span class="sxs-lookup"><span data-stu-id="7499e-105">If you want to control how the data is discretized, you must change the properties on the mining structure column that control how the data is used in the model.</span></span>  
  
 <span data-ttu-id="7499e-106">Para obter informações gerais sobre como definir as propriedades em um modelo de mineração, consulte [Colunas do modelo de mineração](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="7499e-106">For general information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-display-the-properties-for-a-mining-model-column"></a><span data-ttu-id="7499e-107">Para exibir as propriedades para uma coluna do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="7499e-107">To display the properties for a mining model column</span></span>  
  
1.  <span data-ttu-id="7499e-108">Na guia **Modelos de Mineração** do Designer de Mineração de Dados, clique com o botão direito do mouse no cabeçalho da coluna que contém o nome do modelo de mineração ou na linha da grade que contém o nome do algoritmo de mineração e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7499e-108">In the **Mining Models** tab in Data Mining Designer, right-click the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="7499e-109">A janela **Propriedades** exibe as propriedades que são associadas com o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="7499e-109">The **Properties** window displays the properties that are associated with the mining model as a whole.</span></span>  
  
2.  <span data-ttu-id="7499e-110">Na coluna **Estrutura** próxima ao lado esquerdo da tela, clique na coluna que contém os dados numéricos contínuos que você deseja diferenciar.</span><span class="sxs-lookup"><span data-stu-id="7499e-110">In the **Structure** column near the left side of the screen, click the column that contains the continuous numeric data you want to discretize.</span></span>  
  
     <span data-ttu-id="7499e-111">A janela **Propriedades** altera para exibir apenas as propriedades associadas com aquela coluna.</span><span class="sxs-lookup"><span data-stu-id="7499e-111">The **Properties** window changes to display just the properties associated with that column.</span></span>  
  
### <a name="to-change-the-discretization-method"></a><span data-ttu-id="7499e-112">Para alterar o método de diferenciação</span><span class="sxs-lookup"><span data-stu-id="7499e-112">To change the discretization method</span></span>  
  
1.  <span data-ttu-id="7499e-113">Na janela **Propriedades de mineração** , clique na caixa de texto ao lado de **conteúdo**e selecione `Discretized` na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="7499e-113">In the **Mining Properties** window, click the text box next to **Content**, and select `Discretized` from the dropdown list.</span></span>  
  
     <span data-ttu-id="7499e-114">A janela <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> e <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> agora estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="7499e-114">The <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> properties are now enabled.</span></span>  
  
2.  <span data-ttu-id="7499e-115">Na janela **Propriedades** , clique na caixa de texto ao lado de <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> e selecione um dos seguintes valores: `Automatic` , `EqualAreas` ou `Cluster` .</span><span class="sxs-lookup"><span data-stu-id="7499e-115">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> and select one of the following values: `Automatic`, `EqualAreas`, or `Cluster`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7499e-116">Se o uso da coluna for definido como `Ignore` , a janela **Propriedades** da coluna ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="7499e-116">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="7499e-117">O novo valor entrará em vigor quando você selecionar um elemento diferente no designer.</span><span class="sxs-lookup"><span data-stu-id="7499e-117">The new value will take effect when you select a different element in the designer.</span></span>  
  
3.  <span data-ttu-id="7499e-118">Na guia **Propriedades** , clique na caixa de texto próxima a <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> e digite um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="7499e-118">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and type a numeric value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7499e-119">Se alterar essas propriedades, a estrutura deve ser reprocessada juntamente com quaisquer modelos no quais você queira usar a nova configuração.</span><span class="sxs-lookup"><span data-stu-id="7499e-119">If you change these properties, the structure must be reprocessed, along with any models that you want to use the new setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7499e-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7499e-120">See Also</span></span>  
 [<span data-ttu-id="7499e-121">Tarefas e instruções do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="7499e-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
