---
title: Atualizar dados em conjuntos de linhas | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- updating data [SQL Server]
- rowsets [OLE DB], updating data
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, updating data
- SQL Server Native Client OLE DB provider, data updates
- data updates [SQL Server], OLE DB
ms.assetid: 37769b1c-c480-419a-8c54-5cc420bf73db
author: rothja
ms.author: jroth
ms.openlocfilehash: 993cfb67d4e6b72eec7cc0537e9b47371e94af10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681633"
---
# <a name="updating-data-in-rowsets"></a><span data-ttu-id="78233-102">Atualizando dados em conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="78233-102">Updating Data in Rowsets</span></span>
  <span data-ttu-id="78233-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo atualiza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] os dados quando um consumidor atualiza um conjunto de linhas modificável que contém esses dados.</span><span class="sxs-lookup"><span data-stu-id="78233-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider updates [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data when a consumer updates a modifiable rowset that contains that data.</span></span> <span data-ttu-id="78233-104">Um conjunto de linhas modificável é criado quando o consumidor solicita suporte para a interface **IRowsetChange** ou **IRowsetUpdate**.</span><span class="sxs-lookup"><span data-stu-id="78233-104">A modifiable rowset is created when the consumer requests support for either the **IRowsetChange** or **IRowsetUpdate** interface.</span></span>  
  
 <span data-ttu-id="78233-105">Todos os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjuntos de linhas modificáveis do provedor de OLE DB de clientes nativos usam [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursores para dar suporte ao conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="78233-105">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider-modifiable rowsets use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors to support the rowset.</span></span> <span data-ttu-id="78233-106">A propriedade do conjunto de linhas DBPROP_LOCKMODE altera o comportamento de controle da simultaneidade do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em cursores e determina o comportamento da busca de linhas do conjunto de linhas e da geração de erros de integridade de dados nos conjuntos de linhas atualizáveis.</span><span class="sxs-lookup"><span data-stu-id="78233-106">The rowset property DBPROP_LOCKMODE alters [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concurrency control behavior in cursors and determines the behavior of rowset row fetching and data integrity error generation in updatable rowsets.</span></span>  
  
 <span data-ttu-id="78233-107">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo dá suporte à sincronização de linha antes ou depois de uma atualização.</span><span class="sxs-lookup"><span data-stu-id="78233-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports row synchronization before or after an update.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78233-108">IRowChange::SetColumns está disponível para definir os valores de uma ou mais colunas nomeadas de um objeto de linha.</span><span class="sxs-lookup"><span data-stu-id="78233-108">IRowChange::SetColumns is available to set the values of one or more named columns of a row object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78233-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="78233-109">In This Section</span></span>  
  
-   [<span data-ttu-id="78233-110">Atualizando dados em cursores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="78233-110">Updating Data in SQL Server Cursors</span></span>](updating-data-in-sql-server-cursors.md)  
  
-   [<span data-ttu-id="78233-111">Ressincronizando linhas</span><span class="sxs-lookup"><span data-stu-id="78233-111">Resynchronizing Rows</span></span>](updating-data-in-rowsets-resynchronizing-rows.md)  
  
## <a name="see-also"></a><span data-ttu-id="78233-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="78233-112">See Also</span></span>  
 [<span data-ttu-id="78233-113">Conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="78233-113">Rowsets</span></span>](rowsets.md)  
  
  
