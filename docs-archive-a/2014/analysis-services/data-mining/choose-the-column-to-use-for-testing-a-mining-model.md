---
title: Escolha a coluna a ser usada para testar um modelo de mineração | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], predictable mining columns
- Mining Accuracy Chart [Analysis Services], columns
- predictable mining columns [Analysis Services]
ms.assetid: c6a8f23a-da21-4f31-9521-99460d624649
author: minewiskan
ms.author: owend
ms.openlocfilehash: 326a7084600695d95d3a132f633041e9abad045b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575462"
---
# <a name="choose-the-column-to-use-for-testing-a-mining-model"></a><span data-ttu-id="54f5e-102">Escolha a coluna para usar para teste em um modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="54f5e-102">Choose the Column to Use for Testing a Mining Model</span></span>
  <span data-ttu-id="54f5e-103">Antes de poder medir a exatidão de um modelo de mineração, você deverá decidir qual resultado deseja avaliar.</span><span class="sxs-lookup"><span data-stu-id="54f5e-103">Before you can measure the accuracy of a mining model, you must decide which outcome it is that you want to assess.</span></span> <span data-ttu-id="54f5e-104">A maioria dos modelos de mineração de dados exige que você escolha pelo menos uma coluna para usar como o atributo previsível ao criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="54f5e-104">Most data mining models require that you choose at least one column to use as the predictable attribute when you create the model.</span></span> <span data-ttu-id="54f5e-105">Portanto, quando você testar a exatidão do modelo, geralmente terá que selecionar esse atributo para testar.</span><span class="sxs-lookup"><span data-stu-id="54f5e-105">Therefore, when you test the accuracy of the model, you generally must select that attribute to test.</span></span>  
  
 <span data-ttu-id="54f5e-106">A lista a seguir descreve algumas considerações adicionais para escolher o atributo previsível para usar no teste:</span><span class="sxs-lookup"><span data-stu-id="54f5e-106">The following list describes some additional considerations for choosing the predictable attribute to use in testing:</span></span>  
  
-   <span data-ttu-id="54f5e-107">Alguns tipos de modelos de Data Mining podem prever vários atributos, como redes neurais, que podem explorar as relações entre muitos atributos.</span><span class="sxs-lookup"><span data-stu-id="54f5e-107">Some types of data mining models can predict multiple attributes-such as neural networks, which can explore the relationships between many attributes.</span></span>  
  
-   <span data-ttu-id="54f5e-108">Outros tipos de modelos de mineração, como modelos de clustering, não necessariamente têm um atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="54f5e-108">Other types of mining models-such as clustering models-do not necessarily have a predictable attribute.</span></span> <span data-ttu-id="54f5e-109">Os modelos de clustering não podem ser testados a menos que tenham um atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="54f5e-109">Clustering models cannot be tested unless they have a predictable attribute.</span></span>  
  
-   <span data-ttu-id="54f5e-110">Criar um gráfico de dispersão ou medir a exatidão de um modelo de regressão exige que você escolha um atributo previsível contínuo como o resultado.</span><span class="sxs-lookup"><span data-stu-id="54f5e-110">To create a scatter plot or measure the accuracy of a regression model requires that you choose a continuous predictable attribute as the outcome.</span></span> <span data-ttu-id="54f5e-111">Nesse caso, você não pode especificar um valor de destino.</span><span class="sxs-lookup"><span data-stu-id="54f5e-111">In that case, you cannot specify a target value.</span></span> <span data-ttu-id="54f5e-112">Se você estiver criando algo diferente de um gráfico de dispersão, a coluna da estrutura de mineração subjacente também terá que ter um tipo de conteúdo **Discreto** ou **Discretizado**.</span><span class="sxs-lookup"><span data-stu-id="54f5e-112">If you are creating anything other than a scatter plot, the underlying mining structure column must also have a content type of **Discrete** or **Discretized**.</span></span>  
  
-   <span data-ttu-id="54f5e-113">Se você escolher um atributo discreto como o resultado previsível, também poderá especificar um valor de destino ou pode deixar em branco o campo **Valor de Previsão** .</span><span class="sxs-lookup"><span data-stu-id="54f5e-113">If you choose a discrete attribute as the predictable outcome, you can also specify a target value, or you can leave the **Predict Value** field blank.</span></span> <span data-ttu-id="54f5e-114">Se você incluir um **valor de previsão**, o gráfico medirá apenas a eficácia do modelo ao prever o valor de destino.</span><span class="sxs-lookup"><span data-stu-id="54f5e-114">If you include a **Predict Value**, the chart will measure only the model's effectiveness at predicting the target value.</span></span> <span data-ttu-id="54f5e-115">Se você não especificar um resultado de destino, o modelo será medido para sua exatidão em prever todos os resultados.</span><span class="sxs-lookup"><span data-stu-id="54f5e-115">If you do not specify a target outcome, the model is measured for its accuracy in predicting all outcomes.</span></span>  
  
