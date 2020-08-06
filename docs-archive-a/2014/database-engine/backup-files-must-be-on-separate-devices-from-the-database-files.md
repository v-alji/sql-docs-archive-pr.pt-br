---
title: Os arquivos de backup devem estar em dispositivos separados dos arquivos de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 7039bebb-1f25-4cf3-81f1-393dfb78da12
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d5eff9cb3139e1e1043f99ba63d11160b1010c27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681186"
---
# <a name="backup-files-must-be-on-separate-devices-from-the-database-files"></a><span data-ttu-id="fb28b-102">Arquivos de backup devem estar em dispositivos separados dos arquivos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="fb28b-102">Backup Files Must Be on Separate Devices from the Database Files</span></span>
  <span data-ttu-id="fb28b-103">Esta regra verifica se os arquivos de banco de dados estão em dispositivos separados dos arquivos de backup.</span><span class="sxs-lookup"><span data-stu-id="fb28b-103">This rule checks whether database files are on devices separate from the backup files.</span></span> <span data-ttu-id="fb28b-104">Se os arquivos de banco de dados e os arquivos de backup estiverem no mesmo dispositivo e o dispositivo falhar, o banco de dados e os backups não estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fb28b-104">If database files and backup files are on the same device and the device fails, the database and backups will be unavailable.</span></span> <span data-ttu-id="fb28b-105">Além disso, colocar arquivos de banco de dados e de backup em dispositivos separados otimiza o desempenho de E/S para o uso de produção do banco de dados e a gravação de backups.</span><span class="sxs-lookup"><span data-stu-id="fb28b-105">Also, putting the database and backup files on the separate devices optimizes the I/O performance for both the production use of the database and the writing of backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="fb28b-106">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="fb28b-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="fb28b-107">É extremamente recomendável que você coloque o banco de dados e os backups em dispositivos de backup separados.</span><span class="sxs-lookup"><span data-stu-id="fb28b-107">We strongly recommend that you put the database and backups on separate backup devices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb28b-108">Essa política não pode detectar dispositivos físicos separados por pontos de montagem.</span><span class="sxs-lookup"><span data-stu-id="fb28b-108">This policy cannot detect separate physical devices through mount points.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="fb28b-109">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="fb28b-109">For More Information</span></span>  
 [<span data-ttu-id="fb28b-110">Dispositivos de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fb28b-110">Backup Devices &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/backup-devices-sql-server.md)  
  
 [<span data-ttu-id="fb28b-111">Fazer backup e restaurar bancos de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb28b-111">Back Up and Restore of SQL Server Databases</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="fb28b-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fb28b-112">See Also</span></span>  
 [<span data-ttu-id="fb28b-113">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="fb28b-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
