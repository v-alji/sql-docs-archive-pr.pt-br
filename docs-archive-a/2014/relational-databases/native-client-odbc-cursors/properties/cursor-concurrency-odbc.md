---
title: Simultaneidade do cursor (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- concurrency [ODBC]
- cursors [ODBC], concurrency
- ODBC cursors, concurrency
ms.assetid: 68228ece-cbf1-4f19-bfdc-053884c1af48
author: rothja
ms.author: jroth
ms.openlocfilehash: c47f24152978fedf8f2c3d49ec3b721969712814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576346"
---
# <a name="cursor-concurrency-odbc"></a><span data-ttu-id="747de-102">Simultaneidade do cursor (ODBC)</span><span class="sxs-lookup"><span data-stu-id="747de-102">Cursor Concurrency (ODBC)</span></span>
  <span data-ttu-id="747de-103">As operações de cursor, assim como os tipos de cursor, são afetadas pelas opções de simultaneidade definidas pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="747de-103">Cursor operations, like cursor types, are affected by the concurrency options set by the application.</span></span> <span data-ttu-id="747de-104">As opções de simultaneidade são definidas usando a opção SQL_ATTR_CONCURRENCY de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="747de-104">Concurrency options are set using the SQL_ATTR_CONCURRENCY option of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="747de-105">Os tipos de simultaneidade são:</span><span class="sxs-lookup"><span data-stu-id="747de-105">The concurrency types are:</span></span>  
  
-   <span data-ttu-id="747de-106">Somente leitura (SQL_CONCUR_READONLY)</span><span class="sxs-lookup"><span data-stu-id="747de-106">Read-only (SQL_CONCUR_READONLY)</span></span>  
  
-   <span data-ttu-id="747de-107">Valores (SQL_CONCUR_VALUES)</span><span class="sxs-lookup"><span data-stu-id="747de-107">Values (SQL_CONCUR_VALUES)</span></span>  
  
-   <span data-ttu-id="747de-108">Versão de linha (SQL_CONCUR_ROWVER)</span><span class="sxs-lookup"><span data-stu-id="747de-108">Row version (SQL_CONCUR_ROWVER)</span></span>  
  
-   <span data-ttu-id="747de-109">Bloqueio (SQL_CONCUR_LOCK)</span><span class="sxs-lookup"><span data-stu-id="747de-109">Lock (SQL_CONCUR_LOCK)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="747de-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="747de-110">See Also</span></span>  
 [<span data-ttu-id="747de-111">Propriedades do cursor</span><span class="sxs-lookup"><span data-stu-id="747de-111">Cursor Properties</span></span>](cursor-properties.md)  
  
  
