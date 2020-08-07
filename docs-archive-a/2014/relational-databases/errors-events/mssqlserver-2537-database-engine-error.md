---
title: MSSQLSERVER_2537 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2537 (Database Engine error)
ms.assetid: 0af6ff69-d75a-4c39-8da2-9bd0695277c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c227867bac5a0ea5789ba653414444d011e5910d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581863"
---
# <a name="mssqlserver_2537"></a><span data-ttu-id="d78d4-102">MSSQLSERVER_2537</span><span class="sxs-lookup"><span data-stu-id="d78d4-102">MSSQLSERVER_2537</span></span>
    
## <a name="details"></a><span data-ttu-id="d78d4-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d78d4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d78d4-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d78d4-104">Product Name</span></span>|<span data-ttu-id="d78d4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d78d4-105">SQL Server</span></span>|  
|<span data-ttu-id="d78d4-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d78d4-106">Event ID</span></span>|<span data-ttu-id="d78d4-107">2537</span><span class="sxs-lookup"><span data-stu-id="d78d4-107">2537</span></span>|  
|<span data-ttu-id="d78d4-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d78d4-108">Event Source</span></span>|<span data-ttu-id="d78d4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d78d4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d78d4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d78d4-110">Component</span></span>|<span data-ttu-id="d78d4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d78d4-111">SQLEngine</span></span>|  
|<span data-ttu-id="d78d4-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d78d4-112">Symbolic Name</span></span>|<span data-ttu-id="d78d4-113">DBCC_RECORD_CHECK_FAILED</span><span class="sxs-lookup"><span data-stu-id="d78d4-113">DBCC_RECORD_CHECK_FAILED</span></span>|  
|<span data-ttu-id="d78d4-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d78d4-114">Message Text</span></span>|<span data-ttu-id="d78d4-115">Erro de tabela: ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE), página P_ID, linha ROW_ID.</span><span class="sxs-lookup"><span data-stu-id="d78d4-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page P_ID, row ROW_ID.</span></span> <span data-ttu-id="d78d4-116">Falha na verificação de registro (CHECK_TEXT).</span><span class="sxs-lookup"><span data-stu-id="d78d4-116">Record check (CHECK_TEXT) failed.</span></span> <span data-ttu-id="d78d4-117">Os valores são VALUE1 e VALUE2.</span><span class="sxs-lookup"><span data-stu-id="d78d4-117">Values are VALUE1 and VALUE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d78d4-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="d78d4-118">Explanation</span></span>  
 <span data-ttu-id="d78d4-119">A linha ROW_ID (ou uma coluna na linha) falhou no teste ou não atendeu à condição descrita por CHECK_TEXT.</span><span class="sxs-lookup"><span data-stu-id="d78d4-119">The row ROW_ID (or a column in the row) failed the test or condition described by CHECK_TEXT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d78d4-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d78d4-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="d78d4-121">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="d78d4-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="d78d4-122">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="d78d4-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="d78d4-123">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="d78d4-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="d78d4-124">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="d78d4-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="d78d4-125">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="d78d4-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="d78d4-126">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="d78d4-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="d78d4-127">Se você suspeitar de que a gravação em cache seja o problema, entre em contato com o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="d78d4-127">If you suspect that write-caching is the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="d78d4-128">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="d78d4-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="d78d4-129">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="d78d4-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="d78d4-130">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="d78d4-130">Restore from Backup</span></span>  
 <span data-ttu-id="d78d4-131">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="d78d4-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="d78d4-132">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="d78d4-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="d78d4-133">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="d78d4-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="d78d4-134">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="d78d4-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="d78d4-135">Em seguida, execute DBCC CHECKDB com a cláusula REPAIR recomendada.</span><span class="sxs-lookup"><span data-stu-id="d78d4-135">Then, run DBCC CHECKDB with the recommended REPAIR clause.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="d78d4-136">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="d78d4-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="d78d4-137">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="d78d4-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="d78d4-138">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="d78d4-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="d78d4-139">REPAIR reconstruirá o índice se houver um.</span><span class="sxs-lookup"><span data-stu-id="d78d4-139">REPAIR will rebuild the index if an index exists.</span></span>  
  
 <span data-ttu-id="d78d4-140">**Cuidado** Esse reparo pode ocasionar perda de dados.</span><span class="sxs-lookup"><span data-stu-id="d78d4-140">**Caution** This repair may cause data loss.</span></span>  
  
  
