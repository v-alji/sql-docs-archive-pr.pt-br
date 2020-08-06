---
title: Acessar FileTables com Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], accessing files with T-SQL
ms.assetid: 3c4a5ffb-c521-4696-99cb-2b03cffc9c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c47751ef34747e1b3742accf5040846ecde074f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683556"
---
# <a name="access-filetables-with-transact-sql"></a><span data-ttu-id="9d968-102">Acessar FileTables com Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9d968-102">Access FileTables with Transact-SQL</span></span>
  <span data-ttu-id="9d968-103">Descreve como os comandos DML (linguagem de manipulação de dados) do [!INCLUDE[tsql](../../includes/tsql-md.md)] funcionam em FileTables.</span><span class="sxs-lookup"><span data-stu-id="9d968-103">Describes how [!INCLUDE[tsql](../../includes/tsql-md.md)] data manipulation language (DML) commands work with FileTables.</span></span>  
  
##  <a name="insert-operations-on-filetables"></a><a name="BasicsInsert"></a> <span data-ttu-id="9d968-104">Operações INSERT em FileTables</span><span class="sxs-lookup"><span data-stu-id="9d968-104">INSERT Operations on FileTables</span></span>  
 <span data-ttu-id="9d968-105">As considerações a seguir se aplicam a operações **INSERT** em FileTables:</span><span class="sxs-lookup"><span data-stu-id="9d968-105">The following considerations apply to **INSERT** Operations on FileTables:</span></span>  
  
-   <span data-ttu-id="9d968-106">Todas as colunas de atributo de arquivo têm restrições NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="9d968-106">All the file attribute columns have NOT NULL constraints.</span></span> <span data-ttu-id="9d968-107">Se não forem definidos valores explicitamente, então serão fornecidos valores padrão apropriados.</span><span class="sxs-lookup"><span data-stu-id="9d968-107">If values are not explicitly set, then appropriate default values are supplied.</span></span>  
  
