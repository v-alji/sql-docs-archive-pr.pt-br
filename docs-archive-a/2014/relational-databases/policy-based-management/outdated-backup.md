---
title: Backup desatualizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 307a4ad0-675a-4f97-9a3c-cedd61bdfae5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c6a944b08b15d591a9bbce47a0c0c6a8de3eb54a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575776"
---
# <a name="outdated-backup"></a><span data-ttu-id="663d0-102">Backup desatualizado</span><span class="sxs-lookup"><span data-stu-id="663d0-102">Outdated Backup</span></span>
  <span data-ttu-id="663d0-103">Esta regra verifica se um banco de dados possui backups recentes.</span><span class="sxs-lookup"><span data-stu-id="663d0-103">This rule checks that a database has recent backups.</span></span> <span data-ttu-id="663d0-104">Programar backups regulares é importante para proteger os bancos de dados contra perda de dados de muitas falhas diferentes.</span><span class="sxs-lookup"><span data-stu-id="663d0-104">Scheduling regular backups is important for protecting your databases against data loss from many different failures.</span></span> <span data-ttu-id="663d0-105">A frequência apropriada para fazer backup de dados depende do modelo de recuperação do banco de dados, dos requisitos do negócio sobre uma possível perda de dados e da frequência em que o banco de dados é atualizado.</span><span class="sxs-lookup"><span data-stu-id="663d0-105">The appropriate frequency for backing up data depends on the recovery model of the database, on business requirements about potential data loss, and on how frequently the database is updated.</span></span> <span data-ttu-id="663d0-106">Em um banco de dados atualizado frequentemente, a exposição à perda de trabalho aumenta rapidamente entre backups.</span><span class="sxs-lookup"><span data-stu-id="663d0-106">In a frequently updated database, the work-loss exposure increases fairly quickly between backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="663d0-107">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="663d0-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="663d0-108">Recomendamos que você execute backups com frequência para proteger os bancos de dados contra perda de dados.</span><span class="sxs-lookup"><span data-stu-id="663d0-108">We recommend that you perform backups frequently enough to protect databases against data loss.</span></span>  
  
 <span data-ttu-id="663d0-109">O modelo de recuperação simples e modelo de recuperação completa exigem backups de dados.</span><span class="sxs-lookup"><span data-stu-id="663d0-109">The simple recovery model and full recovery model both require data backups.</span></span> <span data-ttu-id="663d0-110">Para qualquer modelo de recuperação, é possível complementar os backups completos com backups diferenciais para reduzir com eficiência o risco de perda de dados.</span><span class="sxs-lookup"><span data-stu-id="663d0-110">For either recovery model, you can supplement your full backups with differential backups to efficiently reduce the risk of data loss.</span></span>  
  
 <span data-ttu-id="663d0-111">Para um banco de dados que usa o modelo de recuperação completa, recomendamos que faça backups de log frequentes.</span><span class="sxs-lookup"><span data-stu-id="663d0-111">For a database that uses the full recovery model, we recommend that you take frequent log backups.</span></span> <span data-ttu-id="663d0-112">Para um banco de dados de produção que contém dados muito importantes, os backups de log normalmente são feitos em intervalos de um a quinze minutos.</span><span class="sxs-lookup"><span data-stu-id="663d0-112">For a production database that contains very important data, log backups would typically be taken every one to fifteen minutes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="663d0-113">O método recomendado para agendar backups é um plano de manutenção de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="663d0-113">The recommended method for scheduling backups is a database maintenance plan.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="663d0-114">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="663d0-114">For More Information</span></span>  
 [<span data-ttu-id="663d0-115">Fazer backup e restaurar bancos de dados do sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="663d0-115">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="663d0-116">Modelos de recuperação &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="663d0-116">Recovery Models &#40;SQL Server&#41;</span></span>](../backup-restore/recovery-models-sql-server.md)  
  
 [<span data-ttu-id="663d0-117">Criar um backup diferencial de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="663d0-117">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 [<span data-ttu-id="663d0-118">Criar um backup completo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="663d0-118">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
 [<span data-ttu-id="663d0-119">Planos de manutenção</span><span class="sxs-lookup"><span data-stu-id="663d0-119">Maintenance Plans</span></span>](../maintenance-plans/maintenance-plans.md)  
  
 [<span data-ttu-id="663d0-120">Backups de log de transações &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="663d0-120">Transaction Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/transaction-log-backups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="663d0-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="663d0-121">See Also</span></span>  
 [<span data-ttu-id="663d0-122">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="663d0-122">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
