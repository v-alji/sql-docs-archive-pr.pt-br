---
title: MSSQLSERVER_7903 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7903 (Database Engine error)
ms.assetid: 991a86df-42cd-435e-85b3-f42e4cb13039
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e30247c5c858cf8ce6dcd75e41f1fb567e974201
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574011"
---
# <a name="mssqlserver_7903"></a><span data-ttu-id="a906b-102">MSSQLSERVER_7903</span><span class="sxs-lookup"><span data-stu-id="a906b-102">MSSQLSERVER_7903</span></span>
    
## <a name="details"></a><span data-ttu-id="a906b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a906b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a906b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a906b-104">Product Name</span></span>|<span data-ttu-id="a906b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a906b-105">SQL Server</span></span>|  
|<span data-ttu-id="a906b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a906b-106">Event ID</span></span>|<span data-ttu-id="a906b-107">7903</span><span class="sxs-lookup"><span data-stu-id="a906b-107">7903</span></span>|  
|<span data-ttu-id="a906b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a906b-108">Event Source</span></span>|<span data-ttu-id="a906b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a906b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a906b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a906b-110">Component</span></span>|<span data-ttu-id="a906b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a906b-111">SQLEngine</span></span>|  
|<span data-ttu-id="a906b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a906b-112">Symbolic Name</span></span>|<span data-ttu-id="a906b-113">DBCC2_FS_ORPHANED_FILE</span><span class="sxs-lookup"><span data-stu-id="a906b-113">DBCC2_FS_ORPHANED_FILE</span></span>|  
|<span data-ttu-id="a906b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a906b-114">Message Text</span></span>|<span data-ttu-id="a906b-115">Erro de tabela: O arquivo órfão 'FILE' encontrado no diretório Filestream da ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de coluna C_ID.</span><span class="sxs-lookup"><span data-stu-id="a906b-115">Table error: The orphaned file 'FILE' was found in the Filestream directory for object ID O_ID, index ID I_ID, partition ID PN_ID, column ID C_ID.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a906b-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="a906b-116">Explanation</span></span>  
 <span data-ttu-id="a906b-117">Um arquivo de FILESTREAM foi encontrado em um diretório de coluna FILESTREAM; entretanto, o valor de coluna correspondente na partição está ausente.</span><span class="sxs-lookup"><span data-stu-id="a906b-117">A FILESTREAM file was found in a FILESTREAM column directory; however, the corresponding column value in the partition is missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a906b-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a906b-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a906b-119">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="a906b-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a906b-120">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="a906b-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a906b-121">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="a906b-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a906b-122">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="a906b-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a906b-123">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="a906b-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a906b-124">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="a906b-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a906b-125">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="a906b-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a906b-126">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="a906b-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a906b-127">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="a906b-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a906b-128">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="a906b-128">Restore from Backup</span></span>  
 <span data-ttu-id="a906b-129">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="a906b-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a906b-130">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a906b-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a906b-131">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="a906b-131">Not applicable.</span></span> <span data-ttu-id="a906b-132">Esse erro não pode ser reparado.</span><span class="sxs-lookup"><span data-stu-id="a906b-132">This error cannot be repaired.</span></span> <span data-ttu-id="a906b-133">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a906b-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
