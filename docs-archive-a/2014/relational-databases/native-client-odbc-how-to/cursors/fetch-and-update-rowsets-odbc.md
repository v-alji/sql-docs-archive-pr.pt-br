---
title: Buscar e atualizar conjuntos de linhas (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [ODBC]
ms.assetid: cf0eb3b4-8b72-49fc-a845-95edc360cf93
author: rothja
ms.author: jroth
ms.openlocfilehash: e09a3033e0883452ecd69b82c9375ed28c920da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568535"
---
# <a name="fetch-and-update-rowsets-odbc"></a><span data-ttu-id="9577c-102">Buscar e atualizar conjuntos de linhas (ODBC)</span><span class="sxs-lookup"><span data-stu-id="9577c-102">Fetch and Update Rowsets (ODBC)</span></span>
    
### <a name="to-fetch-and-update-rowsets"></a><span data-ttu-id="9577c-103">Para buscar e atualizar conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="9577c-103">To fetch and update rowsets</span></span>  
  
1.  <span data-ttu-id="9577c-104">Opcionalmente, chame [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) com SQL_ROW_ARRAY_SIZE para alterar o número de linhas (R) no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="9577c-104">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) with SQL_ROW_ARRAY_SIZE to change the number of rows (R) in the rowset.</span></span>  
  
2.  <span data-ttu-id="9577c-105">Chame [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) ou [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) para obter um conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="9577c-105">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) to get a rowset.</span></span>  
  
3.  <span data-ttu-id="9577c-106">Se forem usadas colunas associadas, use os valores e comprimentos de dados disponíveis agora nos buffers de coluna associada para o conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="9577c-106">If bound columns are used, use the data values and data lengths now available in the bound column buffers for the rowset.</span></span>  
  
     <span data-ttu-id="9577c-107">Se forem usadas colunas desassociadas, para cada chamada de linha [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) com SQL_POSITION para definir a posição do cursor; em seguida, para cada coluna desassociada:</span><span class="sxs-lookup"><span data-stu-id="9577c-107">If unbound columns are used, for each row call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) with SQL_POSITION to set the cursor position; then, for each unbound column:</span></span>  
  
    -   <span data-ttu-id="9577c-108">Chame [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) uma ou mais vezes para obter os dados de colunas desassociadas após a última coluna associada do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="9577c-108">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column of the rowset.</span></span> <span data-ttu-id="9577c-109">As chamadas para [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) devem estar na ordem de aumento do número da coluna.</span><span class="sxs-lookup"><span data-stu-id="9577c-109">Calls to [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) should be in order of increasing column number.</span></span>  
  
    -   <span data-ttu-id="9577c-110">Chame [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) várias vezes para obter dados de uma coluna de textos ou imagens.</span><span class="sxs-lookup"><span data-stu-id="9577c-110">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="9577c-111">Configure quaisquer colunas de imagem ou texto de dados em execução.</span><span class="sxs-lookup"><span data-stu-id="9577c-111">Set up any data-at-execution text or image columns.</span></span>  
  
5.  <span data-ttu-id="9577c-112">Chame [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) ou [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) para definir a posição do cursor, atualizar, atualizar, excluir ou Adicionar linha (s) no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="9577c-112">Call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) or [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) to set the cursor position, refresh, update, delete, or add row(s) within the rowset.</span></span>  
  
     <span data-ttu-id="9577c-113">Se as colunas de imagem ou texto de dados em execução forem usadas para uma operação de atualização ou adição, lide com elas.</span><span class="sxs-lookup"><span data-stu-id="9577c-113">If data-at-execution text or image columns are used for an update or add operation, handle them.</span></span>  
  
6.  <span data-ttu-id="9577c-114">Opcionalmente, execute uma instrução UPDATE ou DELETE posicionada, especificando o nome do cursor (disponível em [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md)) e usando um identificador de instrução diferente na mesma conexão.</span><span class="sxs-lookup"><span data-stu-id="9577c-114">Optionally, execute a positioned UPDATE or DELETE statement, specifying the cursor name (available from [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md)) and using a different statement handle on the same connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9577c-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9577c-115">See Also</span></span>  
 [<span data-ttu-id="9577c-116">Tópicos de instruções sobre o uso de cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="9577c-116">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
