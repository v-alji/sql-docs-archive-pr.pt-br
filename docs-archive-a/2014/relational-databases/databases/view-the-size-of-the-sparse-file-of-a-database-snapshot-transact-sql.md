---
title: Exibir o tamanho do arquivo esparso de um instantâneo de banco de dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- snapshots [SQL Server database snapshots], sparse files
- space [SQL Server], sparse files
- sparse files [SQL Server]
- size [SQL Server], sparse files
- maximum sparse file size
- database snapshots [SQL Server], sparse files
- space [SQL Server], database snapshots
ms.assetid: 1867c5f8-d57c-46d3-933d-3642ab0a8e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: 424399b9915c8e7e26e1076fd2e553aafe06fcf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682271"
---
# <a name="view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql"></a><span data-ttu-id="e43ed-102">Exibir o tamanho do arquivo esparso de um instantâneo de banco de dados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e43ed-102">View the Size of the Sparse File of a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="e43ed-103">Este tópico descreve como usar o [!INCLUDE[tsql](../../includes/tsql-md.md)] para verificar se um arquivo de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é um arquivo esparso e descobrir seu tamanho real e máximo.</span><span class="sxs-lookup"><span data-stu-id="e43ed-103">This topic describes how to use [!INCLUDE[tsql](../../includes/tsql-md.md)] to verify that a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database file is a sparse file and to find out its actual and maximum sizes.</span></span> <span data-ttu-id="e43ed-104">Arquivos esparsos, que são um recurso do sistema de arquivos NTFS, são usados por instantâneos do banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e43ed-104">Sparse files, which are a feature of the NTFS file system, are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshots.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e43ed-105">Durante a criação do instantâneo do banco de dados, arquivos esparsos são criados usando os nomes de arquivo na instrução CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="e43ed-105">During database snapshot creation, sparse files are created by using the file names in the CREATE DATABASE statement.</span></span> <span data-ttu-id="e43ed-106">Esses nomes de arquivo são armazenados em **sys.master_files** na coluna **physical_name** .</span><span class="sxs-lookup"><span data-stu-id="e43ed-106">These file names are stored in **sys.master_files** in the **physical_name** column.</span></span> <span data-ttu-id="e43ed-107">Em **sys.database_files** (quer seja no banco de dados de origem ou em um instantâneo), a coluna **physical_name** sempre contém os nomes dos arquivos de banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="e43ed-107">In **sys.database_files** (whether in the source database or in a snapshot), the **physical_name** column always contains the names of the source database files.</span></span>  
  
## <a name="verify-that-a-database-file-is-a-sparse-file"></a><span data-ttu-id="e43ed-108">Verificar se um arquivo de banco de dados é um arquivo esparso</span><span class="sxs-lookup"><span data-stu-id="e43ed-108">Verify that a Database File is a Sparse File</span></span>  
  
1.  <span data-ttu-id="e43ed-109">Na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e43ed-109">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="e43ed-110">Selecione a coluna **is_sparse** de **sys.database_files** no instantâneo do banco de dados ou de **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="e43ed-110">Select the **is_sparse** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="e43ed-111">O valor indica se o arquivo é um arquivo esparso, como segue:</span><span class="sxs-lookup"><span data-stu-id="e43ed-111">The value indicates whether the file is a sparse file, as follows:</span></span>  
  
     <span data-ttu-id="e43ed-112">1 = O arquivo é um arquivo esparso.</span><span class="sxs-lookup"><span data-stu-id="e43ed-112">1 = File is a sparse file.</span></span>  
  
     <span data-ttu-id="e43ed-113">0 = O arquivo não é um arquivo esparso.</span><span class="sxs-lookup"><span data-stu-id="e43ed-113">0 = File is not a sparse file.</span></span>  
  
