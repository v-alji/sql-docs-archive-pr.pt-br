---
title: Criar, alterar e remover FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], altering
- FileTables [SQL Server], dropping
- FileTables [SQL Server], creating
ms.assetid: 47d69e37-8778-4630-809b-2261b5c41c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a10e6333f6dd38a850a832b82a7cb7a0e0bf698
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570072"
---
# <a name="create-alter-and-drop-filetables"></a><span data-ttu-id="a28d0-102">Criar, alterar e remover FileTables</span><span class="sxs-lookup"><span data-stu-id="a28d0-102">Create, Alter, and Drop FileTables</span></span>
  <span data-ttu-id="a28d0-103">Descreve como criar uma nova FileTable, ou alterar ou remover uma FileTable existente.</span><span class="sxs-lookup"><span data-stu-id="a28d0-103">Describes how to create a new FileTable, or alter or drop an existing FileTable.</span></span>  
  
##  <a name="creating-a-filetable"></a><a name="BasicsCreate"></a> <span data-ttu-id="a28d0-104">Criando uma FileTable</span><span class="sxs-lookup"><span data-stu-id="a28d0-104">Creating a FileTable</span></span>  
 <span data-ttu-id="a28d0-105">Uma FileTable é uma tabela de usuário especializada que tem um esquema predefinido e fixo.</span><span class="sxs-lookup"><span data-stu-id="a28d0-105">A FileTable is a specialized user table that has a pre-defined and fixed schema.</span></span> <span data-ttu-id="a28d0-106">Esse esquema armazena dados FILESTREAM, informações de arquivo e diretório e atributos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a28d0-106">This schema stores FILESTREAM data, file and directory information, and file attributes.</span></span> <span data-ttu-id="a28d0-107">Para obter informações sobre o esquema do FileTable, consulte [FileTable Schema](filetable-schema.md).</span><span class="sxs-lookup"><span data-stu-id="a28d0-107">For information about the FileTable schema, see [FileTable Schema](filetable-schema.md).</span></span>  
  
 <span data-ttu-id="a28d0-108">Você pode criar uma nova FileTable usando Transact-SQL ou o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a28d0-108">You can create a new FileTable by using Transact-SQL or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a28d0-109">Como uma FileTable tem um esquema fixo, você não precisa especificar uma lista de colunas.</span><span class="sxs-lookup"><span data-stu-id="a28d0-109">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="a28d0-110">A sintaxe simples de criação de uma FileTable permite que você especifique:</span><span class="sxs-lookup"><span data-stu-id="a28d0-110">The simple syntax for creating a FileTable lets you specify:</span></span>  
  
-   <span data-ttu-id="a28d0-111">Um nome de diretório.</span><span class="sxs-lookup"><span data-stu-id="a28d0-111">A directory name.</span></span> <span data-ttu-id="a28d0-112">Na hierarquia de pastas de FileTable, esse diretório em nível de tabela se torna o filho do diretório de banco de dados especificado no nível de banco de dados, e o pai dos arquivos ou diretórios armazenados na tabela.</span><span class="sxs-lookup"><span data-stu-id="a28d0-112">In the FileTable folder hierarchy, this table-level directory becomes the child of the database directory specified at the database level, and the parent of the files or directories stored in the table.</span></span>  
  
-   <span data-ttu-id="a28d0-113">O nome da ordenação a ser usado para nomes de arquivo na coluna **Name** da FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-113">The name of the collation to be used for file names in the **Name** column of the FileTable.</span></span>  
  
-   <span data-ttu-id="a28d0-114">Os nomes a serem usados para as 3 chaves primária e restrições exclusivas que são criadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a28d0-114">The names to be used for the 3 primary key and unique constraints that are automatically created.</span></span>  
  
###  <a name="how-to-create-a-filetable"></a><a name="HowToCreate"></a> <span data-ttu-id="a28d0-115">Como criar uma FileTable</span><span class="sxs-lookup"><span data-stu-id="a28d0-115">How To: Create a FileTable</span></span>  
 <span data-ttu-id="a28d0-116">**Criar uma FileTable usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="a28d0-116">**Create a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="a28d0-117">Crie uma FileTable chamando a instrução [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) com a opção **AS FileTable**.</span><span class="sxs-lookup"><span data-stu-id="a28d0-117">Create a FileTable by calling the [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) statement with the **AS FileTable** option.</span></span> <span data-ttu-id="a28d0-118">Como uma FileTable tem um esquema fixo, você não precisa especificar uma lista de colunas.</span><span class="sxs-lookup"><span data-stu-id="a28d0-118">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="a28d0-119">Você pode especificar as seguintes configurações para a nova FileTable:</span><span class="sxs-lookup"><span data-stu-id="a28d0-119">You can specify the following settings for the new FileTable:</span></span>  
  
