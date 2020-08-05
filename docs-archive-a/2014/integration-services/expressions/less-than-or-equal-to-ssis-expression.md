---
title: '&lt;= (Menor ou igual a) (Expressão SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- <= (less than or equal to operator)
- less than or equal to operator (<=)
ms.assetid: 946c5630-dccf-4dae-9cfd-6ea823641ab2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1c0b5ef0a8467cedbc5e390b42f3307cceb7c75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572599"
---
# <a name="lt-less-than-or-equal-to-ssis-expression"></a><span data-ttu-id="74169-102">&lt;= (Menor ou igual a) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="74169-102">&lt;= (Less Than or Equal To) (SSIS Expression)</span></span>
  <span data-ttu-id="74169-103">Executa uma comparação para determinar se a primeira expressão é menor que ou igual à segunda.</span><span class="sxs-lookup"><span data-stu-id="74169-103">Performs a comparison to determine if the first expression is less than or equal to the second one.</span></span> <span data-ttu-id="74169-104">O avaliador de expressões converte automaticamente muitos tipos de dados antes de executar a comparação.</span><span class="sxs-lookup"><span data-stu-id="74169-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74169-105">Este operador não aceita comparações que usam os tipos de dados DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="74169-105">This operator does not support comparisons that use the DT_TEXT, DT_NTEXT, or DT_IMAGE data types.</span></span>  
  
 <span data-ttu-id="74169-106">No entanto, alguns tipos de dados requerem que a expressão inclua uma conversão explícita antes de ser avaliada com êxito.</span><span class="sxs-lookup"><span data-stu-id="74169-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="74169-107">Para obter mais informações sobre conversões legais entre tipos de dados, consulte [Conversão &#40;Expressão do SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="74169-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74169-108">Não há nenhum espaço entre os dois caracteres neste operador.</span><span class="sxs-lookup"><span data-stu-id="74169-108">There are no spaces between the two characters in this operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74169-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="74169-109">Syntax</span></span>  
  
