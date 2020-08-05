---
title: Usar o Microsoft Coordenador de Transações Distribuídas (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, using
ms.assetid: 12a275e1-8c7e-436d-8a4e-b7bee853b35c
author: rothja
ms.author: jroth
ms.openlocfilehash: f7b7da33066a9f4edd01037738ed91155340e6ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572984"
---
# <a name="use-microsoft-distributed-transaction-coordinator-odbc"></a><span data-ttu-id="e65d3-102">Usar o Coordenador de Transações Distribuídas da Microsoft (ODBC)</span><span class="sxs-lookup"><span data-stu-id="e65d3-102">Use Microsoft Distributed Transaction Coordinator (ODBC)</span></span>
    
### <a name="to-update-two-or-more-sql-servers-by-using-ms-dtc"></a><span data-ttu-id="e65d3-103">Para atualizar dois ou mais SQL Servers usando MS DTC</span><span class="sxs-lookup"><span data-stu-id="e65d3-103">To update two or more SQL Servers by using MS DTC</span></span>  
  
1.  <span data-ttu-id="e65d3-104">Conecte-se a MS DTC usando a função DtcGetTransactionManager MS DTC OLE.</span><span class="sxs-lookup"><span data-stu-id="e65d3-104">Connect to MS DTC by using the MS DTC OLE DtcGetTransactionManager function.</span></span> <span data-ttu-id="e65d3-105">Para obter informações sobre o MS DTC, consulte Coordenador de transações distribuídas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e65d3-105">For information about MS DTC, see Microsoft Distributed Transaction Coordinator.</span></span>  
  
2.  <span data-ttu-id="e65d3-106">Chame o SQL DriverConnect uma vez para cada conexão de Microsoft SQL Server que você deseja estabelecer.</span><span class="sxs-lookup"><span data-stu-id="e65d3-106">Call SQL DriverConnect once for each Microsoft SQL Server connection you want to establish.</span></span>  
  
3.  <span data-ttu-id="e65d3-107">Chame a função ITransactionDispenser::BeginTransaction MS DTC OLE para começar uma transação MS DTC e obter um objeto de transação que a represente.</span><span class="sxs-lookup"><span data-stu-id="e65d3-107">Call the MS DTC OLE ITransactionDispenser::BeginTransaction function to begin an MS DTC transaction and obtain a Transaction object that represents the transaction.</span></span>  
  
4.  <span data-ttu-id="e65d3-108">Chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) uma ou mais vezes para cada conexão ODBC que você deseja listar na transação MS DTC.</span><span class="sxs-lookup"><span data-stu-id="e65d3-108">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) one or more times for each ODBC connection you want to enlist in the MS DTC transaction.</span></span> <span data-ttu-id="e65d3-109">O segundo parâmetro [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) deve ser SQL_ATTR_ENLIST_IN_DTC e o terceiro, o objeto de transação (obtido na Etapa 3).</span><span class="sxs-lookup"><span data-stu-id="e65d3-109">[SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) second parameter must be SQL_ATTR_ENLIST_IN_DTC and third parameter must be the Transaction object (obtained in Step 3).</span></span>  
  
5.  <span data-ttu-id="e65d3-110">Chame [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) uma vez para cada SQL Server que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="e65d3-110">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) once for each SQL Server you want to update.</span></span>  
  
6.  <span data-ttu-id="e65d3-111">Chame a função ITransaction::Commit MS DTC OLE para confirmar a transação MS DTC.</span><span class="sxs-lookup"><span data-stu-id="e65d3-111">Call the MS DTC OLE ITransaction::Commit function to commit the MS DTC transaction.</span></span> <span data-ttu-id="e65d3-112">O objeto de transação não é mais válido.</span><span class="sxs-lookup"><span data-stu-id="e65d3-112">The Transaction object is no longer valid.</span></span>  
  
 <span data-ttu-id="e65d3-113">Para executar uma série de MS DTC transações, repita as etapas de 3 a 6.</span><span class="sxs-lookup"><span data-stu-id="e65d3-113">To perform a series of MS DTC transactions, repeat Steps 3 through 6.</span></span>  
  
 <span data-ttu-id="e65d3-114">Para liberar a referência para o objeto de transação, chame a função ITransaction::Return MS DTC OLE.</span><span class="sxs-lookup"><span data-stu-id="e65d3-114">To release the reference to the Transaction object, call the MS DTC OLE ITransaction::Return function.</span></span>  
  
 <span data-ttu-id="e65d3-115">Para usar uma conexão ODBC com uma transação MS DTC e usar a mesma conexão com uma transação do SQL Server local, chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_DTC_DONE.</span><span class="sxs-lookup"><span data-stu-id="e65d3-115">To use an ODBC connection with an MS DTC transaction, and then use the same connection with a local SQL Server transaction, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_DTC_DONE.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e65d3-116">Você também pode chamar [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) e [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) para cada SQL Server, em vez de chamá-lo conforme sugerido nas etapas 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="e65d3-116">You can also call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) and [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) in turn for each SQL Server instead of calling them as suggested earlier in Steps 4 and 5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e65d3-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e65d3-117">See Also</span></span>  
 [<span data-ttu-id="e65d3-118">Executando transações &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="e65d3-118">Performing Transactions &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
