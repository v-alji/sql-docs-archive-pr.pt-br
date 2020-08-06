---
title: Editor de destino de processamento de partições (página Mapeamentos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.mapping.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: e75b766c-85ba-453e-9576-4a1a34f91ecc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3855b15c7ebf1f6fa95c941931869064d552680e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582522"
---
# <a name="partition-processing-destination-editor-mappings-page"></a><span data-ttu-id="09add-102">Editor de Destino de Processamento de Partições (Página Mapeamentos)</span><span class="sxs-lookup"><span data-stu-id="09add-102">Partition Processing Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="09add-103">Use a página **Mapeamentos** da caixa de diálogo **Editor de Destino de Processamento de Partições** para mapear colunas de entrada para colunas de partições.</span><span class="sxs-lookup"><span data-stu-id="09add-103">Use the **Mappings** page of the **Partition Processing Destination Editor** dialog box to map input columns to partition columns.</span></span>  
  
 <span data-ttu-id="09add-104">Para saber mais sobre o destino de Processamento de Partições, consulte [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="09add-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09add-105">As tarefas descritas aqui não se aplicam a modelos de tabela do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="09add-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="09add-106">Você não pode mapear colunas de entrada para as colunas de partição em modelos de tabela.</span><span class="sxs-lookup"><span data-stu-id="09add-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="09add-107">Você pode usar a tarefa Executar DDL do Analysis Services [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) para processar a partição.</span><span class="sxs-lookup"><span data-stu-id="09add-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="09add-108">Opções</span><span class="sxs-lookup"><span data-stu-id="09add-108">Options</span></span>  
 <span data-ttu-id="09add-109">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="09add-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="09add-110">Exiba a lista das colunas de entrada disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09add-110">View the list of available input columns.</span></span> <span data-ttu-id="09add-111">Use uma operação de arrastar e soltar para mapear colunas de entrada disponíveis na tabela para as colunas de destino.</span><span class="sxs-lookup"><span data-stu-id="09add-111">Use a drag-and-drop operation to map available input columns in the table to destination columns.</span></span>  
  
 <span data-ttu-id="09add-112">**Colunas de Destino Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="09add-112">**Available Destination Columns**</span></span>  
 <span data-ttu-id="09add-113">Exiba a lista de colunas de destino disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09add-113">View the list of available destination columns.</span></span> <span data-ttu-id="09add-114">Use uma operação de arrastar e soltar para mapear as colunas de destino disponíveis na tabela para as colunas de entrada.</span><span class="sxs-lookup"><span data-stu-id="09add-114">Use a drag-and-drop operation to map available destination columns in the table to input columns.</span></span>  
  
 <span data-ttu-id="09add-115">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="09add-115">**Input Column**</span></span>  
 <span data-ttu-id="09add-116">Exibir colunas de entrada selecionadas na tabela acima.</span><span class="sxs-lookup"><span data-stu-id="09add-116">View input columns selected from the table above.</span></span> <span data-ttu-id="09add-117">É possível alterar os mapeamentos usando a lista **Colunas de Entrada Disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="09add-117">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="09add-118">**Coluna de Destino**</span><span class="sxs-lookup"><span data-stu-id="09add-118">**Destination Column**</span></span>  
 <span data-ttu-id="09add-119">Exiba cada coluna de destino disponível, seja ela mapeada ou não.</span><span class="sxs-lookup"><span data-stu-id="09add-119">View each available destination column, whether it is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09add-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="09add-120">See Also</span></span>  
 <span data-ttu-id="09add-121">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="09add-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="09add-122">[Editor de destino de processamento de partições &#40;página Gerenciador de conexões&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="09add-122">[Partition Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="09add-123">Editor de Destino de Processamento de Partições &#40;Página Avançado&#41;</span><span class="sxs-lookup"><span data-stu-id="09add-123">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
