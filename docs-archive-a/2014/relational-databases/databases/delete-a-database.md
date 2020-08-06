---
title: Excluir um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database removal [SQL Server], SQL Server Management Studio
- removing databases
- deleting databases
- dropping databases
- databases [SQL Server], dropping
- database removal [SQL Server]
ms.assetid: 1fd8c0f5-03e1-449a-af45-b8cacb479d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 633d97815cf69da12f1aa67fd8ef626a2d46e0b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685745"
---
# <a name="delete-a-database"></a><span data-ttu-id="9289f-102">Excluir um banco de dados</span><span class="sxs-lookup"><span data-stu-id="9289f-102">Delete a Database</span></span>
  <span data-ttu-id="9289f-103">Este tópico descreve como excluir um banco de dados definido pelo usuário no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9289f-103">This topic describes how to delete a user-defined database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9289f-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="9289f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9289f-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="9289f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9289f-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="9289f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9289f-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9289f-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="9289f-108">Recomendações</span><span class="sxs-lookup"><span data-stu-id="9289f-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="9289f-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="9289f-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9289f-110">**Para excluir um diagrama de banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="9289f-110">**To delete a database, using:**</span></span>  
  
     [<span data-ttu-id="9289f-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9289f-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9289f-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9289f-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="9289f-113">**Acompanhamento:**  [após excluir um banco de dados](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="9289f-113">**Follow Up:**  [After deleting a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9289f-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9289f-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9289f-115">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="9289f-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9289f-116">Bancos de dados de sistema não podem ser excluídos.</span><span class="sxs-lookup"><span data-stu-id="9289f-116">System databases cannot be deleted.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9289f-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9289f-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="9289f-118">Exclua todos os instantâneos do banco de dados que existam no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9289f-118">Delete any database snapshots that exist on the database.</span></span> <span data-ttu-id="9289f-119">Para obter mais informações, veja [Remover um instantâneo do banco de dados &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9289f-119">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
-   <span data-ttu-id="9289f-120">Se o banco de dados estiver envolvido em envio de logs, remova o envio do logs.</span><span class="sxs-lookup"><span data-stu-id="9289f-120">If the database is involved in log shipping, remove log shipping.</span></span>  
  
-   <span data-ttu-id="9289f-121">Se o banco de dados for publicado para replicação transacional, publicado ou com assinatura para replicação de mesclagem, remova a replicação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9289f-121">If the database is published for transactional replication, or published or subscribed to merge replication, remove replication from the database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9289f-122">Recomendações</span><span class="sxs-lookup"><span data-stu-id="9289f-122">Recommendations</span></span>  
  
-   <span data-ttu-id="9289f-123">Pense em fazer um backup completo do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9289f-123">Consider taking a full backup of the database.</span></span> <span data-ttu-id="9289f-124">Um banco de dados excluído só poderá ser recriado por meio da restauração de um backup.</span><span class="sxs-lookup"><span data-stu-id="9289f-124">A deleted database can be re-created only by restoring a backup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9289f-125">Segurança</span><span class="sxs-lookup"><span data-stu-id="9289f-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9289f-126">Permissões</span><span class="sxs-lookup"><span data-stu-id="9289f-126">Permissions</span></span>  
 <span data-ttu-id="9289f-127">Para executar DROP DATABASE, a um mínimo, um usuário deve ter permissão CONTROL no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9289f-127">To execute DROP DATABASE, at a minimum, a user must have CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9289f-128">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9289f-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="9289f-129">Para excluir um banco de dados</span><span class="sxs-lookup"><span data-stu-id="9289f-129">To delete a database</span></span>  
  
1.  <span data-ttu-id="9289f-130">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="9289f-130">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="9289f-131">Expanda **Bancos de Dados**, clique com o botão direito do mouse no banco de dados para excluí-lo e depois clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="9289f-131">Expand **Databases**, right-click the database to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="9289f-132">Confirme se o banco de dados correto está selecionado e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9289f-132">Confirm the correct database is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9289f-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9289f-133">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="9289f-134">Para excluir um banco de dados</span><span class="sxs-lookup"><span data-stu-id="9289f-134">To delete a database</span></span>  
  
1.  <span data-ttu-id="9289f-135">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9289f-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9289f-136">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="9289f-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9289f-137">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9289f-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9289f-138">O exemplo remove os bancos de dados `Sales` e `NewSales` .</span><span class="sxs-lookup"><span data-stu-id="9289f-138">The example removes the `Sales` and `NewSales` databases.</span></span>  
  
```sql  
USE master ;  
GO  
DROP DATABASE Sales, NewSales ;  
GO  
```  
  
##  <a name="follow-up-after-deleting-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="9289f-139">Acompanhamento: após excluir um banco de dados</span><span class="sxs-lookup"><span data-stu-id="9289f-139">Follow Up: After deleting a database</span></span>  
 <span data-ttu-id="9289f-140">Faça backup do banco de dados **mestre** .</span><span class="sxs-lookup"><span data-stu-id="9289f-140">Back up the **master** database.</span></span> <span data-ttu-id="9289f-141">Se o **mestre** precisar ser restaurado, todos os bancos de dados que tiverem sido excluídos desde o último backup do **mestre** ainda terão referências nas exibições do catálogo do sistema e poderão gerar mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="9289f-141">If **master** must be restored, any database that has been deleted since the last backup of **master** will still have references in the system catalog views and may cause error messages to be raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9289f-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9289f-142">See Also</span></span>  
 <span data-ttu-id="9289f-143">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9289f-143">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="9289f-144">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9289f-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
