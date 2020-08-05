---
title: Renomear um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], renaming
- renaming databases
ms.assetid: 44c69d35-abcb-4da3-9370-5e0bc9a28496
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd25a78e3d3b9be2e7191ce6ed3d6bdcbb0f9606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573099"
---
# <a name="rename-a-database"></a><span data-ttu-id="a3ed6-102">Renomear um banco de dados</span><span class="sxs-lookup"><span data-stu-id="a3ed6-102">Rename a Database</span></span>
  <span data-ttu-id="a3ed6-103">Este tópico descreve como renomear um banco de dados definido pelo usuário no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3ed6-103">This topic describes how to rename a user-defined database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a3ed6-104">O nome do banco de dados pode incluir qualquer caractere que segue as regras para identificadores.</span><span class="sxs-lookup"><span data-stu-id="a3ed6-104">The name of the database can include any characters that follow the rules for identifiers.</span></span>  
  
 <span data-ttu-id="a3ed6-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="a3ed6-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a3ed6-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="a3ed6-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a3ed6-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a3ed6-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a3ed6-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="a3ed6-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a3ed6-109">**Para renomear um banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="a3ed6-109">**To rename a database, using:**</span></span>  
  
     [<span data-ttu-id="a3ed6-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a3ed6-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a3ed6-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a3ed6-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="a3ed6-112">**Acompanhamento:**  [Após renomear um banco de dados](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a3ed6-112">**Follow Up:**  [After renaming a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a3ed6-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a3ed6-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a3ed6-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="a3ed6-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a3ed6-115">Os bancos de dados de sistema não podem ser renomeados.</span><span class="sxs-lookup"><span data-stu-id="a3ed6-115">System databases cannot be renamed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a3ed6-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="a3ed6-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a3ed6-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="a3ed6-117">Permissions</span></span>  
 <span data-ttu-id="a3ed6-118">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a3ed6-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a3ed6-119">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a3ed6-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="a3ed6-120">Para renomear um banco de dados</span><span class="sxs-lookup"><span data-stu-id="a3ed6-120">To rename a database</span></span>  
  
1.  <span data-ttu-id="a3ed6-121">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="a3ed6-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a3ed6-122">Certifique-se de que ninguém esteja usando o banco de dados e, em seguida, [defina o banco de dados como modo de usuário único](set-a-database-to-single-user-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a3ed6-122">Make sure that no one is using the database, and then [set the database to single-user mode](set-a-database-to-single-user-mode.md).</span></span>  
  
3.  <span data-ttu-id="a3ed6-123">Expanda **Bancos de Dados**, clique com o botão direito do mouse no banco de dados para renomear e, depois, clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="a3ed6-123">Expand **Databases**, right-click the database to rename, and then click **Rename**.</span></span>  
  
4.  <span data-ttu-id="a3ed6-124">Digite o novo nome do banco de dados e, depois, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3ed6-124">Enter the new database name, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a3ed6-125">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a3ed6-125">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="a3ed6-126">Para renomear um banco de dados</span><span class="sxs-lookup"><span data-stu-id="a3ed6-126">To rename a database</span></span>  
  
1.  <span data-ttu-id="a3ed6-127">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3ed6-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a3ed6-128">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="a3ed6-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a3ed6-129">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a3ed6-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a3ed6-130">Este exemplo altera o nome do banco de dados `AdventureWorks2012` para `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="a3ed6-130">This example changes the name of the `AdventureWorks2012` database to `Northwind`.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
Modify Name = Northwind ;  
GO  
```  
  
###  <a name="TsqlExample"></a>   
##  <a name="follow-up-after-renaming-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="a3ed6-131">Acompanhamento: depois de renomear um banco de dados</span><span class="sxs-lookup"><span data-stu-id="a3ed6-131">Follow Up: After renaming a database</span></span>  
 <span data-ttu-id="a3ed6-132">Faça backup do banco de dados **mestre** e, em seguida, renomeie qualquer banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a3ed6-132">Back up the **master** database after you rename any database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ed6-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a3ed6-133">See Also</span></span>  
 <span data-ttu-id="a3ed6-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a3ed6-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="a3ed6-135">Identificadores de banco de dados</span><span class="sxs-lookup"><span data-stu-id="a3ed6-135">Database Identifiers</span></span>](database-identifiers.md)  
  
  
