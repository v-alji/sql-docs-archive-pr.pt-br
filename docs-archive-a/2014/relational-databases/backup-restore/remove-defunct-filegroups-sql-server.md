---
title: Remover grupos de arquivos extintos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], defunct filegroups
- defunct filegroups
- restoring filegroups [SQL Server]
- deferred transactions
- filegroups [SQL Server], defunct
- unrestored filegroups
ms.assetid: 055f9c6a-5c18-4942-98e7-ec918f0ff975
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2bcba095d668c5c1ab317269a18af4dc996f63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683564"
---
# <a name="remove-defunct-filegroups-sql-server"></a><span data-ttu-id="90606-102">Remover grupos de arquivos expirados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="90606-102">Remove Defunct Filegroups (SQL Server)</span></span>
  <span data-ttu-id="90606-103">Este tópico descreve como remover grupos de arquivos expirados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90606-103">This topic describes how to remove defunct filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="90606-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="90606-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="90606-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="90606-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="90606-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="90606-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="90606-107">Recomendações</span><span class="sxs-lookup"><span data-stu-id="90606-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="90606-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="90606-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="90606-109">**Para remover grupos de arquivos expirados usando:**</span><span class="sxs-lookup"><span data-stu-id="90606-109">**To remove defunct filegroups, using:**</span></span>  
  
     [<span data-ttu-id="90606-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="90606-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="90606-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90606-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="90606-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="90606-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="90606-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="90606-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="90606-114">Este tópico é relevante para bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contêm vários arquivos ou grupos de arquivos; no modelo simples, ele é relevante somente para grupos de arquivos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="90606-114">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that contain multiple files or filegroups; and, under the simple model, only for read-only filegroups.</span></span>  
  
-   <span data-ttu-id="90606-115">Todos os arquivos em um grupo de arquivos tornam-se extintos quando um grupo de arquivos off-line é removido.</span><span class="sxs-lookup"><span data-stu-id="90606-115">All files in a filegroup become defunct when an offline filegroup is removed.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="90606-116">Recomendações</span><span class="sxs-lookup"><span data-stu-id="90606-116">Recommendations</span></span>  
  
-   <span data-ttu-id="90606-117">Se um grupo de arquivos não recuperado não precisar mais ser restaurado, você poderá criar o grupo de arquivos *expirado* , removendo-o do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="90606-117">If an unrestored filegroup will never have to be restored, you can make the filegroup *defunct* by removing it from the database.</span></span> <span data-ttu-id="90606-118">O grupo de arquivos expirado não pode mais ser restaurado nesse banco de dados, mas seus metadados permanecem.</span><span class="sxs-lookup"><span data-stu-id="90606-118">The defunct filegroup can never be restored to this database, but its metadata remains.</span></span> <span data-ttu-id="90606-119">Depois que o grupo de arquivos expirar, o banco de dados poderá ser reinicializado e a recuperação tornará o banco de dados consistente nos grupos de arquivos restaurados.</span><span class="sxs-lookup"><span data-stu-id="90606-119">After the filegroup is defunct, the database can be restarted, and recovery will make the database consistent across the restored filegroups.</span></span>  
  
     <span data-ttu-id="90606-120">Por exemplo, a criação de um grupo de arquivos expirado é uma opção para resolver transações adiadas causadas por um grupo de arquivos offline que você já não quer mais no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="90606-120">For example, making a filegroup defunct is an option for resolving deferred transactions that were caused by an offline filegroup that you no longer want in the database.</span></span> <span data-ttu-id="90606-121">Transações que foram adiadas porque o grupo de arquivos estava offline são removidas desse estado depois que o grupo de arquivos é considerado extinto.</span><span class="sxs-lookup"><span data-stu-id="90606-121">Transactions that were deferred because the filegroup was offline are moved out of the deferred state after the filegroup becomes defunct.</span></span> <span data-ttu-id="90606-122">Para obter mais informações, veja [Transações adiadas &#40;SQL Server&#41;](deferred-transactions-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="90606-122">For more information, see [Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="90606-123">Segurança</span><span class="sxs-lookup"><span data-stu-id="90606-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="90606-124">Permissões</span><span class="sxs-lookup"><span data-stu-id="90606-124">Permissions</span></span>  
 <span data-ttu-id="90606-125">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="90606-125">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="90606-126">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="90606-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="90606-127">Para remover grupos de arquivos expirados</span><span class="sxs-lookup"><span data-stu-id="90606-127">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="90606-128">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="90606-128">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="90606-129">Expanda **Bancos de Dados**, clique com o botão direito do mouse no banco de dados do qual deseja excluir o arquivo e depois clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="90606-129">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="90606-130">Selecione a página **Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="90606-130">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="90606-131">Na grade **Arquivos de bancos de dados** , selecione os arquivos a serem excluídos, clique em **Remover**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="90606-131">In the **Database files** grid, select the files to delete, click **Remove**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="90606-132">Selecione a página **Grupos de Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="90606-132">Select the **Filegroups** page.</span></span>  
  
6.  <span data-ttu-id="90606-133">Na grade **Linhas** , selecione o grupo de arquivos a ser excluído, clique em **Remover**e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="90606-133">In the **Rows** grid, select the filegroup to delete, click **Remove**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="90606-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90606-134">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="90606-135">Para remover grupos de arquivos expirados</span><span class="sxs-lookup"><span data-stu-id="90606-135">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="90606-136">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90606-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="90606-137">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="90606-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="90606-138">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="90606-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="90606-139">(**Observação:** este exemplo parte do princípio que os arquivos e o grupo de arquivos já existem.</span><span class="sxs-lookup"><span data-stu-id="90606-139">(**Note:** This example assumes that the files and filegroup already exist.</span></span> <span data-ttu-id="90606-140">Para criar esses objetos, veja o exemplo B no tópico [Opções de arquivos e grupos de arquivos ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).) O primeiro exemplo remove os arquivos `test1dat3` e `test1dat4` do grupo de arquivos expirados usando a instrução `ALTER DATABASE` com a cláusula `REMOVE FILE`.</span><span class="sxs-lookup"><span data-stu-id="90606-140">To create these objects, see example B in the [ALTER DATABASE File and Filegroup Options](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) topic.) The first example removes the `test1dat3` and `test1dat4` files from the defunct filegroup by using the `ALTER DATABASE` statement with the `REMOVE FILE` clause.</span></span> <span data-ttu-id="90606-141">O segundo exemplo remove o grupo de arquivos expirados `Test1FG1`usando a cláusula `REMOVE FILEGROUP` .</span><span class="sxs-lookup"><span data-stu-id="90606-141">The second example removes the defunct filegroup `Test1FG1`by using the `REMOVE FILEGROUP` clause.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat3 ;  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat4 ;  
GO  
  
```  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILEGROUP Test1FG1 ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="90606-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90606-142">See Also</span></span>  
 <span data-ttu-id="90606-143">[Opções de arquivo e grupos de arquivos ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span><span class="sxs-lookup"><span data-stu-id="90606-143">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span></span>  
 <span data-ttu-id="90606-144">[Transações adiadas &#40;SQL Server&#41;](deferred-transactions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90606-144">[Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md) </span></span>  
 <span data-ttu-id="90606-145">[Restaurações de arquivo &#40;Modelo de recuperação completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="90606-145">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="90606-146">[Restaurações de arquivos &#40;Modelo de recuperação simples&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="90606-146">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="90606-147">[Restauração online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90606-147">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="90606-148">[Restaurar páginas &#40;SQL Server&#41;](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90606-148">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 [<span data-ttu-id="90606-149">Restaurações por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="90606-149">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
