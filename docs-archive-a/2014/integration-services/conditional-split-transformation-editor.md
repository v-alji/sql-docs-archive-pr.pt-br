---
title: Editor de transformação Divisão condicional | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittransformation.f1
helpviewer_keywords:
- Conditional Split Transformation Editor
ms.assetid: c30e1633-537a-4837-9991-6203c6f2a21e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 386a93eb7c3058c7c3e98f2b652199d115d841f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570175"
---
# <a name="conditional-split-transformation-editor"></a><span data-ttu-id="c75f5-102">Editor de Transformação Divisão Condicional</span><span class="sxs-lookup"><span data-stu-id="c75f5-102">Conditional Split Transformation Editor</span></span>
  <span data-ttu-id="c75f5-103">Use a caixa de diálogo **Editor de Transformação Divisão Condicional** para criar expressões, definir a ordem na qual as expressões são avaliadas e nomear as saídas de uma divisão condicional.</span><span class="sxs-lookup"><span data-stu-id="c75f5-103">Use the **Conditional Split Transformation Editor** dialog box to create expressions, set the order in which expressions are evaluated, and name the outputs of a conditional split.</span></span> <span data-ttu-id="c75f5-104">Essa caixa de diálogo inclui funções matemáticas, de cadeia de caracteres e de data/hora e operadores que você pode usar para criar expressões.</span><span class="sxs-lookup"><span data-stu-id="c75f5-104">This dialog box includes mathematical, string, and date/time functions and operators that you can use to build expressions.</span></span> <span data-ttu-id="c75f5-105">A primeira condição avaliada como verdadeira determina a saída para a qual uma linha é direcionada.</span><span class="sxs-lookup"><span data-stu-id="c75f5-105">The first condition that evaluates as true determines the output to which a row is directed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c75f5-106">A transformação Divisão Condicional direciona cada fila de entrada para uma única de saída.</span><span class="sxs-lookup"><span data-stu-id="c75f5-106">The Conditional Split transformation directs each input row to one output only.</span></span> <span data-ttu-id="c75f5-107">Se você digitar condições múltiplas, a transformação enviará cada fila à primeira saída para a qual a condição é verdadeira e desconsiderará condições subsequentes para aquela fila.</span><span class="sxs-lookup"><span data-stu-id="c75f5-107">If you enter multiple conditions, the transformation sends each row to the first output for which the condition is true and disregards subsequent conditions for that row.</span></span> <span data-ttu-id="c75f5-108">Se for necessário avaliar várias condições sucessivamente, você poderá ter que concatenar transformações de Divisão Condicional múltiplas no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="c75f5-108">If you need to evaluate several conditions successively, you may need to concatenate multiple Conditional Split transformations in the data flow.</span></span>  
  
 <span data-ttu-id="c75f5-109">Para saber mais sobre a transformação Divisão Condicional, consulte [Transformação Divisão Condicional](data-flow/transformations/conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c75f5-109">To learn more about the Conditional Split transformation, see [Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c75f5-110">Opções</span><span class="sxs-lookup"><span data-stu-id="c75f5-110">Options</span></span>  
 <span data-ttu-id="c75f5-111">**Ordem**</span><span class="sxs-lookup"><span data-stu-id="c75f5-111">**Order**</span></span>  
 <span data-ttu-id="c75f5-112">Selecione uma fila e use as teclas de seta à direita para alterar a ordem de avaliação de expressões.</span><span class="sxs-lookup"><span data-stu-id="c75f5-112">Select a row and use the arrow keys at right to change the order in which to evaluate expressions.</span></span>  
  
 <span data-ttu-id="c75f5-113">**Nome da saída**</span><span class="sxs-lookup"><span data-stu-id="c75f5-113">**Output Name**</span></span>  
 <span data-ttu-id="c75f5-114">Forneça um nome de saída.</span><span class="sxs-lookup"><span data-stu-id="c75f5-114">Provide an output name.</span></span> <span data-ttu-id="c75f5-115">O padrão é uma lista numerada de casos; entretanto, você pode escolher qualquer nome exclusivo e descritivo.</span><span class="sxs-lookup"><span data-stu-id="c75f5-115">The default is a numbered list of cases; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="c75f5-116">**Condição**</span><span class="sxs-lookup"><span data-stu-id="c75f5-116">**Condition**</span></span>  
 <span data-ttu-id="c75f5-117">Digite uma expressão ou compile uma arrastando da lista de colunas, variáveis, funções e operadores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c75f5-117">Type an expression or build one by dragging from the list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="c75f5-118">O valor dessa propriedade pode ser especificado com uma expressão de propriedades.</span><span class="sxs-lookup"><span data-stu-id="c75f5-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="c75f5-119">\*\*Tópicos relacionados: \*\*  [Expressões do Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md), [Operadores &#40;Expressão SSIS&#41;](expressions/operators-ssis-expression.md) e [Funções &#40;Expressão SSIS&#41;](expressions/functions-ssis-expression.md)</span><span class="sxs-lookup"><span data-stu-id="c75f5-119">**Related topics:**  [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="c75f5-120">**Nome de saída padrão**</span><span class="sxs-lookup"><span data-stu-id="c75f5-120">**Default output name**</span></span>  
 <span data-ttu-id="c75f5-121">Digite um nome para a saída padrão ou use o padrão.</span><span class="sxs-lookup"><span data-stu-id="c75f5-121">Type a name for the default output, or use the default.</span></span>  
  
 <span data-ttu-id="c75f5-122">**Configurar saída de erro**</span><span class="sxs-lookup"><span data-stu-id="c75f5-122">**Configure error output**</span></span>  
 <span data-ttu-id="c75f5-123">Especifique como tratar os erros usando a caixa de diálogo [Configurar Saída de Erro](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="c75f5-123">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75f5-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c75f5-124">See Also</span></span>  
 <span data-ttu-id="c75f5-125">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c75f5-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="c75f5-126">Dividir um conjunto de dados por meio da transformação Divisão Condicional</span><span class="sxs-lookup"><span data-stu-id="c75f5-126">Split a Dataset by Using the Conditional Split Transformation</span></span>](data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  
