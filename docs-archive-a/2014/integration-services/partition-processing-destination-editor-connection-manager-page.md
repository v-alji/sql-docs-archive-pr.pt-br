---
title: Editor de destino de processamento de partições (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.connection.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 7add6f82-eed1-47fc-a5d7-7b91f3f24d34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a0f79dfcc9c0d98d871a49618f4dabfb8a3bbac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573165"
---
# <a name="partition-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="42986-102">Editor de Destino de Processamento de Partições (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="42986-102">Partition Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="42986-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Destino de Processamento de Partições** para especificar uma conexão a um projeto do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou a uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42986-103">Use the **Connection Manager** page of the **Partition Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="42986-104">Para saber mais sobre o destino de Processamento de Partições, consulte [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="42986-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42986-105">As tarefas descritas aqui não se aplicam a modelos de tabela do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="42986-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="42986-106">Você não pode mapear colunas de entrada para as colunas de partição em modelos de tabela.</span><span class="sxs-lookup"><span data-stu-id="42986-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="42986-107">Você pode usar a tarefa Executar DDL do Analysis Services [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) para processar a partição.</span><span class="sxs-lookup"><span data-stu-id="42986-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="42986-108">Opções</span><span class="sxs-lookup"><span data-stu-id="42986-108">Options</span></span>  
 <span data-ttu-id="42986-109">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="42986-109">**Connection manager**</span></span>  
 <span data-ttu-id="42986-110">Selecione um gerenciador de conexões existente na lista ou crie uma nova conexão clicando em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="42986-110">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="42986-111">**Novo**</span><span class="sxs-lookup"><span data-stu-id="42986-111">**New**</span></span>  
 <span data-ttu-id="42986-112">Crie uma nova conexão usando a caixa de diálogo **Adicionar Gerenciador de Conexões do Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="42986-112">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="42986-113">**Lista de partições disponíveis**</span><span class="sxs-lookup"><span data-stu-id="42986-113">**List of available partitions**</span></span>  
 <span data-ttu-id="42986-114">Selecione a partição a processar.</span><span class="sxs-lookup"><span data-stu-id="42986-114">Select the partition to process.</span></span>  
  
 <span data-ttu-id="42986-115">**Método de processamento**</span><span class="sxs-lookup"><span data-stu-id="42986-115">**Processing method**</span></span>  
 <span data-ttu-id="42986-116">Selecione o método de processamento.</span><span class="sxs-lookup"><span data-stu-id="42986-116">Select the processing method.</span></span> <span data-ttu-id="42986-117">O valor padrão desta opção é **Completo**.</span><span class="sxs-lookup"><span data-stu-id="42986-117">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="42986-118">Valor</span><span class="sxs-lookup"><span data-stu-id="42986-118">Value</span></span>|<span data-ttu-id="42986-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="42986-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="42986-120">Adicionar (incremental)</span><span class="sxs-lookup"><span data-stu-id="42986-120">Add (incremental)</span></span>|<span data-ttu-id="42986-121">Execute um processamento com incremento da partição.</span><span class="sxs-lookup"><span data-stu-id="42986-121">Perform an incremental processing of the partition.</span></span>|  
|<span data-ttu-id="42986-122">Completo</span><span class="sxs-lookup"><span data-stu-id="42986-122">Full</span></span>|<span data-ttu-id="42986-123">Execute um processamento completo da partição.</span><span class="sxs-lookup"><span data-stu-id="42986-123">Perform full processing of the partition.</span></span>|  
|<span data-ttu-id="42986-124">Apenas dados</span><span class="sxs-lookup"><span data-stu-id="42986-124">Data only</span></span>|<span data-ttu-id="42986-125">Execute um processamento de atualização da partição.</span><span class="sxs-lookup"><span data-stu-id="42986-125">Perform an update processing of the partition.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42986-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="42986-126">See Also</span></span>  
 <span data-ttu-id="42986-127">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="42986-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="42986-128">[Editor de destino de processamento de partições &#40;página Mapeamentos&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="42986-128">[Partition Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="42986-129">Editor de Destino de Processamento de Partições &#40;Página Avançado&#41;</span><span class="sxs-lookup"><span data-stu-id="42986-129">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
