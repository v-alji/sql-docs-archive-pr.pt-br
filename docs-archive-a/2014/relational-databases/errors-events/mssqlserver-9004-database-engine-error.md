---
title: MSSQLSERVER_9004 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9004 (Database Engine error)
ms.assetid: b528bb49-340c-4a81-9c8d-cefce6562f16
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 910665b4349e5b13c5abb4fd687dcf0c6fc122cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573046"
---
# <a name="mssqlserver_9004"></a><span data-ttu-id="d84d7-102">MSSQLSERVER_9004</span><span class="sxs-lookup"><span data-stu-id="d84d7-102">MSSQLSERVER_9004</span></span>
    
## <a name="details"></a><span data-ttu-id="d84d7-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d84d7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d84d7-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d84d7-104">Product Name</span></span>|<span data-ttu-id="d84d7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d84d7-105">SQL Server</span></span>|  
|<span data-ttu-id="d84d7-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d84d7-106">Event ID</span></span>|<span data-ttu-id="d84d7-107">9004</span><span class="sxs-lookup"><span data-stu-id="d84d7-107">9004</span></span>|  
|<span data-ttu-id="d84d7-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d84d7-108">Event Source</span></span>|<span data-ttu-id="d84d7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d84d7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d84d7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d84d7-110">Component</span></span>|<span data-ttu-id="d84d7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d84d7-111">SQLEngine</span></span>|  
|<span data-ttu-id="d84d7-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d84d7-112">Symbolic Name</span></span>|<span data-ttu-id="d84d7-113">LOG_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="d84d7-113">LOG_CORRUPT</span></span>|  
|<span data-ttu-id="d84d7-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d84d7-114">Message Text</span></span>|<span data-ttu-id="d84d7-115">Erro ao processar o log do banco de dados '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="d84d7-115">An error occurred while processing the log for database '%.\*ls'.</span></span>  <span data-ttu-id="d84d7-116">Se possível, restaure do backup.</span><span class="sxs-lookup"><span data-stu-id="d84d7-116">If possible, restore from backup.</span></span> <span data-ttu-id="d84d7-117">Se não houver um backup disponível, talvez seja necessário recriar o log.</span><span class="sxs-lookup"><span data-stu-id="d84d7-117">If a backup is not available, it might be necessary to rebuild the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d84d7-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="d84d7-118">Explanation</span></span>  
 <span data-ttu-id="d84d7-119">Ocorreu um erro ao processar o log durante a reversão, a recuperação ou a replicação.</span><span class="sxs-lookup"><span data-stu-id="d84d7-119">An error was encountered while processing the log during rollback, recovery, or replication.</span></span> <span data-ttu-id="d84d7-120">Isso pode indicar um erro detectado pelo sistema operacional ou um erro de consistência interno detectado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d84d7-120">This could indicate an error detected by the operating system-or an internal consistency error detected by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d84d7-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d84d7-121">User Action</span></span>  
 <span data-ttu-id="d84d7-122">Uma das ações seguintes poderá corrigir esse erro:</span><span class="sxs-lookup"><span data-stu-id="d84d7-122">One of the following actions will correct this error:</span></span>  
  
-   <span data-ttu-id="d84d7-123">Faça uma restauração a partir do backup.</span><span class="sxs-lookup"><span data-stu-id="d84d7-123">Restore from a backup.</span></span>  
  
-   <span data-ttu-id="d84d7-124">Refaça o log.</span><span class="sxs-lookup"><span data-stu-id="d84d7-124">Rebuild the log.</span></span>  
  
 <span data-ttu-id="d84d7-125">Verifique também o evento de sistema e logs de erros para identificar problemas no sistema que podem ter causado o erro.</span><span class="sxs-lookup"><span data-stu-id="d84d7-125">Also, check system event and error logs to identify issues within the system that may have caused the problem.</span></span>  
  
  
