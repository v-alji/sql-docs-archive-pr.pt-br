---
title: MSSQLSERVER_2574 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2574 (Database Engine error)
ms.assetid: efba507a-b5ad-4f1d-b0c8-f73b663a0562
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fd103f8c651ca968ae997ae9c3d544b41cbf3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679371"
---
# <a name="mssqlserver_2574"></a><span data-ttu-id="a8a93-102">MSSQLSERVER_2574</span><span class="sxs-lookup"><span data-stu-id="a8a93-102">MSSQLSERVER_2574</span></span>
    
## <a name="details"></a><span data-ttu-id="a8a93-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a8a93-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8a93-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a8a93-104">Product Name</span></span>|<span data-ttu-id="a8a93-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8a93-105">SQL Server</span></span>|  
|<span data-ttu-id="a8a93-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a8a93-106">Event ID</span></span>|<span data-ttu-id="a8a93-107">2574</span><span class="sxs-lookup"><span data-stu-id="a8a93-107">2574</span></span>|  
|<span data-ttu-id="a8a93-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a8a93-108">Event Source</span></span>|<span data-ttu-id="a8a93-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a8a93-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a8a93-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a8a93-110">Component</span></span>|<span data-ttu-id="a8a93-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a8a93-111">SQLEngine</span></span>|  
|<span data-ttu-id="a8a93-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a8a93-112">Symbolic Name</span></span>|<span data-ttu-id="a8a93-113">DBCC_EMPTY_INDEX_TREE_LEVEL_PAGE</span><span class="sxs-lookup"><span data-stu-id="a8a93-113">DBCC_EMPTY_INDEX_TREE_LEVEL_PAGE</span></span>|  
|<span data-ttu-id="a8a93-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a8a93-114">Message Text</span></span>|<span data-ttu-id="a8a93-115">Erro de tabela: a página P_ID está vazia na ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="a8a93-115">Table error: Page P_ID is empty in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="a8a93-116">Isso não é permitido no nível LEVEL da árvore B.</span><span class="sxs-lookup"><span data-stu-id="a8a93-116">This is not permitted at level LEVEL of the B-tree.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a8a93-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="a8a93-117">Explanation</span></span>  
 <span data-ttu-id="a8a93-118">A página de árvore B acima do nível folha do índice especificado está vazia, isto é, não tem linhas.</span><span class="sxs-lookup"><span data-stu-id="a8a93-118">A B-tree page above the leaf level of the specified index is empty, that is it has no rows.</span></span> <span data-ttu-id="a8a93-119">Esse comportamento é possível em páginas de nível folha do [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], mas nunca foi possível em níveis de árvore.</span><span class="sxs-lookup"><span data-stu-id="a8a93-119">This behavior is possible for leaf-level pages in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], but has never been possible in tree levels.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8a93-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a8a93-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a8a93-121">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="a8a93-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a8a93-122">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="a8a93-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a8a93-123">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="a8a93-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a8a93-124">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="a8a93-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a8a93-125">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="a8a93-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a8a93-126">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="a8a93-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a8a93-127">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="a8a93-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a8a93-128">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="a8a93-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a8a93-129">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="a8a93-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a8a93-130">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="a8a93-130">Restore from Backup</span></span>  
 <span data-ttu-id="a8a93-131">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="a8a93-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a8a93-132">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a8a93-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a8a93-133">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="a8a93-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="a8a93-134">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="a8a93-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="a8a93-135">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="a8a93-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="a8a93-136">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="a8a93-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="a8a93-137">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="a8a93-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="a8a93-138">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="a8a93-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="a8a93-139">O DBCC reconstruirá o índice.</span><span class="sxs-lookup"><span data-stu-id="a8a93-139">DBCC will rebuild the index.</span></span>  
  
  
