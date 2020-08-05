---
title: MSSQLSERVER_3168 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3168 (Database Engine error)
ms.assetid: 991111d9-1eb3-43e9-9333-a75a775c3200
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 764f456653365c085e9f756a749910bbd03b4259
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574027"
---
# <a name="mssqlserver_3168"></a><span data-ttu-id="0c4cc-102">MSSQLSERVER_3168</span><span class="sxs-lookup"><span data-stu-id="0c4cc-102">MSSQLSERVER_3168</span></span>
    
## <a name="details"></a><span data-ttu-id="0c4cc-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0c4cc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c4cc-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="0c4cc-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0c4cc-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="0c4cc-105">Event ID</span></span>|<span data-ttu-id="0c4cc-106">3168</span><span class="sxs-lookup"><span data-stu-id="0c4cc-106">3168</span></span>|  
|<span data-ttu-id="0c4cc-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="0c4cc-107">Event Source</span></span>|<span data-ttu-id="0c4cc-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0c4cc-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0c4cc-109">Componente</span><span class="sxs-lookup"><span data-stu-id="0c4cc-109">Component</span></span>|<span data-ttu-id="0c4cc-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0c4cc-110">SQLEngine</span></span>|  
|<span data-ttu-id="0c4cc-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="0c4cc-111">Symbolic Name</span></span>|<span data-ttu-id="0c4cc-112">LDDB_SYSTEMWRONGVER</span><span class="sxs-lookup"><span data-stu-id="0c4cc-112">LDDB_SYSTEMWRONGVER</span></span>|  
|<span data-ttu-id="0c4cc-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="0c4cc-113">Message Text</span></span>|<span data-ttu-id="0c4cc-114">O backup do banco de dados do sistema no dispositivo %ls não pode ser restaurado porque foi criado por uma versão diferente (%ls) da versão deste servidor (%ls).</span><span class="sxs-lookup"><span data-stu-id="0c4cc-114">The backup of the system database on the device %ls cannot be restored because it was created by a different version of the server (%ls) than this server (%ls).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0c4cc-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="0c4cc-115">Explanation</span></span>  
 <span data-ttu-id="0c4cc-116">Não é possível restaurar um backup de um banco de dados do sistema (**master**, **model** ou **msdb**) em um build do servidor diferente do build em que o backup foi originalmente executado.</span><span class="sxs-lookup"><span data-stu-id="0c4cc-116">You cannot restore a backup of a system database (**master**, **model**, or **msdb**) on a server build that differs from the build on which the backup was originally performed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c4cc-117">A instalação de uma compilação de service pack ou de hotfix altera o número de compilação do servidor e as compilações do servidor são sempre incrementais.</span><span class="sxs-lookup"><span data-stu-id="0c4cc-117">Installing a service pack or a hotfix build changes the server build number, and server builds are always incremental.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="0c4cc-118">Possíveis causas</span><span class="sxs-lookup"><span data-stu-id="0c4cc-118">Possible Causes</span></span>  
 <span data-ttu-id="0c4cc-119">O esquema de banco de dados para os bancos de dados do sistema pode ter sido alterado nas compilações do servidor.</span><span class="sxs-lookup"><span data-stu-id="0c4cc-119">The database schema for system databases may be changed across server builds.</span></span> <span data-ttu-id="0c4cc-120">Para certificar-se de que uma alteração de esquema não cause inconsistências, a instrução RESTORE compara o número de compilação do servidor no arquivo de backup com o número de compilação do servidor no qual você está tentando restaurar o backup.</span><span class="sxs-lookup"><span data-stu-id="0c4cc-120">To make sure that a schema change does not cause inconsistencies, the RESTORE statement compares the server build number on the backup file to the build number of the server on which you are trying to restore the backup.</span></span> <span data-ttu-id="0c4cc-121">Se as compilações forem diferentes, a instrução emitirá uma mensagem de erro 3168 e a operação de restauração será terminada de forma anormal.</span><span class="sxs-lookup"><span data-stu-id="0c4cc-121">If the builds are different, the statement issues the 3168 error message, and the restore operation terminates abnormally.</span></span>  
  
 <span data-ttu-id="0c4cc-122">Alguns cenários nos quais esse problema pode acontecer incluem os seguintes:</span><span class="sxs-lookup"><span data-stu-id="0c4cc-122">Some scenarios in which this problem may occur include the following:</span></span>  
  
-   <span data-ttu-id="0c4cc-123">Um usuário tenta restaurar um banco de dados do sistema no servidor A partir de um backup executado no servidor B. Os servidores A e B estão em diferentes compilações do servidor.</span><span class="sxs-lookup"><span data-stu-id="0c4cc-123">A user tries to restore a system database on Server A from a backup taken on Server B. Servers A and B are on different server builds.</span></span> <span data-ttu-id="0c4cc-124">Por exemplo, o servidor A pode estar em uma compilação da versão original e o servidor B pode estar em uma compilação de service pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="0c4cc-124">For example, Server A might be on the original release version build and Server B might be on a service pack 1 (SP1) build.</span></span>  
  
-   <span data-ttu-id="0c4cc-125">Um usuário tenta restaurar um banco de dados do sistema a partir de um backup executado no mesmo servidor.</span><span class="sxs-lookup"><span data-stu-id="0c4cc-125">A user tries to restore a system database from a backup taken on the same server.</span></span> <span data-ttu-id="0c4cc-126">Porém, o servidor estava executando uma compilação diferente quando o backup aconteceu.</span><span class="sxs-lookup"><span data-stu-id="0c4cc-126">However, the server was running a different build when the backup occurred.</span></span> <span data-ttu-id="0c4cc-127">Isto é, o servidor foi atualizado desde a realização do backup.</span><span class="sxs-lookup"><span data-stu-id="0c4cc-127">That is, the server was upgraded since the backup was performed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0c4cc-128">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="0c4cc-128">User Action</span></span>  
 <span data-ttu-id="0c4cc-129">O processo de restauração nessa situação está claramente envolvido e só é usado em último caso.</span><span class="sxs-lookup"><span data-stu-id="0c4cc-129">The restore process in this situation is fairly involved, and used only as a last resort.</span></span> <span data-ttu-id="0c4cc-130">Para obter mais informações, consulte “[Não é possível restaurar backups de banco de dados do sistema em um build diferente do SQL Server](https://support.microsoft.com/kb/264474)”.</span><span class="sxs-lookup"><span data-stu-id="0c4cc-130">For more information, see"[You cannot restore system database backups to a different build of SQL Server](https://support.microsoft.com/kb/264474)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c4cc-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0c4cc-131">See Also</span></span>  
 [<span data-ttu-id="0c4cc-132">Fazer backup e restaurar bancos de dados do sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0c4cc-132">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
  
