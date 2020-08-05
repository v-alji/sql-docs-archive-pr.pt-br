---
title: Gráfico de ganho (SQL Server suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- accuracy chart
- profit chart
- mining models, charting
- mining models, testing
ms.assetid: 5c902543-4da9-4db3-99d5-4ce04c43d7ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 030e511047b816543c12c81bdab307e599bbc5d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574301"
---
# <a name="profit-chart-sql-server-data-mining-add-ins"></a><span data-ttu-id="022b1-102">Gráfico de Ganho (Suplementos de Mineração de Dados do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="022b1-102">Profit Chart (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="022b1-103">![Botão Gráfico de Ganho na faixa de opções Mineração de Dados](media/dmc-profitchart.gif "Botão Gráfico de Ganho na faixa de opções Mineração de Dados")</span><span class="sxs-lookup"><span data-stu-id="022b1-103">![Profit Chart button in Data Mining ribbon](media/dmc-profitchart.gif "Profit Chart button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="022b1-104">Um gráfico de ganho exibe o aumento estimado de lucro associado ao uso de um modelo de mineração para determinar quais clientes uma empresa deve contatar em um cenário comercial.</span><span class="sxs-lookup"><span data-stu-id="022b1-104">A profit chart displays the estimated profit increase that is associated with using a mining model to determine which customers a company should contact in a business scenario.</span></span> <span data-ttu-id="022b1-105">O eixo Y do gráfico representa o ganho, enquanto que o eixo X representa a porcentagem da população que a empresa contatou.</span><span class="sxs-lookup"><span data-stu-id="022b1-105">The Y-axis of the chart represents the profit, while the X-axis represents the percentage of the population that the company contacted.</span></span> <span data-ttu-id="022b1-106">Um gráfico de ganho típico mostra um aumento nos lucros até certo ponto; depois disso, os lucros diminuem à medida que mais pessoas são contatadas.</span><span class="sxs-lookup"><span data-stu-id="022b1-106">A typical profit chart shows an increase in profits up to a point, after which profits decrease as more of the population is contacted.</span></span>  
  
## <a name="configuring-the-profit-chart"></a><span data-ttu-id="022b1-107">Configurando o gráfico de ganho</span><span class="sxs-lookup"><span data-stu-id="022b1-107">Configuring the Profit Chart</span></span>  
 <span data-ttu-id="022b1-108">Enquanto o gráfico de precisão avalia apenas a probabilidade de as previsões estarem certas ou erradas, o gráfico de ganho incorpora conhecimentos reais sobre as consequências de executar uma ação em uma previsão.</span><span class="sxs-lookup"><span data-stu-id="022b1-108">Whereas the accuracy chart assesses only the probability that predictions are right or wrong, the profit chart incorporates real-world knowledge about the consequences of taking action on a prediction.</span></span> <span data-ttu-id="022b1-109">Isso é obtido considerando-se os seguintes fatores, que você especifica ao executar o assistente:</span><span class="sxs-lookup"><span data-stu-id="022b1-109">This is achieved by taking into account the following factors, which you specify when you run the wizard:</span></span>  
  
-   <span data-ttu-id="022b1-110">**Média**</span><span class="sxs-lookup"><span data-stu-id="022b1-110">**Population**</span></span>  
  
     <span data-ttu-id="022b1-111">O número de casos no conjunto de dados que está sendo usado para criar o gráfico de comparação de precisão.</span><span class="sxs-lookup"><span data-stu-id="022b1-111">The number of cases in the dataset that is being used to create the lift chart.</span></span> <span data-ttu-id="022b1-112">Por exemplo, o número de clientes em potencial.</span><span class="sxs-lookup"><span data-stu-id="022b1-112">For example, the number of potential customers.</span></span>  
  
-   <span data-ttu-id="022b1-113">**Custo fixo**</span><span class="sxs-lookup"><span data-stu-id="022b1-113">**Fixed Cost**</span></span>  
  
     <span data-ttu-id="022b1-114">O custo fixo associado ao problema empresarial.</span><span class="sxs-lookup"><span data-stu-id="022b1-114">The fixed cost that is associated with the business problem.</span></span> <span data-ttu-id="022b1-115">Caso seja destinado a uma solução de correspondência de destino, o custo não poderá depender de variáveis como o número de chamadas telefônicas feitas ou o número de correspondências promocionais enviadas.</span><span class="sxs-lookup"><span data-stu-id="022b1-115">If this were for a targeted mailing solution, the cost would not depend on variables such as the number of telephone calls made or the number of promotional mailings sent.</span></span>  
  
-   <span data-ttu-id="022b1-116">**Custo individual**</span><span class="sxs-lookup"><span data-stu-id="022b1-116">**Individual Cost**</span></span>  
  
     <span data-ttu-id="022b1-117">Os custos adicionais ao custo fixo, que podem estar associados a cada contato de cliente.</span><span class="sxs-lookup"><span data-stu-id="022b1-117">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="022b1-118">Por exemplo, correspondências promocionais ou chamadas telefônicas.</span><span class="sxs-lookup"><span data-stu-id="022b1-118">For example, promotional mailings or telephone calls.</span></span>  
  
-   <span data-ttu-id="022b1-119">**Receita por indivíduo**</span><span class="sxs-lookup"><span data-stu-id="022b1-119">**Revenue Per Individual**</span></span>  
  
     <span data-ttu-id="022b1-120">A receita associada a cada venda bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="022b1-120">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="using-the-profit-chart-wizard"></a><span data-ttu-id="022b1-121">Usando o Assistente de Gráfico de Ganho</span><span class="sxs-lookup"><span data-stu-id="022b1-121">Using the Profit Chart Wizard</span></span>  
 <span data-ttu-id="022b1-122">Para criar um gráfico de ganho, você deve referenciar um modelo de mineração de dados existente.</span><span class="sxs-lookup"><span data-stu-id="022b1-122">To create a profit chart, you must reference an existing data mining model.</span></span> <span data-ttu-id="022b1-123">Você pode procurar modelos para encontrar um modelo que corresponda aos seus dados clicando em **gerenciar modelos** ou **procurar** para ver detalhes sobre o algoritmo que foi usado e as colunas no modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="022b1-123">You can browse models to find a model that matches your data by clicking **Manage Models** or **Browse** to see details about the algorithm that was used and the columns in the mining model.</span></span>  
  
 <span data-ttu-id="022b1-124">Para obter mais informações, consulte [procurando modelos no Excel &#40;SQL Server suplementos de mineração de dados&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) e [gerenciar modelos &#40;SQL Server suplementos de mineração de dados&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="022b1-124">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) and [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
#### <a name="to-create-a-profit-chart"></a><span data-ttu-id="022b1-125">Para criar um gráfico de ganho</span><span class="sxs-lookup"><span data-stu-id="022b1-125">To create a profit chart</span></span>  
  
1.  <span data-ttu-id="022b1-126">Selecione um modelo existente.</span><span class="sxs-lookup"><span data-stu-id="022b1-126">Select an existing model.</span></span>  
  
2.  <span data-ttu-id="022b1-127">Especifique a coluna que você deseja prever e um valor de destino, se apropriado.</span><span class="sxs-lookup"><span data-stu-id="022b1-127">Specify the column that you want to predict, and a target value, if appropriate.</span></span>  
  
3.  <span data-ttu-id="022b1-128">Selecione os dados de origem, o que significa que os dados passarão pelo modelo para criar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="022b1-128">Select the source data, which means the data you will pass through the model in order to create a prediction.</span></span> <span data-ttu-id="022b1-129">Esses não devem ser os mesmos dados usados para criação do modelo.</span><span class="sxs-lookup"><span data-stu-id="022b1-129">This should not be the same data that you used to create the model.</span></span>  
  
4.  <span data-ttu-id="022b1-130">Mapeie as colunas na nova data (origem) para as colunas usadas no modelo de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="022b1-130">Map the columns in the new (source) date to the columns used in the data mining model.</span></span> <span data-ttu-id="022b1-131">Se os nomes das colunas forem semelhantes, eles serão mapeados automaticamente pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="022b1-131">If the column names are similar, the wizard will automatically map them.</span></span>  
  
5.  <span data-ttu-id="022b1-132">Insira as informações de custo necessárias para o assistente: o custo fixo, o custo individual, a população e a receita esperada.</span><span class="sxs-lookup"><span data-stu-id="022b1-132">Enter the cost information required by the wizard: the fixed cost, individual cost, the population, and the revenue expected.</span></span>  
  
6.  <span data-ttu-id="022b1-133">Opcionalmente, você pode inserir uma série de custos graduados (clique no botão procurar **(...)** ).</span><span class="sxs-lookup"><span data-stu-id="022b1-133">Optionally, you can enter a graduated series of costs (click the browse **(...)** button).</span></span> <span data-ttu-id="022b1-134">Por exemplo, talvez uma correspondência fique mais barata à medida que você aumentar o número de itens enviados, para que possa inserir um custo diferente de acordo com o número de itens, e o assistente ajustará automaticamente os custos para cada tamanho de amostra.</span><span class="sxs-lookup"><span data-stu-id="022b1-134">For example, a mailing might become cheaper as you increase the number of items that are sent, so you can enter a different cost depending on the number of items, and the wizard will automatically adjust the costs for each sample size.</span></span>  
  
7.  <span data-ttu-id="022b1-135">O assistente cria um gráfico que contém a análise de custo-benefício do modelo.</span><span class="sxs-lookup"><span data-stu-id="022b1-135">The wizard creates a chart that includes the cost-benefit analysis for the model.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="022b1-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="022b1-136">Requirements</span></span>  
 <span data-ttu-id="022b1-137">Se você estiver prevendo um valor numérico discreto, selecione o valor de destino exato para prever.</span><span class="sxs-lookup"><span data-stu-id="022b1-137">If you are predicting a discrete numeric value, you must select the exact target value to predict.</span></span>  
  
## <a name="understanding-the-profit-chart"></a><span data-ttu-id="022b1-138">Entendendo o gráfico de ganho</span><span class="sxs-lookup"><span data-stu-id="022b1-138">Understanding the Profit Chart</span></span>  
 <span data-ttu-id="022b1-139">O gráfico de ganho contém uma linha vertical cinza, que você pode mover clicando em um local do gráfico.</span><span class="sxs-lookup"><span data-stu-id="022b1-139">The profit chart contains a gray vertical line, which you can move by clicking a location in the chart.</span></span> <span data-ttu-id="022b1-140">A **legenda de mineração** exibe uma pontuação, a população correta e a probabilidade de previsão que estão associadas ao local da linha cinza no gráfico.</span><span class="sxs-lookup"><span data-stu-id="022b1-140">The **Mining Legend** displays a score, the population correct, and the predict probability that are associated with the location of the gray line on the chart.</span></span> <span data-ttu-id="022b1-141">Se você selecionar o ponto máximo de lucros no gráfico usando a linha cinza, utilize o valor de probabilidade de previsão para determinar um limite de probabilidade para contatar um cliente.</span><span class="sxs-lookup"><span data-stu-id="022b1-141">If you select the maximum point of profits in the chart by using the gray line, you can use the predict probability value to determine a probability threshold for contacting a customer.</span></span>  
  
 <span data-ttu-id="022b1-142">Por exemplo, se o ponto máximo da curva de lucro estiver em 55% da população e a probabilidade de previsão associada for 20%, isso indica que para alcançar o máximo de lucro, você só deve contatar os clientes cuja resposta esteja prevista com uma probabilidade de 20% ou mais.</span><span class="sxs-lookup"><span data-stu-id="022b1-142">For example, if the peak of the profit curve is at 55 percent of the population and the associated predict probability is 20 percent, this indicates that to achieve maximum profits you should only contact those customers whose response is predicted with a 20 percent or greater probability.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="022b1-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="022b1-143">See Also</span></span>  
 [<span data-ttu-id="022b1-144">Validando modelos e usando modelos para previsão &#40;suplementos de mineração de dados para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="022b1-144">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
