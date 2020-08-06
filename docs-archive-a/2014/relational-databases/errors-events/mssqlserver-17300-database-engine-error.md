---
title: MSSQLSERVER_17300 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17300 (Database Engine error)
ms.assetid: c1d6bfb6-28af-4df6-8087-25807602d282
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f77e39c71901166085d011d6d00f9a4a379bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679388"
---
# <a name="mssqlserver_17300"></a><span data-ttu-id="8b2f6-102">MSSQLSERVER_17300</span><span class="sxs-lookup"><span data-stu-id="8b2f6-102">MSSQLSERVER_17300</span></span>
    
## <a name="details"></a><span data-ttu-id="8b2f6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8b2f6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8b2f6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="8b2f6-104">Product Name</span></span>|<span data-ttu-id="8b2f6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8b2f6-105">SQL Server</span></span>|  
|<span data-ttu-id="8b2f6-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="8b2f6-106">Event ID</span></span>|<span data-ttu-id="8b2f6-107">17300</span><span class="sxs-lookup"><span data-stu-id="8b2f6-107">17300</span></span>|  
|<span data-ttu-id="8b2f6-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="8b2f6-108">Event Source</span></span>|<span data-ttu-id="8b2f6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8b2f6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8b2f6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8b2f6-110">Component</span></span>|<span data-ttu-id="8b2f6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8b2f6-111">SQLEngine</span></span>|  
|<span data-ttu-id="8b2f6-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="8b2f6-112">Symbolic Name</span></span>|<span data-ttu-id="8b2f6-113">PROC_OUT_OF_SYSTASK_SESSIONS</span><span class="sxs-lookup"><span data-stu-id="8b2f6-113">PROC_OUT_OF_SYSTASK_SESSIONS</span></span>|  
|<span data-ttu-id="8b2f6-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="8b2f6-114">Message Text</span></span>|<span data-ttu-id="8b2f6-115">O SQL Server não pôde executar uma nova tarefa do sistema, porque não há memória suficiente ou o número de sessões configuradas excede o máximo permitido no servidor.</span><span class="sxs-lookup"><span data-stu-id="8b2f6-115">SQL Server was unable to run a new system task, either because there is insufficient memory or the number of configured sessions exceeds the maximum allowed in the server.</span></span> <span data-ttu-id="8b2f6-116">Verifique se o servidor tem memória suficiente.</span><span class="sxs-lookup"><span data-stu-id="8b2f6-116">Verify that the server has adequate memory.</span></span> <span data-ttu-id="8b2f6-117">Use sp_configure com a opção 'conexões de usuário' para verificar o número de máximo de conexões de usuário permitidas.</span><span class="sxs-lookup"><span data-stu-id="8b2f6-117">Use sp_configure with option 'user connections' to check the maximum number of user connections allowed.</span></span> <span data-ttu-id="8b2f6-118">Use sys.dm_exec_sessions para verificar o número atual de sessões, inclusive processos de usuário.</span><span class="sxs-lookup"><span data-stu-id="8b2f6-118">Use sys.dm_exec_sessions to check the current number of sessions, including user processes.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8b2f6-119">Explicação</span><span class="sxs-lookup"><span data-stu-id="8b2f6-119">Explanation</span></span>  
 <span data-ttu-id="8b2f6-120">Uma tentativa de executar uma nova tarefa do sistema falhou devido à memória insuficiente ou porque o número de sessões configuradas no servidor foi excedido.</span><span class="sxs-lookup"><span data-stu-id="8b2f6-120">An attempt to run a new system task failed because of insufficient memory or because the number of configured sessions in the server was exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8b2f6-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="8b2f6-121">User Action</span></span>  
 <span data-ttu-id="8b2f6-122">Verifique se o servidor tem memória suficiente.</span><span class="sxs-lookup"><span data-stu-id="8b2f6-122">Verify that the server has enough memory.</span></span> <span data-ttu-id="8b2f6-123">Verifique o número atual de tarefas do sistema usando sys.dm_exec_sessions e verifique o valor configurado de máximo de conexões do usuário usando sp_configure.</span><span class="sxs-lookup"><span data-stu-id="8b2f6-123">Verify the current number of system tasks by using sys.dm_exec_sessions, and verify the configured value of maximum user connections by using sp_configure.</span></span>  
  
 <span data-ttu-id="8b2f6-124">Execute as seguintes tarefas, conforme apropriado:</span><span class="sxs-lookup"><span data-stu-id="8b2f6-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="8b2f6-125">Adicione mais memória ao servidor.</span><span class="sxs-lookup"><span data-stu-id="8b2f6-125">Add more memory to the server.</span></span>  
  
-   <span data-ttu-id="8b2f6-126">Termine uma ou mais sessões.</span><span class="sxs-lookup"><span data-stu-id="8b2f6-126">Terminate one or more sessions.</span></span>  
  
-   <span data-ttu-id="8b2f6-127">Aumente o número de máximo de conexões do usuário permitido no servidor.</span><span class="sxs-lookup"><span data-stu-id="8b2f6-127">Increase the maximum number of user connections allowed on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2f6-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b2f6-128">See Also</span></span>  
 <span data-ttu-id="8b2f6-129">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b2f6-129">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="8b2f6-130">[Opções de configuração do servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8b2f6-130">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="8b2f6-131">[sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b2f6-131">[sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span></span>  
 <span data-ttu-id="8b2f6-132">[Configurar a opção de configuração de servidor user connections](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="8b2f6-132">[Configure the user connections Server Configuration Option](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="8b2f6-133">KILL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8b2f6-133">KILL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/kill-transact-sql)  
  
  
