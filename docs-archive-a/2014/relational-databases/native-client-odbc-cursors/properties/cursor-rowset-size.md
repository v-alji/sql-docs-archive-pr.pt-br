---
title: Tamanho do conjunto de linhas do cursor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], rowset size
- ODBC cursors, rowset size
- rowsets [ODBC]
ms.assetid: 2febe2ae-fdc1-490e-a79f-c516bc8e7c3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 83c4e55025e6e3724f354f022760b7ba1e2f10e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576338"
---
# <a name="cursor-rowset-size"></a><span data-ttu-id="dea12-102">Tamanho do conjunto de linhas de cursor</span><span class="sxs-lookup"><span data-stu-id="dea12-102">Cursor Rowset Size</span></span>
  <span data-ttu-id="dea12-103">Os cursores ODBC não se limitam a buscar uma linha de cada vez.</span><span class="sxs-lookup"><span data-stu-id="dea12-103">ODBC cursors are not limited to fetching one row at a time.</span></span> <span data-ttu-id="dea12-104">Eles podem recuperar várias linhas em cada chamada para **SQLFetch** ou [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="dea12-104">They can retrieve multiple rows in each call to **SQLFetch** or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="dea12-105">Quando você está trabalhando com um banco de dados cliente/servidor, como o Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], é mais eficaz buscar várias linhas de uma vez.</span><span class="sxs-lookup"><span data-stu-id="dea12-105">When you are working with a client/server database such as Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it is more efficient to fetch several rows at a time.</span></span> <span data-ttu-id="dea12-106">O número de linhas retornadas em uma busca é chamado de tamanho do conjunto de linhas e é especificado usando o SQL_ATTR_ROW_ARRAY_SIZE de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="dea12-106">The number of rows returned on a fetch is called the rowset size and is specified by using the SQL_ATTR_ROW_ARRAY_SIZE of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
```  
SQLUINTEGER uwRowsize;  
SQLSetStmtAttr(m_hstmt, SQL_ATTR_ROW_ARRAY_SIZE, (SQLPOINTER)uwRowsetSize, SQL_IS_UINTEGER);  
```  
  
 <span data-ttu-id="dea12-107">Os cursores com um tamanho de conjunto de linhas maior que 1 são chamados de cursores em bloco.</span><span class="sxs-lookup"><span data-stu-id="dea12-107">Cursors with a rowset size greater than 1 are called block cursors.</span></span>  
  
 <span data-ttu-id="dea12-108">Há duas opções para associar colunas do conjunto de resultados para cursores em bloco:</span><span class="sxs-lookup"><span data-stu-id="dea12-108">There are two options for binding result set columns for block cursors:</span></span>  
  
-   <span data-ttu-id="dea12-109">Associação de coluna</span><span class="sxs-lookup"><span data-stu-id="dea12-109">Column-wise binding</span></span>  
  
     <span data-ttu-id="dea12-110">Cada coluna é associada a uma matriz de variáveis.</span><span class="sxs-lookup"><span data-stu-id="dea12-110">Each column is bound to an array of variables.</span></span> <span data-ttu-id="dea12-111">Cada matriz possui o mesmo número de elementos que o tamanho do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="dea12-111">Each array has the same number of elements as the rowset size.</span></span>  
  
-   <span data-ttu-id="dea12-112">Associação de linha</span><span class="sxs-lookup"><span data-stu-id="dea12-112">Row-wise binding</span></span>  
  
     <span data-ttu-id="dea12-113">Uma matriz baseada em estruturas que armazenam os dados e indicadores de todas as colunas em uma linha.</span><span class="sxs-lookup"><span data-stu-id="dea12-113">An array is built using structures that hold the data and indicators for all the columns in a row.</span></span> <span data-ttu-id="dea12-114">A matriz tem o mesmo número de estruturas que o tamanho do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="dea12-114">The array has the same number of structures as the rowset size.</span></span>  
  
 <span data-ttu-id="dea12-115">Quando uma associação de coluna ou de linha é usada, cada chamada para **SQLFetch** ou **SQLFetchScroll** preenche as matrizes associadas com os dados do conjunto de linhas recuperado.</span><span class="sxs-lookup"><span data-stu-id="dea12-115">When either column-wise or row-wise binding is used, each call to **SQLFetch** or **SQLFetchScroll** fills the bound arrays with data from the rowset retrieved.</span></span>  
  
 <span data-ttu-id="dea12-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) também pode ser usado para recuperar dados de coluna de um cursor de bloco.</span><span class="sxs-lookup"><span data-stu-id="dea12-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) can also be used to retrieve column data from a block cursor.</span></span> <span data-ttu-id="dea12-117">Como **SQLGetData** trabalha uma linha de cada vez, **SQLSetPos** deve ser chamado para definir uma linha específica no conjunto de linhas como a linha atual antes de chamar **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="dea12-117">Because **SQLGetData** works one row at a time, **SQLSetPos** must be called to set a specific row in the rowset as the current row before calling **SQLGetData**.</span></span>  
  
 <span data-ttu-id="dea12-118">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client oferece uma otimização usando conjuntos de linhas para recuperar um conjunto de resultados inteiro rapidamente.</span><span class="sxs-lookup"><span data-stu-id="dea12-118">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers an optimization using rowsets to retrieve a whole result set quickly.</span></span> <span data-ttu-id="dea12-119">Para usar essa otimização, defina os atributos de cursor para seus padrões (somente encaminhamento, somente leitura, tamanho do conjunto de linhas = 1) no momento em que **SQLExecDirect** ou **SQLExecute** é chamado.</span><span class="sxs-lookup"><span data-stu-id="dea12-119">To use this optimization, set the cursor attributes to their defaults (forward-only, read-only, rowset size = 1) at the time **SQLExecDirect** or **SQLExecute** is called.</span></span> <span data-ttu-id="dea12-120">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client configura um conjunto de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="dea12-120">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver sets up a default result set.</span></span> <span data-ttu-id="dea12-121">Esse procedimento é mais eficaz do que o uso de cursores de servidor ao transferir resultados para o cliente sem fazer rolagem.</span><span class="sxs-lookup"><span data-stu-id="dea12-121">This is more efficient than server cursors when transferring results to the client without scrolling.</span></span> <span data-ttu-id="dea12-122">Depois que a instrução tiver sido executada, aumente o tamanho do conjunto de linhas e use a associação de coluna ou de linha.</span><span class="sxs-lookup"><span data-stu-id="dea12-122">After the statement has been executed, increase the rowset size and use either column-wise or row-wise binding.</span></span> <span data-ttu-id="dea12-123">Isso permite [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usar um conjunto de resultados padrão para enviar linhas de resultado com eficiência para o cliente, enquanto o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client efetua pull continuamente de linhas dos buffers de rede no cliente.</span><span class="sxs-lookup"><span data-stu-id="dea12-123">This lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] use a default result set to send result rows efficiently to the client, while the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver continuously pulls rows from the network buffers on the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea12-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dea12-124">See Also</span></span>  
 [<span data-ttu-id="dea12-125">Propriedades do cursor</span><span class="sxs-lookup"><span data-stu-id="dea12-125">Cursor Properties</span></span>](cursor-properties.md)  
  
  
