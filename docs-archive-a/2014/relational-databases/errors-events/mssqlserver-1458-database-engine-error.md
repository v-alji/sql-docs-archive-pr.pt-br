---
title: MSSQLSERVER_1458 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1458 (Database Engine error)
ms.assetid: adc78c59-a6f2-432b-9a07-fdd1dc2b9026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: efa45177a92402b25099be5bb3e3dcc91a5fa6d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581898"
---
# <a name="mssqlserver_1458"></a><span data-ttu-id="2fc0a-102">MSSQLSERVER_1458</span><span class="sxs-lookup"><span data-stu-id="2fc0a-102">MSSQLSERVER_1458</span></span>
    
## <a name="details"></a><span data-ttu-id="2fc0a-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2fc0a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2fc0a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="2fc0a-104">Product Name</span></span>|<span data-ttu-id="2fc0a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2fc0a-105">SQL Server</span></span>|  
|<span data-ttu-id="2fc0a-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="2fc0a-106">Event ID</span></span>|<span data-ttu-id="2fc0a-107">1458</span><span class="sxs-lookup"><span data-stu-id="2fc0a-107">1458</span></span>|  
|<span data-ttu-id="2fc0a-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="2fc0a-108">Event Source</span></span>|<span data-ttu-id="2fc0a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2fc0a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2fc0a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2fc0a-110">Component</span></span>|<span data-ttu-id="2fc0a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2fc0a-111">SQLEngine</span></span>|  
|<span data-ttu-id="2fc0a-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="2fc0a-112">Symbolic Name</span></span>|<span data-ttu-id="2fc0a-113">DBM_FAILREDO_ON_PRIMARY</span><span class="sxs-lookup"><span data-stu-id="2fc0a-113">DBM_FAILREDO_ON_PRIMARY</span></span>|  
|<span data-ttu-id="2fc0a-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="2fc0a-114">Message Text</span></span>|<span data-ttu-id="2fc0a-115">A cópia principal do banco de dados '%.\*ls' encontrou o erro %d, status %d, severidade %d.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-115">The principal copy of the '%.\*ls' database encountered error %d, status %d, severity %d.</span></span> <span data-ttu-id="2fc0a-116">O espelhamento de banco de dados foi suspenso.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-116">Database mirroring has been suspended.</span></span> <span data-ttu-id="2fc0a-117">Tente resolver a condição de erro e retomar o espelhamento.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-117">Try to resolve the error condition, and resume mirroring.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2fc0a-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="2fc0a-118">Explanation</span></span>  
 <span data-ttu-id="2fc0a-119">Essa mensagem indica que o banco de dados principal encontrou um erro que causou a suspensão do espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-119">This messages indicates that the principal database encountered an error that caused database mirroring to be suspended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2fc0a-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="2fc0a-120">User Action</span></span>  
 <span data-ttu-id="2fc0a-121">A maioria dos casos desse erro é corrigida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-121">Most cases of this error are self correcting.</span></span> <span data-ttu-id="2fc0a-122">Se o problema persistir, reiniciar o banco de dados ou a instância do servidor geralmente corrige o problema.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-122">If the problem persists, restarting the database or server instance typically corrects the problem.</span></span> <span data-ttu-id="2fc0a-123">Para obter mais informações, procure no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em cada parceiro o erro associado que precedeu essa mensagem.</span><span class="sxs-lookup"><span data-stu-id="2fc0a-123">For more information, look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on each partner for the associated error that preceded this message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc0a-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2fc0a-124">See Also</span></span>  
 [<span data-ttu-id="2fc0a-125">Monitorando o espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2fc0a-125">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
