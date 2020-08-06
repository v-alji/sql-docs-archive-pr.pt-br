---
title: MSSQLSERVER_8996 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8996 (Database Engine error)
ms.assetid: 4e655cdc-945a-4a18-95dd-75f050563d26
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d0cb5f0294ea471a6e300adbabc0f7b55632994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581824"
---
# <a name="mssqlserver_8996"></a><span data-ttu-id="e4582-102">MSSQLSERVER_8996</span><span class="sxs-lookup"><span data-stu-id="e4582-102">MSSQLSERVER_8996</span></span>
    
## <a name="details"></a><span data-ttu-id="e4582-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e4582-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e4582-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="e4582-104">Product Name</span></span>|<span data-ttu-id="e4582-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4582-105">SQL Server</span></span>|  
|<span data-ttu-id="e4582-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e4582-106">Event ID</span></span>|<span data-ttu-id="e4582-107">8996</span><span class="sxs-lookup"><span data-stu-id="e4582-107">8996</span></span>|  
|<span data-ttu-id="e4582-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="e4582-108">Event Source</span></span>|<span data-ttu-id="e4582-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e4582-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e4582-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e4582-110">Component</span></span>|<span data-ttu-id="e4582-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e4582-111">SQLEngine</span></span>|  
|<span data-ttu-id="e4582-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="e4582-112">Symbolic Name</span></span>|<span data-ttu-id="e4582-113">DBCC3_IAM_PAGE_RANGE_IN_WRONG_FILEGROUP</span><span class="sxs-lookup"><span data-stu-id="e4582-113">DBCC3_IAM_PAGE_RANGE_IN_WRONG_FILEGROUP</span></span>|  
|<span data-ttu-id="e4582-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="e4582-114">Message Text</span></span>|<span data-ttu-id="e4582-115">Página IAM P_ID da ID do objeto O_ID, ID do índice I_ID, ID da partição PN_ID, ID da unidade de alocação A_ID (tipo TYPE), páginas de controles do grupo de arquivos FG_ID1 que deveriam estar no grupo de arquivos FG_ID2.</span><span class="sxs-lookup"><span data-stu-id="e4582-115">IAM page P_ID for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) controls pages in filegroup FG_ID1, that should be in filegroup FG_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e4582-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="e4582-116">Explanation</span></span>  
 <span data-ttu-id="e4582-117">A página IAM (mapa de alocação de índice) *P_ID* no grupo de arquivos *FG_ID1* inclui extensões do grupo de arquivos *FG_ID2* incorretamente.</span><span class="sxs-lookup"><span data-stu-id="e4582-117">The index allocation map (IAM) page *P_ID* in filegroup *FG_ID1* incorrectly includes extents from filegroup *FG_ID2*.</span></span> <span data-ttu-id="e4582-118">Todas as extensões de uma página IAM deveriam estar no mesmo grupo de arquivos que a página IAM propriamente dita.</span><span class="sxs-lookup"><span data-stu-id="e4582-118">All extents for an IAM page should be in the same filegroup as the IAM page itself.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e4582-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="e4582-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="e4582-120">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="e4582-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="e4582-121">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="e4582-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="e4582-122">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="e4582-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="e4582-123">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="e4582-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="e4582-124">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="e4582-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="e4582-125">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="e4582-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="e4582-126">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="e4582-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="e4582-127">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="e4582-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="e4582-128">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e4582-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="e4582-129">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="e4582-129">Restore from Backup</span></span>  
 <span data-ttu-id="e4582-130">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="e4582-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="e4582-131">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="e4582-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="e4582-132">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="e4582-132">Not applicable.</span></span> <span data-ttu-id="e4582-133">Esse erro não pode ser reparado.</span><span class="sxs-lookup"><span data-stu-id="e4582-133">This error cannot be repaired.</span></span> <span data-ttu-id="e4582-134">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4582-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
