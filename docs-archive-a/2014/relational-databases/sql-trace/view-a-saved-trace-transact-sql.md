---
title: Exibir um rastreamento salvo (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], viewing
- displaying traces
- viewing traces
ms.assetid: 3a95a816-aa89-4d5f-858c-968a9cb3ee87
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8b67760d575b651b089a6936adc945d74a1c62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686217"
---
# <a name="view-a-saved-trace-transact-sql"></a><span data-ttu-id="7f8fc-102">Exibir um rastreamento salvo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7f8fc-102">View a Saved Trace (Transact-SQL)</span></span>
  <span data-ttu-id="7f8fc-103">Este tópico descreve como usar funções internas para exibir um rastreamento salvo.</span><span class="sxs-lookup"><span data-stu-id="7f8fc-103">This topic describes how to use built-in functions to view a saved trace.</span></span>  
  
### <a name="to-view-a-specific-trace"></a><span data-ttu-id="7f8fc-104">Exibir um rastreamento específico</span><span class="sxs-lookup"><span data-stu-id="7f8fc-104">To view a specific trace</span></span>  
  
1.  <span data-ttu-id="7f8fc-105">Execute **fn_trace_getinfo** especificando a identificação do rastreamento sobre o qual informações são necessárias.</span><span class="sxs-lookup"><span data-stu-id="7f8fc-105">Execute **fn_trace_getinfo** by specifying the ID of the trace about which information is needed.</span></span> <span data-ttu-id="7f8fc-106">Esta função retorna uma tabela que lista o rastreamento, a propriedade de rastreamento e as informações sobre a propriedade.</span><span class="sxs-lookup"><span data-stu-id="7f8fc-106">This function returns a table that lists the trace, trace property, and information about the property.</span></span>  
  
     <span data-ttu-id="7f8fc-107">Invoque a função deste modo:</span><span class="sxs-lookup"><span data-stu-id="7f8fc-107">Invoke the function this way:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(trace_id)  
    ```  
  
### <a name="to-view-all-existing-traces"></a><span data-ttu-id="7f8fc-108">Exibir todos os rastreamentos existentes</span><span class="sxs-lookup"><span data-stu-id="7f8fc-108">To view all existing traces</span></span>  
  
1.  <span data-ttu-id="7f8fc-109">Execute **fn_trace_getinfo** especificando `0` ou `default`.</span><span class="sxs-lookup"><span data-stu-id="7f8fc-109">Execute **fn_trace_getinfo** by specifying `0` or `default`.</span></span> <span data-ttu-id="7f8fc-110">Esta função retorna uma tabela que lista todos os rastreamentos, suas propriedades e as informações sobre essas propriedades.</span><span class="sxs-lookup"><span data-stu-id="7f8fc-110">This function returns a table that lists all the traces, their properties, and information about these properties.</span></span>  
  
     <span data-ttu-id="7f8fc-111">Chame a função como segue:</span><span class="sxs-lookup"><span data-stu-id="7f8fc-111">Invoke the function as follows:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(default)  
    ```  
  
## <a name="net-framework-security"></a><span data-ttu-id="7f8fc-112">Segurança do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7f8fc-112">.NET Framework Security</span></span>  
 <span data-ttu-id="7f8fc-113">Para executar a função interna **fn_trace_getinfo**, o usuário precisa da seguinte permissão:</span><span class="sxs-lookup"><span data-stu-id="7f8fc-113">To run the built-in function **fn_trace_getinfo**, the user needs the following permission:</span></span>  
  
 <span data-ttu-id="7f8fc-114">ALTER TRACE no servidor.</span><span class="sxs-lookup"><span data-stu-id="7f8fc-114">ALTER TRACE on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f8fc-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7f8fc-115">See Also</span></span>  
 <span data-ttu-id="7f8fc-116">[sys.fn_trace_getinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7f8fc-116">[sys.fn_trace_getinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span></span>  
 [<span data-ttu-id="7f8fc-117">Exibir e analisar rastreamentos com o SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="7f8fc-117">View and Analyze Traces with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/view-and-analyze-traces-with-sql-server-profiler.md)  
  
  
