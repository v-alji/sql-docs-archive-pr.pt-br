---
title: MSSQLSERVER_2596 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2596 (Database Engine error)
ms.assetid: 49ab892f-8ba3-4ba1-b562-ddf205019802
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27b2ceed40274df4ba57c4d61a83fbc60b6a7f80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574047"
---
# <a name="mssqlserver_2596"></a><span data-ttu-id="d3ce4-102">MSSQLSERVER_2596</span><span class="sxs-lookup"><span data-stu-id="d3ce4-102">MSSQLSERVER_2596</span></span>
    
## <a name="details"></a><span data-ttu-id="d3ce4-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d3ce4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d3ce4-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d3ce4-104">Product Name</span></span>|<span data-ttu-id="d3ce4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3ce4-105">SQL Server</span></span>|  
|<span data-ttu-id="d3ce4-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d3ce4-106">Event ID</span></span>|<span data-ttu-id="d3ce4-107">2596</span><span class="sxs-lookup"><span data-stu-id="d3ce4-107">2596</span></span>|  
|<span data-ttu-id="d3ce4-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d3ce4-108">Event Source</span></span>|<span data-ttu-id="d3ce4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d3ce4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d3ce4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d3ce4-110">Component</span></span>|<span data-ttu-id="d3ce4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d3ce4-111">SQLEngine</span></span>|  
|<span data-ttu-id="d3ce4-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d3ce4-112">Symbolic Name</span></span>|<span data-ttu-id="d3ce4-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span><span class="sxs-lookup"><span data-stu-id="d3ce4-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span></span>|  
|<span data-ttu-id="d3ce4-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d3ce4-114">Message Text</span></span>|<span data-ttu-id="d3ce4-115">A instrução de correção não foi processada.</span><span class="sxs-lookup"><span data-stu-id="d3ce4-115">The repair statement was not processed.</span></span> <span data-ttu-id="d3ce4-116">O banco de dados não pode ficar no modo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d3ce4-116">The database cannot be in read-only mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d3ce4-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="d3ce4-117">Explanation</span></span>  
 <span data-ttu-id="d3ce4-118">Essa mensagem indica que o banco de dados está no modo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d3ce4-118">This message indicates that the database is in read-only mode.</span></span> <span data-ttu-id="d3ce4-119">Não é possível fazer correções quando um banco de dados está no modo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="d3ce4-119">Repairs are not possible when a database is in read-only mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d3ce4-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d3ce4-120">User Action</span></span>  
 <span data-ttu-id="d3ce4-121">Defina o banco de dados como leitura/gravação usando ALTER DATABASE e, em seguida, execute o comando DBCC novamente.</span><span class="sxs-lookup"><span data-stu-id="d3ce4-121">Set the database to read-write by using ALTER DATABASE, and then re-run the DBCC command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ce4-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d3ce4-122">See Also</span></span>  
 [<span data-ttu-id="d3ce4-123">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d3ce4-123">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
