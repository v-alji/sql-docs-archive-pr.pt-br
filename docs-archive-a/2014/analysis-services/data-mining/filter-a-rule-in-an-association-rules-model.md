---
title: Filtrar uma regra em um modelo de regras de associação | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filtering rules [Analysis Services]
- Mining Model Viewer [Analysis Services], rules
- Rules Viewer
ms.assetid: 26cdba5b-5bf1-439e-80a3-8759774e918b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c904713acc6eaf132e7cb1195186165f21d971a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575455"
---
# <a name="filter-a-rule-in-an-association-rules-model"></a><span data-ttu-id="1a47f-102">Filtrar uma regra em um modelo de regras de associação</span><span class="sxs-lookup"><span data-stu-id="1a47f-102">Filter a Rule in an Association Rules Model</span></span>
  <span data-ttu-id="1a47f-103">Você pode usar a filtragem com modelos de associação para restringir os resultados a apenas as associações do seu interesse.</span><span class="sxs-lookup"><span data-stu-id="1a47f-103">You can use filtering with association models to restrict the results to just the associations that interest you.</span></span> <span data-ttu-id="1a47f-104">Por exemplo, você pode filtrar as regras para mostrar apenas aquelas que incluem um produto específico.</span><span class="sxs-lookup"><span data-stu-id="1a47f-104">For example, you might filter the rules to show only those that include a specific product.</span></span>  
  
 <span data-ttu-id="1a47f-105">No Designer de Mineração de Dados, você pode usar os controles na guia **Regras** do Visualizador de Regras de Associação da [!INCLUDE[msCoName](../../includes/msconame-md.md)] para filtrar as regras que são exibidas.</span><span class="sxs-lookup"><span data-stu-id="1a47f-105">In Data Mining Designer, you use the controls on the **Rules** tab of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer to filter the rules that are displayed.</span></span>  <span data-ttu-id="1a47f-106">Você também pode criar uma consulta no modelo para ver apenas o conjunto de itens que contém um valor específico.</span><span class="sxs-lookup"><span data-stu-id="1a47f-106">You can also create a query on the model to see only itemset that contains a particular value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a47f-107">Esta opção só está disponível para modelos de mineração que foram criados com o Algoritmo de Associação da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a47f-107">This option is available only for mining models that have been created by using the Microsoft Association Algorithm.</span></span>  
  
### <a name="filter-a-rule-in-an-association-model"></a><span data-ttu-id="1a47f-108">Filtrar uma regra em um modelo de associação</span><span class="sxs-lookup"><span data-stu-id="1a47f-108">Filter a rule in an association model</span></span>  
  
1.  <span data-ttu-id="1a47f-109">Abra o modelo de mineração usando o **Visualizador de Regras de Associação**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-109">Open the mining model by using the **Association Rules Viewer**.</span></span> <span data-ttu-id="1a47f-110">Para fazer isso no SQL Server Management Studio, clique com o botão direito do mouse no nome do modelo e selecione **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-110">To do this in SQL Server Management Studio, right click the model name and select **Browse**.</span></span> <span data-ttu-id="1a47f-111">Para fazer isso no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique duas vezes na estrutura de mineração que contém o modelo e clique na guia **Visualizador do Modelo de Mineração** do **Designer de Mineração de Dados**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-111">To do this in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the model, and then click the **Mining Model Viewer** tab of **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="1a47f-112">Clique na guia **Regras** do **Visualizador de Regras de Associação**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-112">Click the **Rules** tab of the **Association Rules Viewer**.</span></span>  
  
3.  <span data-ttu-id="1a47f-113">Digite em uma condição de regra na caixa **Filtrar Regra** .</span><span class="sxs-lookup"><span data-stu-id="1a47f-113">Type a rule condition into the **Filter Rule** box.</span></span> <span data-ttu-id="1a47f-114">Por exemplo, uma condição de regra poderia ser "Posto de Bicicleta" que também retorna "Postos de Bicicleta."</span><span class="sxs-lookup"><span data-stu-id="1a47f-114">For example, a rule condition might be "Bike Stand", which also returns "Bike Stands".</span></span>  
  
     <span data-ttu-id="1a47f-115">A caixa de texto **Regra do Filtro** dá suporte a expressões regulares conforme a definição da linguagem .NET.</span><span class="sxs-lookup"><span data-stu-id="1a47f-115">The **Filter Rule** text box supports regular expressions as defined by the .NET language.</span></span> <span data-ttu-id="1a47f-116">Por isso, é possível usar expressões como as seguintes: `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`.</span><span class="sxs-lookup"><span data-stu-id="1a47f-116">Therefore, you can use expressions such as the following: `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`.</span></span> <span data-ttu-id="1a47f-117">Essa expressão retornaria qualquer conjuntos de itens que incluísse atributos com as palavras Helmets e Fenders, em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="1a47f-117">This expression would return any itemsets that include attributes with the words Helmets and Fenders, in any order.</span></span>  
  
