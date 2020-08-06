---
title: Definir o período de expiração da assinatura | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication], expiration
- expiration [SQL Server replication]
- retention periods [SQL Server replication]
- deactivating subscriptions
ms.assetid: 542f0613-5817-42d0-b841-fb2c94010665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bc0ecb449af64b88cf3ded032c78c2e399dd4234
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574652"
---
# <a name="set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="60400-102">Definir o período de validade da assinatura</span><span class="sxs-lookup"><span data-stu-id="60400-102">Set the Expiration Period for Subscriptions</span></span>
  <span data-ttu-id="60400-103">Este tópico descreve como definir o período de validade para assinaturas no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60400-103">This topic describes how to set the expiration period for subscriptions in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="60400-104">O período de validade das assinaturas determina o período de tempo antes de uma assinatura expirar e ser removida.</span><span class="sxs-lookup"><span data-stu-id="60400-104">The expiration period for subscriptions determines the period of time before a subscription expires and is removed.</span></span> <span data-ttu-id="60400-105">Para obter mais informações, consulte [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="60400-105">For more information, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="60400-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="60400-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="60400-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="60400-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="60400-108">Recomendações</span><span class="sxs-lookup"><span data-stu-id="60400-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="60400-109">**Para definir o período de validade da assinatura, usando:**</span><span class="sxs-lookup"><span data-stu-id="60400-109">**To set the expiration period for subscriptions, using:**</span></span>  
  
     [<span data-ttu-id="60400-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60400-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="60400-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60400-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="60400-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="60400-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="60400-113">Recomendações</span><span class="sxs-lookup"><span data-stu-id="60400-113">Recommendations</span></span>  
  
-   <span data-ttu-id="60400-114">O período de validade da assinatura também é referenciado como o *período de retenção da publicação*.</span><span class="sxs-lookup"><span data-stu-id="60400-114">The subscription expiration period is also referred to as the *publication retention period*.</span></span> <span data-ttu-id="60400-115">A limpeza dos metadados de replicação de mesclagem depende dessa configuração:</span><span class="sxs-lookup"><span data-stu-id="60400-115">Cleanup of merge replication metadata is dependent on this setting:</span></span>  
  
    -   <span data-ttu-id="60400-116">A replicação não poderá limpar os metadados na publicação e nos bancos de dados de assinatura antes de o período de retenção ser atingido.</span><span class="sxs-lookup"><span data-stu-id="60400-116">Replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="60400-117">Cuidado ao especificar um valor alto para o período de retenção, pois poderá impactar negativamente o desempenho da replicação.</span><span class="sxs-lookup"><span data-stu-id="60400-117">Use caution in specifying a high value for the retention period, because it can negatively impact replication performance.</span></span> <span data-ttu-id="60400-118">Recomendamos que use uma definição mais baixa se puder prevenir com certeza que todos os Assinantes sincronizarão normalmente dentro daquele período de tempo.</span><span class="sxs-lookup"><span data-stu-id="60400-118">It is recommended that you use a lower setting if you can reliably predict that all Subscribers will synchronize regularly within that time period.</span></span>  
  
         <span data-ttu-id="60400-119">O período de retenção para publicações de mesclagem tem um período de tolerância de 24 horas para incluir os Assinantes em fusos horários diferentes.</span><span class="sxs-lookup"><span data-stu-id="60400-119">The retention period for merge publications has a 24-hour grace period to accommodate Subscribers in different time zones.</span></span> <span data-ttu-id="60400-120">Por exemplo, se você definir um período de retenção de um dia, o período de retenção real será de 48 horas.</span><span class="sxs-lookup"><span data-stu-id="60400-120">If, for example, you set a retention period of one day, the actual retention period is 48 hours.</span></span>  
  
    -   <span data-ttu-id="60400-121">É possível especificar para que as assinaturas nunca expirem, mas recomendamos não usar este valor, pois os metadados não poderão ser limpos.</span><span class="sxs-lookup"><span data-stu-id="60400-121">It is possible to specify that subscriptions never expire, but it is strongly recommended that you do not use this value, because metadata cannot be cleaned up.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="60400-122">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60400-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="60400-123">Defina o período de expiração da assinatura na página **Geral** da caixa de diálogo **Propriedades de Publicação – \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="60400-123">Set the expiration period for subscriptions on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="60400-124">Para obter mais informações sobre como acessar essa caixa de diálogo, consulte [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="60400-124">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="60400-125">Para definir o período de validade da assinatura</span><span class="sxs-lookup"><span data-stu-id="60400-125">To set the expiration period for subscriptions</span></span>  
  
1.  <span data-ttu-id="60400-126">Na seção **Expiração da assinatura**, na página **Geral** da caixa de diálogo **Propriedades de Publicação – \<Publication>** , especifique se as assinaturas devem expirar.</span><span class="sxs-lookup"><span data-stu-id="60400-126">In the **Subscription expiration** section on the **General** page of the **Publication Properties - \<Publication>** dialog box, specify whether subscriptions should expire.</span></span>  
  
2.  <span data-ttu-id="60400-127">Caso devam vencer, especifique um período de tempo para o vencimento.</span><span class="sxs-lookup"><span data-stu-id="60400-127">If they should expire, specify an expiration time period.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="60400-128">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="60400-128">Using Transact-SQL</span></span>  
 <span data-ttu-id="60400-129">Você pode usar os procedimentos armazenados de replicação para definir este valor quando uma publicação é criada ou para modificar este valor posteriormente.</span><span class="sxs-lookup"><span data-stu-id="60400-129">You can use replication stored procedures to either set this value when a publication is created or modify this value at a later time.</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="60400-130">Para definir o período de validade de uma assinatura de um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="60400-130">To set the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="60400-131">No Publicador, execute [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60400-131">At the Publisher, execute [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span> <span data-ttu-id="60400-132">Especifique o período de validade de assinatura desejado, em horas, em **\@retention**.</span><span class="sxs-lookup"><span data-stu-id="60400-132">Specify the desired subscription expiration period, in hours, for **\@retention**.</span></span> <span data-ttu-id="60400-133">O período de validade padrão é de 336 horas.</span><span class="sxs-lookup"><span data-stu-id="60400-133">The default expiration period is 336 hours.</span></span> <span data-ttu-id="60400-134">Para obter mais informações, consulte [Criar uma assinatura](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="60400-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="60400-135">Para definir o período de validade para uma assinatura de uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="60400-135">To set the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="60400-136">No Publicador, execute [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60400-136">At the Publisher, execute [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span></span> <span data-ttu-id="60400-137">Especifique o valor desejado para o período de validade da assinatura em **\@retention**.</span><span class="sxs-lookup"><span data-stu-id="60400-137">Specify the desired value for the subscription expiration period for **\@retention**.</span></span> <span data-ttu-id="60400-138">Especifique as unidades nas quais o período de validade é expresso em **\@retention_period_unit**, que pode ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="60400-138">Specify the units in which the expiration period is expressed for **\@retention_period_unit**, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="60400-139">**1** = semana</span><span class="sxs-lookup"><span data-stu-id="60400-139">**1** = week</span></span>  
  
    -   <span data-ttu-id="60400-140">**2** = mês</span><span class="sxs-lookup"><span data-stu-id="60400-140">**2** = month</span></span>  
  
    -   <span data-ttu-id="60400-141">**3** = ano</span><span class="sxs-lookup"><span data-stu-id="60400-141">**3** = year</span></span>  
  
     <span data-ttu-id="60400-142">O período de validade padrão é de 14 dias.</span><span class="sxs-lookup"><span data-stu-id="60400-142">The default expiration period is 14 days.</span></span> <span data-ttu-id="60400-143">Para obter mais informações, consulte [Criar uma assinatura](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="60400-143">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="60400-144">Para alterar o período de validade de uma assinatura de um instantâneo ou publicação transacional</span><span class="sxs-lookup"><span data-stu-id="60400-144">To change the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="60400-145">No Publicador, execute [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60400-145">At the Publisher, execute [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span> <span data-ttu-id="60400-146">Especifique **retention** em **\@property** e o novo período de validade da assinatura, em horas, em **\@value**.</span><span class="sxs-lookup"><span data-stu-id="60400-146">Specify **retention** for **\@property** and the new subscription expiration period, in hours, for **\@value**.</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="60400-147">Para alterar o período de validade para uma assinatura de uma publicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="60400-147">To change the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="60400-148">No Publicador, execute [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql) especificando **\@publication** e **\@publisher**.</span><span class="sxs-lookup"><span data-stu-id="60400-148">At the Publisher, execute [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying **\@publication** and **\@publisher**.</span></span> <span data-ttu-id="60400-149">Observe o valor de **retention_period_unit** no conjunto de resultados que pode ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="60400-149">Note the value of **retention_period_unit** in the result set, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="60400-150">**0** = dia|</span><span class="sxs-lookup"><span data-stu-id="60400-150">**0** = day</span></span>  
  
    -   <span data-ttu-id="60400-151">**1** = semana</span><span class="sxs-lookup"><span data-stu-id="60400-151">**1** = week</span></span>  
  
    -   <span data-ttu-id="60400-152">**2** = mês</span><span class="sxs-lookup"><span data-stu-id="60400-152">**2** = month</span></span>  
  
    -   <span data-ttu-id="60400-153">**3** = ano</span><span class="sxs-lookup"><span data-stu-id="60400-153">**3** = year</span></span>  
  
2.  <span data-ttu-id="60400-154">No Publicador, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60400-154">At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="60400-155">Especifique **retention** em **\@property** e o novo período de validade da assinatura, como texto com base na unidade de período de retenção da etapa 1, em **\@value**.</span><span class="sxs-lookup"><span data-stu-id="60400-155">Specify **retention** for **\@property** and the new subscription expiration period, as text based on the retention period unit from step 1, for **\@value**.</span></span>  
  
3.  <span data-ttu-id="60400-156">(Opcional) No Editor, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="60400-156">(Optional) At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="60400-157">Especifique **retention_period_unit** em **\@property** e uma nova unidade para o período de validade da assinatura em **\@value**.</span><span class="sxs-lookup"><span data-stu-id="60400-157">Specify **retention_period_unit** for **\@property** and a new unit for the subscription expiration period for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60400-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="60400-158">See Also</span></span>  
 <span data-ttu-id="60400-159">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="60400-159">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="60400-160">Desativação e expiração de assinatura</span><span class="sxs-lookup"><span data-stu-id="60400-160">Subscription Expiration and Deactivation</span></span>](../subscription-expiration-and-deactivation.md)  
  
  
