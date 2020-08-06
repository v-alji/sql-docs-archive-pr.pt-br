---
title: MSSQLSERVER_2522 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2522 (Database Engine error)
ms.assetid: 19b9b00c-330f-4dd3-9052-9d88bce83849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60446c21599c02ee9c4bc96789b106b49b71582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569531"
---
# <a name="mssqlserver_2522"></a><span data-ttu-id="92316-102">MSSQLSERVER_2522</span><span class="sxs-lookup"><span data-stu-id="92316-102">MSSQLSERVER_2522</span></span>
    
## <a name="details"></a><span data-ttu-id="92316-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="92316-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="92316-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="92316-104">Product Name</span></span>|<span data-ttu-id="92316-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="92316-105">SQL Server</span></span>|  
|<span data-ttu-id="92316-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="92316-106">Event ID</span></span>|<span data-ttu-id="92316-107">2522</span><span class="sxs-lookup"><span data-stu-id="92316-107">2522</span></span>|  
|<span data-ttu-id="92316-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="92316-108">Event Source</span></span>|<span data-ttu-id="92316-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="92316-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="92316-110">Componente</span><span class="sxs-lookup"><span data-stu-id="92316-110">Component</span></span>|<span data-ttu-id="92316-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="92316-111">SQLEngine</span></span>|  
|<span data-ttu-id="92316-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="92316-112">Symbolic Name</span></span>|<span data-ttu-id="92316-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="92316-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span></span>|  
|<span data-ttu-id="92316-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="92316-114">Message Text</span></span>|<span data-ttu-id="92316-115">Não foi possível processar o índice I_NAME da tabela O_NAME porque o grupo de arquivos F_NAME é inválido.</span><span class="sxs-lookup"><span data-stu-id="92316-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is invalid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="92316-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="92316-116">Explanation</span></span>  
 <span data-ttu-id="92316-117">Essa mensagem informativa indica que não foi possível verificar o índice porque uma das IDs de grupo de arquivos armazenada nos metadados do índice não existe.</span><span class="sxs-lookup"><span data-stu-id="92316-117">This informational message indicates that the index cannot be checked because one of the filegroup IDs that is stored in the metadata of the index does not exist.</span></span> <span data-ttu-id="92316-118">A ID do grupo de arquivos que não é válida deve pertencer aos dados propriamente ditos, aos dados de objeto grande (LOB) ou aos dados de estouro de linha.</span><span class="sxs-lookup"><span data-stu-id="92316-118">The filegroup ID that is not valid might pertain to the data itself, or to the large object (LOB) data, or to the row-overflow data.</span></span>  
  
 <span data-ttu-id="92316-119">Se não houver problemas, todos os demais índices do mesmo objeto serão verificados.</span><span class="sxs-lookup"><span data-stu-id="92316-119">If there are no problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="92316-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="92316-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="92316-121">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="92316-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="92316-122">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="92316-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="92316-123">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="92316-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="92316-124">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="92316-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="92316-125">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="92316-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="92316-126">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="92316-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="92316-127">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="92316-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="92316-128">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="92316-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="92316-129">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="92316-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="92316-130">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="92316-130">Restore from Backup</span></span>  
 <span data-ttu-id="92316-131">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="92316-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="92316-132">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="92316-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="92316-133">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="92316-133">Not applicable.</span></span> <span data-ttu-id="92316-134">Não é possível corrigir esse erro automaticamente.</span><span class="sxs-lookup"><span data-stu-id="92316-134">This error cannot be repaired automatically.</span></span>  
  
  
