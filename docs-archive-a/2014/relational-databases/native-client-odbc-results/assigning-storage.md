---
title: Atribuindo armazenamento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- column-wise binding [ODBC]
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- SQLBindCol function
- storing data [ODBC]
- result sets [ODBC], storage
- SQL Server Native Client ODBC driver, data storage
- row-wise binding
- binding result sets [SQL Server Native Client]
- array binding
ms.assetid: 11c81955-5300-495f-925f-9256f2587b58
author: rothja
ms.author: jroth
ms.openlocfilehash: ada18c91493d91b36ced51bf84c32513a0c5f5df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576321"
---
# <a name="assigning-storage"></a><span data-ttu-id="b969d-102">Atribuindo armazenamento</span><span class="sxs-lookup"><span data-stu-id="b969d-102">Assigning Storage</span></span>
  <span data-ttu-id="b969d-103">Um aplicativo pode atribuir armazenamento para resultados antes ou depois de executar uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="b969d-103">An application can assign storage for results before or after it executes a SQL statement.</span></span> <span data-ttu-id="b969d-104">Caso prepare ou execute a instrução SQL primeiro, um aplicativo pode consultar o conjunto de resultados antes de atribuir o armazenamento para resultados.</span><span class="sxs-lookup"><span data-stu-id="b969d-104">If an application prepares or executes the SQL statement first, it can inquire about the result set before it assigns storage for results.</span></span> <span data-ttu-id="b969d-105">Por exemplo, caso o conjunto de resultados seja desconhecido, o aplicativo deve recuperar o número de colunas antes de atribuir o armazenamento a eles.</span><span class="sxs-lookup"><span data-stu-id="b969d-105">For example, if the result set is unknown, the application must retrieve the number of columns before it can assign storage for them.</span></span>  
  
 <span data-ttu-id="b969d-106">Para associar o armazenamento de uma coluna de dados, um aplicativo chama [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)e o passa:</span><span class="sxs-lookup"><span data-stu-id="b969d-106">To associate storage for a column of data, an application calls [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)and passes it:</span></span>  
  
-   <span data-ttu-id="b969d-107">O tipo de dados no qual os dados serão convertidos.</span><span class="sxs-lookup"><span data-stu-id="b969d-107">The data type to which the data is to be converted.</span></span>  
  
-   <span data-ttu-id="b969d-108">O endereço de um buffer de saída para os dados.</span><span class="sxs-lookup"><span data-stu-id="b969d-108">The address of an output buffer for the data.</span></span>  
  
     <span data-ttu-id="b969d-109">O aplicativo deve alocar esse buffer e ser grande o bastante para manter os dados na forma em que são convertidos.</span><span class="sxs-lookup"><span data-stu-id="b969d-109">The application must allocate this buffer, and it must be large enough to hold the data in the form to which it is converted.</span></span>  
  
-   <span data-ttu-id="b969d-110">O comprimento do buffer de saída.</span><span class="sxs-lookup"><span data-stu-id="b969d-110">The length of the output buffer.</span></span>  
  
     <span data-ttu-id="b969d-111">Esse valor será ignorado se os dados retornados tiverem uma largura fixa em C como, por exemplo, um inteiro, número real ou estrutura de data.</span><span class="sxs-lookup"><span data-stu-id="b969d-111">This value is ignored if the returned data has a fixed width in C, such as an integer, real number, or date structure.</span></span>  
  
-   <span data-ttu-id="b969d-112">O endereço de um buffer de armazenamento no qual retornar o número de bytes de dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b969d-112">The address of a storage buffer in which to return the number of bytes of available data.</span></span>  
  
 <span data-ttu-id="b969d-113">Um aplicativo também pode associar colunas de conjunto de resultados a matrizes de variáveis de programa para oferecer suporte à busca das linhas de conjunto de resultados em blocos.</span><span class="sxs-lookup"><span data-stu-id="b969d-113">An application can also bind result set columns to arrays of program variables to support fetching result set rows in blocks.</span></span> <span data-ttu-id="b969d-114">Há dois tipos diferentes de associação de matriz:</span><span class="sxs-lookup"><span data-stu-id="b969d-114">There are two different types of array binding:</span></span>  
  
-   <span data-ttu-id="b969d-115">A associação que reconhece a coluna é concluída quando cada coluna é associada a sua própria matriz de variáveis.</span><span class="sxs-lookup"><span data-stu-id="b969d-115">Column-wise binding is finished when each column is bound to its own array of variables.</span></span>  
  
     <span data-ttu-id="b969d-116">A associação de coluna é especificada chamando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) com o *atributo* definido como SQL_ATTR_ROW_BIND_TYPE e *ValuePtr* definido como SQL_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="b969d-116">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to SQL_BIND_BY_COLUMN.</span></span> <span data-ttu-id="b969d-117">Todos as matrizes devem ter o mesmo número de elementos.</span><span class="sxs-lookup"><span data-stu-id="b969d-117">All the arrays must have the same number of elements.</span></span>  
  
-   <span data-ttu-id="b969d-118">A associação que reconhece a linha é concluída quando todos os parâmetros na instrução SQL são associados como uma unidade a uma matriz de estruturas que contêm as variáveis individuais dos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="b969d-118">Row-wise binding is finished when all the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>  
  
     <span data-ttu-id="b969d-119">A associação de linha é especificada chamando **SQLSetStmtAttr** com o *atributo* definido como SQL_ATTR_ROW_BIND_TYPE e *ValuePtr* definido como o tamanho da estrutura que contém as variáveis que receberão as colunas do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b969d-119">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to the size of the structure holding the variables that will receive the result set columns.</span></span>  
  
 <span data-ttu-id="b969d-120">O aplicativo também define SQL_ATTR_ROW_ARRAY_SIZE como o número de elementos nas matrizes da coluna ou da linha e define SQL_ATTR_ROW_STATUS_PTR e SQL_ATTR_ROWS_FETCHED_PTR.</span><span class="sxs-lookup"><span data-stu-id="b969d-120">The application also sets SQL_ATTR_ROW_ARRAY_SIZE to the number of elements in the column or row arrays and sets SQL_ATTR_ROW_STATUS_PTR and SQL_ATTR_ROWS_FETCHED_PTR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b969d-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b969d-121">See Also</span></span>  
 [<span data-ttu-id="b969d-122">Processando resultados &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="b969d-122">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
