---
title: Procurando modelos no Excel (SQL Server suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- browse models
- mining models, viewing
ms.assetid: a8cca1d7-602a-449a-875c-99da564965bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: c992f1f61112478a85276b6596da0137ccd5c9be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571099"
---
# <a name="browsing-models-in-excel-sql-server-data-mining-add-ins"></a><span data-ttu-id="50c98-102">Procurando modelos no Excel (Suplementos de Mineração de Dados do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="50c98-102">Browsing Models in Excel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="50c98-103">![Botão Procurar Modelo na faixa de opções Mineração de Dados](media/dmc-browse.gif "Botão Procurar Modelo na faixa de opções Mineração de Dados")</span><span class="sxs-lookup"><span data-stu-id="50c98-103">![Browse Model button in Data Mining ribbon](media/dmc-browse.gif "Browse Model button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="50c98-104">Explorar o modelo visualmente é geralmente a maneira mais rápida e fácil de entender as regras e as relações encontradas pela análise.</span><span class="sxs-lookup"><span data-stu-id="50c98-104">Visually exploring the model is usually the fastest and easiest way to get an understanding of the rules and relationships discovered by analysis.</span></span> <span data-ttu-id="50c98-105">Ao usar o Cliente de Mineração de Dados para Excel, você poderá procurar os modelos temporários criados durante a sessão atual do excel e os modelos armazenados em uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50c98-105">By using the Data Mining Client for Excel, you can browse both temporary models created during the current Excel session, and models stored in an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="50c98-106">Para procurar um modelo, você seleciona um modelo e sua estrutura associada em uma lista de modelos disponíveis, e o suplemento escolhe automaticamente o visualizador apropriado para esse algoritmo de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="50c98-106">To browse a model, you select a model and its associated structure from a list of available models, and the add-in automatically picks the viewer that is appropriate for that data mining algorithm.</span></span> <span data-ttu-id="50c98-107">Você pode analisar as tendências mais interessantes, filtrar o modelo de mineração de dados completo e copiar gráficos e dados para o Excel ou o Visio.</span><span class="sxs-lookup"><span data-stu-id="50c98-107">You can drill into the most interesting trends, filter the completed data mining model, and copy graphs and data to Excel or to Visio.</span></span>  
  
## <a name="using-the-browse-model-wizard"></a><span data-ttu-id="50c98-108">Usando o assistente para Procurar Modelo</span><span class="sxs-lookup"><span data-stu-id="50c98-108">Using the Browse Model Wizard</span></span>  
  
1.  <span data-ttu-id="50c98-109">Clique na guia **mineração de dados** .</span><span class="sxs-lookup"><span data-stu-id="50c98-109">Click the **Data Mining** tab.</span></span>  
  
2.  <span data-ttu-id="50c98-110">No grupo **uso do modelo** , clique em **procurar**.</span><span class="sxs-lookup"><span data-stu-id="50c98-110">In the **Model Usage** group, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="50c98-111">Na caixa de diálogo **selecionar modelo** , escolha um modelo de mineração na lista e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="50c98-111">In the **Select Model** dialog box, choose a mining model from the list, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="50c98-112">O assistente abre uma janela de **procura** apropriada para o tipo de modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="50c98-112">The wizard opens a **Browse** window that is appropriate for the type of model that you selected.</span></span>  
  
## <a name="list-of-data-mining-viewers"></a><span data-ttu-id="50c98-113">Lista de visualizadores de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="50c98-113">List of Data Mining Viewers</span></span>  
 <span data-ttu-id="50c98-114">Dependendo do algoritmo de Data Mining que você usou quando criou o modelo, a janela de **procura** parecerá um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="50c98-114">Depending on the data mining algorithm that you used when you created the model, the **Browse** window will look a bit different.</span></span> <span data-ttu-id="50c98-115">Pode incluir gráficos para ajudar a interpretar os resultados, as legendas que contêm detalhes adicionais e os controles para interagir com os dados.</span><span class="sxs-lookup"><span data-stu-id="50c98-115">It can include graphs to help interpret the results, legends that contain additional detail, and controls for interacting with the data.</span></span>  
  
 <span data-ttu-id="50c98-116">Os tópicos a seguir fornecem diretrizes sobre como usar cada visualizador, incluindo dicas sobre a interpretação de gráficos complexos e como alterar, copiar ou trabalhar com os resultados.</span><span class="sxs-lookup"><span data-stu-id="50c98-116">The following topics provide guidance in how to use each of the viewers, including tips on interpreting the complex graphs, and how to change, copy, or work with the results.</span></span>  
  
 [<span data-ttu-id="50c98-117">Procurando um modelo de regras de associação</span><span class="sxs-lookup"><span data-stu-id="50c98-117">Browsing an Association Rules Model</span></span>](browsing-an-association-rules-model.md)  
  
 [<span data-ttu-id="50c98-118">Procurando um modelo de clustering</span><span class="sxs-lookup"><span data-stu-id="50c98-118">Browsing a Clustering Model</span></span>](browsing-a-clustering-model.md)  
  
 [<span data-ttu-id="50c98-119">Procurando um modelo de árvores de decisão</span><span class="sxs-lookup"><span data-stu-id="50c98-119">Browsing a Decision Trees Model</span></span>](browsing-a-decision-trees-model.md)  
  
 [<span data-ttu-id="50c98-120">Procurando um modelo de previsão</span><span class="sxs-lookup"><span data-stu-id="50c98-120">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
 [<span data-ttu-id="50c98-121">Procurando um modelo Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="50c98-121">Browsing a Naive Bayes Model</span></span>](browsing-a-naive-bayes-model.md)  
  
 [<span data-ttu-id="50c98-122">Procurando um modelo de rede neural</span><span class="sxs-lookup"><span data-stu-id="50c98-122">Browsing a Neural Network Model</span></span>](browsing-a-neural-network-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="50c98-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="50c98-123">See Also</span></span>  
 <span data-ttu-id="50c98-124">[Exibindo modelos de mineração de dados no Visio &#40;suplementos de mineração de dados&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="50c98-124">[Viewing Data Mining Models in Visio &#40;Data Mining Add-ins&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="50c98-125">Gerenciar modelos &#40;SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="50c98-125">Manage Models &#40;SQL Server Data Mining Add-ins&#41;</span></span>](manage-models-sql-server-data-mining-add-ins.md)  
  
  
