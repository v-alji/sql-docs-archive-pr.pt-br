---
title: Usar IRow::GetColumns | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- IRow interface
- single row fetching [SQL Server Native Client]
- OLE DB rowsets, fetching
- rowsets [OLE DB], fetching
- GetColumns method
ms.assetid: 1f5d2e03-e6fe-4ea1-b71d-55d02b5d59ae
author: rothja
ms.author: jroth
ms.openlocfilehash: f323dda790946565bc0dbd63c9e1f9d17ac7494b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571371"
---
# <a name="using-irowgetcolumns"></a><span data-ttu-id="7d01c-102">Usando IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="7d01c-102">Using IRow::GetColumns</span></span>
  <span data-ttu-id="7d01c-103">A implementação de **IRow** permite o acesso sequencial somente de encaminhamento às colunas.</span><span class="sxs-lookup"><span data-stu-id="7d01c-103">The **IRow** implementation allows forward-only sequential access to the columns.</span></span> <span data-ttu-id="7d01c-104">Acesse todas as colunas da linha com uma única chamada a **IRow::GetColumns** ou chame **IRow::GetColumns** várias vezes sempre que você acessar várias colunas na linha.</span><span class="sxs-lookup"><span data-stu-id="7d01c-104">You can either access all the columns in the row with a single call to **IRow::GetColumns** or call **IRow::GetColumns** multiple times every time that you access several columns in the row.</span></span>  
  
 <span data-ttu-id="7d01c-105">As várias chamadas a **IRow::GetColumns** não devem se sobrepor.</span><span class="sxs-lookup"><span data-stu-id="7d01c-105">The multiple calls to **IRow::GetColumns** should not overlap.</span></span> <span data-ttu-id="7d01c-106">Por exemplo, se a primeira chamada a **IRow::GetColumns** recupera as colunas 1, 2 e 3, a segunda chamada a **IRow::GetColumns** deve chamar as colunas 4, 5 e 6.</span><span class="sxs-lookup"><span data-stu-id="7d01c-106">For example, if the first call to **IRow::GetColumns** retrieves columns 1, 2, and 3, the second call to **IRow::GetColumns** should call for columns 4, 5, and 6.</span></span> <span data-ttu-id="7d01c-107">Caso as chamadas posteriores a **IRow::GetColumns** se sobreponham, um sinalizador de status (campo dwstatus em DBCOLUMNACCESS) será definido como DBSTATUS_E_UNAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7d01c-107">If later calls to **IRow::GetColumns** overlap, the status flag (dwstatus field in DBCOLUMNACCESS) is set to DBSTATUS_E_UNAVAILABLE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d01c-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7d01c-108">See Also</span></span>  
 [<span data-ttu-id="7d01c-109">Buscando uma única linha com IRow</span><span class="sxs-lookup"><span data-stu-id="7d01c-109">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
  
