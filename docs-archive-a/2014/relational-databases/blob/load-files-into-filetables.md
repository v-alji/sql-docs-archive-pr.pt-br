---
title: Carregar arquivos em FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], migrating files
- FileTables [SQL Server], bulk loading
- FileTables [SQL Server], loading files
ms.assetid: dc842a10-0586-4b0f-9775-5ca0ecc761d9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 43ea31523da2dfa8b387f68ce4f7c7f07868dd6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684773"
---
# <a name="load-files-into-filetables"></a><span data-ttu-id="90753-102">Carregar arquivos em FileTables</span><span class="sxs-lookup"><span data-stu-id="90753-102">Load Files into FileTables</span></span>
  <span data-ttu-id="90753-103">Descreve como carregar ou migrar arquivos para FileTables.</span><span class="sxs-lookup"><span data-stu-id="90753-103">Describes how to load or migrate files into FileTables.</span></span>  
  
##  <a name="loading-or-migrating-files-into-a-filetable"></a><a name="BasicsLoadNew"></a> <span data-ttu-id="90753-104">Carregando ou migrando arquivos para um FileTable</span><span class="sxs-lookup"><span data-stu-id="90753-104">Loading or Migrating Files into a FileTable</span></span>  
 <span data-ttu-id="90753-105">O método que você escolhe para carregar ou migrar arquivos para uma FileTable depende em onde os arquivos estão armazenados atualmente.</span><span class="sxs-lookup"><span data-stu-id="90753-105">The method that you choose for loading or migrating files into a FileTable depends on where the files are currently stored.</span></span>  
  
