---
title: SQLEndTran | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLEndTran function
ms.assetid: 95cff841-c2d5-4e1e-a18d-f3d4696a5b85
author: rothja
ms.author: jroth
ms.openlocfilehash: e5d44756131b6133baec69e34da11055a965e2da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679947"
---
# <a name="sqlendtran"></a><span data-ttu-id="0189a-102">SQLEndTran</span><span class="sxs-lookup"><span data-stu-id="0189a-102">SQLEndTran</span></span>
  <span data-ttu-id="0189a-103">Por padrão, o driver ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fecha o cursor associado de uma instrução quando **SQLEndTran** confirma ou reverte uma operação.</span><span class="sxs-lookup"><span data-stu-id="0189a-103">By default, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver closes a statement's associated cursor when **SQLEndTran** commits or rolls back an operation.</span></span> <span data-ttu-id="0189a-104">Os cursores de servidor são fechados, a menos que eles sejam estáticos.</span><span class="sxs-lookup"><span data-stu-id="0189a-104">Server cursors are closed unless they are static.</span></span> <span data-ttu-id="0189a-105">Quando **SQLEndTran** confirma ou reverte uma operação, o comportamento do cursor associado da instrução é determinado pelo valor do atributo SQL_COPT_SS_PRESERVE_CURSORS da conexão ODBC específica do driver, definido por [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="0189a-105">When **SQLEndTran** commits or rolls back an operation, the behavior of the statement's associated cursor is determined by the value of the driver-specific ODBC connection attribute SQL_COPT_SS_PRESERVE_CURSORS, set by [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0189a-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0189a-106">See Also</span></span>  
 <span data-ttu-id="0189a-107">[Detalhes de implementação da API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="0189a-107">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 [<span data-ttu-id="0189a-108">Função SQLEndTran</span><span class="sxs-lookup"><span data-stu-id="0189a-108">SQLEndTran Function</span></span>](https://go.microsoft.com/fwlink/?LinkId=59342)  
  
  
