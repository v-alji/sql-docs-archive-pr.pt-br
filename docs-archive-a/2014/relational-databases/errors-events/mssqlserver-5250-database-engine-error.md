---
title: MSSQLSERVER_5250 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5250 (Database Engine error)
ms.assetid: f4a1d0e8-f27f-4cb8-a25d-040b40555dcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace26b88aca5b00c23aff3fe48f7c1d04ef35245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681660"
---
# <a name="mssqlserver_5250"></a><span data-ttu-id="20bb6-102">MSSQLSERVER_5250</span><span class="sxs-lookup"><span data-stu-id="20bb6-102">MSSQLSERVER_5250</span></span>
    
## <a name="details"></a><span data-ttu-id="20bb6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="20bb6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="20bb6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="20bb6-104">Product Name</span></span>|<span data-ttu-id="20bb6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="20bb6-105">SQL Server</span></span>|  
|<span data-ttu-id="20bb6-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="20bb6-106">Event ID</span></span>|<span data-ttu-id="20bb6-107">5250</span><span class="sxs-lookup"><span data-stu-id="20bb6-107">5250</span></span>|  
|<span data-ttu-id="20bb6-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="20bb6-108">Event Source</span></span>|<span data-ttu-id="20bb6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="20bb6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="20bb6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="20bb6-110">Component</span></span>|<span data-ttu-id="20bb6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="20bb6-111">SQLEngine</span></span>|  
|<span data-ttu-id="20bb6-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="20bb6-112">Symbolic Name</span></span>|<span data-ttu-id="20bb6-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="20bb6-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span></span>|  
|<span data-ttu-id="20bb6-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="20bb6-114">Message Text</span></span>|<span data-ttu-id="20bb6-115">Erro de banco de dados: a página PAGE_TYPE P_ID do banco de dados 'NAME' (ID de banco de dados DB_ID) é inválida.</span><span class="sxs-lookup"><span data-stu-id="20bb6-115">Database error: PAGE_TYPE page P_ID for database 'NAME' (database ID DB_ID) is invalid.</span></span> <span data-ttu-id="20bb6-116">Esse erro não pode ser reparado.</span><span class="sxs-lookup"><span data-stu-id="20bb6-116">This error cannot be repaired.</span></span> <span data-ttu-id="20bb6-117">É preciso restaurar a partir do backup.</span><span class="sxs-lookup"><span data-stu-id="20bb6-117">You must restore from backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="20bb6-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="20bb6-118">Explanation</span></span>  
 <span data-ttu-id="20bb6-119">Uma página de cabeçalho de arquivo ou uma página de inicialização no banco de dados especificado está corrompida.</span><span class="sxs-lookup"><span data-stu-id="20bb6-119">A file header page or boot page in the specified database is corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="20bb6-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="20bb6-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="20bb6-121">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="20bb6-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="20bb6-122">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="20bb6-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="20bb6-123">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="20bb6-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="20bb6-124">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="20bb6-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="20bb6-125">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="20bb6-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="20bb6-126">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="20bb6-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="20bb6-127">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="20bb6-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="20bb6-128">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="20bb6-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="20bb6-129">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="20bb6-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="20bb6-130">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="20bb6-130">Restore from Backup</span></span>  
 <span data-ttu-id="20bb6-131">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="20bb6-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="20bb6-132">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="20bb6-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="20bb6-133">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="20bb6-133">Not applicable.</span></span> <span data-ttu-id="20bb6-134">Esse erro não pode ser reparado.</span><span class="sxs-lookup"><span data-stu-id="20bb6-134">This error cannot be repaired.</span></span> <span data-ttu-id="20bb6-135">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20bb6-135">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
