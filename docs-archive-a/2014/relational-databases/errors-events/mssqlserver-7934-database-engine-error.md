---
title: MSSQLSERVER_7934 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7934 (Database Engine error)
ms.assetid: f656bf46-e5be-4c7b-9ea4-0f2eee7441fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4879d1e8a459994704849cead8ea873e479f5869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574699"
---
# <a name="mssqlserver_7934"></a><span data-ttu-id="5c08d-102">MSSQLSERVER_7934</span><span class="sxs-lookup"><span data-stu-id="5c08d-102">MSSQLSERVER_7934</span></span>
    
## <a name="details"></a><span data-ttu-id="5c08d-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5c08d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5c08d-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="5c08d-104">Product Name</span></span>|<span data-ttu-id="5c08d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c08d-105">SQL Server</span></span>|  
|<span data-ttu-id="5c08d-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="5c08d-106">Event ID</span></span>|<span data-ttu-id="5c08d-107">7934</span><span class="sxs-lookup"><span data-stu-id="5c08d-107">7934</span></span>|  
|<span data-ttu-id="5c08d-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="5c08d-108">Event Source</span></span>|<span data-ttu-id="5c08d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5c08d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5c08d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5c08d-110">Component</span></span>|<span data-ttu-id="5c08d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5c08d-111">SQLEngine</span></span>|  
|<span data-ttu-id="5c08d-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="5c08d-112">Symbolic Name</span></span>|<span data-ttu-id="5c08d-113">DBCC2_FS_MISSING_ROWSET_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="5c08d-113">DBCC2_FS_MISSING_ROWSET_DIRECTORY</span></span>|  
|<span data-ttu-id="5c08d-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="5c08d-114">Message Text</span></span>|<span data-ttu-id="5c08d-115">Erro de tabela: ID de diretório de Filestream F_ID para a ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID não encontrada.</span><span class="sxs-lookup"><span data-stu-id="5c08d-115">Table error: The Filestream directory ID F_ID for object ID O_ID, index ID I_ID, partition ID PN_ID was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5c08d-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="5c08d-116">Explanation</span></span>  
 <span data-ttu-id="5c08d-117">Durante DBCC CHECKDB, foi encontrada uma partição; entretanto, o diretório de conjunto de linhas FILESTREAM correspondente não foi localizado no espaço de dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="5c08d-117">During DBCC CHECKDB, a partition was found; however, its corresponding FILESTREAM rowset directory in the FILESTREAM dataspace was not found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5c08d-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="5c08d-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="5c08d-119">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="5c08d-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="5c08d-120">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="5c08d-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="5c08d-121">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="5c08d-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="5c08d-122">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="5c08d-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="5c08d-123">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="5c08d-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="5c08d-124">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="5c08d-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="5c08d-125">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="5c08d-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="5c08d-126">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="5c08d-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="5c08d-127">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="5c08d-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="5c08d-128">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="5c08d-128">Restore from Backup</span></span>  
 <span data-ttu-id="5c08d-129">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="5c08d-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="5c08d-130">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="5c08d-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="5c08d-131">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="5c08d-131">Not applicable.</span></span> <span data-ttu-id="5c08d-132">Não é possível corrigir esse erro automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5c08d-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="5c08d-133">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c08d-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c08d-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5c08d-134">See Also</span></span>  
 [<span data-ttu-id="5c08d-135">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5c08d-135">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
