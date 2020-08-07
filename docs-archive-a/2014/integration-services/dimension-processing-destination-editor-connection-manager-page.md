---
title: Editor de destino de processamento de dimensões (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.connection.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 44aab631-d62d-4895-8fc7-7f1f3b1b68ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 50ba42292c1f48c9b1cdf2ba00c709dacd2f9675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583177"
---
# <a name="dimension-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="f7257-102">Editor de Destino de Processamento de Dimensões (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="f7257-102">Dimension Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="f7257-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Destino de Processamento de Dimensões** para especificar uma conexão com um projeto do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7257-103">Use the **Connection Manager** page of the **Dimension Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f7257-104">Para saber mais sobre o destino de Processamento de Dimensões, consulte [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="f7257-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f7257-105">Opções</span><span class="sxs-lookup"><span data-stu-id="f7257-105">Options</span></span>  
 <span data-ttu-id="f7257-106">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="f7257-106">**Connection manager**</span></span>  
 <span data-ttu-id="f7257-107">Selecione um gerenciador de conexões existente na lista ou clique em **Novo** para criar um novo gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="f7257-107">Select an existing connection manager from the list, or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="f7257-108">**Novo**</span><span class="sxs-lookup"><span data-stu-id="f7257-108">**New**</span></span>  
 <span data-ttu-id="f7257-109">Crie uma nova conexão usando a caixa de diálogo **Adicionar Gerenciador de Conexões do Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="f7257-109">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="f7257-110">**Lista de dimensões disponíveis**</span><span class="sxs-lookup"><span data-stu-id="f7257-110">**List of available dimensions**</span></span>  
 <span data-ttu-id="f7257-111">Selecione a dimensão a processar.</span><span class="sxs-lookup"><span data-stu-id="f7257-111">Select the dimension to process.</span></span>  
  
 <span data-ttu-id="f7257-112">**Método de processamento**</span><span class="sxs-lookup"><span data-stu-id="f7257-112">**Processing method**</span></span>  
 <span data-ttu-id="f7257-113">Selecione o método de processamento a aplicar à dimensão selecionada na lista.</span><span class="sxs-lookup"><span data-stu-id="f7257-113">Select the processing method to apply to the dimension selected in the list.</span></span> <span data-ttu-id="f7257-114">O valor padrão desta opção é **Completo**.</span><span class="sxs-lookup"><span data-stu-id="f7257-114">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="f7257-115">Valor</span><span class="sxs-lookup"><span data-stu-id="f7257-115">Value</span></span>|<span data-ttu-id="f7257-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7257-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f7257-117">**Adicionar (incremental)**</span><span class="sxs-lookup"><span data-stu-id="f7257-117">**Add (incremental)**</span></span>|<span data-ttu-id="f7257-118">Execute um processamento com incremento da dimensão.</span><span class="sxs-lookup"><span data-stu-id="f7257-118">Perform an incremental processing of the dimension.</span></span>|  
|<span data-ttu-id="f7257-119">**Full**</span><span class="sxs-lookup"><span data-stu-id="f7257-119">**Full**</span></span>|<span data-ttu-id="f7257-120">Execute um processamento completo da dimensão.</span><span class="sxs-lookup"><span data-stu-id="f7257-120">Perform full processing of the dimension.</span></span>|  
|<span data-ttu-id="f7257-121">**Atualização**</span><span class="sxs-lookup"><span data-stu-id="f7257-121">**Update**</span></span>|<span data-ttu-id="f7257-122">Execute um processamento de atualização da dimensão.</span><span class="sxs-lookup"><span data-stu-id="f7257-122">Perform an update processing of the dimension.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7257-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f7257-123">See Also</span></span>  
 <span data-ttu-id="f7257-124">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f7257-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="f7257-125">[Editor de destino de processamento de dimensões &#40;página Mapeamentos&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="f7257-125">[Dimension Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="f7257-126">Editor de Destino de Processamento de Dimensões &#40;Página Avançado&#41;</span><span class="sxs-lookup"><span data-stu-id="f7257-126">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-advanced-page.md)  
  
  
