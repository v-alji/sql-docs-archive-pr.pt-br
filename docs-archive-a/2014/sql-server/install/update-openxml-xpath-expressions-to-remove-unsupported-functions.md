---
title: Atualizar expressões OPENXML XPath para remover funções sem suporte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- OPENXML queries
ms.assetid: b459abaf-8787-4b65-9231-ae30e5469fd0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2c64408d6d705654014b6d071012001374a5f486
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573432"
---
# <a name="update-openxml-xpath-expressions-to-remove-unsupported-functions"></a><span data-ttu-id="34f39-102">Atualizar expressões OPENXML XPath para remover funções para as quais não há suporte</span><span class="sxs-lookup"><span data-stu-id="34f39-102">Update OPENXML XPath expressions to remove unsupported functions</span></span>
  <span data-ttu-id="34f39-103">O Supervisor de Atualização detectou o uso da funcionalidade XPath.</span><span class="sxs-lookup"><span data-stu-id="34f39-103">Upgrade Advisor detected the use of XPath functionality.</span></span> <span data-ttu-id="34f39-104">Você pode ser afetado por alterações na funcionalidade XPath para recursos OPENXML depois de atualizar.</span><span class="sxs-lookup"><span data-stu-id="34f39-104">You may be affected by changes in XPath functionality for OPENXML features after you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="34f39-105">Componente</span><span class="sxs-lookup"><span data-stu-id="34f39-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="34f39-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="34f39-106">Description</span></span>  
 <span data-ttu-id="34f39-107">Agora, o MSXML 3.0 é o mecanismo subjacente usado para processar expressões que são usadas dentro de consultas OPENXML.</span><span class="sxs-lookup"><span data-stu-id="34f39-107">MSXML 3.0 is now the underlying engine that is used to process XPath expressions that are used within OPENXML queries.</span></span> <span data-ttu-id="34f39-108">O MSXML 3.0 tem um mecanismo XPath 1.0 mais restrito, do qual foi removido o suporte para as seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="34f39-108">MSXML 3.0 has a stricter XPath 1.0 engine in which support for the following functions has been removed:</span></span>  
  
-   <span data-ttu-id="34f39-109">format-number()</span><span class="sxs-lookup"><span data-stu-id="34f39-109">format-number()</span></span>  
  
-   <span data-ttu-id="34f39-110">formatNumber ()</span><span class="sxs-lookup"><span data-stu-id="34f39-110">formatNumber()</span></span>  
  
-   <span data-ttu-id="34f39-111">current()</span><span class="sxs-lookup"><span data-stu-id="34f39-111">current()</span></span>  
  
-   <span data-ttu-id="34f39-112">element-available()</span><span class="sxs-lookup"><span data-stu-id="34f39-112">element-available()</span></span>  
  
-   <span data-ttu-id="34f39-113">function-available()</span><span class="sxs-lookup"><span data-stu-id="34f39-113">function-available()</span></span>  
  
-   <span data-ttu-id="34f39-114">system-property()</span><span class="sxs-lookup"><span data-stu-id="34f39-114">system-property()</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="34f39-115">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="34f39-115">Corrective Action</span></span>  
 <span data-ttu-id="34f39-116">No caso das funções format-number() e formatNumber(), você pode usar [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34f39-116">In the case of format-number() and formatNumber(), you can use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="34f39-117">Para as outras funções sem-suporte listadas anteriormente, não há nenhuma solução alternativa direta.</span><span class="sxs-lookup"><span data-stu-id="34f39-117">For the other unsupported functions listed earlier, there is no direct workaround.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f39-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34f39-118">See Also</span></span>  
 <span data-ttu-id="34f39-119">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="34f39-119">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="34f39-120">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="34f39-120">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
