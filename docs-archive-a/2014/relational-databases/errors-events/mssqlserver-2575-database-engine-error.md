---
title: MSSQLSERVER_2575 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2575 (Database Engine error)
ms.assetid: 92dfe449-a122-4730-942b-e1d319862d20
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 461d2b57b5ace98ca624f8dc3717c98f3e9e4d67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569528"
---
# <a name="mssqlserver_2575"></a><span data-ttu-id="9f1e1-102">MSSQLSERVER_2575</span><span class="sxs-lookup"><span data-stu-id="9f1e1-102">MSSQLSERVER_2575</span></span>
    
## <a name="details"></a><span data-ttu-id="9f1e1-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9f1e1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f1e1-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="9f1e1-104">Product Name</span></span>|<span data-ttu-id="9f1e1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9f1e1-105">SQL Server</span></span>|  
|<span data-ttu-id="9f1e1-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="9f1e1-106">Event ID</span></span>|<span data-ttu-id="9f1e1-107">2575</span><span class="sxs-lookup"><span data-stu-id="9f1e1-107">2575</span></span>|  
|<span data-ttu-id="9f1e1-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="9f1e1-108">Event Source</span></span>|<span data-ttu-id="9f1e1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9f1e1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9f1e1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9f1e1-110">Component</span></span>|<span data-ttu-id="9f1e1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9f1e1-111">SQLEngine</span></span>|  
|<span data-ttu-id="9f1e1-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="9f1e1-112">Symbolic Name</span></span>|<span data-ttu-id="9f1e1-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="9f1e1-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="9f1e1-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="9f1e1-114">Message Text</span></span>|<span data-ttu-id="9f1e1-115">A página IAM P_ID1 é apontada pelo próximo ponteiro da página IAM P_ID2 na ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE), mas não foi detectada na varredura.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-115">IAM page P_ID1 is pointed to by the next pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9f1e1-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="9f1e1-116">Explanation</span></span>  
 <span data-ttu-id="9f1e1-117">Foi encontrada uma página relativa ao índice especificado, porém a página IAM do ponteiro da próxima página não foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-117">An Index Allocation Map (IAM) page was found for the specified index; however, the IAM page for its next-page pointer was not found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f1e1-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="9f1e1-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="9f1e1-119">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="9f1e1-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="9f1e1-120">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="9f1e1-121">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="9f1e1-122">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="9f1e1-123">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="9f1e1-124">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="9f1e1-125">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="9f1e1-126">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="9f1e1-127">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="9f1e1-128">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="9f1e1-128">Restore from Backup</span></span>  
 <span data-ttu-id="9f1e1-129">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="9f1e1-130">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="9f1e1-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="9f1e1-131">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-131">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="9f1e1-132">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-132">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="9f1e1-133">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-133">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9f1e1-134">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-134">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="9f1e1-135">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-135">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="9f1e1-136">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="9f1e1-136">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="9f1e1-137">O DBCC reconstruirá o índice.</span><span class="sxs-lookup"><span data-stu-id="9f1e1-137">DBCC will rebuild the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f1e1-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9f1e1-138">See Also</span></span>  
 [<span data-ttu-id="9f1e1-139">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9f1e1-139">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
