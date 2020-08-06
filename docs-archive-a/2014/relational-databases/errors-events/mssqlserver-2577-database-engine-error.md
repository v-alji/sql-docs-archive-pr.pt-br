---
title: MSSQLSERVER_2577 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2577 (Database Engine error)
ms.assetid: f53256a2-2fb0-47fd-9ed9-c45389104145
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9e4b7b85f59ba721eae6b4a0ac8db1b2d288422d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581855"
---
# <a name="mssqlserver_2577"></a><span data-ttu-id="6269b-102">MSSQLSERVER_2577</span><span class="sxs-lookup"><span data-stu-id="6269b-102">MSSQLSERVER_2577</span></span>
    
## <a name="details"></a><span data-ttu-id="6269b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="6269b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6269b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="6269b-104">Product Name</span></span>|<span data-ttu-id="6269b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6269b-105">SQL Server</span></span>|  
|<span data-ttu-id="6269b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="6269b-106">Event ID</span></span>|<span data-ttu-id="6269b-107">2577</span><span class="sxs-lookup"><span data-stu-id="6269b-107">2577</span></span>|  
|<span data-ttu-id="6269b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="6269b-108">Event Source</span></span>|<span data-ttu-id="6269b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6269b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6269b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6269b-110">Component</span></span>|<span data-ttu-id="6269b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6269b-111">SQLEngine</span></span>|  
|<span data-ttu-id="6269b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="6269b-112">Symbolic Name</span></span>|<span data-ttu-id="6269b-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="6269b-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="6269b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="6269b-114">Message Text</span></span>|<span data-ttu-id="6269b-115">Os números de sequência de cadeia estão fora de ordem na cadeia de página IAM para a ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="6269b-115">Chain sequence numbers out of order in the Index Allocation Map (IAM) chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="6269b-116">A página P_ID1 com número de sequência SEQUENCE1 aponta para a página P_ID2 com número de sequência SEQUENCE2.</span><span class="sxs-lookup"><span data-stu-id="6269b-116">Page P_ID1 with sequence number SEQUENCE1 points to page P_ID2 with sequence number SEQUENCE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6269b-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="6269b-117">Explanation</span></span>  
 <span data-ttu-id="6269b-118">Toda página IAM tem um número de sequência.</span><span class="sxs-lookup"><span data-stu-id="6269b-118">Every Index Allocation Map (IAM) page has a sequence number.</span></span> <span data-ttu-id="6269b-119">O número de sequência é a posição da página IAM na cadeia IAM.</span><span class="sxs-lookup"><span data-stu-id="6269b-119">The sequence number is the position of the IAM page within the IAM chain.</span></span> <span data-ttu-id="6269b-120">A regra é que os números de sequência aumentam em um para cada página IAM.</span><span class="sxs-lookup"><span data-stu-id="6269b-120">The rule is that sequence numbers increase by one for each IAM page.</span></span> <span data-ttu-id="6269b-121">A página IAM, *P_ID2*, tem um número de sequência que não segue essa regra.</span><span class="sxs-lookup"><span data-stu-id="6269b-121">IAM page, *P_ID2*, has a sequence number that does not follow this rule.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6269b-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="6269b-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="6269b-123">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="6269b-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="6269b-124">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="6269b-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="6269b-125">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="6269b-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="6269b-126">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="6269b-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="6269b-127">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="6269b-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="6269b-128">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="6269b-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="6269b-129">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="6269b-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="6269b-130">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="6269b-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="6269b-131">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="6269b-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="6269b-132">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="6269b-132">Restore from Backup</span></span>  
 <span data-ttu-id="6269b-133">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="6269b-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="6269b-134">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="6269b-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="6269b-135">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="6269b-135">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="6269b-136">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="6269b-136">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="6269b-137">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="6269b-137">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="6269b-138">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="6269b-138">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="6269b-139">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="6269b-139">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="6269b-140">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="6269b-140">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="6269b-141">A execução de REPAIR reconstruirá a cadeia IAM.</span><span class="sxs-lookup"><span data-stu-id="6269b-141">Running REPAIR will rebuild the IAM chain.</span></span> <span data-ttu-id="6269b-142">Primeiro, a cláusula REPAIR divide a cadeia IAM existente em duas metades.</span><span class="sxs-lookup"><span data-stu-id="6269b-142">REPAIR first splits the existing IAM chain in two halves.</span></span> <span data-ttu-id="6269b-143">A primeira metade da cadeia terminará com uma página IAM, *P_ID1*.</span><span class="sxs-lookup"><span data-stu-id="6269b-143">The first half of the chain will end with IAM page, *P_ID1*.</span></span> <span data-ttu-id="6269b-144">O próximo ponteiro da página *P_ID1* será definido como (0:0).</span><span class="sxs-lookup"><span data-stu-id="6269b-144">The next page pointer of the *P_ID1* page will be set to (0:0).</span></span> <span data-ttu-id="6269b-145">A segunda metade da cadeia iniciará com a página IAM, *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="6269b-145">The second half of the chain will start with IAM page, *P_ID2*.</span></span> <span data-ttu-id="6269b-146">O ponteiro anterior da página *P_ID2* será definido como (0:0).</span><span class="sxs-lookup"><span data-stu-id="6269b-146">The previous page pointer of the *P_ID2* page will be set to (0:0).</span></span>  
  
 <span data-ttu-id="6269b-147">Em seguida, a cláusula REPAIR conectará as duas metades da cadeia para gerar novamente os números de sequência da cadeia IAM.</span><span class="sxs-lookup"><span data-stu-id="6269b-147">REPAIR will then connect the two haves of the chain together and regenerate the sequence numbers for the IAM chain.</span></span> <span data-ttu-id="6269b-148">Nenhuma página IAM que não puder ser corrigida será desalocada.</span><span class="sxs-lookup"><span data-stu-id="6269b-148">Any IAM pages that cannot be repaired will be deallocated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="6269b-149">Essa correção pode causar perda de dados.</span><span class="sxs-lookup"><span data-stu-id="6269b-149">This repair may cause data loss.</span></span>  
  
  
