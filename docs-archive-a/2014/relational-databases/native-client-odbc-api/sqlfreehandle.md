---
title: SQLFreeHandle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFreeHandle function
ms.assetid: d374e5c8-ed35-43bf-8dd6-c37e38d9b5f1
author: rothja
ms.author: jroth
ms.openlocfilehash: f51f031bec05715e0345507278113f4f16179a77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572519"
---
# <a name="sqlfreehandle"></a><span data-ttu-id="b3d63-102">SQLFreeHandle</span><span class="sxs-lookup"><span data-stu-id="b3d63-102">SQLFreeHandle</span></span>
  <span data-ttu-id="b3d63-103">No modo de confirmação manual, chamar **SQLFreeHandle** em um identificador de instrução com uma transação aberta causará uma reversão das alterações pendentes do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b3d63-103">In manual-commit mode, calling **SQLFreeHandle** on a statement handle with an open transaction causes a rollback of pending changes to the database.</span></span> <span data-ttu-id="b3d63-104">Chamar **SQLFreeHandle** em um identificador de instrução sempre fechará quaisquer cursores abertos e descartará resultados pendentes, liberando todos os recursos associados ao identificador de instrução.</span><span class="sxs-lookup"><span data-stu-id="b3d63-104">Calling **SQLFreeHandle** on a statement handle always closes any open cursors and discards pending results, freeing all resources associated with the statement handle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3d63-105">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b3d63-105">See Also</span></span>  
 <span data-ttu-id="b3d63-106">[Função SQLFreeHandle](https://go.microsoft.com/fwlink/?LinkId=59345) </span><span class="sxs-lookup"><span data-stu-id="b3d63-106">[SQLFreeHandle Function](https://go.microsoft.com/fwlink/?LinkId=59345) </span></span>  
 [<span data-ttu-id="b3d63-107">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="b3d63-107">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
