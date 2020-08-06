---
title: Usando o detalhamento em dados de estrutura (tutorial de mineração de dados básico) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a693979c-0564-4d6d-b35d-cbbc8f350469
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 49a1ced27150676def541548f47a90a3f847c8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568924"
---
# <a name="using-drillthrough-on-structure-data-basic-data-mining-tutorial"></a><span data-ttu-id="732d5-102">Usando o detalhamento em dados de estrutura (Tutorial de mineração de dados básico)</span><span class="sxs-lookup"><span data-stu-id="732d5-102">Using Drillthrough on Structure Data (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="732d5-103">Como parte de sua campanha publicitária, [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] o está enviando um mensageiro para clientes potenciais na era demográfica de 34-40.</span><span class="sxs-lookup"><span data-stu-id="732d5-103">As part of their advertising campaign, [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] is sending a mailer to potential customers in the 34-40 age demographic.</span></span> <span data-ttu-id="732d5-104">O departamento de marketing decidiu que também gostaria de enviar a mala direta aos clientes que compraram bicicletas da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] há mais de cinco anos.</span><span class="sxs-lookup"><span data-stu-id="732d5-104">The marketing department has decided that they would also like to send the mailer to the customers who purchased bikes from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] more than five years ago.</span></span> <span data-ttu-id="732d5-105">Nesta lição, você identificará clientes com bicicletas mais antigas e irá recuperar suas informações de contato.</span><span class="sxs-lookup"><span data-stu-id="732d5-105">In this lesson you will identify customers with older bikes and retrieve their contact information.</span></span> <span data-ttu-id="732d5-106">Essas informações não estão incluídas no modelo, mas na estrutura.</span><span class="sxs-lookup"><span data-stu-id="732d5-106">This information is not included in the model, but is included in the structure.</span></span> <span data-ttu-id="732d5-107">Para recuperar as informações de contato, primeiro você terá de garantir que o detalhamento esteja habilitado para a estrutura para depois usá-lo para revelar os nomes e os endereços dos clientes-alvo.</span><span class="sxs-lookup"><span data-stu-id="732d5-107">To retrieve the contact information you will first ensure that drillthrough is enabled for the structure and then you will use drillthrough to reveal the names and addresses of the targeted customers.</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="732d5-108">Como habilitar o detalhamento em um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="732d5-108">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="732d5-109">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , na guia **modelos de mineração** do designer de mineração de dados, clique com o botão direito do mouse no modelo de **TM_Decision_Tree** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="732d5-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the **TM_Decision_Tree** model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="732d5-110">Nas janelas Propriedades, clique em **AllowDrillthrough**e selecione **True**.</span><span class="sxs-lookup"><span data-stu-id="732d5-110">In the Properties windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="732d5-111">Na guia Modelos de Mineração , clique com o botão direito do mouse no modelo e selecione **Modelo de Processo**.</span><span class="sxs-lookup"><span data-stu-id="732d5-111">In the Mining Models tab, right-click the model, and select **Process Model**.</span></span>  
  
 <span data-ttu-id="732d5-112">Para obter mais informações, consulte [consultas de detalhamento &#40;mineração de dados&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="732d5-112">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
### <a name="to-view-drillthrough-data-from-a-mining-model"></a><span data-ttu-id="732d5-113">Para exibir dados de detalhamento de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="732d5-113">To view drillthrough data from a mining model</span></span>  
  
1.  <span data-ttu-id="732d5-114">No Designer de Mineração de Dados, clique na guia **Visualizador do Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="732d5-114">In Data Mining Designer, click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="732d5-115">Selecione o modelo de **TM_Decision_Tree** na lista **modelo de mineração** .</span><span class="sxs-lookup"><span data-stu-id="732d5-115">Select the **TM_Decision_Tree** model from the **Mining Model** list.</span></span>  
  
3.  <span data-ttu-id="732d5-116">Altere o valor de **plano de fundo** para `1` .</span><span class="sxs-lookup"><span data-stu-id="732d5-116">Change the **Background** value to `1`.</span></span> <span data-ttu-id="732d5-117">Assim, você mostra apenas a parte do modelo que está relacionada ao cliente que comprou bicicletas.</span><span class="sxs-lookup"><span data-stu-id="732d5-117">By doing this, you show only the part of the model that is related to customer who bought bikes.</span></span>  
  
4.  <span data-ttu-id="732d5-118">Selecione o Visualizador de Árvores da Microsoft na lista **Visualizador** .</span><span class="sxs-lookup"><span data-stu-id="732d5-118">Select the Microsoft Tree viewer from the **Viewer** list.</span></span> <span data-ttu-id="732d5-119">Isso forçará o visualizador a atualizar com as novas condições de filtro.</span><span class="sxs-lookup"><span data-stu-id="732d5-119">This will force the viewer to refresh with the new filter conditions.</span></span> <span data-ttu-id="732d5-120">Em seguida, localize o nó **idade >= 34 e <41** e clique com o botão direito do mouse no nó.</span><span class="sxs-lookup"><span data-stu-id="732d5-120">Then, locate the **Age >=34 and <41** node and right-click the node.</span></span>  
  
5.  <span data-ttu-id="732d5-121">Selecione **Detalhar**e selecione **Colunas do Modelo e da Estrutura** para abrir a janela **Detalhar** .</span><span class="sxs-lookup"><span data-stu-id="732d5-121">Select **Drill Through**, and then select **Model and Structure Columns** to open the **Drill Through** window.</span></span>  
  
6.  <span data-ttu-id="732d5-122">Navegue até a coluna **Estrutura.Data da Primeira Compra** para exibir as datas de compra das bicicletas mais antigas.</span><span class="sxs-lookup"><span data-stu-id="732d5-122">Scroll to the **Structure.Date First Purchase** column to view the purchase dates for the older bikes.</span></span>  
  
7.  <span data-ttu-id="732d5-123">Para copiar os dados para a Área de Transferência, clique com o botão direito do mouse na tabela e selecione **Copiar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="732d5-123">To copy the data to the Clipboard, right-click any row in the table, and select **Copy All**.</span></span>  
  
 <span data-ttu-id="732d5-124">Parabéns, você concluiu o tutorial de mineração de dados básico.</span><span class="sxs-lookup"><span data-stu-id="732d5-124">Congratulations, you have completed the basic data mining tutorial.</span></span> <span data-ttu-id="732d5-125">Agora que você já está se sentindo confortável em usar as ferramentas de mineração de dados, recomendamos que conclua também o Tutorial de mineração de dados intermediário, que demonstra como criar modelos para previsão, análise de cesta básica e clustering de sequências.</span><span class="sxs-lookup"><span data-stu-id="732d5-125">Now that you are comfortable using the data mining tools, we recommend that you also complete the intermediate data mining tutorial, which demonstrates how to create models for forecasting, market basket analysis, and sequence clustering.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="732d5-126">Tarefa anterior da lição</span><span class="sxs-lookup"><span data-stu-id="732d5-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="732d5-127">Criando previsões &#40;Tutorial básico de Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="732d5-127">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="732d5-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="732d5-128">See Also</span></span>  
 [<span data-ttu-id="732d5-129">Criar uma consulta de previsão usando o construtor de consultas de previsão</span><span class="sxs-lookup"><span data-stu-id="732d5-129">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
