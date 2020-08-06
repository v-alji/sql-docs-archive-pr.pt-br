---
title: MSSQLSERVER_5228 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5228 (Database Engine error)
ms.assetid: 5e83c617-4aa2-4755-bcc5-a798c46b97e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eef59e62f00a44aad7bfefb1719a6d8d2b3d0290
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569524"
---
# <a name="mssqlserver_5228"></a><span data-ttu-id="4de5f-102">MSSQLSERVER_5228</span><span class="sxs-lookup"><span data-stu-id="4de5f-102">MSSQLSERVER_5228</span></span>
    
## <a name="details"></a><span data-ttu-id="4de5f-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4de5f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4de5f-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="4de5f-104">Product Name</span></span>|<span data-ttu-id="4de5f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4de5f-105">SQL Server</span></span>|  
|<span data-ttu-id="4de5f-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4de5f-106">Event ID</span></span>|<span data-ttu-id="4de5f-107">5228</span><span class="sxs-lookup"><span data-stu-id="4de5f-107">5228</span></span>|  
|<span data-ttu-id="4de5f-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="4de5f-108">Event Source</span></span>|<span data-ttu-id="4de5f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4de5f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4de5f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4de5f-110">Component</span></span>|<span data-ttu-id="4de5f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4de5f-111">SQLEngine</span></span>|  
|<span data-ttu-id="4de5f-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="4de5f-112">Symbolic Name</span></span>|<span data-ttu-id="4de5f-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span><span class="sxs-lookup"><span data-stu-id="4de5f-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span></span>|  
|<span data-ttu-id="4de5f-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="4de5f-114">Message Text</span></span>|<span data-ttu-id="4de5f-115">Erro de tabela: ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE), página PG_ID, linha R_ID.</span><span class="sxs-lookup"><span data-stu-id="4de5f-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page PG_ID, row R_ID.</span></span> <span data-ttu-id="4de5f-116">DBCC detectou limpeza incompleta de uma operação de criação de índice online.</span><span class="sxs-lookup"><span data-stu-id="4de5f-116">DBCC detected incomplete cleanup from an online index build operation.</span></span> <span data-ttu-id="4de5f-117">(O valor de coluna de antimatéria é VALUE.)</span><span class="sxs-lookup"><span data-stu-id="4de5f-117">(Antimatter column value is VALUE.)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4de5f-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="4de5f-118">Explanation</span></span>  
 <span data-ttu-id="4de5f-119">O build não concluído de um índice online foi detectada para o objeto *O_ID*, o índice *I_ID* e a partição *PN_ID*.</span><span class="sxs-lookup"><span data-stu-id="4de5f-119">An unfinished online index build was detected for object *O_ID*, index *I_ID*, and partition *PN_ID*.</span></span> <span data-ttu-id="4de5f-120">Isso é manifesto pela presença de uma coluna de antimatéria na linha *R_ID*.</span><span class="sxs-lookup"><span data-stu-id="4de5f-120">This is manifested by the presence of an antimatter column on the row *R_ID*.</span></span> <span data-ttu-id="4de5f-121">Uma coluna de antimatéria é usada para reconciliar registros de diversas origens durante a criação de um índice online.</span><span class="sxs-lookup"><span data-stu-id="4de5f-121">An antimatter column is used when reconciling records from multiple sources during an online index build.</span></span> <span data-ttu-id="4de5f-122">A mensagem de erro também indica o valor da coluna de antimatéria.</span><span class="sxs-lookup"><span data-stu-id="4de5f-122">The error message also indicates the value of the antimatter column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4de5f-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="4de5f-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="4de5f-124">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="4de5f-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="4de5f-125">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="4de5f-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="4de5f-126">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="4de5f-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="4de5f-127">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="4de5f-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4de5f-128">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="4de5f-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="4de5f-129">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="4de5f-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="4de5f-130">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="4de5f-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="4de5f-131">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="4de5f-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="4de5f-132">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="4de5f-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="4de5f-133">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="4de5f-133">Restore from Backup</span></span>  
 <span data-ttu-id="4de5f-134">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="4de5f-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="4de5f-135">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="4de5f-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="4de5f-136">Se não houver um backup limpo, execute DBCC CHECKDB sem uma cláusula REPAIR para determinar a extensão do dano.</span><span class="sxs-lookup"><span data-stu-id="4de5f-136">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="4de5f-137">DBCC CHECKDB recomendará uma cláusula REPAIR para ser usada.</span><span class="sxs-lookup"><span data-stu-id="4de5f-137">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="4de5f-138">Execute DBCC CHECKDB com a cláusula REPAIR apropriada para reparar o dano.</span><span class="sxs-lookup"><span data-stu-id="4de5f-138">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4de5f-139">Se você não tiver certeza do efeito de DBCC CHECKDB com uma cláusula REPAIR sobre seus dados, contate o provedor de suporte antes de executar essa instrução.</span><span class="sxs-lookup"><span data-stu-id="4de5f-139">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="4de5f-140">Se a execução de DBCC CHECKDB com uma das cláusulas REPAIR não corrigir o problema, contate seu provedor de suporte.</span><span class="sxs-lookup"><span data-stu-id="4de5f-140">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="4de5f-141">Resultados da execução de opções REPAIR</span><span class="sxs-lookup"><span data-stu-id="4de5f-141">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="4de5f-142">A execução de REPAIR fará com que o índice especificado e todos os seus índices dependentes sejam recriados.</span><span class="sxs-lookup"><span data-stu-id="4de5f-142">Running REPAIR will cause the specified index and all its dependent indexes to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de5f-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4de5f-143">See Also</span></span>  
 [<span data-ttu-id="4de5f-144">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4de5f-144">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
