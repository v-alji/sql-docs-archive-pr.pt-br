---
title: Modo assíncrono e SQLCancel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- asynchronous operations [SQL Server Native Client]
- SQLCancel function
- SQLSetConnectAttr function
- SQL Server Native Client, asynchronous operations
- ODBC functions
- ODBC applications, asynchronous operations
- SQL Server Native Client ODBC driver, asynchronous mode
ms.assetid: f31702a2-df76-4589-ac3b-da5412c03dc2
author: rothja
ms.author: jroth
ms.openlocfilehash: 9071c6821e6edeb577b639223e42899d2927bced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576304"
---
# <a name="asynchronous-mode-and-sqlcancel"></a><span data-ttu-id="19176-102">Modo assíncrono e SQLCancel</span><span class="sxs-lookup"><span data-stu-id="19176-102">Asynchronous Mode and SQLCancel</span></span>
  <span data-ttu-id="19176-103">Algumas funções ODBC podem operar de forma síncrona ou assíncrona.</span><span class="sxs-lookup"><span data-stu-id="19176-103">Some ODBC functions can operate either synchronously or asynchronously.</span></span> <span data-ttu-id="19176-104">O aplicativo pode habilitar operações assíncronas para um identificador de instrução ou um identificador de conexão.</span><span class="sxs-lookup"><span data-stu-id="19176-104">The application can enable asynchronous operations for either a statement handle or a connection handle.</span></span> <span data-ttu-id="19176-105">Se a opção for definida para um identificador de conexão, ela afetará todos os identificadores de instrução do identificador de conexão.</span><span class="sxs-lookup"><span data-stu-id="19176-105">If the option is set for a connection handle, it affects all statement handles on the connection handle.</span></span> <span data-ttu-id="19176-106">O aplicativo usa as seguintes instruções para habilitar ou desabilitar operações assíncronas:</span><span class="sxs-lookup"><span data-stu-id="19176-106">The application uses the following statements to enable or disable asynchronous operations:</span></span>  
  
```  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="19176-107">Quando um aplicativo chama uma função ODBC no modo síncrono, o driver não retorna o controle para o aplicativo antes de ser notificado que o servidor concluiu o comando.</span><span class="sxs-lookup"><span data-stu-id="19176-107">When an application calls an ODBC function in synchronous mode, the driver does not return control to the application until it is notified that the server has completed the command.</span></span>  
  
 <span data-ttu-id="19176-108">Na operação assíncrona, o driver retorna o controle para o aplicativo, mesmo antes de enviar o comando ao servidor.</span><span class="sxs-lookup"><span data-stu-id="19176-108">When operating asynchronously, the driver immediately returns control to the application, even before sending the command to the server.</span></span> <span data-ttu-id="19176-109">O driver define o código de retorno como SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="19176-109">The driver sets the return code to SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="19176-110">O aplicativo poderá, então, executar outro trabalho.</span><span class="sxs-lookup"><span data-stu-id="19176-110">The application can then perform other work.</span></span>  
  
 <span data-ttu-id="19176-111">Quando o aplicativo testa para concluir o comando, faz a mesma chamada de função com os mesmos parâmetros para o driver.</span><span class="sxs-lookup"><span data-stu-id="19176-111">When the application tests for completion of the command, it makes the same function call with the same parameters to the driver.</span></span> <span data-ttu-id="19176-112">Se o driver ainda não tiver recebido uma resposta do servidor, novamente retornará SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="19176-112">If the driver has not yet received an answer from the server, it will again return SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="19176-113">O aplicativo deve testar o comando periodicamente até que o código de retorno seja diferente de SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="19176-113">The application must test the command periodically until the return code is something other than SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="19176-114">Quando o aplicativo obtiver algum outro código de retorno, até mesmo SQL_ERROR, ele poderá determinar que o comando foi concluído.</span><span class="sxs-lookup"><span data-stu-id="19176-114">When the application gets some other return code, even SQL_ERROR, it can determine that the command has completed.</span></span>  
  
 <span data-ttu-id="19176-115">Às vezes um comando fica pendente por muito tempo.</span><span class="sxs-lookup"><span data-stu-id="19176-115">Sometimes a command is outstanding for a long time.</span></span> <span data-ttu-id="19176-116">Se o aplicativo precisar cancelar o comando sem esperar por uma resposta, ele poderá fazer isso chamando **SQLCancel** com o mesmo identificador de instrução que o comando pendente.</span><span class="sxs-lookup"><span data-stu-id="19176-116">If the application needs to cancel the command without waiting for a reply, it can do so by calling **SQLCancel** with the same statement handle as the outstanding command.</span></span> <span data-ttu-id="19176-117">Essa é a única vez que **SQLCancel** deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="19176-117">This is the only time **SQLCancel** should be used.</span></span> <span data-ttu-id="19176-118">Alguns programadores usam **SQLCancel** quando processavam partes por meio de um conjunto de resultados e desejam cancelar o restante do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="19176-118">Some programmers use **SQLCancel** when they have processed part way through a result set and want to cancel the rest of the result set.</span></span> <span data-ttu-id="19176-119">[SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) ou [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) devem ser usados para cancelar o restante de um conjunto de resultados pendentes, e não **SQLCancel**.</span><span class="sxs-lookup"><span data-stu-id="19176-119">[SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) should be used to cancel the remainder of an outstanding result set, not **SQLCancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19176-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="19176-120">See Also</span></span>  
 [<span data-ttu-id="19176-121">Criando um aplicativo de driver ODBC do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="19176-121">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
