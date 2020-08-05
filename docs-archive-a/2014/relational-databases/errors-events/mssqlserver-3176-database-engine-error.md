---
title: MSSQLSERVER_3176 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3176 (Database Engine error)
ms.assetid: 4be24c64-2d52-4cb4-b4d7-36efbe4555b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 64e1a836995fe8738bb5c2ff0cb4de10d84d1f29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574024"
---
# <a name="mssqlserver_3176"></a><span data-ttu-id="60906-102">MSSQLSERVER_3176</span><span class="sxs-lookup"><span data-stu-id="60906-102">MSSQLSERVER_3176</span></span>
    
## <a name="details"></a><span data-ttu-id="60906-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="60906-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60906-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="60906-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="60906-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="60906-105">Event ID</span></span>|<span data-ttu-id="60906-106">3176</span><span class="sxs-lookup"><span data-stu-id="60906-106">3176</span></span>|  
|<span data-ttu-id="60906-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="60906-107">Event Source</span></span>|<span data-ttu-id="60906-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="60906-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="60906-109">Componente</span><span class="sxs-lookup"><span data-stu-id="60906-109">Component</span></span>|<span data-ttu-id="60906-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="60906-110">SQLEngine</span></span>|  
|<span data-ttu-id="60906-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="60906-111">Symbolic Name</span></span>|<span data-ttu-id="60906-112">LDDB_FILE_CLAIM</span><span class="sxs-lookup"><span data-stu-id="60906-112">LDDB_FILE_CLAIM</span></span>|  
|<span data-ttu-id="60906-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="60906-113">Message Text</span></span>|<span data-ttu-id="60906-114">O arquivo '%ls' foi reivindicado por '%ls' (%d) e '%ls' (%d).</span><span class="sxs-lookup"><span data-stu-id="60906-114">File '%ls' is claimed by '%ls'(%d) and '%ls'(%d).</span></span> <span data-ttu-id="60906-115">A cláusula WITH MOVE pode ser usada para realocar um ou mais arquivos.</span><span class="sxs-lookup"><span data-stu-id="60906-115">The WITH MOVE clause can be used to relocate one or more files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="60906-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="60906-116">Explanation</span></span>  
 <span data-ttu-id="60906-117">Tentativa de uso de um arquivo para mais de uma finalidade.</span><span class="sxs-lookup"><span data-stu-id="60906-117">Attempting to use a file for more than one purpose.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="60906-118">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="60906-118">Possible Causes</span></span>  
 <span data-ttu-id="60906-119">Outro banco de dados já está usando o nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="60906-119">Another database is already using the file name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60906-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="60906-120">User Action</span></span>  
 <span data-ttu-id="60906-121">Restaure os arquivos de banco de dados em um local diferente.</span><span class="sxs-lookup"><span data-stu-id="60906-121">Restore the database files to a different location.</span></span> <span data-ttu-id="60906-122">Em uma instrução RESTORE, use uma cláusula WITH MOVE para mover cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="60906-122">In a RESTORE statement, use a WITH MOVE clause to move each file.</span></span> <span data-ttu-id="60906-123">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], altere os locais de arquivo na grade **Restaurar os arquivos de banco de dados como** da caixa de diálogo **Restaurar Opções de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="60906-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], change the file locations in the **Restore the database files as** grid of the **Restore Database Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60906-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60906-124">See Also</span></span>  
 <span data-ttu-id="60906-125">[Restaurar um banco de dados em um novo local &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60906-125">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="60906-126">[Restaurar arquivos para um novo local &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60906-126">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="60906-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60906-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