1.  <span data-ttu-id="a28d0-120">**FILETABLE_DIRECTORY**.</span><span class="sxs-lookup"><span data-stu-id="a28d0-120">**FILETABLE_DIRECTORY**.</span></span> <span data-ttu-id="a28d0-121">Especifica o diretório que atua como diretório raiz de todos os arquivos e diretórios armazenados na FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-121">Specifies the directory that serves as the root directory for all the files and directories stored in the FileTable.</span></span> <span data-ttu-id="a28d0-122">Esse nome deve ser exclusivo entre todos os nomes de diretórios de FileTable no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a28d0-122">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="a28d0-123">A comparação de exclusividade não diferencia maiúsculas de minúsculas, independentemente das configurações de ordenação atuais.</span><span class="sxs-lookup"><span data-stu-id="a28d0-123">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="a28d0-124">Esse valor tem um tipo de dados **nvarchar(255)** e usa uma ordenação fixa de **Latin1_General_CI_AS_KS_WS**.</span><span class="sxs-lookup"><span data-stu-id="a28d0-124">This value has a data type of **nvarchar(255)** and uses a fixed collation of **Latin1_General_CI_AS_KS_WS**.</span></span>  
  
    -   <span data-ttu-id="a28d0-125">O nome de diretório que você fornece deve atender aos requisitos do sistema de arquivos para um nome de diretório válido.</span><span class="sxs-lookup"><span data-stu-id="a28d0-125">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
    -   <span data-ttu-id="a28d0-126">Esse nome deve ser exclusivo entre todos os nomes de diretórios de FileTable no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a28d0-126">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="a28d0-127">A comparação de exclusividade não diferencia maiúsculas de minúsculas, independentemente das configurações de ordenação atuais.</span><span class="sxs-lookup"><span data-stu-id="a28d0-127">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="a28d0-128">Se você não fornecer um nome de diretório ao criar a FileTable, o nome da FileTable será usado como nome do diretório.</span><span class="sxs-lookup"><span data-stu-id="a28d0-128">If you do not provide a directory name when you create the FileTable, then the name of the FileTable itself is used as the directory name.</span></span>  
  
2.  <span data-ttu-id="a28d0-129">**FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="a28d0-129">**FILETABLE_COLLATE_FILENAME**.</span></span> <span data-ttu-id="a28d0-130">Especifica o nome da ordenação a ser aplicado à coluna **Name** da FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-130">Specifies the name of the collation to be applied to the **Name** column in the FileTable.</span></span>  
  
    1.  <span data-ttu-id="a28d0-131">A ordenação especificada não deve fazer **diferenciação de maiúsculas e minúsculas** para estar em conformidade com a semântica de nomenclatura de arquivo do Windows.</span><span class="sxs-lookup"><span data-stu-id="a28d0-131">The specified collation must be **case-insensitive** to comply with Windows file naming semantics.</span></span>  
  
    2.  <span data-ttu-id="a28d0-132">Se você não fornecer um valor para **FILETABLE_COLLATE_FILENAME** ou se você especificar **database_default**, a coluna herdará a ordenação do banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="a28d0-132">If you do not provide a value for **FILETABLE_COLLATE_FILENAME**, or you specify **database_default**, the column inherits the collation of the current database.</span></span> <span data-ttu-id="a28d0-133">Se a ordenação do banco de dados atual diferenciar maiúsculas de minúsculas, será gerado um erro e a operação **CREATE TABLE** falhará.</span><span class="sxs-lookup"><span data-stu-id="a28d0-133">If the current database collation is case-sensitive, an error is raised and the **CREATE TABLE** operation fails.</span></span>  
  
