---
title: Conjuntos de linhas de esquema alterados para parâmetros com valor de tabela do OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- schema rowsets [OLE DB]
- table-valued parameters (OLE DB), schema rowsets changed for (OLE DB)
ms.assetid: 581e3ead-53db-44da-8718-f3fc4b5108f1
author: rothja
ms.author: jroth
ms.openlocfilehash: e09d5127f332c8b6cc948be3eeb74e600bb856f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684686"
---
# <a name="schema-rowsets-changed-for-ole-db-table-valued-parameters"></a><span data-ttu-id="6447a-102">Conjuntos de linhas de esquema alterados para parâmetros com valor de tabela de OLE DB</span><span class="sxs-lookup"><span data-stu-id="6447a-102">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>
  <span data-ttu-id="6447a-103">A seguir, são mostrados os conjuntos de linhas de esquema que foram alterados ou adicionados para dar suporte a parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="6447a-103">The following are the schema rowsets that have been changed or added to support table-valued parameters.</span></span>  
  
|<span data-ttu-id="6447a-104">Conjunto de linhas de esquema</span><span class="sxs-lookup"><span data-stu-id="6447a-104">Schema rowset</span></span>|<span data-ttu-id="6447a-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="6447a-105">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="6447a-106">DBSCHEMA_PROCEDURE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6447a-106">DBSCHEMA_PROCEDURE_PARAMETERS</span></span>|<span data-ttu-id="6447a-107">Foram adicionadas duas novas colunas ao final do conjunto de linhas denominado SS_TYPE_CATALOG_NAME e SS_TYPE_SCHEMANAME.</span><span class="sxs-lookup"><span data-stu-id="6447a-107">Two new columns were added at the end of the rowset named SS_TYPE_CATALOG_NAME and SS_TYPE_SCHEMANAME.</span></span> <span data-ttu-id="6447a-108">Essas colunas poderiam ser reutilizadas para tipos futuros.</span><span class="sxs-lookup"><span data-stu-id="6447a-108">These columns could be re-used for future types.</span></span> <span data-ttu-id="6447a-109">As colunas TYPE_NAME e LOCAL_TYPE_NAME conterão o nome do tipo TABLE do parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="6447a-109">The TYPE_NAME and LOCAL_TYPE_NAME columns will contain the name of the table-valued parameter TABLE type.</span></span> <span data-ttu-id="6447a-110">A coluna DATA_TYPE terá o valor de DBTYPE_TABLE = 143 para parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="6447a-110">The DATA_TYPE column will have value DBTYPE_TABLE = 143 for table-valued parameters.</span></span>|  
|<span data-ttu-id="6447a-111">DBSCHEMA_TABLE_TYPES</span><span class="sxs-lookup"><span data-stu-id="6447a-111">DBSCHEMA_TABLE_TYPES</span></span>|<span data-ttu-id="6447a-112">Este conjunto de linhas foi adicionado para dar suporte a parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="6447a-112">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="6447a-113">Ele é idêntico ao DBSCHEMA_TABLES, a não ser pelo fato de retornar metadados apenas para tipos de tabela, em vez de tabelas, exibições ou sinônimos.</span><span class="sxs-lookup"><span data-stu-id="6447a-113">It is identical to DBSCHEMA_TABLES, except that it returns metadata only for table types, rather than for tables, views, or synonyms.</span></span> <span data-ttu-id="6447a-114">A coluna TABLE_TYPE terá o valor 'TABLE TYPE'.</span><span class="sxs-lookup"><span data-stu-id="6447a-114">The TABLE_TYPE column will have the value 'TABLE TYPE'.</span></span>|  
|<span data-ttu-id="6447a-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="6447a-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span></span>|<span data-ttu-id="6447a-116">Este conjunto de linhas foi adicionado para dar suporte a parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="6447a-116">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="6447a-117">Ele é idêntico ao DBSCHEMA_PRIMARY_KEYS, a não ser pelo fato de retornar metadados de chaves primárias apenas para tipos de tabela, em vez de tabelas.</span><span class="sxs-lookup"><span data-stu-id="6447a-117">It is identical to DBSCHEMA_PRIMARY_KEYS, except that it returns primary keys metadata only for table types, rather than for tables.</span></span>|  
|<span data-ttu-id="6447a-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="6447a-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span></span>|<span data-ttu-id="6447a-119">Este conjunto de linhas foi adicionado para dar suporte a parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="6447a-119">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="6447a-120">Ele é idêntico ao DBSCHEMA_COLUMNS, a não ser pelo fato de retornar metadados de coluna apenas para tipos de tabela, em vez de tabelas, exibições ou sinônimos.</span><span class="sxs-lookup"><span data-stu-id="6447a-120">It is identical to DBSCHEMA_COLUMNS, except that it returns column metadata only for table types, rather than for tables, views, or synonyms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6447a-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6447a-121">See Also</span></span>  
 <span data-ttu-id="6447a-122">[Os parâmetros com valor de tabela &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="6447a-122">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="6447a-123">Usar parâmetros com valor de tabela &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6447a-123">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
