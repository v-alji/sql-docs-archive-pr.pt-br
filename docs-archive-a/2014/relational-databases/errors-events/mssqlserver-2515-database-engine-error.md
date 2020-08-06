---
title: MSSQLSERVER_2515 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2515 (Database Engine error)
ms.assetid: af93aa29-70c9-4923-90af-aafadb20c1c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73b2d8b8ff01b97428ba6149f537d96044c6ae3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679375"
---
# <a name="mssqlserver_2515"></a><span data-ttu-id="920da-102">MSSQLSERVER_2515</span><span class="sxs-lookup"><span data-stu-id="920da-102">MSSQLSERVER_2515</span></span>
    
## <a name="details"></a><span data-ttu-id="920da-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="920da-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="920da-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="920da-104">Product Name</span></span>|<span data-ttu-id="920da-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="920da-105">SQL Server</span></span>|  
|<span data-ttu-id="920da-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="920da-106">Event ID</span></span>|<span data-ttu-id="920da-107">2515</span><span class="sxs-lookup"><span data-stu-id="920da-107">2515</span></span>|  
|<span data-ttu-id="920da-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="920da-108">Event Source</span></span>|<span data-ttu-id="920da-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="920da-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="920da-110">Componente</span><span class="sxs-lookup"><span data-stu-id="920da-110">Component</span></span>|<span data-ttu-id="920da-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="920da-111">SQLEngine</span></span>|  
|<span data-ttu-id="920da-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="920da-112">Symbolic Name</span></span>|<span data-ttu-id="920da-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span><span class="sxs-lookup"><span data-stu-id="920da-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span></span>|  
|<span data-ttu-id="920da-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="920da-114">Message Text</span></span>|<span data-ttu-id="920da-115">A página P_ID, ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID tipo TYPE foi modificada, mas não está marcada como modificada no bitmap de backup diferencial.</span><span class="sxs-lookup"><span data-stu-id="920da-115">Page P_ID, object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID type TYPE has been modified but is not marked modified in the differential backup bitmap.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="920da-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="920da-116">Explanation</span></span>  
 <span data-ttu-id="920da-117">A página especificada tem um LSN (número de sequência de log) maior do que o LSN de referência diferencial no Gerenciador de Backup do banco de dados ou o LSN de base diferencial no bloco de controle de arquivos do arquivo, dos dois o mais recente.</span><span class="sxs-lookup"><span data-stu-id="920da-117">The page specified has a log sequence number (LSN) that is higher than the differential reference LSN in the BackupManager of the database, or the differential base LSN in the file control block of the file, whichever is more recent.</span></span> <span data-ttu-id="920da-118">Porém, a página não está marcada como alterada no bitmap de backup diferencial.</span><span class="sxs-lookup"><span data-stu-id="920da-118">However, the page is not marked as changed in the differential backup bitmap.</span></span>  
  
 <span data-ttu-id="920da-119">Será relatada somente uma página por banco de dados, uma vez que essa verificação só é feita quando se sabe que o bitmap diferencial não apresenta erros.</span><span class="sxs-lookup"><span data-stu-id="920da-119">Only one page per database will be reported, because this check is only performed when the differential bitmap is known to be error free.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="920da-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="920da-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="920da-121">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="920da-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="920da-122">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="920da-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="920da-123">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="920da-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="920da-124">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="920da-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="920da-125">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="920da-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="920da-126">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="920da-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="920da-127">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="920da-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="920da-128">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="920da-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="920da-129">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="920da-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="920da-130">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="920da-130">Restore from Backup</span></span>  
 <span data-ttu-id="920da-131">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="920da-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="920da-132">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="920da-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="920da-133">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="920da-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="920da-134">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="920da-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="920da-135">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="920da-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="920da-136">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="920da-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="920da-137">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="920da-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="920da-138">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="920da-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="920da-139">A execução de REPAIR invalidará o bitmap diferencial.</span><span class="sxs-lookup"><span data-stu-id="920da-139">Running REPAIR will invalidate the differential bitmap.</span></span> <span data-ttu-id="920da-140">Não será possível executar um backup diferencial até que seja feito um backup total do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="920da-140">You cannot perform a differential backup until a full database backup is taken.</span></span> <span data-ttu-id="920da-141">O backup total do banco de dados provê uma base para a recriação do bitmap diferencial.</span><span class="sxs-lookup"><span data-stu-id="920da-141">The full database backup provides a baseline for the differential bitmap to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="920da-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="920da-142">See Also</span></span>  
 <span data-ttu-id="920da-143">[Criar um backup completo de banco de dados &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="920da-143">[Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="920da-144">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="920da-144">MSSQLSERVER_2516</span></span>](mssqlserver-2516-database-engine-error.md)  
  
  
