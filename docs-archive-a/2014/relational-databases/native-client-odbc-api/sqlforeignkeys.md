---
title: SQLForeignKeys | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLForeignKeys function
ms.assetid: 6c01ce0d-30d7-4c86-8705-3ab254d8a845
author: rothja
ms.author: jroth
ms.openlocfilehash: a61e80867abb8ecb4d2628b74dc9956051c8e4ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572082"
---
# <a name="sqlforeignkeys"></a><span data-ttu-id="209c8-102">SQLForeignKeys</span><span class="sxs-lookup"><span data-stu-id="209c8-102">SQLForeignKeys</span></span>
  <span data-ttu-id="209c8-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte a atualizações e exclusões em cascata por meio do mecanismo de restrição de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="209c8-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports cascading updates and deletes through the foreign key constraint mechanism.</span></span> <span data-ttu-id="209c8-104">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retornará SQL_CASCADE para as colunas UPDATE_RULE e/ou DELETE_RULE se a opção CASCADE estiver especificada na cláusula ON UPDATE e/ou ON DELETE das restrições FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="209c8-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns SQL_CASCADE for UPDATE_RULE and/or DELETE_RULE columns if CASCADE option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span> <span data-ttu-id="209c8-105">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retornará SQL_NO_ACTION para as colunas UPDATE_RULE e/ou DELETE_RULE se a opção NO ACTION estiver especificada na cláusula ON UPDATE e/ou ON DELETE das restrições FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="209c8-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns SQL_NO_ACTION for UPDATE_RULE and/or DELETE_RULE columns if NO ACTION option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span>  
  
 <span data-ttu-id="209c8-106">Quando valores inválidos estão presentes em qualquer parâmetro **SQLForeignKeys** , **SQLForeignKeys** retorna SQL_SUCCESS na execução.</span><span class="sxs-lookup"><span data-stu-id="209c8-106">When invalid values are present in any **SQLForeignKeys** parameter, **SQLForeignKeys** returns SQL_SUCCESS on execution.</span></span> <span data-ttu-id="209c8-107">**SQLFetch** retorna SQL_NO_DATA quando são usados valores inválidos nesses parâmetros.</span><span class="sxs-lookup"><span data-stu-id="209c8-107">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="209c8-108">**SQLForeignKeys** pode ser executado em um cursor de servidor estático.</span><span class="sxs-lookup"><span data-stu-id="209c8-108">**SQLForeignKeys** can be executed on a static server cursor.</span></span> <span data-ttu-id="209c8-109">Uma tentativa de executar **SQLForeignKeys** em um cursor atualizável (dinâmico ou de conjunto de chaves) retorna SQL_SUCCESS_WITH_INFO indicando que o tipo de cursor foi alterado.</span><span class="sxs-lookup"><span data-stu-id="209c8-109">An attempt to execute **SQLForeignKeys** on an updatable (dynamic or keyset) cursor returns SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="209c8-110">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client dá suporte a informações de relatório para tabelas em servidores vinculados, aceitando um nome de duas partes para os parâmetros *FKCatalogName* e *PKCatalogName* : *linked_server_name. catalog_name*.</span><span class="sxs-lookup"><span data-stu-id="209c8-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *FKCatalogName* and *PKCatalogName* parameters: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="209c8-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="209c8-111">See Also</span></span>  
 <span data-ttu-id="209c8-112">[Função SQLForeignKeys](https://go.microsoft.com/fwlink/?LinkId=59344) </span><span class="sxs-lookup"><span data-stu-id="209c8-112">[SQLForeignKeys Function](https://go.microsoft.com/fwlink/?LinkId=59344) </span></span>  
 [<span data-ttu-id="209c8-113">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="209c8-113">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