|<span data-ttu-id="90753-106">Localização atual dos arquivos</span><span class="sxs-lookup"><span data-stu-id="90753-106">Current location of files</span></span>|<span data-ttu-id="90753-107">Opções de migração</span><span class="sxs-lookup"><span data-stu-id="90753-107">Options for migration</span></span>|  
|-------------------------------|---------------------------|  
|<span data-ttu-id="90753-108">Os arquivos estão atualmente armazenados no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="90753-108">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="90753-109">não tem conhecimento dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="90753-109">has no knowledge of the files.</span></span>|<span data-ttu-id="90753-110">Como uma FileTable é semelhante a uma pasta no sistema de arquivos do Windows, você pode carregar arquivos com facilidade em uma nova FileTable usando qualquer um dos métodos disponíveis para mover ou copiar arquivos.</span><span class="sxs-lookup"><span data-stu-id="90753-110">Since a FileTable appears as a folder in the Windows file system, you can easily load files into a new FileTable by using any of the available methods for moving or copying files.</span></span> <span data-ttu-id="90753-111">Esses métodos incluem o Windows Explorer, opções de linha de comando, inclusive xcopy e robocopy, e scripts ou aplicativos personalizados.</span><span class="sxs-lookup"><span data-stu-id="90753-111">These methods include Windows Explorer, command line options including xcopy and robocopy, and custom scripts or applications.</span></span><br /><br /> <span data-ttu-id="90753-112">Você não pode converter uma pasta existente em uma FileTable.</span><span class="sxs-lookup"><span data-stu-id="90753-112">You cannot convert an existing folder to a FileTable.</span></span>|  
|<span data-ttu-id="90753-113">Os arquivos estão atualmente armazenados no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="90753-113">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="90753-114">contém uma tabela de metadados que possui ponteiros para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="90753-114">contains a table of metadata that contains pointers to the files.</span></span>|<span data-ttu-id="90753-115">A primeira etapa é mover ou copiar os arquivos usando um dos métodos mencionados acima.</span><span class="sxs-lookup"><span data-stu-id="90753-115">The first step is to move or copy the files by using one of the methods mentioned above.</span></span><br /><br /> <span data-ttu-id="90753-116">A segunda etapa é atualizar a tabela existente de metadados para apontar para o novo local dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="90753-116">The second step is to update the existing table of metadata to point to the new location of the files.</span></span><br /><br /> <span data-ttu-id="90753-117">Para obter mais informações, consulte [Exemplo: migrando arquivos do sistema de arquivos para uma FileTable](#HowToMigrateFiles) neste tópico.</span><span class="sxs-lookup"><span data-stu-id="90753-117">For more information, see [Example: Migrating Files from the File System into a FileTable](#HowToMigrateFiles) in this topic.</span></span>|  
  
###  <a name="how-to-load-files-into-a-filetable"></a><a name="HowToLoadNew"></a> <span data-ttu-id="90753-118">Como Carregar arquivos em uma nova FileTable</span><span class="sxs-lookup"><span data-stu-id="90753-118">How To: Load Files into a FileTable</span></span>  
 <span data-ttu-id="90753-119">Os métodos que você pode usar para carregar arquivos em uma FileTable incluem os seguintes:</span><span class="sxs-lookup"><span data-stu-id="90753-119">The methods that you can use to load files into a FileTable include the following:</span></span>  
  
-   <span data-ttu-id="90753-120">Arrastar e soltar arquivos das pastas de origem para a pasta da nova FileTable no Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="90753-120">Drag and drop files from the source folders to the new FileTable folder in Windows Explorer.</span></span>  
  
-   <span data-ttu-id="90753-121">Usar opções de linha de comando, como MOVE, COPY, XCOPY ou ROBOCOPY, no prompt de comando ou em um arquivo em lotes ou script.</span><span class="sxs-lookup"><span data-stu-id="90753-121">Use command line options such as MOVE, COPY, XCOPY, or ROBOCOPY from the command prompt or in a batch file or script.</span></span>  
  
-   <span data-ttu-id="90753-122">Escrever um aplicativo personalizado em C# ou Visual Basic.NET que use métodos do namespace **System.IO** para mover ou copiar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="90753-122">Write a custom application in C# or Visual Basic.NET that uses methods from the **System.IO** namespace to move or copy the files.</span></span>  
  
###  <a name="example-migrating-files-from-the-file-system-into-a-filetable"></a><a name="HowToMigrateFiles"></a> <span data-ttu-id="90753-123">Exemplo: migrando arquivos do sistema de arquivos para uma FileTable</span><span class="sxs-lookup"><span data-stu-id="90753-123">Example: Migrating Files from the File System into a FileTable</span></span>  
 <span data-ttu-id="90753-124">Neste cenário, seus arquivos são armazenados no sistema de arquivos, e você tem uma tabela de metadados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contém ponteiros para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="90753-124">In this scenario, your files are stored in the file system, and you have a table of metadata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains pointers to the files.</span></span> <span data-ttu-id="90753-125">Você deseja mover os arquivos para uma FileTable e, em seguida, substituir o caminho UNC original de cada arquivo dos metadados pelo caminho UNC da FileTable.</span><span class="sxs-lookup"><span data-stu-id="90753-125">You want to move the files into a FileTable, and then replace the original UNC path for each file in the metadata with the FileTable UNC path.</span></span> <span data-ttu-id="90753-126">A função [GetPathLocator & #40. O Transact-SQL e 41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) ajuda você a atingir esse objetivo.</span><span class="sxs-lookup"><span data-stu-id="90753-126">The [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function helps you to achieve this goal.</span></span>  
  
 <span data-ttu-id="90753-127">Para este exemplo, suponha que exista uma tabela de banco de dados existente, `PhotoMetadata` , que contém informações sobre fotografias.</span><span class="sxs-lookup"><span data-stu-id="90753-127">For this example, assume that there is an existing database table, `PhotoMetadata`, which contains data about photographs.</span></span> <span data-ttu-id="90753-128">Esta tabela tem um coluna `UNCPath` do tipo `varchar`(512) que contém o caminho UNC real para um arquivo .jpg.</span><span class="sxs-lookup"><span data-stu-id="90753-128">This table has a column `UNCPath` of type `varchar`(512) which contains the actual UNC path to a .jpg file.</span></span>  
  
 <span data-ttu-id="90753-129">Para migrar os arquivos de imagem do sistema de arquivos para uma FileTable, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="90753-129">To migrate the image files from the file system into a FileTable, you have to do the following:</span></span>  
  
1.  <span data-ttu-id="90753-130">Crie uma nova FileTable para armazenar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="90753-130">Create a new FileTable to hold the files.</span></span> <span data-ttu-id="90753-131">Este exemplo usa o nome de tabela `dbo.PhotoTable`, mas não mostra o código para criar a tabela.</span><span class="sxs-lookup"><span data-stu-id="90753-131">This example uses the table name, `dbo.PhotoTable`, but does not show the code to create the table.</span></span>  
  
2.  <span data-ttu-id="90753-132">Use xcopy ou uma ferramenta semelhante para copiar os arquivos .jpg, com a respectiva estrutura de diretórios, no diretório raiz da FileTable.</span><span class="sxs-lookup"><span data-stu-id="90753-132">Use xcopy or a similar tool to copy the .jpg files, with their directory structure, into the root directory of the FileTable.</span></span>  
  
3.  <span data-ttu-id="90753-133">Corrija os metadados na tabela `PhotoMetadata` usando código semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="90753-133">Fix the metadata in the `PhotoMetadata` table, by using code similar to the following:</span></span>  
  
```sql  
--  Add a path locator column to the PhotoMetadata table.  
ALTER TABLE PhotoMetadata ADD pathlocator hierarchyid;  
  
-- Get the root path of the Photo directory on the File Server.  
DECLARE @UNCPathRoot varchar(100) = '\\RemoteShare\Photographs';  
  
-- Get the root path of the FileTable.  
DECLARE @FileTableRoot varchar(1000);  
SELECT @FileTableRoot = FileTableRootPath('dbo.PhotoTable');  
  
-- Update the PhotoMetadata table.  
  
-- Replace the File Server UNC path with the FileTable path.  
UPDATE PhotoMetadata  
    SET UNCPath = REPLACE(UNCPath, @UNCPathRoot, @FileTableRoot);  
  
-- Update the pathlocator column to contain the pathlocator IDs from the FileTable.  
UPDATE PhotoMetadata  
    SET pathlocator = GetPathLocator(UNCPath);  
```  
  
##  <a name="bulk-loading-files-into-a-filetable"></a><a name="BasicsBulkLoad"></a> <span data-ttu-id="90753-134">Carregando arquivos em massa em uma FileTable</span><span class="sxs-lookup"><span data-stu-id="90753-134">Bulk Loading Files into a FileTable</span></span>  
 <span data-ttu-id="90753-135">Um FileTable tem o comportamento semelhante ao de uma tabela normal para operações em massa, com as qualificações a seguir.</span><span class="sxs-lookup"><span data-stu-id="90753-135">A FileTable behaves like a normal table for bulk operations, with the following qualifications.</span></span>  
  
 <span data-ttu-id="90753-136">Uma FileTable possui restrições definidas pelo sistema que assegura que a integridade do namespace de arquivo e diretório seja mantida.</span><span class="sxs-lookup"><span data-stu-id="90753-136">A FileTable has system-defined constraints which ensure that the integrity of the file and directory namespace is maintained.</span></span> <span data-ttu-id="90753-137">Essas restrições têm de ser verificadas nos dados carregados em massa na FileTable.</span><span class="sxs-lookup"><span data-stu-id="90753-137">These constraints have to be verified on the data bulk loaded into the FileTable.</span></span> <span data-ttu-id="90753-138">Algumas operações de inserção em massa permitem ignorar as restrições de tabela. Os requisitos a seguir são impostos.</span><span class="sxs-lookup"><span data-stu-id="90753-138">Since some bulk insert operations allow table constraints to be ignored, the following requirements are enforced.</span></span>  
  
-   <span data-ttu-id="90753-139">As operações de carregamento em massa que impõem restrições podem ser executadas em uma FileTable como em qualquer outra tabela.</span><span class="sxs-lookup"><span data-stu-id="90753-139">Bulk loading operations that enforce constraints can be run against a FileTable as against any other table.</span></span> <span data-ttu-id="90753-140">Essa categoria inclui as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="90753-140">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="90753-141">bcp com a cláusula CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="90753-141">bcp with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="90753-142">BULK INSERT com a cláusula CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="90753-142">BULK INSERT with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="90753-143">INSERT INTO... SELECT \* FROM OPENROWSET(BULK ...) sem a cláusula IGNORE_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="90753-143">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) without IGNORE_CONSTRAINTS clause.</span></span>  
  
-   <span data-ttu-id="90753-144">Operações de carregamento de tamanho que não impõem restrições falham a menos que as restrições definidas pelo sistema da FileTable sejam desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="90753-144">Bulk loading operations that do not enforce constraints fail unless the FileTable system-defined constraints have been disabled.</span></span> <span data-ttu-id="90753-145">Essa categoria inclui as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="90753-145">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="90753-146">bcp sem a cláusula CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="90753-146">bcp without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="90753-147">BULK INSERT sem a cláusula CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="90753-147">BULK INSERT without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="90753-148">INSERT INTO... SELECT \* FROM OPENROWSET(BULK ...) com a cláusula IGNORE_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="90753-148">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) with IGNORE_CONSTRAINTS clause.</span></span>  
  
