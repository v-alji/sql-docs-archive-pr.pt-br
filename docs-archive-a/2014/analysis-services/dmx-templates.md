---
title: Modelos DMX | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a577e52-821d-4bd3-ba35-075a6be285c9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79c8615933baf4fa3d80974daae91b4d1c7fa101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582199"
---
# <a name="dmx-templates"></a><span data-ttu-id="76f5d-102">Modelos DMX</span><span class="sxs-lookup"><span data-stu-id="76f5d-102">DMX Templates</span></span>
  <span data-ttu-id="76f5d-103">Os modelos de mineração de dados o ajudam a criar rapidamente consultas sofisticadas.</span><span class="sxs-lookup"><span data-stu-id="76f5d-103">The data mining templates help you quickly build sophisticated queries.</span></span> <span data-ttu-id="76f5d-104">Embora a sintaxe geral para consultas DMX seja bem-documentada, usar os modelos torna mais fácil criar consultas clicando e apontando para argumentos e fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="76f5d-104">Although the general syntax for DMX queries is well documented, using the templates makes it easier to build queries by clicking and pointing to arguments and data sources.</span></span>  
  
## <a name="using-the-templates"></a><span data-ttu-id="76f5d-105">Usando os modelos</span><span class="sxs-lookup"><span data-stu-id="76f5d-105">Using the Templates</span></span>  
  
1.  <span data-ttu-id="76f5d-106">No cliente de mineração de dados para Excel, clique em **consulta**.</span><span class="sxs-lookup"><span data-stu-id="76f5d-106">In the Data Mining Client for Excel, click **Query**.</span></span>  
  
2.  <span data-ttu-id="76f5d-107">Na página **inicial** do assistente, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="76f5d-107">On the wizard **Start** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="76f5d-108">Na página, **selecione modelo**, clique em **avançado**.</span><span class="sxs-lookup"><span data-stu-id="76f5d-108">On the page, **Select Model**, click **Advanced**.</span></span>  
  
     <span data-ttu-id="76f5d-109">**Dica:** Se você pretende criar uma consulta de previsão em um modelo, você pode selecionar o modelo primeiro e, em seguida, clicar em **avançado**para preencher previamente o modelo com o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="76f5d-109">**Tip:** If you are going to create a prediction query on a model, you can select the model first, and then click **Advanced**, to prepopulate the template with the model name.</span></span>  
  
4.  <span data-ttu-id="76f5d-110">No **Editor de consulta avançada de mineração de dados**, clique em **modelos DMX**e selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="76f5d-110">In the **Data Mining Advanced Query Editor**, click **DMX Templates**, and select a template.</span></span>  
  
5.  <span data-ttu-id="76f5d-111">Pressione ENTER para carregar o modelo no painel Consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="76f5d-111">Press ENTER to load the template into the DMX Query pane.</span></span>  
  
6.  <span data-ttu-id="76f5d-112">Continue clicando nos links no modelo e, quando a caixa de diálogo for exibida, selecione uma saída, um modelo ou um parâmetro apropriado.</span><span class="sxs-lookup"><span data-stu-id="76f5d-112">Continue clicking the links in the template, and as the dialog box appears, select an appropriate output, model, or parameter.</span></span>  
  
     <span data-ttu-id="76f5d-113">Para consultas de previsão, escolha o conjunto de dados de entrada primeiro e depois mapeie as colunas.</span><span class="sxs-lookup"><span data-stu-id="76f5d-113">For prediction queries, choose the input dataset first, and then map the columns.</span></span>  
  
7.  <span data-ttu-id="76f5d-114">Clique em **Editar consulta** para alternar para a exibição do editor de texto e alterar manualmente a consulta.</span><span class="sxs-lookup"><span data-stu-id="76f5d-114">Click **Edit Query** to switch to text editor view and manually change the query.</span></span>  
  
     <span data-ttu-id="76f5d-115">Saiba que, se você alternar exibições ao trabalhar no editor de consulta, quaisquer informações contidas na exibição anterior serão limpas.</span><span class="sxs-lookup"><span data-stu-id="76f5d-115">Be aware, however, that if you switch views when working in the query editor, any information that you had in the previous view will be cleared.</span></span> <span data-ttu-id="76f5d-116">Antes de alterar as exibições, salve seu trabalho copiando e colando as instruções DMX em um arquivo separado.</span><span class="sxs-lookup"><span data-stu-id="76f5d-116">Before changing views, save your work by copying and pasting the DMX statements to a separate file.</span></span>  
  
