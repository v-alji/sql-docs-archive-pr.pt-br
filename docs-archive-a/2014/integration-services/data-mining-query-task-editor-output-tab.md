---
title: Editor da tarefa consulta de mineração de dados (guia saída) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.output.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 62f9e015-6fe0-4396-ad90-3ad51bf00025
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1508972b0487daa90f52af723d58185944a19a58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684262"
---
# <a name="data-mining-query-task-editor-output-tab"></a><span data-ttu-id="fc9e6-102">Editor da Tarefa Consulta de Mineração de Dados (guia Saída)</span><span class="sxs-lookup"><span data-stu-id="fc9e6-102">Data Mining Query Task Editor (Output Tab)</span></span>
  <span data-ttu-id="fc9e6-103">Use a guia **Saída** da caixa de diálogo **Editor da Tarefa Consulta de Mineração de Dados** para especificar o destino da consulta de previsão.</span><span class="sxs-lookup"><span data-stu-id="fc9e6-103">Use the **Output** tab of the **Data Mining Query Task Editor** dialog box to specify the destination of the prediction query.</span></span>  
  
 <span data-ttu-id="fc9e6-104">Para saber mais sobre como implementar a mineração de dados em pacotes, consulte [Tarefa Consulta de mineração de dados](control-flow/data-mining-query-task.md) e [Soluções de mineração de dados](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="fc9e6-104">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="fc9e6-105">Opções gerais</span><span class="sxs-lookup"><span data-stu-id="fc9e6-105">General Options</span></span>  
 <span data-ttu-id="fc9e6-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fc9e6-106">**Name**</span></span>  
 <span data-ttu-id="fc9e6-107">Forneça um nome exclusivo para a tarefa Consulta de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="fc9e6-107">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="fc9e6-108">Esse nome é usado como rótulo no ícone de tarefa.</span><span class="sxs-lookup"><span data-stu-id="fc9e6-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc9e6-109">Os nomes das tarefas devem ser exclusivos em um pacote.</span><span class="sxs-lookup"><span data-stu-id="fc9e6-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="fc9e6-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fc9e6-110">**Description**</span></span>  
 <span data-ttu-id="fc9e6-111">Digite uma descrição para a tarefa Consulta de Mineração de Dados.</span><span class="sxs-lookup"><span data-stu-id="fc9e6-111">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="output-tab-options"></a><span data-ttu-id="fc9e6-112">Opções da guia Saída</span><span class="sxs-lookup"><span data-stu-id="fc9e6-112">Output Tab Options</span></span>  
 <span data-ttu-id="fc9e6-113">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="fc9e6-113">**Connection**</span></span>  
 <span data-ttu-id="fc9e6-114">Selecione um gerenciador de conexões na lista ou clique em **Novo** para criar um novo gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="fc9e6-114">Select a connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="fc9e6-115">**Novo**</span><span class="sxs-lookup"><span data-stu-id="fc9e6-115">**New**</span></span>  
 <span data-ttu-id="fc9e6-116">Crie um novo gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="fc9e6-116">Create a new connection manager.</span></span> <span data-ttu-id="fc9e6-117">Só podem ser usados os tipos de gerenciador de conexões ADO.NET e OLE DB.</span><span class="sxs-lookup"><span data-stu-id="fc9e6-117">Only the ADO.NET and OLE DB connection manager types can be used.</span></span>  
  
 <span data-ttu-id="fc9e6-118">**Tabela de saída**</span><span class="sxs-lookup"><span data-stu-id="fc9e6-118">**Output table**</span></span>  
 <span data-ttu-id="fc9e6-119">Especifique a tabela na qual a consulta de previsão deve gravar seus resultados.</span><span class="sxs-lookup"><span data-stu-id="fc9e6-119">Specify the table to which the prediction query writes its results.</span></span>  
  
 <span data-ttu-id="fc9e6-120">**Ignorar e recriar tabela de saída**</span><span class="sxs-lookup"><span data-stu-id="fc9e6-120">**Drop and re-create the output table**</span></span>  
 <span data-ttu-id="fc9e6-121">Indique se a consulta de previsão deve substituir o conteúdo na tabela de destino, ignorando e, em seguida, recriando a tabela.</span><span class="sxs-lookup"><span data-stu-id="fc9e6-121">Indicate whether the prediction query should overwrite content in the destination table by dropping and then re-creating the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc9e6-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fc9e6-122">See Also</span></span>  
 <span data-ttu-id="fc9e6-123">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fc9e6-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="fc9e6-124">[Editor da tarefa consulta de mineração de dados &#40;guia modelo de mineração&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span><span class="sxs-lookup"><span data-stu-id="fc9e6-124">[Data Mining Query Task Editor &#40;Mining Model Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span></span>  
 <span data-ttu-id="fc9e6-125">[Editor da tarefa consulta de mineração de dados &#40;guia consulta&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span><span class="sxs-lookup"><span data-stu-id="fc9e6-125">[Data Mining Query Task Editor &#40;Query Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span></span>  
 [<span data-ttu-id="fc9e6-126">Data Mining Designer</span><span class="sxs-lookup"><span data-stu-id="fc9e6-126">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