-   <span data-ttu-id="54f5e-116">Se você quiser incluir diversos modelos e compará-los em um único gráfico de precisão, todos os modelos deverão usar a mesma coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="54f5e-116">If you want to include multiple models and compare them in a single accuracy chart, all models must use the same predictable column.</span></span>  
  
-   <span data-ttu-id="54f5e-117">Quando você cria um relatório de validação cruzada, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] automaticamente analisa todos os modelos que têm o mesmo atributo previsível.</span><span class="sxs-lookup"><span data-stu-id="54f5e-117">When you create a cross-validation report, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will automatically analyze all models that have the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="54f5e-118">Quando a opção **Sincronizar Colunas e Valores de Previsão**é selecionada, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] automaticamente escolhe as colunas previsíveis que têm os mesmos nomes e tipos de dados correspondentes.</span><span class="sxs-lookup"><span data-stu-id="54f5e-118">When the option, **Synchronize Prediction columns and Values**, is selected, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] automatically chooses predictable columns that have the same names and matching data types.</span></span> <span data-ttu-id="54f5e-119">Se suas colunas não atenderem a estes critérios, você poderá desativar esta opção e manualmente escolher uma coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="54f5e-119">If your columns do not meet these criteria, you can turn off this option and manually choose a predictable column.</span></span> <span data-ttu-id="54f5e-120">Você pode precisar fazer isto se estiver testando o modelo com um conjunto de dados externo que tem colunas diferentes do modelo.</span><span class="sxs-lookup"><span data-stu-id="54f5e-120">You might need to do this if you are testing the model with an external data set that has different columns than the model.</span></span> <span data-ttu-id="54f5e-121">Porém, se você escolher uma coluna com o tipo de dados incorreto, obterá um erro ou resultados incorretos.</span><span class="sxs-lookup"><span data-stu-id="54f5e-121">However, if you choose a column with the wrong the type of data you will either get an error or bad results.</span></span>  
  
### <a name="specify-the-outcome-to-predict"></a><span data-ttu-id="54f5e-122">Especifique o resultado para prever</span><span class="sxs-lookup"><span data-stu-id="54f5e-122">Specify the outcome to predict</span></span>  
  
1.  <span data-ttu-id="54f5e-123">Clique duas vezes na estrutura de mineração para abri-la no Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="54f5e-123">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="54f5e-124">Selecione a guia **Gráfico de Precisão de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="54f5e-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="54f5e-125">Selecione a guia **Seleção de Entrada** .</span><span class="sxs-lookup"><span data-stu-id="54f5e-125">Select the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="54f5e-126">Na guia **Seleção de Entrada** , em **Nome da Coluna Previsível**, selecione uma coluna previsível para cada modelo que você incluir no gráfico.</span><span class="sxs-lookup"><span data-stu-id="54f5e-126">On the **Input Selection** tab, under **Predictable Column Name**, select a predictable column for each model that you include in the chart.</span></span>  
  
     <span data-ttu-id="54f5e-127">As colunas do modelo de mineração disponíveis na caixa **Nome da Coluna Previsível** são somente as que têm o tipo de uso definido como **Previsão** ou **Somente Previsão**.</span><span class="sxs-lookup"><span data-stu-id="54f5e-127">The mining model columns that are available in the **Predictable Column Name** box are only those with the usage type set to **Predict** or **Predict Only**.</span></span>  
  
5.  <span data-ttu-id="54f5e-128">Se quiser determinar o nível de elevação para um modelo, selecione um valor de resultado específico para medir, escolhendo na lista **Valor de Previsão** .</span><span class="sxs-lookup"><span data-stu-id="54f5e-128">If you want to determine the lift for a model, you must select a specific outcome value to measure, for by choosing from the **Predict Value** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f5e-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54f5e-129">See Also</span></span>  
 <span data-ttu-id="54f5e-130">[Escolher e mapear dados de teste de modelo](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="54f5e-130">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="54f5e-131">Escolher um tipo de gráfico de precisão e definir opções de gráfico</span><span class="sxs-lookup"><span data-stu-id="54f5e-131">Choose an Accuracy Chart Type and Set Chart Options</span></span>](choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  
