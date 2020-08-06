---
title: MSSQLSERVER_5256 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5256 (Database Engine error)
ms.assetid: 6fe254b4-2926-446f-8b20-0f1d921a4615
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9146b7744e78550463cbec4c05df5fd75a049898
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681658"
---
# <a name="mssqlserver_5256"></a><span data-ttu-id="9d066-102">MSSQLSERVER_5256</span><span class="sxs-lookup"><span data-stu-id="9d066-102">MSSQLSERVER_5256</span></span>
    
## <a name="details"></a><span data-ttu-id="9d066-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9d066-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d066-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="9d066-104">Product Name</span></span>|<span data-ttu-id="9d066-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9d066-105">SQL Server</span></span>|  
|<span data-ttu-id="9d066-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="9d066-106">Event ID</span></span>|<span data-ttu-id="9d066-107">5256</span><span class="sxs-lookup"><span data-stu-id="9d066-107">5256</span></span>|  
|<span data-ttu-id="9d066-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="9d066-108">Event Source</span></span>|<span data-ttu-id="9d066-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9d066-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9d066-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9d066-110">Component</span></span>|<span data-ttu-id="9d066-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9d066-111">SQLEngine</span></span>|  
|<span data-ttu-id="9d066-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="9d066-112">Symbolic Name</span></span>|<span data-ttu-id="9d066-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="9d066-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="9d066-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="9d066-114">Message Text</span></span>|<span data-ttu-id="9d066-115">Erro de tabela: ID de unidade de alocação A_ID, página P_ID1 contém uma ID de página incorreta no cabeçalho da página.</span><span class="sxs-lookup"><span data-stu-id="9d066-115">Table error: alloc unit ID A_ID, page P_ID1 contains an incorrect page ID in its page header.</span></span> <span data-ttu-id="9d066-116">PageId no cabeçalho da página = P_ID2.</span><span class="sxs-lookup"><span data-stu-id="9d066-116">The PageId in the page header = P_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9d066-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="9d066-117">Explanation</span></span>  
 <span data-ttu-id="9d066-118">O cabeçalho da página *P_ID1* contém uma ID de página incorreta, *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="9d066-118">The page header of page *P_ID1* contains an incorrect page ID, *P_ID2*.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9d066-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="9d066-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="9d066-120">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="9d066-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="9d066-121">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="9d066-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="9d066-122">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="9d066-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="9d066-123">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="9d066-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="9d066-124">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="9d066-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="9d066-125">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="9d066-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="9d066-126">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="9d066-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="9d066-127">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="9d066-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="9d066-128">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9d066-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="9d066-129">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="9d066-129">Restore from Backup</span></span>  
 <span data-ttu-id="9d066-130">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="9d066-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="9d066-131">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="9d066-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="9d066-132">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="9d066-132">Not applicable.</span></span> <span data-ttu-id="9d066-133">Esse erro não pode ser reparado.</span><span class="sxs-lookup"><span data-stu-id="9d066-133">This error cannot be repaired.</span></span> <span data-ttu-id="9d066-134">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d066-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
