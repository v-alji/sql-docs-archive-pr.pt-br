---
title: TOKENCOUNT (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c0efed1-c2b3-4f20-a3a1-ad91283b7c0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9068e4958570a0222bc8e1a4c90d34acc5bdf3dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680998"
---
# <a name="tokencount-ssis-expression"></a><span data-ttu-id="45933-102">TOKENCOUNT (expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="45933-102">TOKENCOUNT (SSIS Expression)</span></span>
  <span data-ttu-id="45933-103">Retorna o número de tokens em uma cadeia de caracteres que contém tokens separados pelos delimitadores especificados.</span><span class="sxs-lookup"><span data-stu-id="45933-103">Returns the number of tokens in a string that contains tokens separated by the specified delimiters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45933-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="45933-104">Syntax</span></span>  
  
```  
TOKENCOUNT(character_expression, delimiter_string)  
```  
  
## <a name="arguments"></a><span data-ttu-id="45933-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="45933-105">Arguments</span></span>  
 <span data-ttu-id="45933-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="45933-106">*character_expression*</span></span>  
 <span data-ttu-id="45933-107">Uma cadeia de caracteres que contém tokens separados por delimitadores.</span><span class="sxs-lookup"><span data-stu-id="45933-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="45933-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="45933-108">*delimiter_string*</span></span>  
 <span data-ttu-id="45933-109">Uma cadeia de caracteres que contém caracteres delimitadores.</span><span class="sxs-lookup"><span data-stu-id="45933-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="45933-110">Por exemplo, "; ," contém três caracteres delimitadores ponto e vírgula, um espaço em branco e uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="45933-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="45933-111">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="45933-111">Result Types</span></span>  
 <span data-ttu-id="45933-112">DT_I4</span><span class="sxs-lookup"><span data-stu-id="45933-112">DT_I4</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45933-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="45933-113">Remarks</span></span>  
 <span data-ttu-id="45933-114">Os comentários a seguir se aplicam à função TOKEN:</span><span class="sxs-lookup"><span data-stu-id="45933-114">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="45933-115">A cadeia de caracteres delimitadores pode conter um ou mais caracteres delimitadores.</span><span class="sxs-lookup"><span data-stu-id="45933-115">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="45933-116">Delimitadores à esquerda são ignorados.</span><span class="sxs-lookup"><span data-stu-id="45933-116">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="45933-117">TOKENCOUNT funciona apenas com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="45933-117">TOKENCOUNT works only with the DT_WSTR data type.</span></span> <span data-ttu-id="45933-118">Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido no tipo de dados DT_WSTR antes de TOKEN executar sua operação.</span><span class="sxs-lookup"><span data-stu-id="45933-118">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="45933-119">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="45933-119">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="45933-120">TOKENCOUNT retornará 0 (zero) se o character_expression for nulo.</span><span class="sxs-lookup"><span data-stu-id="45933-120">TOKENCOUNT returns 0 (zero) if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="45933-121">É possível usar variáveis e colunas como argumentos para essa expressão.</span><span class="sxs-lookup"><span data-stu-id="45933-121">You can use variables and columns as arguments for this expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="45933-122">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="45933-122">Expression Examples</span></span>  
 <span data-ttu-id="45933-123">No exemplo a seguir, a função TOKENCOUNT retorna 3 porque a cadeia de caracteres contém três tokens: "01", "12", "2011".</span><span class="sxs-lookup"><span data-stu-id="45933-123">In the following example, the TOKENCOUNT function returns 3 because the string contains three tokens: "01", "12", "2011".</span></span>  
  
```  
TOKENCOUNT("01/12/2011", "/")  
```  
  
 <span data-ttu-id="45933-124">No exemplo a seguir, a função TOKENCOUNT retorna 4 porque há quatro tokens ("a", "little", "white", "dog").</span><span class="sxs-lookup"><span data-stu-id="45933-124">In the following example, the TOKENCOUNT function returns 4 because there are four tokens ("a", "little", "white", "dog").</span></span>  
  
```  
TOKENCOUNT("a little white dog"," ")  
```  
  
 <span data-ttu-id="45933-125">No exemplo a seguir, a função TOKENCOUNT retorna 1.</span><span class="sxs-lookup"><span data-stu-id="45933-125">In the following example, the TOKENCOUNT function returns 1.</span></span> <span data-ttu-id="45933-126">A função analisa a cadeia de caracteres de entrada para verificar se há delimitadores e, como não há, ela adiciona a cadeia de caracteres inteira como o primeiro token.</span><span class="sxs-lookup"><span data-stu-id="45933-126">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKENCOUNT("a little white dog","|")  
```  
  
 <span data-ttu-id="45933-127">No exemplo a seguir, a função TOKENCOUNT retorna 4.</span><span class="sxs-lookup"><span data-stu-id="45933-127">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="45933-128">A cadeia de caracteres delimitadores neste exemplo contém cinco delimitadores.</span><span class="sxs-lookup"><span data-stu-id="45933-128">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="45933-129">A cadeia de caracteres de entrada contém quatro tokens: "a", "little", "white", "dog".</span><span class="sxs-lookup"><span data-stu-id="45933-129">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKENCOUNT("a:little|white dog","| ,.:")  
```  
  
 <span data-ttu-id="45933-130">No exemplo a seguir, a função TOKENCOUNT retorna 4.</span><span class="sxs-lookup"><span data-stu-id="45933-130">In the following example, the TOKENCOUNT function returns 4.</span></span> <span data-ttu-id="45933-131">Ela ignora todos os caracteres de espaço à esquerda.</span><span class="sxs-lookup"><span data-stu-id="45933-131">It ignores all the leading space characters.</span></span>  
  
```  
TOKENCOUNT("        a little white dog", " ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="45933-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="45933-132">See Also</span></span>  
 [<span data-ttu-id="45933-133">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="45933-133">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
