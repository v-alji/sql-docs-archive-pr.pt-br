---
title: MSSQLSERVER_2533 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2533 (Database Engine error)
ms.assetid: 0418352c-0ab2-4dc7-b8b9-5c3bad94560c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1eb3e2780693a3a0ffed21ce7b9d7887615536c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680431"
---
# <a name="mssqlserver_2533"></a><span data-ttu-id="36330-102">MSSQLSERVER_2533</span><span class="sxs-lookup"><span data-stu-id="36330-102">MSSQLSERVER_2533</span></span>
    
## <a name="details"></a><span data-ttu-id="36330-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="36330-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="36330-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="36330-104">Product Name</span></span>|<span data-ttu-id="36330-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="36330-105">SQL Server</span></span>|  
|<span data-ttu-id="36330-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="36330-106">Event ID</span></span>|<span data-ttu-id="36330-107">2533</span><span class="sxs-lookup"><span data-stu-id="36330-107">2533</span></span>|  
|<span data-ttu-id="36330-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="36330-108">Event Source</span></span>|<span data-ttu-id="36330-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="36330-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="36330-110">Componente</span><span class="sxs-lookup"><span data-stu-id="36330-110">Component</span></span>|<span data-ttu-id="36330-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="36330-111">SQLEngine</span></span>|  
|<span data-ttu-id="36330-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="36330-112">Symbolic Name</span></span>|<span data-ttu-id="36330-113">DBCC_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="36330-113">DBCC_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="36330-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="36330-114">Message Text</span></span>|<span data-ttu-id="36330-115">Erro de tabela: a página P_ID alocada à ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE) não foi vista.</span><span class="sxs-lookup"><span data-stu-id="36330-115">Table error: Page P_ID allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) was not seen.</span></span> <span data-ttu-id="36330-116">A página pode ser inválida ou ter uma ID de unidade de alocação incorreta em seu cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="36330-116">Page may be invalid or have incorrect alloc unit ID in its header.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="36330-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="36330-117">Explanation</span></span>  
 <span data-ttu-id="36330-118">Uma página é alocada para a ID de unidade de alocação, *A_ID*, mas essa ID não está no cabeçalho da página.</span><span class="sxs-lookup"><span data-stu-id="36330-118">A page is allocated to the allocation unit ID, *A_ID*, but this allocation unit ID is not in the header of the page.</span></span> <span data-ttu-id="36330-119">O cabeçalho tem outra ID de unidade de alocação.</span><span class="sxs-lookup"><span data-stu-id="36330-119">The header has a different allocation unit ID.</span></span> <span data-ttu-id="36330-120">Se a ID de unidade de alocação contida no cabeçalho da página for de um objeto válido, talvez a página tenha um erro de incompatibilidade MSSQLEngine_2534.</span><span class="sxs-lookup"><span data-stu-id="36330-120">If the allocation unit ID in the header of the page is for a valid object, the page may have a matching MSSQLEngine_2534 error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="36330-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="36330-121">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="36330-122">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="36330-122">Look for Hardware Failure</span></span>  
 <span data-ttu-id="36330-123">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="36330-123">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="36330-124">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="36330-124">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="36330-125">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="36330-125">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="36330-126">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="36330-126">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="36330-127">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="36330-127">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="36330-128">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="36330-128">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="36330-129">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="36330-129">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="36330-130">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="36330-130">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="36330-131">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="36330-131">Restore from Backup</span></span>  
 <span data-ttu-id="36330-132">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="36330-132">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="36330-133">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="36330-133">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="36330-134">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="36330-134">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="36330-135">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="36330-135">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="36330-136">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="36330-136">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="36330-137">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="36330-137">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="36330-138">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="36330-138">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="36330-139">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="36330-139">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="36330-140">REPAIR desalocará a página.</span><span class="sxs-lookup"><span data-stu-id="36330-140">REPAIR will deallocate the page.</span></span> <span data-ttu-id="36330-141">Se a página for de uma unidade de alocação de dados na linha, o índice, se houver, será recriado.</span><span class="sxs-lookup"><span data-stu-id="36330-141">If the page was from an in-row data allocation unit, the index, if one exists, will be rebuilt.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="36330-142">Essa correção pode causar perda de dados.</span><span class="sxs-lookup"><span data-stu-id="36330-142">This repair may cause data loss.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36330-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="36330-143">See Also</span></span>  
 [<span data-ttu-id="36330-144">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="36330-144">MSSQLSERVER_2534</span></span>](mssqlserver-2534-database-engine-error.md)  
  
  
