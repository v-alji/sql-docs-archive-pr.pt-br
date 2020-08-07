---
title: Cursores de somente avanço rápido (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fast forward-only cursors
- forward-only cursors
- cursors [ODBC], fast forward-only
- ODBC cursors, fast forward-only
ms.assetid: 0707d07e-fc95-42ed-9280-b7e508ac8c62
author: rothja
ms.author: jroth
ms.openlocfilehash: de8d82a0c72ad51741a3785fba2910f691028cba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576351"
---
# <a name="fast-forward-only-cursors-odbc"></a><span data-ttu-id="d087c-102">Cursores de somente avanço rápido (ODBC)</span><span class="sxs-lookup"><span data-stu-id="d087c-102">Fast Forward-Only Cursors (ODBC)</span></span>
  <span data-ttu-id="d087c-103">Quando conectado a uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client dá suporte a otimizações de desempenho para cursores somente de encaminhamento e somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d087c-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports performance optimizations for forward-only, read-only cursors.</span></span> <span data-ttu-id="d087c-104">Os cursores de somente avanço são implementados internamente pelo driver e pelo servidor de maneira bem semelhante a conjuntos de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="d087c-104">Fast forward-only cursors are implemented internally by the driver and server in a manner very similar to default result sets.</span></span> <span data-ttu-id="d087c-105">Além de ter alto desempenho, os cursores de somente avançado também têm essas características:</span><span class="sxs-lookup"><span data-stu-id="d087c-105">Besides having high performance, fast forward-only cursors also have these characteristics:</span></span>  
  
-   <span data-ttu-id="d087c-106">Não há suporte para [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) .</span><span class="sxs-lookup"><span data-stu-id="d087c-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported.</span></span> <span data-ttu-id="d087c-107">As colunas do conjunto de resultados devem ser associadas para programar variáveis.</span><span class="sxs-lookup"><span data-stu-id="d087c-107">The result set columns must be bound to program variables.</span></span>  
  
-   <span data-ttu-id="d087c-108">O servidor fecha automaticamente o cursor quando se detecta a extremidade do cursor.</span><span class="sxs-lookup"><span data-stu-id="d087c-108">The server automatically closes the cursor when the end of the cursor is detected.</span></span> <span data-ttu-id="d087c-109">O aplicativo ainda deve chamar [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) ou [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE), mas o driver não precisa enviar a solicitação de fechamento para o servidor.</span><span class="sxs-lookup"><span data-stu-id="d087c-109">The application must still call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE), but the driver does not have to send the close request to the server.</span></span> <span data-ttu-id="d087c-110">Isso economiza uma viagem de ida-e-volta na rede até o servidor.</span><span class="sxs-lookup"><span data-stu-id="d087c-110">This saves a roundtrip across the network to the server.</span></span>  
  
 <span data-ttu-id="d087c-111">O aplicativo solicita cursores de somente avanço usando o atributo da instrução específica do driver SQL_SOPT_SS_CURSOR_OPTIONS.</span><span class="sxs-lookup"><span data-stu-id="d087c-111">The application requests fast forward-only cursors using the driver-specific statement attribute SQL_SOPT_SS_CURSOR_OPTIONS.</span></span> <span data-ttu-id="d087c-112">Quando definidos como SQL_CO_FFO, os cursores de somente avanço são habilitados sem busca automática.</span><span class="sxs-lookup"><span data-stu-id="d087c-112">When set to SQL_CO_FFO, fast forward-only cursors are enabled without autofetch.</span></span> <span data-ttu-id="d087c-113">Quando definida como SQL_CO_FFO_AF, a opção de busca automática também é habilitada.</span><span class="sxs-lookup"><span data-stu-id="d087c-113">When set to SQL_CO_FFO_AF, the autofetch option is also enabled.</span></span> <span data-ttu-id="d087c-114">Para obter mais informações sobre a busca prévia, consulte [usar a busca prévia com cursores ODBC](using-autofetch-with-odbc-cursors.md).</span><span class="sxs-lookup"><span data-stu-id="d087c-114">For more information about autofetch, see [Using Autofetch with ODBC Cursors](using-autofetch-with-odbc-cursors.md).</span></span>  
  
 <span data-ttu-id="d087c-115">Os cursores de somente avanço com busca automática podem ser usados para recuperar um pequeno conjunto de resultados com apenas uma viagem de ida-e-volta até o servidor.</span><span class="sxs-lookup"><span data-stu-id="d087c-115">Fast forward-only cursors with autofetch can be used to retrieve a small result set with only one roundtrip to the server.</span></span> <span data-ttu-id="d087c-116">Nestas etapas, *n* é o número de linhas a serem retornadas:</span><span class="sxs-lookup"><span data-stu-id="d087c-116">In these steps, *n* is the number of rows to be returned:</span></span>  
  
