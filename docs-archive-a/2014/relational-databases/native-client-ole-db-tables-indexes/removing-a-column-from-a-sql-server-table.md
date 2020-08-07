---
title: Removendo uma coluna de uma tabela do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- removing columns
- DropColumn function
- SQL Server Native Client OLE DB provider, columns
ms.assetid: 210811b7-cbd6-421e-bc6e-df9482236768
author: rothja
ms.author: jroth
ms.openlocfilehash: 8f40c466910aae7e0d349cd4a65ab265282bc8eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575086"
---
# <a name="removing-a-column-from-a-sql-server-table"></a><span data-ttu-id="aea86-102">Removendo uma coluna de uma tabela do SQL Server</span><span class="sxs-lookup"><span data-stu-id="aea86-102">Removing a Column from a SQL Server Table</span></span>
  <span data-ttu-id="aea86-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo expõe a função **ITableDefinition::D ropcolumn** .</span><span class="sxs-lookup"><span data-stu-id="aea86-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::DropColumn** function.</span></span> <span data-ttu-id="aea86-104">Isso permite que os consumidores removam uma coluna de uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aea86-104">This allows consumers to remove a column from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="aea86-105">Os consumidores especificam o nome da tabela como uma cadeia de caracteres Unicode no membro *pwszName* da união *uName* no parâmetro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="aea86-105">Consumers specify the table name as a Unicode character string in the *pwszName*member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="aea86-106">O membro *eKind* de *pTableID* precisa ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="aea86-106">The *eKind*member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="aea86-107">O consumidor indica um nome de coluna no membro *pwszName* da união *uName* no parâmetro *pColumnID*.</span><span class="sxs-lookup"><span data-stu-id="aea86-107">The consumer indicates a column name in the *pwszName*member of the *uName* union in the *pColumnID* parameter.</span></span> <span data-ttu-id="aea86-108">O nome da coluna é uma cadeia de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="aea86-108">The column name is a Unicode character string.</span></span> <span data-ttu-id="aea86-109">O membro *eKind* de *pColumnID* precisa ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="aea86-109">The *eKind* member of *pColumnID* must be DBKIND_NAME.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aea86-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="aea86-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="aea86-111">Código</span><span class="sxs-lookup"><span data-stu-id="aea86-111">Code</span></span>  
  
```  
DBID TableID;  
DBID ColumnID;  
HRESULT hr;  
  
TableID.eKind = DBKIND_NAME;  
TableID.uName.pwszName = L"MyTableName";  
  
ColumnID.eKind = DBKIND_NAME;  
ColumnID.uName.pwszName = L"MyColumnName";  
  
hr = m_pITableDefinition->DropColumn(&TableID, &ColumnID);  
```  
  
## <a name="see-also"></a><span data-ttu-id="aea86-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aea86-112">See Also</span></span>  
 [<span data-ttu-id="aea86-113">Tabelas e índices</span><span class="sxs-lookup"><span data-stu-id="aea86-113">Tables and Indexes</span></span>](tables-and-indexes.md)  
  
  
