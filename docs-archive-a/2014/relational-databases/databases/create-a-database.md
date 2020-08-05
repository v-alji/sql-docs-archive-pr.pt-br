---
title: Criar um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], creating
- database creation [SQL Server], SQL Server Management Studio
- creating databases
ms.assetid: 4c4beea2-6cbc-4352-9db6-49ea8130bb64
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe42e394482e3abf4d87c00c6e79ee84db6ba278
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573121"
---
# <a name="create-a-database"></a><span data-ttu-id="72f85-102">Criar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="72f85-102">Create a Database</span></span>
  <span data-ttu-id="72f85-103">Este tópico descreve como criar um banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72f85-103">This topic describes how to create a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="72f85-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="72f85-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="72f85-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="72f85-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="72f85-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="72f85-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="72f85-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="72f85-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="72f85-108">Recomendações</span><span class="sxs-lookup"><span data-stu-id="72f85-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="72f85-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="72f85-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="72f85-110">**Para criar um diagrama de banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="72f85-110">**To create a database, using:**</span></span>  
  
     [<span data-ttu-id="72f85-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="72f85-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="72f85-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="72f85-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="72f85-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="72f85-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="72f85-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="72f85-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="72f85-115">No máximo 32.767 bancos de dados podem ser especificados em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72f85-115">A maximum of 32,767 databases can be specified on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="72f85-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="72f85-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="72f85-117">A instrução CREATE DATABASE deve ser executada em modo de confirmação automática (o modo padrão de gerenciamento de transações) e não é permitida em uma transação explícita ou implícita.</span><span class="sxs-lookup"><span data-stu-id="72f85-117">The CREATE DATABASE statement must run in autocommit mode (the default transaction management mode) and is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="72f85-118">Recomendações</span><span class="sxs-lookup"><span data-stu-id="72f85-118">Recommendations</span></span>  
  
-   <span data-ttu-id="72f85-119">O backup do banco de dados [mestre](master-database.md) deve ser feito sempre que um banco de dados de usuário for criado, modificado ou descartado.</span><span class="sxs-lookup"><span data-stu-id="72f85-119">The [master](master-database.md) database should be backed up whenever a user database is created, modified, or dropped.</span></span>  
  
-   <span data-ttu-id="72f85-120">Ao criar um banco de dados, torne os arquivos de dados tão grandes quanto possível, com base na quantidade máxima de dados que você espera ter no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="72f85-120">When you create a database, make the data files as large as possible based on the maximum amount of data you expect in the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="72f85-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="72f85-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="72f85-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="72f85-122">Permissions</span></span>  
 <span data-ttu-id="72f85-123">Requer a permissão CREATE DATABASE no banco de dados mestre, ou requer a permissão CREATE ANY DATABASE ou ALTER ANY DATABASE.</span><span class="sxs-lookup"><span data-stu-id="72f85-123">Requires CREATE DATABASE permission in the master database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="72f85-124">Para manter controle sobre o uso do disco em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a permissão para criar bancos de dados geralmente é limitada a algumas contas de logon.</span><span class="sxs-lookup"><span data-stu-id="72f85-124">To maintain control over disk use on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], permission to create databases is typically limited to a few login accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="72f85-125">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="72f85-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="72f85-126">Para criar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="72f85-126">To create a database</span></span>  
  
1.  <span data-ttu-id="72f85-127">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="72f85-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="72f85-128">Clique com o botão direito do mouse em **Bancos de Dados**e clique em **Novo Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="72f85-128">Right-click **Databases**, and then click **New Database**.</span></span>  
  
3.  <span data-ttu-id="72f85-129">Em **Novo Banco de Dados**, digite um nome de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="72f85-129">In **New Database**, enter a database name.</span></span>  
  
4.  <span data-ttu-id="72f85-130">Para criar o banco de dados aceitando todos os valores padrão, clique em **OK**; do contrário, passe para as etapas opcionais a seguir.</span><span class="sxs-lookup"><span data-stu-id="72f85-130">To create the database by accepting all default values, click **OK**; otherwise, continue with the following optional steps.</span></span>  
  
5.  <span data-ttu-id="72f85-131">Para alterar o nome do proprietário, clique em ( **...** ) para selecionar outro proprietário.</span><span class="sxs-lookup"><span data-stu-id="72f85-131">To change the owner name, click (**...**) to select another owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="72f85-132">A opção **Usar indexação de texto completo** sempre está marcada e esmaecida porque, a partir do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], todos os bancos de dados de usuários são habilitados para texto completo.</span><span class="sxs-lookup"><span data-stu-id="72f85-132">The **Use full-text indexing** option is always checked and dimmed because, beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], all user databases are full-text enabled.</span></span>  
  
