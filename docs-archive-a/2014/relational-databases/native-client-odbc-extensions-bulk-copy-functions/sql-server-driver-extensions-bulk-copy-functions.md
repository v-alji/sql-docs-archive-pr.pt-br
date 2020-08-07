---
title: Funções de cópia em massa | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], functions
- ODBC, bulk copy operations
- functions [ODBC]
ms.assetid: 6526b892-1d58-4f55-8335-f09887f6ea02
author: rothja
ms.author: jroth
ms.openlocfilehash: 02dba8cf4d510d2ec5f20e600302bb692c749f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575102"
---
# <a name="bulk-copy-functions"></a><span data-ttu-id="45df8-102">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="45df8-102">Bulk Copy Functions</span></span>
  <span data-ttu-id="45df8-103">A extensão API de cópia em massa específica do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client permite que aplicativos cliente adicionem ou extraiam linhas de dados rapidamente de uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45df8-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific bulk-copy API extension of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver allows client applications to rapidly add data rows to, or extract data rows from, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="45df8-104">Ao usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, você pode referenciar as BCP (funções de cópia em massa) em SQLNCLI11.LIB e em SQLNCLI.H.</span><span class="sxs-lookup"><span data-stu-id="45df8-104">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, you can reference the bulk copy functions (BCP) in SQLNCLI11.LIB and SQLNCLI.H.</span></span>  
  
 <span data-ttu-id="45df8-105">Um aplicativo que usa chamadas de função de API BCP deve ser vinculado com a biblioteca (.lib) que é enviada com o driver (.dll) usado pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="45df8-105">An application that uses BCP API function calls should link with the library (.lib) that shipped with the driver (.dll) used by the application.</span></span> <span data-ttu-id="45df8-106">Um aplicativo BCP não deve vincular com mais de uma biblioteca de driver.</span><span class="sxs-lookup"><span data-stu-id="45df8-106">A BCP application should not link with more than one driver library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45df8-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="45df8-107">In This Section</span></span>  
  
-   [<span data-ttu-id="45df8-108">bcp_batch</span><span class="sxs-lookup"><span data-stu-id="45df8-108">bcp_batch</span></span>](bcp-batch.md)  
  
-   [<span data-ttu-id="45df8-109">bcp_bind</span><span class="sxs-lookup"><span data-stu-id="45df8-109">bcp_bind</span></span>](bcp-bind.md)  
  
-   [<span data-ttu-id="45df8-110">bcp_colfmt</span><span class="sxs-lookup"><span data-stu-id="45df8-110">bcp_colfmt</span></span>](bcp-colfmt.md)  
  
-   [<span data-ttu-id="45df8-111">bcp_collen</span><span class="sxs-lookup"><span data-stu-id="45df8-111">bcp_collen</span></span>](bcp-collen.md)  
  
-   [<span data-ttu-id="45df8-112">bcp_colptr</span><span class="sxs-lookup"><span data-stu-id="45df8-112">bcp_colptr</span></span>](bcp-colptr.md)  
  
-   [<span data-ttu-id="45df8-113">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="45df8-113">bcp_columns</span></span>](bcp-columns.md)  
  
-   [<span data-ttu-id="45df8-114">bcp_control</span><span class="sxs-lookup"><span data-stu-id="45df8-114">bcp_control</span></span>](bcp-control.md)  
  
-   [<span data-ttu-id="45df8-115">bcp_done</span><span class="sxs-lookup"><span data-stu-id="45df8-115">bcp_done</span></span>](bcp-done.md)  
  
-   [<span data-ttu-id="45df8-116">bcp_exec</span><span class="sxs-lookup"><span data-stu-id="45df8-116">bcp_exec</span></span>](bcp-exec.md)  
  
-   [<span data-ttu-id="45df8-117">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="45df8-117">bcp_getcolfmt</span></span>](bcp-getcolfmt.md)  
  
-   [<span data-ttu-id="45df8-118">bcp_gettypename</span><span class="sxs-lookup"><span data-stu-id="45df8-118">bcp_gettypename</span></span>](bcp-gettypename.md)  
  
-   [<span data-ttu-id="45df8-119">bcp_init</span><span class="sxs-lookup"><span data-stu-id="45df8-119">bcp_init</span></span>](bcp-init.md)  
  
-   [<span data-ttu-id="45df8-120">bcp_moretext</span><span class="sxs-lookup"><span data-stu-id="45df8-120">bcp_moretext</span></span>](bcp-moretext.md)  
  
-   [<span data-ttu-id="45df8-121">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="45df8-121">bcp_readfmt</span></span>](bcp-readfmt.md)  
  
-   [<span data-ttu-id="45df8-122">bcp_sendrow</span><span class="sxs-lookup"><span data-stu-id="45df8-122">bcp_sendrow</span></span>](bcp-sendrow.md)  
  
-   [<span data-ttu-id="45df8-123">bcp_setbulkmode</span><span class="sxs-lookup"><span data-stu-id="45df8-123">bcp_setbulkmode</span></span>](bcp-setbulkmode.md)  
  
-   [<span data-ttu-id="45df8-124">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="45df8-124">bcp_setcolfmt</span></span>](bcp-setcolfmt.md)  
  
-   [<span data-ttu-id="45df8-125">bcp_writefmt</span><span class="sxs-lookup"><span data-stu-id="45df8-125">bcp_writefmt</span></span>](bcp-writefmt.md)  
  
## <a name="see-also"></a><span data-ttu-id="45df8-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="45df8-126">See Also</span></span>  
 <span data-ttu-id="45df8-127">[Extensões de driver de SQL Server](../../database-engine/dev-guide/sql-server-driver-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="45df8-127">[SQL Server Driver Extensions](../../database-engine/dev-guide/sql-server-driver-extensions.md) </span></span>  
 [<span data-ttu-id="45df8-128">Executando operações de cópia em massa &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="45df8-128">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md)  
  
  
