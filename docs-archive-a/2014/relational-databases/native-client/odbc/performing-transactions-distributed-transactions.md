---
title: Executando transações distribuídas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, performing distributed transactions
- SQL Server Native Client ODBC driver, transactions
- distributed transactions [ODBC]
- transactions [ODBC]
- ODBC, transactions
ms.assetid: 2c17fba0-7a3c-453c-91b7-f801e7b39ccb
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ec23fd1883749e35e67f888e26bdf031ccf7fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571359"
---
# <a name="performing-distributed-transactions"></a><span data-ttu-id="7982d-102">Executando transações distribuídas</span><span class="sxs-lookup"><span data-stu-id="7982d-102">Performing Distributed Transactions</span></span>
  <span data-ttu-id="7982d-103">O Coordenador de Transações Distribuídas da Microsoft (MS DTC) permite que os aplicativos estendam transações por duas ou mais instâncias do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7982d-103">The Microsoft Distributed Transaction Coordinator (MS DTC) allows applications to extend transactions across two or more instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7982d-104">Permite também que os aplicativos participem de transações gerenciadas por gerenciadores de transações compatíveis com o padrão XA/DTP do Open Group.</span><span class="sxs-lookup"><span data-stu-id="7982d-104">It also allows applications to participate in transactions managed by transaction managers that comply with the Open Group DTP XA standard.</span></span>  
  
 <span data-ttu-id="7982d-105">Normalmente, todos os comandos de gerenciamento de transações são enviados ao servidor pelo driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="7982d-105">Normally, all transaction management commands are sent through the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to the server.</span></span> <span data-ttu-id="7982d-106">O aplicativo inicia uma transação chamando [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) com o modo de confirmação automática desativado.</span><span class="sxs-lookup"><span data-stu-id="7982d-106">The application starts a transaction by calling [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) with the autocommit mode turned off.</span></span> <span data-ttu-id="7982d-107">Em seguida, o aplicativo executa as atualizações que compõem a transação e chama [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) com a opção SQL_COMMIT ou SQL_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="7982d-107">The application then performs the updates comprising the transaction and calls [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) with either the SQL_COMMIT or SQL_ROLLBACK option.</span></span>  
  
 <span data-ttu-id="7982d-108">No entanto, ao usar o MS DTC, o MS DTC torna-se o Gerenciador de transações e o aplicativo não usa mais **SQLEndTran**.</span><span class="sxs-lookup"><span data-stu-id="7982d-108">When using MS DTC, however, MS DTC becomes the transaction manager and the application no longer uses **SQLEndTran**.</span></span>  
  
 <span data-ttu-id="7982d-109">Quando inscrita em uma transação distribuída, e em seguida se inscreve em uma segunda transação distribuída, o Driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client sai da transação distribuída original e se inscreve na nova transação.</span><span class="sxs-lookup"><span data-stu-id="7982d-109">When enlisted in a distributed transaction, and then enlist in a second distributed transaction, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver defects from the original distributed transaction and enlists in the new transaction.</span></span> <span data-ttu-id="7982d-110">Para obter mais informações, consulte [referência do programador do DTC](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span><span class="sxs-lookup"><span data-stu-id="7982d-110">For more information, see [DTC Programmer's Reference](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7982d-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7982d-111">See Also</span></span>  
 [<span data-ttu-id="7982d-112">Executando transações &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="7982d-112">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
