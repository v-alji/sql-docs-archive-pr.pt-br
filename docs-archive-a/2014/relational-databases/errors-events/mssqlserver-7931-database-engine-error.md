---
title: MSSQLSERVER_7931 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7931 (Database Engine error)
ms.assetid: 18e7a3dc-7d8a-41b9-8724-d2a8587b6903
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a93cc56869448d1dbcf95c1d9e1ffe1fe023e7e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574710"
---
# <a name="mssqlserver_7931"></a><span data-ttu-id="c71c2-102">MSSQLSERVER_7931</span><span class="sxs-lookup"><span data-stu-id="c71c2-102">MSSQLSERVER_7931</span></span>
    
## <a name="details"></a><span data-ttu-id="c71c2-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c71c2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c71c2-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="c71c2-104">Product Name</span></span>|<span data-ttu-id="c71c2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c71c2-105">SQL Server</span></span>|  
|<span data-ttu-id="c71c2-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="c71c2-106">Event ID</span></span>|<span data-ttu-id="c71c2-107">7931</span><span class="sxs-lookup"><span data-stu-id="c71c2-107">7931</span></span>|  
|<span data-ttu-id="c71c2-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="c71c2-108">Event Source</span></span>|<span data-ttu-id="c71c2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c71c2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c71c2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c71c2-110">Component</span></span>|<span data-ttu-id="c71c2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c71c2-111">SQLEngine</span></span>|  
|<span data-ttu-id="c71c2-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="c71c2-112">Symbolic Name</span></span>|<span data-ttu-id="c71c2-113">DBCC2_FS_DOUBLE_ROWSET_ACTUAL_FACT</span><span class="sxs-lookup"><span data-stu-id="c71c2-113">DBCC2_FS_DOUBLE_ROWSET_ACTUAL_FACT</span></span>|  
|<span data-ttu-id="c71c2-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="c71c2-114">Message Text</span></span>|<span data-ttu-id="c71c2-115">Erro de banco de dados: a ID de diretório de FileStream F_ID de uma partição foi vista duas vezes.</span><span class="sxs-lookup"><span data-stu-id="c71c2-115">Database error: The FileStream directory ID F_ID for a partition was seen twice.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c71c2-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="c71c2-116">Explanation</span></span>  
 <span data-ttu-id="c71c2-117">A mesma ID de partição de um diretório de Filestream foi encontrada nos metadados.</span><span class="sxs-lookup"><span data-stu-id="c71c2-117">The same partition ID for a Filestream directory was found in the metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c71c2-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="c71c2-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="c71c2-119">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="c71c2-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="c71c2-120">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="c71c2-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="c71c2-121">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="c71c2-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="c71c2-122">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="c71c2-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="c71c2-123">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="c71c2-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="c71c2-124">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="c71c2-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="c71c2-125">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="c71c2-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="c71c2-126">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="c71c2-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="c71c2-127">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c71c2-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="c71c2-128">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="c71c2-128">Restore from Backup</span></span>  
 <span data-ttu-id="c71c2-129">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="c71c2-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="c71c2-130">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="c71c2-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="c71c2-131">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="c71c2-131">Not applicable.</span></span> <span data-ttu-id="c71c2-132">Não é possível corrigir esse erro automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c71c2-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="c71c2-133">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c71c2-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
