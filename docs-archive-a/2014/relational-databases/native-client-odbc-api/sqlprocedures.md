---
title: Hiperprocedimentos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLProcedures function
ms.assetid: ec41f017-f5e0-40ef-913a-65d206068631
author: rothja
ms.author: jroth
ms.openlocfilehash: e37f15841a36eb95c1e9263d137ba2734d622367
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583006"
---
# <a name="sqlprocedures"></a><span data-ttu-id="9d85a-102">SQLProcedures</span><span class="sxs-lookup"><span data-stu-id="9d85a-102">SQLProcedures</span></span>
  <span data-ttu-id="9d85a-103">Todos os procedimentos armazenados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retornam um valor.</span><span class="sxs-lookup"><span data-stu-id="9d85a-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return a value.</span></span> <span data-ttu-id="9d85a-104">A SQL_PT_FUNCTION de relatórios **SQLProcedures** para a coluna do conjunto de resultados PROCEDURE_TYPE.</span><span class="sxs-lookup"><span data-stu-id="9d85a-104">**SQLProcedures** reports SQL_PT_FUNCTION for the result set column PROCEDURE_TYPE.</span></span>  
  
 <span data-ttu-id="9d85a-105">**SQLProcedures** retorna SQL_SUCCESS se os valores existem ou não para os parâmetros *CatalogName, schemas* ou *ProcName* .</span><span class="sxs-lookup"><span data-stu-id="9d85a-105">**SQLProcedures** returns SQL_SUCCESS whether or not values exist for *CatalogName, SchemaName,* or *ProcName* parameters.</span></span> <span data-ttu-id="9d85a-106">**SQLFetch** retorna SQL_NO_DATA quando são usados valores inválidos nesses parâmetros.</span><span class="sxs-lookup"><span data-stu-id="9d85a-106">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="9d85a-107">**SQLProcedures** pode ser executado em um cursor de servidor estático.</span><span class="sxs-lookup"><span data-stu-id="9d85a-107">**SQLProcedures** can be executed on a static server cursor.</span></span> <span data-ttu-id="9d85a-108">Uma tentativa de executar **Hiperprocedimentos** em um cursor atualizável (dinâmico ou de conjunto de chaves) retornará SQL_SUCCESS_WITH_INFO, indicando que o tipo de cursor foi alterado.</span><span class="sxs-lookup"><span data-stu-id="9d85a-108">An attempt to execute **SQLProcedures** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO, indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="9d85a-109">**SQLProcedures** retorna informações sobre os procedimentos cujos nomes correspondem a *ProcName* e podem ser executados pelo usuário atual ou para os quais o usuário atual recebeu a permissão VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="9d85a-109">**SQLProcedures** returns information about any procedures whose names match *ProcName* and can be executed by the current user, or for which the current user has been granted VIEW DEFINITION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d85a-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9d85a-110">See Also</span></span>  
 <span data-ttu-id="9d85a-111">[Função SQLProcedures](https://go.microsoft.com/fwlink/?LinkId=59364) </span><span class="sxs-lookup"><span data-stu-id="9d85a-111">[SQLProcedures Function](https://go.microsoft.com/fwlink/?LinkId=59364) </span></span>  
 [<span data-ttu-id="9d85a-112">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="9d85a-112">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
