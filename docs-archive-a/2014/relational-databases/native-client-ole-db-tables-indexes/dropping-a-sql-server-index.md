---
title: Descartar um índice do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- removing indexes
- deleting indexes
- DropIndex function
- dropping indexes
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: add3ba14-10b1-4723-b7c0-3e83689e9fdd
author: rothja
ms.author: jroth
ms.openlocfilehash: 1267cc92645ff8b28757ad2d266e58917fcb4b28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575088"
---
# <a name="dropping-a-sql-server-index"></a><span data-ttu-id="05d74-102">Descartando um índice do SQL Server</span><span class="sxs-lookup"><span data-stu-id="05d74-102">Dropping a SQL Server Index</span></span>
  <span data-ttu-id="05d74-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo expõe a função **IIndexDefinition::D ropindex** .</span><span class="sxs-lookup"><span data-stu-id="05d74-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::DropIndex** function.</span></span> <span data-ttu-id="05d74-104">Isso permite que os consumidores removam um índice de uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05d74-104">This allows consumers to remove an index from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="05d74-105">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo expõe algumas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] restrições PRIMARY KEY e Unique como índices.</span><span class="sxs-lookup"><span data-stu-id="05d74-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PRIMARY KEY and UNIQUE constraints as indexes.</span></span> <span data-ttu-id="05d74-106">O proprietário da tabela, o proprietário do banco de dados e alguns membros de função administrativa podem modificar uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], removendo uma restrição.</span><span class="sxs-lookup"><span data-stu-id="05d74-106">The table owner, database owner, and some administrative role members can modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, dropping a constraint.</span></span> <span data-ttu-id="05d74-107">Por padrão, somente o proprietário da tabela pode descartar um índice existente.</span><span class="sxs-lookup"><span data-stu-id="05d74-107">By default, only the table owner can drop an existing index.</span></span> <span data-ttu-id="05d74-108">Portanto, o êxito ou a falha de **DropIndex** depende não só dos direitos de acesso do usuário do aplicativo, como também do tipo de índice indicado.</span><span class="sxs-lookup"><span data-stu-id="05d74-108">Therefore, **DropIndex** success or failure depends not only on the application user's access rights but also on the type of index indicated.</span></span>  
  
 <span data-ttu-id="05d74-109">Os consumidores especificam o nome da tabela como uma cadeia de caracteres Unicode no membro *pwszName* da união *uName* no parâmetro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="05d74-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="05d74-110">O membro *eKind* de *pTableID* precisa ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="05d74-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="05d74-111">Os consumidores especificam o nome do índice como uma cadeia de caracteres Unicode no membro *pwszName* da união *uName* no parâmetro *pIndexID*.</span><span class="sxs-lookup"><span data-stu-id="05d74-111">Consumers specify the index name as a Unicode character string in the *pwszName* member of the *uName* union in the *pIndexID* parameter.</span></span> <span data-ttu-id="05d74-112">O membro *eKind* de *pIndexID* precisa ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="05d74-112">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span> <span data-ttu-id="05d74-113">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não dá suporte ao recurso de OLE DB de remover todos os índices em uma tabela quando *pIndexID* é nulo.</span><span class="sxs-lookup"><span data-stu-id="05d74-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support the OLE DB feature of dropping all indexes on a table when *pIndexID* is null.</span></span> <span data-ttu-id="05d74-114">Se *pIndexID* for nulo, E_INVALIDARG será retornado.</span><span class="sxs-lookup"><span data-stu-id="05d74-114">If *pIndexID* is null, E_INVALIDARG is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d74-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05d74-115">See Also</span></span>  
 <span data-ttu-id="05d74-116">[Tabelas e índices](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="05d74-116">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 <span data-ttu-id="05d74-117">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="05d74-117">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="05d74-118">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="05d74-118">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
