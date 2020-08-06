---
title: SQLColumnPrivileges | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLColumnPrivileges function
ms.assetid: c78acd4e-8668-4abc-9bc9-6ad381965863
author: rothja
ms.author: jroth
ms.openlocfilehash: bf46fed47817ed94ea2382f2147df254f2986aec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570683"
---
# <a name="sqlcolumnprivileges"></a><span data-ttu-id="28bb8-102">SQLColumnPrivileges</span><span class="sxs-lookup"><span data-stu-id="28bb8-102">SQLColumnPrivileges</span></span>
  <span data-ttu-id="28bb8-103">**SQLColumnPrivileges** retorna SQL_SUCCESS se os valores existem ou não para os parâmetros*CatalogName*, *schemas*, *TableName*ou *ColumnName* .</span><span class="sxs-lookup"><span data-stu-id="28bb8-103">**SQLColumnPrivileges** returns SQL_SUCCESS whether or not values exist for the*CatalogName*, *SchemaName*, *TableName*, or *ColumnName* parameters.</span></span> <span data-ttu-id="28bb8-104">**SQLFetch** retorna SQL_NO_DATA quando são usados valores inválidos nesses parâmetros.</span><span class="sxs-lookup"><span data-stu-id="28bb8-104">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="28bb8-105">**SQLColumnPrivileges** pode ser executado em um cursor de servidor estático.</span><span class="sxs-lookup"><span data-stu-id="28bb8-105">**SQLColumnPrivileges** can be executed on a static server cursor.</span></span> <span data-ttu-id="28bb8-106">Uma tentativa de executar **SQLColumnPrivileges** em um cursor atualizável (dinâmico ou de conjunto de chaves) retornará SQL_SUCCESS_WITH_INFO indicando que o tipo de cursor foi alterado.</span><span class="sxs-lookup"><span data-stu-id="28bb8-106">An attempt to execute **SQLColumnPrivileges** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="28bb8-107">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client dá suporte ao relatório de informações de tabelas em servidores vinculados, aceitando um nome de duas partes para o parâmetro *CatalogName* : *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="28bb8-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28bb8-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="28bb8-108">See Also</span></span>  
 <span data-ttu-id="28bb8-109">[Função SQLColumnPrivileges](https://go.microsoft.com/fwlink/?LinkId=59335) </span><span class="sxs-lookup"><span data-stu-id="28bb8-109">[SQLColumnPrivileges Function](https://go.microsoft.com/fwlink/?LinkId=59335) </span></span>  
 [<span data-ttu-id="28bb8-110">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="28bb8-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
