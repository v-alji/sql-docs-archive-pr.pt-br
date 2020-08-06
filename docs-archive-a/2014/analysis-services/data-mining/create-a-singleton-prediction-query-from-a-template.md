---
title: Criar uma consulta de Previsão Singleton a partir de um modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton query predictions [DMX]
ms.assetid: e0a68ab0-bece-4d25-b464-47f1719302e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80e853875cce349dd8623fab3c30f1ad09bfbf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570337"
---
# <a name="create-a-singleton-prediction-query-from-a-template"></a><span data-ttu-id="501e8-102">Criar uma consulta de previsão singleton a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="501e8-102">Create a Singleton Prediction Query from a Template</span></span>
  <span data-ttu-id="501e8-103">Uma consulta singleton é útil quando você tem um modelo que deseja usar para previsão, mas não deseja mapeá-la para um conjunto de dados de entrada externo ou fazer previsões em massa.</span><span class="sxs-lookup"><span data-stu-id="501e8-103">A singleton query is useful when you have a model that you want to use for prediction, but don't want to map it to an external input data set or make bulk predictions.</span></span> <span data-ttu-id="501e8-104">Uma consulta singleton permite oferecer um valor ou valores ao modelo e ver instantaneamente o valor previsto.</span><span class="sxs-lookup"><span data-stu-id="501e8-104">With a singleton query, you can provide a value or values to the model and instantly see the predicted value.</span></span>  
  
 <span data-ttu-id="501e8-105">Por exemplo, a consulta DMX a seguir representa uma consulta singleton no modelo de email de destino, TM_Decision_Tree.</span><span class="sxs-lookup"><span data-stu-id="501e8-105">For example, the following DMX query represents a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT * FROM [TM_Decision_tree] ;  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="501e8-106">O procedimento a seguir descreve como usar o Gerenciador de Modelos no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para criar rapidamente esta consulta.</span><span class="sxs-lookup"><span data-stu-id="501e8-106">The procedure that follows describes how to use the Template Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to quickly create this query.</span></span>  
  
### <a name="to-open-the-analysis-services-templates-in-sql-server-management-studio"></a><span data-ttu-id="501e8-107">Para abrir os modelos de Analysis Services no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="501e8-107">To open the Analysis Services templates in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="501e8-108">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Exibir** , clique em **Gerenciador de Modelos**.</span><span class="sxs-lookup"><span data-stu-id="501e8-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="501e8-109">Clique no ícone de cubo para abrir os modelos de **Analysis Server**.</span><span class="sxs-lookup"><span data-stu-id="501e8-109">Click the cube icon to open the **Analysis Server**templates.</span></span>  
  
### <a name="to-open-a-prediction-query-template"></a><span data-ttu-id="501e8-110">Para abrir um modelo de consulta de previsão</span><span class="sxs-lookup"><span data-stu-id="501e8-110">To open a prediction query template</span></span>  
  
1.  <span data-ttu-id="501e8-111">Em **Explorador de Modelos**, na lista de modelos de Analysis Server, expanda **DMX**e **Consultas de Previsão**.</span><span class="sxs-lookup"><span data-stu-id="501e8-111">In **Template Explorer**, in the list of Analysis Server templates, expand **DMX**, and thenexpand **Prediction Queries**.</span></span>  
  
2.  <span data-ttu-id="501e8-112">Clique duas vezes em **Previsão Singleton**.</span><span class="sxs-lookup"><span data-stu-id="501e8-112">Double-click **Singleton Prediction**.</span></span>  
  
3.  <span data-ttu-id="501e8-113">Na caixa de diálogo **Conectar ao Analysis Services** , digite o nome do servidor que tem a instância de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém o modelo de mineração a ser consultado.</span><span class="sxs-lookup"><span data-stu-id="501e8-113">In the **Connect to Analysis Services** dialog box, type the name of the server that has the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining model to be queried.</span></span>  
  
4.  <span data-ttu-id="501e8-114">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="501e8-114">Click **Connect**.</span></span>  
  
5.  <span data-ttu-id="501e8-115">O modelo é aberto no banco de dados especificado, junto com um Pesquisador de Objetos do modelo de mineração que contém as funções de mineração de dados e uma lista de estruturas de mineração de dados e modelos relacionados.</span><span class="sxs-lookup"><span data-stu-id="501e8-115">The template opens in the specified database, together with a mining model Object Browser that contains data mining functions and a list of data mining structures and related models.</span></span>  
  
### <a name="to-customize-the-singleton-query-template"></a><span data-ttu-id="501e8-116">Para personalizar o modelo de consulta singleton</span><span class="sxs-lookup"><span data-stu-id="501e8-116">To customize the singleton query template</span></span>  
  
1.  <span data-ttu-id="501e8-117">No modelo, clique na lista suspensa **Bancos de Dados Disponíveis** e selecione uma instância de Analysis Service na lista.</span><span class="sxs-lookup"><span data-stu-id="501e8-117">In the template, click the **Available Databases** drop-down list, and then select an instance of Analysis Service from the list.</span></span>  
  
2.  <span data-ttu-id="501e8-118">Na lista **Modelo de Mineração** , selecione o modelo de mineração que deseja consultar.</span><span class="sxs-lookup"><span data-stu-id="501e8-118">In the **Mining Model** list, select the mining model that you want to query.</span></span>  
  
     <span data-ttu-id="501e8-119">A lista de colunas no modelo de mineração é exibida no painel **Metadados** do pesquisador de objetos.</span><span class="sxs-lookup"><span data-stu-id="501e8-119">The list of columns in the mining model appears in the **Metadata** pane of the object browser.</span></span>  
  
