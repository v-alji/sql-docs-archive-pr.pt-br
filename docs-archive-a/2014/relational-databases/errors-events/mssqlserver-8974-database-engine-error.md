---
title: MSSQLSERVER_8974 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8974 (Database Engine error)
ms.assetid: 52098678-0858-4a14-ad07-37ebbafca5fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3107f5b62caf04e232532c2d2b93d5da19fb53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584145"
---
# <a name="mssqlserver_8974"></a><span data-ttu-id="777b1-102">MSSQLSERVER_8974</span><span class="sxs-lookup"><span data-stu-id="777b1-102">MSSQLSERVER_8974</span></span>
    
## <a name="details"></a><span data-ttu-id="777b1-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="777b1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="777b1-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="777b1-104">Product Name</span></span>|<span data-ttu-id="777b1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="777b1-105">SQL Server</span></span>|  
|<span data-ttu-id="777b1-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="777b1-106">Event ID</span></span>|<span data-ttu-id="777b1-107">8974</span><span class="sxs-lookup"><span data-stu-id="777b1-107">8974</span></span>|  
|<span data-ttu-id="777b1-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="777b1-108">Event Source</span></span>|<span data-ttu-id="777b1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="777b1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="777b1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="777b1-110">Component</span></span>|<span data-ttu-id="777b1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="777b1-111">SQLEngine</span></span>|  
|<span data-ttu-id="777b1-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="777b1-112">Symbolic Name</span></span>|<span data-ttu-id="777b1-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span><span class="sxs-lookup"><span data-stu-id="777b1-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span></span>|  
|<span data-ttu-id="777b1-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="777b1-114">Message Text</span></span>|<span data-ttu-id="777b1-115">Erro de tabela: ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="777b1-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="777b1-116">O nó de dados fora da linha na página P_ID1, slot S_ID1, ID de texto ID TEXT_ID é apontado pela página P_ID2, slot S_ID2 e pela página P_ID3, slot P_ID3.</span><span class="sxs-lookup"><span data-stu-id="777b1-116">The off-row data node at page P_ID1, slot S_ID1, text ID TEXT_ID is pointed to by page P_ID2, slot S_ID2 and by page P_ID3, slot P_ID3.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="777b1-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="777b1-117">Explanation</span></span>  
 <span data-ttu-id="777b1-118">Um nó de dados fora da linha tem dois registros de dados ou de índice que o listam como um nó filho.</span><span class="sxs-lookup"><span data-stu-id="777b1-118">An off-row data node has two data or index records that list it as a child node.</span></span> <span data-ttu-id="777b1-119">Um nó pode ter apenas um nó pai.</span><span class="sxs-lookup"><span data-stu-id="777b1-119">A node can have only one parent node.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="777b1-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="777b1-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="777b1-121">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="777b1-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="777b1-122">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="777b1-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="777b1-123">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="777b1-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="777b1-124">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="777b1-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="777b1-125">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="777b1-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="777b1-126">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="777b1-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="777b1-127">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="777b1-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="777b1-128">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="777b1-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="777b1-129">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="777b1-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="777b1-130">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="777b1-130">Restore from Backup</span></span>  
 <span data-ttu-id="777b1-131">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="777b1-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="777b1-132">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="777b1-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="777b1-133">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="777b1-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="777b1-134">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="777b1-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="777b1-135">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="777b1-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="777b1-136">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="777b1-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="777b1-137">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="777b1-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="777b1-138">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="777b1-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="777b1-139">O nó de dados fora da linha na página *P_ID1* será excluído e ambas as referências nas páginas *P_ID2* e *P_ID3* serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="777b1-139">The off-row data node on page *P_ID1* will be deleted and both references on pages *P_ID2* and *P_ID3* will be deleted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="777b1-140">Essa correção deve causar perda de dados.</span><span class="sxs-lookup"><span data-stu-id="777b1-140">This repair might cause data loss.</span></span>  
  
  
