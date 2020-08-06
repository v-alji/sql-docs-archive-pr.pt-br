---
title: Executando procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- stored procedures [ODBC], running
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], executing
ms.assetid: 866b6dd3-2acd-4dfb-aeca-a0352b2d4c6a
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e5de6a9a13c95b417657a1d108403fa27abe34b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685619"
---
# <a name="running-stored-procedures"></a><span data-ttu-id="04dfc-102">Executando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="04dfc-102">Running Stored Procedures</span></span>
  <span data-ttu-id="04dfc-103">Um procedimento armazenado é um objeto executável armazenado em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="04dfc-103">A stored procedure is an executable object stored in a database.</span></span> <span data-ttu-id="04dfc-104">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte a:</span><span class="sxs-lookup"><span data-stu-id="04dfc-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports:</span></span>  
  
-   <span data-ttu-id="04dfc-105">Procedimentos armazenados:</span><span class="sxs-lookup"><span data-stu-id="04dfc-105">Stored procedures:</span></span>  
  
     <span data-ttu-id="04dfc-106">Uma ou mais instruções SQL pré-compiladas em um único procedimento executável.</span><span class="sxs-lookup"><span data-stu-id="04dfc-106">One or more SQL statements precompiled into a single executable procedure.</span></span>  
  
-   <span data-ttu-id="04dfc-107">Procedimentos armazenados estendidos:</span><span class="sxs-lookup"><span data-stu-id="04dfc-107">Extended stored procedures:</span></span>  
  
     <span data-ttu-id="04dfc-108">DLLs (bibliotecas de vínculo dinâmico) C ou C++ escritas para a API Open Data Services do SQL Server para procedimentos armazenados estendidos.</span><span class="sxs-lookup"><span data-stu-id="04dfc-108">C or C++ dynamic-link libraries (DLL) written to the SQL Server Open Data Services API for extended stored procedures.</span></span> <span data-ttu-id="04dfc-109">A API Open Data Services estende os recursos de procedimentos armazenados para incluir código C ou C++.</span><span class="sxs-lookup"><span data-stu-id="04dfc-109">The Open Data Services API extends the capabilities of stored procedures to include C or C++ code.</span></span>  
  
 <span data-ttu-id="04dfc-110">Ao executar instruções, chamar um procedimento armazenado na fonte de dados (em vez de executar ou preparar diretamente uma instrução no aplicativo cliente) pode oferecer:</span><span class="sxs-lookup"><span data-stu-id="04dfc-110">When executing statements, calling a stored procedure on the data source (instead of directly executing or preparing a statement in the client application) can provide:</span></span>  
  
-   <span data-ttu-id="04dfc-111">Maior desempenho</span><span class="sxs-lookup"><span data-stu-id="04dfc-111">Higher performance</span></span>  
  
     <span data-ttu-id="04dfc-112">Instruções SQL são analisadas e compiladas quando procedimentos são criados.</span><span class="sxs-lookup"><span data-stu-id="04dfc-112">SQL statements are parsed and compiled when procedures are created.</span></span> <span data-ttu-id="04dfc-113">Esta sobrecarga é então salva quando os procedimentos são executados.</span><span class="sxs-lookup"><span data-stu-id="04dfc-113">This overhead is then saved when the procedures are executed.</span></span>  
  
-   <span data-ttu-id="04dfc-114">Menor sobrecarga da rede</span><span class="sxs-lookup"><span data-stu-id="04dfc-114">Reduced network overhead</span></span>  
  
     <span data-ttu-id="04dfc-115">A execução de um procedimento em vez de enviar consultas complexas pela rede pode reduzir o tráfego de rede.</span><span class="sxs-lookup"><span data-stu-id="04dfc-115">Executing a procedure instead of sending complex queries across the network can reduce network traffic.</span></span> <span data-ttu-id="04dfc-116">Se um aplicativo ODBC usa a sintaxe ODBC { CALL } para executar um procedimento armazenado, o driver ODBC faz otimizações adicionais que eliminam a necessidade de converter dados de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="04dfc-116">If an ODBC application uses the ODBC { CALL } syntax to execute a stored procedure, the ODBC driver makes additional optimizations that eliminate the need to convert parameter data.</span></span>  
  
-   <span data-ttu-id="04dfc-117">Maior consistência</span><span class="sxs-lookup"><span data-stu-id="04dfc-117">Greater consistency</span></span>  
  
     <span data-ttu-id="04dfc-118">Se as regras de uma organização forem implementadas em um recurso central, como um procedimento armazenado, elas poderão ser codificadas, testadas e depuradas de uma vez.</span><span class="sxs-lookup"><span data-stu-id="04dfc-118">If an organization's rules are implemented in a central resource, such as a stored procedure, they can be coded, tested, and debugged once.</span></span> <span data-ttu-id="04dfc-119">Programadores individuais podem então usar os procedimentos armazenados testados em vez de desenvolver suas próprias implementações.</span><span class="sxs-lookup"><span data-stu-id="04dfc-119">Individual programmers can then use the tested stored procedures instead of developing their own implementations.</span></span>  
  
-   <span data-ttu-id="04dfc-120">Maior exatidão</span><span class="sxs-lookup"><span data-stu-id="04dfc-120">Greater accuracy</span></span>  
  
     <span data-ttu-id="04dfc-121">Como geralmente os procedimentos armazenados são desenvolvidos por programadores experientes, existe a tendência de que sejam mais eficientes e tenham menos erros que o código desenvolvido várias vezes por programadores com diversos níveis de habilidade.</span><span class="sxs-lookup"><span data-stu-id="04dfc-121">Because stored procedures are usually developed by experienced programmers, they tend to be more efficient and have fewer errors than code developed multiple times by programmers of varying skill levels.</span></span>  
  
-   <span data-ttu-id="04dfc-122">Maior funcionalidade</span><span class="sxs-lookup"><span data-stu-id="04dfc-122">Added functionality</span></span>  
  
     <span data-ttu-id="04dfc-123">Os procedimentos armazenados estendidos podem usar recursos do C e do C++ não disponíveis em instruções [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04dfc-123">Extended stored procedures can use C and C++ features not available in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="04dfc-124">Para obter um exemplo de como chamar um procedimento armazenado, consulte [processar códigos de retorno e parâmetros de saída &#40;&#41;ODBC ](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="04dfc-124">For an example of how to call a stored procedure, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04dfc-125">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="04dfc-125">In This Section</span></span>  
  
-   [<span data-ttu-id="04dfc-126">Chamando um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="04dfc-126">Calling a Stored Procedure</span></span>](calling-a-stored-procedure.md)  
  
-   [<span data-ttu-id="04dfc-127">Processando em lote as chamadas de procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="04dfc-127">Batching Stored Procedure Calls</span></span>](batching-stored-procedure-calls.md)  
  
-   [<span data-ttu-id="04dfc-128">Processando resultados do procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="04dfc-128">Processing Stored Procedure Results</span></span>](processing-stored-procedure-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="04dfc-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="04dfc-129">See Also</span></span>  
 <span data-ttu-id="04dfc-130">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="04dfc-130">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="04dfc-131">Tópicos de instruções sobre como executar procedimentos armazenados &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="04dfc-131">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
  