```  
  
expression1 <= expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="74169-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="74169-110">Arguments</span></span>  
 <span data-ttu-id="74169-111">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="74169-111">*expression1, expression2*</span></span>  
 <span data-ttu-id="74169-112">É qualquer expressão válida.</span><span class="sxs-lookup"><span data-stu-id="74169-112">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="74169-113">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="74169-113">Result Types</span></span>  
 <span data-ttu-id="74169-114">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="74169-114">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74169-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="74169-115">Remarks</span></span>  
 <span data-ttu-id="74169-116">Se qualquer expressão na comparação for nula, o resultado da comparação será nulo.</span><span class="sxs-lookup"><span data-stu-id="74169-116">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="74169-117">Se ambas as expressões forem nulas, o resultado será nulo.</span><span class="sxs-lookup"><span data-stu-id="74169-117">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="74169-118">O conjunto de expressões, *expression1* e *expression2*, deve seguir uma destas regras:</span><span class="sxs-lookup"><span data-stu-id="74169-118">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="74169-119">**Numérico** Ambas *expression1* e *expression2* devem ser um tipo de dados numérico.</span><span class="sxs-lookup"><span data-stu-id="74169-119">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="74169-120">A intersecção dos tipos de dados deve ser um tipo de dados numérico, como especificado nas regras sobre as conversões numéricas implícitas que o avaliador de expressões executa.</span><span class="sxs-lookup"><span data-stu-id="74169-120">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="74169-121">A interseção dos dois tipos de dados numéricos não pode ser nula.</span><span class="sxs-lookup"><span data-stu-id="74169-121">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="74169-122">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="74169-122">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="74169-123">**Character** Tanto *expression1* quanto *expression2* devem ser avaliadas como um tipo de dados DT_STR ou DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="74169-123">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="74169-124">As duas expressões podem ser avaliadas como tipos de dados de cadeia diferentes.</span><span class="sxs-lookup"><span data-stu-id="74169-124">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="74169-125">Comparações de cadeia de caracteres diferenciam maiúsculas de minúsculas, acentuação, kana e largura.</span><span class="sxs-lookup"><span data-stu-id="74169-125">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="74169-126">**Date, Time, ou Date/Time** Tanto *expression1* quanto *expression2* devem ser avaliadas como um dos seguintes tipos de dados: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET ou DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="74169-126">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="74169-127">O sistema não aceita comparações entre uma expressão que avalia um tipo de dados de hora e uma expressão que avalia um tipo de dados de data ou data/hora.</span><span class="sxs-lookup"><span data-stu-id="74169-127">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="74169-128">O sistema gera um erro.</span><span class="sxs-lookup"><span data-stu-id="74169-128">The system generates an error.</span></span>  
  
     <span data-ttu-id="74169-129">Ao comparar as expressões, o sistema aplica as seguintes regras de conversão na ordem listada:</span><span class="sxs-lookup"><span data-stu-id="74169-129">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="74169-130">Quando as duas expressões avaliarem o mesmo tipo de dados, uma comparação daquele tipo de dados é executada.</span><span class="sxs-lookup"><span data-stu-id="74169-130">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="74169-131">Se uma expressão for um tipo de dados DT_DBTIMESTAMPOFFSET, a outra expressão será convertida implicitamente para DT_DBTIMESTAMPOFFSET, e uma comparação de DT_DBTIMESTAMPOFFSET será executada.</span><span class="sxs-lookup"><span data-stu-id="74169-131">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="74169-132">Para obter mais informações, consulte [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="74169-132">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="74169-133">Se uma expressão for um tipo de dados DT_DBTIMESTAMP2, a outra expressão será convertida implicitamente para DT_DBTIMESTAMP2, e uma comparação de DT_DBTIMESTAMP2 será executada.</span><span class="sxs-lookup"><span data-stu-id="74169-133">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="74169-134">Se uma expressão for um tipo de dados DT_DBTIME2, a outra expressão será convertida implicitamente para DT_DBTIME2, e uma comparação de DT_DBTIME2 será executada.</span><span class="sxs-lookup"><span data-stu-id="74169-134">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="74169-135">Se uma expressão for de um tipo diferente de DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 ou DT_DBTIME2, as expressões serão convertidas para o tipo de dados DT_DBTIMESTAMP antes de serem comparadas.</span><span class="sxs-lookup"><span data-stu-id="74169-135">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="74169-136">Ao comparar as expressões, o sistema faz as seguintes suposições:</span><span class="sxs-lookup"><span data-stu-id="74169-136">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="74169-137">Se cada expressão for um tipo de dados que inclui segundos fracionais, o sistema assumirá que o tipo de dados com o número de dígitos mínimo para os segundos fracionais tem zeros nos dígitos restantes.</span><span class="sxs-lookup"><span data-stu-id="74169-137">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="74169-138">Se cada expressão for um tipo de dados de data, mas somente um tiver um deslocamento de fuso horário, o sistema assumirá que o tipo de dados de data sem o deslocamento de fuso horário estará em UTC (Tempo Universal Coordenado).</span><span class="sxs-lookup"><span data-stu-id="74169-138">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="74169-139">Para obter mais informações sobre tipos de dados, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="74169-139">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="74169-140">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="74169-140">Expression Examples</span></span>  
 <span data-ttu-id="74169-141">Este exemplo será avaliado como TRUE se a data atual for 4 de julho de 2003 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="74169-141">This example evaluates to TRUE if the current date is July 4, 2003 or later.</span></span> <span data-ttu-id="74169-142">Para obter mais informações, consulte [GETDATE &#40;Expressão SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="74169-142">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
"7/4/2003" <= GETDATE()  
```  
  
 <span data-ttu-id="74169-143">Este exemplo será avaliado como TRUE se o valor na coluna **ListPrice** for menor que ou igual a 500.</span><span class="sxs-lookup"><span data-stu-id="74169-143">This example evaluates to TRUE if the value in the **ListPrice** column is less than or equal to 500.</span></span>  
  
```  
ListPrice <= 500  
```  
  
 <span data-ttu-id="74169-144">Este exemplo avalia a variável **LPrice** e será avaliado como TRUE se o valor for menor que ou igual a 500.</span><span class="sxs-lookup"><span data-stu-id="74169-144">This example evaluates the variable **LPrice** and evaluates to TRUE if the value is less than or equal to 500.</span></span> <span data-ttu-id="74169-145">O tipo de dados **LPrice** deve ser numérico para que a expressão seja analisada.</span><span class="sxs-lookup"><span data-stu-id="74169-145">The data type of **LPrice** must be numeric in order for the expression to parse.</span></span>  
  
```  
@LPrice <= 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="74169-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="74169-146">See Also</span></span>  
 <span data-ttu-id="74169-147">[&#62; &#40;Maior que&#41; &#40;Expressão SSIS&#41;](greater-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="74169-147">[&#62; &#40;Greater Than&#41; &#40;SSIS Expression&#41;](greater-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="74169-148">[&#60; &#40;Menor que&#41; &#40;Expressão SSIS&#41;](less-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="74169-148">[&#60; &#40;Less Than&#41; &#40;SSIS Expression&#41;](less-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="74169-149">[&#62;= &#40;Maior ou igual a&#41; &#40;Expressão SSIS&#41;](greater-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="74169-149">[&#62;= &#40;Greater Than or Equal To&#41; &#40;SSIS Expression&#41;](greater-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="74169-150">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="74169-150">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="74169-151">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="74169-151">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
