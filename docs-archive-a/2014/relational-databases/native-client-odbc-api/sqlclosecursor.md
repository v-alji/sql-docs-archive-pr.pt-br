---
title: SQLCloseCursor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLCloseCursor function
ms.assetid: e7134d65-5c1c-4ae2-b119-d9b4b9a42483
author: rothja
ms.author: jroth
ms.openlocfilehash: 770a67432868516e5023d1cf0ff819501b4c130e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685657"
---
# <a name="sqlclosecursor"></a><span data-ttu-id="6f478-102">SQLCloseCursor</span><span class="sxs-lookup"><span data-stu-id="6f478-102">SQLCloseCursor</span></span>
  <span data-ttu-id="6f478-103">**SQLCloseCursor** substitui [SQLFreeStmt](sqlfreestmt.md) por um valor de *opção* de SQL_CLOSE.</span><span class="sxs-lookup"><span data-stu-id="6f478-103">**SQLCloseCursor** replaces [SQLFreeStmt](sqlfreestmt.md) with an *Option* value of SQL_CLOSE.</span></span> <span data-ttu-id="6f478-104">Após a recepção de **SQLCloseCursor**, o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client descarta linhas de conjunto de resultados pendentes.</span><span class="sxs-lookup"><span data-stu-id="6f478-104">On receipt of **SQLCloseCursor**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver discards pending result set rows.</span></span> <span data-ttu-id="6f478-105">Observe que as associações de parâmetro e coluna da instrução (se houver) são mantidas inalteradas por **SQLCloseCursor**.</span><span class="sxs-lookup"><span data-stu-id="6f478-105">Note that the statement's column and parameter bindings (if any exist) are left unaltered by **SQLCloseCursor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f478-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f478-106">See Also</span></span>  
 <span data-ttu-id="6f478-107">[SQLCloseCursor](https://go.microsoft.com/fwlink/?LinkId=59331) </span><span class="sxs-lookup"><span data-stu-id="6f478-107">[SQLCloseCursor](https://go.microsoft.com/fwlink/?LinkId=59331) </span></span>  
 [<span data-ttu-id="6f478-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="6f478-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
