---
title: MSSQLSERVER_7936 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7936 (Database Engine error)
ms.assetid: d78fc8a9-d173-4801-bb32-ed6a29257f08
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c478e998b6185b0a8e22cd99caf2be4fc2fdee33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576433"
---
# <a name="mssqlserver_7936"></a><span data-ttu-id="5feed-102">MSSQLSERVER_7936</span><span class="sxs-lookup"><span data-stu-id="5feed-102">MSSQLSERVER_7936</span></span>
    
## <a name="details"></a><span data-ttu-id="5feed-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5feed-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5feed-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="5feed-104">Product Name</span></span>|<span data-ttu-id="5feed-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5feed-105">SQL Server</span></span>|  
|<span data-ttu-id="5feed-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="5feed-106">Event ID</span></span>|<span data-ttu-id="5feed-107">7936</span><span class="sxs-lookup"><span data-stu-id="5feed-107">7936</span></span>|  
|<span data-ttu-id="5feed-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="5feed-108">Event Source</span></span>|<span data-ttu-id="5feed-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5feed-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5feed-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5feed-110">Component</span></span>|<span data-ttu-id="5feed-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5feed-111">SQLEngine</span></span>|  
|<span data-ttu-id="5feed-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="5feed-112">Symbolic Name</span></span>|<span data-ttu-id="5feed-113">DBCC2_FS_ORPHANED_COLUMN_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="5feed-113">DBCC2_FS_ORPHANED_COLUMN_DIRECTORY</span></span>|  
|<span data-ttu-id="5feed-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="5feed-114">Message Text</span></span>|<span data-ttu-id="5feed-115">Erro de tabela: existe um diretório de Fluxo de arquivos para a ID de coluna C_ID da ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, mas essa coluna não é de Filestream.</span><span class="sxs-lookup"><span data-stu-id="5feed-115">Table error: Filestream directory exists for column ID C_ID of object ID O_ID, index ID I_ID, partition ID PN_ID, but that column is not a Filestream column.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5feed-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="5feed-116">Explanation</span></span>  
 <span data-ttu-id="5feed-117">Durante a execução de DBCC CHECKDB, um diretório de FILESTREAM foi encontrado para a coluna especificada; entretanto, a coluna não é de `FILESTREAM`.</span><span class="sxs-lookup"><span data-stu-id="5feed-117">During DBCC CHECKDB, a FILESTREAM directory was found for the specified column; however, the column is not a `FILESTREAM` column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5feed-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="5feed-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="5feed-119">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="5feed-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="5feed-120">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="5feed-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="5feed-121">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="5feed-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="5feed-122">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="5feed-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="5feed-123">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="5feed-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="5feed-124">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="5feed-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="5feed-125">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="5feed-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="5feed-126">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="5feed-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="5feed-127">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="5feed-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="5feed-128">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="5feed-128">Restore from Backup</span></span>  
 <span data-ttu-id="5feed-129">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="5feed-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="5feed-130">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="5feed-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="5feed-131">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="5feed-131">Not applicable.</span></span> <span data-ttu-id="5feed-132">Não é possível corrigir esse erro automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5feed-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="5feed-133">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5feed-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
