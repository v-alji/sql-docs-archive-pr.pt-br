---
title: Mover arquivos de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- files [SQL Server], moving
- data files [SQL Server], moving
- file moving [SQL Server]
- moving full-text catalogs
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- scheduled disk maintenance [SQL Server]
- moving files
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: 89f01b10-5fae-4ed8-b0fb-a4b9f540fd28
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5491f3c4dfd47cac4047d0409c78001be80d6f13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683543"
---
# <a name="move-database-files"></a><span data-ttu-id="47f32-102">Mover arquivos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="47f32-102">Move Database Files</span></span>
  <span data-ttu-id="47f32-103">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é possível mover bancos de dados de usuários e sistemas especificando o novo local do arquivo na cláusula FILENAME da instrução [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="47f32-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move system and user databases by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="47f32-104">É possível mover arquivos de dados, logs e catálogos de texto completo deste modo.</span><span class="sxs-lookup"><span data-stu-id="47f32-104">Data, log, and full-text catalog files can be moved in this way.</span></span> <span data-ttu-id="47f32-105">Isso pode ser útil nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="47f32-105">This may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="47f32-106">Recuperação de falha.</span><span class="sxs-lookup"><span data-stu-id="47f32-106">Failure recovery.</span></span> <span data-ttu-id="47f32-107">Por exemplo, o banco de dados está em modo suspeito ou foi fechado por causa de um problema de hardware.</span><span class="sxs-lookup"><span data-stu-id="47f32-107">For example, the database is in suspect mode or has shut down, because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="47f32-108">Realocação planejada.</span><span class="sxs-lookup"><span data-stu-id="47f32-108">Planned relocation.</span></span>  
  
-   <span data-ttu-id="47f32-109">Realocação para manutenção de disco programada.</span><span class="sxs-lookup"><span data-stu-id="47f32-109">Relocation for scheduled disk maintenance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47f32-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="47f32-110">In This Section</span></span>  
  
|<span data-ttu-id="47f32-111">Tópico</span><span class="sxs-lookup"><span data-stu-id="47f32-111">Topic</span></span>|<span data-ttu-id="47f32-112">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="47f32-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="47f32-113">Mover bancos de dados de usuário</span><span class="sxs-lookup"><span data-stu-id="47f32-113">Move User Databases</span></span>](move-user-databases.md)|<span data-ttu-id="47f32-114">Descreve os procedimentos para mover arquivos de banco de dados de usuários e arquivos de catálogo de texto completo para um local novo.</span><span class="sxs-lookup"><span data-stu-id="47f32-114">Describes the procedures for moving user database files and full-text catalog files to a new location.</span></span>|  
|[<span data-ttu-id="47f32-115">Mover bancos de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="47f32-115">Move System Databases</span></span>](system-databases.md)|<span data-ttu-id="47f32-116">Descreve os procedimentos para mover arquivos de banco de dados de sistema para um novo local.</span><span class="sxs-lookup"><span data-stu-id="47f32-116">Describes the procedures for moving system database files to a new location.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47f32-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="47f32-117">See Also</span></span>  
 <span data-ttu-id="47f32-118">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="47f32-118">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="47f32-119">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="47f32-119">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="47f32-120">Anexar e desanexar bancos de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="47f32-120">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
