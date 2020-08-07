---
title: Usar um arquivo de formato para ignorar um campo de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], skipping data fields
- skipping data fields when importing
ms.assetid: 6a76517e-983b-47a1-8f02-661b99859a8b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d3f78c3c97c5bbe862867d5f51ff35f57d147df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584143"
---
# <a name="use-a-format-file-to-skip-a-data-field-sql-server"></a><span data-ttu-id="f6052-102">Usar um arquivo de formato para ignorar um campo de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f6052-102">Use a Format File to Skip a Data Field (SQL Server)</span></span>
  <span data-ttu-id="f6052-103">Um arquivo de dados pode conter mais campos do que o número de colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="f6052-103">A data file can contain more fields than the number of columns in the table.</span></span> <span data-ttu-id="f6052-104">Este tópico descreve como modificar arquivos de formato XML e não XML para acomodar um arquivo de dados com mais campos, mapeando as colunas de tabela para os campos de dados correspondentes e ignorando os campos extras.</span><span class="sxs-lookup"><span data-stu-id="f6052-104">This topic describes modifying both non-XML and XML format files to accommodate a data file with more fields by mapping the table columns to the corresponding data fields and ignoring the extra fields.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6052-105">Um arquivo de formato XML ou não XML pode ser usado para importar em massa um arquivo de dados para a tabela usando um comando **bcp** , instrução BULK INSERT ou INSERT... Selecione \* da instrução OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="f6052-105">Either a non-XML or XML format file can be used to bulk import a data file into the table by using a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="f6052-106">Para obter mais informações, veja [Usar um arquivo de formato para importação de dados em massa &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f6052-106">For more information, see [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
## <a name="sample-data-file-and-table"></a><span data-ttu-id="f6052-107">Tabela e arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="f6052-107">Sample Data File and Table</span></span>  
 <span data-ttu-id="f6052-108">Os exemplos de arquivos de formato modificados neste tópico baseiam-se na tabela e no arquivo de dados a seguir.</span><span class="sxs-lookup"><span data-stu-id="f6052-108">The examples of modified format files in this topic are based on the following table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="f6052-109">Tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="f6052-109">Sample Table</span></span>  
 <span data-ttu-id="f6052-110">Os exemplos requerem que uma tabela denominada `myTestSkipField` seja criada no banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] no esquema `dbo` .</span><span class="sxs-lookup"><span data-stu-id="f6052-110">The examples require that a table named `myTestSkipField` be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="f6052-111">Para criar essa tabela, no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Editor de consultas, execute o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="f6052-111">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestSkipField   
   (  
   PersonID smallint,  
   FirstName nvarchar(50) ,  
   LastName nvarchar(50)   
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="f6052-112">Arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="f6052-112">Sample Data File</span></span>  
 <span data-ttu-id="f6052-113">O arquivo de dados `myTestSkipField-c.dat` contém os seguintes registros:</span><span class="sxs-lookup"><span data-stu-id="f6052-113">The data file, `myTestSkipField-c.dat`, contains the following records:</span></span>  
  
```  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
```  
  
 <span data-ttu-id="f6052-114">Para importar em massa dados de `myTestSkipField-c.dat` para a tabela `myTestSkipField` , o arquivo de formato deverá fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f6052-114">To bulk import data from `myTestSkipField-c.dat` into the `myTestSkipField` table, the format file must do the following:</span></span>  
  
-   <span data-ttu-id="f6052-115">Mapear o primeiro campo de dados para a primeira coluna, `PersonID`.</span><span class="sxs-lookup"><span data-stu-id="f6052-115">Map the first data field to the first column, `PersonID`.</span></span>  
  
-   <span data-ttu-id="f6052-116">Ignorar o segundo campo de dados.</span><span class="sxs-lookup"><span data-stu-id="f6052-116">Skip the second data field.</span></span>  
  
-   <span data-ttu-id="f6052-117">Mapear o terceiro campo de dados para a segunda coluna, `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="f6052-117">Map the third data field to the second column, `FirstName`.</span></span>  
  
-   <span data-ttu-id="f6052-118">Mapear o quarto campo de dados para a terceira coluna, `LastName`.</span><span class="sxs-lookup"><span data-stu-id="f6052-118">Map the fourth data field to the third column, `LastName`.</span></span>  
  
## <a name="non-xml-format-file-for-more-data-fields"></a><span data-ttu-id="f6052-119">Arquivo de formato não XML para mais campos de dados</span><span class="sxs-lookup"><span data-stu-id="f6052-119">Non-XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="f6052-120">O arquivo de formato a seguir, `myTestSkipField.fmt`, mapeia os campos em `myTestSkipField-c.dat` para as colunas da tabela `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="f6052-120">The following format file, `myTestSkipField.fmt`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="f6052-121">O arquivo de formato usa o formato de dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f6052-121">The format file uses character data format.</span></span> <span data-ttu-id="f6052-122">Ignorar um mapeamento de coluna requer a alteração do valor da ordem da coluna para 0, como mostrado para a coluna `ExtraField` no arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="f6052-122">Skipping a column mapping requires changing its column order value to 0, as shown for the `ExtraField` column in the format file.</span></span>  
  
 <span data-ttu-id="f6052-123">O arquivo de formato `myTestSkipField.fmt` contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="f6052-123">The `myTestSkipField.fmt` format file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     PersonID               ""  
2       SQLCHAR       0       100       ","    0     ExtraField             SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      2     FirstName              SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   3     LastName               SQL_Latin1_General_CP1_CI_AS  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f6052-124">Para obter informações sobre a sintaxe dos arquivos de formato não XML, veja [Arquivos de formato não XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f6052-124">For information about the syntax of non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="f6052-125">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f6052-125">Examples</span></span>  
 <span data-ttu-id="f6052-126">O exemplo a seguir usa `INSERT ... SELECT * FROM OPENROWSET(BULK...)` utilizando o arquivo de formato `myTestSkipField.fmt` .</span><span class="sxs-lookup"><span data-stu-id="f6052-126">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.fmt` format file.</span></span> <span data-ttu-id="f6052-127">O exemplo importa em massa o arquivo de dados `myTestSkipField-c.dat` para a tabela `myTestSkipField` .</span><span class="sxs-lookup"><span data-stu-id="f6052-127">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="f6052-128">Para criar a tabela e o arquivo de dados de exemplo, consulte "Tabela e arquivo de dados de exemplo", anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f6052-128">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="f6052-129">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], execute o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="f6052-129">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
   SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.fmt'    
       ) AS t1;  
GO   
```  
  
## <a name="xml-format-file-for-more-data-fields"></a><span data-ttu-id="f6052-130">Arquivo de formato XML para mais campos de dados</span><span class="sxs-lookup"><span data-stu-id="f6052-130">XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="f6052-131">O arquivo de formato apresentado neste exemplo tem base em outro arquivo de formato, `myTestSkipField.xml`, que usa formato de dados de caracteres sempre e cujos campos correspondem exatamente em número e ordem às colunas na tabela `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="f6052-131">The format file presented in this example is based on another format file, `myTestSkipField.xml`, which uses character data format throughout and whose fields correspond exactly in number and order to the columns in the `myTestSkipField` table.</span></span> <span data-ttu-id="f6052-132">Para exibir o conteúdo desse arquivo de formato, veja [Criar um arquivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f6052-132">To view the contents of that format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
 <span data-ttu-id="f6052-133">O arquivo de formato a seguir, `myTestSkipField.xml`, mapeia os campos em `myTestSkipField-c.dat` para as colunas da tabela `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="f6052-133">The following format file, `myTestSkipField.xml`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="f6052-134">O arquivo de formato usa o formato de dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f6052-134">The format file uses character data format.</span></span>  
  
 <span data-ttu-id="f6052-135">O arquivo de formato `myTestSkipField.xml` contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="f6052-135">The `myTestSkipField.xml` format file contains the following information:</span></span>  
  
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
  <COLUMN SOURCE="1" NAME="PersonID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="3" NAME="FirstName" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="LastName" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
### <a name="examples"></a><span data-ttu-id="f6052-136">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f6052-136">Examples</span></span>  
 <span data-ttu-id="f6052-137">O exemplo a seguir usa `INSERT ... SELECT * FROM OPENROWSET(BULK...)` utilizando o arquivo de formato `myTestSkipField.Xml` .</span><span class="sxs-lookup"><span data-stu-id="f6052-137">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.Xml` format file.</span></span> <span data-ttu-id="f6052-138">O exemplo importa em massa o arquivo de dados `myTestSkipField-c.dat` para a tabela `myTestSkipField` .</span><span class="sxs-lookup"><span data-stu-id="f6052-138">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="f6052-139">Para criar a tabela e o arquivo de dados de exemplo, consulte "Tabela e arquivo de dados de exemplo", anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f6052-139">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="f6052-140">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], execute o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="f6052-140">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
  SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.xml'    
       ) AS t1;  
GO  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f6052-141">Para obter informações sobre a sintaxe do esquema XML e exemplos adicionais de arquivos de formato XML, veja [Arquivos de formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f6052-141">For information about the syntax of the XML Schema and additional samples of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6052-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6052-142">See Also</span></span>  
 <span data-ttu-id="f6052-143">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="f6052-143">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="f6052-144">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f6052-144">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="f6052-145">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f6052-145">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="f6052-146">[Usar um arquivo de formato para ignorar uma coluna de tabela &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f6052-146">[Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span></span>  
 [<span data-ttu-id="f6052-147">Usar um arquivo de formato para mapear colunas de uma tabela para campos de arquivo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f6052-147">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
  