1.  <span data-ttu-id="d087c-117">Defina SQL_SOPT_SS_CURSOR_OPTIONS como SQL_CO_FFO_AF.</span><span class="sxs-lookup"><span data-stu-id="d087c-117">Set SQL_SOPT_SS_CURSOR_OPTIONS to SQL_CO_FFO_AF.</span></span>  
  
2.  <span data-ttu-id="d087c-118">Defina SQL_ATTR_ROW_ARRAY_SIZE como *n* + 1.</span><span class="sxs-lookup"><span data-stu-id="d087c-118">Set SQL_ATTR_ROW_ARRAY_SIZE to *n* + 1.</span></span>  
  
3.  <span data-ttu-id="d087c-119">Associe as colunas de resultado a matrizes de *n* + 1 elementos (para ser seguro se as *n* + 1 linhas forem realmente buscadas).</span><span class="sxs-lookup"><span data-stu-id="d087c-119">Bind the result columns to arrays of *n* + 1 elements (to be safe if *n* + 1 rows are actually fetched).</span></span>  
  
4.  <span data-ttu-id="d087c-120">Abra o cursor com **SQLExecDirect** ou **SQLExecute**.</span><span class="sxs-lookup"><span data-stu-id="d087c-120">Open the cursor with either **SQLExecDirect** or **SQLExecute**.</span></span>  
  
5.  <span data-ttu-id="d087c-121">Se o status de retorno for SQL_SUCCESS, chame **SQLFreeStmt** ou **SQLCloseCursor** para fechar o cursor.</span><span class="sxs-lookup"><span data-stu-id="d087c-121">If the return status is SQL_SUCCESS, then call **SQLFreeStmt** or **SQLCloseCursor** to close the cursor.</span></span> <span data-ttu-id="d087c-122">Todos os dados das linhas estarão nas variáveis de programas associados.</span><span class="sxs-lookup"><span data-stu-id="d087c-122">All data for the rows will be in the bound program variables.</span></span>  
  
 <span data-ttu-id="d087c-123">Com essas etapas, **SQLExecDirect** ou **SQLExecute** envia uma solicitação de abertura de cursor com a opção de AutoBusca habilitada.</span><span class="sxs-lookup"><span data-stu-id="d087c-123">With these steps, the **SQLExecDirect** or **SQLExecute** sends a cursor open request with the autofetch option enabled.</span></span> <span data-ttu-id="d087c-124">Nessa solicitação única do cliente, o servidor:</span><span class="sxs-lookup"><span data-stu-id="d087c-124">On that single request from the client, the server:</span></span>  
  
-   <span data-ttu-id="d087c-125">Abre o cursor.</span><span class="sxs-lookup"><span data-stu-id="d087c-125">Opens the cursor.</span></span>  
  
-   <span data-ttu-id="d087c-126">Compila o conjunto de resultados e envia as linhas para o cliente.</span><span class="sxs-lookup"><span data-stu-id="d087c-126">Builds the result set and sends the rows to the client.</span></span>  
  
-   <span data-ttu-id="d087c-127">Como o tamanho do conjunto de linhas foi definido como 1 além do número de linhas do conjunto de resultados, o servidor detecta o final do cursor e o fecha.</span><span class="sxs-lookup"><span data-stu-id="d087c-127">Because the rowset size was set to 1 more than the number of rows in the result set, the server detects the end of the cursor and closes the cursor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d087c-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d087c-128">See Also</span></span>  
 [<span data-ttu-id="d087c-129">Detalhes de programação do cursor &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="d087c-129">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
