---
title: Anexar um banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.attachdatabase.f1
helpviewer_keywords:
- database attaching [SQL Server]
- attaching databases [SQL Server]
ms.assetid: b4efb0ae-cfe6-4d81-a4b4-6e4916885caa
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb11b5c257007872e92d3f0a7eadb3e46b4969cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685762"
---
# <a name="attach-a-database"></a><span data-ttu-id="6f4ec-102">Anexar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="6f4ec-102">Attach a Database</span></span>
  <span data-ttu-id="6f4ec-103">Este tópico descreve como anexar um banco de dados no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f4ec-103">This topic describes how to attach a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6f4ec-104">Você pode usar este recurso para copiar, mover ou atualizar um banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f4ec-104">You can use this feature to copy, move, or upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="6f4ec-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6f4ec-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6f4ec-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6f4ec-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="6f4ec-108">Recomendações</span><span class="sxs-lookup"><span data-stu-id="6f4ec-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="6f4ec-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="6f4ec-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6f4ec-110">**Para anexar um banco de dados usando:**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-110">**To Attach a Database by using:**</span></span>  
  
     [<span data-ttu-id="6f4ec-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6f4ec-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6f4ec-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6f4ec-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="6f4ec-113">**Acompanhamento:**  [Depois de atualizar um banco de dados](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="6f4ec-113">**Follow Up:**  [After Upgrading a Database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6f4ec-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6f4ec-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6f4ec-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6f4ec-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="6f4ec-116">O banco de dados primeiro deve ser desanexado.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-116">The database must first be detached.</span></span> <span data-ttu-id="6f4ec-117">A tentativa de anexar um banco de dados que não foi desanexado retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-117">Attempting to attach a database that has not been detached will return an error.</span></span> <span data-ttu-id="6f4ec-118">Para obter mais informações, veja [Desanexar um banco de dados](detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="6f4ec-118">For more information, see [Detach a Database](detach-a-database.md).</span></span>  
  
-   <span data-ttu-id="6f4ec-119">Quando você anexa um banco de dados, todos os arquivos de dados (arquivos MDF e LDF) devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-119">When you attach a database, all data files (MDF and LDF files) must be available.</span></span> <span data-ttu-id="6f4ec-120">Se algum arquivo de dados tiver um caminho diferente de quando o banco de dados foi inicialmente criado ou anexado pela última vez, você deverá especificar o caminho atual do arquivo.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-120">If any data file has a different path from when the database was first created or last attached, you must specify the current path of the file.</span></span>  
  
-   <span data-ttu-id="6f4ec-121">Quando você anexar um banco de dados, se os arquivos MDF e LDF estiverem localizados em diretórios diferentes e um dos caminhos incluir \\\\?\GlobalRoot, a operação falhará.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-121">When you attach a database, if MDF and LDF files are located in different directories and one of the paths includes \\\\?\GlobalRoot, the operation will fail.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="6f4ec-122">Recomendações</span><span class="sxs-lookup"><span data-stu-id="6f4ec-122">Recommendations</span></span>  
<span data-ttu-id="6f4ec-123">Recomendamos que você mova bancos de dados usando o `ALTER DATABASE` procedimento de Realocação planejada, em vez de usar desanexar e anexar.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-123">We recommend that you move databases by using the `ALTER DATABASE` planned relocation procedure, instead of using detach and attach.</span></span> <span data-ttu-id="6f4ec-124">Para obter mais informações, veja [Mover bancos de dados de usuário](move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="6f4ec-124">For more information, see [Move User Databases](move-user-databases.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6f4ec-125">Segurança</span><span class="sxs-lookup"><span data-stu-id="6f4ec-125">Security</span></span>  
<span data-ttu-id="6f4ec-126">As permissões de acesso ao arquivo são definidas durante algumas operações de banco de dados, inclusive desanexar ou anexar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-126">File access permissions are set during a number of database operations, including detaching or attaching a database.</span></span> <span data-ttu-id="6f4ec-127">Para obter informações sobre permissões de arquivo que são definidas sempre que um banco de dados é desanexado e anexado, consulte [Protegendo dados e arquivos de log](https://technet.microsoft.com/library/ms189128.aspx) nos Manuais Online do [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f4ec-127">For information about file permissions that are set whenever a database is detached and attached, see [Securing Data and Log Files](https://technet.microsoft.com/library/ms189128.aspx) in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] Books Online.</span></span>  
  
<span data-ttu-id="6f4ec-128">Não é recomendável anexar ou restaurar bancos de dados de origem desconhecida ou não confiável.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-128">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="6f4ec-129">Esses bancos de dados podem conter um código mal-intencionado que pode executar um código [!INCLUDE[tsql](../../includes/tsql-md.md)] inesperado ou provocar erros modificando o esquema ou a estrutura física do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-129">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="6f4ec-130">Antes de usar um banco de dados de origem desconhecida ou não confiável, execute [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) no banco de dados, em um servidor que não seja de produção. Além disso, examine o código, como procedimentos armazenados ou outro código definido pelo usuário, no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-130">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span> <span data-ttu-id="6f4ec-131">Para obter mais informações sobre como anexar bancos de dados e informações sobre alterações que são feitas em metadados ao anexar um banco de dados, veja [Anexar e desanexar bancos de dados &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6f4ec-131">For more information about attaching databases and information about changes that are made to metadata when you attach a database, see [Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6f4ec-132">Permissões</span><span class="sxs-lookup"><span data-stu-id="6f4ec-132">Permissions</span></span>  
<span data-ttu-id="6f4ec-133">Requer permissão `CREATE DATABASE`, `CREATE ANY DATABASE` ou `ALTER ANY DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-133">Requires `CREATE DATABASE`, `CREATE ANY DATABASE`, or `ALTER ANY DATABASE` permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6f4ec-134">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6f4ec-134">Using SQL Server Management Studio</span></span>  
  
### <a name="to-attach-a-database"></a><span data-ttu-id="6f4ec-135">Para anexar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="6f4ec-135">To Attach a Database</span></span>  
  
1.  <span data-ttu-id="6f4ec-136">No Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-136">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6f4ec-137">Clique com o botão direito do mouse em **Bancos de dados** e clique em **Anexar**.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-137">Right-click **Databases** and click **Attach**.</span></span>  
  
3.  <span data-ttu-id="6f4ec-138">Na caixa de diálogo **Anexar Banco de Dados** , para especificar o banco de dados a ser anexado, clique em **Adicionar**. Na caixa de diálogo **Localizar Arquivos de Banco de Dados** , selecione a unidade de disco onde o banco de dados reside e expanda a árvore de diretório para localizar e selecionar o arquivo .mdf do banco de dados, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6f4ec-138">In the **Attach Databases** dialog box, to specify the database to be attached, click **Add**; and in the **Locate Database Files** dialog box, select the disk drive where the database resides and expand the directory tree to find and select the .mdf file of the database; for example:</span></span>  
  
     `C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\AdventureWorks2012_Data.mdf`  
  
    > [!IMPORTANT]  
    > <span data-ttu-id="6f4ec-139">Tentar selecionar um banco de dados já anexado gera erro.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-139">Trying to select a database that is already attached generates an error.</span></span>  
  
     <span data-ttu-id="6f4ec-140">**Bancos de dados a serem anexados**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-140">**Databases to attach**</span></span>  
     <span data-ttu-id="6f4ec-141">Exibe informações sobre os bancos de dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-141">Displays information about the selected databases.</span></span>  
  
     \<no column header>  
     <span data-ttu-id="6f4ec-142">Exibe um ícone que indica o status da operação de anexação.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-142">Displays an icon indicating the status of the attach operation.</span></span> <span data-ttu-id="6f4ec-143">Os possíveis ícones são descritos em **Status** , abaixo).</span><span class="sxs-lookup"><span data-stu-id="6f4ec-143">The possible icons are described in the **Status** description, below).</span></span>  
  
     <span data-ttu-id="6f4ec-144">**Local do Arquivo MDF**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-144">**MDF File Location**</span></span>  
     <span data-ttu-id="6f4ec-145">Exibe o caminho e o nome de arquivo do arquivo MDF selecionado.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-145">Displays the path and file name of the selected MDF file.</span></span>  
  
     <span data-ttu-id="6f4ec-146">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-146">**Database Name**</span></span>  
     <span data-ttu-id="6f4ec-147">Exibe o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-147">Displays the name of the database.</span></span>  
  
     <span data-ttu-id="6f4ec-148">**Anexar como**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-148">**Attach As**</span></span>  
     <span data-ttu-id="6f4ec-149">Opcionalmente, especifique um nome diferente para o banco de dados anexar como.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-149">Optionally, specifies a different name for the database to attach as.</span></span>  
  
     <span data-ttu-id="6f4ec-150">**Proprietário**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-150">**Owner**</span></span>  
     <span data-ttu-id="6f4ec-151">Fornece uma lista suspensa de possíveis proprietários de banco de dados dos quais você pode selecionar um proprietário diferente opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-151">Provides a drop-down list of possible database owners from which you can optionally select a different owner.</span></span>  
  
     <span data-ttu-id="6f4ec-152">**Status**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-152">**Status**</span></span>  
     <span data-ttu-id="6f4ec-153">Exibe o status do banco de dados de acordo com a seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-153">Displays the status of the database according to the following table.</span></span>  
  
    |<span data-ttu-id="6f4ec-154">ícone</span><span class="sxs-lookup"><span data-stu-id="6f4ec-154">Icon</span></span>|<span data-ttu-id="6f4ec-155">Texto de status</span><span class="sxs-lookup"><span data-stu-id="6f4ec-155">Status text</span></span>|<span data-ttu-id="6f4ec-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="6f4ec-156">Description</span></span>|  
    |----------|-----------------|-----------------|  
    |<span data-ttu-id="6f4ec-157">(No icon)</span><span class="sxs-lookup"><span data-stu-id="6f4ec-157">(No icon)</span></span>|<span data-ttu-id="6f4ec-158">(Nenhum texto)</span><span class="sxs-lookup"><span data-stu-id="6f4ec-158">(No text)</span></span>|<span data-ttu-id="6f4ec-159">A operação de anexação não foi iniciada ou pode estar pendente para esse objeto.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-159">Attach operation has not been started or may be pending for this object.</span></span> <span data-ttu-id="6f4ec-160">Esse é o padrão quando a caixa de diálogo é aberta.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-160">This is the default when the dialog is opened.</span></span>|  
    |<span data-ttu-id="6f4ec-161">Triângulo verde apontando para a direita</span><span class="sxs-lookup"><span data-stu-id="6f4ec-161">Green, right-pointing triangle</span></span>|<span data-ttu-id="6f4ec-162">Em andamento</span><span class="sxs-lookup"><span data-stu-id="6f4ec-162">In progress</span></span>|<span data-ttu-id="6f4ec-163">A operação de anexação foi iniciada mas não está completa.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-163">Attach operation has been started but it is not complete.</span></span>|  
    |<span data-ttu-id="6f4ec-164">Sinal de verificação verde</span><span class="sxs-lookup"><span data-stu-id="6f4ec-164">Green check mark</span></span>|<span data-ttu-id="6f4ec-165">Sucesso</span><span class="sxs-lookup"><span data-stu-id="6f4ec-165">Success</span></span>|<span data-ttu-id="6f4ec-166">O objeto foi anexado com êxito.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-166">The object has been attached successfully.</span></span>|  
    |<span data-ttu-id="6f4ec-167">Círculo vermelho contendo uma cruz branca</span><span class="sxs-lookup"><span data-stu-id="6f4ec-167">Red circle containing a white cross</span></span>|<span data-ttu-id="6f4ec-168">Erro</span><span class="sxs-lookup"><span data-stu-id="6f4ec-168">Error</span></span>|<span data-ttu-id="6f4ec-169">A operação de anexação encontrou um erro e não foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-169">Attach operation encountered an error and did not complete successfully.</span></span>|  
    |<span data-ttu-id="6f4ec-170">Círculo que contém dois quadrantes pretos (à esquerda e à direita) e dois quadrantes brancos (em cima e em baixo)</span><span class="sxs-lookup"><span data-stu-id="6f4ec-170">Circle containing two black quadrants (on left and right) and two white quadrants (on top and bottom)</span></span>|<span data-ttu-id="6f4ec-171">Parado</span><span class="sxs-lookup"><span data-stu-id="6f4ec-171">Stopped</span></span>|<span data-ttu-id="6f4ec-172">A operação de anexação não foi completada com êxito porque o usuário interrompeu a operação.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-172">Attach operation was not completed successfully because the user stopped the operation.</span></span>|  
    |<span data-ttu-id="6f4ec-173">Círculo que contém uma seta curvada que aponta para o sentido anti-horário</span><span class="sxs-lookup"><span data-stu-id="6f4ec-173">Circle containing a curved arrow pointing counter-clockwise</span></span>|<span data-ttu-id="6f4ec-174">Revertida</span><span class="sxs-lookup"><span data-stu-id="6f4ec-174">Rolled Back</span></span>|<span data-ttu-id="6f4ec-175">A operação de anexação teve êxito, mas foi revertida devido a um erro ao se anexar outro objeto.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-175">Attach operation was successful but it has been rolled back due to an error during attachment of another object.</span></span>|  
  
     <span data-ttu-id="6f4ec-176">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-176">**Message**</span></span>  
     <span data-ttu-id="6f4ec-177">Exibe uma mensagem em branco ou um hiperlink "Arquivo não encontrado"</span><span class="sxs-lookup"><span data-stu-id="6f4ec-177">Displays either a blank message or a "File not found" hyperlink.</span></span>  
  
     <span data-ttu-id="6f4ec-178">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-178">**Add**</span></span>  
     <span data-ttu-id="6f4ec-179">Encontrar os arquivos de banco de dados principais necessários.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-179">Find the necessary main database files.</span></span> <span data-ttu-id="6f4ec-180">Quando o usuário selecionar um arquivo .mdf , os respectivos campos são automaticamente preenchidos com informações aplicáveis da grade **Bancos de dados a serem anexados** .</span><span class="sxs-lookup"><span data-stu-id="6f4ec-180">When the user selects an .mdf file, applicable information is automatically filled in the respective fields of the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="6f4ec-181">**Remover**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-181">**Remove**</span></span>  
     <span data-ttu-id="6f4ec-182">Remove o arquivo selecionado da grade **Bancos de dados a serem anexados** .</span><span class="sxs-lookup"><span data-stu-id="6f4ec-182">Removes the selected file from the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="6f4ec-183">**"** *<nome_do_banco_de_dados>* **" detalhes do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-183">**"** *<database_name>* **" database details**</span></span>  
     <span data-ttu-id="6f4ec-184">Exibe os nomes dos arquivos a serem anexados.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-184">Displays the names of the files to be attached.</span></span> <span data-ttu-id="6f4ec-185">Para verificar ou alterar o nome do caminho de um arquivo, clique no botão **Procurar** ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="6f4ec-185">To verify or change the pathname of a file, click the **Browse** button (**...**).</span></span>  
  
    > [!NOTE]  
    > <span data-ttu-id="6f4ec-186">Se um arquivo não existir, a coluna **Mensagem** exibe "Não encontrado."</span><span class="sxs-lookup"><span data-stu-id="6f4ec-186">If a file does not exist, the **Message** column displays "Not found."</span></span> <span data-ttu-id="6f4ec-187">Se um arquivo de log não for encontrado, ele existe em outro diretório ou foi excluído.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-187">If a log file is not found, it exists in another directory or has been deleted.</span></span> <span data-ttu-id="6f4ec-188">Você precisa atualizar o caminho do arquivo na grade **detalhes do banco de dados** para indicar o local correto ou remover o arquivo de log da grade.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-188">You need to either update the file path in the **database details** grid to point to the correct location or remove the log file from the grid.</span></span> <span data-ttu-id="6f4ec-189">Se um arquivo de dados .ndf não for encontrado, você precisará atualizar seu caminho na grade a fim de indicar o local correto.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-189">If an .ndf data file is not found, you need to update its path in the grid to point to the correct location.</span></span>  
  
     <span data-ttu-id="6f4ec-190">**Nome do arquivo original**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-190">**Original File Name**</span></span>  
     <span data-ttu-id="6f4ec-191">Exibe o nome do arquivo anexado que pertence ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-191">Displays the name of the attached file belonging to the database.</span></span>  
  
     <span data-ttu-id="6f4ec-192">**Tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-192">**File Type**</span></span>  
     <span data-ttu-id="6f4ec-193">Indica o tipo de arquivo, **Dados** ou **Log**.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-193">Indicates the type of file, **Data** or **Log**.</span></span>  
  
     <span data-ttu-id="6f4ec-194">**Caminho do arquivo atual**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-194">**Current File Path**</span></span>  
     <span data-ttu-id="6f4ec-195">Exibe o caminho para o arquivo de banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-195">Displays the path to the selected database file.</span></span> <span data-ttu-id="6f4ec-196">O caminho pode ser editado manualmente.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-196">The path can be edited manually.</span></span>  
  
     <span data-ttu-id="6f4ec-197">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="6f4ec-197">**Message**</span></span>  
     <span data-ttu-id="6f4ec-198">Exibe uma mensagem em branco ou um hiperlink “**Arquivo não encontrado**”.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-198">Displays either a blank message or a "**File not found**" hyperlink.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6f4ec-199">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6f4ec-199">Using Transact-SQL</span></span>  
  
### <a name="to-attach-a-database"></a><span data-ttu-id="6f4ec-200">Para anexar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="6f4ec-200">To attach a database</span></span>  
  
1.  <span data-ttu-id="6f4ec-201">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f4ec-201">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6f4ec-202">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-202">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6f4ec-203">Use a instrução [CREATE DATABASE](/sql/t-sql/statements/create-database-sql-server-transact-sql) com o `FOR ATTACH` fechamento.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-203">Use the [CREATE DATABASE](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the `FOR ATTACH` close.</span></span>  
  
     <span data-ttu-id="6f4ec-204">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-204">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6f4ec-205">Este exemplo anexa os arquivos do banco de dados [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] e renomeia o banco de dados como `MyAdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-205">This example attaches the files of the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database and renames the database to `MyAdventureWorks`.</span></span>  
  
    ```sql  
    CREATE DATABASE MyAdventureWorks   
        ON (FILENAME = 'C:\MySQLServer\AdventureWorks_Data.mdf'),   
        (FILENAME = 'C:\MySQLServer\AdventureWorks_Log.ldf')   
        FOR ATTACH;  
    ```  
  
    > [!NOTE]  
    > <span data-ttu-id="6f4ec-206">Se desejar, você poderá usar o procedimento armazenado [sp_attach_db](/sql/relational-databases/system-stored-procedures/sp-attach-db-transact-sql) ou [sp_attach_single_file_db](/sql/relational-databases/system-stored-procedures/sp-attach-single-file-db-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="6f4ec-206">Alternatively, you can use the [sp_attach_db](/sql/relational-databases/system-stored-procedures/sp-attach-db-transact-sql) or [sp_attach_single_file_db](/sql/relational-databases/system-stored-procedures/sp-attach-single-file-db-transact-sql) stored procedure.</span></span> <span data-ttu-id="6f4ec-207">No entanto, esses procedimentos armazenados estendidos são removidos de uma versão futura do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f4ec-207">However, these procedures will be removed in a future version of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6f4ec-208">Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-208">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span> <span data-ttu-id="6f4ec-209">Recomendamos que você use criar banco de dados... PARA anexar em vez disso.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-209">We recommend that you use CREATE DATABASE ... FOR ATTACH instead.</span></span>  
  
##  <a name="follow-up-after-upgrading-a-sql-server-database"></a><a name="FollowUp"></a> <span data-ttu-id="6f4ec-210">Acompanhamento: Depois de atualizar um banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6f4ec-210">Follow Up: After Upgrading a SQL Server Database</span></span>  
 <span data-ttu-id="6f4ec-211">após você atualiza um banco de dados usando o método Attach, o banco de dados fica disponível imediatamente e é atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-211">fter you upgrade a database by using the attach method, the database becomes available immediately and is automatically upgraded.</span></span> <span data-ttu-id="6f4ec-212">Se o banco de dados tiver índices de texto completo, o processo de atualização importará, redefinirá ou recriará esses índices dependendo da configuração da propriedade de servidor **Opção de Atualização de Texto Completo** .</span><span class="sxs-lookup"><span data-stu-id="6f4ec-212">If the database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the **Full-Text Upgrade Option** server property.</span></span> <span data-ttu-id="6f4ec-213">Se a opção de atualização for definida como **Importar** ou **Recriar**, os índices de texto completo permanecerão indisponíveis durante a atualização.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-213">If the upgrade option is set to **Import** or **Rebuild**, the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="6f4ec-214">Dependendo da quantidade de dados a serem indexados, a importação pode levar várias horas, e a recriação pode ser até dez vezes mais demorada.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-214">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="6f4ec-215">Lembre-se também de que, quando a opção de atualização estiver definida como **Importar**, se não houver um catálogo de texto completo disponível, os índices de texto completo associados serão recompilados.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-215">Note also that when the upgrade option is set to **Import**, if a full-text catalog is not available, the associated full-text indexes are rebuilt.</span></span>  
  
<span data-ttu-id="6f4ec-216">Se o nível de compatibilidade de um banco de dados de usuário for 100 ou mais alto antes da atualização, ele permanecerá o mesmo depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="6f4ec-216">If the compatibility level of a user database is 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="6f4ec-217">Se o nível de compatibilidade for 90 ou inferior antes da atualização, no banco de dados atualizado, o nível de compatibilidade será definido como 100, que é o nível de compatibilidade mais baixo com suporte no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f4ec-217">If the compatibility level is 90 before upgrade, in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="6f4ec-218">Para obter mais informações, veja [Nível de compatibilidade de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="6f4ec-218">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f4ec-219">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f4ec-219">See Also</span></span>  
 <span data-ttu-id="6f4ec-220">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6f4ec-220">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="6f4ec-221">Desanexar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="6f4ec-221">Detach a Database</span></span>](detach-a-database.md)  
  
  
