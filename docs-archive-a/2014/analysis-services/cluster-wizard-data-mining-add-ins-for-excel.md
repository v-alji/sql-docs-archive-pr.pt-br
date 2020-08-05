---
title: Assistente de cluster (suplementos de mineração de dados para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clustering [data mining]
ms.assetid: 85b25625-a7ab-4960-9f9c-df22e8ecae37
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90500ae627bcafd1ca5ce17114dac9df9939691d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571690"
---
# <a name="cluster-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="50bdd-102">Assistente de Cluster (Suplementos de Mineração de Dados para Excel)</span><span class="sxs-lookup"><span data-stu-id="50bdd-102">Cluster Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="50bdd-103">![Assistente de Cluster na faixa de opções Mineração de Dados](media/dmc-cluster.gif "Assistente de Cluster na faixa de opções Mineração de Dados")</span><span class="sxs-lookup"><span data-stu-id="50bdd-103">![Cluster wizard in Data Mining ribbon](media/dmc-cluster.gif "Cluster wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="50bdd-104">O assistente de Cluster ajuda a criar um modelo que detecta as linhas que têm características semelhantes e as agrupa para maximizar a distância entre grupos.</span><span class="sxs-lookup"><span data-stu-id="50bdd-104">The Cluster wizard helps you build a model that detects rows that share similar characteristics and groups them to maximize the distance between groups.</span></span> <span data-ttu-id="50bdd-105">Esse assistente é útil para localizar padrões em todos os tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="50bdd-105">This wizard is useful for finding patterns in all kinds of data.</span></span>  
  
 <span data-ttu-id="50bdd-106">O assistente de Cluster usa o algoritmo do Microsoft Clustering e pode ser extensivamente personalizado.</span><span class="sxs-lookup"><span data-stu-id="50bdd-106">The Cluster wizard uses the Microsoft Clustering algorithm and can be extensively customized.</span></span> <span data-ttu-id="50bdd-107">Ele funciona nos dados existentes de uma tabela do Excel, um intervalo do Excel ou uma consulta do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50bdd-107">It works on existing data from an Excel table, an Excel range, or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] query.</span></span> <span data-ttu-id="50bdd-108">A funcionalidade semelhante é fornecida pela ferramenta [detectar categorias](detect-categories-table-analysis-tools-for-excel.md) , fornecida nas ferramentas de análise de tabela para Excel.</span><span class="sxs-lookup"><span data-stu-id="50bdd-108">Similar functionality is provided by the [Detect Categories](detect-categories-table-analysis-tools-for-excel.md) tool, provided in the Table Analysis Tools for Excel.</span></span> <span data-ttu-id="50bdd-109">No entanto, a ferramenta Detectar Categorias não pode ser personalizada e deve usar dados nas tabelas do Excel.</span><span class="sxs-lookup"><span data-stu-id="50bdd-109">However, the Detect Categories tool cannot be customized and must use data in Excel tables.</span></span>  
  
## <a name="using-the-cluster-wizard"></a><span data-ttu-id="50bdd-110">Usando o assistente de Cluster</span><span class="sxs-lookup"><span data-stu-id="50bdd-110">Using the Cluster Wizard</span></span>  
  
1.  <span data-ttu-id="50bdd-111">Na faixa de de mineração de dados, clique em **cluster**e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="50bdd-111">In the Data Mining ribbon, click **Cluster**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="50bdd-112">Na página **selecionar dados de origem** , selecione uma tabela ou um intervalo do Excel.</span><span class="sxs-lookup"><span data-stu-id="50bdd-112">In the **Select Source Data** page, select an Excel table or range.</span></span> <span data-ttu-id="50bdd-113">Ou especifique uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="50bdd-113">Or specify and external data source.</span></span>  
  
     <span data-ttu-id="50bdd-114">Se você usar uma fonte de dados externa, poderá criar exibições personalizadas ou colar um texto de consulta personalizada e salvar o conjunto de dados como uma fonte de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50bdd-114">If you use an external data source, you can create custom views or paste in custom query text, and save the data set as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="50bdd-115">Na página **clustering** , você pode personalizar a maneira como o modelo é criado.</span><span class="sxs-lookup"><span data-stu-id="50bdd-115">On the **Clustering** page, you can customize the way the model is built.</span></span>  
  
    -   <span data-ttu-id="50bdd-116">Para o **número de segmentos**, você pode instruir o assistente a criar um número fixo de categorias ou permitir que ele detecte automaticamente o número ideal de agrupamentos.</span><span class="sxs-lookup"><span data-stu-id="50bdd-116">For **Number of segments**, you can tell the wizard to create a fixed number of categories, or let it automatically detect the optimum number of groupings.</span></span>  
  
    -   <span data-ttu-id="50bdd-117">Examine a lista de colunas na lista **colunas de entrada** e desmarque as colunas que não são úteis na criação de padrões.</span><span class="sxs-lookup"><span data-stu-id="50bdd-117">Review the list of columns in the **Input columns** list, and deselect any columns that are not useful in creating patterns.</span></span> <span data-ttu-id="50bdd-118">As colunas que você deve excluir incluem números de identificação, nomes de clientes e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="50bdd-118">Columns you should exclude include ID numbers, customer names, and so on.</span></span>  
  
4.  <span data-ttu-id="50bdd-119">Opcionalmente, clique em **parâmetros** para alterar os parâmetros do algoritmo e personalizar o comportamento do modelo de clustering.</span><span class="sxs-lookup"><span data-stu-id="50bdd-119">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="50bdd-120">Na página **dividir os dados em conjuntos de treinamento e teste** , especifique a quantidade de dados a serem retidos para teste.</span><span class="sxs-lookup"><span data-stu-id="50bdd-120">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="50bdd-121">O restante é sempre usado para treinar o modelo.</span><span class="sxs-lookup"><span data-stu-id="50bdd-121">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="50bdd-122">A configuração padrão é de 30% de dados para teste e 70% de dados para treinamento.</span><span class="sxs-lookup"><span data-stu-id="50bdd-122">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="50bdd-123">Na página **concluir** , forneça um nome descritivo para seu conjunto de dados e modelo e defina as seguintes opções que controlam como você trabalha com o modelo concluído:</span><span class="sxs-lookup"><span data-stu-id="50bdd-123">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="50bdd-124">**Procurar modelo**.</span><span class="sxs-lookup"><span data-stu-id="50bdd-124">**Browse model**.</span></span> <span data-ttu-id="50bdd-125">Quando essa opção é selecionada, assim que o assistente termina de processar o modelo, ele abre uma janela de **procura** para ajudá-lo a explorar os resultados.</span><span class="sxs-lookup"><span data-stu-id="50bdd-125">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="50bdd-126">O conteúdo do visualizador depende do tipo de modelo que você criou.</span><span class="sxs-lookup"><span data-stu-id="50bdd-126">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="50bdd-127">Para obter mais informações, consulte [navegando em um modelo de clustering](browsing-a-clustering-model.md).</span><span class="sxs-lookup"><span data-stu-id="50bdd-127">For more information, see [Browsing a Clustering Model](browsing-a-clustering-model.md).</span></span>  
  
    -   <span data-ttu-id="50bdd-128">**Habilitar detalhamento**.</span><span class="sxs-lookup"><span data-stu-id="50bdd-128">**Enable drillthrough**.</span></span> <span data-ttu-id="50bdd-129">Selecione esta opção para visualizar os dados subjacentes do modelo finalizado.</span><span class="sxs-lookup"><span data-stu-id="50bdd-129">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="50bdd-130">Essa opção estará disponível somente se você criar um modelo de Árvore de Decisão.</span><span class="sxs-lookup"><span data-stu-id="50bdd-130">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="50bdd-131">**Use o modelo temporário**.</span><span class="sxs-lookup"><span data-stu-id="50bdd-131">**Use temporary model**.</span></span> <span data-ttu-id="50bdd-132">Se você selecionar esta opção, o modelo não será salvo no servidor.</span><span class="sxs-lookup"><span data-stu-id="50bdd-132">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="50bdd-133">Os modelos temporários serão excluídos quando você fechar o Excel.</span><span class="sxs-lookup"><span data-stu-id="50bdd-133">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-clustering-models"></a><span data-ttu-id="50bdd-134">Mais sobre modelos de clustering</span><span class="sxs-lookup"><span data-stu-id="50bdd-134">More about Clustering Models</span></span>  
 <span data-ttu-id="50bdd-135">Você pode alterar o algoritmo de clustering usado por esse assistente clicando em **avançado** e usando a caixa de diálogo **parâmetros de algoritmo** .</span><span class="sxs-lookup"><span data-stu-id="50bdd-135">You can change the clustering algorithm used by this wizard by clicking **Advanced** and using the **Algorithm Parameters** dialog box.</span></span>  
  
 <span data-ttu-id="50bdd-136">O algoritmo Clustering da Microsoft fornece estes métodos de clustering:</span><span class="sxs-lookup"><span data-stu-id="50bdd-136">The Microsoft Clustering algorithm provides these clustering methods:</span></span>  
  
-   <span data-ttu-id="50bdd-137">K-means - evolutivo ou não evolutivo.</span><span class="sxs-lookup"><span data-stu-id="50bdd-137">K-means -  scalable or non-scaling.</span></span>  
  
-   <span data-ttu-id="50bdd-138">Maximização de Expectativa (EM) - evolutiva ou não evolutiva.</span><span class="sxs-lookup"><span data-stu-id="50bdd-138">Expectation Maximization (EM) - scalable or non-scaling.</span></span>  
  
 <span data-ttu-id="50bdd-139">Você também pode usar o parâmetro CLUSTER_SEED para controlar o valor inicial e garantir que os modelos repetidos que usam o mesmo conjunto de dados tenham os mesmos resultados.</span><span class="sxs-lookup"><span data-stu-id="50bdd-139">You can also use the CLUSTER_SEED parameter to control the starting value and ensure that repeated models using the same data set have the same results.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="50bdd-140">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50bdd-140">Requirements</span></span>  
 <span data-ttu-id="50bdd-141">Para usar o assistente de Cluster, você deve estar conectado a um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50bdd-141">To use the Cluster wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="50bdd-142">Para obter mais informações, consulte [conectar-se a dados de origem &#40;cliente de mineração de dados para Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="50bdd-142">For more information, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50bdd-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="50bdd-143">See Also</span></span>  
 <span data-ttu-id="50bdd-144">[Criando um modelo de mineração de dados](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="50bdd-144">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="50bdd-145">Detectar categorias &#40;ferramentas de análise de tabela para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="50bdd-145">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
  
