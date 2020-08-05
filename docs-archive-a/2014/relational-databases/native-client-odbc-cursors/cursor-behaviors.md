---
title: Comportamentos de cursor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- version-based optimistic concurrency
- cursors [ODBC], cursor behaviors
- ODBC applications, cursors
- SQL_ATTR_CURSOR_SENSITIVITY option
- SQL_ATTR_CURSOR_SCROLLABLE option
- sensitivity behavior of cursor
- ODBC cursors, cursor behaviors
ms.assetid: 742ddcd2-232b-4aa1-9212-027df120ad35
author: rothja
ms.author: jroth
ms.openlocfilehash: 89c7c4e9a8dcffe03dd12f8013d5ed43810547f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573945"
---
# <a name="cursor-behaviors"></a><span data-ttu-id="cfa6a-102">Comportamentos de cursor</span><span class="sxs-lookup"><span data-stu-id="cfa6a-102">Cursor Behaviors</span></span>
  <span data-ttu-id="cfa6a-103">O ODBC dá suporte às opções ISO para especificar o comportamento de cursores por meio da definição de sua rolagem e sensibilidade.</span><span class="sxs-lookup"><span data-stu-id="cfa6a-103">ODBC supports the ISO options for specifying the behavior of cursors by specifying their scrollability and sensitivity.</span></span> <span data-ttu-id="cfa6a-104">Esses comportamentos são especificados definindo as opções SQL_ATTR_CURSOR_SCROLLABLE e SQL_ATTR_CURSOR_SENSITIVITY em uma chamada para [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="cfa6a-104">These behaviors are specified by setting the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY options on a call to [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="cfa6a-105">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client implementa essas opções solicitando cursores de servidor com as características a seguir.</span><span class="sxs-lookup"><span data-stu-id="cfa6a-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver implements these options by requesting server cursors with the following characteristics.</span></span>  
  
|<span data-ttu-id="cfa6a-106">Configurações do comportamento de cursor</span><span class="sxs-lookup"><span data-stu-id="cfa6a-106">Cursor behavior settings</span></span>|<span data-ttu-id="cfa6a-107">Características de cursor do servidor solicitadas</span><span class="sxs-lookup"><span data-stu-id="cfa6a-107">Server cursor characteristics requested</span></span>|  
|------------------------------|---------------------------------------------|  
|<span data-ttu-id="cfa6a-108">SQL_SCROLLABLE e SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="cfa6a-108">SQL_SCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="cfa6a-109">Cursor controlado por conjunto de chaves e simultaneidade otimista baseada em versão</span><span class="sxs-lookup"><span data-stu-id="cfa6a-109">Keyset-driven cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="cfa6a-110">SQL_SCROLLABLE e SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="cfa6a-110">SQL_SCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="cfa6a-111">Cursor estático e simultaneidade somente leitura</span><span class="sxs-lookup"><span data-stu-id="cfa6a-111">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="cfa6a-112">SQL_SCROLLABLE e SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="cfa6a-112">SQL_SCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="cfa6a-113">Cursor estático e simultaneidade somente leitura</span><span class="sxs-lookup"><span data-stu-id="cfa6a-113">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="cfa6a-114">SQL_NONSCROLLABLE e SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="cfa6a-114">SQL_NONSCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="cfa6a-115">Cursor de somente avanço e simultaneidade otimista baseada em versão</span><span class="sxs-lookup"><span data-stu-id="cfa6a-115">Forward-only cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="cfa6a-116">SQL_NONSCROLLABLE e SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="cfa6a-116">SQL_NONSCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="cfa6a-117">Conjunto de resultados padrão (somente avanço, somente leitura)</span><span class="sxs-lookup"><span data-stu-id="cfa6a-117">Default result set (forward-only, read-only)</span></span>|  
|<span data-ttu-id="cfa6a-118">SQL_NONSCROLLABLE e SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="cfa6a-118">SQL_NONSCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="cfa6a-119">Conjunto de resultados padrão (somente avanço, somente leitura)</span><span class="sxs-lookup"><span data-stu-id="cfa6a-119">Default result set (forward-only, read-only)</span></span>|  
  
 <span data-ttu-id="cfa6a-120">A simultaneidade otimista baseada em versão requer uma coluna **timestamp** na tabela subjacente.</span><span class="sxs-lookup"><span data-stu-id="cfa6a-120">Version-based optimistic concurrency requires a **timestamp** column in the underlying table.</span></span> <span data-ttu-id="cfa6a-121">Se o controle de simultaneidade otimista baseado em versão for solicitado em uma tabela que não tem uma coluna **timestamp** , o servidor usará a simultaneidade otimista com base em valores.</span><span class="sxs-lookup"><span data-stu-id="cfa6a-121">If version-based optimistic concurrency control is requested on a table that does not have a **timestamp** column, the server uses values-based optimistic concurrency.</span></span>  
  
## <a name="scrollability"></a><span data-ttu-id="cfa6a-122">Rolagem</span><span class="sxs-lookup"><span data-stu-id="cfa6a-122">Scrollability</span></span>  
 <span data-ttu-id="cfa6a-123">Quando SQL_ATTR_CURSOR_SCROLLABLE é definido como SQL_SCROLLABLE, o cursor dá suporte a todos os valores diferentes para o parâmetro *FetchOrientation* de [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="cfa6a-123">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_SCROLLABLE, the cursor supports all the different values for the *FetchOrientation* parameter of [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="cfa6a-124">Quando SQL_ATTR_CURSOR_SCROLLABLE é definido como SQL_NONSCROLLABLE, o cursor só dá suporte a um valor de *FetchOrientation* de SQL_FETCH_NEXT.</span><span class="sxs-lookup"><span data-stu-id="cfa6a-124">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_NONSCROLLABLE, the cursor only supports a *FetchOrientation* value of SQL_FETCH_NEXT.</span></span>  
  
## <a name="sensitivity"></a><span data-ttu-id="cfa6a-125">Sensibilidade</span><span class="sxs-lookup"><span data-stu-id="cfa6a-125">Sensitivity</span></span>  
 <span data-ttu-id="cfa6a-126">Quando SQL_ATTR_CURSOR_SENSITIVITY é definido como SQL_SENSITIVE, o cursor reflete as modificações de dados feitas pelo usuário atual ou confirmadas por outros usuários.</span><span class="sxs-lookup"><span data-stu-id="cfa6a-126">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_SENSITIVE, the cursor reflects data modifications made by the current user or committed by other users.</span></span> <span data-ttu-id="cfa6a-127">Quando SQL_ATTR_CURSOR_SENSITIVITY é definido como SQL_INSENSITIVE, o cursor não reflete as modificações de dados.</span><span class="sxs-lookup"><span data-stu-id="cfa6a-127">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_INSENSITIVE, the cursor does not reflect data modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa6a-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cfa6a-128">See Also</span></span>  
 [<span data-ttu-id="cfa6a-129">Usando cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="cfa6a-129">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
