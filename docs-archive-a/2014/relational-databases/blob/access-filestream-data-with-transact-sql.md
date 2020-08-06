---
title: Acessar dados FILESTREAM com Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Transact-SQL
ms.assetid: a6bf0ce7-7e5e-4a07-8917-ee526c9d0a05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06d395f1acc3723fc6b45fdfa08efbae354d8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681700"
---
# <a name="access-filestream-data-with-transact-sql"></a><span data-ttu-id="a5d5c-102">Acessar dados FILESTREAM com Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a5d5c-102">Access FILESTREAM Data with Transact-SQL</span></span>
  <span data-ttu-id="a5d5c-103">Este tópico descreve como usar as instruções INSERT, UPDATE e DELETE do [!INCLUDE[tsql](../../includes/tsql-md.md)] para gerenciar dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT, UPDATE, and DELETE statements to manage FILESTREAM data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5d5c-104">Os exemplos citados neste tópico exigem o banco de dados e a tabela habilitados para FILESTREAM criados em [Criar um banco de dados habilitado para FILESTREAM](create-a-filestream-enabled-database.md) e [Criar uma tabela para armazenar dados de FILESTREAM](create-a-table-for-storing-filestream-data.md).</span><span class="sxs-lookup"><span data-stu-id="a5d5c-104">The examples in this topic require the FILESTREAM-enabled database and table that are created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md) and [Create a Table for Storing FILESTREAM Data](create-a-table-for-storing-filestream-data.md).</span></span>  
  
##  <a name="inserting-a-row-that-contains-filestream-data"></a><a name="ins"></a> <span data-ttu-id="a5d5c-105">Inserindo uma linha contendo dados de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="a5d5c-105">Inserting a Row That Contains FILESTREAM Data</span></span>  
 <span data-ttu-id="a5d5c-106">Para adicionar uma linha a uma tabela que suporte dados de FILESTREAM, use a instrução INSERT de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5d5c-106">To add a row to a table that supports FILESTREAM data, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span> <span data-ttu-id="a5d5c-107">Ao inserir dados em uma coluna FILESTREAM, você pode inserir NULL ou um valor `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-107">When you insert data into a FILESTREAM column, you can insert NULL or a `varbinary(max)` value.</span></span>  
  
### <a name="inserting-null"></a><span data-ttu-id="a5d5c-108">Inserindo NULL</span><span class="sxs-lookup"><span data-stu-id="a5d5c-108">Inserting NULL</span></span>  
 <span data-ttu-id="a5d5c-109">O exemplo a seguir mostra como inserir `NULL`.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-109">The following example shows how to insert `NULL`.</span></span> <span data-ttu-id="a5d5c-110">Quando o valor de FILESTREAM for `NULL`, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] não criará um arquivo no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-110">When the FILESTREAM value is `NULL`, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not create a file in the file system.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertNULL](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertnull)]  
  
### <a name="inserting-a-zero-length-record"></a><span data-ttu-id="a5d5c-111">Inserindo um registro de comprimento zero</span><span class="sxs-lookup"><span data-stu-id="a5d5c-111">Inserting a Zero-Length Record</span></span>  
 <span data-ttu-id="a5d5c-112">O exemplo a seguir mostra como usar `INSERT` para criar um registro com comprimento zero,</span><span class="sxs-lookup"><span data-stu-id="a5d5c-112">The following example shows how to use `INSERT` to create a zero-length record.</span></span> <span data-ttu-id="a5d5c-113">o que é útil quando você quer obter um identificador de arquivo, mas manipulará o arquivo usando APIs de Win32.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-113">This is useful for when you want to obtain a file handle, but will be manipulating the file by using Win32 APIs.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertZero](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertzero)]  
  
### <a name="creating-a-data-file"></a><span data-ttu-id="a5d5c-114">Criando um arquivo de dados</span><span class="sxs-lookup"><span data-stu-id="a5d5c-114">Creating a Data File</span></span>  
 <span data-ttu-id="a5d5c-115">O exemplo a seguir mostra como usar o objeto `INSERT` para criar um arquivo que contenha dados.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-115">The following example shows how to use `INSERT` to create a file that contains data.</span></span> <span data-ttu-id="a5d5c-116">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] converte a cadeia de caracteres `Seismic Data` para um valor `varbinary(max)` .</span><span class="sxs-lookup"><span data-stu-id="a5d5c-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] converts the string `Seismic Data` to a `varbinary(max)` value.</span></span> <span data-ttu-id="a5d5c-117">O FILESTREAM criará o arquivo Windows se ele ainda não existir. Depois, os dados serão adicionados ao arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-117">FILESTREAM creates the Windows file if it does not already exist.The data is then added to the data file.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertdata)]  
  
 <span data-ttu-id="a5d5c-118">Quando você seleciona todos os dados do `Archive`.`dbo.Records`</span><span class="sxs-lookup"><span data-stu-id="a5d5c-118">When you select all data from the `Archive`.`dbo.Records`</span></span> <span data-ttu-id="a5d5c-119">Quando você seleciona todos os dados da tabela, os resultados são semelhantes aos exibidos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-119">table, the results are similar to the results that are shown in the following table.</span></span> <span data-ttu-id="a5d5c-120">Porém, a coluna `Id` conterá GUIDs diferente.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-120">However, the `Id` column will contain different GUIDs.</span></span>  
  
