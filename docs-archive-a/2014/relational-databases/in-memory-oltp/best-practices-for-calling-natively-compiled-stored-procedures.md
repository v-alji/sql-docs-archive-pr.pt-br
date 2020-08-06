---
title: Práticas recomendadas para chamar procedimentos armazenados compilados nativamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f39fc1c7-cfec-4a95-97f6-6b95954694bb
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d07d0e290d1fbd9b324235e64734a399bf7801d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570007"
---
# <a name="best-practices-for-calling-natively-compiled-stored-procedures"></a><span data-ttu-id="38850-102">Práticas recomendadas para chamar procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="38850-102">Best Practices for Calling Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="38850-103">Estes são os procedimentos armazenados compilados nativamente:</span><span class="sxs-lookup"><span data-stu-id="38850-103">Natively compiled stored procedures are:</span></span>  
  
-   <span data-ttu-id="38850-104">Geralmente usados em partes essenciais do desempenho de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="38850-104">Used typically in performance-critical parts of an application.</span></span>  
  
-   <span data-ttu-id="38850-105">Executados com frequência.</span><span class="sxs-lookup"><span data-stu-id="38850-105">Frequently executed.</span></span>  
  
-   <span data-ttu-id="38850-106">Espera-se que sejam muito rápidos.</span><span class="sxs-lookup"><span data-stu-id="38850-106">Expected to be very fast.</span></span>  
  
 <span data-ttu-id="38850-107">O benefício em termos de desempenho com o uso de um procedimento armazenado compilado nativamente aumenta com o crescente número de linhas e a quantidade de lógica que é processada pelo procedimento.</span><span class="sxs-lookup"><span data-stu-id="38850-107">The performance benefit of using a natively compiled stored procedure increases with the number of rows and the amount of logic that is processed by the procedure.</span></span> <span data-ttu-id="38850-108">Por exemplo, um procedimento armazenado compilado nativamente exibirá o melhor desempenho se ele usar um ou mais dos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="38850-108">For example, a natively compiled stored procedure will exhibit better performance if it uses one or more of the following:</span></span>  
  
-   <span data-ttu-id="38850-109">Agregação.</span><span class="sxs-lookup"><span data-stu-id="38850-109">Aggregation.</span></span>  
  
-   <span data-ttu-id="38850-110">Junções de loops aninhados.</span><span class="sxs-lookup"><span data-stu-id="38850-110">Nested-loops joins.</span></span>  
  
-   <span data-ttu-id="38850-111">Operações de seleção, inserção, atualização e exclusão com várias instruções.</span><span class="sxs-lookup"><span data-stu-id="38850-111">Multi-statement select, insert, update, and delete operations.</span></span>  
  
-   <span data-ttu-id="38850-112">Expressões complexas.</span><span class="sxs-lookup"><span data-stu-id="38850-112">Complex expressions.</span></span>  
  
-   <span data-ttu-id="38850-113">Lógica de procedimento, como instruções condicionais e loops.</span><span class="sxs-lookup"><span data-stu-id="38850-113">Procedural logic, such as conditional statements and loops.</span></span>  
  
 <span data-ttu-id="38850-114">Se você precisa processar apenas uma única linha, usar um procedimento armazenado compilado nativamente talvez não traga um benefício em termos de desempenho.</span><span class="sxs-lookup"><span data-stu-id="38850-114">If you need to process only a single row, using a natively compiled stored procedure may not provide a performance benefit.</span></span>  
  
 <span data-ttu-id="38850-115">Para evitar que o servidor precise mapear nomes de parâmetro e converter tipos:</span><span class="sxs-lookup"><span data-stu-id="38850-115">To avoid the server having to map parameter names and convert types:</span></span>  
  
-   <span data-ttu-id="38850-116">Faça a correspondência dos tipos dos parâmetros passados para o procedimento com os tipos contidos na definição de procedimento.</span><span class="sxs-lookup"><span data-stu-id="38850-116">Match the types of the parameters passed to the procedure with the types in the procedure definition.</span></span>  
  
-   <span data-ttu-id="38850-117">Use parâmetros ordinais (sem nome) ao chamar procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="38850-117">Use ordinal (nameless) parameters when calling natively compiled stored procedures.</span></span> <span data-ttu-id="38850-118">Para uma execução mais eficiente, não use parâmetros nomeados.</span><span class="sxs-lookup"><span data-stu-id="38850-118">For the most efficient execution, do not use named parameters.</span></span>  
  
 <span data-ttu-id="38850-119">O uso de parâmetros nomeados (ineficientes) com procedimentos armazenados compilados nativamente poderá ser detectado com o XEvent `hekaton_slow_parameter_passing`, com `reason=named_parameters`.</span><span class="sxs-lookup"><span data-stu-id="38850-119">Use of (inefficient) named parameters with natively compiled stored procedures can be detected through the XEvent `hekaton_slow_parameter_passing`, with `reason=named_parameters`.</span></span>  
  
 <span data-ttu-id="38850-120">Da mesma forma, você pode detectar o uso de tipos incompatíveis através do mesmo XEvent `hekaton_slow_parameter_passing`, com `reason=parameter_conversion`.</span><span class="sxs-lookup"><span data-stu-id="38850-120">Similarly, you can detect use of mismatched types through the same XEvent `hekaton_slow_parameter_passing`, with `reason=parameter_conversion`.</span></span>  
  
 <span data-ttu-id="38850-121">Como você precisará implementar uma lógica de repetição ao usar tabelas com otimização de memória (em vários cenários) e precisará respeitar determinadas limitações de recurso, talvez queira criar um procedimento armazenado [!INCLUDE[tsql](../../includes/tsql-md.md)] interpretado por wrapper.</span><span class="sxs-lookup"><span data-stu-id="38850-121">Because you will need to implement retry logic when using memory-optimized tables (in many scenarios), and because you will need to work around certain feature limitations, you may want to create a wrapper interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure.</span></span> <span data-ttu-id="38850-122">Para obter um exemplo, consulte [diretrizes para a lógica de repetição para transações em tabelas com otimização de memória](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="38850-122">For an example, see [Guidelines for Retry Logic for Transactions on Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38850-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38850-123">See Also</span></span>  
 [<span data-ttu-id="38850-124">Procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="38850-124">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
