---
title: Modificando a estrutura de previsão (tutorial de mineração de dados intermediário) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1a6c138e-643b-4ae6-ad08-93631f149c20
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 9acf410fe04c53493e559257832e5e21727bc45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568964"
---
# <a name="modifying-the-forecasting-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="36834-102">Modificando a estrutura de previsão (Tutorial de mineração de dados intermediário)</span><span class="sxs-lookup"><span data-stu-id="36834-102">Modifying the Forecasting Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="36834-103">A estrutura de mineração criada na tarefa anterior contém um modelo de previsão único.</span><span class="sxs-lookup"><span data-stu-id="36834-103">The mining structure that you created in the previous task contains a single forecasting model.</span></span> <span data-ttu-id="36834-104">Antes de processar e explorar o modelo, você deve alterar sua estrutura ligeiramente e modificar uma de suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="36834-104">Before you process and explore the model, you must change its structure slightly and modify one of its properties.</span></span>  
  
## <a name="modifying-the-mining-structure"></a><span data-ttu-id="36834-105">Modificando a estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="36834-105">Modifying the Mining Structure</span></span>  
 <span data-ttu-id="36834-106">Você pode alterar a estrutura de mineração usando a guia **estrutura de mineração** do designer de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="36834-106">You can change the mining structure by using the **Mining Structure** tab of Data Mining Designer.</span></span> <span data-ttu-id="36834-107">Ao criar o modelo com o Assistente de Mineração de Dados, você usou três colunas: ReportingDate, ModelRegion e Quantidade.</span><span class="sxs-lookup"><span data-stu-id="36834-107">When you created the model with the Data Mining Wizard, you used three columns: ReportingDate, ModelRegion, and Quantity.</span></span> <span data-ttu-id="36834-108">No entanto, a tabela de **previsão** também contém uma coluna de valor, que pode ser usada para prever a quantidade de vendas.</span><span class="sxs-lookup"><span data-stu-id="36834-108">However, the **Forecasting** table also contains an Amount column, which you can use to forecast the amount of sales.</span></span> <span data-ttu-id="36834-109">Usando a guia **estrutura de mineração** , você pode adicionar essa coluna da exibição da fonte de dados à estrutura de mineração.</span><span class="sxs-lookup"><span data-stu-id="36834-109">By using the **Mining Structure** tab, you can add this column from the data source view to the mining structure.</span></span>  
  
#### <a name="to-add-the-amount-column-to-the-forecasting-mining-structure"></a><span data-ttu-id="36834-110">Para adicionar a coluna Valor à estrutura de mineração de previsão</span><span class="sxs-lookup"><span data-stu-id="36834-110">To add the Amount column to the Forecasting mining structure</span></span>  
  
1.  <span data-ttu-id="36834-111">Na guia **estrutura de mineração** do designer de data mining, no painel **exibição da fonte de dados** , selecione a coluna valor na tabela vTimeSeries.</span><span class="sxs-lookup"><span data-stu-id="36834-111">On the **Mining Structure** tab of Data Mining Designer, in the **Data Source View** pane, select the Amount column in the vTimeSeries table.</span></span>  
  
2.  <span data-ttu-id="36834-112">Arraste a coluna valor do painel **exibição da fonte de dados** para a lista de colunas da estrutura de **previsão** .</span><span class="sxs-lookup"><span data-stu-id="36834-112">Drag the Amount column from the **Data Source View** pane into the list of columns for the **Forecasting** structure.</span></span>  
  
     <span data-ttu-id="36834-113">A coluna de valor agora está incluída na estrutura de mineração de **previsão** .</span><span class="sxs-lookup"><span data-stu-id="36834-113">The Amount column is now included in the **Forecasting** mining structure.</span></span>  
  
