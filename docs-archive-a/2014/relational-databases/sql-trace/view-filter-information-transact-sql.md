---
title: Exibir informações de filtro (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- displaying filter information
- filters [SQL Server], viewing
- filters [SQL Server], traces
- traces [SQL Server], filters
- viewing filter information
ms.assetid: b7e52c13-8c83-47c2-8cd0-af7a49eceb5c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d94a7b4a73c264c1fb3a950aa1c9615a73db956
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686215"
---
# <a name="view-filter-information-transact-sql"></a><span data-ttu-id="0d71a-102">Exibir informações de filtro (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0d71a-102">View Filter Information (Transact-SQL)</span></span>
  <span data-ttu-id="0d71a-103">Este tópico descreve como usar funções internas para exibir informações de filtro de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="0d71a-103">This topic describes how to use built-in functions to view trace filter information.</span></span>  
  
### <a name="to-view-filter-information"></a><span data-ttu-id="0d71a-104">Para exibir informações de filtro</span><span class="sxs-lookup"><span data-stu-id="0d71a-104">To view filter information</span></span>  
  
1.  <span data-ttu-id="0d71a-105">Execute **fn_trace_getfilterinfo** especificando a ID do rastreamento sobre o qual as informações de filtro são necessárias.</span><span class="sxs-lookup"><span data-stu-id="0d71a-105">Execute **fn_trace_getfilterinfo** by specifying the ID of the trace about which filter information is needed.</span></span> <span data-ttu-id="0d71a-106">Essa função retorna uma tabela que lista os filtros, as colunas nas quais os filtros são aplicados e os valores nos quais o filtro é aplicado.</span><span class="sxs-lookup"><span data-stu-id="0d71a-106">This function returns a table that lists the filters, the columns on which the filters are applied, and the values on which the filter is applied.</span></span>  
  
     <span data-ttu-id="0d71a-107">Invoque a função deste modo:</span><span class="sxs-lookup"><span data-stu-id="0d71a-107">Invoke the function this way:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getfilterinfo(trace_id)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0d71a-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0d71a-108">See Also</span></span>  
 <span data-ttu-id="0d71a-109">[sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0d71a-109">[sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql) </span></span>  
 <span data-ttu-id="0d71a-110">[Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0d71a-110">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="0d71a-111">Procedimentos armazenados do SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0d71a-111">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
