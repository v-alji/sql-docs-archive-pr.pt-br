---
title: MSSQLSERVER_7988 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7988 (Database Engine error)
ms.assetid: 29b967b8-de30-4618-99a8-8b1155e69026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 984cb03aeb5feaa230762e200304f16cd8c5df08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680425"
---
# <a name="mssqlserver_7988"></a><span data-ttu-id="72f56-102">MSSQLSERVER_7988</span><span class="sxs-lookup"><span data-stu-id="72f56-102">MSSQLSERVER_7988</span></span>
    
## <a name="details"></a><span data-ttu-id="72f56-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="72f56-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="72f56-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="72f56-104">Product Name</span></span>|<span data-ttu-id="72f56-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="72f56-105">SQL Server</span></span>|  
|<span data-ttu-id="72f56-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="72f56-106">Event ID</span></span>|<span data-ttu-id="72f56-107">7988</span><span class="sxs-lookup"><span data-stu-id="72f56-107">7988</span></span>|  
|<span data-ttu-id="72f56-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="72f56-108">Event Source</span></span>|<span data-ttu-id="72f56-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="72f56-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="72f56-110">Componente</span><span class="sxs-lookup"><span data-stu-id="72f56-110">Component</span></span>|<span data-ttu-id="72f56-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="72f56-111">SQLEngine</span></span>|  
|<span data-ttu-id="72f56-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="72f56-112">Symbolic Name</span></span>|<span data-ttu-id="72f56-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span><span class="sxs-lookup"><span data-stu-id="72f56-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span></span>|  
|<span data-ttu-id="72f56-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="72f56-114">Message Text</span></span>|<span data-ttu-id="72f56-115">Verificações prévias de tabela do sistema: ID do objeto O_ID.</span><span class="sxs-lookup"><span data-stu-id="72f56-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="72f56-116">Detectado loop na cadeia de dados em P_ID.</span><span class="sxs-lookup"><span data-stu-id="72f56-116">Loop in data chain detected at P_ID.</span></span> <span data-ttu-id="72f56-117">Instrução de verificação encerrada devido a um erro irreparável.</span><span class="sxs-lookup"><span data-stu-id="72f56-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="72f56-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="72f56-118">Explanation</span></span>  
 <span data-ttu-id="72f56-119">A primeira fase de um DBCC CHECKDB envolve a execução de verificações primitivas nas páginas de dados das tabelas de sistema críticas.</span><span class="sxs-lookup"><span data-stu-id="72f56-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="72f56-120">Se algum erro for encontrado, eles não poderão ser reparados, portanto, o DBCC CHECKDB será encerrado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="72f56-120">If any errors are found, they cannot be repaired; therefore, DBCC CHECKDB terminates immediately.</span></span> <span data-ttu-id="72f56-121">Foi detectado um loop de ligação de página na página *P_ID*.</span><span class="sxs-lookup"><span data-stu-id="72f56-121">A page linkage loop has been detected on page *P_ID*.</span></span> <span data-ttu-id="72f56-122">Esse tipo de loop ocorre quando os próximos ponteiros de uma página futuramente retornam a ela.</span><span class="sxs-lookup"><span data-stu-id="72f56-122">A page linkage loop occurs when the next page pointers from a page eventually return to the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="72f56-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="72f56-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="72f56-124">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="72f56-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="72f56-125">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="72f56-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="72f56-126">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="72f56-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="72f56-127">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="72f56-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="72f56-128">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="72f56-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="72f56-129">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="72f56-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="72f56-130">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="72f56-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="72f56-131">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="72f56-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="72f56-132">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="72f56-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="72f56-133">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="72f56-133">Restore from Backup</span></span>  
 <span data-ttu-id="72f56-134">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="72f56-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="72f56-135">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="72f56-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="72f56-136">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="72f56-136">Not applicable.</span></span> <span data-ttu-id="72f56-137">Não é possível corrigir esse erro automaticamente.</span><span class="sxs-lookup"><span data-stu-id="72f56-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="72f56-138">Se você não conseguir restaurar o banco de dados a partir de um backup, entre em contato com o Suporte e Atendimento ao Cliente [!INCLUDE[msCoName](../../includes/msconame-md.md)] (CSS).</span><span class="sxs-lookup"><span data-stu-id="72f56-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