3.  <span data-ttu-id="a28d0-134">Você também pode especificar os nomes a serem usados para as 3 restrições de chave primária e exclusivas que são criadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a28d0-134">You can also specify the names to be used for the 3 primary key and unique constraints that are automatically created.</span></span> <span data-ttu-id="a28d0-135">Se você não fornecer nomes, o sistema gerará nomes conforme descrito posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a28d0-135">If you do not provide names, then the system generates names as described later in this topic.</span></span>  
  
    -   <span data-ttu-id="a28d0-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="a28d0-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="a28d0-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="a28d0-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="a28d0-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="a28d0-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
 <span data-ttu-id="a28d0-139">**Exemplos**</span><span class="sxs-lookup"><span data-stu-id="a28d0-139">**Examples**</span></span>  
  
 <span data-ttu-id="a28d0-140">O exemplo a seguir cria uma nova FileTable e especifica valores definidos pelo usuário para **FILETABLE_DIRECTORY** e **FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="a28d0-140">The following example creates a new FileTable and specifies user-defined values for both **FILETABLE_DIRECTORY** and **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable  
    WITH (   
          FileTable_Directory = 'DocumentTable',  
          FileTable_Collate_Filename = database_default  
         );  
GO  
```  
  
 <span data-ttu-id="a28d0-141">O exemplo a seguir também cria uma nova FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-141">The following example also creates a new FileTable.</span></span> <span data-ttu-id="a28d0-142">Como os valores definidos pelo usuário não são especificados, o nome de **FILETABLE_DIRECTORY** se torna o nome do FileTable, o valor de **FILETABLE_COLLATE_FILENAME** se torna database_default e a chave primária e as restrições exclusivas recebem nomes gerados pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="a28d0-142">Since user-defined values are not specified, the value of **FILETABLE_DIRECTORY** becomes the name of the FileTable, the value of **FILETABLE_COLLATE_FILENAME** becomes database_default, and the primary key and unique contraints receive system-generated names.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable;  
GO  
```  
  
 <span data-ttu-id="a28d0-143">**Criar uma FileTable usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="a28d0-143">**Create a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="a28d0-144">No Pesquisador de Objetos, expanda os objetos do banco de dados selecionado, clique com o botão direito do mouse na pasta **Tabelas** e selecione **Nova FileTable**.</span><span class="sxs-lookup"><span data-stu-id="a28d0-144">In Object Explorer, expand the objects under the selected database, then right-click on the **Tables** folder, and then select **New FileTable**.</span></span>  
  
 <span data-ttu-id="a28d0-145">Esta opção abre uma nova janela de script que contém um modelo de script Transact-SQL que você pode personalizar e executar para criar uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-145">This option opens a new script window which contains a Transact-SQL script template that you can customize and run to create a FileTable.</span></span> <span data-ttu-id="a28d0-146">Use a opção **Especificar Valores para Parâmetros de Modelo** no menu **Consulta** para personalizar facilmente o script.</span><span class="sxs-lookup"><span data-stu-id="a28d0-146">Use the **Specify Values for Template Parameters** option on the **Query** menu to customize the script easily.</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-filetable"></a><a name="ReqCreate"></a> <span data-ttu-id="a28d0-147">Requisitos e restrições para a criação de uma FileTable</span><span class="sxs-lookup"><span data-stu-id="a28d0-147">Requirements and Restrictions for Creating a FileTable</span></span>  
  
-   <span data-ttu-id="a28d0-148">Você não pode alterar uma tabela existente para convertê-la em uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-148">You cannot alter an existing table to convert it into a FileTable.</span></span>  
  
-   <span data-ttu-id="a28d0-149">O diretório pai especificado anteriormente no nível do banco de dados deve ter um valor não nulo.</span><span class="sxs-lookup"><span data-stu-id="a28d0-149">The parent directory previously specified at the database level must have a non-null value.</span></span> <span data-ttu-id="a28d0-150">Para obter informações sobre a especificação do diretório no nível de banco de dados, consulte [Habilitar os pré-requisitos para FileTable](enable-the-prerequisites-for-filetable.md).</span><span class="sxs-lookup"><span data-stu-id="a28d0-150">For information about specifying the database-level directory, see [Enable the Prerequisites for FileTable](enable-the-prerequisites-for-filetable.md).</span></span>  
  
