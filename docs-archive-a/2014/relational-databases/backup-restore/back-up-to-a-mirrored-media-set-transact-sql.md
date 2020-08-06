---
title: Fazer backup de um conjunto de mídias espelhado (Transact-SQL)   Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 5fc43a5d-dfd6-4c53-a4ef-3c8da23ccc81
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 255a3c190139c029f5211dcab9780b6d07d975a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574740"
---
# <a name="back-up-to-a-mirrored-media-set-transact-sql"></a><span data-ttu-id="a9c6c-102">Fazer backup em um conjunto de mídias espelhado (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a9c6c-102">Back Up to a Mirrored Media Set (Transact-SQL)</span></span>
  <span data-ttu-id="a9c6c-103">Este tópico descreve como usar a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] [backup](/sql/t-sql/statements/backup-transact-sql) para especificar um conjunto de mídias espelhadas ao fazer backup de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] banco de dados do.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to specify a mirrored media set when backing up a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="a9c6c-104">Na instrução BACKUP, especifique o primeiro espelho na cláusula TO.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-104">In your BACKUP statement, specify the first mirror in the TO clause.</span></span> <span data-ttu-id="a9c6c-105">Em seguida, especifique cada espelho em sua própria cláusula MIRROR TO.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-105">Then, specify each mirror in its own MIRROR TO clause.</span></span> <span data-ttu-id="a9c6c-106">As cláusulas TO e MIRROR TO devem especificar o mesmo número e tipo de dispositivos de backup.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-106">The TO and MIRROR TO clauses must specify the same number and type of backup devices.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9c6c-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a9c6c-107">Example</span></span>  
 <span data-ttu-id="a9c6c-108">O exemplo a seguir cria o conjunto de mídias espelhado mostrado na ilustração anterior e faz backup do banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] para ambos os espelhos.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-108">The following example creates the mirrored media set illustrated in the previous illustration and backs up the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to both mirrors.</span></span>  
  
```  
BACKUP DATABASE AdventureWorks2012  
TO TAPE = '\\.\tape0', TAPE = '\\.\tape1'  
MIRROR TO TAPE = '\\.\tape2', TAPE = '\\.\tape3'  
WITH  
    FORMAT,  
    MEDIANAME = 'AdventureWorks2012Set1';  
GO  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="a9c6c-109">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a9c6c-109">Related Tasks</span></span>  
 <span data-ttu-id="a9c6c-110">**Para restaurar um backup espelhado**</span><span class="sxs-lookup"><span data-stu-id="a9c6c-110">**To restore from a mirrored backup**</span></span>  
  
-   [<span data-ttu-id="a9c6c-111">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a9c6c-111">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="a9c6c-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a9c6c-112">See Also</span></span>  
 <span data-ttu-id="a9c6c-113">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a9c6c-113">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="a9c6c-114">Conjuntos de mídias de backup espelhadas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a9c6c-114">Mirrored Backup Media Sets &#40;SQL Server&#41;</span></span>](mirrored-backup-media-sets-sql-server.md)  
  
  
