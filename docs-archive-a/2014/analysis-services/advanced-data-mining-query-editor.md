---
title: Editor de consulta de mineração de dados avançado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 27e7fc46-689d-43a4-9647-1c27d182bdd6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2aadf4df75b1ccf6001ad8e97d589ce5666f56ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571243"
---
# <a name="advanced-data-mining-query-editor"></a><span data-ttu-id="b37e2-102">Editor de Consulta Avançada de Mineração de Dados</span><span class="sxs-lookup"><span data-stu-id="b37e2-102">Advanced Data Mining Query Editor</span></span>
  <span data-ttu-id="b37e2-103">A **Editor avançado de consulta de mineração de dados** é uma ferramenta para ajudá-lo a criar modelos e consultas personalizados.</span><span class="sxs-lookup"><span data-stu-id="b37e2-103">The **Data Mining Query Advanced Editor** is a tool to help you build custom models and queries.</span></span>  
  
 <span data-ttu-id="b37e2-104">O editor fornece um conjunto de modelos com links clicáveis.</span><span class="sxs-lookup"><span data-stu-id="b37e2-104">The editor provides a set of templates with clickable links.</span></span> <span data-ttu-id="b37e2-105">Basta clicar em cada link e usar as caixas de diálogo para selecionar objetos ou valores, e criar instruções DMX complexas.</span><span class="sxs-lookup"><span data-stu-id="b37e2-105">Just click each link, and use the dialog boxes to select objects or values and build complex Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="b37e2-106">Você pode alternar a exibição para o modelo de edição de texto para modificar manualmente a instrução DMX.</span><span class="sxs-lookup"><span data-stu-id="b37e2-106">You can switch the view to text editing model to modify the DMX statement manually.</span></span>  
  
 <span data-ttu-id="b37e2-107">Para acessar o **Editor avançado de consulta de mineração de dados**, clique em **consulta** e, em seguida, clique em **avançado**.</span><span class="sxs-lookup"><span data-stu-id="b37e2-107">To get to the **Data Mining Query Advanced Editor**, click **Query** and then click **Advanced**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="b37e2-108">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="b37e2-108">UI element list</span></span>  
 <span data-ttu-id="b37e2-109">**Painel Consulta DMX**</span><span class="sxs-lookup"><span data-stu-id="b37e2-109">**DMX Query pane**</span></span>  
 <span data-ttu-id="b37e2-110">Aqui você pode consultar a instrução DMX atual.</span><span class="sxs-lookup"><span data-stu-id="b37e2-110">Here you can see the current DMX statement.</span></span>  
  
 <span data-ttu-id="b37e2-111">Clique com o botão direito do mouse no painel para copiar a instrução DMX atual.</span><span class="sxs-lookup"><span data-stu-id="b37e2-111">Right-click in the pane to copy the current DMX statement.</span></span>  
  
 <span data-ttu-id="b37e2-112">Também é possível clicar em qualquer parte destacada da instrução para obter opções específicas dessa cláusula.</span><span class="sxs-lookup"><span data-stu-id="b37e2-112">You can click any highlighted part of the statement to get options specific to that clause.</span></span> <span data-ttu-id="b37e2-113">Por exemplo, para excluir, adicionar ou editar uma saída, clique com o botão direito do mouse no **\<Output>** link.</span><span class="sxs-lookup"><span data-stu-id="b37e2-113">For example, to delete, add, or edit an output, right-click the **\<Output>** link.</span></span>  
  
 <span data-ttu-id="b37e2-114">**Editar Consulta/Construtor de Consultas**</span><span class="sxs-lookup"><span data-stu-id="b37e2-114">**Edit Query/Query Builder**</span></span>  
 <span data-ttu-id="b37e2-115">Use esse botão para alternar o editor entre um editor de texto, no qual você pode escrever instruções DMX diretamente; e o **Construtor de consultas**, que ajuda a criar uma instrução DMX.</span><span class="sxs-lookup"><span data-stu-id="b37e2-115">Use this button to switch the editor between a text editor, where you can write DMX statements directly; and the **Query Builder**, which helps you build a DMX statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b37e2-116">**AVISO:** Se você alternar entre exibições antes da execução da consulta, será exibida uma mensagem informando que você pode perder algumas alterações.</span><span class="sxs-lookup"><span data-stu-id="b37e2-116">**Warning:** If you switch views before the query has been run, a message appears stating that you might lose some changes.</span></span> <span data-ttu-id="b37e2-117">Se a instrução DMX for válida, em muitos casos a **Construtor de consultas** poderá converter essas alterações com êxito.</span><span class="sxs-lookup"><span data-stu-id="b37e2-117">If the DMX statement is valid, in many cases the **Query Builder** might successfully convert these changes.</span></span> <span data-ttu-id="b37e2-118">No entanto, se criar uma instrução DMX particularmente complexa, você deverá salvar seu trabalho antes de alternar exibições.</span><span class="sxs-lookup"><span data-stu-id="b37e2-118">However, if you have built a particularly complex DMX statement, you should definitely save your work before switching views.</span></span>  
  
 <span data-ttu-id="b37e2-119">**Modelos DMX**</span><span class="sxs-lookup"><span data-stu-id="b37e2-119">**DMX Templates**</span></span>  
 <span data-ttu-id="b37e2-120">Clique e selecione em uma lista de modelos que contenha exemplos de DMX.</span><span class="sxs-lookup"><span data-stu-id="b37e2-120">Click and select from a list of templates that contain DMX examples.</span></span> <span data-ttu-id="b37e2-121">Os modelos oferecem todo tipo de modelo ou consulta de previsão que você possa precisar, inclusive consultas que usam tabelas aninhadas e instruções DMX para gerenciar modelos.</span><span class="sxs-lookup"><span data-stu-id="b37e2-121">The templates provide just about every type of model or prediction query that you might need, including queries that use nested tables, and DMX statements to manage models.</span></span> <span data-ttu-id="b37e2-122">Mesmo que você tenha algum conhecimento de DMX, os modelos poderão economizar tempo ao usar a sintaxe correta.</span><span class="sxs-lookup"><span data-stu-id="b37e2-122">Even if you know some DMX, the templates can save you time by getting the syntax right.</span></span>  
  
 <span data-ttu-id="b37e2-123">**Escolher modelo**</span><span class="sxs-lookup"><span data-stu-id="b37e2-123">**Choose Model**</span></span>  
 <span data-ttu-id="b37e2-124">Clique para exibir uma lista de modelos de mineração de dados disponíveis na conexão atual.</span><span class="sxs-lookup"><span data-stu-id="b37e2-124">Click to view a list of data mining models available on the current connection.</span></span>  
  
 <span data-ttu-id="b37e2-125">Você também pode exibir uma lista de modelos disponíveis clicando no nome do modelo na instrução DMX no painel de **consulta DMX** .</span><span class="sxs-lookup"><span data-stu-id="b37e2-125">You can also display a list of available models by clicking on the model name in the DMX statement in the **DMX Query** pane.</span></span> <span data-ttu-id="b37e2-126">O nome do modelo normalmente é realçado em vermelho.</span><span class="sxs-lookup"><span data-stu-id="b37e2-126">The model name is typically highlighted in red.</span></span>  
  
 <span data-ttu-id="b37e2-127">**Selecione a entrada**</span><span class="sxs-lookup"><span data-stu-id="b37e2-127">**Select Input**</span></span>  
 <span data-ttu-id="b37e2-128">Clique para escolher os dados a serem usados como entrada para o modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="b37e2-128">Click to choose the data to use as input to the mining model.</span></span> <span data-ttu-id="b37e2-129">Se nenhuma fonte de dados tiver sido especificada, você também poderá clicar no **\<Input>** link, que é realçado em vermelho no painel de **consulta DMX** .</span><span class="sxs-lookup"><span data-stu-id="b37e2-129">If no data source has been specified, you can also click the **\<Input>** link, which is highlighted in red in the **DMX Query** pane.</span></span>  
  
 <span data-ttu-id="b37e2-130">Selecione \*\* \@ InputRowset\*\* na lista suspensa para abrir a caixa de diálogo **substituir InputRowset** e modificar uma entrada existente.</span><span class="sxs-lookup"><span data-stu-id="b37e2-130">Select **\@InputRowset** from the dropdown list to open the **Replace InputRowset** dialog box and modify an existing input.</span></span>  
  
 <span data-ttu-id="b37e2-131">Selecione **Adicionar entrada** para abrir a caixa de diálogo **Adicionar entrada** e especifique uma nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b37e2-131">Select **Add Input** to open the **Add Input** dialog box and specify a new data source.</span></span>  
  
 <span data-ttu-id="b37e2-132">Você também pode modificar uma entrada existente clicando no link \*\* \@ InputRowset\*\* , que é realçado em vermelho no painel de consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="b37e2-132">You can also modify an existing input by clicking the **\@InputRowset** link, which is highlighted in red in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="b37e2-133">**Mapear colunas**</span><span class="sxs-lookup"><span data-stu-id="b37e2-133">**Map Columns**</span></span>  
 <span data-ttu-id="b37e2-134">Selecione colunas do modelo de mineração e mapeie-as para colunas na fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="b37e2-134">Select columns from the mining model and then map them to columns in the external data source.</span></span>  
  
 <span data-ttu-id="b37e2-135">Você também pode clicar no link realçado **\<Mapping>** no painel consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="b37e2-135">You can also click the highlighted **\<Mapping>** link in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="b37e2-136">**Adicionar Saída**</span><span class="sxs-lookup"><span data-stu-id="b37e2-136">**Add Output**</span></span>  
 <span data-ttu-id="b37e2-137">Clique para escolher as colunas que devem ser incluídas na saída como parte de uma consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="b37e2-137">Click to choose the columns that should be output as part of a prediction query.</span></span>  
  
 <span data-ttu-id="b37e2-138">Você também pode clicar no link realçado **\<Add Output>** no painel consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="b37e2-138">You can also click the highlighted **\<Add Output>** link in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="b37e2-139">**Colunas do Modelo**</span><span class="sxs-lookup"><span data-stu-id="b37e2-139">**Model Columns**</span></span>  
 <span data-ttu-id="b37e2-140">Lista as colunas no modelo de mineração selecionado.</span><span class="sxs-lookup"><span data-stu-id="b37e2-140">Lists the columns in the selected mining model.</span></span> <span data-ttu-id="b37e2-141">Um losango ao lado do nome da coluna indica que ela é uma coluna previsível.</span><span class="sxs-lookup"><span data-stu-id="b37e2-141">A diamond mark next to the column name indicates that the column is a predictable column.</span></span>  
  
 <span data-ttu-id="b37e2-142">**Colunas de Entrada**</span><span class="sxs-lookup"><span data-stu-id="b37e2-142">**Input Columns**</span></span>  
 <span data-ttu-id="b37e2-143">Lista as colunas da fonte de dados externa que foram adicionadas como entradas.</span><span class="sxs-lookup"><span data-stu-id="b37e2-143">Lists the columns from the external data source that have been added as inputs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b37e2-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b37e2-144">See Also</span></span>  
 [<span data-ttu-id="b37e2-145">&#40;de consulta SQL Server suplementos de mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="b37e2-145">Query &#40;SQL Server Data Mining Add-ins&#41;</span></span>](query-sql-server-data-mining-add-ins.md)  
  
  
