---
title: Chamar procedimentos armazenados (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], calling
ms.assetid: 31176be8-d40e-4f93-8d44-a46e804a3e2d
author: rothja
ms.author: jroth
ms.openlocfilehash: d98d623dbbb4701bb59c95df502d0063d528d0d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573940"
---
# <a name="call-stored-procedures-odbc"></a><span data-ttu-id="8a500-102">Chamar procedimentos armazenados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="8a500-102">Call Stored Procedures (ODBC)</span></span>
  <span data-ttu-id="8a500-103">Quando uma instrução SQL chama um procedimento armazenado usando a cláusula ODBC CALL escape, o driver Microsoft SQL Server envia o procedimento para SQL Server usando o mecanismo RPC (chamada de procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="8a500-103">When a SQL statement calls a stored procedure using the ODBC CALL escape clause, the Microsoft SQL Server driver sends the procedure to SQL Server using the remote stored procedure call (RPC) mechanism.</span></span> <span data-ttu-id="8a500-104">As solicitações de RPC ignoram grande parte da análise de instruções e do processamento de parâmetros no SQL Server e são mais rápidas do que a instrução EXECUTE do Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="8a500-104">RPC requests bypass much of the statement parsing and parameter processing in SQL Server and are faster than using the Transact-SQL EXECUTE statement.</span></span>  
  
 <span data-ttu-id="8a500-105">Para obter um aplicativo de exemplo que demonstra esse recurso, consulte [processar códigos de retorno e parâmetros de saída &#40;&#41;ODBC ](running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="8a500-105">For a sample application that demonstrates this feature, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
### <a name="to-run-a-procedure-as-an-rpc"></a><span data-ttu-id="8a500-106">Para executar um procedimento como um RPC</span><span class="sxs-lookup"><span data-stu-id="8a500-106">To run a procedure as an RPC</span></span>  
  
1.  <span data-ttu-id="8a500-107">Crie uma instrução SQL que use a sequência de escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="8a500-107">Construct a SQL statement that uses the ODBC CALL escape sequence.</span></span> <span data-ttu-id="8a500-108">A instrução usa marcadores de parâmetro para cada parâmetro de entrada, entrada/saída e saída, e para o valor de retorno do procedimento (se houver):</span><span class="sxs-lookup"><span data-stu-id="8a500-108">The statement uses parameter markers for each input, input/output, and output parameter, and for the procedure return value (if any):</span></span>  
  
    ```  
    {? = CALL procname (?,?)}  
    ```  
  
2.  <span data-ttu-id="8a500-109">Chame [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) para cada entrada, entrada/saída e parâmetro de saída e obter o valor de retorno de procedimento (se houver algum).</span><span class="sxs-lookup"><span data-stu-id="8a500-109">Call [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) for each input, input/output, and output parameter, and for the procedure return value (if any).</span></span>  
  
3.  <span data-ttu-id="8a500-110">Execute a instrução com [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span><span class="sxs-lookup"><span data-stu-id="8a500-110">Execute the statement with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a500-111">Se um aplicativo enviar um procedimento usando a sintaxe EXECUTE Transact-SQL (em oposição à sequência de escape ODBC CALL), o driver ODBC SQL Server passará a chamada de procedimento para o SQL Server como uma instrução SQL, em vez de como um RPC.</span><span class="sxs-lookup"><span data-stu-id="8a500-111">If an application submits a procedure using the Transact-SQL EXECUTE syntax (as opposed to the ODBC CALL escape sequence), the SQL Server ODBC driver passes the procedure call to SQL Server as a SQL statement rather than as an RPC.</span></span> <span data-ttu-id="8a500-112">Além disso, os parâmetros de saída não serão retornados se a instrução EXECUTE Transact-SQL for usada.</span><span class="sxs-lookup"><span data-stu-id="8a500-112">Also, output parameters are not returned if the Transact-SQL EXECUTE statement is used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a500-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8a500-113">See Also</span></span>  
 <span data-ttu-id="8a500-114">[Tópicos de instruções sobre como executar procedimentos armazenados &#40;&#41;ODBC](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="8a500-114">[Running Stored Procedures How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="8a500-115">[Processamento em lote de chamadas de procedimento armazenado](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span><span class="sxs-lookup"><span data-stu-id="8a500-115">[Batching Stored Procedure Calls](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span></span>  
 <span data-ttu-id="8a500-116">[Executando procedimentos armazenados](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8a500-116">[Running Stored Procedures](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span></span>  
 <span data-ttu-id="8a500-117">[Chamando um procedimento armazenado](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="8a500-117">[Calling a Stored Procedure](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="8a500-118">Procedimentos</span><span class="sxs-lookup"><span data-stu-id="8a500-118">Procedures</span></span>](../native-client-odbc-queries/executing-statements/procedures.md)  
  
  
