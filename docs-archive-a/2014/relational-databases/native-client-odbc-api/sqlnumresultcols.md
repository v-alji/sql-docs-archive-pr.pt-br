---
title: SQLNumResultCols | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLNumResultCols function
ms.assetid: f79d8b3c-521e-4e50-a564-21d73ae5767b
author: rothja
ms.author: jroth
ms.openlocfilehash: 45e72165eef621dc377b02ed3d2e7e1e3cf7ab8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583010"
---
# <a name="sqlnumresultcols"></a><span data-ttu-id="0aad2-102">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="0aad2-102">SQLNumResultCols</span></span>
  <span data-ttu-id="0aad2-103">Para instruções executadas, o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client não visita o servidor para informar o número de colunas em um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0aad2-103">For executed statements, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not visit the server to report the number of columns in a result set.</span></span> <span data-ttu-id="0aad2-104">Nesse caso, o `SQLNumResultCols` não causa um ida e volta do servidor.</span><span class="sxs-lookup"><span data-stu-id="0aad2-104">In this case, `SQLNumResultCols` does not cause a server roundtrip.</span></span> <span data-ttu-id="0aad2-105">Como [SQLDescribeCol](sqldescribecol.md) e [SQLColAttribute](sqlcolattribute.md), a chamada em instruções preparadas, `SQLNumResultCols` mas não executadas, gera um ida e volta do servidor.</span><span class="sxs-lookup"><span data-stu-id="0aad2-105">Like [SQLDescribeCol](sqldescribecol.md) and [SQLColAttribute](sqlcolattribute.md), calling `SQLNumResultCols` on prepared but not executed statements generates a server roundtrip.</span></span>  
  
 <span data-ttu-id="0aad2-106">Quando uma instrução ou lote de instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] retorna vários conjuntos de linha como resultado, é possível que o número de colunas do conjunto de resultados seja alterado de um conjunto para o outro.</span><span class="sxs-lookup"><span data-stu-id="0aad2-106">When a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statement batch returns multiple result row sets, it is possible for the number of result set columns to change from one set to another.</span></span> <span data-ttu-id="0aad2-107">`SQLNumResultCols`deve ser chamado para cada conjunto.</span><span class="sxs-lookup"><span data-stu-id="0aad2-107">`SQLNumResultCols` should be called for each set.</span></span> <span data-ttu-id="0aad2-108">Quando o número de colunas é alterado, o aplicativo deve associar novamente os valores de dados antes de buscar resultados de linha.</span><span class="sxs-lookup"><span data-stu-id="0aad2-108">When the number of columns changes, the application should rebind data values prior to fetching row results.</span></span> <span data-ttu-id="0aad2-109">Para obter mais informações sobre como manipular vários retornos de conjunto de resultados, consulte [SQLMoreResults](sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="0aad2-109">For more information about handling multiple result set returns, see [SQLMoreResults](sqlmoreresults.md).</span></span>  
  
 <span data-ttu-id="0aad2-110">Melhorias no mecanismo de banco de dados começando com [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permitir SQLNumResultCols para obter descrições mais precisas dos resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="0aad2-110">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow SQLNumResultCols to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="0aad2-111">Esses resultados mais precisos podem ser diferentes dos valores retornados pelo SQLNumResultCols em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0aad2-111">These more accurate results may differ from the values returned by SQLNumResultCols in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0aad2-112">Para obter mais informações, veja [Descoberta de metadados](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="0aad2-112">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aad2-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0aad2-113">See Also</span></span>  
 <span data-ttu-id="0aad2-114">[Função SQLNumResultCols](https://go.microsoft.com/fwlink/?LinkId=59359) </span><span class="sxs-lookup"><span data-stu-id="0aad2-114">[SQLNumResultCols Function](https://go.microsoft.com/fwlink/?LinkId=59359) </span></span>  
 [<span data-ttu-id="0aad2-115">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="0aad2-115">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
