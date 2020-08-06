---
title: Ressincronizar linhas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- synchronization [OLE DB]
- IRowsetResynch interface
- resynchronizing rows
- data updates [SQL Server], OLE DB
ms.assetid: d2d30505-a878-4aa9-b821-53d8118a45a5
author: rothja
ms.author: jroth
ms.openlocfilehash: 47c628ae583f3e635f422d5146f64508372a1114
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571376"
---
# <a name="resynchronizing-rows"></a><span data-ttu-id="a6285-102">Ressincronizando linhas</span><span class="sxs-lookup"><span data-stu-id="a6285-102">Resynchronizing Rows</span></span>
  <span data-ttu-id="a6285-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo dá suporte a **IRowsetResynch** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] somente em conjuntos de linhas com suporte para o cursor.</span><span class="sxs-lookup"><span data-stu-id="a6285-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IRowsetResynch** on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursor-supported rowsets only.</span></span> <span data-ttu-id="a6285-104">**IRowsetResynch** não está disponível sob demanda.</span><span class="sxs-lookup"><span data-stu-id="a6285-104">**IRowsetResynch** is not available on demand.</span></span> <span data-ttu-id="a6285-105">O consumidor deve solicitar a interface antes de abrir o conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="a6285-105">The consumer must request the interface before opening the rowset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6285-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a6285-106">See Also</span></span>  
 [<span data-ttu-id="a6285-107">Atualizando dados em conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="a6285-107">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
  
