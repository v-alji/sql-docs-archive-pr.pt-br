---
title: RTRIM (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- RTRIM function
- trailing blanks
ms.assetid: 529bd43e-3f8a-4682-a33e-569176aa7fc4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 727c30fd72bfca5676b71f4ba42e936a9b926817
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681018"
---
# <a name="rtrim-ssis-expression"></a><span data-ttu-id="34c0b-102">RTRIM (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="34c0b-102">RTRIM (SSIS Expression)</span></span>
  <span data-ttu-id="34c0b-103">Retorna uma expressão character depois de remover espaços em branco à direita.</span><span class="sxs-lookup"><span data-stu-id="34c0b-103">Returns a character expression after removing trailing spaces.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34c0b-104">RTRIM não remove caracteres do espaço em branco como os caracteres de guia ou de alimentação de linha.</span><span class="sxs-lookup"><span data-stu-id="34c0b-104">RTRIM does not remove white space characters such as the tab or line feed characters.</span></span> <span data-ttu-id="34c0b-105">Unicode fornece pontos de código para muitos tipos diferentes de espaços, mas essa função reconhece somente o ponto de código Unicode 0x0020.</span><span class="sxs-lookup"><span data-stu-id="34c0b-105">Unicode provides code points for many different types of spaces, but this function recognizes only the Unicode code point 0x0020.</span></span> <span data-ttu-id="34c0b-106">Quando as cadeias de caracteres de DBCS (Conjunto de caracteres de byte duplo) são convertidas para Unicode, elas podem incluir caracteres de espaço diferentes de 0x0020, e a função não pode remover esses espaços.</span><span class="sxs-lookup"><span data-stu-id="34c0b-106">When double-byte character set (DBCS) strings are converted to Unicode they may include space characters other than 0x0020 and the function cannot remove such spaces.</span></span> <span data-ttu-id="34c0b-107">Para remover todos os tipos de espaços, você poderá usar o método RTrim do Microsoft Visual Basic .NET em uma execução de script a partir do componente Script.</span><span class="sxs-lookup"><span data-stu-id="34c0b-107">To remove all kinds of spaces, you can use the Microsoft Visual Basic .NET RTrim method in a script run from the Script component.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34c0b-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="34c0b-108">Syntax</span></span>  
  
```  
  
RTRIM(character expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="34c0b-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="34c0b-109">Arguments</span></span>  
 <span data-ttu-id="34c0b-110">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="34c0b-110">*character_expression*</span></span>  
 <span data-ttu-id="34c0b-111">É uma expressão de caractere da qual remover espaços.</span><span class="sxs-lookup"><span data-stu-id="34c0b-111">Is a character expression from which to remove spaces.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="34c0b-112">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="34c0b-112">Result Types</span></span>  
 <span data-ttu-id="34c0b-113">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="34c0b-113">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34c0b-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="34c0b-114">Remarks</span></span>  
 <span data-ttu-id="34c0b-115">RTRIM só funciona com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="34c0b-115">RTRIM works only with the DT_WSTR data type.</span></span> <span data-ttu-id="34c0b-116">Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes de RTRIM executar sua operação.</span><span class="sxs-lookup"><span data-stu-id="34c0b-116">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before RTRIM performs its operation.</span></span> <span data-ttu-id="34c0b-117">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="34c0b-117">Other data types must be explicitly cast to the DT_WSTR data type.</span></span> <span data-ttu-id="34c0b-118">Para obter mais informações, consulte [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="34c0b-118">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md) and [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="34c0b-119">RTRIM retornará um resultado nulo se o argumento for nulo.</span><span class="sxs-lookup"><span data-stu-id="34c0b-119">RTRIM returns a null result if the argument is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="34c0b-120">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="34c0b-120">Expression Examples</span></span>  
 <span data-ttu-id="34c0b-121">Este exemplo remove espaços à direita de um literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="34c0b-121">This example removes trailing spaces from a string literal.</span></span> <span data-ttu-id="34c0b-122">O resultado de retorno é "Hello".</span><span class="sxs-lookup"><span data-stu-id="34c0b-122">The return result is "Hello".</span></span>  
  
```  
RTRIM("Hello   ")  
```  
  
 <span data-ttu-id="34c0b-123">Este exemplo remove espaços à direita de uma concatenação das colunas **FirstName** e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="34c0b-123">This example removes trailing spaces from a concatenation of the **FirstName** and **LastName** columns.</span></span>  
  
```  
RTRIM(FirstName + " " + LastName)  
```  
  
 <span data-ttu-id="34c0b-124">Este exemplo remove os espaços à direita da variável **FirstName** .</span><span class="sxs-lookup"><span data-stu-id="34c0b-124">This example removes trailing spaces from the **FirstName** variable.</span></span>  
  
```  
RTRIM(@FirstName)  
```  
  
## <a name="see-also"></a><span data-ttu-id="34c0b-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34c0b-125">See Also</span></span>  
 <span data-ttu-id="34c0b-126">[LTRIM &#40;Expressão SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="34c0b-126">[LTRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 <span data-ttu-id="34c0b-127">[TRIM &#40;Expressão SSIS&#41;](trim-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="34c0b-127">[TRIM &#40;SSIS Expression&#41;](trim-ssis-expression.md) </span></span>  
 [<span data-ttu-id="34c0b-128">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="34c0b-128">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
