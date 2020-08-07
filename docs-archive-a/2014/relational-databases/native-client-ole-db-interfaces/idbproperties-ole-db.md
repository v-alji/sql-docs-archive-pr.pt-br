---
title: IDBProperties (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 2e5a4fd8-5164-495a-9986-3477aef8d8a5
author: rothja
ms.author: jroth
ms.openlocfilehash: f42ab47de2471fc413e4c6acf0d6c61cb2b6d77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582433"
---
# <a name="idbproperties-ole-db"></a><span data-ttu-id="7e18a-102">IDBProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7e18a-102">IDBProperties (OLE DB)</span></span>
  <span data-ttu-id="7e18a-103">A especificação OLE DB padrão permite que os provedores especifiquem VT_EMPTY para `DBPROPINFO::vValues`.</span><span class="sxs-lookup"><span data-stu-id="7e18a-103">The OLE DB standard specification allows providers to specify VT_EMPTY for `DBPROPINFO::vValues`.</span></span> <span data-ttu-id="7e18a-104">No entanto, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB sempre retorna VT_EMPTY quando você chama `IDBProperties::GetPropertyInfo` with `DBPROPSET_ROWSETALL` para recuperar as propriedades do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="7e18a-104">However, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB always returns VT_EMPTY when you call `IDBProperties::GetPropertyInfo` with `DBPROPSET_ROWSETALL` to retrieve rowset properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e18a-105">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e18a-105">See Also</span></span>  
 [<span data-ttu-id="7e18a-106">Interfaces &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="7e18a-106">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
