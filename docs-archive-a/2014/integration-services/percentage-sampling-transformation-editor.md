---
title: Editor de transformação amostragem percentual | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.percentagesamplingtransformation.f1
helpviewer_keywords:
- Percentage Sampling Transformation Editor
ms.assetid: 2c40d804-26a3-4d35-809b-bc923d83d451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c4dbd96ab952b6c88bdaa7bf56a0a2f1b3585c57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570096"
---
# <a name="percentage-sampling-transformation-editor"></a><span data-ttu-id="efc5e-102">Editor de Transformação Amostragem Percentual</span><span class="sxs-lookup"><span data-stu-id="efc5e-102">Percentage Sampling Transformation Editor</span></span>
  <span data-ttu-id="efc5e-103">Use a caixa de diálogo **Editor de Transformação Amostragem Percentual** para dividir parte de uma entrada em uma amostra, usando uma porcentagem de linhas especificada.</span><span class="sxs-lookup"><span data-stu-id="efc5e-103">Use the **Percentage Sampling Transformation Editor** dialog box to split part of an input into a sample using a specified percentage of rows.</span></span> <span data-ttu-id="efc5e-104">Essa transformação divide a entrada em duas saídas separadas.</span><span class="sxs-lookup"><span data-stu-id="efc5e-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="efc5e-105">Para saber mais sobre a transformação amostragem percentual, consulte [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="efc5e-105">To learn more about the percentage sampling transformation, see [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="efc5e-106">Opções</span><span class="sxs-lookup"><span data-stu-id="efc5e-106">Options</span></span>  
 <span data-ttu-id="efc5e-107">**Porcentagem de linhas**</span><span class="sxs-lookup"><span data-stu-id="efc5e-107">**Percentage of rows**</span></span>  
 <span data-ttu-id="efc5e-108">Especifique a porcentagem de linhas na entrada a usar como amostra.</span><span class="sxs-lookup"><span data-stu-id="efc5e-108">Specify the percentage of rows in the input to use as a sample.</span></span>  
  
 <span data-ttu-id="efc5e-109">O valor dessa propriedade pode ser especificado com uma expressão de propriedades.</span><span class="sxs-lookup"><span data-stu-id="efc5e-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="efc5e-110">**Nome de saída do exemplo**</span><span class="sxs-lookup"><span data-stu-id="efc5e-110">**Sample output name**</span></span>  
 <span data-ttu-id="efc5e-111">Forneça um nome exclusivo para a saída que incluirá as linhas de amostra.</span><span class="sxs-lookup"><span data-stu-id="efc5e-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="efc5e-112">O nome fornecido será exibido no Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="efc5e-112">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="efc5e-113">**Nome de saída não selecionado**</span><span class="sxs-lookup"><span data-stu-id="efc5e-113">**Unselected output name**</span></span>  
 <span data-ttu-id="efc5e-114">Forneça um nome exclusivo para a saída que conterá as linhas excluídas da amostragem.</span><span class="sxs-lookup"><span data-stu-id="efc5e-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="efc5e-115">O nome fornecido será exibido no Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="efc5e-115">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="efc5e-116">**Usar a seguinte semente aleatória**</span><span class="sxs-lookup"><span data-stu-id="efc5e-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="efc5e-117">Especifique a semente de amostra para o gerador de números aleatórios que a transformação usa para criar uma amostra.</span><span class="sxs-lookup"><span data-stu-id="efc5e-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="efc5e-118">Recomendado apenas para desenvolvimento e teste.</span><span class="sxs-lookup"><span data-stu-id="efc5e-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="efc5e-119">A transformação usará a contagem de tiques do Microsoft Windows se não for especificada uma semente aleatória.</span><span class="sxs-lookup"><span data-stu-id="efc5e-119">The transformation uses the Microsoft Windows tick count if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc5e-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="efc5e-120">See Also</span></span>  
 <span data-ttu-id="efc5e-121">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="efc5e-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="efc5e-122">Transformação Amostragem de Linhas</span><span class="sxs-lookup"><span data-stu-id="efc5e-122">Row Sampling Transformation</span></span>](data-flow/transformations/row-sampling-transformation.md)  
  
  