-   <span data-ttu-id="a28d0-151">Uma FileTable requer um grupo de arquivos FILESTREAM válido, já que uma FileTable contém uma coluna FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a28d0-151">A FileTable requires a valid FILESTREAM filegroup, since a FileTable contains a FILESTREAM column.</span></span> <span data-ttu-id="a28d0-152">Opcionalmente, você pode especificar um grupo de arquivos FILESTREAM válido como parte do comando **CREATE TABLE** para criação de uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-152">You can optionally specify a valid FILESTREAM filegroup as part of the **CREATE TABLE** command for creating a FileTable.</span></span> <span data-ttu-id="a28d0-153">Se você não especificar um grupo de arquivos, a FileTable usará o grupo de arquivos FILESTREAM padrão para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a28d0-153">If you do not specify a filegroup, then the FileTable uses the default FILESTREAM filegroup for the database.</span></span> <span data-ttu-id="a28d0-154">Se o banco de dados não tiver um grupo de arquivos FILESTREAM, será gerado um erro.</span><span class="sxs-lookup"><span data-stu-id="a28d0-154">If the database does not have a FILESTREAM filegroup, then an error is raised.</span></span>  
  
-   <span data-ttu-id="a28d0-155">Não é possível criar uma restrição de tabela como parte de uma instrução **CREATE TABLE...AS FILETABLE**.</span><span class="sxs-lookup"><span data-stu-id="a28d0-155">You cannot create a table constraint as part of a **CREATE TABLE...AS FILETABLE** statement.</span></span> <span data-ttu-id="a28d0-156">No entanto, você pode adicionar a restrição posteriormente usando uma instrução **ALTER TABLE** .</span><span class="sxs-lookup"><span data-stu-id="a28d0-156">However you can add the constraint later by using an **ALTER TABLE** statement.</span></span>  
  
-   <span data-ttu-id="a28d0-157">Não é possível criar uma FileTable no banco de dados **tempdb** ou em qualquer outro banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="a28d0-157">You cannot create a FileTable in the **tempdb** database or in any of the other system databases.</span></span>  
  
-   <span data-ttu-id="a28d0-158">Você não pode criar uma FileTable como uma tabela temporária.</span><span class="sxs-lookup"><span data-stu-id="a28d0-158">You cannot create a FileTable as a temporary table.</span></span>  
  
