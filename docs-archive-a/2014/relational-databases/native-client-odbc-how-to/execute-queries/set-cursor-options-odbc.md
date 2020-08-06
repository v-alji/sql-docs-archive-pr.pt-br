---
title: Definir opções de cursor (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], options
ms.assetid: 0e72b48a-fc5a-4656-8cf5-39f57d8c1565
author: rothja
ms.author: jroth
ms.openlocfilehash: 877c2596c87ce50295a15912493661c6dd4e0305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684709"
---
# <a name="set-cursor-options-odbc"></a><span data-ttu-id="90c00-102">Definir opções de cursor (ODBC)</span><span class="sxs-lookup"><span data-stu-id="90c00-102">Set Cursor Options (ODBC)</span></span>
  <span data-ttu-id="90c00-103">Para definir opções de cursor, chame [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para definir ou [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) para obter as opções de instrução que controlam o comportamento do cursor.</span><span class="sxs-lookup"><span data-stu-id="90c00-103">To set cursor options, Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get the statement options that control cursor behavior.</span></span>  
  
|<span data-ttu-id="90c00-104">*Atributo*</span><span class="sxs-lookup"><span data-stu-id="90c00-104">*Attribute*</span></span>|<span data-ttu-id="90c00-105">Especifica</span><span class="sxs-lookup"><span data-stu-id="90c00-105">Specifies</span></span>|  
|-----------------|---------------|  
|<span data-ttu-id="90c00-106">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="90c00-106">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="90c00-107">Tipo de cursor: somente avanço, estático, dinâmico ou controlado por conjunto de chaves.</span><span class="sxs-lookup"><span data-stu-id="90c00-107">Cursor type of forward-only, static, dynamic, or keyset-driven</span></span>|  
|<span data-ttu-id="90c00-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="90c00-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="90c00-109">Opção de controle de simultaneidade: somente leitura, bloqueio, otimista usando carimbos de data/hora ou otimista usando valores.</span><span class="sxs-lookup"><span data-stu-id="90c00-109">Concurrency control option of read-only, locking, optimistic using timestamps, or optimistic using values</span></span>|  
|<span data-ttu-id="90c00-110">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="90c00-110">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="90c00-111">Número de linhas recuperadas em cada busca.</span><span class="sxs-lookup"><span data-stu-id="90c00-111">Number of rows retrieved in each fetch</span></span>|  
|<span data-ttu-id="90c00-112">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="90c00-112">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="90c00-113">Cursor que mostra ou não atualizações nas linhas de cursor feitas por outras conexões.</span><span class="sxs-lookup"><span data-stu-id="90c00-113">Cursor that does or does not show updates to cursor rows made by other connections</span></span>|  
|<span data-ttu-id="90c00-114">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="90c00-114">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="90c00-115">Cursor que pode avançar e recuar.</span><span class="sxs-lookup"><span data-stu-id="90c00-115">Cursor that can be scrolled forward and backward</span></span>|  
  
 <span data-ttu-id="90c00-116">Os valores padrão desses atributos (somente avanço, somente leitura, tamanho de conjunto de linhas de 1) não usam cursores de servidor.</span><span class="sxs-lookup"><span data-stu-id="90c00-116">The default values for these attributes (forward-only, read-only, rowset size of 1) do not use server cursors.</span></span> <span data-ttu-id="90c00-117">Para usar cursores de servidor, pelo menos um desses atributos deve ser definido como um valor diferente do padrão e a instrução executada deve ser uma instrução SELECT ou um procedimento armazenado que contém uma única instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="90c00-117">To use server cursors, at least one of these attributes must be set to a value other than the default, and the statement being executed must be a single SELECT statement or a stored procedure that contains a single SELECT statement.</span></span> <span data-ttu-id="90c00-118">Quando cursores de servidor forem usados, as instruções SELECT não poderão usar cláusulas às quais os cursores de servidor não ofereçam suporte: COMPUTE, COMPUTE BY, FOR BROWSE e INTO.</span><span class="sxs-lookup"><span data-stu-id="90c00-118">When using server cursors, SELECT statements cannot use clauses not supported by server cursors: COMPUTE, COMPUTE BY, FOR BROWSE, and INTO.</span></span>  
  
 <span data-ttu-id="90c00-119">Você pode controlar o tipo de cursor usado ao definir SQL_ATTR_CURSOR_TYPE e SQL_ATTR_CONCURRENCY ou ao definir SQL_ATTR_CURSOR_SENSITIVITY e SQL_ATTR_CURSOR_SCROLLABLE.</span><span class="sxs-lookup"><span data-stu-id="90c00-119">You can control the type of cursor used either by setting SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="90c00-120">Você não deve misturar os dois métodos de especificação de comportamento de cursor.</span><span class="sxs-lookup"><span data-stu-id="90c00-120">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90c00-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="90c00-121">Example</span></span>  
 <span data-ttu-id="90c00-122">O exemplo a seguir aloca um identificador de instrução, define um tipo de cursor dinâmico com simultaneidade otimista de controle de versão de linha e, então, executa uma instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="90c00-122">The following sample allocates a statement handle, sets a dynamic cursor type with row versioning optimistic concurrency, and then executes a SELECT.</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_TYPE, (SQLPOINTER)SQL_CURSOR_DYNAMIC, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CONCURRENCY, SQLPOINTER)SQL_CONCUR_ROWVER, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, SELECT au_lname FROM authors", SQL_NTS);  
```  
  
## <a name="example"></a><span data-ttu-id="90c00-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="90c00-123">Example</span></span>  
 <span data-ttu-id="90c00-124">O exemplo a seguir aloca um identificador de instrução, define um cursor sensível rolável e, então, executa uma instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="90c00-124">The following sample allocates a statement handle, sets a scrollable, sensitive cursor, and then executes a SELECT</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
  
// Set the cursor options and execute the statement.  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SCROLLABLE, SQLPOINTER)SQL_SCROLLABLE, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SENSITIVITY, SQLPOINTER)SQL_INSENSITIVE, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, select au_lname from authors", SQL_NTS);  
```  
  
## <a name="see-also"></a><span data-ttu-id="90c00-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90c00-125">See Also</span></span>  
 [<span data-ttu-id="90c00-126">Tópicos de instruções sobre como executar consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="90c00-126">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
