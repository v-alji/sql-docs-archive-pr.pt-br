---
title: MSSQLSERVER_2527 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2527 (Database Engine error)
ms.assetid: 1cef90ef-9c39-44e6-bc7f-316c8f53c10c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 900707634a016ecfd29f9f676e68b4d2f557ccea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572089"
---
# <a name="mssqlserver_2527"></a><span data-ttu-id="9fe0d-102">MSSQLSERVER_2527</span><span class="sxs-lookup"><span data-stu-id="9fe0d-102">MSSQLSERVER_2527</span></span>
    
## <a name="details"></a><span data-ttu-id="9fe0d-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9fe0d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9fe0d-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="9fe0d-104">Product Name</span></span>|<span data-ttu-id="9fe0d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9fe0d-105">SQL Server</span></span>|  
|<span data-ttu-id="9fe0d-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="9fe0d-106">Event ID</span></span>|<span data-ttu-id="9fe0d-107">2527</span><span class="sxs-lookup"><span data-stu-id="9fe0d-107">2527</span></span>|  
|<span data-ttu-id="9fe0d-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="9fe0d-108">Event Source</span></span>|<span data-ttu-id="9fe0d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9fe0d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9fe0d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9fe0d-110">Component</span></span>|<span data-ttu-id="9fe0d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9fe0d-111">SQLEngine</span></span>|  
|<span data-ttu-id="9fe0d-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="9fe0d-112">Symbolic Name</span></span>|<span data-ttu-id="9fe0d-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="9fe0d-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span></span>|  
|<span data-ttu-id="9fe0d-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="9fe0d-114">Message Text</span></span>|<span data-ttu-id="9fe0d-115">Não foi possível processar o índice I_NAME da tabela O_NAME porque o grupo de arquivos F_NAME está offline.</span><span class="sxs-lookup"><span data-stu-id="9fe0d-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is offline.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9fe0d-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="9fe0d-116">Explanation</span></span>  
 <span data-ttu-id="9fe0d-117">Essa mensagem informativa indica que não foi possível verificar o índice porque um dos grupos de arquivos que armazena dados para o índice está offline.</span><span class="sxs-lookup"><span data-stu-id="9fe0d-117">This informational message indicates that the index cannot be checked because one of the filegroups that stores data for the index is offline.</span></span> <span data-ttu-id="9fe0d-118">O estado dos arquivos em um grupo de arquivos determina a disponibilidade de todo o grupo.</span><span class="sxs-lookup"><span data-stu-id="9fe0d-118">The state of the files in a filegroup determines the availability of the whole filegroup.</span></span> <span data-ttu-id="9fe0d-119">Para que um grupo de arquivos fique disponível, todos os seus arquivos devem estar online.</span><span class="sxs-lookup"><span data-stu-id="9fe0d-119">For a filegroup to be available, all files within the filegroup must be online.</span></span> <span data-ttu-id="9fe0d-120">Se não houver outros problemas, todos os demais índices do mesmo objeto serão verificados.</span><span class="sxs-lookup"><span data-stu-id="9fe0d-120">If there are no other problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9fe0d-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="9fe0d-121">User Action</span></span>  
 <span data-ttu-id="9fe0d-122">Para exibir o estado dos arquivos do grupo de arquivos especificado, consulte a exibição do catálogo **sys.database_files** ou **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="9fe0d-122">To view the state of the files for the specified filegroup, query either the **sys.database_files** or **sys.master_files** catalog view.</span></span>  
  
 <span data-ttu-id="9fe0d-123">Restaure o arquivo offline de um backup.</span><span class="sxs-lookup"><span data-stu-id="9fe0d-123">Restore the offline file from a backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe0d-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9fe0d-124">See Also</span></span>  
 <span data-ttu-id="9fe0d-125">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9fe0d-125">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="9fe0d-126">[sys. master_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9fe0d-126">[sys.master_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span></span>  
 [<span data-ttu-id="9fe0d-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9fe0d-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
