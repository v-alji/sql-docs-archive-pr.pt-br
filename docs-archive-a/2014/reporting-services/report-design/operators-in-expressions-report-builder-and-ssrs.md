---
title: Operadores em expressões (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d22dc8b6-4353-40e7-91a1-65e8dae6325d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa8042df39e535425a05414c1e39ee6a12ff2f39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573736"
---
# <a name="operators-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="82506-102">Operadores em expressões (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="82506-102">Operators in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="82506-103">Um operador é um símbolo que representa ações aplicadas a um ou mais termos em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="82506-103">An operator is a symbol that represents actions applied to one or more terms in an expression.</span></span> <span data-ttu-id="82506-104">As seguintes categorias de operadores têm suporte em uma expressão: aritmética, de comparação, de concatenação, lógica ou de bit a bit e de deslocamento de bit.</span><span class="sxs-lookup"><span data-stu-id="82506-104">The following categories of operators are supported in an expression: arithmetic, comparison, concatenation, logical or bitwise, and bit shift.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="arithmetic"></a><span data-ttu-id="82506-105">Aritmético</span><span class="sxs-lookup"><span data-stu-id="82506-105">Arithmetic</span></span>  
 <span data-ttu-id="82506-106">Os operadores aritméticos executam operações matemáticas sobre dois termos numéricos em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="82506-106">Arithmetic operators perform mathematical operations on two numeric terms in an expression.</span></span>  
  
|<span data-ttu-id="82506-107">Operador</span><span class="sxs-lookup"><span data-stu-id="82506-107">Operator</span></span>|<span data-ttu-id="82506-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="82506-108">Description</span></span>|  
|--------------|-----------------|  
|^|<span data-ttu-id="82506-109">Eleva um número à potência de outro número.</span><span class="sxs-lookup"><span data-stu-id="82506-109">Raises a number to the power of another number.</span></span>|  
|*|<span data-ttu-id="82506-110">Multiplica dois números.</span><span class="sxs-lookup"><span data-stu-id="82506-110">Multiplies two numbers.</span></span>|  
|/|<span data-ttu-id="82506-111">Divide dois números e retorna um resultado de ponto flutuante.</span><span class="sxs-lookup"><span data-stu-id="82506-111">Divides two numbers and returns a floating-point result.</span></span>|  
|<span data-ttu-id="82506-112">\|Divide dois números e retorna um resultado de número inteiro.</span><span class="sxs-lookup"><span data-stu-id="82506-112">\|Divides two numbers and returns an integer result.</span></span>|  
|<span data-ttu-id="82506-113">Mod</span><span class="sxs-lookup"><span data-stu-id="82506-113">Mod</span></span>|<span data-ttu-id="82506-114">Retorna o resto inteiro de uma divisão.</span><span class="sxs-lookup"><span data-stu-id="82506-114">Returns the integer remainder of a division.</span></span> <span data-ttu-id="82506-115">Por exemplo, 7 Mod 5 = 2 porque o resto de 7 dividido por 5 é 2.</span><span class="sxs-lookup"><span data-stu-id="82506-115">For example, 7 Mod 5 = 2 because the remainder of 7 divided by 5 is 2.</span></span>|  
|+|<span data-ttu-id="82506-116">Soma dois números.</span><span class="sxs-lookup"><span data-stu-id="82506-116">Adds two numbers together.</span></span>|  
|-|<span data-ttu-id="82506-117">Retorna a diferença entre dois números ou indica o valor negativo de um termo numérico.</span><span class="sxs-lookup"><span data-stu-id="82506-117">Returns the difference between two numbers or indicates the negative value of a numeric term.</span></span>|  
  
### <a name="comparison"></a><span data-ttu-id="82506-118">Comparação</span><span class="sxs-lookup"><span data-stu-id="82506-118">Comparison</span></span>  
 <span data-ttu-id="82506-119">Os operadores de comparação testam se duas expressões são iguais.</span><span class="sxs-lookup"><span data-stu-id="82506-119">Comparison operators test whether two expressions are the same.</span></span>  
  
|<span data-ttu-id="82506-120">Operador</span><span class="sxs-lookup"><span data-stu-id="82506-120">Operator</span></span>|<span data-ttu-id="82506-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="82506-121">Description</span></span>|  
|--------------|-----------------|  
|<|<span data-ttu-id="82506-122">Menor que.</span><span class="sxs-lookup"><span data-stu-id="82506-122">Less than.</span></span>|  
|\<=|<span data-ttu-id="82506-123">Menor que ou igual a.</span><span class="sxs-lookup"><span data-stu-id="82506-123">Less than or equal to.</span></span>|  
|>|<span data-ttu-id="82506-124">Maior que.</span><span class="sxs-lookup"><span data-stu-id="82506-124">Greater than.</span></span>|  
|>=|<span data-ttu-id="82506-125">Maior que ou igual a.</span><span class="sxs-lookup"><span data-stu-id="82506-125">Greater than or equal to.</span></span>|  
|=|<span data-ttu-id="82506-126">Igual a.</span><span class="sxs-lookup"><span data-stu-id="82506-126">Equal to.</span></span>|  
|<>|<span data-ttu-id="82506-127">Não igual a.</span><span class="sxs-lookup"><span data-stu-id="82506-127">Not equal to.</span></span>|  
|<span data-ttu-id="82506-128">Como</span><span class="sxs-lookup"><span data-stu-id="82506-128">Like</span></span>|<span data-ttu-id="82506-129">Determina se uma cadeia de caracteres específica corresponde a um padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="82506-129">Determines whether a specific character string matches a specified pattern.</span></span> <span data-ttu-id="82506-130">Um padrão pode incluir caracteres normais e curingas.</span><span class="sxs-lookup"><span data-stu-id="82506-130">A pattern can include regular characters and wildcard characters.</span></span> <span data-ttu-id="82506-131">Durante a correspondência de padrões, os caracteres normais devem corresponder exatamente aos caracteres especificados na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="82506-131">During pattern matching, regular characters must exactly match the characters specified in the character string.</span></span> <span data-ttu-id="82506-132">No entanto, os caracteres curinga podem ser correspondidos a fragmentos arbitrários da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="82506-132">However, wildcard characters can be matched with arbitrary fragments of the character string.</span></span> <span data-ttu-id="82506-133">O uso de caracteres curinga torna o operador LIKE mais flexível que o uso dos operadores de comparação de cadeias de caracteres = e !=.</span><span class="sxs-lookup"><span data-stu-id="82506-133">Using wildcard characters makes the LIKE operator more flexible than using the = and != string comparison operators.</span></span><br /><br /> <span data-ttu-id="82506-134">O seguinte lista os caracteres que podem ser usados como curingas:</span><span class="sxs-lookup"><span data-stu-id="82506-134">The following lists characters that can be used as wildcards:</span></span><br /><br /> <span data-ttu-id="82506-135">**%**: Qualquer cadeia de zero ou mais caracteres.</span><span class="sxs-lookup"><span data-stu-id="82506-135">**%**: Any string of zero or more characters.</span></span><br /><br /> <span data-ttu-id="82506-136">**_**: Qualquer caractere único.</span><span class="sxs-lookup"><span data-stu-id="82506-136">**_**: Any single character.</span></span><br /><br /> <span data-ttu-id="82506-137">**[]**: Qualquer caractere único dentro do intervalo especificado (por exemplo, [a-f]) ou definido (por exemplo, [aeiou]).</span><span class="sxs-lookup"><span data-stu-id="82506-137">**[ ]**: Any single character within the specified range (for example, [a-f]) or set (for example, [aeiou]).</span></span><br /><br /> <span data-ttu-id="82506-138">**[^]**: Qualquer caractere único que não esteja dentro do intervalo especificado (por exemplo, [^ a-f]) ou definido (por exemplo, [^ aeiou]).</span><span class="sxs-lookup"><span data-stu-id="82506-138">**[^]**: Any single character not within the specified range (for example, [^a-f]) or set (for example, [^aeiou]).</span></span>|  
|<span data-ttu-id="82506-139">Is</span><span class="sxs-lookup"><span data-stu-id="82506-139">Is</span></span>|<span data-ttu-id="82506-140">Compara duas referências de objeto.</span><span class="sxs-lookup"><span data-stu-id="82506-140">Compares two object references.</span></span>|  
  
### <a name="string-concatenation"></a><span data-ttu-id="82506-141">Concatenação de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="82506-141">String Concatenation</span></span>  
 <span data-ttu-id="82506-142">A concatenação de cadeias de caracteres anexa a segunda cadeia de caracteres à primeira em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="82506-142">String concatenation appends the second string to the first string in an expression.</span></span> <span data-ttu-id="82506-143">Para outras operações de cadeia de caracteres, use funções internas.</span><span class="sxs-lookup"><span data-stu-id="82506-143">For other string operations, use built-in functions.</span></span>  
  
|<span data-ttu-id="82506-144">Operador</span><span class="sxs-lookup"><span data-stu-id="82506-144">Operator</span></span>|<span data-ttu-id="82506-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="82506-145">Description</span></span>|  
|--------------|-----------------|  
|&|<span data-ttu-id="82506-146">Concatena duas cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="82506-146">Concatenates two strings</span></span>|  
|+|<span data-ttu-id="82506-147">Concatena duas cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="82506-147">Concatenates two strings</span></span>|  
  
### <a name="logical-and-bitwise"></a><span data-ttu-id="82506-148">Lógico e de bit a bit</span><span class="sxs-lookup"><span data-stu-id="82506-148">Logical and Bitwise</span></span>  
 <span data-ttu-id="82506-149">Os operadores lógicos e de bit a bit executam manipulações lógicas entre dois termos inteiros em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="82506-149">Logical and bitwise operators perform logical manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="82506-150">Operador</span><span class="sxs-lookup"><span data-stu-id="82506-150">Operator</span></span>|<span data-ttu-id="82506-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="82506-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="82506-152">And</span><span class="sxs-lookup"><span data-stu-id="82506-152">And</span></span>|<span data-ttu-id="82506-153">Executa uma conjunção lógica em duas expressões boolianas ou uma conjunção bit a bit em duas expressões numéricas.</span><span class="sxs-lookup"><span data-stu-id="82506-153">Performs a logical conjunction on two Boolean expressions, or bitwise conjunction on two numeric expressions.</span></span>|  
|<span data-ttu-id="82506-154">Not</span><span class="sxs-lookup"><span data-stu-id="82506-154">Not</span></span>|<span data-ttu-id="82506-155">Executa uma negação lógica em uma expressão booliana ou uma negação bit a bit em uma expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="82506-155">Performs logical negation on a Boolean expression, or bitwise negation on a numeric expression.</span></span>|  
|<span data-ttu-id="82506-156">Ou</span><span class="sxs-lookup"><span data-stu-id="82506-156">Or</span></span>|<span data-ttu-id="82506-157">Executa uma disjunção lógica em duas expressões boolianas ou uma disjunção bit a bit em dois valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="82506-157">Performs a logical disjunction on two Boolean expressions, or bitwise disjunction on two numeric values.</span></span>|  
|<span data-ttu-id="82506-158">Xor</span><span class="sxs-lookup"><span data-stu-id="82506-158">Xor</span></span>|<span data-ttu-id="82506-159">Executa uma operação de exclusão lógica em duas expressões boolianas ou uma exclusão bit a bit em duas expressões numéricas.</span><span class="sxs-lookup"><span data-stu-id="82506-159">Performs a logical exclusion operation on two Boolean expressions, or a bitwise exclusion on two numeric expressions.</span></span>|  
|<span data-ttu-id="82506-160">AndAlso</span><span class="sxs-lookup"><span data-stu-id="82506-160">AndAlso</span></span>|<span data-ttu-id="82506-161">Executa a conjunção lógica em duas expressões.</span><span class="sxs-lookup"><span data-stu-id="82506-161">Performs logical conjunction on two expressions.</span></span>|  
|<span data-ttu-id="82506-162">OrElse</span><span class="sxs-lookup"><span data-stu-id="82506-162">OrElse</span></span>|<span data-ttu-id="82506-163">Executa a disjunção lógica em duas expressões.</span><span class="sxs-lookup"><span data-stu-id="82506-163">Performs logical disjunction on two expressions.</span></span>|  
  
### <a name="bit-shift"></a><span data-ttu-id="82506-164">Bit Shift</span><span class="sxs-lookup"><span data-stu-id="82506-164">Bit Shift</span></span>  
 <span data-ttu-id="82506-165">Os operadores bit a bit executam manipulações de bit entre dois termos inteiros em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="82506-165">Bitwise operators perform bit manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="82506-166">Operador</span><span class="sxs-lookup"><span data-stu-id="82506-166">Operator</span></span>|<span data-ttu-id="82506-167">Descrição</span><span class="sxs-lookup"><span data-stu-id="82506-167">Description</span></span>|  
|--------------|-----------------|  
|<\<|<span data-ttu-id="82506-168">Executa um deslocamento aritmético à esquerda em um padrão de bit.</span><span class="sxs-lookup"><span data-stu-id="82506-168">Performs an arithmetic left-shift on a bit pattern.</span></span>|  
|>>|<span data-ttu-id="82506-169">Executa um deslocamento aritmético à direita em um padrão de bit.</span><span class="sxs-lookup"><span data-stu-id="82506-169">Performs an arithmetic right-shift on a bit pattern.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82506-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82506-170">See Also</span></span>  
 <span data-ttu-id="82506-171">[Caixa de diálogo Expressão](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="82506-171">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="82506-172">[Expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="82506-172">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="82506-173">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="82506-173">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="82506-174">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="82506-174">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="82506-175">Caixa de diálogo Expressão &#40;Construtor de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="82506-175">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
