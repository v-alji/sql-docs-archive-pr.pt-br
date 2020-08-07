---
title: '? : (Condicional) (Expressão SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- conditional operator (?:)
- '?: (conditional operator)'
ms.assetid: d38e6890-7338-4ce0-a837-2dbb41823a37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e607f9ed495184ef47ac2e4f1139b9a9566055ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583176"
---
# <a name="--conditional-ssis-expression"></a><span data-ttu-id="79bd3-103">?</span><span class="sxs-lookup"><span data-stu-id="79bd3-103">?</span></span> <span data-ttu-id="79bd3-104">: (Condicional) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="79bd3-104">: (Conditional) (SSIS Expression)</span></span>
  <span data-ttu-id="79bd3-105">Retorna uma de duas expressões baseadas na avaliação de uma expressão booliana.</span><span class="sxs-lookup"><span data-stu-id="79bd3-105">Returns one of two expressions based on the evaluation of a Boolean expression.</span></span> <span data-ttu-id="79bd3-106">Se a expressão Booleana for avaliada como TRUE, a primeira expressão será avaliada e o resultado será o resultado da expressão.</span><span class="sxs-lookup"><span data-stu-id="79bd3-106">If the Boolean expression evaluates to TRUE, then the first expression is evaluated and the result is the expression result.</span></span> <span data-ttu-id="79bd3-107">Se a expressão Booleana for avaliada como FALSE, a segunda expressão será avaliada e seu resultado será o resultado da expressão.</span><span class="sxs-lookup"><span data-stu-id="79bd3-107">If the Boolean expression evaluates to FALSE then the second expression is evaluated and its result is the expression result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79bd3-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="79bd3-108">Syntax</span></span>  
  
