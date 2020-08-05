---
title: MSSQLSERVER_7905 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7905 (Database Engine error)
ms.assetid: cf19fbbb-7158-45f2-8778-8f3cad7f574a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 253bf03c1bfacccfd809cd417163eb9d54644f28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574009"
---
# <a name="mssqlserver_7905"></a><span data-ttu-id="cb286-102">MSSQLSERVER_7905</span><span class="sxs-lookup"><span data-stu-id="cb286-102">MSSQLSERVER_7905</span></span>
    
## <a name="details"></a><span data-ttu-id="cb286-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cb286-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb286-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="cb286-104">Product Name</span></span>|<span data-ttu-id="cb286-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb286-105">SQL Server</span></span>|  
|<span data-ttu-id="cb286-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="cb286-106">Event ID</span></span>|<span data-ttu-id="cb286-107">7905</span><span class="sxs-lookup"><span data-stu-id="cb286-107">7905</span></span>|  
|<span data-ttu-id="cb286-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="cb286-108">Event Source</span></span>|<span data-ttu-id="cb286-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cb286-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cb286-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cb286-110">Component</span></span>|<span data-ttu-id="cb286-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cb286-111">SQLEngine</span></span>|  
|<span data-ttu-id="cb286-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="cb286-112">Symbolic Name</span></span>|<span data-ttu-id="cb286-113">DBCC2_FS_INVALID_ROWSET_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="cb286-113">DBCC2_FS_INVALID_ROWSET_DIRECTORY</span></span>|  
|<span data-ttu-id="cb286-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="cb286-114">Message Text</span></span>|<span data-ttu-id="cb286-115">Erro de banco de dados: o diretório 'DIRECTORY' não é um diretório válido de Fluxo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="cb286-115">Database error: The directory 'DIRECTORY' is not a valid Filestream directory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cb286-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="cb286-116">Explanation</span></span>  
 <span data-ttu-id="cb286-117">O nome de um diretório de conjunto de linhas é a ID de partição, exceto para os nomes de diretório de conjunto de linhas especiais, como 'ghost'.</span><span class="sxs-lookup"><span data-stu-id="cb286-117">The name of a rowset directory is the partition ID of the partition, except for the special rowset directory names such as 'ghost'.</span></span> <span data-ttu-id="cb286-118">Se o nome de um diretório de conjunto de linhas não puder ser convertido em uma ID de partição, o diretório não será um diretório de conjunto de linhas válido.</span><span class="sxs-lookup"><span data-stu-id="cb286-118">If a rowset directory name cannot be converted to a partition ID, the directory is not a valid rowset directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cb286-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="cb286-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="cb286-120">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="cb286-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="cb286-121">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="cb286-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="cb286-122">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="cb286-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="cb286-123">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="cb286-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="cb286-124">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="cb286-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="cb286-125">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="cb286-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="cb286-126">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="cb286-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="cb286-127">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="cb286-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="cb286-128">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="cb286-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="cb286-129">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="cb286-129">Restore from Backup</span></span>  
 <span data-ttu-id="cb286-130">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="cb286-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="cb286-131">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="cb286-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="cb286-132">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="cb286-132">Not applicable.</span></span> <span data-ttu-id="cb286-133">Esse erro não pode ser reparado.</span><span class="sxs-lookup"><span data-stu-id="cb286-133">This error cannot be repaired.</span></span> <span data-ttu-id="cb286-134">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb286-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
