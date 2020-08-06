---
title: TOKEN (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9fdd06bf-5bc9-445c-95bf-709e0ca5989b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5c0598c3832e4bf6f838087be4fee541663c8bff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681002"
---
# <a name="token--ssis-expression"></a><span data-ttu-id="c790a-102">TOKEN (expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="c790a-102">TOKEN  (SSIS Expression)</span></span>
  <span data-ttu-id="c790a-103">Retorna um token (subcadeia de caracteres) de uma cadeia de caracteres com base nos delimitadores especificados, que separam os tokens na cadeia de caracteres, e o número do token que denota qual token deve ser retornado.</span><span class="sxs-lookup"><span data-stu-id="c790a-103">Returns a token (substring) from a string based on the specified delimiters that separate tokens in the string and the number of the token that denotes which token to be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c790a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c790a-104">Syntax</span></span>  
  
```  
TOKEN(character_expression, delimiter_string, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c790a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c790a-105">Arguments</span></span>  
 <span data-ttu-id="c790a-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="c790a-106">*character_expression*</span></span>  
 <span data-ttu-id="c790a-107">Uma cadeia de caracteres que contém tokens separados por delimitadores.</span><span class="sxs-lookup"><span data-stu-id="c790a-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="c790a-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="c790a-108">*delimiter_string*</span></span>  
 <span data-ttu-id="c790a-109">Uma cadeia de caracteres que contém caracteres delimitadores.</span><span class="sxs-lookup"><span data-stu-id="c790a-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="c790a-110">Por exemplo, "; ," contém três caracteres delimitadores ponto e vírgula, um espaço em branco e uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="c790a-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
 <span data-ttu-id="c790a-111">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="c790a-111">*occurrence*</span></span>  
 <span data-ttu-id="c790a-112">Um inteiro assinado ou não assinado que especifica o token a ser retornado.</span><span class="sxs-lookup"><span data-stu-id="c790a-112">A signed or unsigned integer that specifies the token to be returned.</span></span> <span data-ttu-id="c790a-113">Por exemplo, se você especificar 3 como um valor para esse parâmetro, o terceiro token da cadeia de caracteres será retornado.</span><span class="sxs-lookup"><span data-stu-id="c790a-113">For example, if you specify 3 as a value for this parameter, the third token in the string is returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c790a-114">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="c790a-114">Result Types</span></span>  
 <span data-ttu-id="c790a-115">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="c790a-115">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c790a-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="c790a-116">Remarks</span></span>  
 <span data-ttu-id="c790a-117">Essa função divide a cadeia de caracteres <character_expression> em um conjunto de tokens separados pelos delimitadores especificados na <delimiter_string> e retorna o enésimo token, em que N é o número de ocorrência do token especificado pelo parâmetro \<occurrence>.</span><span class="sxs-lookup"><span data-stu-id="c790a-117">This function splits up the <character_expression> string into a set of tokens separated by the delimiters specified in the <delimiter_string> and then returns the Nth token where N is the number of occurrence of the token specified by the \<occurrence> parameter.</span></span> <span data-ttu-id="c790a-118">Consulte a seção Exemplos para obter os usos dessa função.</span><span class="sxs-lookup"><span data-stu-id="c790a-118">See Examples section for sample usages of this function.</span></span>  
  
 <span data-ttu-id="c790a-119">Os comentários a seguir se aplicam à função TOKEN:</span><span class="sxs-lookup"><span data-stu-id="c790a-119">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="c790a-120">A cadeia de caracteres delimitadores pode conter um ou mais caracteres delimitadores.</span><span class="sxs-lookup"><span data-stu-id="c790a-120">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="c790a-121">Se o valor do parâmetro \<occurrence> for mais alto que o número total de tokens na cadeia de caracteres, a função retornará NULL.</span><span class="sxs-lookup"><span data-stu-id="c790a-121">If the value of \<occurrence> parameter is higher than the total number of tokens in the string, the function returns NULL.</span></span>  
  
-   <span data-ttu-id="c790a-122">Delimitadores à esquerda são ignorados.</span><span class="sxs-lookup"><span data-stu-id="c790a-122">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="c790a-123">TOKEN funciona apenas com o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c790a-123">TOKEN works only with the DT_WSTR data type.</span></span> <span data-ttu-id="c790a-124">Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido no tipo de dados DT_WSTR antes de TOKEN executar sua operação.</span><span class="sxs-lookup"><span data-stu-id="c790a-124">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="c790a-125">Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c790a-125">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="c790a-126">TOKEN retornará um resultado nulo se character_expression for nula.</span><span class="sxs-lookup"><span data-stu-id="c790a-126">TOKEN returns a null result if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="c790a-127">É possível usar variáveis e colunas como valores de todos os argumentos da expressão.</span><span class="sxs-lookup"><span data-stu-id="c790a-127">You can use variables and columns as values of all arguments in the expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c790a-128">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="c790a-128">Expression Examples</span></span>  
 <span data-ttu-id="c790a-129">No exemplo a seguir, a função TOKEN retorna "a".</span><span class="sxs-lookup"><span data-stu-id="c790a-129">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="c790a-130">A cadeia de caracteres "a little white dog" tem 4 tokens "a", "little", "white", "dog" separadas pelo delimitador " " (caractere de espaço).</span><span class="sxs-lookup"><span data-stu-id="c790a-130">The string "a little white dog" has 4 tokens "a", "little", "white", "dog" separated by the delimiter " " (space character).</span></span> <span data-ttu-id="c790a-131">O segundo argumento, uma cadeia de caracteres delimitadora, especifica apenas um delimitador, o caractere de espaço, a ser usado na divisão da cadeia de caracteres de entrada em tokens.</span><span class="sxs-lookup"><span data-stu-id="c790a-131">The second argument, a delimiter string, specifies only one delimiter, the space character, to be used in splitting the input string into tokens.</span></span> <span data-ttu-id="c790a-132">O último argumento, 1, especifica o primeiro token a ser retornado.</span><span class="sxs-lookup"><span data-stu-id="c790a-132">The last argument, 1, specifies that the first token to be returned.</span></span> <span data-ttu-id="c790a-133">O primeiro token é "a" nesta cadeia de caracteres de exemplo.</span><span class="sxs-lookup"><span data-stu-id="c790a-133">The first token is "a" in this sample string.</span></span>  
  
```  
TOKEN("a little white dog"," ",1)  
```  
  
 <span data-ttu-id="c790a-134">No exemplo a seguir, a função TOKEN retorna "dog".</span><span class="sxs-lookup"><span data-stu-id="c790a-134">In the following example, the TOKEN function returns "dog".</span></span> <span data-ttu-id="c790a-135">A cadeia de caracteres delimitadores neste exemplo contém cinco delimitadores.</span><span class="sxs-lookup"><span data-stu-id="c790a-135">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="c790a-136">A cadeia de caracteres de entrada contém quatro tokens: "a", "little", "white", "dog".</span><span class="sxs-lookup"><span data-stu-id="c790a-136">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKEN("a:little|white dog","| ,.:",4)  
```  
  
 <span data-ttu-id="c790a-137">No exemplo a seguir, a função TOKEN retorna "" (uma cadeia de caracteres vazia) porque não há 99 tokens na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c790a-137">In the following example, the TOKEN function returns "" (an empty string) because there are no 99 tokens in the string.</span></span>  
  
```  
TOKEN("a little white dog"," ",99)  
```  
  
 <span data-ttu-id="c790a-138">No exemplo a seguir, a função TOKEN retorna uma cadeia de caracteres completa.</span><span class="sxs-lookup"><span data-stu-id="c790a-138">In the following example, the TOKEN function returns the full string.</span></span> <span data-ttu-id="c790a-139">A função analisa a cadeia de caracteres de entrada para verificar se há delimitadores e, como não há, ela adiciona a cadeia de caracteres inteira como o primeiro token.</span><span class="sxs-lookup"><span data-stu-id="c790a-139">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKEN("a little white dog","|",1)  
```  
  
 <span data-ttu-id="c790a-140">No exemplo a seguir, a função TOKEN retorna "a".</span><span class="sxs-lookup"><span data-stu-id="c790a-140">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="c790a-141">Ela ignora todos os caracteres de espaço à esquerda.</span><span class="sxs-lookup"><span data-stu-id="c790a-141">It ignores all the leading space characters.</span></span>  
  
```  
TOKEN("        a little white dog", " ", 1)  
```  
  
 <span data-ttu-id="c790a-142">No exemplo a seguir, a função TOKEN retorna o ano de uma cadeia de caracteres de data.</span><span class="sxs-lookup"><span data-stu-id="c790a-142">In the following example, the TOKEN function returns the year from a date string.</span></span>  
  
```  
TOKEN("2009/01/01", "/"), 1  
```  
  
 <span data-ttu-id="c790a-143">No exemplo a seguir, a função TOKEN retorna o nome do arquivo do caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="c790a-143">In the following example, the TOKEN function returns the file name from the specified path.</span></span> <span data-ttu-id="c790a-144">Por exemplo, se o valor de User::Path for "c:\program files\data\myfile.txt", a função TOKEN retornará "myfile.txt".</span><span class="sxs-lookup"><span data-stu-id="c790a-144">For example, if the value of User::Path is "c:\program files\data\myfile.txt", the TOKEN function returns "myfile.txt".</span></span> <span data-ttu-id="c790a-145">A função TOKENCOUNT retorna 4 e a função TOKEN função retorna o 4º token, "myfile.txt".</span><span class="sxs-lookup"><span data-stu-id="c790a-145">The TOKENCOUNT function returns 4 and the TOKEN function return the 4th token, "myfile.txt".</span></span>  
  
```  
TOKEN(@[User::Path], "\\", TOKENCOUNT(@[User::Path], "\\"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="c790a-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c790a-146">See Also</span></span>  
 [<span data-ttu-id="c790a-147">Funções &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c790a-147">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
