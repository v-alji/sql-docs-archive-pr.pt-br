---
title: Usando SQL Server conjuntos de resultados padrão | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetStmtAttr function
- ODBC cursors, default result sets
- cursors [ODBC], default result sets
- default result sets
- result sets [ODBC], default
- ODBC applications, cursors
ms.assetid: ee1db3e5-60eb-4425-8a6b-977eeced3f98
author: rothja
ms.author: jroth
ms.openlocfilehash: 18cd10dd95329f68a42497d2bea5ce63f345ceff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572067"
---
# <a name="using-sql-server-default-result-sets"></a><span data-ttu-id="fd57a-102">Usando conjuntos de resultados padrão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="fd57a-102">Using SQL Server Default Result Sets</span></span>
  <span data-ttu-id="fd57a-103">Os atributos padrão de cursor do ODBC são:</span><span class="sxs-lookup"><span data-stu-id="fd57a-103">The default ODBC cursor attributes are:</span></span>  
  
```  
SQLSetStmtAttr(hstmt, SQL_ATTR_CURSOR_TYPE, SQL_CURSOR_FORWARD_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_CONCURRENCY, SQL_CONCUR_READ_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ROW_ARRAY_SIZE, 1, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="fd57a-104">Sempre que esses atributos são definidos para seus padrões, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client usa um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] conjunto de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="fd57a-104">Whenever these attributes are set to their defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set.</span></span> <span data-ttu-id="fd57a-105">Os conjuntos de resultado padrão podem ser usados para qualquer instrução do SQL com suporte do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e são o método mais eficiente para transferir todo um conjunto de resultados para o cliente.</span><span class="sxs-lookup"><span data-stu-id="fd57a-105">Default result sets can be used for any SQL statement supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and are the most efficient method of transferring an entire result set to the client.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]<span data-ttu-id="fd57a-106">introduziu suporte para MARS (vários conjuntos de resultados ativos); Agora, os aplicativos podem ter mais de um conjunto de resultados padrão ativo por conexão.</span><span class="sxs-lookup"><span data-stu-id="fd57a-106">introduced support for multiple active result sets (MARS); applications can now have more than one active default result set per connection.</span></span> <span data-ttu-id="fd57a-107">O MARS não está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fd57a-107">MARS is not enabled by default.</span></span>  
  
 <span data-ttu-id="fd57a-108">Antes do [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], os conjuntos de resultados padrão não ofereciam suporte a várias instruções ativas na mesma conexão.</span><span class="sxs-lookup"><span data-stu-id="fd57a-108">Before [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], default result sets did not support multiple active statements on the same connection.</span></span> <span data-ttu-id="fd57a-109">Depois que uma instrução SQL é executada em uma conexão, o servidor não aceita comandos (exceto uma solicitação para cancelar o restante do conjunto de resultados) do cliente nessa conexão até que todas as linhas do conjunto de resultados sejam processadas.</span><span class="sxs-lookup"><span data-stu-id="fd57a-109">After an SQL statement is executed on a connection, the server does not accept commands (except a request to cancel the rest of the result set) from the client on that connection until all the rows in the result set have been processed.</span></span> <span data-ttu-id="fd57a-110">Para cancelar o restante de um conjunto de resultados parcialmente processado, chame [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) ou [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) com o parâmetro *fOption* definido como SQL_CLOSE.</span><span class="sxs-lookup"><span data-stu-id="fd57a-110">To cancel the remainder of a partially processed result set, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with the *fOption* parameter set to SQL_CLOSE.</span></span> <span data-ttu-id="fd57a-111">Para concluir um conjunto de resultados parcialmente processado e testar a presença de outro conjunto de resultados, chame [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="fd57a-111">To finish a partially processed result set and test for the presence of another result set, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md).</span></span> <span data-ttu-id="fd57a-112">Se um aplicativo ODBC tentar um comando em um identificador de conexão antes que um conjunto de resultados padrão seja completamente processado, a chamada gerará SQL_ERROR e uma chamada para **SQLGetDiagRec** retornará:</span><span class="sxs-lookup"><span data-stu-id="fd57a-112">If an ODBC application attempts a command on a connection handle before a default result set has been completely processed, the call generates SQL_ERROR and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState: "HY000", pfNativeError: 0  
szErrorMsg: "[Microsoft][SQL Server Native Client]  
                Connection is busy with results for another hstmt."  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd57a-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd57a-113">See Also</span></span>  
 [<span data-ttu-id="fd57a-114">Como os cursores são implementados</span><span class="sxs-lookup"><span data-stu-id="fd57a-114">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  
