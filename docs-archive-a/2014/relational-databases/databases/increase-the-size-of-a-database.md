---
title: Aumentar o tamanho de um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], size
- increasing database size
- database size [SQL Server], increasing
- size [SQL Server], databases
ms.assetid: 14f4206d-3afa-4ba9-9849-23e81d63306d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 71dcb00b3f5525f7059fc54911baed929f763008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685740"
---
# <a name="increase-the-size-of-a-database"></a><span data-ttu-id="10e26-102">Aumentar o tamanho de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="10e26-102">Increase the Size of a Database</span></span>
  <span data-ttu-id="10e26-103">Este tópico descreve como aumentar o tamanho de um banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10e26-103">This topic describes how to increase the size of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="10e26-104">O banco de dados é expandido ao aumentar o tamanho de um arquivo de dados ou de log existente ou ao adicionar um novo arquivo ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="10e26-104">The database is expanded by either increasing the size of an existing data or log file or by adding a new file to the database.</span></span>  
  
 <span data-ttu-id="10e26-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="10e26-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="10e26-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="10e26-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="10e26-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="10e26-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="10e26-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="10e26-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="10e26-109">**Para aumentar o tamanho de um banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="10e26-109">**To increase the size of a database, using:**</span></span>  
  
     [<span data-ttu-id="10e26-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10e26-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="10e26-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="10e26-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="10e26-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="10e26-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="10e26-113">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="10e26-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="10e26-114">Você não pode adicionar ou remover um arquivo enquanto uma instrução BACKUP está em execução.</span><span class="sxs-lookup"><span data-stu-id="10e26-114">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="10e26-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="10e26-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="10e26-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="10e26-116">Permissions</span></span>  
 <span data-ttu-id="10e26-117">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="10e26-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="10e26-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10e26-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="10e26-119">Para aumentar o tamanho de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="10e26-119">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="10e26-120">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="10e26-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="10e26-121">Expanda **Bancos de Dados**, clique com o botão direito do mouse no banco de dados para aumentá-lo e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="10e26-121">Expand **Databases**, right-click the database to increase, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="10e26-122">Em **Propriedades do Banco de Dados**, selecione a página **Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="10e26-122">In **Database Properties**, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="10e26-123">Para aumentar o tamanho de um arquivo existente, aumente o valor na coluna **Tamanho inicial (MB)** para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="10e26-123">To increase the size of an existing file, increase the value in the **Initial Size (MB)** column for the file.</span></span> <span data-ttu-id="10e26-124">Você deve aumentar o tamanho do banco de dados em pelo menos 1 megabyte.</span><span class="sxs-lookup"><span data-stu-id="10e26-124">You must increase the size of the database by at least 1 megabyte.</span></span>  
  
5.  <span data-ttu-id="10e26-125">Para aumentar o tamanho do banco de dados adicionando um novo arquivo, clique em **Adicionar** e, depois, digite os valores para o novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="10e26-125">To increase the size of the database by adding a new file, click **Add** and then enter the values for the new file.</span></span> <span data-ttu-id="10e26-126">Para obter mais informações, consulte [adicionar dados ou arquivos de Log para um banco de dados](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="10e26-126">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
6.  <span data-ttu-id="10e26-127">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="10e26-127">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="10e26-128">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="10e26-128">Using Transact-SQL</span></span>  
  
#### <a name="to-increase-the-size-of-a-database"></a><span data-ttu-id="10e26-129">Para aumentar o tamanho de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="10e26-129">To increase the size of a database</span></span>  
  
1.  <span data-ttu-id="10e26-130">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10e26-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="10e26-131">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="10e26-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="10e26-132">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="10e26-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="10e26-133">Este exemplo aumenta o tamanho do arquivo `test1dat3`.</span><span class="sxs-lookup"><span data-stu-id="10e26-133">This example increases the size of the file `test1dat3`.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase5](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase5)]  
  
 <span data-ttu-id="10e26-134">Para obter mais exemplos, consulte [Opções de arquivo e grupos de arquivos ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="10e26-134">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e26-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="10e26-135">See Also</span></span>  
 <span data-ttu-id="10e26-136">[Adicionar arquivos de dados ou de log a um banco de dados](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="10e26-136">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="10e26-137">Reduzir um banco de dados</span><span class="sxs-lookup"><span data-stu-id="10e26-137">Shrink a Database</span></span>](shrink-a-database.md)  
  
  
