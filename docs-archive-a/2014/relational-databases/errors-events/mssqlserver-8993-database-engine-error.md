---
title: MSSQLSERVER_8993 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8993 (Database Engine error)
ms.assetid: 06aac110-a41c-4853-bc8e-a83e8535b8be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5ee9497e9c4484fd885803c0feff20362a159ff2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569520"
---
# <a name="mssqlserver_8993"></a><span data-ttu-id="fdb0a-102">MSSQLSERVER_8993</span><span class="sxs-lookup"><span data-stu-id="fdb0a-102">MSSQLSERVER_8993</span></span>
    
## <a name="details"></a><span data-ttu-id="fdb0a-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fdb0a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fdb0a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="fdb0a-104">Product Name</span></span>|<span data-ttu-id="fdb0a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fdb0a-105">SQL Server</span></span>|  
|<span data-ttu-id="fdb0a-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="fdb0a-106">Event ID</span></span>|<span data-ttu-id="fdb0a-107">8993</span><span class="sxs-lookup"><span data-stu-id="fdb0a-107">8993</span></span>|  
|<span data-ttu-id="fdb0a-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="fdb0a-108">Event Source</span></span>|<span data-ttu-id="fdb0a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fdb0a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fdb0a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fdb0a-110">Component</span></span>|<span data-ttu-id="fdb0a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fdb0a-111">SQLEngine</span></span>|  
|<span data-ttu-id="fdb0a-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="fdb0a-112">Symbolic Name</span></span>|<span data-ttu-id="fdb0a-113">DBCC3_MISSING_FORWARDED_ROW</span><span class="sxs-lookup"><span data-stu-id="fdb0a-113">DBCC3_MISSING_FORWARDED_ROW</span></span>|  
|<span data-ttu-id="fdb0a-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="fdb0a-114">Message Text</span></span>|<span data-ttu-id="fdb0a-115">ID do objeto O_ID, página de linha de encaminhamento P_ID1, slot S_ID1 aponta para página P_ID2, slot S_ID2.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-115">Object ID O_ID, forwarding row page P_ID1, slot S_ID1 points to page P_ID2, slot S_ID2.</span></span> <span data-ttu-id="fdb0a-116">A linha encaminhada não foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-116">Did not encounter forwarded row.</span></span> <span data-ttu-id="fdb0a-117">Possível erro de alocação.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-117">Possible allocation error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fdb0a-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="fdb0a-118">Explanation</span></span>  
 <span data-ttu-id="fdb0a-119">Uma linha de encaminhamento em um heap aponta para uma linha encaminhada inexistente.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-119">A forwarding row in a heap points to a nonexistent forwarded row.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fdb0a-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="fdb0a-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="fdb0a-121">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="fdb0a-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="fdb0a-122">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="fdb0a-123">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="fdb0a-124">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="fdb0a-125">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="fdb0a-126">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="fdb0a-127">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="fdb0a-128">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="fdb0a-129">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="fdb0a-130">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="fdb0a-130">Restore from Backup</span></span>  
 <span data-ttu-id="fdb0a-131">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="fdb0a-132">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="fdb0a-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="fdb0a-133">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="fdb0a-134">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="fdb0a-135">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="fdb0a-136">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="fdb0a-137">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="fdb0a-138">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="fdb0a-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="fdb0a-139">A linha de encaminhamento será excluída e todos os índices não clusterizados serão recriados.</span><span class="sxs-lookup"><span data-stu-id="fdb0a-139">The forwarding row will be deleted and any nonclustered indexes will be rebuilt.</span></span>  
  
  
