---
title: Configurar o trabalho do conjunto de transações para um Publicador Oracle (Programação Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_publisherproperty
- Oracle publishing [SQL Server replication], configuring
ms.assetid: beea1a5c-0053-4971-a68f-0da53063fcbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 43a25ce755a505f0efd7c25243b8969a962ea701
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685591"
---
# <a name="configure-the-transaction-set-job-for-an-oracle-publisher-replication-transact-sql-programming"></a><span data-ttu-id="6aab5-102">Configurar o trabalho do conjunto de transações para um Publicador Oracle (programação Transact-SQL de replicação)</span><span class="sxs-lookup"><span data-stu-id="6aab5-102">Configure the Transaction Set Job for an Oracle Publisher (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="6aab5-103">O trabalho **Xactset** é um banco de dados Oracle criado pela replicação em execução em um Editor Oracle, para criar conjuntos de transações, quando o Log Reader Agent não está conectado ao Publicador.</span><span class="sxs-lookup"><span data-stu-id="6aab5-103">The **Xactset** job is an Oracle database job created by replication that runs at an Oracle Publisher to create transaction sets when the Log Reader Agent is not connected to the Publisher.</span></span> <span data-ttu-id="6aab5-104">Você pode ativar e configurar esse trabalho do Distribuidor usando os procedimentos armazenados de replicação programaticamente.</span><span class="sxs-lookup"><span data-stu-id="6aab5-104">You can enable and configure this job from the Distributor programmatically using replication stored procedures.</span></span> <span data-ttu-id="6aab5-105">Para obter mais informações, consulte [Ajuste de desempenho para Publicadores Oracle](../non-sql/performance-tuning-for-oracle-publishers.md).</span><span class="sxs-lookup"><span data-stu-id="6aab5-105">For more information, see [Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md).</span></span>  
  
### <a name="to-enable-the-transaction-set-job"></a><span data-ttu-id="6aab5-106">Habilitar o conjunto de trabalho de transação</span><span class="sxs-lookup"><span data-stu-id="6aab5-106">To enable the transaction set job</span></span>  
  
1.  <span data-ttu-id="6aab5-107">No Editor Oracle, defina o parâmetro de inicialização **job_queue_processes** com um valor que seja suficiente para permitir a execução do trabalho Xactset.</span><span class="sxs-lookup"><span data-stu-id="6aab5-107">At the Oracle Publisher, set the **job_queue_processes** initialization parameter to a sufficient value to allow the Xactset job run.</span></span> <span data-ttu-id="6aab5-108">Para obter mais informações sobre esse parâmetro, veja a documentação de banco de dados para o Editor Oracle.</span><span class="sxs-lookup"><span data-stu-id="6aab5-108">For more information about this parameter, see the database documentation for the Oracle Publisher.</span></span>  
  
2.  <span data-ttu-id="6aab5-109">No Distribuidor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6aab5-109">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="6aab5-110">Especifique o nome do editor Oracle para o \*\* \@ Publicador**, um valor de `xactsetbatching` para \*\* \@ PropertyName**e um valor de `enabled` para \*\* \@ PropertyValue\*\*.</span><span class="sxs-lookup"><span data-stu-id="6aab5-110">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetbatching` for **\@propertyname**, and a value of `enabled` for **\@propertyvalue**.</span></span>  
  
3.  <span data-ttu-id="6aab5-111">No Distribuidor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6aab5-111">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="6aab5-112">Especifique o nome do editor Oracle para o \*\* \@ Publicador**, um valor de `xactsetjobinterval` para \*\* \@ PropertyName**e o intervalo de trabalho, em minutos, para \*\* \@ PropertyValue\*\*.</span><span class="sxs-lookup"><span data-stu-id="6aab5-112">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjobinterval` for **\@propertyname**, and the job interval, in minutes, for **\@propertyvalue**.</span></span>  
  
4.  <span data-ttu-id="6aab5-113">No Distribuidor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6aab5-113">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="6aab5-114">Especifique o nome do editor Oracle para o \*\* \@ Publicador**, um valor de `xactsetjob` para \*\* \@ PropertyName**e um valor de `enabled` para \*\* \@ PropertyValue\*\*.</span><span class="sxs-lookup"><span data-stu-id="6aab5-114">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjob` for **\@propertyname**, and a value of `enabled` for **\@propertyvalue**.</span></span>  
  
### <a name="to-configure-the-transaction-set-job"></a><span data-ttu-id="6aab5-115">Para configurar o trabalho de conjunto de transação</span><span class="sxs-lookup"><span data-stu-id="6aab5-115">To configure the transaction set job</span></span>  
  
1.  <span data-ttu-id="6aab5-116">(opcional) No Distribuidor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6aab5-116">(Optional) At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="6aab5-117">Especifique o nome do Publicador Oracle em **\@publisher**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-117">Specify the name of the Oracle Publisher for **\@publisher**.</span></span> <span data-ttu-id="6aab5-118">Isso retorna as propriedades do trabalho **Xactset** no Publicador.</span><span class="sxs-lookup"><span data-stu-id="6aab5-118">This returns properties of the **Xactset** job at the Publisher.</span></span>  
  
2.  <span data-ttu-id="6aab5-119">No Distribuidor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6aab5-119">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="6aab5-120">Especifique o nome do editor Oracle para o \*\* \@ Publicador**, o nome da Propriedade do trabalho Xactset que está sendo definida para \*\* \@ PropertyName**e a nova configuração para \*\* \@ PropertyValue\*\*.</span><span class="sxs-lookup"><span data-stu-id="6aab5-120">Specify the name of the Oracle Publisher for **\@publisher**, the name of the Xactset job property being set for **\@propertyname**, and new setting for **\@propertyvalue**.</span></span>  
  
3.  <span data-ttu-id="6aab5-121">(Opcional) Repita a etapa 2 para cada propriedade de trabalho Xactset que estiver sendo definida.</span><span class="sxs-lookup"><span data-stu-id="6aab5-121">(Optional) Repeat step 2 for each Xactset job property being set.</span></span> <span data-ttu-id="6aab5-122">Ao alterar a `xactsetjobinterval` propriedade, você deve reiniciar o trabalho no Publicador Oracle para que o novo intervalo entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="6aab5-122">When changing the `xactsetjobinterval` property, you must restart the job on the Oracle Publisher for the new interval to take effect.</span></span>  
  
### <a name="to-view-properties-of-the-transaction-set-job"></a><span data-ttu-id="6aab5-123">Para exibir as propriedades do trabalho de conjunto de transação</span><span class="sxs-lookup"><span data-stu-id="6aab5-123">To view properties of the transaction set job</span></span>  
  
1.  <span data-ttu-id="6aab5-124">No Distributor, execute [sp_helpxactsetjob](/sql/relational-databases/system-stored-procedures/sp-helpxactsetjob-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6aab5-124">At the Distributor, execute [sp_helpxactsetjob](/sql/relational-databases/system-stored-procedures/sp-helpxactsetjob-transact-sql).</span></span> <span data-ttu-id="6aab5-125">Especifique o nome do Publicador Oracle em **\@publisher**.</span><span class="sxs-lookup"><span data-stu-id="6aab5-125">Specify the name of the Oracle Publisher for **\@publisher**.</span></span>  
  
### <a name="to-disable-the-transaction-set-job"></a><span data-ttu-id="6aab5-126">Para desativar o trabalho de conjunto de transação</span><span class="sxs-lookup"><span data-stu-id="6aab5-126">To disable the transaction set job</span></span>  
  
1.  <span data-ttu-id="6aab5-127">No Distribuidor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6aab5-127">At the Distributor, execute [sp_publisherproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-publisherproperty-transact-sql).</span></span> <span data-ttu-id="6aab5-128">Especifique o nome do editor Oracle para o \*\* \@ Publicador**, um valor de `xactsetjob` para \*\* \@ PropertyName**e um valor de `disabled` para \*\* \@ PropertyValue\*\*.</span><span class="sxs-lookup"><span data-stu-id="6aab5-128">Specify the name of the Oracle Publisher for **\@publisher**, a value of `xactsetjob` for **\@propertyname**, and a value of `disabled` for **\@propertyvalue**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aab5-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6aab5-129">Example</span></span>  
 <span data-ttu-id="6aab5-130">O exemplo a seguir habilita o trabalho `Xactset` e define um intervalo de três minutos entre as execuções.</span><span class="sxs-lookup"><span data-stu-id="6aab5-130">The following example enables the `Xactset` job and sets an interval of three minutes between runs.</span></span>  
  
 [!code-sql[HowTo#sp_enable_xactsetjob](../../../snippets/tsql/SQL15/replication/howto/tsql/enablexactsetjob.sql#sp_enable_xactsetjob)]  
  
## <a name="see-also"></a><span data-ttu-id="6aab5-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6aab5-131">See Also</span></span>  
 <span data-ttu-id="6aab5-132">[Ajuste de desempenho para Publicadores Oracle](../non-sql/performance-tuning-for-oracle-publishers.md) </span><span class="sxs-lookup"><span data-stu-id="6aab5-132">[Performance Tuning for Oracle Publishers](../non-sql/performance-tuning-for-oracle-publishers.md) </span></span>  
 [<span data-ttu-id="6aab5-133">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="6aab5-133">Replication System Stored Procedures Concepts</span></span>](../concepts/replication-system-stored-procedures-concepts.md)  
  
  
