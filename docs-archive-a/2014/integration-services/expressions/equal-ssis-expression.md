---
title: == (Igual a) (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- equal operator (==)
- == (equal operator)
ms.assetid: 36fd2354-7b93-4c95-9cf3-51ee24568950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 12f92a267543c366dee4905010aeb84d93c4f408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681045"
---
# <a name="-equal-ssis-expression"></a><span data-ttu-id="63e79-102">== (Igual a) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="63e79-102">== (Equal) (SSIS Expression)</span></span>
  <span data-ttu-id="63e79-103">Executará uma comparação para determinar se duas expressões são iguais.</span><span class="sxs-lookup"><span data-stu-id="63e79-103">Performs a comparison to determine if two expressions are equal.</span></span> <span data-ttu-id="63e79-104">O avaliador de expressões converte automaticamente muitos tipos de dados antes de executar a comparação.</span><span class="sxs-lookup"><span data-stu-id="63e79-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span> <span data-ttu-id="63e79-105">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="63e79-105">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
 <span data-ttu-id="63e79-106">No entanto, alguns tipos de dados requerem que a expressão inclua uma conversão explícita antes de ser avaliada com êxito.</span><span class="sxs-lookup"><span data-stu-id="63e79-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="63e79-107">Para obter mais informações sobre conversões legais entre tipos de dados, consulte [Conversão &#40;Expressão do SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="63e79-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63e79-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="63e79-108">Syntax</span></span>  
  
```  
  
expression1 == expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="63e79-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="63e79-109">Arguments</span></span>  
 <span data-ttu-id="63e79-110">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="63e79-110">*expression1, expression2*</span></span>  
 <span data-ttu-id="63e79-111">É qualquer expressão válida.</span><span class="sxs-lookup"><span data-stu-id="63e79-111">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="63e79-112">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="63e79-112">Result Types</span></span>  
 <span data-ttu-id="63e79-113">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="63e79-113">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63e79-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="63e79-114">Remarks</span></span>  
 <span data-ttu-id="63e79-115">Se qualquer expressão na comparação for nula, o resultado da comparação será nulo.</span><span class="sxs-lookup"><span data-stu-id="63e79-115">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="63e79-116">Se ambas as expressões forem nulas, o resultado será nulo.</span><span class="sxs-lookup"><span data-stu-id="63e79-116">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="63e79-117">O conjunto de expressões, *expression1* e *expression2*, deve seguir uma destas regras:</span><span class="sxs-lookup"><span data-stu-id="63e79-117">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="63e79-118">**Numérico** Ambas *expression1* e *expression2* devem ser um tipo de dados numérico.</span><span class="sxs-lookup"><span data-stu-id="63e79-118">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="63e79-119">A interseção dos tipos de dados deve ser um tipo de dados numérico, como especificado nas regras sobre as conversões numéricas implícitas que o avaliador de expressões executa.</span><span class="sxs-lookup"><span data-stu-id="63e79-119">The intersection of the data types must be a numeric data type, as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="63e79-120">A interseção dos dois tipos de dados numéricos não pode ser nula.</span><span class="sxs-lookup"><span data-stu-id="63e79-120">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="63e79-121">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="63e79-121">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="63e79-122">**Character** Tanto *expression1* quanto *expression2* devem ser avaliadas como um tipo de dados DT_STR ou DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="63e79-122">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="63e79-123">As duas expressões podem ser avaliadas como tipos de dados de cadeia diferentes.</span><span class="sxs-lookup"><span data-stu-id="63e79-123">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63e79-124">Comparações de cadeia de caracteres diferenciam maiúsculas de minúsculas, acentuação, kana e largura.</span><span class="sxs-lookup"><span data-stu-id="63e79-124">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="63e79-125">**Date, Time, ou Date/Time** Tanto *expression1* quanto *expression2* devem ser avaliadas como um dos seguintes tipos de dados: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET ou DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="63e79-125">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63e79-126">O sistema não aceita comparações entre uma expressão que avalia um tipo de dados de hora e uma expressão que avalia um tipo de dados de data ou data/hora.</span><span class="sxs-lookup"><span data-stu-id="63e79-126">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="63e79-127">O sistema gera um erro.</span><span class="sxs-lookup"><span data-stu-id="63e79-127">The system generates an error.</span></span>  
  
     <span data-ttu-id="63e79-128">Ao comparar as expressões, o sistema aplica as seguintes regras de conversão na ordem listada:</span><span class="sxs-lookup"><span data-stu-id="63e79-128">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="63e79-129">Quando as duas expressões avaliarem o mesmo tipo de dados, uma comparação daquele tipo de dados é executada.</span><span class="sxs-lookup"><span data-stu-id="63e79-129">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="63e79-130">Se uma expressão for um tipo de dados DT_DBTIMESTAMPOFFSET, a outra expressão será convertida implicitamente para DT_DBTIMESTAMPOFFSET, e uma comparação de DT_DBTIMESTAMPOFFSET será executada.</span><span class="sxs-lookup"><span data-stu-id="63e79-130">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="63e79-131">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="63e79-131">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="63e79-132">Se uma expressão for um tipo de dados DT_DBTIMESTAMP2, a outra expressão será convertida implicitamente para DT_DBTIMESTAMP2, e uma comparação de DT_DBTIMESTAMP2 será executada.</span><span class="sxs-lookup"><span data-stu-id="63e79-132">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="63e79-133">Se uma expressão for um tipo de dados DT_DBTIME2, a outra expressão será convertida implicitamente para DT_DBTIME2, e uma comparação de DT_DBTIME2 será executada.</span><span class="sxs-lookup"><span data-stu-id="63e79-133">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="63e79-134">Se uma expressão for de um tipo diferente de DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 ou DT_DBTIME2, as expressões serão convertidas para o tipo de dados DT_DBTIMESTAMP antes de serem comparadas.</span><span class="sxs-lookup"><span data-stu-id="63e79-134">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="63e79-135">Ao comparar as expressões, o sistema faz as seguintes suposições:</span><span class="sxs-lookup"><span data-stu-id="63e79-135">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="63e79-136">Se cada expressão for um tipo de dados que inclui segundos fracionais, o sistema assumirá que o tipo de dados com o número de dígitos mínimo para os segundos fracionais tem zeros nos dígitos restantes.</span><span class="sxs-lookup"><span data-stu-id="63e79-136">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="63e79-137">Se cada expressão for um tipo de dados de data, mas somente um tiver um deslocamento de fuso horário, o sistema assumirá que o tipo de dados de data sem o deslocamento de fuso horário estará em UTC (Tempo Universal Coordenado).</span><span class="sxs-lookup"><span data-stu-id="63e79-137">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
-   <span data-ttu-id="63e79-138">**Logical** Tanto *expression1* quanto *expression2* devem ser avaliadas como um booliano.</span><span class="sxs-lookup"><span data-stu-id="63e79-138">**Logical** Both *expression1* and *expression2* must evaluate to a Boolean.</span></span>  
  
-   <span data-ttu-id="63e79-139">**GUID** Tanto *expression1* quanto *expression2* devem ser avaliadas como um tipo de dados DT_GUID.</span><span class="sxs-lookup"><span data-stu-id="63e79-139">**GUID** Both *expression1* and *expression2* must evaluate to the DT_GUID data type.</span></span>  
  
-   <span data-ttu-id="63e79-140">**Binary** Tanto *expression1* quanto *expression2* devem ser avaliadas como um tipo de dados DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="63e79-140">**Binary** Both *expression1* and *expression2* must evaluate to the DT_BYTES data type.</span></span>  
  
-   <span data-ttu-id="63e79-141">**BLOB** Tanto *expression1* quanto *expression2* devem ser avaliadas como o mesmo tipo de dados BLOB (Bloco de Objetos Binários Grandes): DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="63e79-141">**BLOB** Both *expression1* and *expression2* must evaluate to the same Binary Large Object Block (BLOB) data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="63e79-142">Para obter mais informações sobre tipos de dados, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="63e79-142">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="63e79-143">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="63e79-143">Expression Examples</span></span>  
 <span data-ttu-id="63e79-144">Este exemplo será avaliado como TRUE se a data atual for 4 de julho de 2003.</span><span class="sxs-lookup"><span data-stu-id="63e79-144">This example evaluates to TRUE if the current date is July 4, 2003.</span></span> <span data-ttu-id="63e79-145">Para obter mais informações, consulte [GETDATE &#40;Expressão SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="63e79-145">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="63e79-146">"7/4/2003" == GETDATE()</span><span class="sxs-lookup"><span data-stu-id="63e79-146">"7/4/2003" == GETDATE()</span></span>  
  
 <span data-ttu-id="63e79-147">Este exemplo será avaliado como TRUE se o valor na coluna **ListPrice** for 500.</span><span class="sxs-lookup"><span data-stu-id="63e79-147">This example evaluates to TRUE if the value in the **ListPrice** column is 500.</span></span>  
  
```  
ListPrice == 500  
```  
  
 <span data-ttu-id="63e79-148">Este exemplo usa a variável **LPrice**.</span><span class="sxs-lookup"><span data-stu-id="63e79-148">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="63e79-149">Ele será avaliado como TRUE se o valor de **LPrice** for 500.</span><span class="sxs-lookup"><span data-stu-id="63e79-149">It evaluates to TRUE if the value of **LPrice** is 500.</span></span> <span data-ttu-id="63e79-150">O tipo de dados da variável deve ser numérico para que a expressão seja analisada com sucesso.</span><span class="sxs-lookup"><span data-stu-id="63e79-150">The data type of the variable must be numeric for the expression to parse successfully.</span></span>  
  
```  
@LPrice == 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="63e79-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="63e79-151">See Also</span></span>  
 <span data-ttu-id="63e79-152">[\!= &#40;Diferente&#41; &#40;Expressão do SSIS&#41;](equal-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="63e79-152">[!= &#40;Unequal&#41; &#40;SSIS Expression&#41;](equal-ssis-expression.md) </span></span>  
 <span data-ttu-id="63e79-153">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="63e79-153">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="63e79-154">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="63e79-154">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
