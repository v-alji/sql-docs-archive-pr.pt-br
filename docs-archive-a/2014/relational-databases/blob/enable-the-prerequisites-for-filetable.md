---
title: Habilitar os pré-requisitos para FileTable | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], prerequisites
ms.assetid: 6286468c-9dc9-4eda-9961-071d2a36ebd6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5d5d2c5dab7909ec5403911d482823f488cdd809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568649"
---
# <a name="enable-the-prerequisites-for-filetable"></a><span data-ttu-id="60a47-102">Habilitar os pré-requisitos para FileTable</span><span class="sxs-lookup"><span data-stu-id="60a47-102">Enable the Prerequisites for FileTable</span></span>
  <span data-ttu-id="60a47-103">Descreve como habilitar os pré-requisitos para criar e usar FileTables.</span><span class="sxs-lookup"><span data-stu-id="60a47-103">Describes how to enable the prerequisites for creating and using FileTables.</span></span>  
  
##  <a name="enabling-the-prerequisites-for-filetable"></a><a name="EnablePrereq"></a> <span data-ttu-id="60a47-104">Habilitando os pré-requisitos para FileTable</span><span class="sxs-lookup"><span data-stu-id="60a47-104">Enabling the Prerequisites for FileTable</span></span>  
 <span data-ttu-id="60a47-105">Para habilitar os pré-requisitos para criar e usar FileTables, habilite os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="60a47-105">To enable the prerequisites for creating and using FileTables, enable the following items:</span></span>  
  