6.  <span data-ttu-id="72f85-133">Para alterar os valores padrão dos arquivos de dados primários e de log de transação, na grade **Arquivos de banco de dados** , clique na célula apropriada e digite o novo valor.</span><span class="sxs-lookup"><span data-stu-id="72f85-133">To change the default values of the primary data and transaction log files, in the **Database files** grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="72f85-134">Para obter mais informações, consulte [adicionar dados ou arquivos de Log para um banco de dados](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="72f85-134">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
7.  <span data-ttu-id="72f85-135">Para alterar a ordenação do banco de dados, selecione a página **Opções** e depois marque uma ordenação na lista.</span><span class="sxs-lookup"><span data-stu-id="72f85-135">To change the collation of the database, select the **Options** page, and then select a collation from the list.</span></span>  
  
8.  <span data-ttu-id="72f85-136">Para alterar o modelo de recuperação, selecione a página **Opções** e marque um modelo de recuperação na lista.</span><span class="sxs-lookup"><span data-stu-id="72f85-136">To change the recovery model, select the **Options** page and select a recovery model from the list.</span></span>  
  
9. <span data-ttu-id="72f85-137">Para alterar opções de banco de dados, selecione a página **Opções** e depois modifique as opções de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="72f85-137">To change database options, select the **Options** page, and then modify the database options.</span></span> <span data-ttu-id="72f85-138">Para obter uma descrição de cada opção, consulte [Opções ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="72f85-138">For a description of each option, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
10. <span data-ttu-id="72f85-139">Para adicionar um novo grupo de arquivos, clique na página **Grupos de Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="72f85-139">To add a new filegroup, click the **Filegroups** page.</span></span> <span data-ttu-id="72f85-140">Clique em **Adicionar** e, em seguida, digite os valores para o grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="72f85-140">Click **Add** and then enter the values for the filegroup.</span></span>  
  
11. <span data-ttu-id="72f85-141">Para adicionar uma propriedade estendida ao banco de dados, selecione a página **Propriedades Estendidas** .</span><span class="sxs-lookup"><span data-stu-id="72f85-141">To add an extended property to the database, select the **Extended Properties** page.</span></span>  
  
    1.  <span data-ttu-id="72f85-142">Na coluna **Nome** , digite um nome para a propriedade estendida.</span><span class="sxs-lookup"><span data-stu-id="72f85-142">In the **Name** column, enter a name for the extended property.</span></span>  
  
    2.  <span data-ttu-id="72f85-143">Na coluna **Valor** , digite o texto da propriedade estendida.</span><span class="sxs-lookup"><span data-stu-id="72f85-143">In the **Value** column, enter the extended property text.</span></span> <span data-ttu-id="72f85-144">Por exemplo, digite uma ou mais instruções que descrevem o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="72f85-144">For example, enter one or more statements that describe the database.</span></span>  
  
12. <span data-ttu-id="72f85-145">Para criar o banco de dados, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="72f85-145">To create the database, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="72f85-146">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="72f85-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="72f85-147">Para criar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="72f85-147">To create a database</span></span>  
  
1.  <span data-ttu-id="72f85-148">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72f85-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="72f85-149">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="72f85-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="72f85-150">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="72f85-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="72f85-151">Este exemplo cria o banco de dados `Sales`.</span><span class="sxs-lookup"><span data-stu-id="72f85-151">This example creates the database `Sales`.</span></span> <span data-ttu-id="72f85-152">Como a palavra-chave PRIMARY não é usada, o primeiro arquivo (`Sales`_`dat`) torna-se o arquivo primário.</span><span class="sxs-lookup"><span data-stu-id="72f85-152">Because the keyword PRIMARY is not used, the first file (`Sales`_`dat`) becomes the primary file.</span></span> <span data-ttu-id="72f85-153">Como nem MB nem KB é especificado no parâmetro SIZE do arquivo `Sales`\_`dat` , ele usa MB e é alocado em megabytes.</span><span class="sxs-lookup"><span data-stu-id="72f85-153">Because neither MB nor KB is specified in the SIZE parameter for the `Sales`\_`dat` file, it uses MB and is allocated in megabytes.</span></span> <span data-ttu-id="72f85-154">O backup do banco de dados `Sales`\_`log` é alocado em megabytes porque o sufixo `MB` é explicitamente declarado no parâmetro `SIZE` .</span><span class="sxs-lookup"><span data-stu-id="72f85-154">The `Sales`\_`log` file is allocated in megabytes because the `MB` suffix is explicitly stated in the `SIZE` parameter.</span></span>  
  
```sql  
USE master ;  
GO  
CREATE DATABASE Sales  
ON   
( NAME = Sales_dat,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\saledat.mdf',  
    SIZE = 10,  
    MAXSIZE = 50,  
    FILEGROWTH = 5 )  
LOG ON  
( NAME = Sales_log,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\salelog.ldf',  
    SIZE = 5MB,  
    MAXSIZE = 25MB,  
    FILEGROWTH = 5MB ) ;  
GO  
```  
  
 <span data-ttu-id="72f85-155">Para obter mais exemplos, consulte [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="72f85-155">For more examples, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f85-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="72f85-156">See Also</span></span>  
 <span data-ttu-id="72f85-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="72f85-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="72f85-158">[Anexar e desanexar bancos de dados &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="72f85-158">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="72f85-159">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="72f85-159">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="72f85-160">Adicionar arquivos de dados ou de log a um banco de dados</span><span class="sxs-lookup"><span data-stu-id="72f85-160">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
