---
title: Processamento em lote de chamadas de procedimento armazenado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], batching
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- batches [ODBC]
- ODBC CALL escape sequence
ms.assetid: b7f53e11-15f0-4602-8134-b166160888f0
author: rothja
ms.author: jroth
ms.openlocfilehash: a0df58ce59853ee15b863cbc7bce34041c37fee4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685628"
---
# <a name="batching-stored-procedure-calls"></a><span data-ttu-id="96e5c-102">Processando em lote as chamadas de procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="96e5c-102">Batching Stored Procedure Calls</span></span>
  <span data-ttu-id="96e5c-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client faz automaticamente o lote de chamadas de procedimento armazenado para o servidor quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="96e5c-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver automatically batches stored procedure calls to the server when appropriate.</span></span> <span data-ttu-id="96e5c-104">O driver só faz isso quando é usada a sequência de escape de ODBC CALL; não o faz para a instrução EXECUTE [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96e5c-104">The driver only does this when the ODBC CALL escape sequence is used; it does not do this for the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE statement.</span></span> <span data-ttu-id="96e5c-105">O processamento em lote de chamadas de procedimento armazenado pode reduzir o número de viagens de ida e volta ao servidor e aumentar significativamente o desempenho.</span><span class="sxs-lookup"><span data-stu-id="96e5c-105">Batching stored procedure calls can reduce the number of round trips to the server and significantly increase performance.</span></span>  
  
 <span data-ttu-id="96e5c-106">O driver processa em lote as chamadas de procedimento ao servidor quando você executa um lote que contém várias sequências de escape de ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="96e5c-106">The driver batches procedure calls to the server when you execute a batch that contains multiple ODBC CALL escape sequences.</span></span> <span data-ttu-id="96e5c-107">Também processa em lote as chamadas de procedimento quando matrizes de parâmetro associadas são usadas com uma sequência de escape de ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="96e5c-107">It also batches procedure calls when bound parameter arrays are used with an ODBC CALL escape sequence.</span></span> <span data-ttu-id="96e5c-108">Por exemplo, se você usar a associação de parâmetro de linha-Wise ou de coluna para associar uma matriz com cinco elementos aos parâmetros de uma instrução SQL de chamada ODBC, quando **SQLExecute** ou **SQLExecDirect** for chamado, o driver enviará um único lote com cinco chamadas de procedimento para o servidor.</span><span class="sxs-lookup"><span data-stu-id="96e5c-108">For example, if you use either row-wise or column-wise parameter binding to bind an array with five elements to the parameters of an ODBC CALL SQL statement, when **SQLExecute** or **SQLExecDirect** is called, the driver sends a single batch with five procedure calls to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e5c-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96e5c-109">See Also</span></span>  
 [<span data-ttu-id="96e5c-110">Executando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="96e5c-110">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