## <a name="modifying-the-columns-in-the-mining-model"></a><span data-ttu-id="36834-114">Modificando as colunas do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="36834-114">Modifying the Columns in the Mining Model</span></span>  
 <span data-ttu-id="36834-115">Como você adicionou uma nova coluna à estrutura, é preciso definir como o modelo a usará.</span><span class="sxs-lookup"><span data-stu-id="36834-115">Because you added a new column to the structure, you must define how the model will use the column.</span></span> <span data-ttu-id="36834-116">Você pode especificar como a coluna será usada na guia **modelos de mineração** do designer de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="36834-116">You can specify how the column will be used on the **Mining Models** tab of Data Mining Designer.</span></span>  
  
 <span data-ttu-id="36834-117">A guia **modelos de mineração** lista as colunas que a estrutura de mineração contém na coluna **estrutura** da grade e lista as colunas que o modelo de mineração contém na coluna que tem o nome do modelo, neste caso, **previsão**.</span><span class="sxs-lookup"><span data-stu-id="36834-117">The **Mining Models** tab lists the columns that the mining structure contains in the **Structure** column of the grid, and lists the columns that the mining model contains in the column that has the name of the model, in this case **Forecasting**.</span></span> <span data-ttu-id="36834-118">Clique nos nomes das colunas para fazer modificações.</span><span class="sxs-lookup"><span data-stu-id="36834-118">Click the names of the columns to make modifications.</span></span> <span data-ttu-id="36834-119">No modelo de mineração de **previsão** , a coluna valor é usada como uma coluna de entrada e também é usada para prever vendas futuras.</span><span class="sxs-lookup"><span data-stu-id="36834-119">In the **Forecasting** mining model, the Amount column is used as an input column and is also used to forecast future sales.</span></span> <span data-ttu-id="36834-120">Portanto, é preciso definir as propriedades da coluna de forma que ela possa ser usada como uma coluna de entrada e uma coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="36834-120">Therefore, you must set the properties of the column so that it can be used as both an input column and a predictable column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36834-121">Na guia **modelos de mineração** , você também pode criar novos modelos com base na mesma estrutura e pode ajustar as propriedades de algoritmo e coluna para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="36834-121">In the **Mining Models** tab, you can also create new models based on the same structure, and you can adjust the algorithm and column properties for each model.</span></span> <span data-ttu-id="36834-122">No entanto, você deverá processar o modelo antes que essas alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="36834-122">However, you must process the model before these changes take effect.</span></span>  
  
#### <a name="to-define-how-the-amount-column-will-be-used"></a><span data-ttu-id="36834-123">Para definir a coluna Valor que será usada</span><span class="sxs-lookup"><span data-stu-id="36834-123">To define how the Amount column will be used</span></span>  
  
1.  <span data-ttu-id="36834-124">Na coluna **previsão** da grade na guia **modelos de mineração** , clique na célula da linha valor.</span><span class="sxs-lookup"><span data-stu-id="36834-124">In the **Forecasting** column of the grid on the **Mining Models** tab, click the cell in the Amount row.</span></span>  
  
2.  <span data-ttu-id="36834-125">Selecione **prever** na lista.</span><span class="sxs-lookup"><span data-stu-id="36834-125">Select **Predict** from the list.</span></span>  
  
     <span data-ttu-id="36834-126">Agora, a coluna Valor passa a ser uma coluna de entrada e uma coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="36834-126">The Amount column is now both an input column and a predictable column.</span></span>  
  
 <span data-ttu-id="36834-127">Você também pode alterar as propriedades de colunas individuais selecionando a coluna e abrindo a janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="36834-127">You can also change the properties of individual columns by selecting the column and opening the **Properties** window.</span></span> <span data-ttu-id="36834-128">Para abrir a janela **Propriedades** , clique com o botão direito do mouse no nome da coluna e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="36834-128">To open the **Properties** window, right-click the column name, and then select **Properties**.</span></span> <span data-ttu-id="36834-129">Se você alterar uma propriedade dentro da coluna de um modelo individual, só será possível alterar as propriedades deste modelo.</span><span class="sxs-lookup"><span data-stu-id="36834-129">If you change a property within the column for an individual model, you can change the properties only for that model.</span></span> <span data-ttu-id="36834-130">No entanto, quando você altera uma propriedade dentro da coluna de **estrutura** , a alteração afeta todos os modelos associados à estrutura.</span><span class="sxs-lookup"><span data-stu-id="36834-130">However, when you change a property within the **Structure** column, the change affects every model that is associated with the structure.</span></span> <span data-ttu-id="36834-131">Sempre que você fizer alterações no modelo ou na estrutura, deverá processá-los novamente para ver os efeitos.</span><span class="sxs-lookup"><span data-stu-id="36834-131">Whenever you make changes to the model or structure, you must reprocess to see the effects.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="36834-132">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="36834-132">Next Task in Lesson</span></span>  
 [<span data-ttu-id="36834-133">Personalizando e processando o modelo de previsão &#40;tutorial de mineração de dados intermediário&#41;</span><span class="sxs-lookup"><span data-stu-id="36834-133">Customizing and Processing the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/customize-process-forecasting-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="36834-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="36834-134">See Also</span></span>  
 <span data-ttu-id="36834-135">[Estruturas de mineração &#40;Analysis Services de mineração de dados&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="36834-135">[Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="36834-136">Modelos de mineração &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="36834-136">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-models-analysis-services-data-mining.md)  
  
  