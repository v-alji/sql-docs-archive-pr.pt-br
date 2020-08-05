---
title: MSSQLSERVER_7907 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7907 (Database Engine error)
ms.assetid: a1c94e4a-7e91-46e0-9fac-07bbbf6dd018
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e09e95d9a2416ae54c40f5c8e57d9444497c579f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574006"
---
# <a name="mssqlserver_7907"></a><span data-ttu-id="b886a-102">MSSQLSERVER_7907</span><span class="sxs-lookup"><span data-stu-id="b886a-102">MSSQLSERVER_7907</span></span>
    
## <a name="details"></a><span data-ttu-id="b886a-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b886a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b886a-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="b886a-104">Product Name</span></span>|<span data-ttu-id="b886a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b886a-105">SQL Server</span></span>|  
|<span data-ttu-id="b886a-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="b886a-106">Event ID</span></span>|<span data-ttu-id="b886a-107">7907</span><span class="sxs-lookup"><span data-stu-id="b886a-107">7907</span></span>|  
|<span data-ttu-id="b886a-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="b886a-108">Event Source</span></span>|<span data-ttu-id="b886a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b886a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b886a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b886a-110">Component</span></span>|<span data-ttu-id="b886a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b886a-111">SQLEngine</span></span>|  
|<span data-ttu-id="b886a-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="b886a-112">Symbolic Name</span></span>|<span data-ttu-id="b886a-113">DBCC2_FS_INVALID_COLUMN_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="b886a-113">DBCC2_FS_INVALID_COLUMN_DIRECTORY</span></span>|  
|<span data-ttu-id="b886a-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="b886a-114">Message Text</span></span>|<span data-ttu-id="b886a-115">Erro de tabela: o diretório 'DIRECTORY' na ID de partição PN_ID não é um diretório de Fluxo de arquivos válido.</span><span class="sxs-lookup"><span data-stu-id="b886a-115">Table error: The directory 'DIRECTORY' in partition ID PN_ID is not a valid Filestream directory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b886a-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="b886a-116">Explanation</span></span>  
 <span data-ttu-id="b886a-117">O nome de um diretório de coluna é a ID de coluna de mecanismo relacional da partição.</span><span class="sxs-lookup"><span data-stu-id="b886a-117">The name of a column directory is the relational engine column ID of the partition.</span></span> <span data-ttu-id="b886a-118">Se o nome de um diretório de coluna não puder ser convertido em uma ID de coluna, o diretório não será um diretório de coluna válido.</span><span class="sxs-lookup"><span data-stu-id="b886a-118">If a column directory name cannot be converted to a column ID, the directory is not a valid column directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b886a-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="b886a-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b886a-120">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="b886a-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b886a-121">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="b886a-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b886a-122">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="b886a-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b886a-123">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="b886a-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b886a-124">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="b886a-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b886a-125">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="b886a-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b886a-126">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="b886a-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b886a-127">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="b886a-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b886a-128">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="b886a-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b886a-129">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="b886a-129">Restore from Backup</span></span>  
 <span data-ttu-id="b886a-130">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="b886a-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b886a-131">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b886a-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b886a-132">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="b886a-132">Not applicable.</span></span> <span data-ttu-id="b886a-133">Esse erro não pode ser reparado.</span><span class="sxs-lookup"><span data-stu-id="b886a-133">This error cannot be repaired.</span></span> <span data-ttu-id="b886a-134">Se você não conseguir restaurar o banco de dados com base em um backup, contate o CSS (Suporte e Atendimento ao Cliente) [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b886a-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
