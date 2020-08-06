---
title: Nível de isolamento da transação do cursor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- isolation levels [ODBC]
- ODBC applications, row versioning
- cursors [ODBC], isolation levels
- ODBC cursors, isolation levels
- row versioning [SQL Server], ODBC
ms.assetid: 0c6663a4-5a25-44aa-8fe4-e35af9bf4a83
author: rothja
ms.author: jroth
ms.openlocfilehash: 30f3dc8a9136a7cbe1d5897cb0bcc9fff8c35ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684208"
---
# <a name="cursor-transaction-isolation-level"></a><span data-ttu-id="eee63-102">Nível de isolamento da transação de cursor</span><span class="sxs-lookup"><span data-stu-id="eee63-102">Cursor Transaction Isolation Level</span></span>
  <span data-ttu-id="eee63-103">O comportamento de bloqueio completo de cursores se baseia em uma interação entre atributos de simultaneidade e o nível de isolamento da transação definidos pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="eee63-103">The complete locking behavior of cursors is based on an interaction between concurrency attributes and the transaction isolation level set by the client.</span></span> <span data-ttu-id="eee63-104">Os clientes ODBC definem o nível de isolamento da transação usando os atributos [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION ou SQL_COPT_SS_TXN_ISOLATION.</span><span class="sxs-lookup"><span data-stu-id="eee63-104">ODBC clients set the transaction isolation level using the [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION or SQL_COPT_SS_TXN_ISOLATION attributes.</span></span> <span data-ttu-id="eee63-105">O comportamento de bloqueio de um ambiente de cursor específico é determinado pela combinação dos comportamentos de bloqueio das opções de nível de isolamento da transação e de simultaneidade.</span><span class="sxs-lookup"><span data-stu-id="eee63-105">The locking behavior of a specific cursor environment is determined by combining the locking behaviors of the concurrency and transaction isolation level options.</span></span>  
  
 <span data-ttu-id="eee63-106">Os seguintes níveis de isolamento da transação de cursor são suportados pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client:</span><span class="sxs-lookup"><span data-stu-id="eee63-106">The following cursor transaction isolation levels are supported by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver:</span></span>  
  
-   <span data-ttu-id="eee63-107">Leitura confirmada (SQL_TXN_READ_COMMITTED)</span><span class="sxs-lookup"><span data-stu-id="eee63-107">Read committed (SQL_TXN_READ_COMMITTED)</span></span>  
  
-   <span data-ttu-id="eee63-108">Leitura não confirmada (SQL_TXN_READ_UNCOMMITTED)</span><span class="sxs-lookup"><span data-stu-id="eee63-108">Read uncommitted (SQL_TXN_READ_UNCOMMITTED)</span></span>  
  
-   <span data-ttu-id="eee63-109">Leitura repetível (SQL_TXN_REPEATABLE_READ)</span><span class="sxs-lookup"><span data-stu-id="eee63-109">Repeatable read (SQL_TXN_REPEATABLE_READ)</span></span>  
  
-   <span data-ttu-id="eee63-110">Serializável (SQL_TXN_SERIALIZABLE)</span><span class="sxs-lookup"><span data-stu-id="eee63-110">Serializable (SQL_TXN_SERIALIZABLE)</span></span>  
  
-   <span data-ttu-id="eee63-111">Instantâneo (SQL_TXN_SS_SNAPSHOT)</span><span class="sxs-lookup"><span data-stu-id="eee63-111">Snapshot (SQL_TXN_SS_SNAPSHOT)</span></span>  
  
 <span data-ttu-id="eee63-112">Observe que a API ODBC especifica níveis de isolamento de transação adicionais, mas eles não são suportados pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client.</span><span class="sxs-lookup"><span data-stu-id="eee63-112">Note that the ODBC API specifies additional transaction isolation levels, but these are not supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee63-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eee63-113">See Also</span></span>  
 [<span data-ttu-id="eee63-114">Propriedades do cursor</span><span class="sxs-lookup"><span data-stu-id="eee63-114">Cursor Properties</span></span>](cursor-properties.md)  
  
  
