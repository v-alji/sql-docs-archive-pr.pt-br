---
title: Trabalhar com diretórios e caminhos em FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], directories
ms.assetid: f1e45900-bea0-4f6f-924e-c11e1f98ab62
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4641159e894b764cbee4d7f02085f3ceb8e6d87d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678791"
---
# <a name="work-with-directories-and-paths-in-filetables"></a><span data-ttu-id="2de83-102">Trabalhar com diretórios e caminhos em FileTables</span><span class="sxs-lookup"><span data-stu-id="2de83-102">Work with Directories and Paths in FileTables</span></span>
  <span data-ttu-id="2de83-103">Descreve a estrutura de diretórios na qual os arquivos são armazenados em FileTables.</span><span class="sxs-lookup"><span data-stu-id="2de83-103">Describes the directory structure in which the files are stored in FileTables.</span></span>  
  
##  <a name="how-to-work-with-directories-and-paths-in-filetables"></a><a name="HowToDirectories"></a> <span data-ttu-id="2de83-104">Como Trabalhar com diretórios e caminhos em FileTables</span><span class="sxs-lookup"><span data-stu-id="2de83-104">How To: Work with Directories and Paths in FileTables</span></span>  
 <span data-ttu-id="2de83-105">É possível usar as 3 funções a seguir para trabalhar com diretórios FileTable no [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="2de83-105">You can use the following 3 functions to work with FileTable directories in [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
|<span data-ttu-id="2de83-106">Para obter este resultado</span><span class="sxs-lookup"><span data-stu-id="2de83-106">To get this result</span></span>|<span data-ttu-id="2de83-107">Use esta função</span><span class="sxs-lookup"><span data-stu-id="2de83-107">Use this function</span></span>|  
|------------------------|-----------------------|  
|<span data-ttu-id="2de83-108">Obtém o caminho UNC no nível raiz de uma FileTable específica ou do banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="2de83-108">Get the root-level UNC path for a specific FileTable or for the current database.</span></span>|[<span data-ttu-id="2de83-109">FileTableRootPath &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2de83-109">FileTableRootPath &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/filetablerootpath-transact-sql)|  
|<span data-ttu-id="2de83-110">Obtém um caminho UNC absoluto ou relativo de um arquivo ou diretório em uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="2de83-110">Get an absolute or relative UNC path for a file or directory in a FileTable.</span></span>|[<span data-ttu-id="2de83-111">GetFileNamespacePath &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2de83-111">GetFileNamespacePath &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql)|  
|<span data-ttu-id="2de83-112">Obtém a ID do localizador do caminho do arquivo ou diretório especificado em uma FileTable, fornecendo o caminho.</span><span class="sxs-lookup"><span data-stu-id="2de83-112">Get the path locator ID value for the specified file or directory in a FileTable, by providing the path.</span></span>|[<span data-ttu-id="2de83-113">GetPathLocator &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2de83-113">GetPathLocator &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/getpathlocator-transact-sql)|  
  
##  <a name="how-to-use-relative-paths-for-portable-code"></a><a name="BestPracticeRelativePaths"></a> <span data-ttu-id="2de83-114">Como usar caminhos relativos para código portátil</span><span class="sxs-lookup"><span data-stu-id="2de83-114">How to: Use Relative Paths for Portable Code</span></span>  
 <span data-ttu-id="2de83-115">Para manter código e aplicativos independentes do computador e do banco de dados atuais, evite escrever código baseado em caminhos de arquivo absolutos.</span><span class="sxs-lookup"><span data-stu-id="2de83-115">To keep code and applications independent of the current computer and database, avoid writing code that relies on absolute file paths.</span></span> <span data-ttu-id="2de83-116">Em vez disso, obtenha o caminho completo para um arquivo em tempo de execução usando as funções [FileTableRootPath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filetablerootpath-transact-sql) e [GetFileNamespacePath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql)juntas, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="2de83-116">Instead, get the complete path for a file at run time by using the [FileTableRootPath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filetablerootpath-transact-sql) and [GetFileNamespacePath &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getfilenamespacepath-transact-sql)) functions together, as shown in the following example.</span></span> <span data-ttu-id="2de83-117">Por padrão, a função `GetFileNamespacePath` retorna o caminho relativo do arquivo sob o caminho raiz do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2de83-117">By default, the `GetFileNamespacePath` function returns the relative path of the file under the root path for the database.</span></span>  
  
```sql  
USE database_name;  
DECLARE @root nvarchar(100);  
DECLARE @fullpath nvarchar(1000);  
  
SELECT @root = FileTableRootPath();  
SELECT @fullpath = @root + file_stream.GetFileNamespacePath()  
    FROM filetable_name  
    WHERE name = N'document_name';  
  
PRINT @fullpath;  
GO  
```  
  
##  <a name="important-restrictions"></a><a name="restrictions"></a> <span data-ttu-id="2de83-118">Restrições importantes</span><span class="sxs-lookup"><span data-stu-id="2de83-118">Important restrictions</span></span>  
  
###  <a name="nesting-level"></a><a name="nesting"></a> <span data-ttu-id="2de83-119">Nível de aninhamento</span><span class="sxs-lookup"><span data-stu-id="2de83-119">Nesting level</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2de83-120">Você não pode armazenar mais de 15 níveis de subdiretórios no diretório FileTable.</span><span class="sxs-lookup"><span data-stu-id="2de83-120">You cannot store more than 15 levels of subdirectories in the FileTable directory.</span></span> <span data-ttu-id="2de83-121">Quando você armazenar 15 níveis de subdiretórios, o nível mais baixo não poderá conter arquivos, pois esses arquivos representariam um nível adicional.</span><span class="sxs-lookup"><span data-stu-id="2de83-121">When you store 15 levels of subdirectories, then the lowest level cannot contain files, since these files would represent an additional level.</span></span>  
  
###  <a name="length-of-full-path-name"></a><a name="fqnlength"></a> <span data-ttu-id="2de83-122">Comprimento do nome do caminho completo</span><span class="sxs-lookup"><span data-stu-id="2de83-122">Length of full path name</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2de83-123">O sistema de arquivos NTFS oferece suporte a nomes do caminho maiores do que o limite de 260 caracteres do shell do Windows e da maioria das APIs do Windows.</span><span class="sxs-lookup"><span data-stu-id="2de83-123">The NTFS file system supports path names that are much longer than the 260-character limit of the Windows shell and most Windows APIs.</span></span> <span data-ttu-id="2de83-124">Portanto, é possível criar arquivos na hierarquia de arquivos de um FileTable usando Transact-SQL que você não poderá exibir ou abrir com o Windows Explorer ou com muitos outros aplicativos do Windows, porque o nome do caminho completo excede 260 caracteres.</span><span class="sxs-lookup"><span data-stu-id="2de83-124">Therefore it is possible to create files in the file hierarchy of a FileTable by using Transact-SQL that you cannot view or open with Windows Explorer or many other Windows applications, because the full path name exceeds 260 characters.</span></span> <span data-ttu-id="2de83-125">Entretanto, é possível continuar a acessar esses arquivos usando o Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="2de83-125">However you can continue to access these files by using Transact-SQL.</span></span>  
  
##  <a name="the-full-path-to-an-item-stored-in-a-filetable"></a><a name="fullpath"></a> <span data-ttu-id="2de83-126">O caminho completo para um item armazenado em uma FileTable</span><span class="sxs-lookup"><span data-stu-id="2de83-126">The full path to an item stored in a FileTable</span></span>  
 <span data-ttu-id="2de83-127">O caminho completo para um arquivo ou diretório armazenado em uma FileTable começa com os seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="2de83-127">The full path to a file or directory stored in a FileTable begins with the following elements:</span></span>  
  
1.  <span data-ttu-id="2de83-128">O compartilhamento habilitado para acesso de E/S de arquivos FILESTREAM no nível da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2de83-128">The share enabled for FILESTREAM file I/O access at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance level.</span></span>  
  
2.  <span data-ttu-id="2de83-129">O **DIRECTORY_NAME** especificado no nível do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2de83-129">The **DIRECTORY_NAME** specified at the database level.</span></span>  
  
3.  <span data-ttu-id="2de83-130">O **FILETABLE_DIRECTORY** especificado no nível de FileTable.</span><span class="sxs-lookup"><span data-stu-id="2de83-130">The **FILETABLE_DIRECTORY** specified at the FileTable level.</span></span>  
  
 <span data-ttu-id="2de83-131">A hierarquia resultante será semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="2de83-131">The resulting hierarchy looks like this:</span></span>  
  
 `\\<machine>\<instance-level FILESTREAM share>\<database-level directory>\<FileTable directory>\`  
  
 <span data-ttu-id="2de83-132">Essa hierarquia de diretórios forma a raiz de um namespace de arquivo da FileTable.</span><span class="sxs-lookup"><span data-stu-id="2de83-132">This directory hierarchy forms the root of the FileTable's file namespace.</span></span> <span data-ttu-id="2de83-133">Sob essa hierarquia de diretórios, os dados do FILESTREAM da FileTable são armazenados como arquivos e subdiretórios que também podem conter arquivos e subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="2de83-133">Under this directory hierarchy, the FILESTREAM data for the FileTable is stored as files, and as subdirectories which can also contain files and subdirectories.</span></span>  
  
 <span data-ttu-id="2de83-134">É importante ter em mente que a hierarquia de diretórios criada sob o compartilhamento do FILESTREAM no nível da instância é uma hierarquia de diretórios virtuais.</span><span class="sxs-lookup"><span data-stu-id="2de83-134">It is important to keep in mind that the directory hierarchy created under the instance-level FILESTREAM share is a virtual directory hierarchy.</span></span> <span data-ttu-id="2de83-135">Essa hierarquia é armazenada no banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e não é representada fisicamente no sistema de arquivos NTFS.</span><span class="sxs-lookup"><span data-stu-id="2de83-135">This hierarchy is stored in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and is not represented physically in the NTFS file system.</span></span> <span data-ttu-id="2de83-136">Todas as operações que acessam arquivos e diretórios sob o compartilhamento do FILESTREAM e nas FileTables são interceptadas e tratadas por um componente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inserido no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2de83-136">All operations that access files and directories under the FILESTREAM share and in the FileTables that it contains are intercepted and handled by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component embedded in the file system.</span></span>  
  
##  <a name="the-semantics-of-the-root-directories-at-the-instance-database-and-filetable-levels"></a><a name="roots"></a> <span data-ttu-id="2de83-137">A semântica dos diretórios raiz nos níveis de instância, banco de dados e FileTable</span><span class="sxs-lookup"><span data-stu-id="2de83-137">The semantics of the root directories at the instance, database, and FileTable levels</span></span>  
 <span data-ttu-id="2de83-138">Essa hierarquia de diretórios observa a seguinte semântica:</span><span class="sxs-lookup"><span data-stu-id="2de83-138">This directory hierarchy observes the following semantics:</span></span>  
  
-   <span data-ttu-id="2de83-139">O compartilhamento do FILESTREAM do nível da instância é configurado por um administrador e armazenado como propriedade do servidor.</span><span class="sxs-lookup"><span data-stu-id="2de83-139">The instance-level FILESTREAM share is configured by an administrator and stored as a property of the server.</span></span> <span data-ttu-id="2de83-140">Você pode renomear esse compartilhamento usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2de83-140">You can rename this share by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="2de83-141">Uma operação de renomeação não entra em vigor até que o servidor seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="2de83-141">A renaming operation does not take effect until the server is restarted.</span></span>  
  
-   <span data-ttu-id="2de83-142">O nível do banco de dados **DIRECTORY_NAME** é nulo por padrão quando você cria um novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2de83-142">The database-level **DIRECTORY_NAME** is null by default when you create a new database.</span></span> <span data-ttu-id="2de83-143">Um administrador pode definir ou alterar esse nome usando a instrução **ALTER DATABASE** .</span><span class="sxs-lookup"><span data-stu-id="2de83-143">An administrator can set or change this name by using the **ALTER DATABASE** statement.</span></span> <span data-ttu-id="2de83-144">O nome deve ser exclusivo (em uma comparação sem diferenciação de maiúsculas e minúsculas) nessa instância.</span><span class="sxs-lookup"><span data-stu-id="2de83-144">The name must be unique (in a case-insensitive comparison) in that instance.</span></span>  
  
-   <span data-ttu-id="2de83-145">Normalmente, você fornece o nome **FILETABLE_DIRECTORY** como parte da instrução **CREATE TABLE** quando você cria uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="2de83-145">You typically provide the **FILETABLE_DIRECTORY** name as part of the **CREATE TABLE** statement when you create a FileTable.</span></span> <span data-ttu-id="2de83-146">Você pode alterar esse nome usando o comando **ALTER TABLE** .</span><span class="sxs-lookup"><span data-stu-id="2de83-146">You can change this name by using the **ALTER TABLE** command.</span></span>  
  
-   <span data-ttu-id="2de83-147">Você não pode renomear esses diretórios raiz por operações de E/S de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2de83-147">You cannot rename these root directories through file I/O operations.</span></span>  
  
-   <span data-ttu-id="2de83-148">Você não pode abrir esses diretórios raiz com identificadores de arquivo exclusivos.</span><span class="sxs-lookup"><span data-stu-id="2de83-148">You cannot open these root directories with exclusive file handles.</span></span>  
  
##  <a name="the-is_directory-column-in-the-filetable-schema"></a><a name="is_directory"></a> <span data-ttu-id="2de83-149">A coluna is_directory no esquema de FileTable</span><span class="sxs-lookup"><span data-stu-id="2de83-149">The is_directory column in the FileTable schema</span></span>  
 <span data-ttu-id="2de83-150">A tabela a seguir descreve a interação entre a coluna **is_directory** e a coluna **file_stream** que contém os dados do FILESTREAM em uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="2de83-150">The following table describes the interaction between the **is_directory** column and the **file_stream** column that contains the FILESTREAM data in a FileTable.</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="2de83-151">*is_directory* **value**</span><span class="sxs-lookup"><span data-stu-id="2de83-151">*is_directory* **value**</span></span>|<span data-ttu-id="2de83-152">*file_stream* **value**</span><span class="sxs-lookup"><span data-stu-id="2de83-152">*file_stream* **value**</span></span>|<span data-ttu-id="2de83-153">**Comportamento**</span><span class="sxs-lookup"><span data-stu-id="2de83-153">**Behavior**</span></span>|  
|<span data-ttu-id="2de83-154">FALSE</span><span class="sxs-lookup"><span data-stu-id="2de83-154">FALSE</span></span>|<span data-ttu-id="2de83-155">NULO</span><span class="sxs-lookup"><span data-stu-id="2de83-155">NULL</span></span>|<span data-ttu-id="2de83-156">Esta é uma combinação inválida que será capturada por uma restrição definida por sistema.</span><span class="sxs-lookup"><span data-stu-id="2de83-156">This is an invalid combination that will be caught by a system-defined constraint.</span></span>|  
|<span data-ttu-id="2de83-157">FALSE</span><span class="sxs-lookup"><span data-stu-id="2de83-157">FALSE</span></span>|\<value>|<span data-ttu-id="2de83-158">O item representa um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2de83-158">The item represents a file.</span></span>|  
|<span data-ttu-id="2de83-159">TRUE</span><span class="sxs-lookup"><span data-stu-id="2de83-159">TRUE</span></span>|<span data-ttu-id="2de83-160">NULO</span><span class="sxs-lookup"><span data-stu-id="2de83-160">NULL</span></span>|<span data-ttu-id="2de83-161">O item representa um diretório.</span><span class="sxs-lookup"><span data-stu-id="2de83-161">The item represents a directory.</span></span>|  
|<span data-ttu-id="2de83-162">TRUE</span><span class="sxs-lookup"><span data-stu-id="2de83-162">TRUE</span></span>|\<value>|<span data-ttu-id="2de83-163">Esta é uma combinação inválida que será capturada por uma restrição definida por sistema.</span><span class="sxs-lookup"><span data-stu-id="2de83-163">This is an invalid combination that will be caught by a system-defined constraint.</span></span>|  
  
##  <a name="using-virtual-network-names-vnns-with-alwayson-availability-groups"></a><a name="alwayson"></a> <span data-ttu-id="2de83-164">Usando VNNs (nomes de rede virtual) com grupos de disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="2de83-164">Using Virtual Network Names (VNNs) with AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="2de83-165">Quando o banco de dados que contém dados FILESTREAM ou FileTable pertence a um grupo de disponibilidade AlwaysOn:</span><span class="sxs-lookup"><span data-stu-id="2de83-165">When the database that contains FILESTREAM or FileTable data belongs to an AlwaysOn availability group:</span></span>  
  
-   <span data-ttu-id="2de83-166">As funções FILESTREAM e FileTable aceitam ou retornam VNNs (nomes de rede virtual) em vez de nomes de computadores.</span><span class="sxs-lookup"><span data-stu-id="2de83-166">The FILESTREAM and FileTable functions accept or return virtual network names (VNNs) instead of computer names.</span></span> <span data-ttu-id="2de83-167">Para obter mais informações sobre essas funções, veja [Funções Filestream e FileTable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2de83-167">For more information about these functions, see [Filestream and FileTable Functions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/filestream-and-filetable-functions-transact-sql).</span></span>  
  
-   <span data-ttu-id="2de83-168">Todo o acesso aos dados FILESTREAM ou FileTable pelas APIs do sistema de arquivos deve usar VNNs em vez de nomes de computadores.</span><span class="sxs-lookup"><span data-stu-id="2de83-168">All access to FILESTREAM or FileTable data through the file system APIs should use VNNs instead of computer names.</span></span> <span data-ttu-id="2de83-169">Para obter mais informações, veja [FILESTREAM e FileTable com grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/filestream-and-filetable-with-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2de83-169">For more information, see [FILESTREAM and FileTable with AlwaysOn Availability Groups &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/filestream-and-filetable-with-always-on-availability-groups-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de83-170">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2de83-170">See Also</span></span>  
 <span data-ttu-id="2de83-171">[Habilitar os pré-requisitos para FileTable](enable-the-prerequisites-for-filetable.md) </span><span class="sxs-lookup"><span data-stu-id="2de83-171">[Enable the Prerequisites for FileTable](enable-the-prerequisites-for-filetable.md) </span></span>  
 <span data-ttu-id="2de83-172">[Criar, alterar e remover FileTables](create-alter-and-drop-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="2de83-172">[Create, Alter, and Drop FileTables](create-alter-and-drop-filetables.md) </span></span>  
 <span data-ttu-id="2de83-173">[Acessar FileTables com Transact-SQL](access-filetables-with-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="2de83-173">[Access FileTables with Transact-SQL](access-filetables-with-transact-sql.md) </span></span>  
 [<span data-ttu-id="2de83-174">Acessar FileTables com APIs de entrada e saída de arquivo</span><span class="sxs-lookup"><span data-stu-id="2de83-174">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
  
  
