---
title: Descartar uma tabela do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- tables [OLE DB]
- deleting tables
- SQL Server Native Client OLE DB provider, tables
- removing tables
- dropping tables
ms.assetid: b6d6c4de-43c6-473e-92aa-34ffddd58cbe
author: rothja
ms.author: jroth
ms.openlocfilehash: 4d7bea98a3afcd0022f66117b6bde2d968a866b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575087"
---
# <a name="dropping-a-sql-server-table"></a><span data-ttu-id="35b57-102">Descartando uma tabela do SQL Server</span><span class="sxs-lookup"><span data-stu-id="35b57-102">Dropping a SQL Server Table</span></span>
  <span data-ttu-id="35b57-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo expõe a função **ITableDefinition::D roptable** .</span><span class="sxs-lookup"><span data-stu-id="35b57-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::DropTable** function.</span></span> <span data-ttu-id="35b57-104">Isso permite que os consumidores removam uma [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="35b57-104">This allows consumers to remove a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table from a database.</span></span>  
  
 <span data-ttu-id="35b57-105">Os consumidores especificam o nome da tabela como uma cadeia de caracteres Unicode no membro *pwszName* da união *uName* no parâmetro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="35b57-105">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="35b57-106">O membro *eKind* de *pTableID* precisa ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="35b57-106">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b57-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="35b57-107">See Also</span></span>  
 [<span data-ttu-id="35b57-108">Tabelas e índices</span><span class="sxs-lookup"><span data-stu-id="35b57-108">Tables and Indexes</span></span>](tables-and-indexes.md)  
  
  
