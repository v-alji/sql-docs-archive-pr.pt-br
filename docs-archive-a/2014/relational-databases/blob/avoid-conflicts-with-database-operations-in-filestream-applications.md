---
title: Evitar conflitos com operações de banco de dados em aplicativos de FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Win32 and Transact-SQL Conflicts
ms.assetid: 8b1ee196-69af-4f9b-9bf5-63d8ac2bc39b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0ac7e681766396d3a3b4412d91a968b4cdc653c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581976"
---
# <a name="avoid-conflicts-with-database-operations-in-filestream-applications"></a><span data-ttu-id="94eee-102">Evitar conflitos com operações de banco de dados em aplicativos de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="94eee-102">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>
  <span data-ttu-id="94eee-103">Os aplicativos que usam SqlOpenFilestream() para abrir identificadores de arquivo do Win32 para ler ou gravar dados BLOB FILESTREAM podem apresentar erros de conflito com instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] gerenciadas em uma transação em comum.</span><span class="sxs-lookup"><span data-stu-id="94eee-103">Applications that use SqlOpenFilestream() to open Win32 file handles for reading or writing FILESTREAM BLOB data can encounter conflict errors with [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are managed in a common transaction.</span></span> <span data-ttu-id="94eee-104">Isso inclui consultas [!INCLUDE[tsql](../../includes/tsql-md.md)] ou MARS cuja execução demora muito tempo para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="94eee-104">This includes [!INCLUDE[tsql](../../includes/tsql-md.md)] or MARS queries that take a long time to finish execution.</span></span> <span data-ttu-id="94eee-105">Os aplicativos devem ser criados cautelosamente para evitar esses tipos de conflitos.</span><span class="sxs-lookup"><span data-stu-id="94eee-105">Applications must be carefully designed to help avoid these types of conflicts.</span></span>  
  
 <span data-ttu-id="94eee-106">Quando o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ou os aplicativos tentam abrir FILESTREAM BLOBs, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] verifica o contexto de transação associado.</span><span class="sxs-lookup"><span data-stu-id="94eee-106">When [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or applications try to open FILESTREAM BLOBs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] checks the associated transaction context.</span></span> <span data-ttu-id="94eee-107">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] permite ou nega as solicitações, dependendo se a operação em aberto funciona com instruções DDL e DML, transações de recuperação de dados ou de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="94eee-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] allows or denies the request based on whether the open operation is working with DDL statements, DML statements, retrieving data, or managing transactions.</span></span> <span data-ttu-id="94eee-108">A tabela a seguir mostra como o [!INCLUDE[ssDE](../../includes/ssde-md.md)] determina se uma instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] será permitida ou negada com base no tipo de arquivos abertos na transação.</span><span class="sxs-lookup"><span data-stu-id="94eee-108">The following table shows how the [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines whether a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will be allowed or denied based on the type of files that are open in the transaction.</span></span>  
  
