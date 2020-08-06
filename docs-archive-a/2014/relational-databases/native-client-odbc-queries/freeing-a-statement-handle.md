---
title: Liberando um identificador de instrução | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- reusing statement handles
- freeing statement handles
- statements [ODBC], statement handles
- SQLFreeStmt function
- ODBC applications, statements
- statement handles [ODBC]
ms.assetid: 96fdff84-0ca7-460a-a240-94ee826ea41c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8d7a1e93d222e2b87058bc878f7eca85313b4108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569404"
---
# <a name="freeing-a-statement-handle"></a><span data-ttu-id="f1831-102">Liberando um identificador de instrução</span><span class="sxs-lookup"><span data-stu-id="f1831-102">Freeing a Statement Handle</span></span>
  <span data-ttu-id="f1831-103">É mais eficiente reutilizar identificadores de instrução do que eliminá-los e alocar novos.</span><span class="sxs-lookup"><span data-stu-id="f1831-103">It is more efficient to reuse statement handles than to drop them and allocate new ones.</span></span> <span data-ttu-id="f1831-104">Antes de executar uma nova instrução SQL em um identificador de instrução, os aplicativos deverão verificar se as configurações de instrução atuais são apropriadas.</span><span class="sxs-lookup"><span data-stu-id="f1831-104">Before executing a new SQL statement on a statement handle, applications should verify that the current statement settings are appropriate.</span></span> <span data-ttu-id="f1831-105">Essas configurações incluem atributos de instrução, associações de parâmetro e associações de conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="f1831-105">These include statement attributes, parameter bindings, and result set bindings.</span></span> <span data-ttu-id="f1831-106">Geralmente, os parâmetros e os conjuntos de resultados para a instrução SQL antiga devem ser desassociados chamando [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) com as opções SQL_RESET_PARAMS e SQL_UNBIND e, em seguida, reassociar para a nova instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="f1831-106">Generally, parameters and result sets for the old SQL statement must be unbound by calling [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the SQL_RESET_PARAMS and SQL_UNBIND options and then re-bound for the new SQL statement.</span></span>  
  
 <span data-ttu-id="f1831-107">Quando o aplicativo termina de usar a instrução, ele chama [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) para liberar a instrução.</span><span class="sxs-lookup"><span data-stu-id="f1831-107">When the application has finished using the statement, it calls [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the statement.</span></span> <span data-ttu-id="f1831-108">Observe que **SQLDisconnect** libera automaticamente todas as instruções em uma conexão.</span><span class="sxs-lookup"><span data-stu-id="f1831-108">Note that **SQLDisconnect** automatically frees all statements on a connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1831-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1831-109">See Also</span></span>  
 [<span data-ttu-id="f1831-110">Executando consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f1831-110">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