###  <a name="how-to-bulk-load-files-into-a-filetable"></a><a name="HowToBulkLoad"></a> <span data-ttu-id="90753-149">Como Carregar arquivos em massa em uma nova FileTable</span><span class="sxs-lookup"><span data-stu-id="90753-149">How To: Bulk Load Files into a FileTable</span></span>  
 <span data-ttu-id="90753-150">Você pode usar vários métodos para carregar arquivos em massa em uma FileTable:</span><span class="sxs-lookup"><span data-stu-id="90753-150">You can use various methods to bulk load files into a FileTable:</span></span>  
  
-   <span data-ttu-id="90753-151">**bcp**</span><span class="sxs-lookup"><span data-stu-id="90753-151">**bcp**</span></span>  
  
    -   <span data-ttu-id="90753-152">Chame com a cláusula **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="90753-152">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="90753-153">Desabilite o namespace da FileTable e chame sem a cláusula **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="90753-153">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="90753-154">Em seguida, reabilite o namespace da FileTable.</span><span class="sxs-lookup"><span data-stu-id="90753-154">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="90753-155">**BULK INSERT**</span><span class="sxs-lookup"><span data-stu-id="90753-155">**BULK INSERT**</span></span>  
  
    -   <span data-ttu-id="90753-156">Chame com a cláusula **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="90753-156">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="90753-157">Desabilite o namespace da FileTable e chame sem a cláusula **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="90753-157">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="90753-158">Em seguida, reabilite o namespace da FileTable.</span><span class="sxs-lookup"><span data-stu-id="90753-158">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="90753-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...)**</span><span class="sxs-lookup"><span data-stu-id="90753-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...)**</span></span>  
  
    -   <span data-ttu-id="90753-160">Chame com a cláusula **IGNORE_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="90753-160">Call with the **IGNORE_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="90753-161">Desabilite o namespace da FileTable e chame sem a cláusula **IGNORE_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="90753-161">Disable the FileTable namespace and call without the **IGNORE_CONSTRAINTS** clause.</span></span> <span data-ttu-id="90753-162">Em seguida, reabilite o namespace da FileTable.</span><span class="sxs-lookup"><span data-stu-id="90753-162">Then re-enable the FileTable namespace.</span></span>  
  
 <span data-ttu-id="90753-163">Para obter informações sobre como desabilitar as restrições de FileTable, consulte [Gerenciar FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="90753-163">For information about disabling the FileTable constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-disable-filetable-constraints-for-bulk-loading"></a><a name="disabling"></a> <span data-ttu-id="90753-164">Como Desabilitar restrições de FileTable para carregamento em massa</span><span class="sxs-lookup"><span data-stu-id="90753-164">How To: Disable FileTable Constraints for Bulk Loading</span></span>  
 <span data-ttu-id="90753-165">Para carregar os arquivos em massa em uma FileTable sem a sobrecarga de impor as restrições definidas pelo sistema, você pode desabilitar temporariamente as restrições.</span><span class="sxs-lookup"><span data-stu-id="90753-165">To bulk load files into a FileTable without the overhead of enforcing the system-defined constraints, you can temporarily disable the constraints.</span></span> <span data-ttu-id="90753-166">Para obter mais informações, consulte [Gerenciar FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="90753-166">For more information, see [Manage FileTables](manage-filetables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90753-167">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90753-167">See Also</span></span>  
 <span data-ttu-id="90753-168">[Acessar FileTables com Transact-SQL](access-filetables-with-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="90753-168">[Access FileTables with Transact-SQL](access-filetables-with-transact-sql.md) </span></span>  
 [<span data-ttu-id="90753-169">Acessar FileTables com APIs de entrada e saída de arquivo</span><span class="sxs-lookup"><span data-stu-id="90753-169">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
  
  
