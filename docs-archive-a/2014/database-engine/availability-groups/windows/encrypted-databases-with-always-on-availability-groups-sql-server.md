---
title: Bancos de dados criptografados com Grupos de Disponibilidade AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, AlwaysOn Availability Groups
- TDE, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 09eb6ebc-3051-4fff-86a5-93524507b1fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 91e717a896634a7df5a96253c51207831f142cff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570251"
---
# <a name="encrypted-databases-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="ebfb5-102">Bancos de dados criptografados com grupos de disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ebfb5-102">Encrypted Databases with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="ebfb5-103">Este tópico contém informações sobre como o usar bancos de dados atualmente criptografados ou recentemente descriptografados com o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebfb5-103">This topic contains information about the using currently encrypted or recently decrypted databases with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="ebfb5-104">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="ebfb5-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="ebfb5-105">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="ebfb5-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="ebfb5-106">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ebfb5-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ebfb5-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="ebfb5-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ebfb5-108">Se um banco de dados estiver criptografado ou contiver até mesmo uma DEK (chave de criptografia de banco de dados), você não poderá usar o [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] nem o [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] para adicionar um grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ebfb5-108">If a database is encrypted or even contains a Database Encryption Key (DEK), you cannot use the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] to add the database to an availability group.</span></span> <span data-ttu-id="ebfb5-109">Mesmo se um banco de dados criptografado for descriptografado, seus backups de log poderão conter dados criptografados.</span><span class="sxs-lookup"><span data-stu-id="ebfb5-109">Even if an encrypted database has been decrypted, its log backups might contain encrypted data.</span></span> <span data-ttu-id="ebfb5-110">Nesse caso, a total sincronização inicial de dados poderia falhar no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ebfb5-110">In this case, full initial data synchronization could fail on the database.</span></span> <span data-ttu-id="ebfb5-111">Isso é porque a operação de log de restauração pode exigir o certificado que foi usado pelas DEKs (chaves de criptografia de banco de dados), e esse certificado pode não estar disponível.</span><span class="sxs-lookup"><span data-stu-id="ebfb5-111">This is because the restore log operation might require the certificate that was used by the database encryption keys (DEKs), and that certificate might be unavailable.</span></span>  
  
     <span data-ttu-id="ebfb5-112">Para tornar um banco de dados descriptografado elegível para adição a um grupo de disponibilidade usando o assistente:</span><span class="sxs-lookup"><span data-stu-id="ebfb5-112">To make a decrypted database eligible to add to an availability group using the wizard:</span></span>  
  
    1.  <span data-ttu-id="ebfb5-113">Crie um backup de log do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="ebfb5-113">Create a log backup of the primary database.</span></span>  
  
    2.  <span data-ttu-id="ebfb5-114">Crie um backup completo do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="ebfb5-114">Create a full database backup of the primary database.</span></span>  
  
    3.  <span data-ttu-id="ebfb5-115">Restaure o backup do banco de dados na instância de servidor que hospeda a réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="ebfb5-115">Restore the database backup on the server instance that hosts the secondary replica.</span></span>  
  
    4.  <span data-ttu-id="ebfb5-116">Crie um novo backup de log a partir do banco de dados primário.</span><span class="sxs-lookup"><span data-stu-id="ebfb5-116">Create a new log backup from primary database.</span></span>  
  
    5.  <span data-ttu-id="ebfb5-117">Restaure esse backup de log no banco de dados secundário.</span><span class="sxs-lookup"><span data-stu-id="ebfb5-117">Restore this log backup on the secondary database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ebfb5-118">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ebfb5-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ebfb5-119">Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ebfb5-119">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="ebfb5-120">Usar o Assistente de Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ebfb5-120">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="ebfb5-121">Usar o Assistente para Adicionar Banco de Dados ao Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ebfb5-121">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="ebfb5-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ebfb5-122">See Also</span></span>  
 <span data-ttu-id="ebfb5-123">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ebfb5-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="ebfb5-124">TDE &#40;Transparent Data Encryption&#41;</span><span class="sxs-lookup"><span data-stu-id="ebfb5-124">Transparent Data Encryption &#40;TDE&#41;</span></span>](../../../relational-databases/security/encryption/transparent-data-encryption.md)  
  
  
