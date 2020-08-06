---
title: MSSQLSERVER_2579 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2579 (Database Engine error)
ms.assetid: 8f929d69-8eb4-4fe9-be52-b9680a7820db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e68cd090ff9d20b14b3456dcda66496fc2bc02d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581851"
---
# <a name="mssqlserver_2579"></a><span data-ttu-id="c3b2a-102">MSSQLSERVER_2579</span><span class="sxs-lookup"><span data-stu-id="c3b2a-102">MSSQLSERVER_2579</span></span>
    
## <a name="details"></a><span data-ttu-id="c3b2a-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c3b2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3b2a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="c3b2a-104">Product Name</span></span>|<span data-ttu-id="c3b2a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c3b2a-105">SQL Server</span></span>|  
|<span data-ttu-id="c3b2a-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="c3b2a-106">Event ID</span></span>|<span data-ttu-id="c3b2a-107">2579</span><span class="sxs-lookup"><span data-stu-id="c3b2a-107">2579</span></span>|  
|<span data-ttu-id="c3b2a-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="c3b2a-108">Event Source</span></span>|<span data-ttu-id="c3b2a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c3b2a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c3b2a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c3b2a-110">Component</span></span>|<span data-ttu-id="c3b2a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c3b2a-111">SQLEngine</span></span>|  
|<span data-ttu-id="c3b2a-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="c3b2a-112">Symbolic Name</span></span>|<span data-ttu-id="c3b2a-113">DBCC_EXTENT_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="c3b2a-113">DBCC_EXTENT_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="c3b2a-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="c3b2a-114">Message Text</span></span>|<span data-ttu-id="c3b2a-115">Erro de tabela: A extensão P_ID da ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE) ultrapassa o intervalo deste banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-115">Table error: Extent P_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) is beyond the range of this database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c3b2a-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="c3b2a-116">Explanation</span></span>  
 <span data-ttu-id="c3b2a-117">*P_ID* é uma PageID no formato *(filenum:pageinfile)* .</span><span class="sxs-lookup"><span data-stu-id="c3b2a-117">*P_ID* is a PageID of the form *(filenum:pageinfile)*.</span></span> <span data-ttu-id="c3b2a-118">O componente *pageinfile* dessa extensão é maior que o tamanho físico do arquivo (*filenum)* do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-118">The *pageinfile* of this extent is greater than the physical size of the file (*filenum)* of the database.</span></span> <span data-ttu-id="c3b2a-119">A extensão é marcada como estando alocada em uma página IAM para a ID de unidade de alocação indicada.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-119">The extent is marked as being allocated in an IAM page for the indicated allocation unit ID.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c3b2a-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="c3b2a-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="c3b2a-121">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="c3b2a-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="c3b2a-122">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="c3b2a-123">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="c3b2a-124">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="c3b2a-125">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="c3b2a-126">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="c3b2a-127">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="c3b2a-128">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="c3b2a-129">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="c3b2a-130">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="c3b2a-130">Restore from Backup</span></span>  
 <span data-ttu-id="c3b2a-131">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="c3b2a-132">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="c3b2a-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="c3b2a-133">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="c3b2a-134">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="c3b2a-135">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="c3b2a-136">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="c3b2a-137">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="c3b2a-138">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="c3b2a-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="c3b2a-139">A execução de REPAIR fará com que a extensão seja desalocada da página IAM.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-139">Running REPAIR will cause the extent to be deallocated from the IAM page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="c3b2a-140">Essa correção pode causar perda de dados.</span><span class="sxs-lookup"><span data-stu-id="c3b2a-140">This repair may cause data loss.</span></span>  
  
  