|<span data-ttu-id="94eee-109">instruções Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="94eee-109">Transact-SQL statements</span></span>|<span data-ttu-id="94eee-110">Abertas para leitura</span><span class="sxs-lookup"><span data-stu-id="94eee-110">Opened for read</span></span>|<span data-ttu-id="94eee-111">Abertas para gravação</span><span class="sxs-lookup"><span data-stu-id="94eee-111">Opened for write</span></span>|  
|------------------------------|---------------------|----------------------|  
|<span data-ttu-id="94eee-112">Instruções de DDL que funcionam com metadados de banco de dados, como CREATE TABLE, CREATE INDEX, DROP TABLE e ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="94eee-112">DDL statements that work with database metadata, such as CREATE TABLE, CREATE INDEX, DROP TABLE, and ALTER TABLE.</span></span>|<span data-ttu-id="94eee-113">Permitido</span><span class="sxs-lookup"><span data-stu-id="94eee-113">Allowed</span></span>|<span data-ttu-id="94eee-114">São bloqueadas e falham devido ao tempo limite esgotado.</span><span class="sxs-lookup"><span data-stu-id="94eee-114">Are blocked and fail with a time-out.</span></span>|  
|<span data-ttu-id="94eee-115">Instruções DML que funcionam com os dados armazenados no banco de dados, como UPDATE, DELETE e INSERT.</span><span class="sxs-lookup"><span data-stu-id="94eee-115">DML statements that work with the data that is stored in the database, such as UPDATE, DELETE, and INSERT.</span></span>|<span data-ttu-id="94eee-116">Permitido</span><span class="sxs-lookup"><span data-stu-id="94eee-116">Allowed</span></span>|<span data-ttu-id="94eee-117">Negadas</span><span class="sxs-lookup"><span data-stu-id="94eee-117">Denied</span></span>|  
|<span data-ttu-id="94eee-118">SELECT</span><span class="sxs-lookup"><span data-stu-id="94eee-118">SELECT</span></span>|<span data-ttu-id="94eee-119">Permitido</span><span class="sxs-lookup"><span data-stu-id="94eee-119">Allowed</span></span>|<span data-ttu-id="94eee-120">Permitido</span><span class="sxs-lookup"><span data-stu-id="94eee-120">Allowed</span></span>|  
|<span data-ttu-id="94eee-121">COMMIT TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="94eee-121">COMMIT TRANSACTION</span></span>|<span data-ttu-id="94eee-122">Negadas\*</span><span class="sxs-lookup"><span data-stu-id="94eee-122">Denied\*</span></span>|<span data-ttu-id="94eee-123">Negadas\*.</span><span class="sxs-lookup"><span data-stu-id="94eee-123">Denied\*.</span></span>|  
|<span data-ttu-id="94eee-124">SAVE TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="94eee-124">SAVE TRANSACTION</span></span>|<span data-ttu-id="94eee-125">Negadas\*</span><span class="sxs-lookup"><span data-stu-id="94eee-125">Denied\*</span></span>|<span data-ttu-id="94eee-126">Negadas\*</span><span class="sxs-lookup"><span data-stu-id="94eee-126">Denied\*</span></span>|  
|<span data-ttu-id="94eee-127">ROLLBACK</span><span class="sxs-lookup"><span data-stu-id="94eee-127">ROLLBACK</span></span>|<span data-ttu-id="94eee-128">Permitidas\*</span><span class="sxs-lookup"><span data-stu-id="94eee-128">Allowed\*</span></span>|<span data-ttu-id="94eee-129">Permitidas\*</span><span class="sxs-lookup"><span data-stu-id="94eee-129">Allowed\*</span></span>|  
  
 <span data-ttu-id="94eee-130">\* A transação é cancelada e os identificadores em aberto do contexto da transação são invalidados.</span><span class="sxs-lookup"><span data-stu-id="94eee-130">\* The transaction is canceled, and open handles for the transaction context are invalidated.</span></span> <span data-ttu-id="94eee-131">O aplicativo deve fechar todos os identificadores abertos.</span><span class="sxs-lookup"><span data-stu-id="94eee-131">The application must close all open handles.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="94eee-132">Exemplos</span><span class="sxs-lookup"><span data-stu-id="94eee-132">Examples</span></span>  
 <span data-ttu-id="94eee-133">Os exemplos a seguir mostram como as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] e o acesso de FILESTREAM do Win32 podem causar conflitos.</span><span class="sxs-lookup"><span data-stu-id="94eee-133">The following examples show how [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and FILESTREAM Win32 access can cause conflicts.</span></span>  
  
### <a name="a-opening-a-filestream-blob-for-write-access"></a><span data-ttu-id="94eee-134">a.</span><span class="sxs-lookup"><span data-stu-id="94eee-134">A.</span></span> <span data-ttu-id="94eee-135">Abrindo um BLOB FILESTREAM para acesso de gravação</span><span class="sxs-lookup"><span data-stu-id="94eee-135">Opening a FILESTREAM BLOB for write access</span></span>  
 <span data-ttu-id="94eee-136">O exemplo a seguir mostra o efeito de abrir um arquivo para acesso apenas de gravação.</span><span class="sxs-lookup"><span data-stu-id="94eee-136">The following example shows the effect of opening a file for write access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//Write some date to the FILESTREAM BLOB.  
WriteFile(dstHandle, updateData, ...);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed. The FILESTREAM BLOB is  
//returned without the modifications that are made by  
//WriteFile(dstHandle, updateData, ...).  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed. The FILESTREAM BLOB  
//is returned with the updateData applied.  
```  
  
### <a name="b-opening-a-filestream-blob-for-read-access"></a><span data-ttu-id="94eee-137">B.</span><span class="sxs-lookup"><span data-stu-id="94eee-137">B.</span></span> <span data-ttu-id="94eee-138">Abrindo um BLOB FILESTREAM para acesso de leitura</span><span class="sxs-lookup"><span data-stu-id="94eee-138">Opening a FILESTREAM BLOB for read access</span></span>  
 <span data-ttu-id="94eee-139">O exemplo a seguir mostra o efeito de abrir um arquivo para acesso apenas de leitura.</span><span class="sxs-lookup"><span data-stu-id="94eee-139">The following example shows the effect of opening a file for read access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed. Any changes that are  
//made to the FILESTREAM BLOB will not be returned until  
//the dstHandle is closed.  
//SELECT statements will be allowed.  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="c-opening-and-closing-multiple-filestream-blob-files"></a><span data-ttu-id="94eee-140">C.</span><span class="sxs-lookup"><span data-stu-id="94eee-140">C.</span></span> <span data-ttu-id="94eee-141">Abrindo e fechando vários arquivos de BLOB FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="94eee-141">Opening and closing multiple FILESTREAM BLOB files</span></span>  
 <span data-ttu-id="94eee-142">Se vários arquivos estiverem abertos, será usada a regra mais restritiva.</span><span class="sxs-lookup"><span data-stu-id="94eee-142">If multiple files are open, the most restrictive rule is used.</span></span> <span data-ttu-id="94eee-143">O exemplo a seguir abre dois arquivos.</span><span class="sxs-lookup"><span data-stu-id="94eee-143">The following example opens two files.</span></span> <span data-ttu-id="94eee-144">O primeiro é aberto para leitura e o segundo, para gravação.</span><span class="sxs-lookup"><span data-stu-id="94eee-144">The first file is opened for read and the second for write.</span></span> <span data-ttu-id="94eee-145">As instruções DML serão negadas até que o segundo arquivo seja aberto.</span><span class="sxs-lookup"><span data-stu-id="94eee-145">DML statements will be denied until the second file is opened.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
  
dstHandle1 =  OpenSqlFilestream(dstFilePath1, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
//Close the read handle. The write handle is still open.  
CloseHandle(dstHandle);  
//DML statements are still denied because the write handle is open.  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
CloseHandle(dstHandle1);  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="d-failing-to-close-a-cursor"></a><span data-ttu-id="94eee-146">D.</span><span class="sxs-lookup"><span data-stu-id="94eee-146">D.</span></span> <span data-ttu-id="94eee-147">Falha ao fechar um cursor</span><span class="sxs-lookup"><span data-stu-id="94eee-147">Failing to close a cursor</span></span>  
 <span data-ttu-id="94eee-148">O exemplo a seguir mostra como um cursor de instrução que não está fechado pode impedir `OpenSqlFilestream()` de abrir o BLOB para acesso de gravação.</span><span class="sxs-lookup"><span data-stu-id="94eee-148">The following example shows how a statement cursor that is not closed can prevent `OpenSqlFilestream()` from opening the BLOB for write access.</span></span>  
  
```  
TCHAR *sqlDBQuery =  
TEXT("SELECT GET_FILESTREAM_TRANSACTION_CONTEXT(),")  
TEXT("Chart.PathName() FROM Archive.dbo.Records");  
  
//Execute a long-running Transact-SQL statement. Do not allow  
//the statement to complete before trying to  
//open the file.  
  
SQLExecDirect(hstmt, sqlDBQuery, SQL_NTS);  
  
//Before you call OpenSqlFilestream() any open files  
//that the Cursor the Transact-SQL statement is using  
// must be closed. In this example,  
//SQLCloseCursor(hstmt) is not called so that  
//the transaction will indicate that there is a file  
//open for reading. This will cause the call to  
//OpenSqlFilestream() to fail because the file is  
//still open.  
  
HANDLE srcHandle =  OpenSqlFilestream(srcFilePath,  
     Write, 0,  transactionToken,  cbTransactionToken,  0);  
  
//srcHandle will == INVALID_HANDLE_VALUE because the  
//cursor is still open.  
```  
  
## <a name="see-also"></a><span data-ttu-id="94eee-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94eee-149">See Also</span></span>  
 <span data-ttu-id="94eee-150">[Acessar dados do FILESTREAM com OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span><span class="sxs-lookup"><span data-stu-id="94eee-150">[Access FILESTREAM Data with OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span></span>  
 [<span data-ttu-id="94eee-151">Usando MARS &#40;Multiple Active Result Sets&#41;</span><span class="sxs-lookup"><span data-stu-id="94eee-151">Using Multiple Active Result Sets &#40;MARS&#41;</span></span>](../native-client/features/using-multiple-active-result-sets-mars.md)  
  
  
