---
title: LTRIM (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- LTRIM function
ms.assetid: d082f42a-d7e7-49f5-a503-ac44ba630832
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 678d9d93eb1dcd7649d2085b651a08418bbcd6a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573202"
---
# <a name="ltrim-ssis-expression"></a><span data-ttu-id="a346e-102">LTRIM (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="a346e-102">LTRIM (SSIS Expression)</span></span>
  <span data-ttu-id="a346e-103">Retorna uma expressão de caractere depois de remover espaços em branco à esquerda.</span><span class="sxs-lookup"><span data-stu-id="a346e-103">Returns a character expression after removing leading spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a346e-104">LTRIM não remove caracteres do espaço em branco como os caracteres de guia ou de alimentação de linha.</span><span class="sxs-lookup"><span data-stu-id="a346e-104">LTRIM does not remove white-space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="a346e-105">Unicode fornece pontos de código para muitos tipos diferentes de espaços, mas essa função reconhece somente o ponto de código Unicode 0x0020.</span><span class="sxs-lookup"><span data-stu-id="a346e-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="a346e-106">Quando as cadeias de caracteres de DBCS (Conjunto de caracteres de byte duplo) são convertidas para Unicode, elas podem incluir caracteres de espaço diferentes de 0x0020, e a função não pode remover esses espaços.</span><span class="sxs-lookup"><span data-stu-id="a346e-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="a346e-107">Para remover todos os tipos de espaços, você poderá usar o método LTrim do Microsoft Visual Basic .NET em uma execução de script a partir do componente Script.</span><span class="sxs-lookup"><span data-stu-id="a346e-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET LTrim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a346e-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a346e-108">Syntax</span></span>  
  
```  
  
LTRIM(character expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="a346e-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a346e-109">Arguments</span></span>  
 <span data-ttu-id="a346e-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="a346e-110">*character_expression*</span></span>  
 <span data-ttu-id="a346e-111">É uma expressão de caractere da qual remover espaços.</span><span class="sxs-lookup"><span data-stu-id="a346e-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a346e-112">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="a346e-112">Result Types</span></span>  
 <span data-ttu-id="a346e-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="a346e-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a346e-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="a346e-114">Remarks</span></span>  
 <span data-ttu-id="a346e-115">LTRIM só funciona com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="a346e-115">LTRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="a346e-116">Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes de LTRIM executar sua operação.</span><span class="sxs-lookup"><span data-stu-id="a346e-116">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before LTRIM performs its operation.</span></span> <span data-ttu-id="a346e-117">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="a346e-117">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="a346e-118">Para obter mais informações, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="a346e-118">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="a346e-119">LTRIM retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="a346e-119">LTRIM returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="a346e-120">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="a346e-120">Expression Examples</span></span>  
 <span data-ttu-id="a346e-121">Este exemplo remove espaços à esquerda de um literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a346e-121">This example removes leading spaces from a string literal.</span></span> <span data-ttu-id="a346e-122">O resultado de retorno é "Hello".</span><span class="sxs-lookup"><span data-stu-id="a346e-122">The return result is "Hello".</span></span>  
  
```  
LTRIM("    Hello")  
```  
  
 <span data-ttu-id="a346e-123">Este exemplo remove espaços à esquerda da coluna **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="a346e-123">This example removes leading spaces from the **FirstName** column.</span></span>  
  
```  
LTRIM(FirstName)  
```  
  
 <span data-ttu-id="a346e-124">Este exemplo remove os espaços à esquerda da variável **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="a346e-124">This example removes leading spaces from the **FirstName** variable.</span></span>  
  
```  
LTRIM(@FirstName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="a346e-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a346e-125">See Also</span></span>  
 <span data-ttu-id="a346e-126">[RTRIM &#40;Expressão SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a346e-126">[RTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="a346e-127">[TRIM &#40;Expressão SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="a346e-127">[TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="a346e-128">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="a346e-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
