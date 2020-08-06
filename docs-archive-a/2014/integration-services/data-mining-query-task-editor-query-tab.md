---
title: Editor da tarefa consulta de mineração de dados (guia consulta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.query.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 72b1755d-d226-46c5-b862-0c9333196a10
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6005c92d0d48850461c01353ddf94c61140d0f2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684260"
---
# <a name="data-mining-query-task-editor-query-tab"></a><span data-ttu-id="651bc-102">Editor da Tarefa Consulta de Mineração de Dados (guia Consulta)</span><span class="sxs-lookup"><span data-stu-id="651bc-102">Data Mining Query Task Editor (Query Tab)</span></span>
  <span data-ttu-id="651bc-103">Use a guia **Consulta** da caixa de diálogo **Tarefa Consulta de Mineração de Dados** para criar consultas de previsão baseadas em um modelo de mineração.</span><span class="sxs-lookup"><span data-stu-id="651bc-103">Use the **Query** tab of the **Data Mining Query Task** dialog box to create prediction queries based on a mining model.</span></span> <span data-ttu-id="651bc-104">Nessa caixa de diálogo, você também pode associar parâmetros e conjuntos de resultados a variáveis.</span><span class="sxs-lookup"><span data-stu-id="651bc-104">In this dialog box you can also bind parameters and result sets to variables.</span></span>  
  
 <span data-ttu-id="651bc-105">Para saber mais sobre como implementar a mineração de dados em pacotes, consulte [Tarefa Consulta de mineração de dados](control-flow/data-mining-query-task.md) e [Soluções de mineração de dados](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="651bc-105">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="651bc-106">Opções gerais</span><span class="sxs-lookup"><span data-stu-id="651bc-106">General Options</span></span>  
 <span data-ttu-id="651bc-107">**Nome**</span><span class="sxs-lookup"><span data-stu-id="651bc-107">**Name**</span></span>  
 <span data-ttu-id="651bc-108">Forneça um nome exclusivo para a tarefa Consulta de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="651bc-108">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="651bc-109">Esse nome é usado como rótulo no ícone de tarefa.</span><span class="sxs-lookup"><span data-stu-id="651bc-109">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="651bc-110">Os nomes das tarefas devem ser exclusivos em um pacote.</span><span class="sxs-lookup"><span data-stu-id="651bc-110">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="651bc-111">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="651bc-111">**Description**</span></span>  
 <span data-ttu-id="651bc-112">Digite uma descrição para a tarefa Consulta de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="651bc-112">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="build-query-tab-options"></a><span data-ttu-id="651bc-113">Opções da guia Construir Consulta</span><span class="sxs-lookup"><span data-stu-id="651bc-113">Build Query Tab Options</span></span>  
 <span data-ttu-id="651bc-114">**Consulta de mineração de dados**</span><span class="sxs-lookup"><span data-stu-id="651bc-114">**Data mining query**</span></span>  
 <span data-ttu-id="651bc-115">Digite uma consulta de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="651bc-115">Type a data mining query.</span></span>  
  
 <span data-ttu-id="651bc-116">**Tópicos relacionados:**  [Referência de &#40;extensões DMX&#41;](/sql/dmx/data-mining-extensions-dmx-reference)</span><span class="sxs-lookup"><span data-stu-id="651bc-116">**Related Topics:**  [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference)</span></span>  
  
 <span data-ttu-id="651bc-117">**Construir Nova Consulta**</span><span class="sxs-lookup"><span data-stu-id="651bc-117">**Build New Query**</span></span>  
 <span data-ttu-id="651bc-118">Crie a consulta de mineração de dados usando uma ferramenta gráfica.</span><span class="sxs-lookup"><span data-stu-id="651bc-118">Create the data mining query using a graphical tool.</span></span>  
  
 <span data-ttu-id="651bc-119">**Tópicos relacionados:** [Data Mining Query](control-flow/data-mining-query.md)</span><span class="sxs-lookup"><span data-stu-id="651bc-119">**Related Topics:** [Data Mining Query](control-flow/data-mining-query.md)</span></span>  
  
## <a name="parameter-mapping-tab-options"></a><span data-ttu-id="651bc-120">Opções da guia Mapeamento de Parâmetros</span><span class="sxs-lookup"><span data-stu-id="651bc-120">Parameter Mapping Tab Options</span></span>  
 <span data-ttu-id="651bc-121">**Nome do parâmetro**</span><span class="sxs-lookup"><span data-stu-id="651bc-121">**Parameter Name**</span></span>  
 <span data-ttu-id="651bc-122">Opcionalmente, atualize o nome de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="651bc-122">Optionally, update the parameter name.</span></span> <span data-ttu-id="651bc-123">Mapeie o parâmetro para uma variável, selecionando uma variável na lista **Nome da Variável** .</span><span class="sxs-lookup"><span data-stu-id="651bc-123">Map the parameter to a variable by selecting a variable in the **Variable Name** list.</span></span>  
  
 <span data-ttu-id="651bc-124">**Nome da Variável**</span><span class="sxs-lookup"><span data-stu-id="651bc-124">**Variable Name**</span></span>  
 <span data-ttu-id="651bc-125">Selecione uma variável na lista para mapeá-la para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="651bc-125">Select a variable in the list to map it to the parameter.</span></span>  
  
 <span data-ttu-id="651bc-126">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="651bc-126">**Add**</span></span>  
 <span data-ttu-id="651bc-127">Adicione um parâmetro à lista.</span><span class="sxs-lookup"><span data-stu-id="651bc-127">Add to a parameter to the list.</span></span>  
  
 <span data-ttu-id="651bc-128">**Remover**</span><span class="sxs-lookup"><span data-stu-id="651bc-128">**Remove**</span></span>  
 <span data-ttu-id="651bc-129">Selecione um parâmetro e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="651bc-129">Select a parameter, and then click **Remove**.</span></span>  
  
## <a name="result-set-tab-options"></a><span data-ttu-id="651bc-130">Opções da guia Conjunto de Resultados</span><span class="sxs-lookup"><span data-stu-id="651bc-130">Result Set Tab Options</span></span>  
 <span data-ttu-id="651bc-131">**Nome do Resultado**</span><span class="sxs-lookup"><span data-stu-id="651bc-131">**Result Name**</span></span>  
 <span data-ttu-id="651bc-132">Opcionalmente, atualize o nome do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="651bc-132">Optionally, update the result set name.</span></span> <span data-ttu-id="651bc-133">Mapeie o resultado para uma variável, selecionando uma variável na lista **Nome da Variável** .</span><span class="sxs-lookup"><span data-stu-id="651bc-133">Map the result to a variable by selecting a variable in the **Variable Name** list.</span></span>  
  
 <span data-ttu-id="651bc-134">Depois que você adicionar um resultado, clicando em **Adicionar**, forneça um nome exclusivo para o resultado.</span><span class="sxs-lookup"><span data-stu-id="651bc-134">After you have added a result by clicking **Add**, provide a unique name for the result.</span></span>  
  
 <span data-ttu-id="651bc-135">**Nome da Variável**</span><span class="sxs-lookup"><span data-stu-id="651bc-135">**Variable Name**</span></span>  
 <span data-ttu-id="651bc-136">Selecione uma variável na lista para mapeá-la para o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="651bc-136">Select a variable in the list to map it to the result set.</span></span>  
  
 <span data-ttu-id="651bc-137">**Tipo de resultado**</span><span class="sxs-lookup"><span data-stu-id="651bc-137">**Result Type**</span></span>  
 <span data-ttu-id="651bc-138">Indique se deve ser retornada uma única linha ou um conjunto de resultados completo.</span><span class="sxs-lookup"><span data-stu-id="651bc-138">Indicate whether to return a single row or a full result set.</span></span>  
  
 <span data-ttu-id="651bc-139">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="651bc-139">**Add**</span></span>  
 <span data-ttu-id="651bc-140">Adicione um conjunto de resultados à lista.</span><span class="sxs-lookup"><span data-stu-id="651bc-140">Add a result set to the list.</span></span>  
  
 <span data-ttu-id="651bc-141">**Remover**</span><span class="sxs-lookup"><span data-stu-id="651bc-141">**Remove**</span></span>  
 <span data-ttu-id="651bc-142">Selecione um resultado e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="651bc-142">Select a result, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="651bc-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="651bc-143">See Also</span></span>  
 <span data-ttu-id="651bc-144">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="651bc-144">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="651bc-145">[Editor da tarefa consulta de mineração de dados &#40;guia modelo de mineração&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span><span class="sxs-lookup"><span data-stu-id="651bc-145">[Data Mining Query Task Editor &#40;Mining Model Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span></span>  
 <span data-ttu-id="651bc-146">[Editor da tarefa consulta de mineração de dados &#40;guia saída&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span><span class="sxs-lookup"><span data-stu-id="651bc-146">[Data Mining Query Task Editor &#40;Output Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span></span>  
 [<span data-ttu-id="651bc-147">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="651bc-147">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
