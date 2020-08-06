---
title: MSSQLSERVER_2540 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2540 (Database Engine error)
ms.assetid: eb5ee2be-acbb-4fb7-9b45-dc6200bde06e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4a49abeadcd49263ea7d0701ee468a36882179cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679373"
---
# <a name="mssqlserver_2540"></a><span data-ttu-id="1cc9b-102">MSSQLSERVER_2540</span><span class="sxs-lookup"><span data-stu-id="1cc9b-102">MSSQLSERVER_2540</span></span>
    
## <a name="details"></a><span data-ttu-id="1cc9b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1cc9b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1cc9b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="1cc9b-104">Product Name</span></span>|<span data-ttu-id="1cc9b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cc9b-105">SQL Server</span></span>|  
|<span data-ttu-id="1cc9b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="1cc9b-106">Event ID</span></span>|<span data-ttu-id="1cc9b-107">2540</span><span class="sxs-lookup"><span data-stu-id="1cc9b-107">2540</span></span>|  
|<span data-ttu-id="1cc9b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="1cc9b-108">Event Source</span></span>|<span data-ttu-id="1cc9b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1cc9b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1cc9b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1cc9b-110">Component</span></span>|<span data-ttu-id="1cc9b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1cc9b-111">SQLEngine</span></span>|  
|<span data-ttu-id="1cc9b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="1cc9b-112">Symbolic Name</span></span>|<span data-ttu-id="1cc9b-113">DBCC_REPAIR_ERROR_NOT_REPAIRABLE</span><span class="sxs-lookup"><span data-stu-id="1cc9b-113">DBCC_REPAIR_ERROR_NOT_REPAIRABLE</span></span>|  
|<span data-ttu-id="1cc9b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="1cc9b-114">Message Text</span></span>|<span data-ttu-id="1cc9b-115">O sistema não pode reparar este erro por conta própria.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-115">The system cannot self repair this error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1cc9b-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="1cc9b-116">Explanation</span></span>  
 <span data-ttu-id="1cc9b-117">Essa mensagem de erro indica problemas que não podem ser reparados automaticamente, como metadados corrompidos, danos em páginas PFS ou danos em certas tabelas base do sistema que são críticas.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-117">This error message indicates problems that cannot be repaired automatically, such as corrupt metadata, Page Free Space (PFS) page corruptions, or corruptions in certain critical system base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1cc9b-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="1cc9b-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="1cc9b-119">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="1cc9b-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="1cc9b-120">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="1cc9b-121">Examine também os logs do aplicativo e do sistema [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para verificar se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="1cc9b-122">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="1cc9b-123">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="1cc9b-124">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="1cc9b-125">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="1cc9b-126">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="1cc9b-127">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="1cc9b-128">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="1cc9b-128">Restore from Backup</span></span>  
 <span data-ttu-id="1cc9b-129">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="1cc9b-130">Executar DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="1cc9b-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="1cc9b-131">Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-131">Not applicable.</span></span> <span data-ttu-id="1cc9b-132">Não é possível corrigir esse erro automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1cc9b-132">This error cannot be repaired automatically.</span></span>  
  
  
