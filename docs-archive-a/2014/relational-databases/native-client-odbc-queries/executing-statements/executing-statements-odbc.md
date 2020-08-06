---
title: Executando instruções (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC]
- ODBC applications, statements
- statements [ODBC], executing
ms.assetid: 063fc40d-ff81-490d-9c9b-2faefb729f37
author: rothja
ms.author: jroth
ms.openlocfilehash: 3066a09cb1f5e63105ca3ffe2441f19e4bbe0101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569413"
---
# <a name="executing-statements-odbc"></a><span data-ttu-id="491be-102">Executando instruções (ODBC)</span><span class="sxs-lookup"><span data-stu-id="491be-102">Executing Statements (ODBC)</span></span>
  <span data-ttu-id="491be-103">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client oferece várias maneiras de executar instruções SQL em um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] banco de dados:</span><span class="sxs-lookup"><span data-stu-id="491be-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers a variety ways to execute SQL statements in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database:</span></span>  
  
-   <span data-ttu-id="491be-104">Execução direta</span><span class="sxs-lookup"><span data-stu-id="491be-104">Direct execution</span></span>  
  
-   <span data-ttu-id="491be-105">Execução preparada</span><span class="sxs-lookup"><span data-stu-id="491be-105">Prepared execution</span></span>  
  
 <span data-ttu-id="491be-106">A execução direta envolve criar uma cadeia de caracteres que contém uma [!INCLUDE[tsql](../../../includes/tsql-md.md)] instrução e enviá-la para execução usando a função **SQLExecDirect** .</span><span class="sxs-lookup"><span data-stu-id="491be-106">Direct execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and submitting it for execution using the **SQLExecDirect** function.</span></span> <span data-ttu-id="491be-107">A execução preparada envolve a compilação de uma cadeia de caracteres contendo uma instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] e a execução em dois estágios.</span><span class="sxs-lookup"><span data-stu-id="491be-107">Prepared execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and then executing it in two stages.</span></span> <span data-ttu-id="491be-108">O primeiro estágio usa a função de [função SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) para analisar e compilar o plano de execução para a instrução no [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="491be-108">The first stage uses the [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) function to parse and compile the execution plan for the statement in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="491be-109">O segundo estágio usa a função **SQLExecute** para executar o plano de execução preparado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="491be-109">The second stage uses the **SQLExecute** function to execute the previously prepared execution plan.</span></span> <span data-ttu-id="491be-110">Dessa forma, a sobrecarga de análise e compilação é salva em cada execução.</span><span class="sxs-lookup"><span data-stu-id="491be-110">This saves the parsing and compiling overhead on each execution.</span></span> <span data-ttu-id="491be-111">A execução preparada geralmente é usada através de aplicativos para executar a mesma instrução SQL com parâmetros várias vezes.</span><span class="sxs-lookup"><span data-stu-id="491be-111">Prepared execution is commonly used by applications to repeatedly execute the same, parameterized SQL statement.</span></span>  
  
 <span data-ttu-id="491be-112">As execuções direta e preparada podem executar uma única instrução [!INCLUDE[tsql](../../../includes/tsql-md.md)] ou um lote de instruções SQL, ou elas podem chamar um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="491be-112">Both direct and prepared execution can execute a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement or a batch of SQL statements, or they can call a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="491be-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="491be-113">In This Section</span></span>  
  
-   [<span data-ttu-id="491be-114">Execução direta</span><span class="sxs-lookup"><span data-stu-id="491be-114">Direct Execution</span></span>](direct-execution.md)  
  
-   [<span data-ttu-id="491be-115">Execução preparada</span><span class="sxs-lookup"><span data-stu-id="491be-115">Prepared Execution</span></span>](prepared-execution.md)  
  
-   [<span data-ttu-id="491be-116">Procedimentos</span><span class="sxs-lookup"><span data-stu-id="491be-116">Procedures</span></span>](procedures.md)  
  
-   [<span data-ttu-id="491be-117">Lotes de instruções</span><span class="sxs-lookup"><span data-stu-id="491be-117">Batches of Statements</span></span>](batches-of-statements.md)  
  
-   [<span data-ttu-id="491be-118">Efeitos das opções ISO</span><span class="sxs-lookup"><span data-stu-id="491be-118">Effects of ISO Options</span></span>](effects-of-iso-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="491be-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="491be-119">See Also</span></span>  
 [<span data-ttu-id="491be-120">Executando consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="491be-120">Executing Queries &#40;ODBC&#41;</span></span>](../executing-queries-odbc.md)  
  
  
