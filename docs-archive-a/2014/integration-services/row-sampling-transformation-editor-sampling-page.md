---
title: Editor de transformação amostragem de linhas (página amostragem) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ROWSAMPLINGTRANSFORMATION.COLUMNS.F1
- sql12.dts.designer.rowsamplingtransformation.f1
helpviewer_keywords:
- Row Sampling Transformation Editor
ms.assetid: 544c7709-6de0-4c08-bda3-759985be9a05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 26d0c0439e548172225f02220d8f6814a1168ea9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679406"
---
# <a name="row-sampling-transformation-editor-sampling-page"></a><span data-ttu-id="bc91e-102">Editor de Transformação Amostragem de Linhas (página Amostragem)</span><span class="sxs-lookup"><span data-stu-id="bc91e-102">Row Sampling Transformation Editor (Sampling Page)</span></span>
  <span data-ttu-id="bc91e-103">Use a caixa de diálogo **Editor de Transformação Amostragem de Linhas** para dividir uma parte de uma entrada em uma amostra usando um número de linhas especificado.</span><span class="sxs-lookup"><span data-stu-id="bc91e-103">Use the **Row Sampling Transformation Editor** dialog box to split a portion of an input into a sample using a specified number of rows.</span></span> <span data-ttu-id="bc91e-104">Essa transformação divide a entrada em duas saídas separadas.</span><span class="sxs-lookup"><span data-stu-id="bc91e-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="bc91e-105">Para saber mais sobre a transformação Amostragem de Linhas, consulte [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="bc91e-105">To learn more about the Row Sampling transformation, see [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bc91e-106">Opções</span><span class="sxs-lookup"><span data-stu-id="bc91e-106">Options</span></span>  
 <span data-ttu-id="bc91e-107">**Número de linhas**</span><span class="sxs-lookup"><span data-stu-id="bc91e-107">**Number of rows**</span></span>  
 <span data-ttu-id="bc91e-108">Especifique o número de linhas da entrada a serem usadas como amostra.</span><span class="sxs-lookup"><span data-stu-id="bc91e-108">Specify the number of rows from the input to use as a sample.</span></span>  
  
 <span data-ttu-id="bc91e-109">O valor dessa propriedade pode ser especificado com uma expressão de propriedades.</span><span class="sxs-lookup"><span data-stu-id="bc91e-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="bc91e-110">**Nome de saída do exemplo**</span><span class="sxs-lookup"><span data-stu-id="bc91e-110">**Sample output name**</span></span>  
 <span data-ttu-id="bc91e-111">Forneça um nome exclusivo para a saída que incluirá as linhas de amostra.</span><span class="sxs-lookup"><span data-stu-id="bc91e-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="bc91e-112">O nome fornecido será exibido no Designer SSIS.</span><span class="sxs-lookup"><span data-stu-id="bc91e-112">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="bc91e-113">**Nome de saída não selecionado**</span><span class="sxs-lookup"><span data-stu-id="bc91e-113">**Unselected output name**</span></span>  
 <span data-ttu-id="bc91e-114">Forneça um nome exclusivo para a saída que conterá as linhas excluídas da amostragem.</span><span class="sxs-lookup"><span data-stu-id="bc91e-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="bc91e-115">O nome fornecido será exibido no Designer SSIS.</span><span class="sxs-lookup"><span data-stu-id="bc91e-115">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="bc91e-116">**Usar a seguinte semente aleatória**</span><span class="sxs-lookup"><span data-stu-id="bc91e-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="bc91e-117">Especifique a semente de amostra para o gerador de números aleatórios que a transformação usa para criar uma amostra.</span><span class="sxs-lookup"><span data-stu-id="bc91e-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="bc91e-118">Recomendado apenas para desenvolvimento e teste.</span><span class="sxs-lookup"><span data-stu-id="bc91e-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="bc91e-119">A transformação usará a contagem de tiques do Microsoft Windows como semente se não for especificada uma semente aleatória.</span><span class="sxs-lookup"><span data-stu-id="bc91e-119">The transformation uses the Microsoft Windows tick count as a seed if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc91e-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bc91e-120">See Also</span></span>  
 <span data-ttu-id="bc91e-121">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bc91e-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="bc91e-122">Transformação Amostragem Percentual</span><span class="sxs-lookup"><span data-stu-id="bc91e-122">Percentage Sampling Transformation</span></span>](data-flow/transformations/percentage-sampling-transformation.md)  
  
  
