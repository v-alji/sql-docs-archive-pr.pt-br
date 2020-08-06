---
title: Copiar uma exibição de um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clipboards [data mining]
- Mining Model Viewer [Analysis Services], clipboards
- copying mining models to clipboard
ms.assetid: 768372db-e5b4-4990-b459-03d854fd9a6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 36d4d372bd235cd1cc0c043ff98151091e242269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678359"
---
# <a name="copy-a-view-of-a-mining-model"></a><span data-ttu-id="aedac-102">Copiar uma exibição de um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="aedac-102">Copy a View of a Mining Model</span></span>
  <span data-ttu-id="aedac-103">O **Visualizador do Modelo de Mineração** do Designer de Mineração de Dados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] usa um visualizador separado para cada tipo de modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="aedac-103">The **Mining Model Viewer** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] uses a separate viewer for each type of mining model.</span></span> <span data-ttu-id="aedac-104">Muitos dos visualizadores têm componentes a partir dos quais você pode copiar o conteúdo para a Área de Transferência e de lá colar o conteúdo em um documento ou no software de manipulação de imagens.</span><span class="sxs-lookup"><span data-stu-id="aedac-104">Several of the viewers have components from which you can copy the contents to the Clipboard, and from there paste the contents into a document or into image manipulation software.</span></span> <span data-ttu-id="aedac-105">Os componentes a seguir tornam essa funcionalidade disponível:</span><span class="sxs-lookup"><span data-stu-id="aedac-105">The following components make this functionality available:</span></span>  
  
-   <span data-ttu-id="aedac-106">Diagrama de Cluster no Visualizador de Cluster da [!INCLUDE[msCoName](../../includes/msconame-md.md)] e o Visualizador de Cluster de Sequências da [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aedac-106">Cluster Diagram in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Cluster Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="aedac-107">Árvore de Decisão no Visualizador de Árvore da [!INCLUDE[msCoName](../../includes/msconame-md.md)] e o Visualizador MTS [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aedac-107">Decision Tree in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series Viewer</span></span>  
  
-   <span data-ttu-id="aedac-108">Transições de estado no Visualizador de Cluster de Sequências da [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aedac-108">State Transitions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="aedac-109">Rede de Dependências no Visualizador de Regras de Associação da [!INCLUDE[msCoName](../../includes/msconame-md.md)] , Visualizador Naïve Bayes da [!INCLUDE[msCoName](../../includes/msconame-md.md)] e o Visualizador de Árvore da [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aedac-109">Dependency Network in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer, and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer</span></span>  
  
-   <span data-ttu-id="aedac-110">Conteúdo do modelo de mineração, do painel Detalhes do Nó do Visualizador de Árvore de Conteúdo Genérica da [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aedac-110">Mining model content, from the Node Details pane of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer</span></span>  
  
 <span data-ttu-id="aedac-111">Você pode copiar a representação completa do modelo de mineração ou apenas a parte que está visível no visualizador.</span><span class="sxs-lookup"><span data-stu-id="aedac-111">You can copy the complete representation of the mining model, or just the part that is visible in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="aedac-112">Quando você copia um modelo usando o visualizador, ele não cria um novo objeto modelo.</span><span class="sxs-lookup"><span data-stu-id="aedac-112">When you copy a model using the viewer, it does not create a new model object.</span></span> <span data-ttu-id="aedac-113">Para criar um novo modelo, você deve usar o assistente ou o Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="aedac-113">To create a new model, you must use either the wizard, or the Data Mining Designer,.</span></span> <span data-ttu-id="aedac-114">Para obter mais informações, consulte [Criar uma cópia de um modelo de mineração](make-a-copy-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="aedac-114">For more information, see [Make a Copy of a Mining Model](make-a-copy-of-a-mining-model.md).</span></span>  
  
### <a name="to-copy-the-complete-model-to-the-clipboard"></a><span data-ttu-id="aedac-115">Para copiar o modelo completo para a Área de Transferência</span><span class="sxs-lookup"><span data-stu-id="aedac-115">To copy the complete model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="aedac-116">Na lista **Modelo de Mineração** na guia **Visualizador do Modelo de Mineração** , selecione o modelo de mineração que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="aedac-116">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="aedac-117">Selecione a guia apropriada, como a guia **Rede de Dependências** e, em seguida, clique em **Copiar Gráfico Inteiro** na barra de ferramentas da guia.</span><span class="sxs-lookup"><span data-stu-id="aedac-117">Select the appropriate tab, such as the **Dependency Network** tab, and then click **Copy Entire Graph** on the toolbar of that tab.</span></span>  
  
### <a name="to-copy-the-visible-piece-of-the-model-to-the-clipboard"></a><span data-ttu-id="aedac-118">Para copiar a parte visível do modelo para a Área de Transferência</span><span class="sxs-lookup"><span data-stu-id="aedac-118">To copy the visible piece of the model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="aedac-119">Na lista **Modelo de Mineração** na guia **Visualizador do Modelo de Mineração** , selecione o modelo de mineração que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="aedac-119">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="aedac-120">Selecione a guia apropriada, como a guia **Rede de Dependência** e, em seguida, aplique mais ou menos zoom para exibir o modelo no nível desejado.</span><span class="sxs-lookup"><span data-stu-id="aedac-120">Select the appropriate tab, such as the **Dependency Network** tab, and then zoom in or out to view the model at the level that you want.</span></span>  
  
3.  <span data-ttu-id="aedac-121">Clique em **Copiar Exibição de Gráfico** na barra de ferramentas da guia selecionada.</span><span class="sxs-lookup"><span data-stu-id="aedac-121">Click **Copy Graph View** on the toolbar of the selected tab.</span></span>  
  
### <a name="to-copy-the-mining-model-content-to-the-clipboard"></a><span data-ttu-id="aedac-122">Para copiar o conteúdo do modelo de mineração para a Área de Transferência</span><span class="sxs-lookup"><span data-stu-id="aedac-122">To copy the mining model content to the Clipboard</span></span>  
  
1.  <span data-ttu-id="aedac-123">Na lista **Modelo de Mineração** na guia **Visualizador do Modelo de Mineração** , selecione o modelo de mineração que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="aedac-123">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="aedac-124">Na lista suspensa **Visualizador** , selecione **Visualizador de Árvore de Conteúdo Genérica da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="aedac-124">From the **Viewer** drop-down list, select **Microsoft Generic Content Tree Viewer**.</span></span>  
  
3.  <span data-ttu-id="aedac-125">No painel **Legenda do Nó (ID Exclusiva)** , clique em um nó.</span><span class="sxs-lookup"><span data-stu-id="aedac-125">In the **Node Caption (Unique ID)** pane, click a node.</span></span>  
  
4.  <span data-ttu-id="aedac-126">Clique com o botão direito do mouse no painel **Detalhes do Nó** e, em seguida, selecione **Selecionar tudo**.</span><span class="sxs-lookup"><span data-stu-id="aedac-126">Right-click the **Node Details** pane and then select **Select All**.</span></span>  
  
5.  <span data-ttu-id="aedac-127">Clique com o botão direito do mouse no painel **Detalhes do Nó** novamente e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="aedac-127">Right-click the **Node Details** pane again and select **Copy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aedac-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aedac-128">See Also</span></span>  
 [<span data-ttu-id="aedac-129">Tarefas e instruções do visualizador do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="aedac-129">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
  
