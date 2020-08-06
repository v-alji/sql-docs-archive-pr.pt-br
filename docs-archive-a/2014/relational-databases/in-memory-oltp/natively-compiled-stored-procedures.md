---
title: Procedimentos armazenados compilados nativamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- natively compiled stored procedures
ms.assetid: d5ed432c-10c5-4e4f-883c-ef4d1fa32366
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b8fb7a379c0c08ca357baa1042ebcf51c512c9ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684213"
---
# <a name="natively-compiled-stored-procedures"></a><span data-ttu-id="8c026-102">procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="8c026-102">Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="8c026-103">Os procedimentos armazenados compilados nativamente são procedimentos armazenados [!INCLUDE[tsql](../../includes/tsql-md.md)] compilados no código nativo que acessam tabelas com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="8c026-103">Natively compiled stored procedures are [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures compiled to native code that access memory-optimized tables.</span></span> <span data-ttu-id="8c026-104">Procedimentos armazenados compilados nativamente permitem a execução eficiente de consultas e lógica de negócios no procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="8c026-104">Natively compiled stored procedures allow for efficient execution of queries and business logic in the stored procedure.</span></span> <span data-ttu-id="8c026-105">Para obter mais detalhes sobre o processo de compilação nativo, consulte [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8c026-105">For more details about the native compilation process, see [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md).</span></span> <span data-ttu-id="8c026-106">Para mais informações sobre a migração de procedimentos armazenados baseados em disco para procedimentos armazenados compilados de modo nativo, veja [Problemas de migração para procedimentos armazenados compilados de modo nativo](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8c026-106">For more information about migrating disk-based stored procedures to natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8c026-107">Uma diferença entre procedimentos armazenados interpretados (com base em disco) e procedimentos armazenados compilados nativamente é que o procedimento armazenado interpretado é criado na primeira execução enquanto que um procedimento armazenado compilado nativamente é compilado quando é criado.</span><span class="sxs-lookup"><span data-stu-id="8c026-107">One difference between interpreted (disk-based) stored procedures and natively compiled stored procedures is that an interpreted stored procedure is compiled at first execution whereas a natively compiled stored procedure is compiled when it is created.</span></span> <span data-ttu-id="8c026-108">Com os procedimentos armazenados compilados nativamente, muitas condições de erro (estouro aritmético, conversão de tipo e algumas condições de divisão por zero) podem ser detectadas no momento da criação e causarão a falha na geração do procedimento armazenado compilado nativamente.</span><span class="sxs-lookup"><span data-stu-id="8c026-108">With natively compiled stored procedures, many error conditions (arithmetic overflow, type conversion, and some divide-by-zero conditions) can be detected at create time and will cause creation of the natively compiled stored procedure to fail.</span></span> <span data-ttu-id="8c026-109">Com os procedimentos armazenados interpretados, essas condições de erro geralmente não causarão uma falha quando o procedimento armazenado for criado, mas todas as execuções falharão.</span><span class="sxs-lookup"><span data-stu-id="8c026-109">With interpreted stored procedures, these error conditions will typically not cause a failure when the stored procedure is created, but all executions will fail.</span></span>  
  
 <span data-ttu-id="8c026-110">Tópicos desta seção:</span><span class="sxs-lookup"><span data-stu-id="8c026-110">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="8c026-111">Criando procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="8c026-111">Creating Natively Compiled Stored Procedures</span></span>](creating-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="8c026-112">Blocos atômicos</span><span class="sxs-lookup"><span data-stu-id="8c026-112">Atomic Blocks</span></span>](atomic-blocks-in-native-procedures.md)  
  
-   [<span data-ttu-id="8c026-113">Construções com suporte nos procedimentos armazenados compilados de modo nativo</span><span class="sxs-lookup"><span data-stu-id="8c026-113">Supported Constructs in Natively Compiled Stored Procedures</span></span>](supported-features-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="8c026-114">Usando Try...Catch em procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="8c026-114">Using Try..Catch in Natively Compiled Stored Procedures</span></span>](../../database-engine/using-try-catch-in-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="8c026-115">Construções com suporte em procedimentos armazenados compilados de modo nativo</span><span class="sxs-lookup"><span data-stu-id="8c026-115">Supported Constructs on Natively Compiled Stored Procedures</span></span>](supported-ddl-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="8c026-116">Procedimentos armazenados compilados nativamente e opções de execução Set</span><span class="sxs-lookup"><span data-stu-id="8c026-116">Natively Compiled Stored Procedures and Execution Set Options</span></span>](natively-compiled-stored-procedures-and-execution-set-options.md)  
  
-   [<span data-ttu-id="8c026-117">Práticas recomendadas para chamar procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="8c026-117">Best Practices for Calling Natively Compiled Stored Procedures</span></span>](best-practices-for-calling-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="8c026-118">Monitorando o desempenho de procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="8c026-118">Monitoring Performance of Natively Compiled Stored Procedures</span></span>](monitoring-performance-of-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="8c026-119">Chamando procedimentos armazenados compilados nativamente em aplicativos de acesso a dados</span><span class="sxs-lookup"><span data-stu-id="8c026-119">Calling Natively Compiled Stored Procedures from Data Access Applications</span></span>](calling-natively-compiled-stored-procedures-from-data-access-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="8c026-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8c026-120">See Also</span></span>  
 [<span data-ttu-id="8c026-121">Memory-Optimized Tables</span><span class="sxs-lookup"><span data-stu-id="8c026-121">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
