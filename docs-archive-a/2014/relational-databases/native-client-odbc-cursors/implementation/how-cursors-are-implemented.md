---
title: Como os cursores são implementados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC cursors, about ODBC cursors
- ODBC applications, cursors
- cursors [ODBC], about ODBC cursors
ms.assetid: 2b1d7dd4-08a4-43fc-b3eb-70c183d0941f
author: rothja
ms.author: jroth
ms.openlocfilehash: 18995355b825d9cb1e62b4794429b5e98ef2b472
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572078"
---
# <a name="how-cursors-are-implemented"></a><span data-ttu-id="0a49b-102">Como os cursores são implementados</span><span class="sxs-lookup"><span data-stu-id="0a49b-102">How Cursors Are Implemented</span></span>
  <span data-ttu-id="0a49b-103">Os aplicativos ODBC controlam o comportamento de um cursor definindo um ou mais atributos de instrução antes de executar uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="0a49b-103">ODBC applications control the behavior of a cursor by setting one or more statement attributes before executing an SQL statement.</span></span> <span data-ttu-id="0a49b-104">ODBC tem dois modos diferentes de especificar as características de um cursor:</span><span class="sxs-lookup"><span data-stu-id="0a49b-104">ODBC has two different ways to specify the characteristics of a cursor:</span></span>  
  
-   <span data-ttu-id="0a49b-105">Tipo de cursor</span><span class="sxs-lookup"><span data-stu-id="0a49b-105">Cursor type</span></span>  
  
     <span data-ttu-id="0a49b-106">Os tipos de cursor são definidos usando o atributo SQL_ATTR_CURSOR_TYPE de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="0a49b-106">Cursor types are set using the SQL_ATTR_CURSOR_TYPE attribute of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="0a49b-107">Os tipos de cursor ODBC são de somente avanço, estático, controlado por conjunto de chaves, misto e dinâmico.</span><span class="sxs-lookup"><span data-stu-id="0a49b-107">The ODBC cursor types are forward-only, static, keyset-driven, mixed, and dynamic.</span></span> <span data-ttu-id="0a49b-108">Definir o tipo do cursor era o método original de especificação de cursores no ODBC.</span><span class="sxs-lookup"><span data-stu-id="0a49b-108">Setting the cursor type was the original method of specifying cursors in ODBC.</span></span>  
  
-   <span data-ttu-id="0a49b-109">Comportamento do cursor</span><span class="sxs-lookup"><span data-stu-id="0a49b-109">Cursor behavior</span></span>  
  
     <span data-ttu-id="0a49b-110">O comportamento do cursor é definido usando os atributos SQL_ATTR_CURSOR_SCROLLABLE e SQL_ATTR_CURSOR_SENSITIVITY de **SQLSetStmtAttr**.</span><span class="sxs-lookup"><span data-stu-id="0a49b-110">Cursor behavior is set using the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY attributes of **SQLSetStmtAttr**.</span></span> <span data-ttu-id="0a49b-111">Esses atributos são modelados nas palavras-chave SCROLL e SENSITIVE definidas para a instrução DECLARE CURSOR com base nos padrões ISO.</span><span class="sxs-lookup"><span data-stu-id="0a49b-111">These attributes are modeled on the SCROLL and SENSITIVE keywords defined for the DECLARE CURSOR statement in ISO standards.</span></span> <span data-ttu-id="0a49b-112">Essas duas opções ISO foram introduzidas no ODBC versão 3.0.</span><span class="sxs-lookup"><span data-stu-id="0a49b-112">These two ISO options were introduced in ODBC version 3.0.</span></span>  
  
 <span data-ttu-id="0a49b-113">As características de um cursor ODBC devem ser especificadas com um desses dois métodos, sendo preferível usar o primeiro, ou seja, tipo do cursor ODBC.</span><span class="sxs-lookup"><span data-stu-id="0a49b-113">The characteristics of an ODBC cursor should be specified using either one or the other of these two methods, with the preference being to use the ODBC cursor types.</span></span>  
  
 <span data-ttu-id="0a49b-114">Além de definir o tipo de um cursor, os aplicativos ODBC também definem outras opções, tais como o número de linhas retornadas em cada extração, opções de simultaneidade e níveis de isolamento da transação.</span><span class="sxs-lookup"><span data-stu-id="0a49b-114">In addition to setting the type of a cursor, ODBC applications also set other options, such as the number of rows returned on each fetch, concurrency options, and transaction isolation levels.</span></span> <span data-ttu-id="0a49b-115">Essas opções podem ser definidas para cursores do tipo ODBC (de somente avanço, estático, controlado por conjunto de chaves, misto e dinâmico) ou cursores ISO (rolagem e sensibilidade).</span><span class="sxs-lookup"><span data-stu-id="0a49b-115">These options can be set for either ODBC-style cursors (forward-only, static, keyset-driven, mixed, and dynamic) or ISO style cursors (scrollability and sensitivity).</span></span>  
  
 <span data-ttu-id="0a49b-116">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client dá suporte a várias maneiras de implementar fisicamente os vários tipos de cursores.</span><span class="sxs-lookup"><span data-stu-id="0a49b-116">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports several ways to physically implement the various types of cursors.</span></span> <span data-ttu-id="0a49b-117">O driver implementa alguns tipos de cursor usando um conjunto de resultados padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; ele implementa outros como cursores de servidor ou usando a biblioteca de cursores ODBC.</span><span class="sxs-lookup"><span data-stu-id="0a49b-117">The driver implements some types of cursors using a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set; it implements others as server cursors or by using the ODBC Cursor Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a49b-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0a49b-118">In This Section</span></span>  
  
-   [<span data-ttu-id="0a49b-119">Usando conjuntos de resultados padrão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="0a49b-119">Using SQL Server Default Result Sets</span></span>](using-sql-server-default-result-sets.md)  
  
-   [<span data-ttu-id="0a49b-120">Usando cursores de servidor</span><span class="sxs-lookup"><span data-stu-id="0a49b-120">Using Server Cursors</span></span>](using-server-cursors.md)  
  
-   [<span data-ttu-id="0a49b-121">Biblioteca de cursores ODBC</span><span class="sxs-lookup"><span data-stu-id="0a49b-121">ODBC Cursor Library</span></span>](odbc-cursor-library.md)  
  
## <a name="see-also"></a><span data-ttu-id="0a49b-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a49b-122">See Also</span></span>  
 [<span data-ttu-id="0a49b-123">Usando cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="0a49b-123">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  
