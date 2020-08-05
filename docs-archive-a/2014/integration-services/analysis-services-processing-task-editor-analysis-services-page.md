---
title: Editor da tarefa de processamento de Analysis Services (página Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asprocessingtask.as.f1
helpviewer_keywords:
- Analysis Services Processing Task Editor
ms.assetid: 5612be78-57cf-4e4e-92cf-6bfa9f971040
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aabcfe286b40f58b429227654107d58e8a4ee837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571527"
---
# <a name="analysis-services-processing-task-editor-analysis-services-page"></a><span data-ttu-id="eddf0-102">Editor da Tarefa Processamento do Analysis Services (página Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="eddf0-102">Analysis Services Processing Task Editor (Analysis Services Page)</span></span>
  <span data-ttu-id="eddf0-103">Use a página **Analysis Services** da caixa de diálogo **Editor da Tarefa Processamento do Analysis Services** para especificar um gerenciador de conexões do Analysis Services, selecione os objetos analíticos a serem processados e defina as opções de processamento e manipulação de erros.</span><span class="sxs-lookup"><span data-stu-id="eddf0-103">Use the **Analysis Services** page of the **Analysis Services Processing Task Editor** dialog box to specify an Analysis Services connection manager, select the analytic objects to process, and set processing and error handling options.</span></span>  
  
 <span data-ttu-id="eddf0-104">Lembre-se do seguinte quando for processar modelos tabulares:</span><span class="sxs-lookup"><span data-stu-id="eddf0-104">When processing tabular models, keep the following in mind:</span></span>  
  
1.  <span data-ttu-id="eddf0-105">Você não pode executar a análise de impacto em modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="eddf0-105">You cannot perform impact analysis on tabular models.</span></span>  
  
2.  <span data-ttu-id="eddf0-106">Algumas opções de processamento para modo tabular não são expostas, como Processar Desfragmentação e Processar Recálculo.</span><span class="sxs-lookup"><span data-stu-id="eddf0-106">Some processing options for tabular mode are not exposed, such as Process Defrag and Process Recalc.</span></span> <span data-ttu-id="eddf0-107">Você pode executar essas funções usando a tarefa Executar DDL.</span><span class="sxs-lookup"><span data-stu-id="eddf0-107">You can perform these functions by using the Execute DDL task.</span></span>  
  
3.  <span data-ttu-id="eddf0-108">Algumas opções de processamento fornecidas, como índices de processo, não são apropriadas para modelos tabulares e não devem ser usadas.</span><span class="sxs-lookup"><span data-stu-id="eddf0-108">Some processing options provided, such as process indexes, are not appropriate for tabular models and should not be used.</span></span>  
  
4.  <span data-ttu-id="eddf0-109">As configurações de lote para modelos tabulares são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="eddf0-109">Batch settings are ignored for tabular models.</span></span>  
  
 <span data-ttu-id="eddf0-110">Para obter informações sobre essa tarefa, consulte [Analysis Services Processing Task](control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="eddf0-110">To learn about this task, see [Analysis Services Processing Task](control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="eddf0-111">Opções</span><span class="sxs-lookup"><span data-stu-id="eddf0-111">Options</span></span>  
 <span data-ttu-id="eddf0-112">**Gerenciador de conexões Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="eddf0-112">**Analysis Services connection manager**</span></span>  
 <span data-ttu-id="eddf0-113">Selecione na lista um gerenciador de conexões do Analysis Services existente ou clique em **Novo** para criar um novo gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="eddf0-113">Select an existing Analysis Services connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="eddf0-114">**Novo**</span><span class="sxs-lookup"><span data-stu-id="eddf0-114">**New**</span></span>  
 <span data-ttu-id="eddf0-115">Cria um novo gerenciador de conexões do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="eddf0-115">Create a new Analysis Services connection manager.</span></span>  
  
 <span data-ttu-id="eddf0-116">**Tópicos relacionados:** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Referência da interface do usuário da caixa de diálogo Adicionar Gerenciador de Conexões do Analysis Services](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span><span class="sxs-lookup"><span data-stu-id="eddf0-116">**Related Topics:** [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md), [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span></span>  
  
 <span data-ttu-id="eddf0-117">**Lista de objetos**</span><span class="sxs-lookup"><span data-stu-id="eddf0-117">**Object list**</span></span>  
 |<span data-ttu-id="eddf0-118">Propriedade</span><span class="sxs-lookup"><span data-stu-id="eddf0-118">Property</span></span>|<span data-ttu-id="eddf0-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="eddf0-119">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="eddf0-120">**Object Name**</span><span class="sxs-lookup"><span data-stu-id="eddf0-120">**Object Name**</span></span>|<span data-ttu-id="eddf0-121">Lista os nomes de objeto especificados.</span><span class="sxs-lookup"><span data-stu-id="eddf0-121">Lists the specified object names.</span></span>|  
|<span data-ttu-id="eddf0-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="eddf0-122">**Type**</span></span>|<span data-ttu-id="eddf0-123">Lista os tipos dos objetos especificados.</span><span class="sxs-lookup"><span data-stu-id="eddf0-123">Lists the types of the specified objects.</span></span>|  
|<span data-ttu-id="eddf0-124">**Opções de Processo**</span><span class="sxs-lookup"><span data-stu-id="eddf0-124">**Process Options**</span></span>|<span data-ttu-id="eddf0-125">Selecione uma opção de processamento na lista.</span><span class="sxs-lookup"><span data-stu-id="eddf0-125">Select a processing option in the list.</span></span><br /><br /> <span data-ttu-id="eddf0-126">**Tópicos relacionados**: [processamento de objeto de modelo multidimensional](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span><span class="sxs-lookup"><span data-stu-id="eddf0-126">**Related Topics**: [Multidimensional Model Object Processing](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services)</span></span>|  
|<span data-ttu-id="eddf0-127">**Configurações**</span><span class="sxs-lookup"><span data-stu-id="eddf0-127">**Settings**</span></span>|<span data-ttu-id="eddf0-128">Lista configurações de processamento para os objetos especificados.</span><span class="sxs-lookup"><span data-stu-id="eddf0-128">Lists processing settings for the specified objects.</span></span>|  
  
 <span data-ttu-id="eddf0-129">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="eddf0-129">**Add**</span></span>  
 <span data-ttu-id="eddf0-130">Adicione à lista um objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eddf0-130">Add an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object to the list.</span></span>  
  
 <span data-ttu-id="eddf0-131">**Remover**</span><span class="sxs-lookup"><span data-stu-id="eddf0-131">**Remove**</span></span>  
 <span data-ttu-id="eddf0-132">Selecione um objeto e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="eddf0-132">Select an object, and then click **Delete**.</span></span>  
  
 <span data-ttu-id="eddf0-133">**Análise de Impacto**</span><span class="sxs-lookup"><span data-stu-id="eddf0-133">**Impact Analysis**</span></span>  
 <span data-ttu-id="eddf0-134">Execute uma análise de impacto no objeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="eddf0-134">Perform impact analysis on the selected object.</span></span>  
  
 <span data-ttu-id="eddf0-135">**Tópicos relacionados:** [Caixa de diálogo Análise de Impacto &#40;Analysis Services – Dados Multidimensionais&#41;](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="eddf0-135">**Related Topics:** [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/impact-analysis-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
 <span data-ttu-id="eddf0-136">**Resumo de Configurações de Lote**</span><span class="sxs-lookup"><span data-stu-id="eddf0-136">**Batch Settings Summary**</span></span>  
 |<span data-ttu-id="eddf0-137">Propriedade</span><span class="sxs-lookup"><span data-stu-id="eddf0-137">Property</span></span>|<span data-ttu-id="eddf0-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="eddf0-138">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="eddf0-139">**Ordem de processamento**</span><span class="sxs-lookup"><span data-stu-id="eddf0-139">**Processing order**</span></span>|<span data-ttu-id="eddf0-140">Especifica se os objetos são processados em sequência ou em um lote; se for usado o processamento paralelo, especifica o número de objetos a serem processados simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="eddf0-140">Specifies whether objects are processed sequentially or in a batch; if parallel processing is used, specifies the number of objects to process concurrently.</span></span>|  
|<span data-ttu-id="eddf0-141">**Modo de transação**</span><span class="sxs-lookup"><span data-stu-id="eddf0-141">**Transaction mode**</span></span>|<span data-ttu-id="eddf0-142">Especifica o modo da transação para processamento sequencial.</span><span class="sxs-lookup"><span data-stu-id="eddf0-142">Specifies the transaction mode for sequential processing.</span></span>|  
|<span data-ttu-id="eddf0-143">**Erros de dimensão**</span><span class="sxs-lookup"><span data-stu-id="eddf0-143">**Dimension errors**</span></span>|<span data-ttu-id="eddf0-144">Especifica o comportamento da tarefa quando ocorrem erros.</span><span class="sxs-lookup"><span data-stu-id="eddf0-144">Specifies the task behavior when errors occur.</span></span>|  
|<span data-ttu-id="eddf0-145">**Caminho do log de erros da chave de dimensão**</span><span class="sxs-lookup"><span data-stu-id="eddf0-145">**Dimension key error log path**</span></span>|<span data-ttu-id="eddf0-146">Especifica o caminho do arquivo no qual são feitos logs de erros.</span><span class="sxs-lookup"><span data-stu-id="eddf0-146">Specifies the path of the file to which errors are logged.</span></span>|  
|<span data-ttu-id="eddf0-147">**Objetos afetados pelo processo**</span><span class="sxs-lookup"><span data-stu-id="eddf0-147">**Process affected objects**</span></span>|<span data-ttu-id="eddf0-148">Indica se também são processados objetos dependentes ou afetados.</span><span class="sxs-lookup"><span data-stu-id="eddf0-148">Indicates whether dependent or affected objects are also processed.</span></span>|  
  
 <span data-ttu-id="eddf0-149">**Alterar configurações**</span><span class="sxs-lookup"><span data-stu-id="eddf0-149">**Change Settings**</span></span>  
 <span data-ttu-id="eddf0-150">Altere as opções de processamento e a manipulação de erros em chaves de dimensão.</span><span class="sxs-lookup"><span data-stu-id="eddf0-150">Change the processing options and the handling of errors in dimension keys.</span></span>  
  
 <span data-ttu-id="eddf0-151">**Tópicos relacionados:** [Caixa de diálogo Alterar Configurações &#40;Analysis Services – Dados Multidimensionais&#41;](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span><span class="sxs-lookup"><span data-stu-id="eddf0-151">**Related Topics:** [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/change-settings-dialog-box-analysis-services-multidimensional-data.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eddf0-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eddf0-152">See Also</span></span>  
 <span data-ttu-id="eddf0-153">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="eddf0-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="eddf0-154">[Editor da tarefa de processamento de Analysis Services &#40;página Geral&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="eddf0-154">[Analysis Services Processing Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="eddf0-155">Tarefa Executar DDL do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="eddf0-155">Analysis Services Execute DDL Task</span></span>](control-flow/analysis-services-execute-ddl-task.md)  
  
  
