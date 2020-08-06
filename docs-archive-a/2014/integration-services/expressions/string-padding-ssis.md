---
title: Preenchimento de cadeia (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- padding strings [Integration Services]
- expressions [Integration Services], string padding
- string padding
ms.assetid: d3fed73d-e0d4-4c67-9355-fb7083a72dd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3985fd1b2f29260e2313a761797d2528f5d0e328
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681008"
---
# <a name="string-padding-ssis"></a><span data-ttu-id="e8687-102">Preenchimento de cadeia (SSIS)</span><span class="sxs-lookup"><span data-stu-id="e8687-102">String Padding (SSIS)</span></span>
  <span data-ttu-id="e8687-103">O avaliador de expressão não verifica se uma cadeia de caracteres contém espaços à esquerda e à direita, e não preenche as cadeias de caracteres para que fiquem com o mesmo comprimento antes de compará-las.</span><span class="sxs-lookup"><span data-stu-id="e8687-103">The expression evaluator does not check if a string contains leading and trailing spaces, and it does not pad strings to make them the same length before it compares them.</span></span> <span data-ttu-id="e8687-104">Se as expressões exigirem preenchimento de cadeia de caracteres, você poderá usar o operador + para concatenar valores de coluna e cadeias de caracteres vazias.</span><span class="sxs-lookup"><span data-stu-id="e8687-104">If expressions requires string padding, you can use the + operator to concatenate column values and blank strings.</span></span> <span data-ttu-id="e8687-105">Para obter mais informações, consulte [+ &#40;Concatenar&#41; &#40;Expressão SSIS&#41;](concatenate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="e8687-105">For more information, see [+ &#40;Concatenate&#41; &#40;SSIS Expression&#41;](concatenate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="e8687-106">Por ouro lado, se você quiser remover espaços, o avaliador de expressão fornece as funções LTRIM, RTRIM e TRIM, que removem os espaços à esquerda e/ou à direita.</span><span class="sxs-lookup"><span data-stu-id="e8687-106">On the other hand, if you want to remove spaces, the expression evaluator provides the LTRIM, RTRIM, and TRIM functions, which remove leading or trailing spaces, or both.</span></span> <span data-ttu-id="e8687-107">Para obter mais informações, consulte [LTRIM &#40;Expressão SSIS&#41;](trim-ssis-expression.md), [RTRIM &#40;Expressão SSIS&#41;](rtrim-ssis-expression.md) e [TRIM &#40;Expressão SSIS&#41;](trim-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="e8687-107">For more information, see [LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md), [RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md), and [TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8687-108">A função LEN inclui espaços em branco à esquerda e à direita em sua conta.</span><span class="sxs-lookup"><span data-stu-id="e8687-108">The LEN function includes leading and trailing blanks in its count.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="e8687-109">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="e8687-109">Related Content</span></span>  
 <span data-ttu-id="e8687-110">Artigo técnico, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
), em pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="e8687-110">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet
), on pragmaticworks.com</span></span>  
  
  
