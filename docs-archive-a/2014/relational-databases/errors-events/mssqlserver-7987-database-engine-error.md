---
title: MSSQLSERVER_7987 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7987 (Database Engine error)
ms.assetid: 314aebf1-6cdf-488d-a274-ce967fadb57b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2fec3cf707e2e9923084f48096a88c60655513e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680959"
---
# <a name="mssqlserver_7987"></a><span data-ttu-id="4a8f9-102">MSSQLSERVER_7987</span><span class="sxs-lookup"><span data-stu-id="4a8f9-102">MSSQLSERVER_7987</span></span>
    
## <a name="details"></a><span data-ttu-id="4a8f9-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4a8f9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4a8f9-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="4a8f9-104">Product Name</span></span>|<span data-ttu-id="4a8f9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a8f9-105">SQL Server</span></span>|  
|<span data-ttu-id="4a8f9-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="4a8f9-106">Event ID</span></span>|<span data-ttu-id="4a8f9-107">7987</span><span class="sxs-lookup"><span data-stu-id="4a8f9-107">7987</span></span>|  
|<span data-ttu-id="4a8f9-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="4a8f9-108">Event Source</span></span>|<span data-ttu-id="4a8f9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4a8f9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4a8f9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4a8f9-110">Component</span></span>|<span data-ttu-id="4a8f9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4a8f9-111">SQLEngine</span></span>|  
|<span data-ttu-id="4a8f9-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="4a8f9-112">Symbolic Name</span></span>|<span data-ttu-id="4a8f9-113">DBCC2_PRE_CHECKS_CHAIN_LINKAGE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="4a8f9-113">DBCC2_PRE_CHECKS_CHAIN_LINKAGE_MISMATCH</span></span>|  
|<span data-ttu-id="4a8f9-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="4a8f9-114">Message Text</span></span>|<span data-ttu-id="4a8f9-115">Verificações prévias de tabela do sistema: A ID do objeto O_ID tem incompatibilidade de vínculos de cadeia.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-115">System table pre-checks: Object ID O_ID has chain linkage mismatch.</span></span> <span data-ttu-id="4a8f9-116">P_ID1 ->next = P_ID2, mas P_ID2 ->prev = P_ID3.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-116">P_ID1->next = P_ID2, but P_ID2->prev = P_ID3.</span></span> <span data-ttu-id="4a8f9-117">Instrução de verificação encerrada devido a um erro irreparável.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4a8f9-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="4a8f9-118">Explanation</span></span>  
 <span data-ttu-id="4a8f9-119">A primeira fase de um DBCC CHECKDB envolve a execução de verificações primitivas nas páginas de dados das tabelas de sistema críticas.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="4a8f9-120">Se forem encontrados erros, não será possível corrigi-los; por isso, DBCC CHECKDB é encerrado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-120">If any errors are found, they cannot be repaired; therefore, the DBCC CHECKDB terminates immediately.</span></span>  
  
 <span data-ttu-id="4a8f9-121">O ponteiro de próxima página da página *P_ID1* aponta para a página *P_ID2*, no entanto, o ponteiro de página anterior da página *P_ID2* aponta para a página *P_ID3*, mas não retorna para a página *P_ID1* como deveria.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-121">The next page pointer of page *P_ID1* points to page *P_ID2*; however, the previous page pointer of page *P_ID2* points to page *P_ID3* but not back to page *P_ID1*, as it should.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4a8f9-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="4a8f9-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="4a8f9-123">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="4a8f9-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="4a8f9-124">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="4a8f9-125">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="4a8f9-126">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4a8f9-127">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="4a8f9-128">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="4a8f9-129">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="4a8f9-130">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="4a8f9-131">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="4a8f9-132">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="4a8f9-132">Restore from Backup</span></span>  
 <span data-ttu-id="4a8f9-133">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="4a8f9-134">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="4a8f9-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="4a8f9-135">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-135">Not applicable.</span></span> <span data-ttu-id="4a8f9-136">Não é possível corrigir esse erro automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4a8f9-136">This error cannot be repaired automatically.</span></span> <span data-ttu-id="4a8f9-137">Se você não conseguir restaurar o banco de dados a partir de um backup, entre em contato com o Suporte e Atendimento ao Cliente [!INCLUDE[msCoName](../../includes/msconame-md.md)] (CSS).</span><span class="sxs-lookup"><span data-stu-id="4a8f9-137">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
