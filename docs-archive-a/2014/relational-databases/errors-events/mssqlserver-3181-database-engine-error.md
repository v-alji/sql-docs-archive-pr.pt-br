---
title: MSSQLSERVER_3181 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3181 (Database Engine error)
ms.assetid: e6d2e716-5263-477c-ad0e-7bcbfef4c1f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f18509d9a18ba8be1f4e40c93bff5abfcae3d69c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574023"
---
# <a name="mssqlserver_3181"></a><span data-ttu-id="0dd8f-102">MSSQLSERVER_3181</span><span class="sxs-lookup"><span data-stu-id="0dd8f-102">MSSQLSERVER_3181</span></span>
    
## <a name="details"></a><span data-ttu-id="0dd8f-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0dd8f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0dd8f-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="0dd8f-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0dd8f-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="0dd8f-105">Event ID</span></span>|<span data-ttu-id="0dd8f-106">3181</span><span class="sxs-lookup"><span data-stu-id="0dd8f-106">3181</span></span>|  
|<span data-ttu-id="0dd8f-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="0dd8f-107">Event Source</span></span>|<span data-ttu-id="0dd8f-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0dd8f-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0dd8f-109">Componente</span><span class="sxs-lookup"><span data-stu-id="0dd8f-109">Component</span></span>|<span data-ttu-id="0dd8f-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0dd8f-110">SQLEngine</span></span>|  
|<span data-ttu-id="0dd8f-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="0dd8f-111">Symbolic Name</span></span>|<span data-ttu-id="0dd8f-112">LDDB_STORAGE_VERIFY</span><span class="sxs-lookup"><span data-stu-id="0dd8f-112">LDDB_STORAGE_VERIFY</span></span>|  
|<span data-ttu-id="0dd8f-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="0dd8f-113">Message Text</span></span>|<span data-ttu-id="0dd8f-114">A tentativa de restaurar este backup pode encontrar problemas de espaço de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="0dd8f-114">Attempting to restore this backup may encounter storage space problems.</span></span> <span data-ttu-id="0dd8f-115">As próximas mensagens fornecerão detalhes.</span><span class="sxs-lookup"><span data-stu-id="0dd8f-115">Subsequent messages will provide details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0dd8f-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="0dd8f-116">Explanation</span></span>  
 <span data-ttu-id="0dd8f-117">A instrução RESTORE VERIFYONLY verifica o espaço de armazenamento disponível no disco onde o banco de dados será restaurado.</span><span class="sxs-lookup"><span data-stu-id="0dd8f-117">The RESTORE VERIFYONLY statement checks the available storage space on the disk to which the database is to be restored.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="0dd8f-118">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="0dd8f-118">Possible Causes</span></span>  
 <span data-ttu-id="0dd8f-119">O espaço disponível em disco pode ser insuficiente para restaurar o backup que está sendo verificado.</span><span class="sxs-lookup"><span data-stu-id="0dd8f-119">The available disk space may be insufficient to restore the backup being verified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0dd8f-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="0dd8f-120">User Action</span></span>  
 <span data-ttu-id="0dd8f-121">Restaure o backup em um local com espaço em disco suficiente ou forneça mais espaço no disco.</span><span class="sxs-lookup"><span data-stu-id="0dd8f-121">Restore the backup to a location with sufficient disk space, or provide more space on the disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd8f-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0dd8f-122">See Also</span></span>  
 <span data-ttu-id="0dd8f-123">[Restaurar um banco de dados em um novo local &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0dd8f-123">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="0dd8f-124">[Restaurar arquivos para um novo local &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0dd8f-124">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="0dd8f-125">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0dd8f-125">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="0dd8f-126">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0dd8f-126">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql)  
  
  
