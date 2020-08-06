---
title: Usar Associação de conjunto de linhas (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowset binding [ODBC]
ms.assetid: a7be05f0-6b11-4b53-9fbc-501e591eef09
author: rothja
ms.author: jroth
ms.openlocfilehash: e2e0671fd1140e72005cd1a7532ea581f077382f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568528"
---
# <a name="use-rowset-binding-odbc"></a><span data-ttu-id="0da93-102">Usar associação de conjunto de linhas (ODBC)</span><span class="sxs-lookup"><span data-stu-id="0da93-102">Use Rowset Binding (ODBC)</span></span>
    
### <a name="to-use-column-wise-binding"></a><span data-ttu-id="0da93-103">Para usar uma associação por coluna</span><span class="sxs-lookup"><span data-stu-id="0da93-103">To use column-wise binding</span></span>  
  
1.  <span data-ttu-id="0da93-104">Para cada coluna associada, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="0da93-104">For each bound column, do the following:</span></span>  
  
    -   <span data-ttu-id="0da93-105">Aloque uma matriz de R (ou mais) buffers de coluna para armazenar valores de dados, onde R é o número de linhas no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="0da93-105">Allocate an array of R (or more) column buffers to store data values, where R is number of rows in the rowset.</span></span>  
  
    -   <span data-ttu-id="0da93-106">Outra opção é alocar uma matriz de R (ou mais) buffers de coluna para armazenar comprimentos de dados.</span><span class="sxs-lookup"><span data-stu-id="0da93-106">Optionally, allocate an array of R (or more) column buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="0da93-107">Chame [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) para associar o valor de dados da coluna e as matrizes de comprimento de dados à coluna do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="0da93-107">Call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to bind the column's data value and data length arrays to the column of the rowset.</span></span>  
  
2.  <span data-ttu-id="0da93-108">Chame [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para definir os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="0da93-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="0da93-109">Defina SQL_ATTR_ROW_ARRAY_SIZE como o número de linhas no conjunto de linhas (R).</span><span class="sxs-lookup"><span data-stu-id="0da93-109">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="0da93-110">Defina SQL_ATTR_ROW_BIND_TYPE como SQL_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="0da93-110">Set SQL_ATTR_ROW_BIND_TYPE to SQL_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="0da93-111">Defina o atributo SQL_ATTR_ROWS FETCHED_PTR de modo que aponte para uma variável SQLUINTEGER que contém o número de linhas buscadas.</span><span class="sxs-lookup"><span data-stu-id="0da93-111">Set the SQL_ATTR_ROWS FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="0da93-112">Defina SQL_ATTR_ROW_STATUS_PTR de modo que aponte para uma matriz[R] de variáveis SQLUSSMALLINT que contém indicadores de status de linha.</span><span class="sxs-lookup"><span data-stu-id="0da93-112">Set SQL_ATTR_ROW_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="0da93-113">Executar a instrução.</span><span class="sxs-lookup"><span data-stu-id="0da93-113">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="0da93-114">Cada chamada para [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) ou [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) recupera R linhas e transfere os dados para as colunas associadas.</span><span class="sxs-lookup"><span data-stu-id="0da93-114">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
### <a name="to-use-row-wise-binding"></a><span data-ttu-id="0da93-115">Para usar uma associação por linha</span><span class="sxs-lookup"><span data-stu-id="0da93-115">To use row-wise binding</span></span>  
  
1.  <span data-ttu-id="0da93-116">Aloque uma matriz[R] de estruturas, onde R é o número de linhas no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="0da93-116">Allocate an array[R] of structures, where R is the number of rows in the rowset.</span></span> <span data-ttu-id="0da93-117">A estrutura tem um elemento para cada coluna e cada elemento tem duas partes:</span><span class="sxs-lookup"><span data-stu-id="0da93-117">The structure has one element for each column, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="0da93-118">A primeira parte é uma variável do tipo de dados apropriado que contém os dados de coluna.</span><span class="sxs-lookup"><span data-stu-id="0da93-118">The first part is a variable of the appropriate data type to hold the column data.</span></span>  
  
    -   <span data-ttu-id="0da93-119">A segunda parte é uma variável SQLINTEGER que contém o indicador de coluna.</span><span class="sxs-lookup"><span data-stu-id="0da93-119">The second part is a SQLINTEGER variable to hold the column status indicator.</span></span>  
  
2.  <span data-ttu-id="0da93-120">Chame [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para definir os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="0da93-120">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="0da93-121">Defina SQL_ATTR_ROW_ARRAY_SIZE como o número de linhas no conjunto de linhas (R).</span><span class="sxs-lookup"><span data-stu-id="0da93-121">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="0da93-122">Defina SQL_ATTR_ROW_BIND_TYPE como o tamanho da estrutura alocada na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="0da93-122">Set SQL_ATTR_ROW_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="0da93-123">Defina o atributo SQL_ATTR_ROWS_FETCHED_PTR de modo que aponte para uma variável SQLUINTEGER que contém o número de linhas buscadas.</span><span class="sxs-lookup"><span data-stu-id="0da93-123">Set the SQL_ATTR_ROWS_FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="0da93-124">Defina SQL_ATTR_PARAMS_STATUS_PTR de modo que aponte para uma matriz[R] de variáveis SQLUSSMALLINT que contém indicadores de status de linha.</span><span class="sxs-lookup"><span data-stu-id="0da93-124">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="0da93-125">Para cada coluna no conjunto de resultados, chame [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) para apontar o valor de dados e o ponteiro de comprimento de dados da coluna para suas variáveis no primeiro elemento da matriz de estruturas alocada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="0da93-125">For each column in the result set, call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to point the data value and data length pointer of the column to their variables in the first element of the array of structures allocated in Step 1.</span></span>  
  
4.  <span data-ttu-id="0da93-126">Executar a instrução.</span><span class="sxs-lookup"><span data-stu-id="0da93-126">Execute the statement.</span></span>  
  
5.  <span data-ttu-id="0da93-127">Cada chamada para [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) ou [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) recupera R linhas e transfere os dados para as colunas associadas.</span><span class="sxs-lookup"><span data-stu-id="0da93-127">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da93-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0da93-128">See Also</span></span>  
 <span data-ttu-id="0da93-129">[Tópicos de instruções sobre o uso de cursores &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="0da93-129">[Using Cursors How-to Topics &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="0da93-130">[Como os cursores são implementados](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span><span class="sxs-lookup"><span data-stu-id="0da93-130">[How Cursors Are Implemented](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span></span>  
 [<span data-ttu-id="0da93-131">Usar cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="0da93-131">Use Cursors &#40;ODBC&#41;</span></span>](use-cursors-odbc.md)  
  
  
