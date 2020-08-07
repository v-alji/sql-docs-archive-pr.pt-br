---
title: MSSQLSERVER_1401 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1401 (Database Engine error)
ms.assetid: 02928770-aa63-4509-8713-406c73e4cedc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 720263939e2f1685649fc41896e8ea10907d92ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581909"
---
# <a name="mssqlserver_1401"></a><span data-ttu-id="d45c4-102">MSSQLSERVER_1401</span><span class="sxs-lookup"><span data-stu-id="d45c4-102">MSSQLSERVER_1401</span></span>
    
## <a name="details"></a><span data-ttu-id="d45c4-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d45c4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d45c4-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d45c4-104">Product Name</span></span>|<span data-ttu-id="d45c4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d45c4-105">SQL Server</span></span>|  
|<span data-ttu-id="d45c4-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d45c4-106">Event ID</span></span>|<span data-ttu-id="d45c4-107">1401</span><span class="sxs-lookup"><span data-stu-id="d45c4-107">1401</span></span>|  
|<span data-ttu-id="d45c4-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d45c4-108">Event Source</span></span>|<span data-ttu-id="d45c4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d45c4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d45c4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d45c4-110">Component</span></span>|<span data-ttu-id="d45c4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d45c4-111">SQLEngine</span></span>|  
|<span data-ttu-id="d45c4-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d45c4-112">Symbolic Name</span></span>|<span data-ttu-id="d45c4-113">DBM_MASTERSTARTUP</span><span class="sxs-lookup"><span data-stu-id="d45c4-113">DBM_MASTERSTARTUP</span></span>|  
|<span data-ttu-id="d45c4-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d45c4-114">Message Text</span></span>|<span data-ttu-id="d45c4-115">Falha na inicialização da rotina de thread mestre do espelhamento de banco de dados pelo seguinte motivo: %ls.</span><span class="sxs-lookup"><span data-stu-id="d45c4-115">Startup of the database-mirroring master thread routine failed for the following reason: %ls.</span></span> <span data-ttu-id="d45c4-116">Corrija a causa do erro e reinicialize o serviço SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d45c4-116">Correct the cause of this error, and restart the SQL Server service.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d45c4-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="d45c4-117">Explanation</span></span>  
 <span data-ttu-id="d45c4-118">Falha na inicialização do thread de controle de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="d45c4-118">Startup of the mirroring control thread failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d45c4-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d45c4-119">User Action</span></span>  
 <span data-ttu-id="d45c4-120">No log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], procure o erro associado que precedeu essa mensagem.</span><span class="sxs-lookup"><span data-stu-id="d45c4-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, look for the associated error that preceded this message.</span></span> <span data-ttu-id="d45c4-121">Corrija a causa do erro e reinicie o serviço (MSSQLSERVER) do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d45c4-121">Correct the cause of this error, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service (MSSQLSERVER).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d45c4-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d45c4-122">See Also</span></span>  
 [<span data-ttu-id="d45c4-123">Iniciar, parar, pausar, retomar, reiniciar o mecanismo de banco de dados, o SQL Server Agent ou o serviço SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="d45c4-123">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
