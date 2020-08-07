---
title: LEFT (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5634dbfb-740d-4c93-8fd5-2854cc741327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f21d134988414c7d8579d720877feec45383270
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582010"
---
# <a name="left-ssis-expression"></a><span data-ttu-id="71db9-102">LEFT (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="71db9-102">LEFT (SSIS Expression)</span></span>
  <span data-ttu-id="71db9-103">Retorna o número especificado de caracteres da parte mais à esquerda da expressão character especificada.</span><span class="sxs-lookup"><span data-stu-id="71db9-103">Returns the specified number of characters from the leftmost portion of the given character expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71db9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="71db9-104">Syntax</span></span>  
  
```  
  
LEFT(character_expression,number)  
```  
  
## <a name="arguments"></a><span data-ttu-id="71db9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="71db9-105">Arguments</span></span>  
 <span data-ttu-id="71db9-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="71db9-106">*character_expression*</span></span>  
 <span data-ttu-id="71db9-107">É uma expressão de caractere da qual extrair caracteres.</span><span class="sxs-lookup"><span data-stu-id="71db9-107">Is a character expression from which to extract characters.</span></span>  
  
 <span data-ttu-id="71db9-108">*number*</span><span class="sxs-lookup"><span data-stu-id="71db9-108">*number*</span></span>  
 <span data-ttu-id="71db9-109">É uma expressão de inteiro que indica o número de caracteres retornados.</span><span class="sxs-lookup"><span data-stu-id="71db9-109">Is an integer expression that indicates the number of characters to be returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="71db9-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="71db9-110">Result Types</span></span>  
 <span data-ttu-id="71db9-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="71db9-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71db9-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="71db9-112">Remarks</span></span>  
 <span data-ttu-id="71db9-113">Se *number* for maior que o comprimento de *character_expression*, a função retornará *character_expression*.</span><span class="sxs-lookup"><span data-stu-id="71db9-113">If *number* is greater than the length of *character_expression*, the function returns *character_expression*.</span></span>  
  
 <span data-ttu-id="71db9-114">Se *number* for zero, a função retornará uma cadeia de comprimento zero.</span><span class="sxs-lookup"><span data-stu-id="71db9-114">If *number* is zero, the function returns a zero-length string.</span></span>  
  
 <span data-ttu-id="71db9-115">Se *number* for um número negativo, a função retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="71db9-115">If *number* is a negative number, the function returns an error.</span></span>  
  
 <span data-ttu-id="71db9-116">O argumento *number* pode obter variáveis e colunas.</span><span class="sxs-lookup"><span data-stu-id="71db9-116">The *number* argument can take variables and columns.</span></span>  
  
 <span data-ttu-id="71db9-117">LEFT só funciona com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="71db9-117">LEFT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="71db9-118">Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes de LEFT executar sua operação.</span><span class="sxs-lookup"><span data-stu-id="71db9-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LEFT performs its operation.</span></span> <span data-ttu-id="71db9-119">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="71db9-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="71db9-120">Para obter mais informações, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="71db9-120">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="71db9-121">LEFT retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="71db9-121">LEFT returns a null result if either argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="71db9-122">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="71db9-122">Expression Examples</span></span>  
 <span data-ttu-id="71db9-123">O exemplo a seguir usa um literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="71db9-123">The following example uses a string literal.</span></span> <span data-ttu-id="71db9-124">O resultado de retorno é `"Mountain"`.</span><span class="sxs-lookup"><span data-stu-id="71db9-124">The return result is `"Mountain"`.</span></span>  
  
```  
LEFT("Mountain Bike", 8)  
```  
  
## <a name="see-also"></a><span data-ttu-id="71db9-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71db9-125">See Also</span></span>  
 <span data-ttu-id="71db9-126">[RIGHT &#40;Expressão SSIS&#41;](right-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="71db9-126">[RIGHT &#40;SSIS Expression&#41;](right-ssis-expression.md) </span></span>  
 [<span data-ttu-id="71db9-127">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="71db9-127">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
