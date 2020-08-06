---
title: MSSQLSERVER_7995 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7995 (Database Engine error)
ms.assetid: af6d6322-3cba-43d8-be97-e6ef15f8c933
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c65cf2b16c4d7a0dcf40272f8280205a111d08e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574696"
---
# <a name="mssqlserver_7995"></a><span data-ttu-id="44af7-102">MSSQLSERVER_7995</span><span class="sxs-lookup"><span data-stu-id="44af7-102">MSSQLSERVER_7995</span></span>
    
## <a name="details"></a><span data-ttu-id="44af7-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="44af7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44af7-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="44af7-104">Product Name</span></span>|<span data-ttu-id="44af7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="44af7-105">SQL Server</span></span>|  
|<span data-ttu-id="44af7-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="44af7-106">Event ID</span></span>|<span data-ttu-id="44af7-107">7995</span><span class="sxs-lookup"><span data-stu-id="44af7-107">7995</span></span>|  
|<span data-ttu-id="44af7-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="44af7-108">Event Source</span></span>|<span data-ttu-id="44af7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="44af7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="44af7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="44af7-110">Component</span></span>|<span data-ttu-id="44af7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="44af7-111">SQLEngine</span></span>|  
|<span data-ttu-id="44af7-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="44af7-112">Symbolic Name</span></span>|<span data-ttu-id="44af7-113">DBCC2_SYSTEM_CATALOGS_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="44af7-113">DBCC2_SYSTEM_CATALOGS_CORRUPT</span></span>|  
|<span data-ttu-id="44af7-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="44af7-114">Message Text</span></span>|<span data-ttu-id="44af7-115">Banco de dados 'DBNAME': erros de consistência em catálogos do sistema impedem processamento adicional de DBCC CHECKNAME.</span><span class="sxs-lookup"><span data-stu-id="44af7-115">Database 'DBNAME': consistency errors in system catalogs prevent further DBCC CHECKNAME processing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="44af7-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="44af7-116">Explanation</span></span>  
 <span data-ttu-id="44af7-117">O processo DBCC CHECKDB consiste nestas três fases:</span><span class="sxs-lookup"><span data-stu-id="44af7-117">The DBCC CHECKDB process consists of the following three stages:</span></span>  
  
1.  <span data-ttu-id="44af7-118">Verificações de alocação.</span><span class="sxs-lookup"><span data-stu-id="44af7-118">Allocation checks.</span></span> <span data-ttu-id="44af7-119">É equivalente a executar DBCC CHECKALLOC.</span><span class="sxs-lookup"><span data-stu-id="44af7-119">This is equivalent to running DBCC CHECKALLOC.</span></span>  
  
2.  <span data-ttu-id="44af7-120">Verificações de consistência de tabelas do sistema.</span><span class="sxs-lookup"><span data-stu-id="44af7-120">System tables consistency checks.</span></span> <span data-ttu-id="44af7-121">É equivalente a executar DBCC CHECKTABLE em uma pequena lista de tabelas base do sistema necessárias.</span><span class="sxs-lookup"><span data-stu-id="44af7-121">This is equivalent to running DBCC CHECKTABLE on a small list of necessary system base tables.</span></span>  
  
3.  <span data-ttu-id="44af7-122">Verificações de consistência no banco de dados completo.</span><span class="sxs-lookup"><span data-stu-id="44af7-122">Complete database consistency checks.</span></span>  
  
 <span data-ttu-id="44af7-123">MSSQLEngine_7995 é gerado na fase 2 para indicar que DBCC CHECKDB encontrou erros que não podem ser corrigidos pelo comando ou que REPAIR não foi especificado.</span><span class="sxs-lookup"><span data-stu-id="44af7-123">MSSQLEngine_7995 is raised in stage 2 to indicate that DBCC CHECKDB has found errors that the command cannot repair or that REPAIR has not been specified.</span></span> <span data-ttu-id="44af7-124">DBCC CHECKDB não pode prosseguir para a fase 3, pois as tabelas base do sistema em questão armazenam os metadados de todos os objetos do banco de dados ou porque as tabelas base do sistema estão corrompidas.</span><span class="sxs-lookup"><span data-stu-id="44af7-124">DBCC CHECKDB cannot continue with stage 3 because either the system base tables in question store the metadata for all objects in the database or the system base tables are corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44af7-125">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="44af7-125">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="44af7-126">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="44af7-126">Look for Hardware Failure</span></span>  
 <span data-ttu-id="44af7-127">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="44af7-127">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="44af7-128">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="44af7-128">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="44af7-129">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="44af7-129">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="44af7-130">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="44af7-130">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="44af7-131">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="44af7-131">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="44af7-132">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="44af7-132">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="44af7-133">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="44af7-133">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="44af7-134">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="44af7-134">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="44af7-135">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="44af7-135">Restore from Backup</span></span>  
 <span data-ttu-id="44af7-136">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="44af7-136">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="44af7-137">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="44af7-137">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="44af7-138">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="44af7-138">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="44af7-139">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="44af7-139">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="44af7-140">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="44af7-140">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="44af7-141">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="44af7-141">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="44af7-142">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="44af7-142">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="44af7-143">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="44af7-143">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="44af7-144">Examine a lista de erros para saber o que a cláusula REPAIR fará em relação a cada erro.</span><span class="sxs-lookup"><span data-stu-id="44af7-144">Examine the list of errors to see what REPAIR will do for each.</span></span>  
  
  
