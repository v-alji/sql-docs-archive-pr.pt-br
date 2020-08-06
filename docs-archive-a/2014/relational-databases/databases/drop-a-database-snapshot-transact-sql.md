---
title: Remover um instantâneo de banco de dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- removing database snapshots
- deleting database snapshots
- database snapshots [SQL Server], deleting
ms.assetid: ad70ec97-d5fb-41aa-b72a-915e74b61b76
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0d9d912a092e581fad7d3d53504309f63ba1806
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568621"
---
# <a name="drop-a-database-snapshot-transact-sql"></a><span data-ttu-id="cd48c-102">Descartar um instantâneo do banco de dados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cd48c-102">Drop a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="cd48c-103">A remoção de um instantâneo do banco de dados exclui o instantâneo do banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e exclui os arquivos esparsos utilizados pelo instantâneo.</span><span class="sxs-lookup"><span data-stu-id="cd48c-103">Dropping a database snapshot deletes the database snapshot from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and deletes the sparse files that are used by the snapshot.</span></span> <span data-ttu-id="cd48c-104">Quando um instantâneo do banco de dados é removido, todas as conexões de usuário com ele são encerradas.</span><span class="sxs-lookup"><span data-stu-id="cd48c-104">When you drop a database snapshot, all user connections to it are terminated.</span></span>  
  
## <a name="security"></a><span data-ttu-id="cd48c-105">Segurança</span><span class="sxs-lookup"><span data-stu-id="cd48c-105">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cd48c-106">Permissões</span><span class="sxs-lookup"><span data-stu-id="cd48c-106">Permissions</span></span>  
 <span data-ttu-id="cd48c-107">Qualquer usuário com permissões DROP DATABASE pode remover um instantâneo do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="cd48c-107">Any user with DROP DATABASE permissions can drop a database snapshot.</span></span>  
  
##  <a name="how-to-drop-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cd48c-108">Como remover um instantâneo do banco de dados (usando o Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cd48c-108">How to Drop a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="cd48c-109">**Para remover um instantâneo do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="cd48c-109">**To drop a database snapshot**</span></span>  
  
1.  <span data-ttu-id="cd48c-110">Identifique o instantâneo do banco de dados que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="cd48c-110">Identify the database snapshot that you want to drop.</span></span> <span data-ttu-id="cd48c-111">Você pode exibir os instantâneos em um banco de dados no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd48c-111">You can view the snapshots on a database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cd48c-112">Para obter mais informações, veja [Exibir um instantâneo de banco de dados &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cd48c-112">For more information, see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="cd48c-113">Emita uma instrução [DROP DATABASE](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) , especificando o nome do instantâneo do banco de dados ser removido.</span><span class="sxs-lookup"><span data-stu-id="cd48c-113">Issue a [DROP DATABASE](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) statement, specifying the name of the database snapshot to be dropped.</span></span> <span data-ttu-id="cd48c-114">A sintaxe é mostrada a seguir:</span><span class="sxs-lookup"><span data-stu-id="cd48c-114">The syntax is as follows:</span></span>  
  
     <span data-ttu-id="cd48c-115">DROP DATABASE *database_snapshot_name* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="cd48c-115">DROP DATABASE *database_snapshot_name* [ **,**...*n* ]</span></span>  
  
     <span data-ttu-id="cd48c-116">Em que *database_snapshot_name* é o nome do instantâneo de banco de dados a ser removido.</span><span class="sxs-lookup"><span data-stu-id="cd48c-116">Where *database_snapshot_name* is the name of the database snapshot to be dropped.</span></span>  
  
####  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="cd48c-117">Exemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cd48c-117">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="cd48c-118">Este exemplo remove um instantâneo do banco de dados denominado SalesSnapshot0600 sem afetar o banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="cd48c-118">This example drops a database snapshot named SalesSnapshot0600, without affecting the source database.</span></span>  
  
```  
DROP DATABASE SalesSnapshot0600 ;  
```  
  
 <span data-ttu-id="cd48c-119">Todas as conexões de usuário para SalesSnapshot0600 são interrompidas, e todos os arquivos esparsos do sistema de arquivos NTFS usados pelo instantâneo são excluídos.</span><span class="sxs-lookup"><span data-stu-id="cd48c-119">Any user connections to SalesSnapshot0600 are terminated, and all of the NTFS file system sparse files used by the snapshot are deleted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd48c-120">Para obter informações sobre o uso de arquivos esparsos por instantâneos do banco de dados, veja [Instantâneos de banco de dados &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cd48c-120">For information about the use of sparse files by database snapshots, see [Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="cd48c-121">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="cd48c-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="cd48c-122">Criar um instantâneo de banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cd48c-122">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="cd48c-123">Exibir um instantâneo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd48c-123">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="cd48c-124">Reverter um banco de dados para um instantâneo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="cd48c-124">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="cd48c-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cd48c-125">See Also</span></span>  
 <span data-ttu-id="cd48c-126">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd48c-126">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span></span>  
 [<span data-ttu-id="cd48c-127">Instantâneos de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd48c-127">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
