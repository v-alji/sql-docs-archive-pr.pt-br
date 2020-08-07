---
title: MSSQLSERVER_9003 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9003 (Database Engine error)
ms.assetid: 7fdfb391-5c6f-428b-b434-6c3d0b30fd7b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6f67e4184ea54be6bcd5c2a74d3c0e0711b702f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575852"
---
# <a name="mssqlserver_9003"></a><span data-ttu-id="46b3d-102">MSSQLSERVER_9003</span><span class="sxs-lookup"><span data-stu-id="46b3d-102">MSSQLSERVER_9003</span></span>
    
## <a name="details"></a><span data-ttu-id="46b3d-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="46b3d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46b3d-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="46b3d-104">Product Name</span></span>|<span data-ttu-id="46b3d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="46b3d-105">SQL Server</span></span>|  
|<span data-ttu-id="46b3d-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="46b3d-106">Event ID</span></span>|<span data-ttu-id="46b3d-107">9003</span><span class="sxs-lookup"><span data-stu-id="46b3d-107">9003</span></span>|  
|<span data-ttu-id="46b3d-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="46b3d-108">Event Source</span></span>|<span data-ttu-id="46b3d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="46b3d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="46b3d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="46b3d-110">Component</span></span>|<span data-ttu-id="46b3d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="46b3d-111">SQLEngine</span></span>|  
|<span data-ttu-id="46b3d-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="46b3d-112">Symbolic Name</span></span>|<span data-ttu-id="46b3d-113">LOG_INVALID_LSN</span><span class="sxs-lookup"><span data-stu-id="46b3d-113">LOG_INVALID_LSN</span></span>|  
|<span data-ttu-id="46b3d-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="46b3d-114">Message Text</span></span>|<span data-ttu-id="46b3d-115">O número de exames do log %S_LSN passado para o exame no banco de dados '%.\*ls' não é válido.</span><span class="sxs-lookup"><span data-stu-id="46b3d-115">The log scan number %S_LSN passed to log scan in database '%.\*ls' is not valid.</span></span> <span data-ttu-id="46b3d-116">Esse erro pode indicar danos nos dados ou que o arquivo de log (.ldf) não corresponde ao arquivo de dados (.mdf).</span><span class="sxs-lookup"><span data-stu-id="46b3d-116">This error may indicate data corruption or that the log file (.ldf) does not match the data file (.mdf).</span></span> <span data-ttu-id="46b3d-117">Se esse erro ocorreu durante a replicação, crie a publicação novamente.</span><span class="sxs-lookup"><span data-stu-id="46b3d-117">If this error occurred during replication, re-create the publication.</span></span> <span data-ttu-id="46b3d-118">Caso contrário, se o problema resultar em uma falha durante a inicialização, restaure de um backup.</span><span class="sxs-lookup"><span data-stu-id="46b3d-118">Otherwise, restore from backup if the problem results in a failure during startup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46b3d-119">Explicação</span><span class="sxs-lookup"><span data-stu-id="46b3d-119">Explanation</span></span>  
 <span data-ttu-id="46b3d-120">Um componente passou um número de sequência de log inválido ao gerenciador de log do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="46b3d-120">A component passed an invalid log sequence number to the log manager for the database.</span></span> <span data-ttu-id="46b3d-121">Isso pode causar replicação, corrompimento ou uma inconsistência entre o arquivo de dados primário e o log.</span><span class="sxs-lookup"><span data-stu-id="46b3d-121">This could be replication, corruption, or an inconsistency between the primary data file and the log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46b3d-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="46b3d-122">User Action</span></span>  
 <span data-ttu-id="46b3d-123">Se ele ocorreu durante replicação, recrie a publicação.</span><span class="sxs-lookup"><span data-stu-id="46b3d-123">If this occurred during replication, recreate the publication.</span></span> <span data-ttu-id="46b3d-124">Caso contrário, faça uma restauração a partir do backup.</span><span class="sxs-lookup"><span data-stu-id="46b3d-124">Otherwise, restore from backup.</span></span>  
  
  
