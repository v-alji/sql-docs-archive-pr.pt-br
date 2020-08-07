---
title: Iniciar ou interromper um conjunto de coleta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection sets [SQL Server], stopping
- collection sets [SQL Server], starting
ms.assetid: 48a7b2fe-6bc3-4278-a7ec-1babc1290345
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e37d4b2edcd7a6e048c405b072bcbf9b1fef78c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581967"
---
# <a name="start-or-stop-a-collection-set"></a><span data-ttu-id="54d04-102">Iniciar ou interromper um conjunto de coleta</span><span class="sxs-lookup"><span data-stu-id="54d04-102">Start or Stop a Collection Set</span></span>
  <span data-ttu-id="54d04-103">Este tópico descreve como iniciar ou interromper um conjunto de coleta no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54d04-103">This topic describes how to start or stop a collection set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="54d04-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="54d04-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="54d04-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="54d04-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="54d04-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="54d04-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="54d04-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="54d04-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="54d04-108">Recomendações</span><span class="sxs-lookup"><span data-stu-id="54d04-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="54d04-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="54d04-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="54d04-110">**Para iniciar ou interromper um conjunto de coleta usando:**</span><span class="sxs-lookup"><span data-stu-id="54d04-110">**To start or stop a collection set, using:**</span></span>  
  
     [<span data-ttu-id="54d04-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54d04-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="54d04-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54d04-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="54d04-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="54d04-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="54d04-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="54d04-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="54d04-115">Os procedimentos armazenados e as exibições do catálogo do coletor de dados são armazenados no banco de dados **msdb** .</span><span class="sxs-lookup"><span data-stu-id="54d04-115">Data Collector stored procedures and catalog views are stored in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="54d04-116">Diferentemente de procedimentos armazenados comuns, os procedimentos armazenados do coletor de dados usam estritamente parâmetros digitados e não oferecem suporte à conversão automática de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="54d04-116">Unlike regular stored procedures, the parameters for data collector stored procedures are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="54d04-117">Se esses parâmetros não forem chamados pelos tipos de dados com parâmetros de entrada corretos, como especificado na descrição do argumento, o procedimento armazenado retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="54d04-117">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="54d04-118">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="54d04-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="54d04-119">O SQL Server Agent deve ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="54d04-119">SQL Server Agent must be started.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="54d04-120">Recomendações</span><span class="sxs-lookup"><span data-stu-id="54d04-120">Recommendations</span></span>  
  
-   <span data-ttu-id="54d04-121">Para obter informações sobre conjuntos de coleta, consulte a exibição de catálogo [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="54d04-121">To obtain information about collection sets, query the [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) catalog view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="54d04-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="54d04-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="54d04-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="54d04-123">Permissions</span></span>  
 <span data-ttu-id="54d04-124">Exige a associação na função de banco de dados fixa **dc_operator** .</span><span class="sxs-lookup"><span data-stu-id="54d04-124">Requires membership in the **dc_operator** fixed database role.</span></span> <span data-ttu-id="54d04-125">Se o conjunto de coleta não tiver uma conta proxy, a associação da função de servidor fixa **sysadmin** será necessária. Exemplos</span><span class="sxs-lookup"><span data-stu-id="54d04-125">If the collection set does not have a proxy account, membership in the **sysadmin** fixed server role is required.Examples</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="54d04-126">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54d04-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="54d04-127">Para iniciar um conjunto de coleta</span><span class="sxs-lookup"><span data-stu-id="54d04-127">To start a collection set</span></span>  
  
1.  <span data-ttu-id="54d04-128">No Pesquisador de Objetos, expanda o nó **Gerenciamento** , expanda **Coleta de Dados**e, em seguida, **Conjuntos de Coleta de Dados do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="54d04-128">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="54d04-129">Clique com o botão direito do mouse no conjunto de coleta que deseja iniciar e clique em **Iniciar Conjunto de Coleta de Dados**.</span><span class="sxs-lookup"><span data-stu-id="54d04-129">Right-click the collection set that you want to start, and then click **Start Data Collection Set**.</span></span>  
  
     <span data-ttu-id="54d04-130">Uma caixa de mensagem exibe os resultados desta ação e uma seta verde no ícone do conjunto de coleta indica que o conjunto de coleta foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="54d04-130">A message box displays the results of this action, and a green arrow on the icon for the collection set indicates that the collection set has started.</span></span>  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="54d04-131">Para parar um conjunto de coleta</span><span class="sxs-lookup"><span data-stu-id="54d04-131">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="54d04-132">No Pesquisador de Objetos, expanda o nó **Gerenciamento** , expanda **Coleta de Dados**e, em seguida, **Conjuntos de Coleta de Dados do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="54d04-132">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="54d04-133">Clique com o botão direito do mouse no conjunto de coleta a ser interrompido e clique em **Parar Conjunto de Coleta de Dados**.</span><span class="sxs-lookup"><span data-stu-id="54d04-133">Right-click the collection set that you want to stop, and then click **Stop Data Collection Set**.</span></span>  
  
     <span data-ttu-id="54d04-134">Uma caixa de mensagem exibe os resultados dessa ação e um círculo vermelho no ícone do conjunto de coleta indica que o conjunto de coleta foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="54d04-134">A message box displays the results of this action, and a red circle on the icon for the collection set indicates that the collection set has stopped.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="54d04-135">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54d04-135">Using Transact-SQL</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="54d04-136">Para iniciar um conjunto de coleta</span><span class="sxs-lookup"><span data-stu-id="54d04-136">To start a collection set</span></span>  
  
1.  <span data-ttu-id="54d04-137">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54d04-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="54d04-138">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="54d04-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="54d04-139">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="54d04-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="54d04-140">Este exemplo usa [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) para iniciar o conjunto de coleta que tem a ID `1`.</span><span class="sxs-lookup"><span data-stu-id="54d04-140">This example uses [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) to start the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_start_collection_set @collection_set_id = 1;  
```  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="54d04-141">Para parar um conjunto de coleta</span><span class="sxs-lookup"><span data-stu-id="54d04-141">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="54d04-142">Conecte-se ao [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54d04-142">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="54d04-143">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="54d04-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="54d04-144">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="54d04-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="54d04-145">Este exemplo usa [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) para interromper o conjunto de coleta que tem a ID `1`.</span><span class="sxs-lookup"><span data-stu-id="54d04-145">This example uses [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) to stop the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_stop_collection_set @collection_set_id = 1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="54d04-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54d04-146">See Also</span></span>  
 <span data-ttu-id="54d04-147">[Exibições do Coletor de Dados &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54d04-147">[Data Collector Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span></span>  
 [<span data-ttu-id="54d04-148">Coleta de Dados</span><span class="sxs-lookup"><span data-stu-id="54d04-148">Data Collection</span></span>](data-collection.md)  
  
  
