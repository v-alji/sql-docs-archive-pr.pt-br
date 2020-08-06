---
title: Próxima posição de busca | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- OLE DB rowsets, fetching
- next fetch position
- rowsets [OLE DB], fetching
ms.assetid: 9ef74b3f-c9c0-492f-9b93-d65738a61abd
author: rothja
ms.author: jroth
ms.openlocfilehash: fcc771eef4acf603148bc4b4318e810b1bd72302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679329"
---
# <a name="next-fetch-position"></a><span data-ttu-id="db18d-102">Próxima posição de busca</span><span class="sxs-lookup"><span data-stu-id="db18d-102">Next Fetch Position</span></span>
  <span data-ttu-id="db18d-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo controla a próxima posição de busca para que uma sequência de chamadas para o método **GetNextRows** (sem ignorar, alterações de direção ou chamadas intermediárias para os métodos **FindNextRow**, **Seek**ou **RestartPosition** ) Leia todo o conjunto de linhas sem ignorar ou repetir nenhuma linha.</span><span class="sxs-lookup"><span data-stu-id="db18d-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider keeps track of the next fetch position so that a sequence of calls to the **GetNextRows** method (without skips, changes of direction, or intervening calls to the **FindNextRow**, **Seek**, or **RestartPosition** methods) reads the whole rowset without skipping or repeating any row.</span></span> <span data-ttu-id="db18d-104">A próxima posição de fetch é alterada chamando **IRowset::GetNextRows**, **IRowset::RestartPosition** ou **IRowsetIndex::Seek**, ou chamando **FindNextRow** com um valor de *pBookmark* nulo.</span><span class="sxs-lookup"><span data-stu-id="db18d-104">The next fetch position is changed either by calling **IRowset::GetNextRows**, **IRowset::RestartPosition**, or **IRowsetIndex::Seek**, or by calling **FindNextRow** with a null *pBookmark* value.</span></span> <span data-ttu-id="db18d-105">A chamada de **FindNextRow** com um valor *pBookmark* não nulo não afeta a próxima posição de fetch.</span><span class="sxs-lookup"><span data-stu-id="db18d-105">Calling **FindNextRow** with a nonnull *pBookmark* value does not affect the next fetch position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db18d-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db18d-106">See Also</span></span>  
 [<span data-ttu-id="db18d-107">Buscando linhas</span><span class="sxs-lookup"><span data-stu-id="db18d-107">Fetching Rows</span></span>](fetching-rows.md)  
  
  