##  <a name="altering-a-filetable"></a><a name="BasicsAlter"></a> <span data-ttu-id="a28d0-159">Alterando uma FileTable</span><span class="sxs-lookup"><span data-stu-id="a28d0-159">Altering a FileTable</span></span>  
 <span data-ttu-id="a28d0-160">Como uma FileTable tem um esquema predefinido e fixo, você não pode adicionar nem alterar suas colunas.</span><span class="sxs-lookup"><span data-stu-id="a28d0-160">Since a FileTable has a pre-defined and fixed schema, you cannot add or change its columns.</span></span> <span data-ttu-id="a28d0-161">No entanto, você pode adicionar índices personalizados, gatilhos, restrições e outras opções a uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-161">However, you can add custom indexes, triggers, constraints, and other options to a FileTable.</span></span>  
  
 <span data-ttu-id="a28d0-162">Para obter informações sobre como usar a instrução ALTER TABLE para habilitar ou desabilitar o namespace da FileTable, incluindo as restrições definidas pelo sistema, consulte [Gerenciar FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="a28d0-162">For information about using the ALTER TABLE statement to enable or disable the FileTable namespace, including the system-defined constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-change-the-directory-for-a-filetable"></a><a name="HowToChange"></a> <span data-ttu-id="a28d0-163">Como alterar o diretório de uma FileTable</span><span class="sxs-lookup"><span data-stu-id="a28d0-163">How To: Change the Directory for a FileTable</span></span>  
 <span data-ttu-id="a28d0-164">**Alterar o diretório para uma FileTable usando Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="a28d0-164">**Change the Directory for a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="a28d0-165">Chame a instrução ALTER TABLE e forneça um novo valor válido para a opção **FILETABLE_DIRECTORY** SET.</span><span class="sxs-lookup"><span data-stu-id="a28d0-165">Call the ALTER TABLE statement and provide a valid new value for the **FILETABLE_DIRECTORY** SET option.</span></span>  
  
 <span data-ttu-id="a28d0-166">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="a28d0-166">**Example**</span></span>  
  
```sql  
ALTER TABLE filetable_name  
    SET ( FILETABLE_DIRECTORY = N'directory_name' );  
GO  
```  
  
 <span data-ttu-id="a28d0-167">**Alterar um diretório para uma FileTable usando o SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="a28d0-167">**Change the Directory for a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="a28d0-168">No Explorador de Objetos, clique com o botão direito do mouse em FileTable e selecione **Propriedades** para abrir a caixa de diálogo **Propriedades de Tabela** .</span><span class="sxs-lookup"><span data-stu-id="a28d0-168">In Object Explorer, right-click on the FileTable and select **Properties** to open the **Table Properties** dialog box.</span></span> <span data-ttu-id="a28d0-169">Na página **FileTable** , insira um novo valor para o **Nome de diretório da FileTable**.</span><span class="sxs-lookup"><span data-stu-id="a28d0-169">On the **FileTable** page, enter a new value for **FileTable directory name**.</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-a-filetable"></a><a name="ReqAlter"></a> <span data-ttu-id="a28d0-170">Requisitos e restrições para alterar uma FileTable</span><span class="sxs-lookup"><span data-stu-id="a28d0-170">Requirements and Restrictions for Altering a FileTable</span></span>  
  
-   <span data-ttu-id="a28d0-171">Você não pode alterar o valor de **FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="a28d0-171">You cannot alter the value of **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
-   <span data-ttu-id="a28d0-172">Você não pode alterar, remover ou desabilitar as colunas definidas pelo sistema de uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-172">You cannot change, drop, or disable the system-defined columns of a FileTable.</span></span>  
  
-   <span data-ttu-id="a28d0-173">Você não pode adicionar novas colunas de usuário, colunas computadas ou colunas computadas persistentes a uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-173">You cannot add new user columns, computed columns, or persisted computed columns to a FileTable.</span></span>  
  
##  <a name="dropping-a-filetable"></a><a name="BasicsDrop"></a> <span data-ttu-id="a28d0-174">Removendo uma FileTable</span><span class="sxs-lookup"><span data-stu-id="a28d0-174">Dropping a FileTable</span></span>  
 <span data-ttu-id="a28d0-175">Você pode remover uma FileTable usando a sintaxe normal da instrução [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a28d0-175">You can drop a FileTable by using the ordinary syntax for the [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="a28d0-176">Quando você remover uma FileTable, os seguintes objetos também serão removidos:</span><span class="sxs-lookup"><span data-stu-id="a28d0-176">When you drop a FileTable, the following objects are also dropped:</span></span>  
  
-   <span data-ttu-id="a28d0-177">Todas as colunas da FileTable e todos os objetos associados à tabela, como índices, restrições e gatilhos, também serão removidos.</span><span class="sxs-lookup"><span data-stu-id="a28d0-177">All the columns of the FileTable and all the objects associated with the table, such as indexes, constraints, and triggers, are also dropped.</span></span>  
  
-   <span data-ttu-id="a28d0-178">O diretório da FileTable e seus subdiretórios desaparecerão do arquivo FILESTREAM e da hierarquia de diretórios do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a28d0-178">The FileTable directory and the sub-directories that it contained disappear from the FILESTREAM file and directory hierarchy of the database.</span></span>  
  
 <span data-ttu-id="a28d0-179">O comando DROP TABLE falhará se houver identificadores de arquivos abertos no namespace de arquivo da FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-179">The DROP TABLE command fails if there are open file handles in the FileTable's file namespace.</span></span> <span data-ttu-id="a28d0-180">Para obter mais informações sobre o fechamento de identificadores abertos, consulte [Gerenciar FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="a28d0-180">For information about closing open handles, see [Manage FileTables](manage-filetables.md).</span></span>  
  
##  <a name="other-database-objects-are-created-when-you-create-a-filetable"></a><a name="BasicsOtherObjects"></a> <span data-ttu-id="a28d0-181">Outros objetos de banco de dados são criados quando você cria uma FileTable</span><span class="sxs-lookup"><span data-stu-id="a28d0-181">Other Database Objects Are Created When You Create a FileTable</span></span>  
 <span data-ttu-id="a28d0-182">Quando você cria uma nova FileTable, também são criados alguns índices e restrições definidos pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="a28d0-182">When you create a new FileTable, some system-defined indexes and constraints are also created.</span></span> <span data-ttu-id="a28d0-183">Você não pode alterar ou remover esses objetos. Eles desaparecem apenas quando a própria FileTable é removida.</span><span class="sxs-lookup"><span data-stu-id="a28d0-183">You cannot alter or drop these objects; they disappear only when the FileTable itself is dropped.</span></span> <span data-ttu-id="a28d0-184">Para ver a lista desses objetos, consulte a exibição de catálogo [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a28d0-184">To see the list of these objects, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
--View all objects for all filetables, unsorted  
SELECT * FROM sys.filetable_system_defined_objects;  
GO  
  
--View sorted list with friendly names  
SELECT OBJECT_NAME(parent_object_id) AS 'FileTable', OBJECT_NAME(object_id) AS 'System-defined Object'  
    FROM sys.filetable_system_defined_objects  
    ORDER BY FileTable, 'System-defined Object';  
GO  
```  
  
 <span data-ttu-id="a28d0-185">**Índices que são criados quando você cria uma nova FileTable**</span><span class="sxs-lookup"><span data-stu-id="a28d0-185">**Indexes that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="a28d0-186">Quando você cria uma nova FileTable, os seguintes índices definidos pelo sistema também são criados:</span><span class="sxs-lookup"><span data-stu-id="a28d0-186">When you create a new FileTable, the following system-defined indexes are also created:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a28d0-187">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="a28d0-187">**Columns**</span></span>|<span data-ttu-id="a28d0-188">**Tipo de índice**</span><span class="sxs-lookup"><span data-stu-id="a28d0-188">**Index type**</span></span>|  
|<span data-ttu-id="a28d0-189">[path_locator] ASC</span><span class="sxs-lookup"><span data-stu-id="a28d0-189">[path_locator] ASC</span></span>|<span data-ttu-id="a28d0-190">Chave primária, não clusterizado</span><span class="sxs-lookup"><span data-stu-id="a28d0-190">Primary Key, nonclustered</span></span>|  
|<span data-ttu-id="a28d0-191">[parent_path_locator] ASC,</span><span class="sxs-lookup"><span data-stu-id="a28d0-191">[parent_path_locator] ASC,</span></span><br /><br /> <span data-ttu-id="a28d0-192">[name] ASC</span><span class="sxs-lookup"><span data-stu-id="a28d0-192">[name] ASC</span></span>|<span data-ttu-id="a28d0-193">Exclusivo, não clusterizado</span><span class="sxs-lookup"><span data-stu-id="a28d0-193">Unique, nonclustered</span></span>|  
|<span data-ttu-id="a28d0-194">[stream_id] ASC</span><span class="sxs-lookup"><span data-stu-id="a28d0-194">[stream_id] ASC</span></span>|<span data-ttu-id="a28d0-195">Exclusivo, não clusterizado</span><span class="sxs-lookup"><span data-stu-id="a28d0-195">Unique, nonclustered</span></span>|  
  
 <span data-ttu-id="a28d0-196">**Restrições que são criadas quando você cria uma nova FileTable**</span><span class="sxs-lookup"><span data-stu-id="a28d0-196">**Constraints that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="a28d0-197">Quando você cria uma nova FileTable, as seguintes restrições definidas pelo sistema também são criadas:</span><span class="sxs-lookup"><span data-stu-id="a28d0-197">When you create a new FileTable, the following system-defined constraints are also created:</span></span>  
  
|<span data-ttu-id="a28d0-198">Restrições</span><span class="sxs-lookup"><span data-stu-id="a28d0-198">Constraints</span></span>|<span data-ttu-id="a28d0-199">Impõe</span><span class="sxs-lookup"><span data-stu-id="a28d0-199">Enforces</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="a28d0-200">Restrições padrão nas seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="a28d0-200">Default constraints on the following columns:</span></span><br /><br /> <span data-ttu-id="a28d0-201">**creation_time**</span><span class="sxs-lookup"><span data-stu-id="a28d0-201">**creation_time**</span></span> <br /> <span data-ttu-id="a28d0-202">**is_archive**</span><span class="sxs-lookup"><span data-stu-id="a28d0-202">**is_archive**</span></span> <br /> <span data-ttu-id="a28d0-203">**is_directory**</span><span class="sxs-lookup"><span data-stu-id="a28d0-203">**is_directory**</span></span> <br /> <span data-ttu-id="a28d0-204">**is_hidden**</span><span class="sxs-lookup"><span data-stu-id="a28d0-204">**is_hidden**</span></span> <br /> <span data-ttu-id="a28d0-205">**is_offline**</span><span class="sxs-lookup"><span data-stu-id="a28d0-205">**is_offline**</span></span> <br /> <span data-ttu-id="a28d0-206">**is_readonly**</span><span class="sxs-lookup"><span data-stu-id="a28d0-206">**is_readonly**</span></span> <br /> <span data-ttu-id="a28d0-207">**is_system**</span><span class="sxs-lookup"><span data-stu-id="a28d0-207">**is_system**</span></span> <br /> <span data-ttu-id="a28d0-208">**is_temporary**</span><span class="sxs-lookup"><span data-stu-id="a28d0-208">**is_temporary**</span></span> <br /> <span data-ttu-id="a28d0-209">**last_access_time**</span><span class="sxs-lookup"><span data-stu-id="a28d0-209">**last_access_time**</span></span> <br /> <span data-ttu-id="a28d0-210">**last_write_time**</span><span class="sxs-lookup"><span data-stu-id="a28d0-210">**last_write_time**</span></span> <br /> <span data-ttu-id="a28d0-211">**path_locator**</span><span class="sxs-lookup"><span data-stu-id="a28d0-211">**path_locator**</span></span> <br /> <span data-ttu-id="a28d0-212">**stream_id**</span><span class="sxs-lookup"><span data-stu-id="a28d0-212">**stream_id**</span></span>|<span data-ttu-id="a28d0-213">As restrições padrão definidas pelo sistema impõem valores padrão para as colunas especificadas.</span><span class="sxs-lookup"><span data-stu-id="a28d0-213">The system-defined default constraints enforce default values for the specified columns.</span></span>|  
|<span data-ttu-id="a28d0-214">Verificar restrições</span><span class="sxs-lookup"><span data-stu-id="a28d0-214">Check constraints</span></span>|<span data-ttu-id="a28d0-215">As restrições de verificação definidas pelo sistema impõem os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="a28d0-215">The system-defined check constraints enforce the following requirements:</span></span><br /><br /> <span data-ttu-id="a28d0-216">Nomes de arquivo válidos.</span><span class="sxs-lookup"><span data-stu-id="a28d0-216">Valid filenames.</span></span><br /><br /> <span data-ttu-id="a28d0-217">Atributos de arquivo válidos.</span><span class="sxs-lookup"><span data-stu-id="a28d0-217">Valid file attributes.</span></span><br /><br /> <span data-ttu-id="a28d0-218">O objeto pai deve ser um diretório.</span><span class="sxs-lookup"><span data-stu-id="a28d0-218">Parent object must be a directory.</span></span><br /><br /> <span data-ttu-id="a28d0-219">A hierarquia de namespaces é bloqueada durante a manipulação do arquivo.</span><span class="sxs-lookup"><span data-stu-id="a28d0-219">Namespace hierarchy is locked during file manipulation.</span></span>|  
  
 <span data-ttu-id="a28d0-220">**Convenção de nomenclatura para as restrições definidas pelo sistema**</span><span class="sxs-lookup"><span data-stu-id="a28d0-220">**Naming convention for the system-defined constraints**</span></span>  
 <span data-ttu-id="a28d0-221">As restrições definidas pelo sistema descritas acima são nomeadas no formato **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** , em que:</span><span class="sxs-lookup"><span data-stu-id="a28d0-221">The system-defined constraints described above are named in the format **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** where:</span></span>  
  
-   <span data-ttu-id="a28d0-222">*<constraint_type>* é CK (restrição de verificação), DF (restrição padrão), FK (chave estrangeira), PK (chave primária) ou UQ (restrição exclusiva).</span><span class="sxs-lookup"><span data-stu-id="a28d0-222">*<constraint_type>* is CK (check constraint), DF (default constraint), FK (foreign key), PK (primary key), or UQ (unique constraint).</span></span>  
  
-   <span data-ttu-id="a28d0-223">*\<uniquifier>* é uma cadeia de caracteres gerada pelo sistema para tornar o nome exclusivo.</span><span class="sxs-lookup"><span data-stu-id="a28d0-223">*\<uniquifier>* is a system-generated string to make the name unique.</span></span> <span data-ttu-id="a28d0-224">Essa cadeia de caracteres pode conter o nome e um identificador exclusivo da FileTable.</span><span class="sxs-lookup"><span data-stu-id="a28d0-224">This string may contain the FileTable name and a unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a28d0-225">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a28d0-225">See Also</span></span>  
 [<span data-ttu-id="a28d0-226">Gerenciar FileTables</span><span class="sxs-lookup"><span data-stu-id="a28d0-226">Manage FileTables</span></span>](manage-filetables.md)  
  
  