3.  <span data-ttu-id="501e8-120">No menu **Consulta** , selecione **Especificar Valores para Parâmetros de Modelo**.</span><span class="sxs-lookup"><span data-stu-id="501e8-120">On the **Query** menu, select **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="501e8-121">Na linha **lista de seleção** , digite \* para retornar todas as colunas ou digite uma lista delimitada por vírgulas das colunas e expressões para retornar colunas específicas.</span><span class="sxs-lookup"><span data-stu-id="501e8-121">In the **select list** row, type \* to return all columns, or type a comma-delimited list of columns and expressions to return specific columns.</span></span>  
  
     <span data-ttu-id="501e8-122">Se você digitar \*, a coluna de previsão será retornada, junto com qualquer coluna para a qual você fornece novos valores na etapa 6.</span><span class="sxs-lookup"><span data-stu-id="501e8-122">If you type \*, the predictable column is returned, together with any columns for which you provide new values for in step 6.</span></span>  
  
     <span data-ttu-id="501e8-123">Para o exemplo de código mostrado no início desse tópico, a linha **lista de seleção** foi definida como \*.</span><span class="sxs-lookup"><span data-stu-id="501e8-123">For the sample code shown at the start of this topic, the **select list** row was set to \*.</span></span>  
  
5.  <span data-ttu-id="501e8-124">Na linha **modelo de mineração** , digite o nome do modelo de mineração da lista de modelos de mineração exibidos no **Explorador de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="501e8-124">In the **mining model** row, type the name of the mining model from among the list of mining models that appear in **Object Explorer**.</span></span>  
  
     <span data-ttu-id="501e8-125">Para o código de exemplo mostrado no início deste tópico, a linha do **modelo de mineração** foi definida como o nome, `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="501e8-125">For the sample code shown at the start of this topic, the **mining model** row was set to the name, `TM_Decision_Tree`.</span></span>  
  
6.  <span data-ttu-id="501e8-126">Na linha **valor** , digite o novo valor de dados para os quais você deseja fazer uma previsão.</span><span class="sxs-lookup"><span data-stu-id="501e8-126">In the **value** row, type the new data value for which you want to make a prediction.</span></span>  
  
     <span data-ttu-id="501e8-127">Para o código de exemplo mostrado no início deste tópico, a linha de **valor** foi definida como `2` para prever o comportamento de compra de bicicletas com base no número de filhos em casa.</span><span class="sxs-lookup"><span data-stu-id="501e8-127">For the sample code shown at the start of this topic, the **value** row was set to `2` to predict bike buying behavior based on the number of children at home.</span></span>  
  
7.  <span data-ttu-id="501e8-128">Na linha **coluna** , digite o nome da coluna no modelo de mineração para o qual os novos dados devem ser mapeados.</span><span class="sxs-lookup"><span data-stu-id="501e8-128">In the **column** row, type the name of the column in the mining model to which the new data should be mapped.</span></span>  
  
     <span data-ttu-id="501e8-129">Para o código de exemplo mostrado no início deste tópico, a linha da **coluna** foi definida como `Number Children at Home` .</span><span class="sxs-lookup"><span data-stu-id="501e8-129">For the sample code shown at the start of this topic, the **column** row was set to `Number Children at Home`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="501e8-130">Quando você usa a caixa de diálogo **Especificar Valores para Parâmetros de Modelo** , você não tem que adicionar colchetes ao redor do nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="501e8-130">When you use the **Specify Values for Template Parameters** dialog box, you do not have to add square brackets around the column name.</span></span> <span data-ttu-id="501e8-131">Os colchetes serão adicionados automaticamente para você.</span><span class="sxs-lookup"><span data-stu-id="501e8-131">The brackets will automatically be added for you.</span></span>  
  
8.  <span data-ttu-id="501e8-132">Deixe o **alias de entrada** como `t` .</span><span class="sxs-lookup"><span data-stu-id="501e8-132">Leave the **input alias** as `t`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="501e8-133">No painel de texto de consulta, localize a pequena curva vermelha sob a vírgula e a elipse que indica um erro de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="501e8-133">In the query text pane, find the red squiggle under the comma and ellipsis that indicates a syntax error.</span></span> <span data-ttu-id="501e8-134">Exclua a elipse e adicione qualquer condição de consulta adicional desejada.</span><span class="sxs-lookup"><span data-stu-id="501e8-134">Delete the ellipsis, and add any additional query condition that you want.</span></span> <span data-ttu-id="501e8-135">Se você não quiser adicionar nenhuma outra condição, exclua a vírgula.</span><span class="sxs-lookup"><span data-stu-id="501e8-135">If you do not add any other conditions, delete the comma.</span></span>  
  
     <span data-ttu-id="501e8-136">Para o exemplo de código mostrado no início desse tópico, a condição de consulta adicional foi definida como `'45' as [Age]`.</span><span class="sxs-lookup"><span data-stu-id="501e8-136">For the sample code shown at the start of this topic, the additional query condition was set to `'45' as [Age]`.</span></span>  
  
11. <span data-ttu-id="501e8-137">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="501e8-137">Click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="501e8-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="501e8-138">See Also</span></span>  
 [<span data-ttu-id="501e8-139">Criando previsões &#40;Tutorial básico de Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="501e8-139">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
  
