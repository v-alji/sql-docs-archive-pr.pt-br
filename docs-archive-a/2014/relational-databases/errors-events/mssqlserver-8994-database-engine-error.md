---
title: MSSQLSERVER_8994 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8994 (Database Engine error)
ms.assetid: 8f4b0e2f-04c0-46e4-9208-20a7085d7a1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0bcc0b1db100b70390c09e9c825dbfd068d968af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569519"
---
# <a name="mssqlserver_8994"></a><span data-ttu-id="837c7-102">MSSQLSERVER_8994</span><span class="sxs-lookup"><span data-stu-id="837c7-102">MSSQLSERVER_8994</span></span>
    
## <a name="details"></a><span data-ttu-id="837c7-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="837c7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="837c7-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="837c7-104">Product Name</span></span>|<span data-ttu-id="837c7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="837c7-105">SQL Server</span></span>|  
|<span data-ttu-id="837c7-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="837c7-106">Event ID</span></span>|<span data-ttu-id="837c7-107">8994</span><span class="sxs-lookup"><span data-stu-id="837c7-107">8994</span></span>|  
|<span data-ttu-id="837c7-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="837c7-108">Event Source</span></span>|<span data-ttu-id="837c7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="837c7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="837c7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="837c7-110">Component</span></span>|<span data-ttu-id="837c7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="837c7-111">SQLEngine</span></span>|  
|<span data-ttu-id="837c7-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="837c7-112">Symbolic Name</span></span>|<span data-ttu-id="837c7-113">DBCC3_MISSING_FORWARDING_ROW</span><span class="sxs-lookup"><span data-stu-id="837c7-113">DBCC3_MISSING_FORWARDING_ROW</span></span>|  
|<span data-ttu-id="837c7-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="837c7-114">Message Text</span></span>|<span data-ttu-id="837c7-115">ID de objeto O_ID, página de linha encaminhada P_ID1, slot S_ID1 deveria ser apontada pela página de linha de encaminhamento P_ID2, slot S_ID2.</span><span class="sxs-lookup"><span data-stu-id="837c7-115">Object ID O_ID, forwarded row page P_ID1, slot S_ID1 should be pointed to by forwarding row page P_ID2, slot S_ID2.</span></span> <span data-ttu-id="837c7-116">Linha encaminhada não encontrada.</span><span class="sxs-lookup"><span data-stu-id="837c7-116">Did not encounter forwarding row.</span></span> <span data-ttu-id="837c7-117">Possível erro de alocação.</span><span class="sxs-lookup"><span data-stu-id="837c7-117">Possible allocation error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="837c7-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="837c7-118">Explanation</span></span>  
 <span data-ttu-id="837c7-119">Uma linha encaminhada em um heap não contém a linha de encaminhamento que deveria apontar para ela.</span><span class="sxs-lookup"><span data-stu-id="837c7-119">A forwarded row in a heap is missing the forwarding row that should point to it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="837c7-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="837c7-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="837c7-121">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="837c7-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="837c7-122">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="837c7-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="837c7-123">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="837c7-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="837c7-124">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="837c7-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="837c7-125">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="837c7-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="837c7-126">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="837c7-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="837c7-127">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="837c7-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="837c7-128">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="837c7-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="837c7-129">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="837c7-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="837c7-130">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="837c7-130">Restore from Backup</span></span>  
 <span data-ttu-id="837c7-131">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="837c7-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="837c7-132">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="837c7-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="837c7-133">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="837c7-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="837c7-134">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="837c7-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="837c7-135">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="837c7-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="837c7-136">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="837c7-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="837c7-137">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="837c7-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="837c7-138">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="837c7-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="837c7-139">A linha encaminhada será convertida em uma linha de dados comum.</span><span class="sxs-lookup"><span data-stu-id="837c7-139">The forwarded row will be converted to a regular data row.</span></span>  
  
  