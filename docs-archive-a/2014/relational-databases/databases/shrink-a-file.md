---
title: Reduzir um arquivo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkfile.f1
helpviewer_keywords:
- shrinking files
- decreasing file size
- databases [SQL Server], shrinking
- reducing file size
- size [SQL Server], files
- file size [SQL Server]
ms.assetid: ce5c8798-c039-4ab2-81e7-90a8d688b893
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac69e4bd2db3ef7fe0815d235dd1de7d3396b302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678780"
---
# <a name="shrink-a-file"></a><span data-ttu-id="c5688-102">Reduzir um arquivo</span><span class="sxs-lookup"><span data-stu-id="c5688-102">Shrink a File</span></span>
  <span data-ttu-id="c5688-103">Este tópico descreve como reduzir um arquivo de dados ou de log no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5688-103">This topic describes how to shrink a data or log file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c5688-104">A redução de arquivos de dados recupera espaço com a movimentação de páginas de dados do final do arquivo para o espaço desocupado mais próximo à frente do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5688-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="c5688-105">Quando espaço livre suficiente é criado no final do arquivo, as páginas de dados no final do arquivo podem ser desalocadas e retornadas para o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c5688-105">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
 <span data-ttu-id="c5688-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="c5688-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c5688-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="c5688-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c5688-108">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c5688-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c5688-109">Recomendações</span><span class="sxs-lookup"><span data-stu-id="c5688-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="c5688-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="c5688-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c5688-111">**Para reduzir um arquivo de dados ou de log, usando:**</span><span class="sxs-lookup"><span data-stu-id="c5688-111">**To shrink a data or log file, using:**</span></span>  
  
     [<span data-ttu-id="c5688-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c5688-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c5688-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c5688-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c5688-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c5688-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c5688-115">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="c5688-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c5688-116">O arquivo de dados principal não pode ser menor que o arquivo principal no banco de dados modelo.</span><span class="sxs-lookup"><span data-stu-id="c5688-116">The primary data file cannot be made smaller than the size of the primary file in the model database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c5688-117">Recomendações</span><span class="sxs-lookup"><span data-stu-id="c5688-117">Recommendations</span></span>  
  
-   <span data-ttu-id="c5688-118">Os dados movidos para reduzir um arquivo podem ser espalhados para qualquer local disponível no arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5688-118">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="c5688-119">Isso provoca uma fragmentação do índice e pode reduzir a velocidade do desempenho de consultas que pesquisam um intervalo do índice.</span><span class="sxs-lookup"><span data-stu-id="c5688-119">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="c5688-120">Para eliminar a fragmentação, considere a recompilação dos índices no arquivo após a redução.</span><span class="sxs-lookup"><span data-stu-id="c5688-120">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c5688-121">Segurança</span><span class="sxs-lookup"><span data-stu-id="c5688-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c5688-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="c5688-122">Permissions</span></span>  
 <span data-ttu-id="c5688-123">Exige associação à função de servidor fixa **sysadmin** ou à função de banco de dados fixa **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="c5688-123">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c5688-124">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c5688-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="c5688-125">Para reduzir um arquivo de dados ou de log</span><span class="sxs-lookup"><span data-stu-id="c5688-125">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="c5688-126">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="c5688-126">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c5688-127">Expanda **Bancos de Dados** e clique com o botão direito do mouse no banco de dados que deseja reduzir.</span><span class="sxs-lookup"><span data-stu-id="c5688-127">Expand **Databases** and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="c5688-128">Aponte para **Tarefas**, aponte para **Reduzir**e, então, clique em **Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="c5688-128">Point to **Tasks**, point to **Shrink**, and then click **Files**.</span></span>  
  
     <span data-ttu-id="c5688-129">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="c5688-129">**Database**</span></span>  
     <span data-ttu-id="c5688-130">Exibe o nome do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="c5688-130">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="c5688-131">**Tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="c5688-131">**File type**</span></span>  
     <span data-ttu-id="c5688-132">Seleciona o tipo de arquivo para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5688-132">Select the file type for the file.</span></span> <span data-ttu-id="c5688-133">As escolhas disponíveis são arquivos de **Dados** e de **Log** .</span><span class="sxs-lookup"><span data-stu-id="c5688-133">The available choices are **Data** and **Log** files.</span></span> <span data-ttu-id="c5688-134">A seleção padrão é **Dados**.</span><span class="sxs-lookup"><span data-stu-id="c5688-134">The default selection is **Data**.</span></span> <span data-ttu-id="c5688-135">Selecionar um tipo diferente de grupo de arquivos altera as seleções nos outros campos de acordo o tipo selecionado.</span><span class="sxs-lookup"><span data-stu-id="c5688-135">Selecting a different filegroup type changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="c5688-136">**Grupo de arquivos**</span><span class="sxs-lookup"><span data-stu-id="c5688-136">**Filegroup**</span></span>  
     <span data-ttu-id="c5688-137">Selecione um grupo de arquivos da lista de grupos de arquivos associado com o **Tipo de arquivo** selecionado acima.</span><span class="sxs-lookup"><span data-stu-id="c5688-137">Select a filegroup from the list of Filegroups associated with the selected **File type** above.</span></span> <span data-ttu-id="c5688-138">Selecionar um grupo de arquivos diferente altera as seleções nos outros campos de acordo o grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="c5688-138">Selecting a different filegroup changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="c5688-139">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="c5688-139">**File name**</span></span>  
     <span data-ttu-id="c5688-140">Selecione um arquivo da lista de arquivos disponíveis do grupo de arquivos e tipo de arquivos selecionados.</span><span class="sxs-lookup"><span data-stu-id="c5688-140">Select a file from the list of available files of the selected filegroup and file type.</span></span>  
  
     <span data-ttu-id="c5688-141">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="c5688-141">**Location**</span></span>  
     <span data-ttu-id="c5688-142">Exibe o caminho completo para o arquivo atualmente selecionado.</span><span class="sxs-lookup"><span data-stu-id="c5688-142">Displays the full path to the currently selected file.</span></span> <span data-ttu-id="c5688-143">O caminho não é editável, mas pode ser copiado para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="c5688-143">The path is not editable, but it can be copied to the clipboard.</span></span>  
  
     <span data-ttu-id="c5688-144">**Espaço alocado no momento**</span><span class="sxs-lookup"><span data-stu-id="c5688-144">**Currently allocated space**</span></span>  
     <span data-ttu-id="c5688-145">Para arquivos de dados, exibe o espaço alocado no momento.</span><span class="sxs-lookup"><span data-stu-id="c5688-145">For data files, displays the current allocated space.</span></span> <span data-ttu-id="c5688-146">Para arquivos de log, exibe o espaço alocado no momento computado da saída de DBCC SQLPERF(LOGSPACE).</span><span class="sxs-lookup"><span data-stu-id="c5688-146">For log files, displays the current allocated space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="c5688-147">**Espaço livre disponível**</span><span class="sxs-lookup"><span data-stu-id="c5688-147">**Available free space**</span></span>  
     <span data-ttu-id="c5688-148">Para arquivos de dados, exibe o espaço livre disponível no momento computado da saída de DBCC SHOWFILESTATS(fileid).</span><span class="sxs-lookup"><span data-stu-id="c5688-148">For data files, displays the current available free space computed from the output of DBCC SHOWFILESTATS(fileid).</span></span> <span data-ttu-id="c5688-149">Para arquivos de log, exibe o espaço livre disponível no momento computado da saída de DBCC SQLPERF(LOGSPACE).</span><span class="sxs-lookup"><span data-stu-id="c5688-149">For log files, displays the current available free space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="c5688-150">**Liberar espaço não utilizado**</span><span class="sxs-lookup"><span data-stu-id="c5688-150">**Release unused space**</span></span>  
     <span data-ttu-id="c5688-151">Faz com que qualquer espaço não utilizado nos arquivos seja liberado para o sistema operacional e reduz o arquivo para a última extensão alocada, reduzindo o tamanho do arquivo sem mover nenhum dado.</span><span class="sxs-lookup"><span data-stu-id="c5688-151">Cause any unused space in the files to be released to the operating system and shrink the file to the last allocated extent, reducing the file size without moving any data.</span></span> <span data-ttu-id="c5688-152">Não é feita nenhuma tentativa para realocar linhas em páginas não alocadas.</span><span class="sxs-lookup"><span data-stu-id="c5688-152">No attempt is made to relocate rows to unallocated pages.</span></span>  
  
     <span data-ttu-id="c5688-153">**Reorganizar páginas antes de liberar espaço não utilizado**</span><span class="sxs-lookup"><span data-stu-id="c5688-153">**Reorganize pages before releasing unused space**</span></span>  
     <span data-ttu-id="c5688-154">Equivale a executar DBCC SHRINKFILE especificando o tamanho do arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="c5688-154">Equivalent to executing DBCC SHRINKFILE specifying the target file size.</span></span> <span data-ttu-id="c5688-155">Quando essa opção é selecionada, o usuário deve especificar um tamanho de arquivo de destino na **Reduzir arquivo a** .</span><span class="sxs-lookup"><span data-stu-id="c5688-155">When this option is selected, the user must specify a target file size in the **Shrink file to** box.</span></span>  
  
     <span data-ttu-id="c5688-156">**Reduzir arquivo a**</span><span class="sxs-lookup"><span data-stu-id="c5688-156">**Shrink file to**</span></span>  
     <span data-ttu-id="c5688-157">Especifica o tamanho do arquivo de destino para a operação de redução.</span><span class="sxs-lookup"><span data-stu-id="c5688-157">Specifies the target file size for the shrink operation.</span></span> <span data-ttu-id="c5688-158">O tamanho não pode ser menor do que o espaço alocado no momento nem mais do que a extensão total alocada para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5688-158">The size cannot be less than the current allocated space or more than the total extents allocated to the file.</span></span> <span data-ttu-id="c5688-159">Digitar um valor abaixo do mínimo ou além do máximo fará com que ele reverta ao mínimo ou ao máximo assim que o foco for alterado ou quando você clicar em qualquer botão da barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="c5688-159">Entering a value beyond the minimum or the maximum will revert to the min or the max once the focus is changed or when any of the buttons on the toolbar are clicked.</span></span>  
  
     <span data-ttu-id="c5688-160">**Esvaziar o arquivo migrando os dados para outros arquivos do mesmo grupo**</span><span class="sxs-lookup"><span data-stu-id="c5688-160">**Empty file by migrating the data to other files in the same filegroup**</span></span>  
     <span data-ttu-id="c5688-161">Migra todos os dados do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c5688-161">Migrate all data from the specified file.</span></span> <span data-ttu-id="c5688-162">Essa opção permite descartar o arquivo usando a instrução ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="c5688-162">This option allows the file to be dropped using the ALTER DATABASE statement.</span></span> <span data-ttu-id="c5688-163">Essa opção é equivalente a executar DBCC SHRINKFILE com a opção de EMPTYFILE.</span><span class="sxs-lookup"><span data-stu-id="c5688-163">This option is equivalent to executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
4.  <span data-ttu-id="c5688-164">Selecione o tipo e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5688-164">Select the file type and file name.</span></span>  
  
5.  <span data-ttu-id="c5688-165">Opcionalmente, marque a caixa de seleção **Liberar espaço não utilizado** .</span><span class="sxs-lookup"><span data-stu-id="c5688-165">Optionally, select the **Release unused space** check box.</span></span>  
  
     <span data-ttu-id="c5688-166">Selecionar essa opção faz com que qualquer espaço não usado no arquivo seja liberado para o sistema operacional e reduz o arquivo à última extensão alocada.</span><span class="sxs-lookup"><span data-stu-id="c5688-166">Selecting this option causes any unused space in the file to be released to the operating system and shrinks the file to the last allocated extent.</span></span> <span data-ttu-id="c5688-167">Isso reduz o tamanho do arquivo sem mover quaisquer dados.</span><span class="sxs-lookup"><span data-stu-id="c5688-167">This reduces the file size without moving any data.</span></span>  
  
6.  <span data-ttu-id="c5688-168">Opcionalmente, marque a caixa de seleção **Reorganizar arquivos antes de liberar o espaço não utilizado** .</span><span class="sxs-lookup"><span data-stu-id="c5688-168">Optionally, select the **Reorganize files before releasing unused space** check box.</span></span> <span data-ttu-id="c5688-169">Se isso for selecionado, o valor **Reduzir arquivo para** deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="c5688-169">If this is selected, the **Shrink file to** value must be specified.</span></span> <span data-ttu-id="c5688-170">Por padrão, a opção fica desmarcada.</span><span class="sxs-lookup"><span data-stu-id="c5688-170">By default, the option is cleared.</span></span>  
  
     <span data-ttu-id="c5688-171">Selecionar essa opção faz com que qualquer espaço não usado no arquivo seja liberado para o sistema operacional e tenta realocar linhas a páginas não alocadas.</span><span class="sxs-lookup"><span data-stu-id="c5688-171">Selecting this option causes any unused space in the file to be released to the operating system and tries to relocate rows to unallocated pages.</span></span>  
  
7.  <span data-ttu-id="c5688-172">Opcionalmente, insira a porcentagem máxima de espaço livre a ser deixado no arquivo de banco de dados após o banco de dados ter sido reduzido.</span><span class="sxs-lookup"><span data-stu-id="c5688-172">Optionally, enter the maximum percentage of free space to be left in the database file after the database has been shrunk.</span></span> <span data-ttu-id="c5688-173">Os valores permitidos estão entre 0 e 99.</span><span class="sxs-lookup"><span data-stu-id="c5688-173">Permissible values are between 0 and 99.</span></span> <span data-ttu-id="c5688-174">Essa opção só está disponível quando **Reorganizar arquivos antes de liberar o espaço não utilizado** estiver habilitada.</span><span class="sxs-lookup"><span data-stu-id="c5688-174">This option is only available when **Reorganize files before releasing unused space** is enabled.</span></span>  
  
8.  <span data-ttu-id="c5688-175">Opcionalmente, marque a caixa de seleção **Esvaziar arquivo migrando os dados para outros arquivos no mesmo grupo de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="c5688-175">Optionally, select the **Empty file by migrating the data to other files in the same filegroup** check box.</span></span>  
  
     <span data-ttu-id="c5688-176">Selecionar essa opção move todos os dados do arquivo especificado para outros arquivos no grupo de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c5688-176">Selecting this option moves all data from the specified file to other files in the filegroup.</span></span> <span data-ttu-id="c5688-177">O arquivo vazio pode, então, ser excluído.</span><span class="sxs-lookup"><span data-stu-id="c5688-177">The empty file can then be deleted.</span></span> <span data-ttu-id="c5688-178">Essa opção é igual a executar DBCC SHRINKFILE com a opção de EMPTYFILE.</span><span class="sxs-lookup"><span data-stu-id="c5688-178">This option is the same as executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
9. <span data-ttu-id="c5688-179">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5688-179">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c5688-180">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c5688-180">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="c5688-181">Para reduzir um arquivo de dados ou de log</span><span class="sxs-lookup"><span data-stu-id="c5688-181">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="c5688-182">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5688-182">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c5688-183">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c5688-183">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c5688-184">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c5688-184">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c5688-185">Este exemplo usa [DBCC SHRINKFILE](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) para reduzir o tamanho de um arquivo de dados denominado `DataFile1` no banco de dados `UserDB` para 7 MB.</span><span class="sxs-lookup"><span data-stu-id="c5688-185">This example uses [DBCC SHRINKFILE](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) to shrink the size of a data file named `DataFile1` in the `UserDB` database to 7 MB.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKFILE1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkfile1)]  
  
## <a name="see-also"></a><span data-ttu-id="c5688-186">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c5688-186">See Also</span></span>  
 <span data-ttu-id="c5688-187">[DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c5688-187">[DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span></span>  
 <span data-ttu-id="c5688-188">[Reduzir um banco de dados](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="c5688-188">[Shrink a Database](shrink-a-database.md) </span></span>  
 <span data-ttu-id="c5688-189">[Excluir arquivos de dados ou de log de um banco de dados](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="c5688-189">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 <span data-ttu-id="c5688-190">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c5688-190">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="c5688-191">sys.database_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5688-191">sys.database_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql)  
  
  
