---
title: Resultados do processo (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- processing results [ODBC]
ms.assetid: 4810fe3f-78ee-4f0d-8bcc-a4659fbcf46f
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a22e9d7280f88de7799c31d2d0611e5299043d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684185"
---
# <a name="process-results-odbc"></a><span data-ttu-id="51252-102">Processar resultados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="51252-102">Process Results (ODBC)</span></span>
    
### <a name="to-process-results"></a><span data-ttu-id="51252-103">Para processar resultados</span><span class="sxs-lookup"><span data-stu-id="51252-103">To process results</span></span>  
  
1.  <span data-ttu-id="51252-104">Recupere informações do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="51252-104">Retrieve result set information.</span></span>  
  
2.  <span data-ttu-id="51252-105">Se forem usadas colunas associadas, para cada coluna à qual deseja associar, chame [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) para associar um buffer de programa à coluna.</span><span class="sxs-lookup"><span data-stu-id="51252-105">If bound columns are used, for each column you want to bind to, call [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) to bind a program buffer to the column.</span></span>  
  
3.  <span data-ttu-id="51252-106">Para cada linha no conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="51252-106">For each row in the result set:</span></span>  
  
    -   <span data-ttu-id="51252-107">Chame [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) para acessar a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="51252-107">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) to get the next row.</span></span>  
  
    -   <span data-ttu-id="51252-108">Se forem usadas colunas associadas, use os dados disponíveis agora nos buffers de coluna associados.</span><span class="sxs-lookup"><span data-stu-id="51252-108">If bound columns are used, use the data now available in the bound column buffers.</span></span>  
  
    -   <span data-ttu-id="51252-109">Se forem usadas colunas desassociadas, chame [SQLGetData](../native-client-odbc-api/sqlgetdata.md) uma ou mais vezes para obter os dados dessas colunas depois da última coluna associada.</span><span class="sxs-lookup"><span data-stu-id="51252-109">If unbound columns are used, call [SQLGetData](../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column.</span></span> <span data-ttu-id="51252-110">As chamadas a `SQLGetData` deveriam estar em ordem crescente de número de coluna.</span><span class="sxs-lookup"><span data-stu-id="51252-110">Calls to `SQLGetData` should be in increasing order of column number.</span></span>  
  
    -   <span data-ttu-id="51252-111">Chame `SQLGetData` várias vezes para obter dados de uma coluna de textos ou imagens.</span><span class="sxs-lookup"><span data-stu-id="51252-111">Call `SQLGetData` multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="51252-112">Quando [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) sinalizar o término do conjunto de resultados retornando SQL_NO_DATA, chame [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) para determinar se há outro conjunto de resultados disponível.</span><span class="sxs-lookup"><span data-stu-id="51252-112">When [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) signals the end of the result set by returning SQL_NO_DATA, call [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="51252-113">Se SQL_SUCCESS for retornado, outro conjunto de resultados estará disponível.</span><span class="sxs-lookup"><span data-stu-id="51252-113">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="51252-114">Se SQL_NO_DATA for retornado, nenhum outro conjunto de resultados estará disponível.</span><span class="sxs-lookup"><span data-stu-id="51252-114">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="51252-115">Se SQL_SUCCESS_WITH_INFO ou SQL_ERROR for retornado, chame [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) para determinar se a saída de uma instrução PRINT ou RAISERROR estará disponível.</span><span class="sxs-lookup"><span data-stu-id="51252-115">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
         <span data-ttu-id="51252-116">Se parâmetros de instrução associados forem usados para parâmetros de saída ou o valor retornado de um procedimento armazenado, use os dados disponíveis agora nos buffers de parâmetro associados.</span><span class="sxs-lookup"><span data-stu-id="51252-116">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span> <span data-ttu-id="51252-117">Além disso, quando são usados parâmetros associados, cada chamada para [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) ou [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) terá executado a instrução SQL por *S* vezes, em que *S* é o número de elementos na matriz de parâmetros associados.</span><span class="sxs-lookup"><span data-stu-id="51252-117">Also, when bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement *S* times, where *S* is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="51252-118">Isso significa que haverá *S* conjuntos de resultados a serem processados, em que cada conjunto de resultados inclui todos os conjuntos de resultados, parâmetros de saída e códigos de retorno geralmente retornados por uma única execução da instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="51252-118">This means that there will be *S* sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="51252-119">Quando um conjunto de resultados contém linhas computadas, cada linha computada é disponibilizada como um conjunto de resultados separado.</span><span class="sxs-lookup"><span data-stu-id="51252-119">When a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="51252-120">Esses conjuntos de resultados computados são intercalados nas linhas normais e dividem as linhas normais em vários conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="51252-120">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
5.  <span data-ttu-id="51252-121">Outra opção é chamar [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) com SQL_UNBIND para liberar qualquer buffer de coluna associado.</span><span class="sxs-lookup"><span data-stu-id="51252-121">Optionally, call [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
6.  <span data-ttu-id="51252-122">Se outro conjunto de resultados estiver disponível, vá para a Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="51252-122">If another result set is available, go to Step 1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51252-123">Para cancelar o processamento de um conjunto de resultados antes que [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) retorne SQL_NO_DATA, chame [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="51252-123">To cancel processing a result set before [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) returns SQL_NO_DATA, call [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51252-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51252-124">See Also</span></span>  
 [<span data-ttu-id="51252-125">Tópicos de instruções sobre o processamento de resultados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="51252-125">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
  
