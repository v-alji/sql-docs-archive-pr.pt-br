---
title: Criar uma consulta singleton no designer de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton queries [Analysis Services]
- Mining Model Prediction [Analysis Services], singleton queries
ms.assetid: 6cdca8a0-cf16-46eb-a652-0bff820625ab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07491924dbcf0bd35d049e6a7c290d49becfb45d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570336"
---
# <a name="create-a-singleton-query-in-the-data-mining-designer"></a><span data-ttu-id="1cd55-102">Criar uma consulta Singleton no Designer de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="1cd55-102">Create a Singleton Query in the Data Mining Designer</span></span>
  <span data-ttu-id="1cd55-103">Uma consulta singleton será útil se você quiser criar uma previsão para um único caso.</span><span class="sxs-lookup"><span data-stu-id="1cd55-103">A singleton query is useful if you want to create a prediction for a single case.</span></span> <span data-ttu-id="1cd55-104">Para obter mais informações sobre as consultas singleton, veja [Consultas de mineração de dados](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1cd55-104">For more information about singleton queries, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
 <span data-ttu-id="1cd55-105">Na guia **Previsão do Modelo de Mineração** do Designer de Mineração de Dados, você pode criar vários tipos diferentes de consultas.</span><span class="sxs-lookup"><span data-stu-id="1cd55-105">In the **Mining Model Prediction** tab of Data Mining Designer, you can create many different types of queries.</span></span> <span data-ttu-id="1cd55-106">Você pode criar uma consulta usando o designer ou digitando instruções DMX  (Extensões de Mineração de Dados).</span><span class="sxs-lookup"><span data-stu-id="1cd55-106">You can create a query by using the designer, or by typing Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="1cd55-107">Você também pode começar com o designer e modificar a consulta que ele cria alterando as instruções DMX ou adicionando uma cláusula WHERE ou ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="1cd55-107">You can also start with the designer and modify the query that it creates by changing the DMX statements, or by adding a WHERE or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="1cd55-108">Para trocar entre a exibição de design de consulta e a exibição de texto de consulta, clique no primeiro botão na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="1cd55-108">To switch between the query design view and the query text view, click the first button on the toolbar.</span></span> <span data-ttu-id="1cd55-109">Quando você está na exibição de texto de consulta, pode exibir o código DMX criado pelo Construtor de Consultas de Previsão.</span><span class="sxs-lookup"><span data-stu-id="1cd55-109">When you are in the query text view, you can view the DMX code that Prediction Query Builder creates.</span></span> <span data-ttu-id="1cd55-110">Você também pode executar a consulta, modificar a consulta e executar a consulta modificada.</span><span class="sxs-lookup"><span data-stu-id="1cd55-110">You can also run the query, modify the query, and run the modified query.</span></span> <span data-ttu-id="1cd55-111">Porém, a consulta modificada não será mantida se você retornar à exibição de design de consulta.</span><span class="sxs-lookup"><span data-stu-id="1cd55-111">However, the modified query is not persisted if you switch back to the query design view.</span></span>  
  
 <span data-ttu-id="1cd55-112">O código seguinte mostra um exemplo de uma consulta singleton em relação ao modelo de correspondência destinada, TM_Decision_Tree.</span><span class="sxs-lookup"><span data-stu-id="1cd55-112">The following code shows an example of a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT [Bike Buyer], PredictProbability([Bike Buyer]) as ProbableBuyer  
FROM [TM_Decision_Tree]  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="1cd55-113">As etapas a seguir explicam como criar essa consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="1cd55-113">The following steps explain how to create this prediction query.</span></span>  
  
### <a name="to-create-a-singleton-query-by-using-the-data-mining-designer"></a><span data-ttu-id="1cd55-114">Para criar uma consulta singleton utilizando o Designer de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="1cd55-114">To create a singleton query by using the Data Mining Designer</span></span>  
  
1.  <span data-ttu-id="1cd55-115">Clique na guia **Previsão do Modelo de Mineração** do Designer de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="1cd55-115">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="1cd55-116">Clique em **Selecionar Modelo** na tabela **Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="1cd55-116">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="1cd55-117">A caixa de diálogo **Selecionar Modelo de Mineração** é aberta e mostra todas as estruturas de mineração existentes no projeto atual.</span><span class="sxs-lookup"><span data-stu-id="1cd55-117">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
     <span data-ttu-id="1cd55-118">Selecione o modelo que deseja usar para criar a previsão.</span><span class="sxs-lookup"><span data-stu-id="1cd55-118">Select the model that you want to use for creating a prediction.</span></span>  
  
     <span data-ttu-id="1cd55-119">Por exemplo, para criar o código de amostra mostrado no início deste tópico, selecione TM_Decision_Tree e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1cd55-119">For example, to create the sample code shown at the start of this topic, select TM_Decision_Tree, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1cd55-120">Clique em **Consulta Singleton** na barra de ferramentas da guia **Previsão do Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="1cd55-120">Click **Singleton query** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="1cd55-121">A tabela **Entrada da Consulta Singleton** é exibida na guia, com as colunas mapeadas automaticamente para as colunas na tabela **Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="1cd55-121">The **Singleton Query Input** table appears on the tab, with the columns automatically mapped to the columns in the **Mining Model** table.</span></span>  
  
4.  <span data-ttu-id="1cd55-122">Na tabela **Entrada da Consulta Singleton** , selecione os valores na coluna **Valor** para descrever o caso para o qual deseja criar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="1cd55-122">On the **Singleton Query Input** table, select values in the **Value** column to describe the case for which you want to create a prediction.</span></span>  
  
     <span data-ttu-id="1cd55-123">Por exemplo, selecione **2** para **número de filhos em casa**e, em seguida, digite `45` para **idade**.</span><span class="sxs-lookup"><span data-stu-id="1cd55-123">For example, select **2** for **Number Children At Home**, and then type `45` for **Age**.</span></span>  
  
5.  <span data-ttu-id="1cd55-124">Arraste uma coluna previsível da tabela do **modelo de mineração** para a coluna de **origem** na parte inferior da guia. opcionalmente, você pode digitar um alias para a coluna.</span><span class="sxs-lookup"><span data-stu-id="1cd55-124">Drag a predictable column from the **Mining Model** table to the **Source** column at the bottom of the tab. Optionally, you can type an alias for the column.</span></span>  
  
     <span data-ttu-id="1cd55-125">Por exemplo, arraste **Comprador de Bicicleta** para a coluna **Origem** .</span><span class="sxs-lookup"><span data-stu-id="1cd55-125">For example, drag **Bike Buyer** to the **Source** column.</span></span>  
  
6.  <span data-ttu-id="1cd55-126">Adicione qualquer função extra à consulta, selecionando **Função de Previsão** ou **Expressão Personalizada** na lista suspensa na coluna **Origem** .</span><span class="sxs-lookup"><span data-stu-id="1cd55-126">Add any additional functions to the query by selecting **Prediction Function** or **Custom Expression** from the drop-down list in the **Source** column.</span></span>  
  
     <span data-ttu-id="1cd55-127">Por exemplo, clique em **Função de Previsão**e selecione **PredictProbability**.</span><span class="sxs-lookup"><span data-stu-id="1cd55-127">For example, click **Prediction Function**, and select **PredictProbability**.</span></span>  
  
7.  <span data-ttu-id="1cd55-128">Clique em **Critérios/Argumento** na linha **PredictProbability** e digite o nome da coluna para previsão e, como opção, um valor específico para previsão.</span><span class="sxs-lookup"><span data-stu-id="1cd55-128">Click **Criteria/Argument** in the **PredictProbability** row, and type the name of the column to predict, and optionally a specific value to predict.</span></span>  
  
     <span data-ttu-id="1cd55-129">Por exemplo, digite `[Bike Buyer], 1`.</span><span class="sxs-lookup"><span data-stu-id="1cd55-129">For example, type `[Bike Buyer], 1`.</span></span>  
  
8.  <span data-ttu-id="1cd55-130">Clique na caixa **Alias** na linha **PredictProbability** e digite um nome para fazer referência à coluna nova.</span><span class="sxs-lookup"><span data-stu-id="1cd55-130">Click the **Alias** box in the **PredictProbability** row, and type a name to refer to the new column.</span></span>  
  
     <span data-ttu-id="1cd55-131">Por exemplo, digite `ProbableBuyer`.</span><span class="sxs-lookup"><span data-stu-id="1cd55-131">For example, type `ProbableBuyer`.</span></span>  
  
9. <span data-ttu-id="1cd55-132">Clique em **Alternar para a exibição do resultado da consulta** na barra de ferramentas da guia **Previsão do Modelo de Mineração** .</span><span class="sxs-lookup"><span data-stu-id="1cd55-132">Click **Switch to query result view** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="1cd55-133">Uma tela nova se abre para mostrar o resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="1cd55-133">A new screen opens to show the result of the query.</span></span> <span data-ttu-id="1cd55-134">Para exibir a instrução DMX que você acabou de criar, clique em **SQL**.</span><span class="sxs-lookup"><span data-stu-id="1cd55-134">To view the DMX statement that you just created, click **SQL**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd55-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1cd55-135">See Also</span></span>  
 [<span data-ttu-id="1cd55-136">Consultas de previsão &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="1cd55-136">Prediction Queries &#40;Data Mining&#41;</span></span>](prediction-queries-data-mining.md)  
  
  
