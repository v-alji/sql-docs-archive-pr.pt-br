---
title: Caixa de diálogo Verificar Expressão de Restrição (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraintexpression
ms.assetid: beb6ce43-3913-4d66-8826-8e885335b790
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38268d4e49a9c674c100bc22c0782e3e61477967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568297"
---
# <a name="check-constraint-expression-dialog-box-visual-database-tools"></a><span data-ttu-id="db253-102">Caixa de diálogo Verificar Expressão de Restrição (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="db253-102">Check Constraint Expression Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="db253-103">Ao anexar uma restrição de verificação a uma tabela ou coluna, é necessário incluir uma expressão SQL.</span><span class="sxs-lookup"><span data-stu-id="db253-103">When you attach a check constraint to a table or column, you must include an SQL expression.</span></span> <span data-ttu-id="db253-104">Digite a expressão de restrição de verificação na caixa fornecida.</span><span class="sxs-lookup"><span data-stu-id="db253-104">Type the check constraint expression in the box provided.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="db253-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="db253-105">UI element list</span></span>  
 <span data-ttu-id="db253-106">Expression</span><span class="sxs-lookup"><span data-stu-id="db253-106">Expression</span></span>  
 <span data-ttu-id="db253-107">Insira a expressão</span><span class="sxs-lookup"><span data-stu-id="db253-107">Enter the expression</span></span>  
  
 <span data-ttu-id="db253-108">É possível criar uma expressão de restrição simples para verificar dados para uma condição simples ou você pode criar uma expressão complexa, usando operadores Boolianos, para verificar dados para várias condições.</span><span class="sxs-lookup"><span data-stu-id="db253-108">You can create a simple constraint expression to check data for a simple condition; or you can create a complex expression, using Boolean operators, to check data for several conditions.</span></span> <span data-ttu-id="db253-109">Por exemplo, suponha que a tabela de autores tenha uma coluna de código de área onde uma cadeia de caracteres de 5 dígitos é requerida.</span><span class="sxs-lookup"><span data-stu-id="db253-109">For example, suppose the authors table has a zip column where a 5-digit character string is required.</span></span> <span data-ttu-id="db253-110">Esse exemplo de expressão de restrição garante que são permitidos apenas números de 5 dígitos:</span><span class="sxs-lookup"><span data-stu-id="db253-110">This sample constraint expression guarantees that only 5-digit numbers are allowed:</span></span>  
  
```  
zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
```  
  
 <span data-ttu-id="db253-111">Ou, suponha que a tabela de vendas tenha uma coluna chamada quantidade que requer um valor maior que 0.</span><span class="sxs-lookup"><span data-stu-id="db253-111">Or suppose the sales table has a column called qty which requires a value greater than 0.</span></span> <span data-ttu-id="db253-112">Esse exemplo de expressão de restrição garante que são permitidos apenas valores positivos:</span><span class="sxs-lookup"><span data-stu-id="db253-112">This sample constraint guarantees that only positive values are allowed:</span></span>  
  
```  
qty > 0  
```  
  
 <span data-ttu-id="db253-113">Ou, suponha que a tabela de pedidos limita o tipo de cartões de crédito aceito para todos os pedidos com cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="db253-113">Or suppose the orders table limits the type of credit cards accepted for all credit card orders.</span></span> <span data-ttu-id="db253-114">Esse exemplo de expressão de restrição garante que se o pedido for feito com um cartão de crédito, então só Visa, MasterCard, ou American Express são aceitos:</span><span class="sxs-lookup"><span data-stu-id="db253-114">This sample constraint guarantees that if the order is placed on a credit card, then only Visa, MasterCard, or American Express is accepted:</span></span>  
  
```  
NOT (payment_method = 'credit card') OR  
   (card_type IN ('VISA', 'MASTERCARD', 'AMERICAN EXPRESS'))  
```  
  
## <a name="to-define-a-constraint-expression"></a><span data-ttu-id="db253-115">Para definir uma expressão de restrição</span><span class="sxs-lookup"><span data-stu-id="db253-115">To define a constraint expression</span></span>  
 <span data-ttu-id="db253-116">Na guia Verificar Restrições das páginas de propriedades, digite uma expressão na caixa de expressão de Restrição que usa a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="db253-116">In the Check Constraints tab of the property pages, type an expression in the Constraint expression box using the following syntax:</span></span>  
  
 `{constant | column_name | function | (subquery)}`  
  
 `[{operator | AND | OR | NOT}`  
  
 `{constant | column_name | function | (subquery)}...]`  
  
 <span data-ttu-id="db253-117">A sintaxe de SQL é criada para os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="db253-117">The SQL syntax is made up of the following parameters:</span></span>  
  
|<span data-ttu-id="db253-118">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="db253-118">Parameter</span></span>|<span data-ttu-id="db253-119">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="db253-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db253-120">constante</span><span class="sxs-lookup"><span data-stu-id="db253-120">constant</span></span>|<span data-ttu-id="db253-121">Um valor literal, como numérico ou dados de caractere.</span><span class="sxs-lookup"><span data-stu-id="db253-121">A literal value, such as numeric or character data.</span></span> <span data-ttu-id="db253-122">Os dados de caractere devem estar entre aspas (').</span><span class="sxs-lookup"><span data-stu-id="db253-122">Character data must be enclosed within single quotation marks (').</span></span>|  
|<span data-ttu-id="db253-123">column_name</span><span class="sxs-lookup"><span data-stu-id="db253-123">column_name</span></span>|<span data-ttu-id="db253-124">Especifica uma coluna.</span><span class="sxs-lookup"><span data-stu-id="db253-124">Specifies a column.</span></span>|  
|<span data-ttu-id="db253-125">função</span><span class="sxs-lookup"><span data-stu-id="db253-125">function</span></span>|<span data-ttu-id="db253-126">Uma função interna.</span><span class="sxs-lookup"><span data-stu-id="db253-126">A built-in function.</span></span>|  
|<span data-ttu-id="db253-127">operador</span><span class="sxs-lookup"><span data-stu-id="db253-127">operator</span></span>|<span data-ttu-id="db253-128">Aritmética, bit a bit, comparação ou operadores de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="db253-128">Arithmetic, bitwise, comparison, or string operators.</span></span>|  
|<span data-ttu-id="db253-129">AND</span><span class="sxs-lookup"><span data-stu-id="db253-129">AND</span></span>|<span data-ttu-id="db253-130">Use expressões em Booliano para conectar duas expressões.</span><span class="sxs-lookup"><span data-stu-id="db253-130">Use in Boolean expressions to connect two expressions.</span></span> <span data-ttu-id="db253-131">Os resultados são retornados quando ambas as expressões forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="db253-131">Results are returned when both expressions are true.</span></span><br /><br /> <span data-ttu-id="db253-132">Quando AND e OR forem ambas usadas em uma instrução, AND é processado primeiro.</span><span class="sxs-lookup"><span data-stu-id="db253-132">When AND and OR are both used in a statement, AND is processed first.</span></span> <span data-ttu-id="db253-133">É possível alterar a ordem de execução usando parênteses.</span><span class="sxs-lookup"><span data-stu-id="db253-133">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="db253-134">OU</span><span class="sxs-lookup"><span data-stu-id="db253-134">OR</span></span>|<span data-ttu-id="db253-135">Use expressões Booleanas para conectar duas ou mais expressões.</span><span class="sxs-lookup"><span data-stu-id="db253-135">Use in Boolean expressions to connect two or more conditions.</span></span> <span data-ttu-id="db253-136">Os resultados são retornados quando nenhuma das condições for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="db253-136">Results are returned when either condition is true.</span></span><br /><br /> <span data-ttu-id="db253-137">Quando AND e OR forem ambas usadas em uma instrução, OR é avaliado após AND.</span><span class="sxs-lookup"><span data-stu-id="db253-137">When AND and OR are both used in a statement, OR is evaluated after AND.</span></span> <span data-ttu-id="db253-138">É possível alterar a ordem de execução usando parênteses.</span><span class="sxs-lookup"><span data-stu-id="db253-138">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="db253-139">NOT</span><span class="sxs-lookup"><span data-stu-id="db253-139">NOT</span></span>|<span data-ttu-id="db253-140">Nega qualquer expressão Booleana (que pode incluir palavras-chaves, como LIKE, NULL, BETWEEN, IN e EXISTS).</span><span class="sxs-lookup"><span data-stu-id="db253-140">Negates any Boolean expression (which can include keywords, such as LIKE, NULL, BETWEEN, IN, and EXISTS).</span></span><br /><br /> <span data-ttu-id="db253-141">Quando mais de um operador lógico for usado em uma instrução, NOT é processado primeiro.</span><span class="sxs-lookup"><span data-stu-id="db253-141">When more than one logical operator is used in a statement, NOT is processed first.</span></span> <span data-ttu-id="db253-142">É possível alterar a ordem de execução usando parênteses.</span><span class="sxs-lookup"><span data-stu-id="db253-142">You can change the order of execution by using parentheses.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db253-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db253-143">See Also</span></span>  
 <span data-ttu-id="db253-144">[Restrições exclusivas e restrições de verificação](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="db253-144">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="db253-145">Criar restrições exclusivas</span><span class="sxs-lookup"><span data-stu-id="db253-145">Create Unique Constraints</span></span>](../../relational-databases/tables/create-unique-constraints.md)  
  
  
