---
title: MSSQLSERVER_2534 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2534 (Database Engine error)
ms.assetid: 121cf99d-0722-494c-be24-3369c1a0badc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 409c429f961cd8357bfa2e40663c33f3c1f2e36d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581868"
---
# <a name="mssqlserver_2534"></a><span data-ttu-id="67f84-102">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="67f84-102">MSSQLSERVER_2534</span></span>
    
## <a name="details"></a><span data-ttu-id="67f84-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="67f84-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67f84-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="67f84-104">Product Name</span></span>|<span data-ttu-id="67f84-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="67f84-105">SQL Server</span></span>|  
|<span data-ttu-id="67f84-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="67f84-106">Event ID</span></span>|<span data-ttu-id="67f84-107">2534</span><span class="sxs-lookup"><span data-stu-id="67f84-107">2534</span></span>|  
|<span data-ttu-id="67f84-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="67f84-108">Event Source</span></span>|<span data-ttu-id="67f84-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="67f84-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="67f84-110">Componente</span><span class="sxs-lookup"><span data-stu-id="67f84-110">Component</span></span>|<span data-ttu-id="67f84-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="67f84-111">SQLEngine</span></span>|  
|<span data-ttu-id="67f84-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="67f84-112">Symbolic Name</span></span>|<span data-ttu-id="67f84-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span><span class="sxs-lookup"><span data-stu-id="67f84-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span></span>|  
|<span data-ttu-id="67f84-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="67f84-114">Message Text</span></span>|<span data-ttu-id="67f84-115">Erro de tabela: a página P_ID, cujo cabeçalho indica que está alocada na ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE), está alocada por outro objeto.</span><span class="sxs-lookup"><span data-stu-id="67f84-115">Table error: Page P_ID, whose header indicates it as being allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), is allocated by another object.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67f84-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="67f84-116">Explanation</span></span>  
 <span data-ttu-id="67f84-117">O cabeçalho da página contém a ID de unidade de alocação *A_ID*, mas nenhuma das páginas IAM dessa unidade de alocação alocou a página.</span><span class="sxs-lookup"><span data-stu-id="67f84-117">The header of the page contains the allocation unit ID, *A_ID*, but none of the Index Allocation Map (IAM) pages of that allocation unit allocates the page.</span></span> <span data-ttu-id="67f84-118">Por isso, o cabeçalho da página contém a ID de unidade de alocação errada, e a página terá um erro de compatibilidade MSSQLServer_2533 que corresponde à ID de unidade de alocação para a qual a página está efetivamente alocada.</span><span class="sxs-lookup"><span data-stu-id="67f84-118">Therefore, the header of the page contains the wrong allocation unit ID, and the page will have a matching MSSQLServer_2533 error that corresponds to the allocation unit ID to which the page is actually allocated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67f84-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="67f84-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="67f84-120">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="67f84-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="67f84-121">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="67f84-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="67f84-122">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="67f84-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="67f84-123">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="67f84-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="67f84-124">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="67f84-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="67f84-125">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="67f84-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="67f84-126">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="67f84-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="67f84-127">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="67f84-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="67f84-128">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="67f84-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="67f84-129">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="67f84-129">Restore from Backup</span></span>  
 <span data-ttu-id="67f84-130">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="67f84-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="67f84-131">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="67f84-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="67f84-132">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="67f84-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="67f84-133">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="67f84-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="67f84-134">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="67f84-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="67f84-135">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="67f84-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="67f84-136">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="67f84-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="67f84-137">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="67f84-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="67f84-138">REPAIR reconstruirá o índice se houver um.</span><span class="sxs-lookup"><span data-stu-id="67f84-138">REPAIR will rebuild the index if an index exists.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="67f84-139">A execução de REPAIR para o erro de compatibilidade [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md) desaloca a página antes da recompilação.</span><span class="sxs-lookup"><span data-stu-id="67f84-139">Running REPAIR for the matching [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md) error deallocates the page before the rebuild.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="67f84-140">Essa correção pode causar perda de dados.</span><span class="sxs-lookup"><span data-stu-id="67f84-140">This repair may cause data loss.</span></span>  
  
  
