---
title: MSSQLSERVER_18752 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18752 (Database Engine error)
ms.assetid: 234c58d8-7a1e-4b07-a64b-32a311527980
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a463e4019875f4a233ae2920f32bc2252376a41c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573081"
---
# <a name="mssqlserver_18752"></a><span data-ttu-id="1698f-102">MSSQLSERVER_18752</span><span class="sxs-lookup"><span data-stu-id="1698f-102">MSSQLSERVER_18752</span></span>
    
## <a name="details"></a><span data-ttu-id="1698f-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1698f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1698f-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="1698f-104">Product Name</span></span>|<span data-ttu-id="1698f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1698f-105">SQL Server</span></span>|  
|<span data-ttu-id="1698f-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="1698f-106">Event ID</span></span>|<span data-ttu-id="1698f-107">18752</span><span class="sxs-lookup"><span data-stu-id="1698f-107">18752</span></span>|  
|<span data-ttu-id="1698f-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="1698f-108">Event Source</span></span>|<span data-ttu-id="1698f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1698f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1698f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1698f-110">Component</span></span>|<span data-ttu-id="1698f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1698f-111">SQLEngine</span></span>|  
|<span data-ttu-id="1698f-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="1698f-112">Symbolic Name</span></span>|<span data-ttu-id="1698f-113">REPL_INUSE</span><span class="sxs-lookup"><span data-stu-id="1698f-113">REPL_INUSE</span></span>|  
|<span data-ttu-id="1698f-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="1698f-114">Message Text</span></span>|<span data-ttu-id="1698f-115">Somente um Agente de Leitor de Log ou um procedimento relacionado ao log (sp_repldone, sp_replcmds e sp_replshowcmds) pode se conectar ao banco de dados de cada vez.</span><span class="sxs-lookup"><span data-stu-id="1698f-115">Only one Log Reader Agent or log-related procedure (sp_repldone, sp_replcmds, and sp_replshowcmds) can connect to a database at a time.</span></span> <span data-ttu-id="1698f-116">Se você tiver executado um procedimento relacionado ao log, descarte a conexão através da qual o procedimento foi executado ou execute sp_replflush por essa conexão antes de iniciar o Agente de Leitor de Log ou de executar outro procedimento relacionado ao log.</span><span class="sxs-lookup"><span data-stu-id="1698f-116">If you executed a log-related procedure, drop the connection over which the procedure was executed or execute sp_replflush over that connection before starting the Log Reader Agent or executing another log-related procedure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1698f-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="1698f-117">Explanation</span></span>  
 <span data-ttu-id="1698f-118">Somente um Log Reader Agent ou um procedimento relacionado ao log pode se conectar ao banco de dados de cada vez.</span><span class="sxs-lookup"><span data-stu-id="1698f-118">Only one Log Reader agent or log-related procedure can connect to a database at a time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1698f-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="1698f-119">User Action</span></span>  
 <span data-ttu-id="1698f-120">Verifique se nenhum outro leitor de log está sendo executado no mesmo banco de dados de publicação e se nenhuma outra conexão ativa executou sp_replcmds/sp_repltrans/sp_repldone anteriormente sem executar sp_replflush em seguida ou desconectar.</span><span class="sxs-lookup"><span data-stu-id="1698f-120">Make sure no other logreader is running for the same publishing database, and no other active connection had previously run sp_replcmds/sp_repltrans/sp_repldone without running sp_replflush afterwards or disconnecting.</span></span>  
  
  