4.  <span data-ttu-id="1a47f-118">Para **Probabilidade mínima**, aumente o valor da probabilidade para exibir menos regras ou diminua o valor para exibir mais regras.</span><span class="sxs-lookup"><span data-stu-id="1a47f-118">For **Minimum probability**, increase the value of probability to see fewer rules, or decrease the value to see more rules.</span></span>  
  
5.  <span data-ttu-id="1a47f-119">Para **Importância mínima**, aumente o valor da importância para exibir menos regras ou diminua o valor para exibir mais regras.</span><span class="sxs-lookup"><span data-stu-id="1a47f-119">For **Minimum importance**, increase the value of importance to see fewer rules, or decrease the value to see more rules.</span></span>  
  
6.  <span data-ttu-id="1a47f-120">Para **Mostrar**, selecione um das seguintes opções: **Mostrar nome e valor do atributo**, **Mostrar apenas o nome de atributo**ou **Mostrar apenas o valor de atributo**.</span><span class="sxs-lookup"><span data-stu-id="1a47f-120">For **Show**, select one of the following options: **Show attribute name and value**, **Show attribute name only**, or **Show attribute value only**.</span></span>  
  
7.  <span data-ttu-id="1a47f-121">Para **Máximo de linhas**, aumente o valor para aumentar o número total de regras que atendem às condições especificadas ou diminua o valor para limitar o número de regras retornadas.</span><span class="sxs-lookup"><span data-stu-id="1a47f-121">For **Maximum rows**, increase the value to increase the total number of rules that meet the specified conditions, or decrease the value to limit the number of rules returned.</span></span> <span data-ttu-id="1a47f-122">As regras são ordenadas por probabilidade, assim você poderia eliminar regras adicionais que atendem às condições especificadas de probabilidade ou importância.</span><span class="sxs-lookup"><span data-stu-id="1a47f-122">Rules are ordered by probability, so you might eliminate additional rules that meet the specified conditions for probability or importance.</span></span>  
  
8.  <span data-ttu-id="1a47f-123">Marque ou desmarque a caixa de seleção **Mostrar nome longo** para alternar o modo como os nomes de regras são exibidos.</span><span class="sxs-lookup"><span data-stu-id="1a47f-123">Select or deselect the **Show long name** check box to toggle the way that the rules names are displayed.</span></span>  
  
     <span data-ttu-id="1a47f-124">As regras agora são filtradas para exibir apenas as regras de exibição que contenham o item indicado.</span><span class="sxs-lookup"><span data-stu-id="1a47f-124">The rules are now filtered to only display rules that contain the indicated item.</span></span> <span data-ttu-id="1a47f-125">A condição de filtro se aplica a valores de atributo antes ou depois do delimitador de regra, "->".</span><span class="sxs-lookup"><span data-stu-id="1a47f-125">The filter condition applies to attribute values either before or after the rule delimiter, "->".</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1a47f-126">O visualizador armazena em cache a lista inicial de regras, baseado em uma consulta para o modelo de mineração, e não atualiza a lista de regras a menos que você altere as condições da consulta definindo o máximo de linhas, a probabilidade, importância ou a exibição de nomes longos.</span><span class="sxs-lookup"><span data-stu-id="1a47f-126">The viewer caches the initial list of rules, based on a query to the mining model, and does not refresh the list of rules unless you change the conditions of the query by setting the maximum rows, the probability, importance, or the display of long names.</span></span> <span data-ttu-id="1a47f-127">Por isso, se digitar uma condição e a exibição não for atualizada imediatamente, você poderá forçar o visualizador a atualizar os dados, marcando e desmarcando a caixa de seleção **Mostrar nomes longos** .</span><span class="sxs-lookup"><span data-stu-id="1a47f-127">Therefore, if you type a condition and the display does not immediately refresh, you can force the viewer to refresh the data by selecting and then deselecting the **Show long names** check box.</span></span>  
  
### <a name="create-a-query-on-the-itemsets-in-an-association-model"></a><span data-ttu-id="1a47f-128">Criar uma consulta nos conjuntos de itens em um modelo de associação</span><span class="sxs-lookup"><span data-stu-id="1a47f-128">Create a query on the itemsets in an association model</span></span>  
  
-   [<span data-ttu-id="1a47f-129">Exemplos de consulta de um modelo de associação</span><span class="sxs-lookup"><span data-stu-id="1a47f-129">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
## <a name="see-also"></a><span data-ttu-id="1a47f-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1a47f-130">See Also</span></span>  
 <span data-ttu-id="1a47f-131">[Tarefas e instruções do Visualizador do modelo de mineração](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="1a47f-131">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="1a47f-132">[Procurar um modelo usando o Visualizador de regras de associação da Microsoft](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="1a47f-132">[Browse a Model Using the Microsoft Association Rules Viewer](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span></span>  
 [<span data-ttu-id="1a47f-133">Lição 3: Criando um cenário de cesta de compras &#40;Tutorial intermediário de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="1a47f-133">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
  
