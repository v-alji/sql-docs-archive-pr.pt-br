---
title: MSSQLSERVER_3156 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3156 (Database Engine error)
ms.assetid: 345d8ed4-177e-4ec3-bab3-25d30000e323
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 25b5a037012a6d6b47b91e763a49cfb67b89f43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574028"
---
# <a name="mssqlserver_3156"></a><span data-ttu-id="114dc-102">MSSQLSERVER_3156</span><span class="sxs-lookup"><span data-stu-id="114dc-102">MSSQLSERVER_3156</span></span>
    
## <a name="details"></a><span data-ttu-id="114dc-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="114dc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="114dc-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="114dc-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="114dc-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="114dc-105">Event ID</span></span>|<span data-ttu-id="114dc-106">3156</span><span class="sxs-lookup"><span data-stu-id="114dc-106">3156</span></span>|  
|<span data-ttu-id="114dc-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="114dc-107">Event Source</span></span>|<span data-ttu-id="114dc-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="114dc-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="114dc-109">Componente</span><span class="sxs-lookup"><span data-stu-id="114dc-109">Component</span></span>|<span data-ttu-id="114dc-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="114dc-110">SQLEngine</span></span>|  
|<span data-ttu-id="114dc-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="114dc-111">Symbolic Name</span></span>|<span data-ttu-id="114dc-112">LDDB_CANT_WRITE</span><span class="sxs-lookup"><span data-stu-id="114dc-112">LDDB_CANT_WRITE</span></span>|  
|<span data-ttu-id="114dc-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="114dc-113">Message Text</span></span>|<span data-ttu-id="114dc-114">O arquivo '%ls' não pode ser restaurado para '%ls'.</span><span class="sxs-lookup"><span data-stu-id="114dc-114">File '%ls' cannot be restored to '%ls'.</span></span> <span data-ttu-id="114dc-115">Use WITH MOVE para identificar um local válido para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="114dc-115">Use WITH MOVE to identify a valid location for the file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="114dc-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="114dc-116">Explanation</span></span>  
 <span data-ttu-id="114dc-117">Esta mensagem geral identifica os nomes de arquivo lógicos ou físicos dos arquivos que não puderam ser restaurados devido a um problema com o local especificado.</span><span class="sxs-lookup"><span data-stu-id="114dc-117">This general message identifies the logical or physical file names of files that could not be restored because of a problem with the specified location.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="114dc-118">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="114dc-118">Possible Causes</span></span>  
 <span data-ttu-id="114dc-119">As causas possíveis incluem as seguintes:</span><span class="sxs-lookup"><span data-stu-id="114dc-119">The possible causes include the following:</span></span>  
  
-   <span data-ttu-id="114dc-120">Talvez seja preciso acessar o diretório especificado do Windows.</span><span class="sxs-lookup"><span data-stu-id="114dc-120">You might need access to the specified Windows directory.</span></span>  
  
-   <span data-ttu-id="114dc-121">Você pode ter digitado incorretamente o caminho ou pode ter especificado um caminho que não existe.</span><span class="sxs-lookup"><span data-stu-id="114dc-121">You might have mistyped the path or specified a path that does not exist.</span></span>  
  
-   <span data-ttu-id="114dc-122">O nome de arquivo pode estar sendo usado por um arquivo que não pode ser substituído.</span><span class="sxs-lookup"><span data-stu-id="114dc-122">The file name might be being used by a file that cannot be overwritten.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="114dc-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="114dc-123">User Action</span></span>  
 <span data-ttu-id="114dc-124">Veja nos logs de erros outras mensagens mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="114dc-124">Look at the error logs for other messages that provide more details.</span></span>  
  
 <span data-ttu-id="114dc-125">Corrija o problema com o local especificado, por exemplo, concedendo acesso, ou use a opção WITH MOVE em sua instrução RESTORE para realocar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="114dc-125">Correct the problem with the specified location, for example, by granting access, or use the WITH MOVE option in your RESTORE statement to relocate the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="114dc-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="114dc-126">See Also</span></span>  
 <span data-ttu-id="114dc-127">[Restaurar um banco de dados em um novo local &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="114dc-127">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="114dc-128">[Restaurar arquivos para um novo local &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="114dc-128">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="114dc-129">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="114dc-129">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
