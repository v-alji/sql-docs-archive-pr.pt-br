---
title: SQLTablePrivileges | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLTablePrivileges function
ms.assetid: 8cce22d5-28b1-4b50-a5bc-1de03e0ffd6b
author: rothja
ms.author: jroth
ms.openlocfilehash: 63298330d3f0ebf707dbb42c337553c1f363deab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573961"
---
# <a name="sqltableprivileges"></a><span data-ttu-id="4cb72-102">SQLTablePrivileges</span><span class="sxs-lookup"><span data-stu-id="4cb72-102">SQLTablePrivileges</span></span>
  <span data-ttu-id="4cb72-103">**SQLTablePrivileges** pode ser executado em um cursor estático.</span><span class="sxs-lookup"><span data-stu-id="4cb72-103">**SQLTablePrivileges** can be executed on a static cursor.</span></span> <span data-ttu-id="4cb72-104">Uma tentativa de executar **SQLTablePrivileges** em um atualizável (controlado por conjunto de chaves ou dinâmico) retorna SQL_SUCCESS_WITH_INFO indicando que o tipo de cursor foi alterado.</span><span class="sxs-lookup"><span data-stu-id="4cb72-104">An attempt to execute **SQLTablePrivileges** on an updatable (keyset-driven or dynamic) returns SQL_SUCCESS_WITH_INFO indicating the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="4cb72-105">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client dá suporte ao relatório de informações de tabelas em servidores vinculados, aceitando um nome de duas partes para o parâmetro *CatalogName* : *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="4cb72-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb72-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4cb72-106">See Also</span></span>  
 <span data-ttu-id="4cb72-107">[Função SQLTablePrivileges] (https://go.microsoft.com/fwlink/?LinkId=59373\)</span><span class="sxs-lookup"><span data-stu-id="4cb72-107">[SQLTablePrivileges Function](https://go.microsoft.com/fwlink/?LinkId=59373\)</span></span>   
 [<span data-ttu-id="4cb72-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="4cb72-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