-   <span data-ttu-id="60a47-106">**No nível de instância:**</span><span class="sxs-lookup"><span data-stu-id="60a47-106">**At the instance level:**</span></span>  
  
    -   [<span data-ttu-id="60a47-107">Habilitando o FILESTREAM no nível de instância</span><span class="sxs-lookup"><span data-stu-id="60a47-107">Enabling FILESTREAM at the Instance Level</span></span>](#BasicsFilestream)  
  
-   <span data-ttu-id="60a47-108">**No nível de banco de dados:**</span><span class="sxs-lookup"><span data-stu-id="60a47-108">**At the database level:**</span></span>  
  
    -   [<span data-ttu-id="60a47-109">Fornecendo um grupo de arquivos FILESTREAM no nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="60a47-109">Providing a FILESTREAM Filegroup at the Database Level</span></span>](#filegroup)  
  
    -   [<span data-ttu-id="60a47-110">Habilitando o acesso não transacional em nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="60a47-110">Enabling Non-Transactional Access at the Database Level</span></span>](#BasicsNTAccess)  
  
    -   [<span data-ttu-id="60a47-111">Especificando um diretório para FileTables no nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="60a47-111">Specifying a Directory for FileTables at the Database Level</span></span>](#BasicsDirectory)  
  
##  <a name="enabling-filestream-at-the-instance-level"></a><a name="BasicsFilestream"></a> <span data-ttu-id="60a47-112">Habilitando o FILESTREAM no nível de instância</span><span class="sxs-lookup"><span data-stu-id="60a47-112">Enabling FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="60a47-113">As FileTables ampliam os recursos de FILESTREAM do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60a47-113">FileTables extend the capabilities of the FILESTREAM feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="60a47-114">Portanto, você precisa habilitar o FILESTREAM para acesso de E/S de arquivo no nível do Windows e na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que possa criar e usar FileTables.</span><span class="sxs-lookup"><span data-stu-id="60a47-114">Therefore you have to enable FILESTREAM for file I/O access at the Windows level and on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you can create and use FileTables.</span></span>  
  
###  <a name="how-to-enable-filestream-at-the-instance-level"></a><a name="HowToFilestream"></a> <span data-ttu-id="60a47-115">Como Habilitar o FILESTREAM no nível de instância</span><span class="sxs-lookup"><span data-stu-id="60a47-115">How To: Enable FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="60a47-116">Para obter informações sobre como habilitar o FILESTREAM, veja [Habilitar e configurar o FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="60a47-116">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
 <span data-ttu-id="60a47-117">Quando você chama o `sp_configure` para habilitar o FILESTREAM no nível de instância, precisa definir a opção filestream_access_level como 2.</span><span class="sxs-lookup"><span data-stu-id="60a47-117">When you call `sp_configure` to enable FILESTREAM at the instance level, you have to set the filestream_access_level option to 2.</span></span> <span data-ttu-id="60a47-118">Para obter mais informações, veja [Opção filestream access level de configuração de servidor](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="60a47-118">For more information, see [filestream access level Server Configuration Option](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span></span>  
  
###  <a name="how-to-allow-filestream-through-the-firewall"></a><a name="firewall"></a> <span data-ttu-id="60a47-119">Como Permitir o FILESTREAM através do firewall</span><span class="sxs-lookup"><span data-stu-id="60a47-119">How To: Allow FILESTREAM through the Firewall</span></span>  
 <span data-ttu-id="60a47-120">Para obter informações sobre como permitir o FILESTREAM através do firewall, consulte [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span><span class="sxs-lookup"><span data-stu-id="60a47-120">For information about how to allow FILESTREAM through the firewall, see [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span></span>  
  
##  <a name="providing-a-filestream-filegroup-at-the-database-level"></a><a name="filegroup"></a> <span data-ttu-id="60a47-121">Fornecendo um grupo de arquivos FILESTREAM no nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="60a47-121">Providing a FILESTREAM Filegroup at the Database Level</span></span>  
 <span data-ttu-id="60a47-122">Antes de você poder criar FileTables em um banco de dados, o banco de dados deve ter um grupo de arquivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="60a47-122">Before you can create FileTables in a database, the database must have a FILESTREAM filegroup.</span></span> <span data-ttu-id="60a47-123">Para obter mais informações sobre esses pré-requisitos, veja [Criar um banco de dados habilitado para FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="60a47-123">For more information about this prerequisite, see [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
##  <a name="enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsNTAccess"></a> <span data-ttu-id="60a47-124">Habilitando o acesso não transacional em nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="60a47-124">Enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="60a47-125">As FileTables permitem que os aplicativos do Windows obtenham um identificador de arquivo do Windows para dados de FILESTREAM sem precisar de uma transação.</span><span class="sxs-lookup"><span data-stu-id="60a47-125">FileTables let Windows applications obtain a Windows file handle to FILESTREAM data without requiring a transaction.</span></span> <span data-ttu-id="60a47-126">Para permitir esse acesso não transacional a arquivos armazenados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você deve especificar o nível desejado de acesso não transacional no nível de banco de dados para cada banco de dados que conterá FileTables.</span><span class="sxs-lookup"><span data-stu-id="60a47-126">To allow this non-transactional access to files stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you have to specify the desired level of non-transactional access at the database level for each database that will contain FileTables.</span></span>  
  
###  <a name="how-to-check-whether-non-transactional-access-is-enabled-on-databases"></a><a name="HowToCheckAccess"></a> <span data-ttu-id="60a47-127">Como Verificar se o acesso não transacional está habilitado em bancos de dados</span><span class="sxs-lookup"><span data-stu-id="60a47-127">How To: Check Whether Non-Transactional Access Is Enabled on Databases</span></span>  
 <span data-ttu-id="60a47-128">Consulte a exibição de catálogo [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) e verifique as colunas **non_transacted_access** e **non_transacted_access_desc**.</span><span class="sxs-lookup"><span data-stu-id="60a47-128">Query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **non_transacted_access** and **non_transacted_access_desc** columns.</span></span>  
  
```sql  
SELECT DB_NAME(database_id), non_transacted_access, non_transacted_access_desc  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="how-to-enable-non-transactional-access-at-the-database-level"></a><a name="HowToNTAccess"></a> <span data-ttu-id="60a47-129">Como Habilitar o acesso não transacional no nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="60a47-129">How To: Enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="60a47-130">Os níveis disponíveis de acesso não transacional são FULL, READ_ONLY e OFF.</span><span class="sxs-lookup"><span data-stu-id="60a47-130">The available levels of non-transactional access are FULL, READ_ONLY, and OFF.</span></span>  
  
 <span data-ttu-id="60a47-131">**Especificar o nível de acesso não transacional usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="60a47-131">**Specify the level of non-transactional access by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="60a47-132">Quando você **criar um novo banco de dados**, chame a instrução [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) com a opção **NON_TRANSACTED_ACCESS** de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="60a47-132">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
-   <span data-ttu-id="60a47-133">Ao **alterar um banco de dados existente**, chame a instrução [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) com a opção FILESTREAM **NON_TRANSACTED_ACCESS**.</span><span class="sxs-lookup"><span data-stu-id="60a47-133">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
 <span data-ttu-id="60a47-134">**Especificar o nível de acesso não transacional usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="60a47-134">**Specify the level of non-transactional access by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="60a47-135">Você pode especificar o nível de acesso não transacional no campo **Acesso Não Transacionado a FILESTREAM** da página **Opções** da caixa de diálogo **Propriedades do Banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="60a47-135">You can specify the level of non-transactional access in the **FILESTREAM Non-transacted Access** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="60a47-136">Para obter mais informações sobre essa caixa de diálogo, veja [Propriedades de banco de dados &#40;Página Opções&#41;](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="60a47-136">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
##  <a name="specifying-a-directory-for-filetables-at-the-database-level"></a><a name="BasicsDirectory"></a> <span data-ttu-id="60a47-137">Especificando um diretório para FileTables no nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="60a47-137">Specifying a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="60a47-138">Quando você habilita o acesso não transacional a arquivos no nível de banco de dados, tem como opção fornecer um nome de diretório ao mesmo tempo usando a opção **DIRECTORY_NAME** .</span><span class="sxs-lookup"><span data-stu-id="60a47-138">When you enable non-transactional access to files at the database level, you can optionally provide a directory name at the same time by using the **DIRECTORY_NAME** option.</span></span> <span data-ttu-id="60a47-139">Se você não fornecer um nome de diretório ao habilitar o acesso não transacional, deverá fornecê-lo posteriormente para que possa criar FileTables no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="60a47-139">If you do not provide a directory name when you enable non-transactional access, then you have to provide it later before you can create FileTables in the database.</span></span>  
  
 <span data-ttu-id="60a47-140">Na hierarquia de pastas de FileTable, esse diretório em nível de banco de dados se torna o filho do nome de compartilhamento especificado para FILESTREAM no nível de instância, e o pai das FileTables criadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="60a47-140">In the FileTable folder hierarchy, this database-level directory becomes the child of the share name specified for FILESTREAM at the instance level, and the parent of the FileTables created in the database.</span></span> <span data-ttu-id="60a47-141">Para obter mais informações, consulte [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="60a47-141">For more information, see [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span></span>  
  
###  <a name="how-to-specify-a-directory-for-filetables-at-the-database-level"></a><a name="HowToDirectory"></a> <span data-ttu-id="60a47-142">Como Especifique um diretório para FileTables no nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="60a47-142">How To: Specify a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="60a47-143">O nome que você especifica deve estar exclusivo na instância para diretórios em nível de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="60a47-143">The name that you specify must be unique across the instance for database-level directories.</span></span>  
  
 <span data-ttu-id="60a47-144">**Especificar um diretório para FileTables usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="60a47-144">**Specify a directory for FileTables by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="60a47-145">Quando você **criar um novo banco de dados**, chame a instrução [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) com a opção **DIRECTORY_NAME** de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="60a47-145">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="60a47-146">Ao **alterar um banco de dados existente**, chame a instrução [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) com a opção FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="60a47-146">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span> <span data-ttu-id="60a47-147">Quando você usa estas opções para alterar o nome do diretório, o banco de dados deve ser bloqueado de forma exclusiva, sem identificadores de arquivos abertos.</span><span class="sxs-lookup"><span data-stu-id="60a47-147">When you use these options to change the directory name, the database must be exclusively locked, with no open file handles.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="60a47-148">Ao **anexar um banco de dados**, chame a instrução [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) com a opção **FOR ATTACH** e com a opção FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="60a47-148">When you **attach a database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **FOR ATTACH** option and with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        FOR ATTACH WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="60a47-149">Ao **restaurar um banco de dados**, chame a instrução [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) com a opção FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="60a47-149">When you **restore a database**, call the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    RESTORE DATABASE database_name  
        WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
 <span data-ttu-id="60a47-150">**Especificar um diretório para FileTables usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="60a47-150">**Specify a directory for FileTables by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="60a47-151">Você pode especificar um nome de diretório no campo **Nome do Diretório FILESTREAM** da página **Opções** da caixa de diálogo **Propriedades do Banco de dados** .</span><span class="sxs-lookup"><span data-stu-id="60a47-151">You can specify a directory name in the **FILESTREAM Directory Name** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="60a47-152">Para obter mais informações sobre essa caixa de diálogo, veja [Propriedades de banco de dados &#40;Página Opções&#41;](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="60a47-152">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
###  <a name="how-to-view-existing-directory-names-for-the-instance"></a><a name="viewnames"></a> <span data-ttu-id="60a47-153">Como Exibir nomes de diretórios existentes para a instância</span><span class="sxs-lookup"><span data-stu-id="60a47-153">How to: View Existing Directory Names for the Instance</span></span>  
 <span data-ttu-id="60a47-154">Para exibir a lista de nomes de diretórios existentes para a instância, veja a exibição de catálogo [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) e verifique a coluna **filestream_database_directory_name**.</span><span class="sxs-lookup"><span data-stu-id="60a47-154">To view the list of existing directory names for the instance, query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **filestream_database_directory_name** column.</span></span>  
  
```sql  
SELECT DB_NAME ( database_id ), directory_name  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="requirements-and-restrictions-for-the-database-level-directory"></a><a name="ReqDirectory"></a> <span data-ttu-id="60a47-155">Requisitos e restrições para o diretório em nível de banco de dados</span><span class="sxs-lookup"><span data-stu-id="60a47-155">Requirements and Restrictions for the Database-Level Directory</span></span>  
  
-   <span data-ttu-id="60a47-156">Definir **DIRECTORY_NAME** é opcional quando você chama **CREATE DATABASE** ou **ALTER DATABASE**.</span><span class="sxs-lookup"><span data-stu-id="60a47-156">Setting the **DIRECTORY_NAME** is optional when you call **CREATE DATABASE** or **ALTER DATABASE**.</span></span> <span data-ttu-id="60a47-157">Se você não especificar um valor para **DIRECTORY_NAME**, o nome de diretório permanecerá nulo.</span><span class="sxs-lookup"><span data-stu-id="60a47-157">If you do not specify a value for **DIRECTORY_NAME**, then the directory name remains null.</span></span> <span data-ttu-id="60a47-158">Entretanto, você só poderá criar FileTables no banco de dados quando especificar um valor para **DIRECTORY_NAME** no nível de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="60a47-158">However you cannot create FileTables in the database until you specify a value for **DIRECTORY_NAME** at the database level.</span></span>  
  
-   <span data-ttu-id="60a47-159">O nome de diretório que você fornece deve atender aos requisitos do sistema de arquivos para um nome de diretório válido.</span><span class="sxs-lookup"><span data-stu-id="60a47-159">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
-   <span data-ttu-id="60a47-160">Quando o banco de dados contém FileTables, não é possível definir **DIRECTORY_NAME** como um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="60a47-160">When the database contains FileTables, you cannot set the **DIRECTORY_NAME** back to a null value.</span></span>  
  
-   <span data-ttu-id="60a47-161">Quando você anexar ou restaurar um banco de dados, a operação falhará se o novo banco de dados tiver um valor para **DIRECTORY_NAME** já existente na instância de destino.</span><span class="sxs-lookup"><span data-stu-id="60a47-161">When you attach or restore a database, the operation fails if the new database has a value for **DIRECTORY_NAME** that already exists in the target instance.</span></span> <span data-ttu-id="60a47-162">Especifique um valor exclusivo para **DIRECTORY_NAME** quando chamar **CREATE DATABASE FOR ATTACH** ou **RESTORE DATABASE**.</span><span class="sxs-lookup"><span data-stu-id="60a47-162">Specify a unique value for **DIRECTORY_NAME** when you call **CREATE DATABASE FOR ATTACH** or **RESTORE DATABASE**.</span></span>  
  
-   <span data-ttu-id="60a47-163">Quando você atualizar um banco de dados existente para [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], o valor de **DIRECTORY_NAME** será nulo.</span><span class="sxs-lookup"><span data-stu-id="60a47-163">When you upgrade an existing database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the value of **DIRECTORY_NAME** is null.</span></span>  
  
-   <span data-ttu-id="60a47-164">Quando você habilita ou desabilita o acesso não transacional no nível de banco de dados, a operação não verifica se o nome de diretório foi especificado ou se é exclusivo.</span><span class="sxs-lookup"><span data-stu-id="60a47-164">When you enable or disable non-transactional access at the database level, the operation does not check whether the directory name has been specified or whether it is unique.</span></span>  
  
-   <span data-ttu-id="60a47-165">Quando você remove um banco de dados que foi habilitado para FileTables, o diretório no nível de banco de dados e todas as estruturas de diretórios de todos os FileTables contidos nele serão removidos.</span><span class="sxs-lookup"><span data-stu-id="60a47-165">When you drop a database that was enabled for FileTables, the database-level directory and all the directory stuctures of all the FileTables under it are removed.</span></span>  
  
  
