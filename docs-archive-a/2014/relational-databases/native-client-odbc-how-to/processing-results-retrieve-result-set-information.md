---
title: Recuperar informações do conjunto de resultados (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC]
- result sets [ODBC], fetching
ms.assetid: 34f235e4-f80b-4123-8764-9deb18506f14
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f7ed275eb9b6558a77160c3c7fb2fc233c199cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572046"
---
# <a name="retrieve-result-set-information-odbc"></a><span data-ttu-id="a30dc-102">Recuperar informações do conjunto de resultados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="a30dc-102">Retrieve Result Set Information (ODBC)</span></span>
    
### <a name="to-get-information-about-a-result-set"></a><span data-ttu-id="a30dc-103">Para obter informações sobre um conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="a30dc-103">To get information about a result set</span></span>  
  
1.  <span data-ttu-id="a30dc-104">Chame [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) para obter o número de colunas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="a30dc-104">Call [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns in the result set.</span></span>  
  
2.  <span data-ttu-id="a30dc-105">Para cada coluna no conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="a30dc-105">For each column in the result set:</span></span>  
  
    -   <span data-ttu-id="a30dc-106">Chame [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) para obter informações sobre a coluna de resultado.</span><span class="sxs-lookup"><span data-stu-id="a30dc-106">Call [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) to get information about the result column.</span></span>  
  
     <span data-ttu-id="a30dc-107">Ou</span><span class="sxs-lookup"><span data-stu-id="a30dc-107">Or</span></span>  
  
    -   <span data-ttu-id="a30dc-108">Chame [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) para obter informações de descritor específicas sobre a coluna de resultado.</span><span class="sxs-lookup"><span data-stu-id="a30dc-108">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) to get specific descriptor information about the result column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a30dc-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a30dc-109">See Also</span></span>  
 <span data-ttu-id="a30dc-110">[Tópicos de instruções sobre o processamento de resultados &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="a30dc-110">[Processing Results How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="a30dc-111">Determinando as características de um conjunto de resultados &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="a30dc-111">Determining the Characteristics of a Result Set &#40;ODBC&#41;</span></span>](../native-client-odbc-results/determining-the-characteristics-of-a-result-set-odbc.md)  
  
  
