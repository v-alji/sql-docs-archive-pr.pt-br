---
title: SQLExecute | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLExecute function
ms.assetid: 4d7db8b6-611f-4fe4-be85-2a407059de45
author: rothja
ms.author: jroth
ms.openlocfilehash: 514436c65ef103cafae2189a03b560255b447eda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572987"
---
# <a name="sqlexecute"></a><span data-ttu-id="2781c-102">SQLExecute</span><span class="sxs-lookup"><span data-stu-id="2781c-102">SQLExecute</span></span>
  <span data-ttu-id="2781c-103">Se o atributo de instrução SQL_SOPT_SS_PARAM_FOCUS não estiver definido como 0, SQLExecute retornará SQL_ERROR e gerará um registro de diagnóstico com SQLSTATE = HY024 e a mensagem "valor de atributo inválido SQL_SOPT_SS_PARAM_FOCUS (deve ser zero em tempo de execução)".</span><span class="sxs-lookup"><span data-stu-id="2781c-103">If the statement attribute SQL_SOPT_SS_PARAM_FOCUS is not set to 0, SQLExecute will return SQL_ERROR and generate a diagnostic record with SQLSTATE=HY024 and the message "Invalid attribute value, SQL_SOPT_SS_PARAM_FOCUS (must be zero at execution time)".</span></span> <span data-ttu-id="2781c-104">Para obter mais informações sobre SQL_SPOT_SS_PARAM_FOCUS, consulte [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="2781c-104">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2781c-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="2781c-105">Remarks</span></span>  
 <span data-ttu-id="2781c-106">Para obter mais informações sobre parâmetros com valor de tabela, consulte [parâmetros com valor de tabela &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="2781c-106">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2781c-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2781c-107">See Also</span></span>  
 <span data-ttu-id="2781c-108">[SQLExecute](https://go.microsoft.com/fwlink/?LinkId=80708) </span><span class="sxs-lookup"><span data-stu-id="2781c-108">[SQLExecute](https://go.microsoft.com/fwlink/?LinkId=80708) </span></span>  
 [<span data-ttu-id="2781c-109">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="2781c-109">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
