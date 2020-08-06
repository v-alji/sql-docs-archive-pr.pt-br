---
title: Linhas de indicador no ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- ODBC cursors, scrolling rows
- bookmarks [ODBC]
ms.assetid: 9cfcd243-c9d4-4c2a-abc4-399dbabe5f6b
author: rothja
ms.author: jroth
ms.openlocfilehash: def05f478c16dcbcdc91771925a11b0b91da2e9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684728"
---
# <a name="bookmarking-rows-in-odbc"></a><span data-ttu-id="0ca82-102">Indicando linhas em ODBC</span><span class="sxs-lookup"><span data-stu-id="0ca82-102">Bookmarking Rows in ODBC</span></span>
  <span data-ttu-id="0ca82-103">Um indicador é um valor usado para identificar uma linha de dados.</span><span class="sxs-lookup"><span data-stu-id="0ca82-103">A bookmark is a value used to identify a row of data.</span></span> <span data-ttu-id="0ca82-104">O significado do valor de indicador só é conhecido para o driver ou a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="0ca82-104">The meaning of the bookmark value is known only to the driver or data source.</span></span> <span data-ttu-id="0ca82-105">Por exemplo, ele poderá ser tão simples quanto um número de linha ou tão complexo quanto um endereço de disco.</span><span class="sxs-lookup"><span data-stu-id="0ca82-105">For example, it might be as simple as a row number or as complex as a disk address.</span></span> <span data-ttu-id="0ca82-106">Em ODBC, o aplicativo solicita um indicador para uma linha específica, armazena-o e transmite-o novamente ao cursor para que retorne à linha.</span><span class="sxs-lookup"><span data-stu-id="0ca82-106">In ODBC, the application requests a bookmark for a particular row, stores it, and passes it back to the cursor to return to the row.</span></span>  
  
 <span data-ttu-id="0ca82-107">Ao buscar linhas com [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md), um aplicativo pode usar um indicador como base para selecionar a linha inicial.</span><span class="sxs-lookup"><span data-stu-id="0ca82-107">When fetching rows with [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md), an application can use a bookmark as a basis for selecting the starting row.</span></span> <span data-ttu-id="0ca82-108">Esta é uma forma de endereçamento absoluto porque não depende da posição atual do cursor.</span><span class="sxs-lookup"><span data-stu-id="0ca82-108">This is a form of absolute addressing because it does not depend on the current cursor position.</span></span> <span data-ttu-id="0ca82-109">Para rolar para uma linha com indicador, o aplicativo chama **SQLFetchScroll** com um *FetchOrientation* de SQL_FETCH_BOOKMARK.</span><span class="sxs-lookup"><span data-stu-id="0ca82-109">To scroll to a bookmarked row, the application calls **SQLFetchScroll** with a *FetchOrientation* of SQL_FETCH_BOOKMARK.</span></span> <span data-ttu-id="0ca82-110">Esta operação usa o indicador apontado pelo atributo da opção SQL_ATTR_FETCH_BOOKMARK_PTR.</span><span class="sxs-lookup"><span data-stu-id="0ca82-110">This operation uses the bookmark pointed to by the SQL_ATTR_FETCH_BOOKMARK_PTR option attribute.</span></span> <span data-ttu-id="0ca82-111">Retorna o conjunto de linhas que inicia com a linha identificada por esse indicador.</span><span class="sxs-lookup"><span data-stu-id="0ca82-111">It returns the rowset starting with the row identified by that bookmark.</span></span> <span data-ttu-id="0ca82-112">Um aplicativo pode especificar um deslocamento para essa operação no argumento *FetchOffset* da chamada para **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="0ca82-112">An application can specify an offset for this operation in the *FetchOffset* argument of the call to **SQLFetchScroll**.</span></span> <span data-ttu-id="0ca82-113">Quando um deslocamento é especificado, a primeira linha do conjunto de linhas retornado é determinada adicionando o número no argumento FetchOffset ao número da linha identificada pelo indicador.</span><span class="sxs-lookup"><span data-stu-id="0ca82-113">When an offset is specified, the first row of the returned rowset is determined by adding the number in the FetchOffset argument to the number of the row identified by the bookmark.</span></span> <span data-ttu-id="0ca82-114">O driver ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client apenas dá suporte a indicadores em cursores estáticos e do conjunto de chaves.</span><span class="sxs-lookup"><span data-stu-id="0ca82-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver only supports bookmarks on static and keyset cursors.</span></span> <span data-ttu-id="0ca82-115">Se um cursor dinâmico for solicitado quando indicadores forem definidos, um cursor do conjunto de chaves será aberto no lugar.</span><span class="sxs-lookup"><span data-stu-id="0ca82-115">If a dynamic cursor is requested when bookmarks are set on, a keyset cursor is opened instead.</span></span>  
  
 <span data-ttu-id="0ca82-116">Os indicadores também podem ser usados com a função **SQLBulkOperations** para executar operações em um conjunto de linhas, começando no indicador.</span><span class="sxs-lookup"><span data-stu-id="0ca82-116">Bookmarks can also be used with the **SQLBulkOperations** function to perform operations on a set of rows starting at the bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca82-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ca82-117">See Also</span></span>  
 [<span data-ttu-id="0ca82-118">Rolando e buscando linhas</span><span class="sxs-lookup"><span data-stu-id="0ca82-118">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
  
