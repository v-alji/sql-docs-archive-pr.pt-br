---
title: MSSQLSERVER_2576 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2576 (Database Engine error)
ms.assetid: b727cc2f-c76c-46f8-bbbe-5e7a05a6eabf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f378051c7844bf08d617db56666d69b22ecf732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572087"
---
# <a name="mssqlserver_2576"></a><span data-ttu-id="643eb-102">MSSQLSERVER_2576</span><span class="sxs-lookup"><span data-stu-id="643eb-102">MSSQLSERVER_2576</span></span>
    
## <a name="details"></a><span data-ttu-id="643eb-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="643eb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="643eb-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="643eb-104">Product Name</span></span>|<span data-ttu-id="643eb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="643eb-105">SQL Server</span></span>|  
|<span data-ttu-id="643eb-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="643eb-106">Event ID</span></span>|<span data-ttu-id="643eb-107">2576</span><span class="sxs-lookup"><span data-stu-id="643eb-107">2576</span></span>|  
|<span data-ttu-id="643eb-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="643eb-108">Event Source</span></span>|<span data-ttu-id="643eb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="643eb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="643eb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="643eb-110">Component</span></span>|<span data-ttu-id="643eb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="643eb-111">SQLEngine</span></span>|  
|<span data-ttu-id="643eb-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="643eb-112">Symbolic Name</span></span>|<span data-ttu-id="643eb-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="643eb-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="643eb-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="643eb-114">Message Text</span></span>|<span data-ttu-id="643eb-115">A página IAM P_ID1 é apontada pelo ponteiro anterior da página IAM P_ID2 na ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE), mas não foi detectada na varredura.</span><span class="sxs-lookup"><span data-stu-id="643eb-115">The Index Allocation Map (IAM) page P_ID1 is pointed to by the previous pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="643eb-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="643eb-116">Explanation</span></span>  
 <span data-ttu-id="643eb-117">Uma página IAM ou entrada de metadados não foi localizada, ainda que exista uma referência à página como o link de página anterior em outra página IAM de uma cadeia IAM.</span><span class="sxs-lookup"><span data-stu-id="643eb-117">An Index Allocation Map (IAM) page or metadata entry was not located, even though a reference to the page exists as the previous page link on another IAM page in an IAM chain.</span></span> <span data-ttu-id="643eb-118">Se a página *P_ID1* for (0:0), a página IAM, *P_ID2*, corresponderá ao início de uma cadeia IAM e a entrada de metadados da cadeia IAM estará ausente.</span><span class="sxs-lookup"><span data-stu-id="643eb-118">If the *P_ID1* page is (0:0), the IAM page, *P_ID2*, is the start of an IAM chain, and the metadata entry for the IAM chain is missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="643eb-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="643eb-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="643eb-120">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="643eb-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="643eb-121">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="643eb-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="643eb-122">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="643eb-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="643eb-123">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="643eb-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="643eb-124">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="643eb-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="643eb-125">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="643eb-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="643eb-126">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="643eb-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="643eb-127">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="643eb-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="643eb-128">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="643eb-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="643eb-129">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="643eb-129">Restore from Backup</span></span>  
 <span data-ttu-id="643eb-130">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="643eb-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="643eb-131">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="643eb-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="643eb-132">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="643eb-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="643eb-133">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="643eb-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="643eb-134">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="643eb-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="643eb-135">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="643eb-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="643eb-136">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="643eb-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="643eb-137">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="643eb-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="643eb-138">REPAIR tentará recompilar a cadeia IAM que envolve a página *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="643eb-138">REPAIR will try to rebuild the IAM chain involving the *P_ID2* page.</span></span> <span data-ttu-id="643eb-139">A reconstrução da cadeia pode envolver a remoção de páginas ou a remoção da cadeia inteira caso os metadados estejam corrompidos.</span><span class="sxs-lookup"><span data-stu-id="643eb-139">Rebuilding the chain may involve removing pages from the chain, or removing the whole chain if the metadata is corrupted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="643eb-140">Essa correção pode causar perda de dados.</span><span class="sxs-lookup"><span data-stu-id="643eb-140">This repair may cause data loss.</span></span>  
  
  