|<span data-ttu-id="a5d5c-121">ID</span><span class="sxs-lookup"><span data-stu-id="a5d5c-121">Id</span></span>|<span data-ttu-id="a5d5c-122">SerialNumber</span><span class="sxs-lookup"><span data-stu-id="a5d5c-122">SerialNumber</span></span>|<span data-ttu-id="a5d5c-123">Retomar</span><span class="sxs-lookup"><span data-stu-id="a5d5c-123">Resume</span></span>|  
|--------|------------------|------------|  
|`C871B90F-D25E-47B3-A560-7CC0CA405DAC`|`1`|`NULL`|  
|`F8F5C314-0559-4927-8FA9-1535EE0BDF50`|`2`|`0x`|  
|`7F680840-B7A4-45D4-8CD5-527C44D35B3F`|`3`|`0x536569736D69632044617461`|  
  
##  <a name="updating-filestream-data"></a><a name="upd"></a> <span data-ttu-id="a5d5c-124">Atualizando dados de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="a5d5c-124">Updating FILESTREAM Data</span></span>  
 <span data-ttu-id="a5d5c-125">Você pode usar o [!INCLUDE[tsql](../../includes/tsql-md.md)] para atualizar os dados no arquivo do sistema de arquivos; não é recomendável fazer isso quando houver grandes quantidades de fluxo de dados em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-125">You can use [!INCLUDE[tsql](../../includes/tsql-md.md)] to update the data in the file system file; although, you might not want to do this when you have to stream large amounts of data to a file.</span></span>  
  
 <span data-ttu-id="a5d5c-126">O exemplo a seguir substitui qualquer texto no registro do arquivo pelo texto `Xray 1`.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-126">The following example replaces any text in the file record with the text `Xray 1`.</span></span>  
  
 [!code-sql[FILESTREAM#FS_UpdateData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_updatedata)]  
  
##  <a name="deleting-filestream-data"></a><a name="del"></a> <span data-ttu-id="a5d5c-127">Excluindo dados de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="a5d5c-127">Deleting FILESTREAM Data</span></span>  
 <span data-ttu-id="a5d5c-128">Ao excluir uma linha que contém um campo de FILESTREAM, você também exclui seus arquivos subjacentes do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-128">When you delete a row that contains a FILESTREAM field, you also delete its underlying file system files.</span></span> <span data-ttu-id="a5d5c-129">O único modo de excluir uma linha, e portanto o arquivo, é usar a instrução DELETE do [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5d5c-129">The only way to delete a row, and therefore the file, is to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span>  
  
 <span data-ttu-id="a5d5c-130">O exemplo a seguir mostra como excluir uma linha e seus arquivos associados do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-130">The following example shows how to delete a row and its associated file system files.</span></span>  
  
 [!code-sql[FILESTREAM#FS_DeleteData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_deletedata)]  
  
 <span data-ttu-id="a5d5c-131">Quando você selecionar todos os dados da tabela `dbo.Archive` , a linha será excluída.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-131">When you select all data from the `dbo.Archive` table, the row is gone.</span></span> <span data-ttu-id="a5d5c-132">Não é mais possível usar o arquivo associado.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-132">You can no longer use the associated file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5d5c-133">Os arquivos subjacentes são removidos pelo coletor de lixo do FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a5d5c-133">The underlying files are removed by the FILESTREAM garbage collector.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d5c-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a5d5c-134">See Also</span></span>  
 <span data-ttu-id="a5d5c-135">[Habilitar e configurar FILESTREAM](enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="a5d5c-135">[Enable and Configure FILESTREAM](enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="a5d5c-136">Evitar conflitos com operações de banco de dados em aplicativos de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="a5d5c-136">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>](avoid-conflicts-with-database-operations-in-filestream-applications.md)  
  
  
