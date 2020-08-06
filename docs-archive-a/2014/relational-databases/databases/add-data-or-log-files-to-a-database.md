---
title: Adicionar arquivos de dados ou de log a um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- adding data files
- adding files
- adding log files
- file additions [SQL Server], steps
- files [SQL Server], adding
- data additions [SQL Server]
ms.assetid: 8ead516a-1334-4f40-84b2-509d0a8ffa45
author: stevestein
ms.author: sstein
ms.openlocfilehash: f72e00f9dab422652237b4b85579c544d0cda9fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685765"
---
# <a name="add-data-or-log-files-to-a-database"></a><span data-ttu-id="fda8a-102">Adicionar arquivos de dados ou de log a um banco de dados</span><span class="sxs-lookup"><span data-stu-id="fda8a-102">Add Data or Log Files to a Database</span></span>
  <span data-ttu-id="fda8a-103">Este tópico descreve como adicionar um arquivo de dados ou de log a um banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fda8a-103">This topic describes how to add data or log files to a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="fda8a-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="fda8a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fda8a-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="fda8a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fda8a-106">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="fda8a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fda8a-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="fda8a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fda8a-108">**Para adicionar arquivos de dados ou de log a um banco de dados existente usando:**</span><span class="sxs-lookup"><span data-stu-id="fda8a-108">**To add data or log files to a database, using:**</span></span>  
  
     [<span data-ttu-id="fda8a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fda8a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fda8a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fda8a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fda8a-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fda8a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fda8a-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="fda8a-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="fda8a-113">Você não pode adicionar ou remover um arquivo enquanto uma instrução BACKUP está em execução.</span><span class="sxs-lookup"><span data-stu-id="fda8a-113">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
-   <span data-ttu-id="fda8a-114">Um máximo de 32.767 arquivos e 32.767 grupos de arquivos pode ser especificado para cada banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fda8a-114">A maximum of 32,767 files and 32,767 filegroups can be specified for each database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fda8a-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="fda8a-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fda8a-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="fda8a-116">Permissions</span></span>  
 <span data-ttu-id="fda8a-117">Requer a permissão ALTER no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fda8a-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fda8a-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fda8a-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="fda8a-119">Para adicionar arquivos de dados ou de log a um banco de dados existente</span><span class="sxs-lookup"><span data-stu-id="fda8a-119">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="fda8a-120">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="fda8a-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fda8a-121">Expanda **Bancos de Dados**, clique com o botão direito do mouse no banco de dados ao qual deseja adicionar os arquivos e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-121">Expand **Databases**, right-click the database from which to add the files, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="fda8a-122">Na caixa de diálogo **Propriedades do Banco de Dados** , selecione a página **Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="fda8a-122">In the **Database Properties** dialog box, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="fda8a-123">Para adicionar arquivos de dados ou de log de transação, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-123">To add a data or transaction log file, click **Add**.</span></span>  
  
5.  <span data-ttu-id="fda8a-124">Na grade **Arquivos do Banco de Dados** , digite um nome lógico para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="fda8a-124">In the **Database files** grid, enter a logical name for the file.</span></span> <span data-ttu-id="fda8a-125">O nome do arquivo deve ser exclusivo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fda8a-125">The file name must be unique within the database.</span></span>  
  
6.  <span data-ttu-id="fda8a-126">Selecione o tipo de arquivo, de dados ou de log.</span><span class="sxs-lookup"><span data-stu-id="fda8a-126">Select the file type, data or log.</span></span>  
  
7.  <span data-ttu-id="fda8a-127">Para um arquivo de dados, selecione na lista o grupo de arquivos no qual ele deve ser incluído ou selecione **\<new filegroup>** para criar um grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fda8a-127">For a data file, select the filegroup in which the file should be included from the list, or select **\<new filegroup>** to create a new filegroup.</span></span> <span data-ttu-id="fda8a-128">Logs de transações não podem ser colocados em grupos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fda8a-128">Transaction logs cannot be put in filegroups.</span></span>  
  
8.  <span data-ttu-id="fda8a-129">Especifique o tamanho inicial do arquivo.</span><span class="sxs-lookup"><span data-stu-id="fda8a-129">Specify the initial size of the file.</span></span> <span data-ttu-id="fda8a-130">Deixe os arquivos de dados tão grandes quanto possível, com base na quantidade máxima de dados que você espera ter no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fda8a-130">Make the data file as large as possible, based on the maximum amount of data you expect in the database.</span></span>  
  
9. <span data-ttu-id="fda8a-131">Para especificar como o arquivo deve se expandir, clique em ( **…** ) na coluna **Aumento Automático**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-131">To specify how the file should grow, click (**...**) in the **Autogrowth** column.</span></span> <span data-ttu-id="fda8a-132">Selecione entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fda8a-132">Select from the following options:</span></span>  
  
    1.  <span data-ttu-id="fda8a-133">Para permitir que o arquivo selecionado aumente conforme mais espaço de dados se fizer necessário; marque a caixa de seleção **Habilitar Aumento Automático** e depois selecione entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fda8a-133">To allow for the currently selected file to grow as more data space is required, select the **Enable Autogrowth** check box and then select from the following options:</span></span>  
  
    2.  <span data-ttu-id="fda8a-134">Para especificar que o arquivo deve aumentar em incrementos fixos, selecione **Em Megabytes** e especifique um valor.</span><span class="sxs-lookup"><span data-stu-id="fda8a-134">To specify that the file should grow by fixed increments, select **In Megabytes** and specify a value.</span></span>  
  
    3.  <span data-ttu-id="fda8a-135">Para especificar que o arquivo deve aumentar em uma porcentagem do tamanho atual do arquivo, selecione **Em Porcentagem** e especifique um valor.</span><span class="sxs-lookup"><span data-stu-id="fda8a-135">To specify that the file should grow by a percentage of the current file size, select **In Percent** and specify a value.</span></span>  
  
10. <span data-ttu-id="fda8a-136">Para especificar o limite máximo de tamanho do arquivo, selecione entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fda8a-136">To specify the maximum file size limit, select from the following options:</span></span>  
  
    1.  <span data-ttu-id="fda8a-137">Para especificar o tamanho máximo até o qual o arquivo pode se expandir, selecione **Expansão de Arquivo Restrita (MB)** e especifique um valor.</span><span class="sxs-lookup"><span data-stu-id="fda8a-137">To specify the maximum size the file should be able to grow to, select **Restricted File Growth (MB)** and specify a value.</span></span>  
  
    2.  <span data-ttu-id="fda8a-138">Para permitir que o arquivo aumente conforme o necessário, selecione **Aumento de Arquivo Irrestrito**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-138">To allow for the file to grow as much as needed, select **Unrestricted File Growth**.</span></span>  
  
    3.  <span data-ttu-id="fda8a-139">Para impedir o aumento do arquivo, desmarque a caixa de seleção **Habilitar Aumento Automático** .</span><span class="sxs-lookup"><span data-stu-id="fda8a-139">To prevent the file from growing, clear the **Enable Autogrowth** check box.</span></span> <span data-ttu-id="fda8a-140">O tamanho do arquivo não se expandirá além do valor especificado na coluna **Tamanho Inicial (MB)** .</span><span class="sxs-lookup"><span data-stu-id="fda8a-140">The size of the file will not grow beyond the value specified in the **Initial Size (MB)** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fda8a-141">O tamanho máximo do banco de dados é determinado pela quantidade disponível de espaço em disco e dos limites de licença determinados pela versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em uso.</span><span class="sxs-lookup"><span data-stu-id="fda8a-141">The maximum database size is determined by the amount of disk space available and the licensing limits determined by the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using.</span></span>  
  
11. <span data-ttu-id="fda8a-142">Especifique o caminho para o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="fda8a-142">Specify the path for the file location.</span></span> <span data-ttu-id="fda8a-143">O caminho especificado deve existir antes de adicionar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="fda8a-143">The specified path must exist before adding the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fda8a-144">Por padrão, os logs de transação e os dados são colocados na mesma unidade e caminho para acomodar sistemas em um único disco, mas essa pode não ser a melhor opção para ambientes de produção.</span><span class="sxs-lookup"><span data-stu-id="fda8a-144">By default, the data and transaction logs are put on the same drive and path to accommodate single-disk systems, but may not be optimal for production environments.</span></span> <span data-ttu-id="fda8a-145">Para obter mais informações, consulte [Database Files and Filegroups](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="fda8a-145">For more information, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
12. <span data-ttu-id="fda8a-146">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-146">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fda8a-147">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fda8a-147">Using Transact-SQL</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="fda8a-148">Para adicionar arquivos de dados ou de log a um banco de dados existente</span><span class="sxs-lookup"><span data-stu-id="fda8a-148">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="fda8a-149">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fda8a-149">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fda8a-150">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-150">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fda8a-151">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="fda8a-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="fda8a-152">O exemplo adiciona um grupo de arquivos com dois arquivos a um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fda8a-152">The example adds a filegroup with two files to a database.</span></span> <span data-ttu-id="fda8a-153">O exemplo cria o grupo de arquivos `Test1FG1` no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] e adiciona dois arquivos de 5 MB ao grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fda8a-153">The example creates the filegroup `Test1FG1` in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database and adds two 5-MB files to the filegroup.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase2](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase2)]  
  
 <span data-ttu-id="fda8a-154">Para obter mais exemplos, consulte [Opções de arquivo e grupos de arquivos ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="fda8a-154">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda8a-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fda8a-155">See Also</span></span>  
 <span data-ttu-id="fda8a-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="fda8a-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="fda8a-157">[Excluir arquivos de dados ou de log de um banco de dados](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="fda8a-157">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 [<span data-ttu-id="fda8a-158">Aumentar o tamanho de um banco de dados</span><span class="sxs-lookup"><span data-stu-id="fda8a-158">Increase the Size of a Database</span></span>](increase-the-size-of-a-database.md)  
  
  
