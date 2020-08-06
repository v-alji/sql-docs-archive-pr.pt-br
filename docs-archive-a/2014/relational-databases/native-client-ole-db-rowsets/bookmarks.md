---
title: Indicadores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bookmarks [OLE DB]
- SQL Server Native Client OLE DB provider, bookmarks
- rowsets [OLE DB], bookmarks
- OLE DB rowsets, bookmarks
ms.assetid: 7d9076f2-bf9c-452e-b816-70371a0c1644
author: rothja
ms.author: jroth
ms.openlocfilehash: be8e5486e5a442ddafa133a9cbd3f408d30a50d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684172"
---
# <a name="bookmarks"></a><span data-ttu-id="7e7fe-102">Indicadores</span><span class="sxs-lookup"><span data-stu-id="7e7fe-102">Bookmarks</span></span>
  <span data-ttu-id="7e7fe-103">Os indicadores permitem que os consumidores voltem rapidamente para uma linha.</span><span class="sxs-lookup"><span data-stu-id="7e7fe-103">Bookmarks let consumers quickly return to a row.</span></span> <span data-ttu-id="7e7fe-104">Com os indicadores, os consumidores podem acessar linhas aleatoriamente com base no valor do indicador.</span><span class="sxs-lookup"><span data-stu-id="7e7fe-104">With bookmarks, consumers can access rows randomly based on the bookmark value.</span></span> <span data-ttu-id="7e7fe-105">A coluna do indicador é a coluna 0 no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="7e7fe-105">The bookmark column is column 0 in the rowset.</span></span> <span data-ttu-id="7e7fe-106">O consumidor define o valor de campo dwFrag da estrutura associada como DBCOLUMNSINFO_ISBOOKMARK para indicar que a coluna é usada como um indicador.</span><span class="sxs-lookup"><span data-stu-id="7e7fe-106">The consumer sets the dwFlag field value of the binding structure to DBCOLUMNSINFO_ISBOOKMARK to indicate that the column is used as a bookmark.</span></span> <span data-ttu-id="7e7fe-107">O consumidor também define a propriedade DBPROP_BOOKMARKS do conjunto de linhas como VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="7e7fe-107">The consumer also sets the rowset property DBPROP_BOOKMARKS to VARIANT_TRUE.</span></span> <span data-ttu-id="7e7fe-108">Isso permite que a coluna 0 esteja presente no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="7e7fe-108">This lets column 0 be present in the rowset.</span></span> <span data-ttu-id="7e7fe-109">Em seguida, o método **IRowsetLocate::GetRowsAt** é usado para buscar linhas, começando com a linha especificada como um deslocamento de um indicador.</span><span class="sxs-lookup"><span data-stu-id="7e7fe-109">The **IRowsetLocate::GetRowsAt** method is then used to fetch rows, starting with the row specified as an offset from a bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e7fe-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e7fe-110">See Also</span></span>  
 [<span data-ttu-id="7e7fe-111">Conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="7e7fe-111">Rowsets</span></span>](rowsets.md)  
  
  
