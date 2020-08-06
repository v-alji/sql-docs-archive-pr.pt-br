---
title: Habilitar ou desabilitar a coleta de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], disabling
- data collector [SQL Server], enabling
ms.assetid: 0137971b-fb48-4a3e-822a-3df2b9bb09d7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af5cc647a63d3a9451086fc9e2211dec809e88fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570708"
---
# <a name="enable-or-disable-data-collection"></a><span data-ttu-id="b2914-102">Habilitar ou desabilitar a coleta de dados</span><span class="sxs-lookup"><span data-stu-id="b2914-102">Enable or Disable Data Collection</span></span>
  <span data-ttu-id="b2914-103">Este tópico descreve como habilitar ou desabilitar a coleta de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2914-103">This topic describes how to enable or disable data collection in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b2914-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="b2914-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b2914-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="b2914-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b2914-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="b2914-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b2914-107">**Para habilitar ou desabilitar a coleta de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="b2914-107">**To enable or disable data collection, using:**</span></span>  
  
     [<span data-ttu-id="b2914-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2914-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b2914-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b2914-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b2914-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b2914-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b2914-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="b2914-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b2914-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="b2914-112">Permissions</span></span>  
 <span data-ttu-id="b2914-113">É necessária a associação na função de banco de dados fixa **dc_admin** ou **dc_operator** (com a permissão EXECUTE) para executar esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="b2914-113">Requires membership in the **dc_admin** or **dc_operator** (with EXECUTE permission) fixed database role to execute this procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b2914-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2914-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="b2914-115">Para habilitar o coletor de dados</span><span class="sxs-lookup"><span data-stu-id="b2914-115">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="b2914-116">No Pesquisador de Objetos, expanda o nó **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="b2914-116">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="b2914-117">Clique com o botão direito do mouse em **Coleta de Dados**e clique em **Habilitar Coleta de Dados**.</span><span class="sxs-lookup"><span data-stu-id="b2914-117">Right-click **Data Collection**, and then click **Enable Data Collection**.</span></span>  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="b2914-118">Para desabilitar o coletor de dados</span><span class="sxs-lookup"><span data-stu-id="b2914-118">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="b2914-119">No Pesquisador de Objetos, expanda o nó **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="b2914-119">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="b2914-120">Clique com o botão direito do mouse em **Coleta de Dados**e clique em **Desabilitar Coleta de Dados**.</span><span class="sxs-lookup"><span data-stu-id="b2914-120">Right-click **Data Collection**, and then click **Disable Data Collection**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b2914-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b2914-121">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="b2914-122">Para habilitar o coletor de dados</span><span class="sxs-lookup"><span data-stu-id="b2914-122">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="b2914-123">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2914-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b2914-124">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b2914-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b2914-125">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b2914-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b2914-126">Este exemplo usa [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) para habilitar o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="b2914-126">This example uses [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) to enable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_enable_collector ;  
```  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="b2914-127">Para desabilitar o coletor de dados</span><span class="sxs-lookup"><span data-stu-id="b2914-127">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="b2914-128">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2914-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b2914-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="b2914-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b2914-130">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b2914-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b2914-131">Este exemplo usa [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) para desabilitar o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="b2914-131">This example uses [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) to disable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_disable_collector;  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2914-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b2914-132">See Also</span></span>  
 <span data-ttu-id="b2914-133">[Coleta de Dados](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="b2914-133">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="b2914-134">Procedimentos armazenados do sistema &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b2914-134">System Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql)  
  
  
