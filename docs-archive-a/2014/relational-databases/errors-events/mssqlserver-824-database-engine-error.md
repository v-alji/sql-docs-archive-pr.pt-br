---
title: MSSQLSERVER_824 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
ms.assetid: 2aa22246-2712-4fdb-9744-36e7e6f3175e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d57b19bc8c837b92b65728fbb0046039b862d31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573995"
---
# <a name="mssqlserver_824"></a><span data-ttu-id="bceea-102">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="bceea-102">MSSQLSERVER_824</span></span>
    
## <a name="details"></a><span data-ttu-id="bceea-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="bceea-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bceea-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="bceea-104">Product Name</span></span>|<span data-ttu-id="bceea-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bceea-105">SQL Server</span></span>|  
|<span data-ttu-id="bceea-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="bceea-106">Event ID</span></span>|<span data-ttu-id="bceea-107">824</span><span class="sxs-lookup"><span data-stu-id="bceea-107">824</span></span>|  
|<span data-ttu-id="bceea-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="bceea-108">Event Source</span></span>|<span data-ttu-id="bceea-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bceea-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bceea-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bceea-110">Component</span></span>|<span data-ttu-id="bceea-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bceea-111">SQLEngine</span></span>|  
|<span data-ttu-id="bceea-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="bceea-112">Symbolic Name</span></span>|<span data-ttu-id="bceea-113">B_HARDSSERR</span><span class="sxs-lookup"><span data-stu-id="bceea-113">B_HARDSSERR</span></span>|  
|<span data-ttu-id="bceea-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="bceea-114">Message Text</span></span>|<span data-ttu-id="bceea-115">O SQL Server detectou um erro de E/S baseado em consistência lógica: %ls.</span><span class="sxs-lookup"><span data-stu-id="bceea-115">SQL Server detected a logical consistency-based I/O error: %ls.</span></span> <span data-ttu-id="bceea-116">Isso aconteceu durante um %S_MSG da página %S_PGID na ID de banco de dados %d no deslocamento %#016I64x no arquivo '%ls'.</span><span class="sxs-lookup"><span data-stu-id="bceea-116">It occurred during a %S_MSG of page %S_PGID in database ID %d at offset %#016I64x in file '%ls'.</span></span>  <span data-ttu-id="bceea-117">Mensagens adicionais no log de erros ou no log de eventos do sistema no SQL Server poderão fornecer mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="bceea-117">Additional messages in the SQL Server error log or system event log may provide more detail.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bceea-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="bceea-118">Explanation</span></span>  
 <span data-ttu-id="bceea-119">Esse erro indica que o Windows informa que a página foi lida com êxito no disco, mas o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] descobriu algo errado com a página.</span><span class="sxs-lookup"><span data-stu-id="bceea-119">This error indicates that Windows reports that the page is successfully read from disk, but [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has discovered something wrong with the page.</span></span> <span data-ttu-id="bceea-120">Esse erro é semelhante ao erro 823, exceto pelo fato de o Windows não ter detectado o erro.</span><span class="sxs-lookup"><span data-stu-id="bceea-120">This error is similar to error 823 except that Windows did not detect the error.</span></span> <span data-ttu-id="bceea-121">Ele normalmente indica um problema no subsistema de E/S, como uma unidade de disco deficiente, problemas de firmware de disco, driver de dispositivo defeituoso e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="bceea-121">This usually indicates a problem in the I/O subsystem, such as a failing disk drive, disk firmware problems, faulty device driver, and so on.</span></span> <span data-ttu-id="bceea-122">Para obter mais informações sobre erros de E/S, consulte [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) (Noções básicas de E/S do Microsoft SQL Server, Capítulo 2).</span><span class="sxs-lookup"><span data-stu-id="bceea-122">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bceea-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="bceea-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="bceea-124">Procurar falhas de hardware</span><span class="sxs-lookup"><span data-stu-id="bceea-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="bceea-125">Execute o diagnóstico de hardware e corrija quaisquer problemas.</span><span class="sxs-lookup"><span data-stu-id="bceea-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="bceea-126">Examine também os logs do aplicativo e do sistema do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver se o erro ocorreu devido a uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="bceea-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred because of hardware failure.</span></span> <span data-ttu-id="bceea-127">Corrija quaisquer problemas relacionados a hardware existentes nos logs.</span><span class="sxs-lookup"><span data-stu-id="bceea-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="bceea-128">Se você tiver problemas contínuos de danos aos dados, tente alternar diferentes componentes de hardware para isolar o problema.</span><span class="sxs-lookup"><span data-stu-id="bceea-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="bceea-129">Verifique se o sistema não está com a gravação em cache habilitada no controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="bceea-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="bceea-130">Se você suspeitar que a gravação de caching seja o problema, contate o fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="bceea-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="bceea-131">Finalmente, pode ser útil mudar para um sistema de hardware novo.</span><span class="sxs-lookup"><span data-stu-id="bceea-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="bceea-132">Essa mudança pode incluir a reformatação de unidades de disco e a reinstalação do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="bceea-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="bceea-133">Restaurar a partir de backup</span><span class="sxs-lookup"><span data-stu-id="bceea-133">Restore from Backup</span></span>  
 <span data-ttu-id="bceea-134">Se o problema não estiver relacionado ao hardware e se houver um backup limpo conhecido, restaure o banco de dados do backup.</span><span class="sxs-lookup"><span data-stu-id="bceea-134">If the problem is not hardware-related and a known clean backup is available, restore the database from the backup.</span></span>  
  
 <span data-ttu-id="bceea-135">Experimente mudar os bancos de dados para usar a opção PAGE_VERIFY CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="bceea-135">Consider changing the databases to use the PAGE_VERIFY CHECKSUM option.</span></span> <span data-ttu-id="bceea-136">Para obter informações sobre PAGE_VERIFY, consulte [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bceea-136">For information about PAGE_VERIFY, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bceea-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bceea-137">See Also</span></span>  
 [<span data-ttu-id="bceea-138">Gerenciar a tabela suspect_pages &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bceea-138">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
