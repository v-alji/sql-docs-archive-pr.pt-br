---
title: Manipulando erros e mensagens | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, about error handling
- errors [ODBC]
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], about messages
- ODBC error handling
- SQL_INVALID_HANDLE return code
- errors [ODBC], about error handling
- messages [ODBC]
ms.assetid: 74ea9630-e482-4a46-bb45-f5234f079b48
author: rothja
ms.author: jroth
ms.openlocfilehash: 4701b3224b87e7d19f1121f193d4be20f9d4c441
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679948"
---
# <a name="handling-errors-and-messages"></a><span data-ttu-id="d0828-102">Tratando de erros e mensagens</span><span class="sxs-lookup"><span data-stu-id="d0828-102">Handling Errors and Messages</span></span>
  <span data-ttu-id="d0828-103">Quando um aplicativo chama uma função ODBC, o driver executa a função e retorna informações de diagnóstico de duas formas: um código de retorno indica o êxito ou a falha geral de uma função ODBC, e registros de diagnóstico fornecem informações detalhadas sobre a função.</span><span class="sxs-lookup"><span data-stu-id="d0828-103">When an application calls an ODBC function, the driver executes the function and returns diagnostic information in two ways: A return code indicates the overall success or failure of an ODBC function, and diagnostic records provide detailed information about the function.</span></span> <span data-ttu-id="d0828-104">Os registros de diagnóstico incluem um registro de cabeçalho e registros de status.</span><span class="sxs-lookup"><span data-stu-id="d0828-104">Diagnostic records include a header record and status records.</span></span> <span data-ttu-id="d0828-105">Pelo menos um registro de diagnóstico, o registro de cabeçalho, será retornado, mesmo que a função tenha êxito.</span><span class="sxs-lookup"><span data-stu-id="d0828-105">At least one diagnostic record, the header record, is returned even if the function succeeds.</span></span>  
  
 <span data-ttu-id="d0828-106">As informações de diagnóstico são usadas em tempo de desenvolvimento para capturar erros de programação, como identificadores inválidos e erros de sintaxe em instruções SQL embutidas em código.</span><span class="sxs-lookup"><span data-stu-id="d0828-106">Diagnostic information is used at development time to catch programming errors, such as invalid handles and syntax errors in hard-coded SQL statements.</span></span> <span data-ttu-id="d0828-107">Elas também são usadas em tempo de execução para capturar erros e avisos de tempo de execução, como truncamento de dados, violações de regras e erros de sintaxe em instruções SQL inseridas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="d0828-107">It is also used at run time to catch run-time errors and warnings, such as data truncation, rule violations, and syntax errors in SQL statements entered by the user.</span></span> <span data-ttu-id="d0828-108">Em geral, a lógica de programação se baseia em códigos de retorno.</span><span class="sxs-lookup"><span data-stu-id="d0828-108">Program logic is generally based on return codes.</span></span>  
  
 <span data-ttu-id="d0828-109">Por exemplo, depois que um aplicativo chama **SQLFetch** para recuperar as linhas em um conjunto de resultados, o código de retorno indica se o final do conjunto de resultados foi atingido (SQL_NO_DATA), se alguma mensagem informativa foi retornada (SQL_SUCCESS_WITH_INFO) ou se ocorreu um erro (SQL_ERROR).</span><span class="sxs-lookup"><span data-stu-id="d0828-109">For example, after an application calls **SQLFetch** to retrieve the rows in a result set, the return code indicates whether the end of the result set was reached (SQL_NO_DATA), if any informational messages were returned (SQL_SUCCESS_WITH_INFO), or if an error occurred (SQL_ERROR).</span></span>  
  
 <span data-ttu-id="d0828-110">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client retornar algo diferente de SQL_SUCCESS, o aplicativo poderá chamar **SQLGetDiagRec** para recuperar qualquer mensagem de erro ou informativa.</span><span class="sxs-lookup"><span data-stu-id="d0828-110">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns anything other than SQL_SUCCESS, the application can call **SQLGetDiagRec** to retrieve any informational or error messages.</span></span> <span data-ttu-id="d0828-111">Use **SQLGetDiagRec** para rolar para cima e para baixo no conjunto de mensagens se houver mais de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="d0828-111">Use **SQLGetDiagRec** to scroll up and down the message set if there is more than one message.</span></span>  
  
 <span data-ttu-id="d0828-112">O código de retorno SQL_INVALID_HANDLE sempre indica um erro de programação e nunca deve ser encontrado em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d0828-112">The return code SQL_INVALID_HANDLE always indicates a programming error and should never be encountered at run time.</span></span> <span data-ttu-id="d0828-113">Todos os outros códigos de retorno fornecem informações, embora SQL_ERROR possa indicar um erro de programação.</span><span class="sxs-lookup"><span data-stu-id="d0828-113">All other return codes provide run-time information, although SQL_ERROR may indicate a programming error.</span></span>  
  
 <span data-ttu-id="d0828-114">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] API nativa original, DB-Library para C, permite que um aplicativo instale as funções de tratamento de erros de retorno de chamada e tratamento de mensagens que retornam erros ou mensagens.</span><span class="sxs-lookup"><span data-stu-id="d0828-114">The original [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native API, DB-Library for C, allows an application to install callback error-handling and message-handling functions that return errors or messages.</span></span> <span data-ttu-id="d0828-115">Algumas instruções [!INCLUDE[tsql](../../includes/tsql-md.md)], como PRINT, RAISERROR, DBCC e SET, retornam seus resultados para a função de manipulador de mensagens de DB-Library e não para um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="d0828-115">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, such as PRINT, RAISERROR, DBCC, and SET, return their results to the DB-Library message handler function instead of to a result set.</span></span> <span data-ttu-id="d0828-116">Porém, a API ODBC não tem nenhum recurso de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="d0828-116">However, the ODBC API has no such callback capability.</span></span> <span data-ttu-id="d0828-117">Quando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client detecta mensagens retornando do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ele define o código de retorno do ODBC para SQL_SUCCESS_WITH_INFO ou SQL_ERROR e retorna a mensagem como um ou mais registros de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d0828-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver detects messages coming back from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it sets the ODBC return code to SQL_SUCCESS_WITH_INFO or SQL_ERROR and returns the message as one or more diagnostic records.</span></span> <span data-ttu-id="d0828-118">Portanto, um aplicativo ODBC deve testar cuidadosamente esses códigos de retorno e chamar **SQLGetDiagRec** para recuperar dados de mensagem.</span><span class="sxs-lookup"><span data-stu-id="d0828-118">Therefore, an ODBC application must carefully test for these return codes and call **SQLGetDiagRec** to retrieve message data.</span></span>  
  
 <span data-ttu-id="d0828-119">Para obter informações sobre como rastrear erros, confira [Rastreamento do acesso a dados](https://go.microsoft.com/fwlink/?LinkId=125805).</span><span class="sxs-lookup"><span data-stu-id="d0828-119">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="d0828-120">Para obter informações sobre aprimoramentos no rastreamento de erros adicionados em [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], confira [Acessar informações de diagnóstico nos logs de eventos estendidos](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="d0828-120">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d0828-121">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d0828-121">In This Section</span></span>  
  
-   [<span data-ttu-id="d0828-122">Processando instruções que geram mensagens</span><span class="sxs-lookup"><span data-stu-id="d0828-122">Processing Statements That Generate Messages</span></span>](processing-statements-that-generate-messages.md)  
  
-   [<span data-ttu-id="d0828-123">Registros e campos de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d0828-123">Diagnostic Records and Fields</span></span>](diagnostic-records-and-fields.md)  
  
-   [<span data-ttu-id="d0828-124">Números de erro nativos</span><span class="sxs-lookup"><span data-stu-id="d0828-124">Native Error Numbers</span></span>](native-error-numbers.md)  
  
-   [<span data-ttu-id="d0828-125">SQLSTATE &#40;códigos de erro ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="d0828-125">SQLSTATE &#40;ODBC Error Codes&#41;</span></span>](sqlstate-odbc-error-codes.md)  
  
-   [<span data-ttu-id="d0828-126">Mensagens de erro</span><span class="sxs-lookup"><span data-stu-id="d0828-126">Error Messages</span></span>](error-messages.md)  
  
## <a name="see-also"></a><span data-ttu-id="d0828-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d0828-127">See Also</span></span>  
 [<span data-ttu-id="d0828-128">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="d0828-128">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
