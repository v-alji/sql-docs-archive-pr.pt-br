---
title: Desconectando de uma fonte de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- disconnecting [ODBC]
- ODBC applications, disconnecting
- SQLDisconnect function
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLFreeHandle function
- ODBC data sources, disconnecting
- SQL Server Native Client ODBC driver, data sources
- ODBC functions
- SQL Server Native Client ODBC driver, connections
ms.assetid: 65b0267d-b2ab-4a59-83f2-436d90cfbf79
author: rothja
ms.author: jroth
ms.openlocfilehash: 5db3b83ab65d854f3a4d2182d9a4a1314e097681
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573949"
---
# <a name="disconnecting-from-a-data-source"></a><span data-ttu-id="ffa6b-102">Desconectando uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="ffa6b-102">Disconnecting from a Data Source</span></span>
  <span data-ttu-id="ffa6b-103">Quando um aplicativo termina de usar uma fonte de dados, ele chama **SQLDisconnect**.</span><span class="sxs-lookup"><span data-stu-id="ffa6b-103">When an application has finished using a data source, it calls **SQLDisconnect**.</span></span> <span data-ttu-id="ffa6b-104">O **SQLDisconnect** libera Todas as instruções que são alocadas na conexão e desconecta o driver da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ffa6b-104">**SQLDisconnect** frees any statements that are allocated on the connection and disconnects the driver from the data source.</span></span> <span data-ttu-id="ffa6b-105">Após a desconexão, o aplicativo pode chamar [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) para liberar o identificador de conexão.</span><span class="sxs-lookup"><span data-stu-id="ffa6b-105">After disconnecting, the application can call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the connection handle.</span></span> <span data-ttu-id="ffa6b-106">Antes de sair, um aplicativo também chama **SQLFreeHandle** para liberar o identificador do ambiente.</span><span class="sxs-lookup"><span data-stu-id="ffa6b-106">Before exiting, an application also calls **SQLFreeHandle** to free the environment handle.</span></span>  
  
 <span data-ttu-id="ffa6b-107">Depois de desconectar, um aplicativo pode reutilizar o identificador de conexão alocado para se conectar a uma outra fonte de dados ou para reconectar-se à mesma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ffa6b-107">After disconnecting, an application can reuse the allocated connection handle, either to connect to a different data source or reconnect to the same data source.</span></span> <span data-ttu-id="ffa6b-108">A decisão de permanecer conectado em vez de desconectar e reconectar posteriormente exige que o criador do aplicativo considere os custos relativos de cada opção.</span><span class="sxs-lookup"><span data-stu-id="ffa6b-108">The decision to remain connected instead of disconnecting and reconnecting later requires that the application writer consider the relative costs of each option.</span></span> <span data-ttu-id="ffa6b-109">Conectar-se a uma fonte de dados e permanecer conectado podem ser relativamente caro, dependendo do meio de conexão.</span><span class="sxs-lookup"><span data-stu-id="ffa6b-109">Connecting to a data source and remaining connected can be relatively costly, depending on the connection medium.</span></span> <span data-ttu-id="ffa6b-110">Ao fazer uma compensação, o aplicativo deve também fazer suposições sobre a probabilidade e o tempo das operações adicionais na mesma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ffa6b-110">In making a trade-off, the application must also make assumptions about the probability and timing of additional operations on the same data source.</span></span> <span data-ttu-id="ffa6b-111">Talvez o aplicativo também precise usar mais de uma conexão.</span><span class="sxs-lookup"><span data-stu-id="ffa6b-111">An application may also have to use more than one connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa6b-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ffa6b-112">See Also</span></span>  
 [<span data-ttu-id="ffa6b-113">Comunicando-se com SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="ffa6b-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
