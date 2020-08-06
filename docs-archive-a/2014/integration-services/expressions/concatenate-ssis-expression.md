---
title: + (Concatenar) (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- concatenation [Integration Services]
- + (concatenate operator)
- concatenate operator (+)
ms.assetid: 0fed6334-7a4f-42dc-a611-191fcaa0e443
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1c01f82a50962f42862db836171b0ad683c97453
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681048"
---
# <a name="-concatenate-ssis-expression"></a><span data-ttu-id="a324f-102">+ (Concatenar) (Expressão SSIS)</span><span class="sxs-lookup"><span data-stu-id="a324f-102">+ (Concatenate) (SSIS Expression)</span></span>
  <span data-ttu-id="a324f-103">Concatena duas expressões em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="a324f-103">Concatenates two expressions into one expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a324f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a324f-104">Syntax</span></span>  
  
```  
  
character_expression1 + character_expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a324f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a324f-105">Arguments</span></span>  
 <span data-ttu-id="a324f-106">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="a324f-106">*expression1, expression2*</span></span>  
 <span data-ttu-id="a324f-107">É qualquer expressão de tipo de dados válida DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="a324f-107">Is any valid DT_STR, DT_WSTR, DT_TEXT, DT_NTEXT, or DT_IMAGE data type expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a324f-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="a324f-108">Result Types</span></span>  
 <span data-ttu-id="a324f-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="a324f-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a324f-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="a324f-110">Remarks</span></span>  
 <span data-ttu-id="a324f-111">A expressão pode usar um ou ambos os tipos de dados DT_STR e DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="a324f-111">The expression can use either or both of the DT_STR and DT_WSTR data types.</span></span>  
  
 <span data-ttu-id="a324f-112">A concatenação dos tipos de dados DT_STR e DT_WSTR retorna um resultado do tipo DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="a324f-112">The concatenation of the DT_STR and DT_WSTR data types returns a result of the DT_WSTR type.</span></span> <span data-ttu-id="a324f-113">O comprimento da cadeia de caracteres é a soma dos comprimentos das cadeias originais expressas em caracteres.</span><span class="sxs-lookup"><span data-stu-id="a324f-113">The length of the string is the sum of the lengths of the original strings expressed in characters.</span></span>  
  
 <span data-ttu-id="a324f-114">Somente os dados com os tipo de dados DT_STR e DT_WSTR da cadeia de caracteres ou os tipos de dados DT_TEXT, DT_NTEXT e DT_IMAGE do BLOB (Bloco de objetos binários grande) podem ser concatenados.</span><span class="sxs-lookup"><span data-stu-id="a324f-114">Only data with the string data types DT_STR and DT_WSTR or the Binary Large Object Block (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE can be concatenated.</span></span> <span data-ttu-id="a324f-115">Outros tipos de dados devem ser convertidos explicitamente a um desses tipos de dados antes de ocorrer a concatenação.</span><span class="sxs-lookup"><span data-stu-id="a324f-115">Other data types must be explicitly converted to one of these data types before concatenation occurs.</span></span> <span data-ttu-id="a324f-116">Para obter mais informações sobre conversões legais entre tipos de dados, consulte [Conversão &#40;Expressão do SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="a324f-116">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="a324f-117">Ambas as expressões devem ser do mesmo tipo de dados ou uma expressão deve ser convertida implicitamente para o tipo de dados da outra expressão.</span><span class="sxs-lookup"><span data-stu-id="a324f-117">Both expressions must be of the same data type, or one expression must be implicitly convertible to the data type of the other expression.</span></span> <span data-ttu-id="a324f-118">Por exemplo, se a cadeia "Order date is " e a coluna **OrderDate** forem concatenadas, os valores em **OrderDate** serão implicitamente convertidos em um tipo de dados de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a324f-118">For example, if the string "Order date is " and the column **OrderDate** are concatenated, the values in **OrderDate** are implicitly converted to a string data type.</span></span> <span data-ttu-id="a324f-119">Para concatenar dois valores numéricos, ambos os valores numéricos devem ser lançados explicitamente a um tipo de dados de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a324f-119">To concatenate two numeric values, both numeric values must be explicitly cast to a string data type.</span></span>  
  
 <span data-ttu-id="a324f-120">Uma concatenação pode usar só um tipo de dados BLOB: DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="a324f-120">A concatenation can use only one BLOB data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="a324f-121">Se qualquer elemento for nulo, o resultado será nulo.</span><span class="sxs-lookup"><span data-stu-id="a324f-121">If either element is null, the result is null.</span></span>  
  
 <span data-ttu-id="a324f-122">Literais da cadeia de caracteres devem estar entre aspas.</span><span class="sxs-lookup"><span data-stu-id="a324f-122">String literals must be enclosed in quotation marks.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="a324f-123">Exemplos de expressões</span><span class="sxs-lookup"><span data-stu-id="a324f-123">Expression Examples</span></span>  
 <span data-ttu-id="a324f-124">Este exemplo concatena os valores nas colunas **FirstName** e **LastName** e insere um espaço entre eles.</span><span class="sxs-lookup"><span data-stu-id="a324f-124">This example concatenates the values in the **FirstName** and **LastName** columns and inserts a space between them.</span></span>  
  
```  
FirstName + ' ' + LastName  
```  
  
 <span data-ttu-id="a324f-125">Este exemplo concatena as variáveis **ZIPCode** e **ZIPCode+4**.</span><span class="sxs-lookup"><span data-stu-id="a324f-125">This example concatenates the variables **ZIPCode** and **ZIPCode+4**.</span></span> <span data-ttu-id="a324f-126">Ambas as variáveis têm um tipo de dados de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a324f-126">Both variables have a string data type.</span></span> <span data-ttu-id="a324f-127">**ZIPCode+4** deve ser incluído em parênteses porque o nome da variável inclui o caractere +.</span><span class="sxs-lookup"><span data-stu-id="a324f-127">**ZIPCode+4** must be enclosed in brackets because the variable name includes the + character.</span></span>  
  
```  
@ZIPCcode + "-" + @[ZipCode+4]  
```  
  
## <a name="see-also"></a><span data-ttu-id="a324f-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a324f-128">See Also</span></span>  
 <span data-ttu-id="a324f-129">[Precedência de operador e capacidade de associação](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="a324f-129">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="a324f-130">Operadores &#40;Expressão do SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="a324f-130">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