## <a name="find-out-the-actual-size-of-a-sparse-file"></a><span data-ttu-id="e43ed-114">Descobrir o tamanho real de um arquivo esparso</span><span class="sxs-lookup"><span data-stu-id="e43ed-114">Find Out the Actual Size of a Sparse File</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e43ed-115">Arquivos esparsos crescem em incrementos de 64 KB (quilobyte); portanto, o tamanho de um arquivo esparso no disco sempre é um múltiplo de 64 KB.</span><span class="sxs-lookup"><span data-stu-id="e43ed-115">Sparse files grow in 64-kilobyte (KB) increments; thus, the size of a sparse file on disk is always a multiple of 64 KB.</span></span>  
  
 <span data-ttu-id="e43ed-116">Para exibir o número de bytes que cada arquivo esparso de um instantâneo está usando atualmente no disco, consulte a coluna **size_on_disk_bytes** da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exibição de gerenciamento dinâmico [Sys. dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e43ed-116">To view the number of bytes that each sparse file of a snapshot is currently using on disk, query the **size_on_disk_bytes** column of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][sys.dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) dynamic management view.</span></span>  
  
 <span data-ttu-id="e43ed-117">Para exibir o espaço em disco usado por um arquivo esparso, clique com o botão direito do mouse no Microsoft Windows, clique em **Propriedades**e examine o valor de **Tamanho em disco** .</span><span class="sxs-lookup"><span data-stu-id="e43ed-117">To view the disk space used by a sparse file, right-click the file in Microsoft Windows, click **Properties**, and look at the **Size on disk** value.</span></span>  
  
## <a name="find-out-the-maximum-size-of-a-sparse-file"></a><span data-ttu-id="e43ed-118">Descobrir o tamanho máximo de um arquivo esparso</span><span class="sxs-lookup"><span data-stu-id="e43ed-118">Find Out the Maximum Size of a Sparse File</span></span>  
 <span data-ttu-id="e43ed-119">O tamanho máximo de crescimento de um arquivo esparso é o tamanho do arquivo de banco de dados de origem correspondente, no momento da criação do instantâneo.</span><span class="sxs-lookup"><span data-stu-id="e43ed-119">The maximum size to which a sparse can grow is the size of the corresponding source database file at the time of the snapshot creation.</span></span> <span data-ttu-id="e43ed-120">Para saber qual é este tamanho, você pode usar uma das alternativas seguintes:</span><span class="sxs-lookup"><span data-stu-id="e43ed-120">To learn this size, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="e43ed-121">Usando o prompt de comando do Windows:</span><span class="sxs-lookup"><span data-stu-id="e43ed-121">Using Windows Command Prompt:</span></span>  
  
    1.  <span data-ttu-id="e43ed-122">Use os comandos **dir** do Windows.</span><span class="sxs-lookup"><span data-stu-id="e43ed-122">Use Windows **dir** commands.</span></span>  
  
    2.  <span data-ttu-id="e43ed-123">Selecione o arquivo esparso, abra a caixa de diálogo **Propriedades** do arquivo no Windows, e consulte o valor **Tamanho** .</span><span class="sxs-lookup"><span data-stu-id="e43ed-123">Select the sparse file, open the file **Properties** dialog box in Windows, and look at the **Size** value.</span></span>  
  
-   <span data-ttu-id="e43ed-124">Na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e43ed-124">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="e43ed-125">Selecione a coluna **size** em **sys.database_files** no instantâneo do banco de dados ou em **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="e43ed-125">Select the **size** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="e43ed-126">O valor da coluna **size** reflete o espaço máximo, em páginas SQL, que o instantâneo pode vir a usar; esse valor é equivalente ao campo **Tamanho** do Windows, a não ser que seja representado em número de páginas SQL no arquivo; o tamanho em bytes é:</span><span class="sxs-lookup"><span data-stu-id="e43ed-126">The value of **size** column reflects the maximum space, in SQL pages, that the snapshot can ever use; this value is equivalent to the Windows **Size** field, except that it is represented in terms of the number of SQL pages in the file; the size in bytes is:</span></span>  
  
     <span data-ttu-id="e43ed-127">( *number_of_pages* \* 8192)</span><span class="sxs-lookup"><span data-stu-id="e43ed-127">( *number_of_pages* \* 8192)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43ed-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e43ed-128">See Also</span></span>  
 <span data-ttu-id="e43ed-129">[Instantâneos de banco de dados &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e43ed-129">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="e43ed-130">[sys.fn_virtualfilestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e43ed-130">[sys.fn_virtualfilestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span></span>  
 <span data-ttu-id="e43ed-131">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e43ed-131">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 [<span data-ttu-id="e43ed-132">sys.master_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e43ed-132">sys.master_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)  
  
  