```  
  
boolean_expression?expression1:expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="79bd3-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="79bd3-109">Arguments</span></span>  
 <span data-ttu-id="79bd3-110">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="79bd3-110">*boolean_expression*</span></span>  
 <span data-ttu-id="79bd3-111">É qualquer expressão válida que é avaliada como TRUE, FALSE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="79bd3-111">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
 <span data-ttu-id="79bd3-112">*expression1*</span><span class="sxs-lookup"><span data-stu-id="79bd3-112">*expression1*</span></span>  
 <span data-ttu-id="79bd3-113">É qualquer expressão válida.</span><span class="sxs-lookup"><span data-stu-id="79bd3-113">Is any valid expression.</span></span>  
  
 <span data-ttu-id="79bd3-114">*expression2*</span><span class="sxs-lookup"><span data-stu-id="79bd3-114">*expression2*</span></span>  
 <span data-ttu-id="79bd3-115">É qualquer expressão válida.</span><span class="sxs-lookup"><span data-stu-id="79bd3-115">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="79bd3-116">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="79bd3-116">Result Types</span></span>  
 <span data-ttu-id="79bd3-117">O tipo de dados de *expression1* ou *expression2*.</span><span class="sxs-lookup"><span data-stu-id="79bd3-117">The data type of *expression1* or *expression2*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79bd3-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="79bd3-118">Remarks</span></span>  
 <span data-ttu-id="79bd3-119">Se *boolean_expression* for avaliada como NULL, o resultado da expressão será NULL.</span><span class="sxs-lookup"><span data-stu-id="79bd3-119">If the *boolean_expression* evaluates to NULL, the expression result is NULL.</span></span> <span data-ttu-id="79bd3-120">Se uma expressão selecionada, *expression1* ou *expression2* for NULL, o resultado será NULL.</span><span class="sxs-lookup"><span data-stu-id="79bd3-120">If a selected expression, either *expression1* or *expression2* is NULL, the result is NULL.</span></span> <span data-ttu-id="79bd3-121">Se uma expressão selecionada não for NULL, mas aquela não selecionada for NULL, o resultado será o valor da expressão selecionada.</span><span class="sxs-lookup"><span data-stu-id="79bd3-121">If a selected expression is not NULL, but the one not selected is NULL, the result is the value of the selected expression.</span></span>  
  
 <span data-ttu-id="79bd3-122">Se *expression1* e *expression2* tiverem o mesmo tipo de dados, o resultado será aquele tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="79bd3-122">If *expression1* and *expression2* have the same data type, the result is that data type.</span></span> <span data-ttu-id="79bd3-123">As regras adicionais a seguir se aplicam aos tipos de resultado:</span><span class="sxs-lookup"><span data-stu-id="79bd3-123">The following additional rules apply to result types:</span></span>  
  
-   <span data-ttu-id="79bd3-124">O tipo de dados DT_TEXT requer que *expression1* e *expression2* tenham a mesma página de código.</span><span class="sxs-lookup"><span data-stu-id="79bd3-124">The DT_TEXT data type requires that *expression1* and *expression2* have the same code page.</span></span>  
  
-   <span data-ttu-id="79bd3-125">O comprimento de um resultado com o tipo de dados DT_BYTES é o comprimento do argumento mais longo.</span><span class="sxs-lookup"><span data-stu-id="79bd3-125">The length of a result with the DT_BYTES data type is the length of the longer argument.</span></span>  
  
 <span data-ttu-id="79bd3-126">O conjunto de expressão, *expression1* e *expression2*, deve ser avaliado como os tipos de dados válidos e seguir um destas regras:</span><span class="sxs-lookup"><span data-stu-id="79bd3-126">The expression set, *expression1* and *expression2*, must evaluate to valid data types and follow one of these rules:</span></span>  
  
-   <span data-ttu-id="79bd3-127">**Numérico** Ambas *expression1* e *expression2* devem ser um tipo de dados numérico.</span><span class="sxs-lookup"><span data-stu-id="79bd3-127">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="79bd3-128">A intersecção dos tipos de dados deve ser um tipo de dados numérico, como especificado nas regras sobre as conversões numéricas implícitas que o avaliador de expressões executa.</span><span class="sxs-lookup"><span data-stu-id="79bd3-128">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="79bd3-129">A interseção dos dois tipos de dados numéricos não pode ser nula.</span><span class="sxs-lookup"><span data-stu-id="79bd3-129">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="79bd3-130">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="79bd3-130">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="79bd3-131">**Cadeia de caracteres** Ambas as *expression1* e *expression2* devem ser um tipo de dados String: DT_STR ou DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="79bd3-131">**String** Both *expression1* and *expression2* must be a string data type: DT_STR or DT_WSTR.</span></span> <span data-ttu-id="79bd3-132">As duas expressões podem ser avaliadas como tipos de dados de cadeia diferentes.</span><span class="sxs-lookup"><span data-stu-id="79bd3-132">The two expressions can evaluate to different string data types.</span></span> <span data-ttu-id="79bd3-133">O resultado tem o tipo de dados DT_WSTR com um comprimento do argumento mais longo.</span><span class="sxs-lookup"><span data-stu-id="79bd3-133">The result has the DT_WSTR data type with a length of the longer argument.</span></span>  
  
-   <span data-ttu-id="79bd3-134">**Date, Time, ou Date/Time** Tanto *expression1* quanto *expression2* devem ser avaliadas como um dos seguintes tipos de dados: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET ou DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="79bd3-134">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="79bd3-135">O sistema não aceita comparações entre uma expressão que avalia um tipo de dados de hora e uma expressão que avalia um tipo de dados de data ou data/hora.</span><span class="sxs-lookup"><span data-stu-id="79bd3-135">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="79bd3-136">O sistema gera um erro.</span><span class="sxs-lookup"><span data-stu-id="79bd3-136">The system generates an error.</span></span>  
  
     <span data-ttu-id="79bd3-137">Ao comparar as expressões, o sistema aplica as seguintes regras de conversão na ordem listada:</span><span class="sxs-lookup"><span data-stu-id="79bd3-137">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="79bd3-138">Quando as duas expressões avaliarem o mesmo tipo de dados, uma comparação daquele tipo de dados é executada.</span><span class="sxs-lookup"><span data-stu-id="79bd3-138">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="79bd3-139">Se uma expressão for um tipo de dados DT_DBTIMESTAMPOFFSET, a outra expressão será convertida implicitamente para DT_DBTIMESTAMPOFFSET, e uma comparação de DT_DBTIMESTAMPOFFSET será executada.</span><span class="sxs-lookup"><span data-stu-id="79bd3-139">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="79bd3-140">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="79bd3-140">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="79bd3-141">Se uma expressão for um tipo de dados DT_DBTIMESTAMP2, a outra expressão será convertida implicitamente para DT_DBTIMESTAMP2, e uma comparação de DT_DBTIMESTAMP2 será executada.</span><span class="sxs-lookup"><span data-stu-id="79bd3-141">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="79bd3-142">Se uma expressão for um tipo de dados DT_DBTIME2, a outra expressão será convertida implicitamente para DT_DBTIME2, e uma comparação de DT_DBTIME2 será executada.</span><span class="sxs-lookup"><span data-stu-id="79bd3-142">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="79bd3-143">Se uma expressão for de um tipo diferente de DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 ou DT_DBTIME2, as expressões serão convertidas para o tipo de dados DT_DBTIMESTAMP antes de serem comparadas.</span><span class="sxs-lookup"><span data-stu-id="79bd3-143">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="79bd3-144">Ao comparar as expressões, o sistema faz as seguintes suposições:</span><span class="sxs-lookup"><span data-stu-id="79bd3-144">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="79bd3-145">Se cada expressão for um tipo de dados que inclui segundos fracionais, o sistema assumirá que o tipo de dados com o número de dígitos mínimo para os segundos fracionais tem zeros nos dígitos restantes.</span><span class="sxs-lookup"><span data-stu-id="79bd3-145">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="79bd3-146">Se cada expressão for um tipo de dados de data, mas somente um tiver um deslocamento de fuso horário, o sistema assumirá que o tipo de dados de data sem o deslocamento de fuso horário estará em UTC (Tempo Universal Coordenado).</span><span class="sxs-lookup"><span data-stu-id="79bd3-146">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="79bd3-147">Para obter mais informações sobre tipos de dados, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="79bd3-147">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="79bd3-148">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="79bd3-148">Expression Examples</span></span>  
 <span data-ttu-id="79bd3-149">Este exemplo mostra uma expressão que condicionalmente é avaliada como `savannah` ou `unknown`.</span><span class="sxs-lookup"><span data-stu-id="79bd3-149">This example shows an expression that conditionally evaluates to `savannah` or `unknown`.</span></span>  
  
```  
@AnimalName == "Elephant"? "savannah": "unknown"  
```  
  
 <span data-ttu-id="79bd3-150">Este exemplo mostra uma expressão que faz referências a uma coluna **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="79bd3-150">This example shows an expression that references a **ListPrice** column.</span></span> <span data-ttu-id="79bd3-151">**ListPrice** tem o tipo de dados DT_CY.</span><span class="sxs-lookup"><span data-stu-id="79bd3-151">**ListPrice** has the DT_CY data type.</span></span> <span data-ttu-id="79bd3-152">A expressão multiplica **ListPrice** condicionalmente por .2 ou .1.</span><span class="sxs-lookup"><span data-stu-id="79bd3-152">The expression conditionally multiplies **ListPrice** by .2 or .1.</span></span>  
  
```  
ListPrice < 350.00 ? ListPrice * .2 : ListPrice * .1  
```  
  
## <a name="see-also"></a><span data-ttu-id="79bd3-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79bd3-153">See Also</span></span>  
 <span data-ttu-id="79bd3-154">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="79bd3-154">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="79bd3-155">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="79bd3-155">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
