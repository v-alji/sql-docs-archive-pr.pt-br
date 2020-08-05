---
title: Construções com suporte em procedimentos armazenados compilados nativamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 6b21f47e-bceb-4054-8b3c-9d39bb9583c0
author: rothja
ms.author: jroth
ms.openlocfilehash: f3bc7e28fa2a868ac39c6adbb2dea3cc5c3ace73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572556"
---
# <a name="supported-constructs-on-natively-compiled-stored-procedures"></a><span data-ttu-id="86d09-102">Construções com suporte em procedimentos armazenados compilados de modo nativo</span><span class="sxs-lookup"><span data-stu-id="86d09-102">Supported Constructs on Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="86d09-103">Este tópico lista as construções com suporte nos procedimentos armazenados compilados nativamente.</span><span class="sxs-lookup"><span data-stu-id="86d09-103">This topic lists the supported constructs on natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="86d09-104">Para obter informações sobre construções sem suporte, veja [Construções do Transact-SQL sem suporte pelo OLTP in-memory](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="86d09-104">For information about unsupported constructs, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="procedure-ddl"></a><span data-ttu-id="86d09-105">DDL do procedimento</span><span class="sxs-lookup"><span data-stu-id="86d09-105">Procedure DDL</span></span>  
 <span data-ttu-id="86d09-106">Há suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="86d09-106">The following are supported:</span></span>  
  
-   <span data-ttu-id="86d09-107">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="86d09-107">CREATE PROCEDURE</span></span>  
  
-   <span data-ttu-id="86d09-108">DROP PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="86d09-108">DROP PROCEDURE</span></span>  
  
-   <span data-ttu-id="86d09-109">SCHEMABINDING (necessário para procedimentos armazenados compilados nativamente)</span><span class="sxs-lookup"><span data-stu-id="86d09-109">SCHEMABINDING (required for natively compiled stored procedures)</span></span>  
  
-   <span data-ttu-id="86d09-110">NATIVE_COMPILATION</span><span class="sxs-lookup"><span data-stu-id="86d09-110">NATIVE_COMPILATION</span></span>  
  
-   <span data-ttu-id="86d09-111">Os parâmetros podem ser declarados com NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="86d09-111">Parameters can be declared as NOT NULL.</span></span>  
  
-   <span data-ttu-id="86d09-112">Parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="86d09-112">Table-valued parameters.</span></span>  
  
## <a name="security"></a><span data-ttu-id="86d09-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="86d09-113">Security</span></span>  
 <span data-ttu-id="86d09-114">Há suporte para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="86d09-114">The following are supported:</span></span>  
  
-   <span data-ttu-id="86d09-115">Para procedimentos: EXECUTE AS OWNER, SELF e usuário.</span><span class="sxs-lookup"><span data-stu-id="86d09-115">For procedures: EXECUTE AS OWNER, SELF, and user.</span></span>  
  
-   <span data-ttu-id="86d09-116">Permissões GRANT e DENY em tabelas e procedimentos.</span><span class="sxs-lookup"><span data-stu-id="86d09-116">GRANT and DENY permissions on tables and procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d09-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="86d09-117">See Also</span></span>  
 [<span data-ttu-id="86d09-118">Procedimentos armazenados compilados nativamente</span><span class="sxs-lookup"><span data-stu-id="86d09-118">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
