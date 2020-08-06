---
title: Backup e restauração para Publicadores Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], Oracle publishing
- backups [SQL Server replication], Oracle publishing
- Oracle publishing [SQL Server replication], backup and restore
- restoring [SQL Server replication], Oracle publishing
ms.assetid: e5f181d0-cacf-442b-8b7a-202b3cfc358b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6b994c34e4f4bebc010fe6d71bbd43f6e557cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569358"
---
# <a name="backup-and-restore-for-oracle-publishers"></a><span data-ttu-id="3afa9-102">Backup e restauração para Publicadores Oracle</span><span class="sxs-lookup"><span data-stu-id="3afa9-102">Backup and Restore for Oracle Publishers</span></span>
  <span data-ttu-id="3afa9-103">Siga essas diretrizes ao realizar backup e restauração:</span><span class="sxs-lookup"><span data-stu-id="3afa9-103">Follow these guidelines when backing up and restoring:</span></span>  
  
-   <span data-ttu-id="3afa9-104">Assegure-se de que o Log Reader Agent não está sendo executado e que não haja outras atividades de banco de dados nas tabelas publicadas enquanto o Publicador estiver passando por backup.</span><span class="sxs-lookup"><span data-stu-id="3afa9-104">Ensure the Log Reader Agent does not run and that other database activity on the published tables does not occur while the Publisher is being backed up.</span></span>  
  
-   <span data-ttu-id="3afa9-105">Efetue backup do Publicador e do Distribuidor ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="3afa9-105">Backup up the Publisher and Distributor at the same time.</span></span>  
  
-   <span data-ttu-id="3afa9-106">Se houver necessidade de restaurar o Publicador ou o Distribuidor, reinicialize todas as assinaturas.</span><span class="sxs-lookup"><span data-stu-id="3afa9-106">If the Publisher or Distributor must be restored, reinitialize all subscriptions.</span></span>  
  
-   <span data-ttu-id="3afa9-107">Para restaurar um Assinante de um backup (sem ter de reinicializar as assinaturas), as transações entregues ao banco de dados de distribuição após a conclusão do último backup de banco de dados de assinatura ainda devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3afa9-107">To restore a Subscriber from a backup (without having to reinitialize subscriptions), the transactions delivered to the distribution database after the last subscription database backup was completed must still be available.</span></span> <span data-ttu-id="3afa9-108">O tempo em que as transações estão disponíveis depende das configurações de retenção de distribuição.</span><span class="sxs-lookup"><span data-stu-id="3afa9-108">The length of time transactions are available depends on distribution retention settings.</span></span> <span data-ttu-id="3afa9-109">Para obter informações sobre essas configurações, consulte [Desativação e expiração de assinatura](../subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="3afa9-109">For information on these settings, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="3afa9-110">Se o Publicador ou o Distribuidor ficar fora de sincronia como resultado de uma restauração de banco de dados, os agentes de replicação registrarão mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="3afa9-110">If the Publisher or Distributor becomes out of sync as the result of a database restore, the replication agents log error messages.</span></span> <span data-ttu-id="3afa9-111">Nesse ponto, você deve descartar e recriar todas as publicações e assinaturas relevantes:</span><span class="sxs-lookup"><span data-stu-id="3afa9-111">At this point, you must drop and recreate all relevant publications and subscriptions:</span></span>  
  
    1.  <span data-ttu-id="3afa9-112">Faça um script da definição das publicações e assinaturas.</span><span class="sxs-lookup"><span data-stu-id="3afa9-112">Script the definition of the publications and subscriptions.</span></span> <span data-ttu-id="3afa9-113">Para obter mais informações, consulte [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="3afa9-113">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
         <span data-ttu-id="3afa9-114">Se a definição das publicações tiver sido alterada entre as versões presentes no Publicador e no Distribuidor, você precisará modificar os scripts.</span><span class="sxs-lookup"><span data-stu-id="3afa9-114">If the definition of the publications has changed between the versions of the Publisher and Distributor states, you will need to modify the scripts.</span></span>  
  
    2.  <span data-ttu-id="3afa9-115">Descarte as publicações e as assinaturas.</span><span class="sxs-lookup"><span data-stu-id="3afa9-115">Drop the publications and subscriptions.</span></span>  
  
    3.  <span data-ttu-id="3afa9-116">Execute os scripts criados na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3afa9-116">Run the scripts created in step 1.</span></span>  
  
     <span data-ttu-id="3afa9-117">Se houver necessidade de descartar e reconfigurar o Publicador, descarte o sinônimo público **MSSQLSERVERDISTRIBUTOR** e configure o usuário de replicação Oracle com a opção **CASCADE** para remover todos os objetos de replicação do Oracle Publisher.</span><span class="sxs-lookup"><span data-stu-id="3afa9-117">If the Publisher must be dropped and reconfigured, drop the **MSSQLSERVERDISTRIBUTOR** public synonym and the configured Oracle replication user with the **CASCADE** option to remove all replication objects from the Oracle Publisher.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3afa9-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3afa9-118">See Also</span></span>  
 <span data-ttu-id="3afa9-119">[Fazer backup e restaurar bancos de dados replicados](../administration/back-up-and-restore-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="3afa9-119">[Back Up and Restore Replicated Databases](../administration/back-up-and-restore-replicated-databases.md) </span></span>  
 <span data-ttu-id="3afa9-120">[Configurar um Publicador Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="3afa9-120">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="3afa9-121">Visão geral da publicação do Oracle</span><span class="sxs-lookup"><span data-stu-id="3afa9-121">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  
