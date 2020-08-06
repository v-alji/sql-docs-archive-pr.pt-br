---
title: MSSQLSERVER_7932 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7932 (Database Engine error)
ms.assetid: e2ad218a-3249-4f18-8b32-09f0030765a5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 237d9be3e0f22664adb061d3bba526c9878d3bfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574709"
---
# <a name="mssqlserver_7932"></a><span data-ttu-id="d902b-102">MSSQLSERVER_7932</span><span class="sxs-lookup"><span data-stu-id="d902b-102">MSSQLSERVER_7932</span></span>
    
## <a name="details"></a><span data-ttu-id="d902b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d902b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d902b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d902b-104">Product Name</span></span>|<span data-ttu-id="d902b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d902b-105">SQL Server</span></span>|  
|<span data-ttu-id="d902b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d902b-106">Event ID</span></span>|<span data-ttu-id="d902b-107">7932</span><span class="sxs-lookup"><span data-stu-id="d902b-107">7932</span></span>|  
|<span data-ttu-id="d902b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d902b-108">Event Source</span></span>|<span data-ttu-id="d902b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d902b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d902b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d902b-110">Component</span></span>|<span data-ttu-id="d902b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d902b-111">SQLEngine</span></span>|  
|<span data-ttu-id="d902b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d902b-112">Symbolic Name</span></span>|<span data-ttu-id="d902b-113">DBCC2_FS_ROWSET_IN_WRONG_FILEGROUP</span><span class="sxs-lookup"><span data-stu-id="d902b-113">DBCC2_FS_ROWSET_IN_WRONG_FILEGROUP</span></span>|  
|<span data-ttu-id="d902b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d902b-114">Message Text</span></span>|<span data-ttu-id="d902b-115">Erro de tabela: a ID de diretório de Fluxo de arquivos F_ID da ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID está no grupo de arquivos FG_ID1, mas deveria estar no grupo de arquivos FG_ID2.</span><span class="sxs-lookup"><span data-stu-id="d902b-115">Table error: The FileStream directory ID F_ID for object ID O_ID, index ID I_ID, partition ID PN_ID is in filegroup FG_ID1, but should be in filegroup FG_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d902b-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="d902b-116">Explanation</span></span>  
 <span data-ttu-id="d902b-117">Durante DBCC CHECKDB, o armazenamento de FILESTREAM para o objeto especificado foi detectado no grupo de arquivos errado.</span><span class="sxs-lookup"><span data-stu-id="d902b-117">During DBCC CHECKDB, the FILESTREAM storage for the specified object was detected in the wrong filegroup.</span></span> <span data-ttu-id="d902b-118">Isso pode indicar que houve danos nos metadados do objeto.</span><span class="sxs-lookup"><span data-stu-id="d902b-118">This could be a corruption in the metadata of the object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d902b-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d902b-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="d902b-120">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="d902b-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="d902b-121">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="d902b-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="d902b-122">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="d902b-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="d902b-123">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="d902b-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="d902b-124">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="d902b-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="d902b-125">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="d902b-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="d902b-126">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="d902b-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="d902b-127">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="d902b-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="d902b-128">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="d902b-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="d902b-129">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="d902b-129">Restore from Backup</span></span>  
 <span data-ttu-id="d902b-130">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="d902b-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="d902b-131">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="d902b-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="d902b-132">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="d902b-132">Not applicable.</span></span> <span data-ttu-id="d902b-133">Não é possível corrigir esse erro automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d902b-133">This error cannot be repaired automatically.</span></span> <span data-ttu-id="d902b-134">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d902b-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
