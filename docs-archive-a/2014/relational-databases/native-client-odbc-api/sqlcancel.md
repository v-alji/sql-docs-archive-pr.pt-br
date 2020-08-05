---
title: SQLCancel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLCancel function
ms.assetid: d4c965ae-c1ac-4e9d-b4b9-32b561401106
author: rothja
ms.author: jroth
ms.openlocfilehash: dc3d86229501f80b25fb077788d1835a5f4f5c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572998"
---
# <a name="sqlcancel"></a><span data-ttu-id="9c9fe-102">SQLCancel</span><span class="sxs-lookup"><span data-stu-id="9c9fe-102">SQLCancel</span></span>
  <span data-ttu-id="9c9fe-103">O tópico [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) diz que, no ODBC 2. x, se um aplicativo chama `SQLCancel` quando nenhum processamento está sendo feito na instrução, `SQLCancel` tem o mesmo efeito que `SQLFreeStmt` com a `SQL_CLOSE` opção; esse comportamento é definido somente para fins de integridade e os aplicativos devem chamar `SQLFreeStmt` ou `SQLCloseCursor` fechar cursores.</span><span class="sxs-lookup"><span data-stu-id="9c9fe-103">The [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) topic says that in ODBC 2.x, if an application calls `SQLCancel` when no processing is being done on the statement, `SQLCancel` has the same effect as `SQLFreeStmt` with the `SQL_CLOSE` option; this behavior is defined only for completeness and applications should call `SQLFreeStmt` or `SQLCloseCursor` to close cursors.</span></span> <span data-ttu-id="9c9fe-104">Mas mesmo que seu aplicativo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Cliente defina a versão do ODBC API para que seja 3.5.x ou posterior, a função `SQLCancel` usará o comportamento do ODBC 2.x.</span><span class="sxs-lookup"><span data-stu-id="9c9fe-104">But even if your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client application sets the ODBC API version to be 3.5.x or later, the `SQLCancel` function will use the ODBC 2.x behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c9fe-105">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9c9fe-105">See Also</span></span>  
 <span data-ttu-id="9c9fe-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span><span class="sxs-lookup"><span data-stu-id="9c9fe-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span></span>  
 [<span data-ttu-id="9c9fe-107">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="9c9fe-107">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