-   <span data-ttu-id="9d968-108">Serão impostas restrições definidas pelo sistema se a instrução INSERT definir **name**, **path_locator**, **parent_path_locator** ou atributos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9d968-108">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="9d968-109">O aplicativo pode obter o **path_locator** para um arquivo ou diretório fornecendo o caminho do sistema de arquivos à função [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9d968-109">The application can obtain the **path_locator** for a file or directory by providing the file system path to the [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function.</span></span>  
  
##  <a name="update-operations-on-filetables"></a><a name="BasicsUpdate"></a> <span data-ttu-id="9d968-110">Operações UPDATE em FileTables</span><span class="sxs-lookup"><span data-stu-id="9d968-110">UPDATE Operations on FileTables</span></span>  
 <span data-ttu-id="9d968-111">As considerações a seguir se aplicam a operações **UPDATE** em FileTables:</span><span class="sxs-lookup"><span data-stu-id="9d968-111">The following considerations apply to **UPDATE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="9d968-112">São permitidas atualizações em quaisquer dados definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="9d968-112">Updates to any user-defined data are allowed.</span></span>  
  
-   <span data-ttu-id="9d968-113">Serão impostas restrições definidas pelo sistema se a instrução INSERT definir **name**, **path_locator**, **parent_path_locator** ou atributos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9d968-113">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="9d968-114">Podem ser feitas atualizações nos dados FILESTREAM da coluna **file_stream** sem afetar nenhuma outra coluna, incluindo os carimbos de data/hora.</span><span class="sxs-lookup"><span data-stu-id="9d968-114">Updates can be made to the FILESTREAM data in the **file_stream** column without affecting any of the other columns, including the timestamps.</span></span>  
  
##  <a name="delete-operations-on-filetables"></a><a name="BasicsDelete"></a> <span data-ttu-id="9d968-115">Operações DELETE em FileTables</span><span class="sxs-lookup"><span data-stu-id="9d968-115">DELETE Operations on FileTables</span></span>  
 <span data-ttu-id="9d968-116">As considerações a seguir se aplicam a operações **DELETE** em FileTables:</span><span class="sxs-lookup"><span data-stu-id="9d968-116">The following considerations apply to **DELETE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="9d968-117">A exclusão de uma linha remove o arquivo ou diretório correspondente do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9d968-117">Deleting a row also removes the corresponding file or directory from the file system.</span></span>  
  
-   <span data-ttu-id="9d968-118">A exclusão de uma linha não funcionará se a linha corresponder a um diretório que contém outros arquivos ou diretórios.</span><span class="sxs-lookup"><span data-stu-id="9d968-118">Deleting a row fails if the row corresponds to a directory that contains other files or directories.</span></span>  
  
##  <a name="constraints-that-are-enforced-for-dml-operations-on-filetables"></a><a name="BasicsConstraints"></a> <span data-ttu-id="9d968-119">Restrições que são impostas para operações DML em FileTables</span><span class="sxs-lookup"><span data-stu-id="9d968-119">Constraints That Are Enforced for DML Operations on FileTables</span></span>  
 <span data-ttu-id="9d968-120">As restrições definidas pelo sistema garante que as ações DML não comprometem a integridade da hierarquia de namespaces de arquivo.</span><span class="sxs-lookup"><span data-stu-id="9d968-120">System-defined constraints ensure that DML actions do not compromise the integrity of the file namespace hierarchy.</span></span> <span data-ttu-id="9d968-121">Estas são as restrições impostas:</span><span class="sxs-lookup"><span data-stu-id="9d968-121">The constraints that are enforced include the following:</span></span>  
  
-   <span data-ttu-id="9d968-122">Quando você define ou altera o **nome** do arquivo ou diretório:</span><span class="sxs-lookup"><span data-stu-id="9d968-122">When you set or change the **name** of the file or directory:</span></span>  
  
    -   <span data-ttu-id="9d968-123">As convenções de nomenclatura de arquivo e diretório do Windows são impostas.</span><span class="sxs-lookup"><span data-stu-id="9d968-123">Windows file and directory naming conventions are enforced.</span></span>  
  
    -   <span data-ttu-id="9d968-124">A exclusividade do nome no diretório pai é imposta.</span><span class="sxs-lookup"><span data-stu-id="9d968-124">The uniqueness of the name in the parent directory is enforced.</span></span>  
  
-   <span data-ttu-id="9d968-125">Quando você define ou altera o local de um arquivo ou diretório definindo ou alterando o **path_locator** ou **parent_path_locator**:</span><span class="sxs-lookup"><span data-stu-id="9d968-125">When you set or change the location of a file or directory by setting or changing the **path_locator** or **parent_path_locator**:</span></span>  
  
    -   <span data-ttu-id="9d968-126">A exclusividade é imposta.</span><span class="sxs-lookup"><span data-stu-id="9d968-126">Uniqueness is enforced.</span></span>  
  
    -   <span data-ttu-id="9d968-127">A consistência da árvore hierárquica de diretórios e arquivos é imposta, incluindo a consistência dos valores **path_locator** e **parent_path_locator** .</span><span class="sxs-lookup"><span data-stu-id="9d968-127">The consistency of the hierarchical tree of directories and files is enforced, including the consistency of **path_locator** and **parent_path_locator** values.</span></span>  
  
-   <span data-ttu-id="9d968-128">O valor de **is_directory** não pode ser definido como true quando uma coluna **file_stream** não é nula.</span><span class="sxs-lookup"><span data-stu-id="9d968-128">The value of **is_directory** cannot be set to true when the **file_stream** column is not null.</span></span> <span data-ttu-id="9d968-129">Os dados na coluna **file_stream** indicam que a linha representa um arquivo, e não um diretório.</span><span class="sxs-lookup"><span data-stu-id="9d968-129">Data in the **file_stream** column indicates that the row represents a file and not a directory.</span></span>  
  
-   <span data-ttu-id="9d968-130">As colunas de atributo de arquivo não podem ser nulas.</span><span class="sxs-lookup"><span data-stu-id="9d968-130">File attribute columns cannot be null.</span></span> <span data-ttu-id="9d968-131">As restrições NOT NULL são impostas com valores padrão.</span><span class="sxs-lookup"><span data-stu-id="9d968-131">NOT NULL constraints are enforced with default values.</span></span>  
  
-   <span data-ttu-id="9d968-132">O valor de **last_access_time** não pode ser anterior a **last_write_time** e **creation_time**.</span><span class="sxs-lookup"><span data-stu-id="9d968-132">The value of **last_access_time** cannot be earlier than **last_write_time** and **creation_time**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d968-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9d968-133">See Also</span></span>  
 <span data-ttu-id="9d968-134">[Carregar arquivos em FileTables](load-files-into-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="9d968-134">[Load Files into FileTables](load-files-into-filetables.md) </span></span>  
 <span data-ttu-id="9d968-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="9d968-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span></span>  
 <span data-ttu-id="9d968-136">[Acessar FileTables com APIs de entrada e saída de arquivo](access-filetables-with-file-input-output-apis.md) </span><span class="sxs-lookup"><span data-stu-id="9d968-136">[Access FileTables with File Input-Output APIs](access-filetables-with-file-input-output-apis.md) </span></span>  
 [<span data-ttu-id="9d968-137">DDL, funções, procedimentos armazenados e exibições de FileTable</span><span class="sxs-lookup"><span data-stu-id="9d968-137">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
