---
title: Remover a testemunha de uma sessão de espelhamento de banco de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], turning off
- witness [SQL Server], removing
- database mirroring [SQL Server], witness
ms.assetid: f3ce7afc-8936-4d35-80ce-d0f8fbc318d3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5ede54aca3588a6fcd7cee8759112b606eac752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681152"
---
# <a name="remove-the-witness-from-a-database-mirroring-session-sql-server"></a><span data-ttu-id="62d49-102">Remover a testemunha de uma sessão de espelhamento de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="62d49-102">Remove the Witness from a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="62d49-103">Este tópico descreve como remover uma testemunha de uma sessão de espelhamento de banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62d49-103">This topic describes how to remove a witness from a database mirroring session in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="62d49-104">Em qualquer momento durante uma sessão de espelhamento de banco de dados, o proprietário do banco de dados pode desativar a testemunha da sessão de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="62d49-104">At any time during a database mirroring session, the database owner can turn off the witness for a database mirroring session.</span></span>  
  
 <span data-ttu-id="62d49-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="62d49-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="62d49-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="62d49-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="62d49-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="62d49-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="62d49-108">**Para Substituir, remova a testemunha, usando:**</span><span class="sxs-lookup"><span data-stu-id="62d49-108">**To Replace remove the witness, using:**</span></span>  
  
     [<span data-ttu-id="62d49-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="62d49-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="62d49-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="62d49-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="62d49-111">**Acompanhamento:**  [depois de remover a testemunha](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="62d49-111">**Follow Up:**  [After Removing the Witness](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="62d49-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="62d49-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="62d49-113">Segurança</span><span class="sxs-lookup"><span data-stu-id="62d49-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="62d49-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="62d49-114">Permissions</span></span>  
 <span data-ttu-id="62d49-115">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="62d49-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="62d49-116">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="62d49-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="62d49-117">Para remover a testemunha</span><span class="sxs-lookup"><span data-stu-id="62d49-117">To remove the witness</span></span>  
  
1.  <span data-ttu-id="62d49-118">Conecte-se à instância do servidor principal e, no painel **Pesquisador de Objetos** , clique no nome do servidor para expandir a árvore do servidor.</span><span class="sxs-lookup"><span data-stu-id="62d49-118">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="62d49-119">Expanda **Bancos de Dados**e selecione o banco de dados cuja testemunha deseja remover.</span><span class="sxs-lookup"><span data-stu-id="62d49-119">Expand **Databases**, and select the database whose witness you want to remove.</span></span>  
  
3.  <span data-ttu-id="62d49-120">Clique com o botão direito do mouse no banco de dados, selecione **Tarefas**e clique em **Espelhar**.</span><span class="sxs-lookup"><span data-stu-id="62d49-120">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="62d49-121">Isso abre a página **Espelhamento** da caixa de diálogo **Propriedades do Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="62d49-121">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="62d49-122">Para remover o servidor testemunha, exclua seu endereço de rede do campo **Testemunha** .</span><span class="sxs-lookup"><span data-stu-id="62d49-122">To remove the witness, delete its server network address from the **Witness** field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="62d49-123">Se você mudar do modo de alta segurança com failover automático para o modo de alto desempenho, o campo **Testemunha** será desmarcado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="62d49-123">If you switch from high-safety mode with automatic failover to high-performance mode, the **Witness** field is automatically cleared.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="62d49-124">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="62d49-124">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="62d49-125">Para remover a testemunha</span><span class="sxs-lookup"><span data-stu-id="62d49-125">To remove the witness</span></span>  
  
1.  <span data-ttu-id="62d49-126">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)] em qualquer instância de servidor de parceiro.</span><span class="sxs-lookup"><span data-stu-id="62d49-126">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on either partner server instance.</span></span>  
  
2.  <span data-ttu-id="62d49-127">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="62d49-127">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="62d49-128">Emita a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="62d49-128">Issue the following statement:</span></span>  
  
     <span data-ttu-id="62d49-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET WITNESS OFF</span><span class="sxs-lookup"><span data-stu-id="62d49-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET WITNESS OFF</span></span>  
  
     <span data-ttu-id="62d49-130">em que *database_name* é o nome do banco de dados espelhado.</span><span class="sxs-lookup"><span data-stu-id="62d49-130">where *database_name* is the name of the mirrored database.</span></span>  
  
     <span data-ttu-id="62d49-131">O exemplo a seguir remove a testemunha do banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62d49-131">The following example removes the witness from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET WITNESS OFF ;  
    ```  
  
##  <a name="follow-up-after-removing-the-witness"></a><a name="FollowUp"></a><span data-ttu-id="62d49-132">Acompanhamento: depois de remover a testemunha</span><span class="sxs-lookup"><span data-stu-id="62d49-132">Follow Up: After Removing the Witness</span></span>  
 <span data-ttu-id="62d49-133">A desativação da testemunha altera o [modo operacional](database-mirroring-operating-modes.md)conforme a configuração de segurança da transação:</span><span class="sxs-lookup"><span data-stu-id="62d49-133">Turning off the witness changes the [operating mode](database-mirroring-operating-modes.md)in accordance with the transaction-safety setting:</span></span>  
  
-   <span data-ttu-id="62d49-134">Se segurança de transação estiver definida como FULL (o padrão), a sessão usará o modo síncrono de alta proteção sem failover automático.</span><span class="sxs-lookup"><span data-stu-id="62d49-134">If transaction safety is set to FULL (the default), the session uses high-safety, synchronous mode without automatic failover.</span></span>  
  
-   <span data-ttu-id="62d49-135">Se a segurança de transação estiver definida como OFF, a sessão irá operar de modo assíncrono (em modo de alto desempenho) sem exigir quorum.</span><span class="sxs-lookup"><span data-stu-id="62d49-135">If transaction safety is set to OFF, the session operates asynchronously (in high-performance mode) without requiring quorum.</span></span> <span data-ttu-id="62d49-136">Sempre que a segurança de transação estiver desativada, é recomendável desativar também a testemunha.</span><span class="sxs-lookup"><span data-stu-id="62d49-136">Whenever transaction safety is turned off, we strongly recommend also turning the witness off.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="62d49-137">A configuração de segurança de transação do banco de dados é registrada em cada parceiro na exibição de catálogo [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql) nas colunas **mirroring_safety_level** e **mirroring_safety_level_desc**.</span><span class="sxs-lookup"><span data-stu-id="62d49-137">The transaction safety setting of the database is recorded on each partner in the [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql) catalog view in the **mirroring_safety_level** and **mirroring_safety_level_desc** columns.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="62d49-138">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="62d49-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="62d49-139">Adicionar uma testemunha de espelhamento de banco de dados usando a Autenticação do Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="62d49-139">Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="62d49-140">Adicionar ou substituir uma testemunha de espelhamento de banco de dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="62d49-140">Add or Replace a Database Mirroring Witness &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/add-or-replace-a-database-mirroring-witness-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="62d49-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="62d49-141">See Also</span></span>  
 <span data-ttu-id="62d49-142">[Espelhamento de banco de dados ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="62d49-142">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="62d49-143">[Alterar a segurança da transação em uma sessão de espelhamento de banco de dados &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="62d49-143">[Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="62d49-144">[Adicionar uma testemunha de espelhamento de banco de dados usando a autenticação do Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="62d49-144">[Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="62d49-145">Testemunha de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="62d49-145">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
