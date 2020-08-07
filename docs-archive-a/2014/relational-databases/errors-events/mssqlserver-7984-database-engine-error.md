---
title: MSSQLSERVER_7984 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7984 (Database Engine error)
ms.assetid: e3192f56-e4e2-41da-b132-65f1e7540b1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c7f92fe4f3751621e0cc636ffcd2d4de73b348d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576428"
---
# <a name="mssqlserver_7984"></a><span data-ttu-id="b5b41-102">MSSQLSERVER_7984</span><span class="sxs-lookup"><span data-stu-id="b5b41-102">MSSQLSERVER_7984</span></span>
    
## <a name="details"></a><span data-ttu-id="b5b41-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b5b41-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5b41-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="b5b41-104">Product Name</span></span>|<span data-ttu-id="b5b41-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b5b41-105">SQL Server</span></span>|  
|<span data-ttu-id="b5b41-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="b5b41-106">Event ID</span></span>|<span data-ttu-id="b5b41-107">7984</span><span class="sxs-lookup"><span data-stu-id="b5b41-107">7984</span></span>|  
|<span data-ttu-id="b5b41-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="b5b41-108">Event Source</span></span>|<span data-ttu-id="b5b41-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b5b41-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b5b41-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b5b41-110">Component</span></span>|<span data-ttu-id="b5b41-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b5b41-111">SQLEngine</span></span>|  
|<span data-ttu-id="b5b41-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="b5b41-112">Symbolic Name</span></span>|<span data-ttu-id="b5b41-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b5b41-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span></span>|  
|<span data-ttu-id="b5b41-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="b5b41-114">Message Text</span></span>|<span data-ttu-id="b5b41-115">Verificações prévias de tabela do sistema: ID do objeto O_ID.</span><span class="sxs-lookup"><span data-stu-id="b5b41-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="b5b41-116">A página P_ID tem um tipo PAGETYPE inesperado.</span><span class="sxs-lookup"><span data-stu-id="b5b41-116">Page P_ID has unexpected page type PAGETYPE.</span></span> <span data-ttu-id="b5b41-117">Instrução de verificação encerrada devido a um erro irreparável.</span><span class="sxs-lookup"><span data-stu-id="b5b41-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b5b41-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="b5b41-118">Explanation</span></span>  
 <span data-ttu-id="b5b41-119">Uma página com um tipo diferente de DATA_PAGE foi encontrada no nível de dados do objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="b5b41-119">A page with a type other than DATA_PAGE was found in the data level of the specified object.</span></span> <span data-ttu-id="b5b41-120">Esse erro ocorre durante a primeira fase das verificações do comando DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="b5b41-120">This error is raised during the first phase of the DBCC CHECKDB command checks.</span></span> <span data-ttu-id="b5b41-121">Nessa fase, DBCC CHECKDB executa verificações primitivas nas páginas de dados de tabelas base do sistema que são críticas.</span><span class="sxs-lookup"><span data-stu-id="b5b41-121">During this phase, DBCC CHECKDB performs primitive checks on the data pages of critical system base tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5b41-122">Se forem encontrados erros nas tabelas do sistema, não será possível corrigi-los; por isso, o comando DBCC CHECKDB é encerrado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b5b41-122">If any errors are found in the system tables, the errors cannot be repaired; therefore, the DBCC CHECKDB command ends immediately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b5b41-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="b5b41-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b5b41-124">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="b5b41-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b5b41-125">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="b5b41-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b5b41-126">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="b5b41-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b5b41-127">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="b5b41-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b5b41-128">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="b5b41-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b5b41-129">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="b5b41-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b5b41-130">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="b5b41-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b5b41-131">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="b5b41-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b5b41-132">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="b5b41-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b5b41-133">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="b5b41-133">Restore from Backup</span></span>  
 <span data-ttu-id="b5b41-134">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="b5b41-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b5b41-135">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b5b41-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b5b41-136">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="b5b41-136">Not applicable.</span></span> <span data-ttu-id="b5b41-137">Não é possível corrigir esse erro automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b5b41-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="b5b41-138">Se você não conseguir restaurar o banco de dados a partir de um backup, entre em contato com o Suporte e Atendimento ao Cliente [!INCLUDE[msCoName](../../includes/msconame-md.md)] (CSS).</span><span class="sxs-lookup"><span data-stu-id="b5b41-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
