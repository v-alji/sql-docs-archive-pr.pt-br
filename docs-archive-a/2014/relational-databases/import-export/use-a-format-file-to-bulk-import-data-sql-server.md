---
title: Usar um arquivo de formato para importação em massa de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], format files
- format files [SQL Server], importing data using
ms.assetid: 2956df78-833f-45fa-8a10-41d6522562b9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6d9779209b3ffb317658243c168d74740f6731b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584144"
---
# <a name="use-a-format-file-to-bulk-import-data-sql-server"></a><span data-ttu-id="b9b20-102">Usar um arquivo de formato para importação em massa de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b9b20-102">Use a Format File to Bulk Import Data (SQL Server)</span></span>
  <span data-ttu-id="b9b20-103">Este tópico ilustra o uso de um arquivo de formato operações de importação em massa.</span><span class="sxs-lookup"><span data-stu-id="b9b20-103">This topic illustrates the use of a format file in bulk-import operations.</span></span> <span data-ttu-id="b9b20-104">O arquivo de formato mapeia os campos do arquivo de dados para as colunas da tabela.</span><span class="sxs-lookup"><span data-stu-id="b9b20-104">The format file maps the fields of the data file to the columns of the table.</span></span>  <span data-ttu-id="b9b20-105">Você pode usar um arquivo de formato XML ou não XML para importar dados em massa ao usar um comando **bcp** ou um BULK INSERT ou INSERT... SELECIONAR \* de OPENROWSET (BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] linha.</span><span class="sxs-lookup"><span data-stu-id="b9b20-105">You can use a non-XML or XML format file to bulk import data when using a **bcp** command or a BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b9b20-106">Para trabalhar com um arquivo de dados de caractere Unicode, todos os campos de entrada devem ser cadeias de caracteres de texto Unicode (isto é, sejam cadeias de caracteres Unicode de tamanho fixo ou terminadas por caractere).</span><span class="sxs-lookup"><span data-stu-id="b9b20-106">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9b20-107">Se você não estiver familiarizado com arquivos de formato, consulte [arquivos de formato não XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) e [arquivos de formato XML &#40;SQL Server ](xml-format-files-sql-server.md)&#41;.</span><span class="sxs-lookup"><span data-stu-id="b9b20-107">If you are unfamiliar with format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) and [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="format-file-options-for-bulk-import-commands"></a><span data-ttu-id="b9b20-108">Opções arquivo de formato de dados para comandos de importação em massa</span><span class="sxs-lookup"><span data-stu-id="b9b20-108">Format File Options for Bulk-Import Commands</span></span>  
 <span data-ttu-id="b9b20-109">A tabela a seguir resume a opção de arquivo de formato para cada um dos comandos de importação em massa.</span><span class="sxs-lookup"><span data-stu-id="b9b20-109">The following table summarizes the format-file option of for each of the bulk-import commands.</span></span>  
  
|<span data-ttu-id="b9b20-110">Comando de carregamento em massa</span><span class="sxs-lookup"><span data-stu-id="b9b20-110">Bulk-load Command</span></span>|<span data-ttu-id="b9b20-111">Usando a opção de Arquivo de Formato</span><span class="sxs-lookup"><span data-stu-id="b9b20-111">Using the Format-File Option</span></span>|  
|------------------------|-----------------------------------|  
|<span data-ttu-id="b9b20-112">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="b9b20-112">BULK INSERT</span></span>|<span data-ttu-id="b9b20-113">FORMATFILE = '*format_file_path*'</span><span class="sxs-lookup"><span data-stu-id="b9b20-113">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="b9b20-114">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="b9b20-114">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="b9b20-115">FORMATFILE = '*format_file_path*'</span><span class="sxs-lookup"><span data-stu-id="b9b20-115">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="b9b20-116">**bcp** ... **em**</span><span class="sxs-lookup"><span data-stu-id="b9b20-116">**bcp** ... **in**</span></span>|<span data-ttu-id="b9b20-117">**-f** *format_file*</span><span class="sxs-lookup"><span data-stu-id="b9b20-117">**-f** *format_file*</span></span>|  
  
 <span data-ttu-id="b9b20-118">Para obter mais informações, consulte [Utilitário bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) ou [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b9b20-118">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9b20-119">Para exportar ou importar dados SQLXML em massa, use um dos tipos de dados a seguir em seu arquivo de formato: SQLCHAR ou SQLVARYCHAR (os dados são enviados na página de código do cliente ou na página de código implícita pela ordenação), SQLNCHAR ou SQLNVARCHAR (os dados são enviados como Unicode), ou SQLBINARY ou SQLVARYBIN (os dados são enviados sem nenhuma conversão).</span><span class="sxs-lookup"><span data-stu-id="b9b20-119">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b9b20-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b9b20-120">Examples</span></span>  
 <span data-ttu-id="b9b20-121">Os exemplos nesta seção ilustram como usar arquivos de formato para importar dados em massa usando o comando **bcp** e o BULK INSERT e inserir... Instruções SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="b9b20-121">The examples in this section illustrate how to use format files to bulk-import data by using the **bcp** command and the BULK INSERT, and INSERT ... SELECT \* FROM OPENROWSET(BULK...) statements.</span></span> <span data-ttu-id="b9b20-122">Antes de poder executar um dos exemplos de importação em massa, você precisa criar uma amostra de tabela, arquivo de dados e arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="b9b20-122">Before you can run one of the bulk-import examples, you need to create a sample table, data file, and a format file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="b9b20-123">Tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="b9b20-123">Sample Table</span></span>  
 <span data-ttu-id="b9b20-124">Os exemplos requerem que uma tabela denominada **myTestFormatFiles** seja criada no banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] no esquema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="b9b20-124">The examples require that a table named **myTestFormatFiles** table be created in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="b9b20-125">Para criar esta tabela, no Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute:</span><span class="sxs-lookup"><span data-stu-id="b9b20-125">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestFormatFiles (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50),  
   Col4 nvarchar(50)  
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="b9b20-126">Arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="b9b20-126">Sample Data File</span></span>  
 <span data-ttu-id="b9b20-127">Os exemplos usam um arquivo de dados de amostra, `myTestFormatFiles-c.Dat`que contém os seguintes registros.</span><span class="sxs-lookup"><span data-stu-id="b9b20-127">The examples use a sample data file, `myTestFormatFiles-c.Dat`, which contains the following records.</span></span> <span data-ttu-id="b9b20-128">Para criar esse arquivo de dados, no prompt de comando do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="b9b20-128">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
10,Field2,Field3,Field4  
15,Field2,Field3,Field4  
46,Field2,Field3,Field4  
58,Field2,Field3,Field4  
```  
  
### <a name="sample-format-files"></a><span data-ttu-id="b9b20-129">Arquivo de formato de exemplo</span><span class="sxs-lookup"><span data-stu-id="b9b20-129">Sample Format Files</span></span>  
 <span data-ttu-id="b9b20-130">Alguns dos exemplos nessa seção usam um arquivo de formato XML, `myTestFormatFiles-f-x-c.Xml`e, outros exemplos usam um arquivo de formato não XML.</span><span class="sxs-lookup"><span data-stu-id="b9b20-130">Some of the examples in this section use an XML format file, `myTestFormatFiles-f-x-c.Xml`, and other examples use a non-XML format file.</span></span> <span data-ttu-id="b9b20-131">Ambos os arquivos de formato usam formatos de dados de caracteres e um terminador de campo não padrão (,).</span><span class="sxs-lookup"><span data-stu-id="b9b20-131">Both format files use character data formats and a non-default field terminator (,).</span></span>  
  
#### <a name="the-sample-non-xml-format-file"></a><span data-ttu-id="b9b20-132">O exemplo de arquivo de formato não XML</span><span class="sxs-lookup"><span data-stu-id="b9b20-132">The Sample Non-XML Format File</span></span>  
 <span data-ttu-id="b9b20-133">O exemplo a seguir usa **bcp** para gerar um arquivo de formato XML a partir da tabela `myTestFormatFiles` .</span><span class="sxs-lookup"><span data-stu-id="b9b20-133">The following example uses **bcp** to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="b9b20-134">O arquivo `myTestFormatFiles.Fmt` contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="b9b20-134">The `myTestFormatFiles.Fmt` file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     Col1         ""  
2       SQLCHAR       0       100     ","      2     Col2         SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      3     Col3         SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   4     Col4         SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="b9b20-135">Para usar **bcp** com a opção **format** para criar esse arquivo de formato, no prompt de comando do Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="b9b20-135">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -f myTestFormatFiles.Fmt -T  
  
```  
  
 <span data-ttu-id="b9b20-136">Para obter mais informações sobre como criar um arquivo de formato, consulte [Criar um arquivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b9b20-136">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
#### <a name="the-sample-xml-format-file"></a><span data-ttu-id="b9b20-137">O arquivo de formato XML de exemplo</span><span class="sxs-lookup"><span data-stu-id="b9b20-137">The Sample XML Format File</span></span>  
 <span data-ttu-id="b9b20-138">O exemplo a seguir usa **bcp** para criar a geração de um arquivo de formato XML a partir da tabela `myTestFormatFiles` .</span><span class="sxs-lookup"><span data-stu-id="b9b20-138">The following example uses **bcp** to create to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="b9b20-139">O arquivo `myTestFormatFiles.Xml` contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="b9b20-139">The `myTestFormatFiles.Xml` file contains the following information:</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>  
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Col4" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="b9b20-140">Para usar **bcp** com a opção **format** para criar esse arquivo de formato, no prompt de comando do Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="b9b20-140">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -x -f myTestFormatFiles.Xml -T  
```  
  
### <a name="using-bcp"></a><span data-ttu-id="b9b20-141">Usando bcp</span><span class="sxs-lookup"><span data-stu-id="b9b20-141">Using bcp</span></span>  
 <span data-ttu-id="b9b20-142">O exemplo a seguir usa **bcp** para importar em massa dados do arquivo de dados `myTestFormatFiles-c.Dat` na tabela `HumanResources.myTestFormatFiles` no banco de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="b9b20-142">The following example uses **bcp** to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the  sample database.</span></span> <span data-ttu-id="b9b20-143">Este exemplo usa um arquivo de formato XML, `MyTestFormatFiles.Xml`.</span><span class="sxs-lookup"><span data-stu-id="b9b20-143">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="b9b20-144">O exemplo exclui as linhas existentes na tabela antes de importar o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="b9b20-144">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="b9b20-145">No prompt de comando do Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="b9b20-145">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestFormatFiles in C:\myTestFormatFiles-c.Dat -f C:\myTestFormatFiles.Xml -T  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b9b20-146">Para obter mais informações sobre esse comando, consulte [Utilitário bcp](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b9b20-146">For more information about this command, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
### <a name="using-bulk-insert"></a><span data-ttu-id="b9b20-147">Usando BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="b9b20-147">Using BULK INSERT</span></span>  
 <span data-ttu-id="b9b20-148">O exemplo a seguir usa BULK INSERT para importar em massa dados do arquivo de dados `myTestFormatFiles-c.Dat` na tabela `HumanResources.myTestFormatFiles` no banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9b20-148">The following example uses BULK INSERT to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="b9b20-149">Este exemplo usa um arquivo de formato não XML, `MyTestFormatFiles.Fmt`.</span><span class="sxs-lookup"><span data-stu-id="b9b20-149">This example uses a non-XML format file, `MyTestFormatFiles.Fmt`.</span></span> <span data-ttu-id="b9b20-150">O exemplo exclui as linhas existentes na tabela antes de importar o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="b9b20-150">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="b9b20-151">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute:</span><span class="sxs-lookup"><span data-stu-id="b9b20-151">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DELETE myTestFormatFiles;  
GO  
BULK INSERT myTestFormatFiles   
   FROM 'C:\myTestFormatFiles-c.Dat'   
   WITH (FORMATFILE = 'C:\myTestFormatFiles.Fmt');  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b9b20-152">Para obter mais informações sobre esta instrução, consulte [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b9b20-152">For more information about this statement, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="using-the-openrowset-bulk-rowset-provider"></a><span data-ttu-id="b9b20-153">Usando o Provedor de Conjuntos de Linhas em Massa OPENROWSET</span><span class="sxs-lookup"><span data-stu-id="b9b20-153">Using the OPENROWSET Bulk Rowset Provider</span></span>  
 <span data-ttu-id="b9b20-154">O exemplo a seguir usa `INSERT ... SELECT * FROM OPENROWSET(BULK...)`para importar em massa dados do arquivo de dados `myTestFormatFiles-c.Dat` na tabela `HumanResources.myTestFormatFiles` no banco de dados de exemplo `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="b9b20-154">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the `AdventureWorks` sample database.</span></span> <span data-ttu-id="b9b20-155">Este exemplo usa um arquivo de formato XML, `MyTestFormatFiles.Xml`.</span><span class="sxs-lookup"><span data-stu-id="b9b20-155">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="b9b20-156">O exemplo exclui as linhas existentes na tabela antes de importar o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="b9b20-156">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="b9b20-157">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute:</span><span class="sxs-lookup"><span data-stu-id="b9b20-157">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
DELETE myTestFormatFiles;  
GO  
INSERT INTO myTestFormatFiles  
    SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestFormatFiles-c.Dat',  
      FORMATFILE='C:\myTestFormatFiles.Xml'       
      ) as t1 ;  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
 <span data-ttu-id="b9b20-158">Quando você terminar de usar a tabela de amostra, pode descartá-la usando a instrução:</span><span class="sxs-lookup"><span data-stu-id="b9b20-158">When you finish using the sample table, you can drop it using the following statement:</span></span>  
  
```  
DROP TABLE myTestFormatFiles  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b9b20-159">Para obter mais informações sobre a cláusula OPENROWSET BULK, veja [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b9b20-159">For more information about the OPENROWSET BULK clause, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="b9b20-160">Exemplos adicionais</span><span class="sxs-lookup"><span data-stu-id="b9b20-160">Additional Examples</span></span>  
 [<span data-ttu-id="b9b20-161">Criar um arquivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9b20-161">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
 [<span data-ttu-id="b9b20-162">Usar um arquivo de formato para ignorar uma coluna de tabela &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9b20-162">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 [<span data-ttu-id="b9b20-163">Usar um arquivo de formato para ignorar um campo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9b20-163">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
 [<span data-ttu-id="b9b20-164">Usar um arquivo de formato para mapear colunas de uma tabela para campos de arquivo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9b20-164">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="b9b20-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b9b20-165">See Also</span></span>  
 <span data-ttu-id="b9b20-166">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b9b20-166">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="b9b20-167">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b9b20-167">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="b9b20-168">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b9b20-168">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="b9b20-169">[Arquivos de formato não XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b9b20-169">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="b9b20-170">Arquivos de formato XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b9b20-170">XML Format Files &#40;SQL Server&#41;</span></span>](xml-format-files-sql-server.md)  
  
  
