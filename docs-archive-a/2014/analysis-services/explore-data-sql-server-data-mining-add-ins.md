---
title: Explorar dados (SQL Server suplementos de mineração de dados) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- histogram [data mining]
- data visualization
ms.assetid: 714845a9-4c27-461a-9ba3-149e1e818386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2572c11e92dcf99dfa3adf661603e8f65f05116e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681895"
---
# <a name="explore-data-sql-server-data-mining-add-ins"></a><span data-ttu-id="2f3bc-102">Explorar dados (Suplementos de Mineração de Dados do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2f3bc-102">Explore Data (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="2f3bc-103">![Assistente para Explorar Dados](media/dmc-explore.gif "Assistente para Explorar Dados")</span><span class="sxs-lookup"><span data-stu-id="2f3bc-103">![Explore Data wizard](media/dmc-explore.gif "Explore Data wizard")</span></span>  
  
 <span data-ttu-id="2f3bc-104">O assistente para **explorar dados** ajuda você a entender o tipo e a quantidade de dados em sua tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-104">The **Explore Data** wizard helps you understand the type and amount of data in your data table.</span></span> <span data-ttu-id="2f3bc-105">O assistente representa graficamente a distribuição e os valores das colunas selecionadas, uma coluna por vez.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-105">The wizard graphs the distribution and values for the selected columns, one column at a time.</span></span> <span data-ttu-id="2f3bc-106">Assim, você pode fazer experiências alterando a maneira como os dados são agrupados ou copiar um gráfico que mostra o conteúdo de uma pasta de trabalho do Excel para análise.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-106">You can then experiment with changing the way that data is grouped, or copy the chart that shows the content to an Excel workbook for review.</span></span>  
  
 <span data-ttu-id="2f3bc-107">Se seus dados contiverem dados numéricos contínuos, você poderá ativar /desativar entre essas duas exibições:</span><span class="sxs-lookup"><span data-stu-id="2f3bc-107">If your data contains continuous numeric data, you can toggle between these two views:</span></span>  
  
-   <span data-ttu-id="2f3bc-108">**Gráfico de linhas.**</span><span class="sxs-lookup"><span data-stu-id="2f3bc-108">**Line graph.**</span></span> <span data-ttu-id="2f3bc-109">Esse gráfico de linha coloca os valores de dados no eixo X e o número de casos no eixo Y.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-109">This graph charts the data values on the X-axis and the number of cases on the y-axis.</span></span>  
  
-   <span data-ttu-id="2f3bc-110">**Gráfico de barras.**</span><span class="sxs-lookup"><span data-stu-id="2f3bc-110">**Bar chart.**</span></span> <span data-ttu-id="2f3bc-111">Esse gráfico agrupa os valores pelo número de casos para cada valor.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-111">This graph groups values by the number of cases for each value.</span></span>  
  
 <span data-ttu-id="2f3bc-112">Quando o assistente encontra grupos nos dados, ele usa a distribuição real dos valores de dados.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-112">When the wizard finds groups in the data, it uses the actual distribution of data values.</span></span> <span data-ttu-id="2f3bc-113">Portanto, o gráfico de barras não mostra marcadores de eixo numérico de número inteiro típicos, como 10 ou 100.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-113">Therefore, the bar chart does not show typical whole-number numeric axis markers such as 10 or 100.</span></span> <span data-ttu-id="2f3bc-114">Em vez disso, os intervalos mostrados no gráfico de barras podem ser algo como 43521-55603 (para a coluna de renda).</span><span class="sxs-lookup"><span data-stu-id="2f3bc-114">Instead, the ranges shown in the bar chart might be something like 43521-55603 (for the Income column).</span></span>  
  
 <span data-ttu-id="2f3bc-115">Se você quiser agrupar os dados em outros intervalos, faça isso no Excel antes de analisar os dados.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-115">If you want to group your data into other ranges, you should do this in Excel before analyzing the data.</span></span> <span data-ttu-id="2f3bc-116">Ou, você pode rerotular os dados usando o assistente de [rerotulação](relabel-sql-server-data-mining-add-ins.md) .</span><span class="sxs-lookup"><span data-stu-id="2f3bc-116">Or, you can relabel the data by using the [Relabel](relabel-sql-server-data-mining-add-ins.md) wizard.</span></span>  
  
## <a name="using-the-explore-data-wizard"></a><span data-ttu-id="2f3bc-117">Usando o Assistente para Explorar Dados</span><span class="sxs-lookup"><span data-stu-id="2f3bc-117">Using the Explore Data Wizard</span></span>  
  
1.  <span data-ttu-id="2f3bc-118">Na faixa de faixas de **mineração de dados** , clique em **explorar dados**.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-118">In the **Data Mining** ribbon, click **Explore Data**.</span></span>  
  
2.  <span data-ttu-id="2f3bc-119">Na caixa de diálogo **selecionar origem** , selecione a tabela ou o intervalo de células que contém os dados.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-119">In the **Select Source** dialog box, select the table or range of cells that contains your data.</span></span>  
  
3.  <span data-ttu-id="2f3bc-120">Na caixa de diálogo **Selecionar coluna** , escolha a coluna a ser analisada, dos dados de exemplo exibidos no painel.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-120">In the **Select Column** dialog box, choose the column to analyze, from the sample data displayed in the pane.</span></span>  
  
4.  <span data-ttu-id="2f3bc-121">Na caixa de diálogo **explorar dados** , escolha os tipos de gráfico para exibir a distribuição de dados.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-121">In the **Explore Data** dialog box, choose the chart types for displaying the distribution of data.</span></span>  
  
5.  <span data-ttu-id="2f3bc-122">Se desejar, adicione novas colunas aos dados, altere a segmentação dos dados ou copie o gráfico para o Excel.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-122">Optionally, you can add new columns to the data, change the way that the data is segmented, or copy the chart to Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="2f3bc-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f3bc-123">Requirements</span></span>  
 <span data-ttu-id="2f3bc-124">Para usar o assistente para **explorar dados** , seus dados devem estar em uma tabela de dados do Excel.</span><span class="sxs-lookup"><span data-stu-id="2f3bc-124">To use the **Explore Data** wizard, your data must be in an Excel data table.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="2f3bc-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f3bc-125">See Also</span></span>  
 [<span data-ttu-id="2f3bc-126">Lista de verificação de preparação para mineração de dados</span><span class="sxs-lookup"><span data-stu-id="2f3bc-126">Checklist of Preparation for Data Mining</span></span>](checklist-of-preparation-for-data-mining.md)  
  
  
