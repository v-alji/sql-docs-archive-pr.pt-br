---
title: MSSQLSERVER_7933 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7933 (Database Engine error)
ms.assetid: 722bd2c6-0fb9-4838-954a-439744c6ac4b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7ff25201d56b1bf55a0ecafbba7fbc787dc2fb64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574703"
---
# <a name="mssqlserver_7933"></a><span data-ttu-id="1d4f8-102">MSSQLSERVER_7933</span><span class="sxs-lookup"><span data-stu-id="1d4f8-102">MSSQLSERVER_7933</span></span>
    
## <a name="details"></a><span data-ttu-id="1d4f8-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1d4f8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d4f8-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="1d4f8-104">Product Name</span></span>|<span data-ttu-id="1d4f8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1d4f8-105">SQL Server</span></span>|  
|<span data-ttu-id="1d4f8-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="1d4f8-106">Event ID</span></span>|<span data-ttu-id="1d4f8-107">7933</span><span class="sxs-lookup"><span data-stu-id="1d4f8-107">7933</span></span>|  
|<span data-ttu-id="1d4f8-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="1d4f8-108">Event Source</span></span>|<span data-ttu-id="1d4f8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1d4f8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1d4f8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1d4f8-110">Component</span></span>|<span data-ttu-id="1d4f8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1d4f8-111">SQLEngine</span></span>|  
|<span data-ttu-id="1d4f8-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="1d4f8-112">Symbolic Name</span></span>|<span data-ttu-id="1d4f8-113">DBCC2_FS_ORPHANED_ROWSET_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="1d4f8-113">DBCC2_FS_ORPHANED_ROWSET_DIRECTORY</span></span>|  
|<span data-ttu-id="1d4f8-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="1d4f8-114">Message Text</span></span>|<span data-ttu-id="1d4f8-115">Erro de tabela: existe uma ID de diretório de Fluxo de arquivos F_ID para uma partição, mas a partição correspondente não existe no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-115">Table error: A Filestream directory ID F_ID exists for a partition, but the corresponding partition does not exist in the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1d4f8-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="1d4f8-116">Explanation</span></span>  
 <span data-ttu-id="1d4f8-117">Durante DBCC CHECKDB, foi encontrado um diretório de conjunto de linhas no espaço de dados FILESTREAM; entretanto, a partição correspondente não foi localizada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-117">During DBCC CHECKDB, a rowset directory was found in the FILESTREAM dataspace; however, its corresponding partition is missing in the database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d4f8-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="1d4f8-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="1d4f8-119">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="1d4f8-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="1d4f8-120">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="1d4f8-121">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="1d4f8-122">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="1d4f8-123">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="1d4f8-124">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="1d4f8-125">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="1d4f8-126">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="1d4f8-127">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="1d4f8-128">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="1d4f8-128">Restore from Backup</span></span>  
 <span data-ttu-id="1d4f8-129">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="1d4f8-130">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="1d4f8-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="1d4f8-131">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-131">Not applicable.</span></span> <span data-ttu-id="1d4f8-132">Não é possível corrigir esse erro automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="1d4f8-133">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d4f8-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
