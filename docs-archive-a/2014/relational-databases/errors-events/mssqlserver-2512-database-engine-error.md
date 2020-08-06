---
title: MSSQLSERVER_2512 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2512 (Database Engine error)
ms.assetid: 989b527f-5b02-403c-9b7f-51580f4e7688
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da121c8b49ab8290c494d33f0f2a0ba6fded9e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679972"
---
# <a name="mssqlserver_2512"></a><span data-ttu-id="a511f-102">MSSQLSERVER_2512</span><span class="sxs-lookup"><span data-stu-id="a511f-102">MSSQLSERVER_2512</span></span>
    
## <a name="details"></a><span data-ttu-id="a511f-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a511f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a511f-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a511f-104">Product Name</span></span>|<span data-ttu-id="a511f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a511f-105">SQL Server</span></span>|  
|<span data-ttu-id="a511f-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a511f-106">Event ID</span></span>|<span data-ttu-id="a511f-107">2512</span><span class="sxs-lookup"><span data-stu-id="a511f-107">2512</span></span>|  
|<span data-ttu-id="a511f-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a511f-108">Event Source</span></span>|<span data-ttu-id="a511f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a511f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a511f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a511f-110">Component</span></span>|<span data-ttu-id="a511f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a511f-111">SQLEngine</span></span>|  
|<span data-ttu-id="a511f-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a511f-112">Symbolic Name</span></span>|<span data-ttu-id="a511f-113">DBCC_DUPLICATE_KEYS</span><span class="sxs-lookup"><span data-stu-id="a511f-113">DBCC_DUPLICATE_KEYS</span></span>|  
|<span data-ttu-id="a511f-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a511f-114">Message Text</span></span>|<span data-ttu-id="a511f-115">Erro de tabela: ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="a511f-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="a511f-116">Chaves duplicadas na página P_ID1 slot SLOT1 e na página P_ID2 slot SLOT2.</span><span class="sxs-lookup"><span data-stu-id="a511f-116">Duplicate keys on page P_ID1 slot SLOT1 and page P_ID2 slot SLOT2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a511f-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="a511f-117">Explanation</span></span>  
 <span data-ttu-id="a511f-118">Os dois slots especificados têm chaves idênticas, inclusive `uniqueifiers`.</span><span class="sxs-lookup"><span data-stu-id="a511f-118">The two specified slots have identical keys, including any `uniqueifiers`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a511f-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a511f-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a511f-120">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="a511f-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a511f-121">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="a511f-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a511f-122">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="a511f-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a511f-123">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="a511f-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a511f-124">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="a511f-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a511f-125">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="a511f-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a511f-126">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="a511f-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a511f-127">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="a511f-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a511f-128">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="a511f-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a511f-129">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="a511f-129">Restore from Backup</span></span>  
 <span data-ttu-id="a511f-130">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="a511f-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a511f-131">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a511f-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a511f-132">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="a511f-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="a511f-133">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="a511f-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="a511f-134">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="a511f-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="a511f-135">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="a511f-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="a511f-136">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="a511f-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="a511f-137">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="a511f-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="a511f-138">Se o registro for fantasma ou se o índice não for exclusivo, DBCC poderá corrigir o problema por meio da reconstrução do índice.</span><span class="sxs-lookup"><span data-stu-id="a511f-138">If either record is a ghost or the index is nonunique, DBCC can repair this problem by rebuilding the index.</span></span> <span data-ttu-id="a511f-139">Caso contrário, se necessário, REPAIR excluirá o slot *SLOT2* da página *P_ID2* ou o marcará como duplicado.</span><span class="sxs-lookup"><span data-stu-id="a511f-139">Otherwise, if necessary, REPAIR will delete slot *SLOT2* on page *P_ID2* or mark the slot as a ghost.</span></span>  
  
  
