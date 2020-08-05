---
title: MSSQLSERVER_125 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "125"
helpviewer_keywords:
- 125 (Database Engine error)
ms.assetid: 0f58338d-2ea0-48b8-8a20-c438b0940433
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59c732d80ccfafc8f242bb1c42fe60e3dea81f19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574049"
---
# <a name="mssqlserver_125"></a><span data-ttu-id="16c49-102">MSSQLSERVER_125</span><span class="sxs-lookup"><span data-stu-id="16c49-102">MSSQLSERVER_125</span></span>
    
## <a name="details"></a><span data-ttu-id="16c49-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="16c49-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="16c49-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="16c49-104">Product Name</span></span>|<span data-ttu-id="16c49-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="16c49-105">SQL Server</span></span>|  
|<span data-ttu-id="16c49-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="16c49-106">Event ID</span></span>|<span data-ttu-id="16c49-107">125</span><span class="sxs-lookup"><span data-stu-id="16c49-107">125</span></span>|  
|<span data-ttu-id="16c49-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="16c49-108">Event Source</span></span>|<span data-ttu-id="16c49-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="16c49-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="16c49-110">Componente</span><span class="sxs-lookup"><span data-stu-id="16c49-110">Component</span></span>|<span data-ttu-id="16c49-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="16c49-111">SQLEngine</span></span>|  
|<span data-ttu-id="16c49-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="16c49-112">Symbolic Name</span></span>||  
|<span data-ttu-id="16c49-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="16c49-113">Message Text</span></span>|<span data-ttu-id="16c49-114">As expressões Case só podem ser aninhadas no nível %d.</span><span class="sxs-lookup"><span data-stu-id="16c49-114">Case expressions may only be nested to level %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="16c49-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="16c49-115">Explanation</span></span>  
 <span data-ttu-id="16c49-116">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite apenas 10 níveis de aninhamento em expressões CASE.</span><span class="sxs-lookup"><span data-stu-id="16c49-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows for only 10 levels of nesting in CASE expressions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="16c49-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="16c49-117">User Action</span></span>  
 <span data-ttu-id="16c49-118">Reduza o nível de instruções CASE instruções para 10 ou menos.</span><span class="sxs-lookup"><span data-stu-id="16c49-118">Reduce the level of CASE statements to 10 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c49-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16c49-119">See Also</span></span>  
 [<span data-ttu-id="16c49-120">CASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="16c49-120">CASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/case-transact-sql)  
  
  
