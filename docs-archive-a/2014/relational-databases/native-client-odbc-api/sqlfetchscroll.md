---
title: SQLFetchScroll | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFetchScroll function
ms.assetid: 524a3985-a08d-4445-99e0-bb551a666615
author: rothja
ms.author: jroth
ms.openlocfilehash: eecf9714a97577ff490b642cee5b9c380333e40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572081"
---
# <a name="sqlfetchscroll"></a><span data-ttu-id="ecff2-102">SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="ecff2-102">SQLFetchScroll</span></span>
  <span data-ttu-id="ecff2-103">**SQLFetchScroll** retorna um conjunto de linhas de dados para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ecff2-103">**SQLFetchScroll** returns one row set of data to the application.</span></span> <span data-ttu-id="ecff2-104">O tamanho do conjunto de linhas é definido com [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="ecff2-104">The size of the row set is set using [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span> <span data-ttu-id="ecff2-105">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client dá suporte a todas as instruções de busca definidas (por exemplo, SQL_FETCH_RELATIVE) com as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="ecff2-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports all defined fetch instructions (for example, SQL_FETCH_RELATIVE) with the following limitations:</span></span>  
  
-   <span data-ttu-id="ecff2-106">Se um cursor de somente avanço for definido para a instrução, SQL_FETCH_NEXT será necessário e as tentativas de busca de qualquer outro modo resultarão em erro.</span><span class="sxs-lookup"><span data-stu-id="ecff2-106">If a forward-only cursor is defined for the statement, SQL_FETCH_NEXT is required and attempts to fetch in any other fashion will result in an error return.</span></span>  
  
-   <span data-ttu-id="ecff2-107">SQL_FETCH_BOOKMARK só é suportado para cursores estáticos e controlados por conjunto de chaves.</span><span class="sxs-lookup"><span data-stu-id="ecff2-107">SQL_FETCH_BOOKMARK is supported for static and keyset-driven cursors only.</span></span>  
  
## <a name="sqlfetchscroll-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="ecff2-108">Suporte SQLFetchScroll para recursos avançados de data e hora</span><span class="sxs-lookup"><span data-stu-id="ecff2-108">SQLFetchScroll Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="ecff2-109">Os valores de coluna de resultado de tipos de data/hora são convertidos conforme descrito em [conversões de SQL para C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span><span class="sxs-lookup"><span data-stu-id="ecff2-109">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="ecff2-110">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="ecff2-110">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlfetchscroll-support-for-large-clr-udts"></a><span data-ttu-id="ecff2-111">Suporte SQLFetchScroll para UDTs CLR grandes</span><span class="sxs-lookup"><span data-stu-id="ecff2-111">SQLFetchScroll Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="ecff2-112">**SQLFetchScroll** dá suporte a UDTs (tipos definidos pelo usuário) CLR grandes.</span><span class="sxs-lookup"><span data-stu-id="ecff2-112">**SQLFetchScroll** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="ecff2-113">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="ecff2-113">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecff2-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ecff2-114">See Also</span></span>  
 <span data-ttu-id="ecff2-115">[Função SQLFetchScroll](https://go.microsoft.com/fwlink/?LinkId=59343) </span><span class="sxs-lookup"><span data-stu-id="ecff2-115">[SQLFetchScroll Function](https://go.microsoft.com/fwlink/?LinkId=59343) </span></span>  
 [<span data-ttu-id="ecff2-116">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="ecff2-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
