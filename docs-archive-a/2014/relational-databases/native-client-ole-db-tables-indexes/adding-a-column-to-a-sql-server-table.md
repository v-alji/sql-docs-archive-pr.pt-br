---
title: Adicionar uma coluna a uma tabela do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- AddColumn function
- SQL Server Native Client OLE DB provider, columns
- adding columns
ms.assetid: 22bae18a-bc9d-4617-8660-ed8b17a468d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 97aa2656ccde662a34e1dd80fd662b22f601d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684687"
---
# <a name="adding-a-column-to-a-sql-server-table"></a><span data-ttu-id="e49d9-102">Adicionando uma coluna a uma tabela do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e49d9-102">Adding a Column to a SQL Server Table</span></span>
  <span data-ttu-id="e49d9-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo expõe a função **ITableDefinition:: AddColumn** .</span><span class="sxs-lookup"><span data-stu-id="e49d9-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::AddColumn** function.</span></span> <span data-ttu-id="e49d9-104">Isso permite que os consumidores adicionem uma coluna a uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e49d9-104">This allows consumers to add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="e49d9-105">Quando você adiciona uma coluna a uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor do provedor de OLE DB de cliente nativo é restrito da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e49d9-105">When you add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is constrained as follows:</span></span>  
  
-   <span data-ttu-id="e49d9-106">Caso DBPROP_COL_AUTOINCREMENT seja VARIANT_TRUE, DBPROP_COL_NULLABLE deve ser VARIANT_FALSE.</span><span class="sxs-lookup"><span data-stu-id="e49d9-106">If DBPROP_COL_AUTOINCREMENT is VARIANT_TRUE, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="e49d9-107">Caso a coluna seja definida usando o tipo de dados  **timestamp** do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], DBPROP_COL_NULLABLE precisará ser VARIANT_FALSE.</span><span class="sxs-lookup"><span data-stu-id="e49d9-107">If the column is defined by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **timestamp** data type, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="e49d9-108">Para qualquer outra definição de coluna, DBPROP_COL_NULLABLE deve ser VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="e49d9-108">For any other column definition, DBPROP_COL_NULLABLE must be VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="e49d9-109">Os consumidores especificam o nome da tabela como uma cadeia de caracteres Unicode no membro *pwszName* da união *uName* no parâmetro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="e49d9-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="e49d9-110">O membro *eKind* de *pTableID* precisa ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="e49d9-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="e49d9-111">O nome da nova coluna é especificado como uma cadeia de caracteres Unicode no membro *pwszName* da união *uName* no membro *dbcid* do parâmetro *pColumnDesc* de DBCOLUMNDESC.</span><span class="sxs-lookup"><span data-stu-id="e49d9-111">The new column name is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *dbcid* member of the DBCOLUMNDESC parameter *pColumnDesc*.</span></span> <span data-ttu-id="e49d9-112">O membro *eKind* precisa ser DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="e49d9-112">The *eKind* member must be DBKIND_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e49d9-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e49d9-113">See Also</span></span>  
 <span data-ttu-id="e49d9-114">[Tabelas e índices](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="e49d9-114">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 [<span data-ttu-id="e49d9-115">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e49d9-115">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