8.  <span data-ttu-id="76f5d-117">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="76f5d-117">Click **Finish**.</span></span> <span data-ttu-id="76f5d-118">Na caixa de diálogo **escolher destino** , especifique onde você deseja que o resultado seja salvo.</span><span class="sxs-lookup"><span data-stu-id="76f5d-118">In the **Choose Destination** dialog  box, specify where you want the result saved.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="76f5d-119">Se você executou uma instrução com êxito, a instrução DMX que você enviou para o servidor também será registrada na janela de **rastreamento** .</span><span class="sxs-lookup"><span data-stu-id="76f5d-119">If you executed a statement successfully, the DMX statement that you sent to the server is also recorded in the **Trace** window.</span></span> <span data-ttu-id="76f5d-120">Para obter mais informações sobre como usar o recurso de rastreamento, consulte [rastrear &#40;cliente de mineração de dados para Excel&#41;](trace-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="76f5d-120">For more information about how to use the Trace feature, see [Trace &#40;Data Mining Client for Excel&#41;](trace-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="76f5d-121">Para obter mais informações sobre como usar o editor de consultas avançadas de mineração de dados, consulte [consulta &#40;SQL Server suplementos de mineração](query-sql-server-data-mining-add-ins.md) de dados&#41;e [Editor de consulta de mineração de dados avançado](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="76f5d-121">For more information about how to use the Data Mining Advanced Query Editor, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) and [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="list-of-dmx-templates"></a><span data-ttu-id="76f5d-122">Lista de modelos DMX</span><span class="sxs-lookup"><span data-stu-id="76f5d-122">List of DMX Templates</span></span>  
 <span data-ttu-id="76f5d-123">Os seguintes modelos DMX são incluídos no Cliente de Mineração de Dados para Excel.</span><span class="sxs-lookup"><span data-stu-id="76f5d-123">The following DMX templates are included in the Data Mining Client for Excel.</span></span>  
  
 <span data-ttu-id="76f5d-124">**Previsão**</span><span class="sxs-lookup"><span data-stu-id="76f5d-124">**Prediction**</span></span>  
  
 <span data-ttu-id="76f5d-125">Use esses modelos para criar consultas de previsão avançadas, inclusive as consultas sem suporte dos assistentes nos suplementos, como as consultas que usam tabelas aninhadas ou fontes de dados externas.</span><span class="sxs-lookup"><span data-stu-id="76f5d-125">Use these templates to create advanced prediction queries, including queries not supported by the wizards in the add-ins, such as queries that use nested tables or external data sources.</span></span>  
  
-   <span data-ttu-id="76f5d-126">Previsões filtradas</span><span class="sxs-lookup"><span data-stu-id="76f5d-126">Filtered predictions</span></span>  
  
-   <span data-ttu-id="76f5d-127">Previsões aninhadas filtradas</span><span class="sxs-lookup"><span data-stu-id="76f5d-127">Filtered nested predictions</span></span>  
  
-   <span data-ttu-id="76f5d-128">Previsões aninhadas</span><span class="sxs-lookup"><span data-stu-id="76f5d-128">Nested predictions</span></span>  
  
-   <span data-ttu-id="76f5d-129">Previsões singleton</span><span class="sxs-lookup"><span data-stu-id="76f5d-129">Singleton predictions</span></span>  
  
-   <span data-ttu-id="76f5d-130">Previsões padrão</span><span class="sxs-lookup"><span data-stu-id="76f5d-130">Standard predictions</span></span>  
  
-   <span data-ttu-id="76f5d-131">Previsões de série temporal</span><span class="sxs-lookup"><span data-stu-id="76f5d-131">Time series predictions</span></span>  
  
-   <span data-ttu-id="76f5d-132">Consulta de previsão TOP</span><span class="sxs-lookup"><span data-stu-id="76f5d-132">TOP prediction query</span></span>  
  
-   <span data-ttu-id="76f5d-133">Consulta de previsão TOP em tabela aninhada</span><span class="sxs-lookup"><span data-stu-id="76f5d-133">TOP prediction query on nested table</span></span>  
  
 <span data-ttu-id="76f5d-134">**Criar**</span><span class="sxs-lookup"><span data-stu-id="76f5d-134">**Create**</span></span>  
  
 <span data-ttu-id="76f5d-135">Use esses modelos para criar modelos ou estruturas de dados personalizados.</span><span class="sxs-lookup"><span data-stu-id="76f5d-135">Use these templates to build custom models or data structures.</span></span> <span data-ttu-id="76f5d-136">Você não está limitado aos modelos suportados pelos assistentes-você pode usar qualquer Data Mining algoritmo com suporte na instância do à [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qual você está conectado, incluindo algoritmos de plug-in.</span><span class="sxs-lookup"><span data-stu-id="76f5d-136">You are not limited to the models supported by the wizards - you can use any data mining algorithm supported by the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you are connected to, including plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="76f5d-137">Modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-137">Mining model</span></span>  
  
-   <span data-ttu-id="76f5d-138">Estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-138">Mining structure</span></span>  
  
-   <span data-ttu-id="76f5d-139">Estrutura de mineração com controle</span><span class="sxs-lookup"><span data-stu-id="76f5d-139">Mining structure with holdout</span></span>  
  
-   <span data-ttu-id="76f5d-140">Modelo temporário</span><span class="sxs-lookup"><span data-stu-id="76f5d-140">Temporary model</span></span>  
  
-   <span data-ttu-id="76f5d-141">Estrutura temporária</span><span class="sxs-lookup"><span data-stu-id="76f5d-141">Temporary structure</span></span>  
  
 <span data-ttu-id="76f5d-142">**Propriedades do modelo**</span><span class="sxs-lookup"><span data-stu-id="76f5d-142">**Model Properties**</span></span>  
  
 <span data-ttu-id="76f5d-143">Use esses modelos para criar consultas que obtêm metadados sobre o modelo e o conjunto de treinamento.</span><span class="sxs-lookup"><span data-stu-id="76f5d-143">Use these templates to create queries that get metadata about the model and the training set.</span></span> <span data-ttu-id="76f5d-144">Você também pode recuperar detalhes do conteúdo do modelo ou obter um perfil estatístico dos dados de treinamento.</span><span class="sxs-lookup"><span data-stu-id="76f5d-144">You can also retrieve details from the model content, or get a statistical profile of the training data.</span></span>  
  
-   <span data-ttu-id="76f5d-145">Conteúdo do modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-145">Mining model content</span></span>  
  
-   <span data-ttu-id="76f5d-146">Valores mínimo e máximo de coluna</span><span class="sxs-lookup"><span data-stu-id="76f5d-146">Minimum and maximum column values</span></span>  
  
-   <span data-ttu-id="76f5d-147">Casos de teste/treinamento da estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-147">Mining structure test/training cases</span></span>  
  
-   <span data-ttu-id="76f5d-148">Valores discretos de coluna</span><span class="sxs-lookup"><span data-stu-id="76f5d-148">Discrete column values</span></span>  
  
 <span data-ttu-id="76f5d-149">**Gerenciamento**</span><span class="sxs-lookup"><span data-stu-id="76f5d-149">**Management**</span></span>  
  
 <span data-ttu-id="76f5d-150">Use esses modelos para executar qualquer tarefa de gerenciamento com suporte no DMX, o que inclui importar e exportar modelos, excluir modelos e limpar modelos e estruturas de dados.</span><span class="sxs-lookup"><span data-stu-id="76f5d-150">Use these templates to perform any management task supported by DMX, which includes importing and exporting models, deleting models, and clearing models or data structures.</span></span>  
  
-   <span data-ttu-id="76f5d-151">Limpar modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-151">Clear mining model</span></span>  
  
-   <span data-ttu-id="76f5d-152">Limpar estrutura e modelos</span><span class="sxs-lookup"><span data-stu-id="76f5d-152">Clear structure and models</span></span>  
  
-   <span data-ttu-id="76f5d-153">Limpar estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-153">Clear mining structure</span></span>  
  
-   <span data-ttu-id="76f5d-154">Excluir modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-154">Delete mining model</span></span>  
  
-   <span data-ttu-id="76f5d-155">Excluir estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-155">Delete mining structure</span></span>  
  
-   <span data-ttu-id="76f5d-156">Renomear modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-156">Rename mining model</span></span>  
  
-   <span data-ttu-id="76f5d-157">Renomear estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-157">Rename mining structure</span></span>  
  
-   <span data-ttu-id="76f5d-158">Treinar modelo de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-158">Train mining model</span></span>  
  
-   <span data-ttu-id="76f5d-159">Treinar estrutura de mineração aninhada</span><span class="sxs-lookup"><span data-stu-id="76f5d-159">Train nested mining structure</span></span>  
  
-   <span data-ttu-id="76f5d-160">Treinar estrutura de mineração</span><span class="sxs-lookup"><span data-stu-id="76f5d-160">Train mining structure</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="76f5d-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76f5d-161">Requirements</span></span>  
 <span data-ttu-id="76f5d-162">Dependendo do modelo usado, talvez você precise de permissões administrativas para acessar o servidor [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="76f5d-162">Depending on which template you are using, you might need administrative permissions to access the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and execute the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f5d-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="76f5d-163">See Also</span></span>  
 [<span data-ttu-id="76f5d-164">Criar um modelo de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="76f5d-164">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
