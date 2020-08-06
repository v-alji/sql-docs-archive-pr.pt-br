---
title: TRIM (expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- TRIM function
- trailing blanks
ms.assetid: 7dd9081d-a3d4-483a-bf7e-bf2bd7692d39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 42cef8a816f399e39ac99061f34c394156bde45f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680996"
---
# <a name="trim-ssis-expression"></a><span data-ttu-id="ca6b7-102">TRIM (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca6b7-102">TRIM (SSIS Expression)</span></span>
  <span data-ttu-id="ca6b7-103">Retorna uma expressão de caractere depois de remover espaços em branco à esquerda e direita.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-103">Returns a character expression after removing leading and trailing spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca6b7-104">TRIM não remove caracteres do espaço em branco como os caracteres de guia ou de alimentação de linha.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-104">TRIM does not remove white-space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="ca6b7-105">Unicode fornece pontos de código para muitos tipos diferentes de espaços, mas essa função reconhece somente o ponto de código Unicode 0x0020.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="ca6b7-106">Quando as cadeias de caracteres de DBCS (Conjunto de caracteres de byte duplo) são convertidas para Unicode, elas podem incluir caracteres de espaço diferentes de 0x0020, e a função não pode remover esses espaços.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="ca6b7-107">Para remover todos os tipos de espaços, você poderá usar o método Trim do Microsoft Visual Basic .NET em uma execução de script a partir do componente Script.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET Trim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca6b7-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ca6b7-108">Syntax</span></span>  
  
```  
  
TRIM(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="ca6b7-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ca6b7-109">Arguments</span></span>  
 <span data-ttu-id="ca6b7-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="ca6b7-110">*character_expression*</span></span>  
 <span data-ttu-id="ca6b7-111">É uma expressão de caractere da qual remover espaços.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ca6b7-112">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="ca6b7-112">Result Types</span></span>  
 <span data-ttu-id="ca6b7-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="ca6b7-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca6b7-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="ca6b7-114">Remarks</span></span>  
 <span data-ttu-id="ca6b7-115">TRIM retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-115">TRIM returns a null result if the argument is null.</span></span>  
  
 <span data-ttu-id="ca6b7-116">TRIM só funciona com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-116">TRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="ca6b7-117">Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes de TRIM executar sua operação.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-117">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TRIM performs its operation.</span></span> <span data-ttu-id="ca6b7-118">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-118">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="ca6b7-119">Para obter mais informações, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="ca6b7-119">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="ca6b7-120">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="ca6b7-120">Expression Examples</span></span>  
 <span data-ttu-id="ca6b7-121">Este exemplo remove espaços à direita e à esquerda de um literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-121">This example removes leading and trailing spaces from a string literal.</span></span> <span data-ttu-id="ca6b7-122">O resultado de retorno é "Nova Iorque".</span><span class="sxs-lookup"><span data-stu-id="ca6b7-122">The return result is "New York".</span></span>  
  
```  
TRIM("   New York   ")  
```  
  
 <span data-ttu-id="ca6b7-123">Este exemplo remove espaços à direita e à esquerda do resultado da concatenação das colunas **FirstName** e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="ca6b7-123">This example removes leading and trailing spaces from the result of concatenating the **FirstName** and **LastName** columns.</span></span> <span data-ttu-id="ca6b7-124">A cadeia de caracteres vazia entre **FirstName** e **LastName** não é removida.</span><span class="sxs-lookup"><span data-stu-id="ca6b7-124">The empty string between **FirstName** and **LastName** is not removed.</span></span>  
  
```  
TRIM(FirstName + " "+ LastName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca6b7-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ca6b7-125">See Also</span></span>  
 <span data-ttu-id="ca6b7-126">[LTRIM &#40;Expressão SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ca6b7-126">[LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="ca6b7-127">[RTRIM &#40;Expressão SSIS&#41;](rtrim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ca6b7-127">[RTRIM &#40;SSIS Expression&#41;](rtrim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="ca6b7-128">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="ca6b7-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
