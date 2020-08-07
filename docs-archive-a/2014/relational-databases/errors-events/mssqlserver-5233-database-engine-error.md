---
title: MSSQLSERVER_5233 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5233 (Database Engine error)
ms.assetid: 7a855afa-2d3b-49b7-adef-197b99fc98b1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0a5e2c603652534a6d3093a01da0a926a7195954
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581835"
---
# <a name="mssqlserver_5233"></a><span data-ttu-id="d3426-102">MSSQLSERVER_5233</span><span class="sxs-lookup"><span data-stu-id="d3426-102">MSSQLSERVER_5233</span></span>
    
## <a name="details"></a><span data-ttu-id="d3426-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d3426-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d3426-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d3426-104">Product Name</span></span>|<span data-ttu-id="d3426-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3426-105">SQL Server</span></span>|  
|<span data-ttu-id="d3426-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d3426-106">Event ID</span></span>|<span data-ttu-id="d3426-107">5233</span><span class="sxs-lookup"><span data-stu-id="d3426-107">5233</span></span>|  
|<span data-ttu-id="d3426-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d3426-108">Event Source</span></span>|<span data-ttu-id="d3426-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d3426-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d3426-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d3426-110">Component</span></span>|<span data-ttu-id="d3426-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d3426-111">SQLEngine</span></span>|  
|<span data-ttu-id="d3426-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d3426-112">Symbolic Name</span></span>|<span data-ttu-id="d3426-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="d3426-113">DBCC4_INCORRECT_VALUE_IN_PAGE_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="d3426-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d3426-114">Message Text</span></span>|<span data-ttu-id="d3426-115">Erro de tabela: ID de unidade de alocação A_ID, página P_ID.</span><span class="sxs-lookup"><span data-stu-id="d3426-115">Table error: alloc unit ID A_ID, page P_ID.</span></span> <span data-ttu-id="d3426-116">Falha no teste (TEST).</span><span class="sxs-lookup"><span data-stu-id="d3426-116">The test (TEST) failed.</span></span> <span data-ttu-id="d3426-117">Os valores são VAL1 e VAL2.</span><span class="sxs-lookup"><span data-stu-id="d3426-117">The values are VAL1 and VAL2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d3426-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="d3426-118">Explanation</span></span>  
 <span data-ttu-id="d3426-119">A página *P_ID* não foi aprovada na auditoria devido a um dano no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="d3426-119">Page *P_ID* has failed auditing due to a corruption in its page header.</span></span> <span data-ttu-id="d3426-120">A cadeia de caracteres em TEST informa o teste real não aprovado.</span><span class="sxs-lookup"><span data-stu-id="d3426-120">The string in TEST gives the actual test that failed.</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="d3426-121">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="d3426-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="d3426-122">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="d3426-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="d3426-123">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="d3426-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="d3426-124">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="d3426-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="d3426-125">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="d3426-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="d3426-126">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="d3426-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="d3426-127">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="d3426-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="d3426-128">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="d3426-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="d3426-129">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="d3426-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="d3426-130">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="d3426-130">Restore from Backup</span></span>  
 <span data-ttu-id="d3426-131">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="d3426-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="d3426-132">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="d3426-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="d3426-133">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="d3426-133">Not applicable.</span></span> <span data-ttu-id="d3426-134">Esse erro não pode ser reparado.</span><span class="sxs-lookup"><span data-stu-id="d3426-134">This error cannot be repaired.</span></span> <span data-ttu-id="d3426-135">Se você não conseguir restaurar o banco de dados a partir de um backup, entre em contato com o Suporte e Atendimento ao Cliente Microsoft (CSS).</span><span class="sxs-lookup"><span data-stu-id="d3426-135">If you cannot restore the database from a backup, contact Microsoft Customer Service and Support (CSS).</span></span>  
  
  
