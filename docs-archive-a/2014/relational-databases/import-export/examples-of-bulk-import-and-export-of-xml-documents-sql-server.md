---
title: Exemplos de importação e exportação em massa de documentos XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- field terminators [SQL Server]
- bulk importing [SQL Server], data formats
- row terminators [SQL Server]
- OPENROWSET function, XML bulk load
- terminators [SQL Server]
- bulk exporting [SQL Server], data formats
- XML bulk load [SQL Server]
ms.assetid: dff99404-a002-48ee-910e-f37f013d946d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d72c84a7ed84503e0c88d2a46c808196903900b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576394"
---
# <a name="examples-of-bulk-import-and-export-of-xml-documents-sql-server"></a><span data-ttu-id="b4184-102">Exemplos de importação e exportação em massa de documentos XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b4184-102">Examples of Bulk Import and Export of XML Documents (SQL Server)</span></span>
    
##  <a name="you-can-bulk-import-xml-documents-into-a-ssnoversion-database-or-bulk-export-them-from-a-ssnoversion-database-this-topic-provides-examples-of-both"></a><a name="top"></a><span data-ttu-id="b4184-103">Você pode importar documentos XML em massa em um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] banco de dados ou exportá-los em massa de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b4184-103">You can bulk import XML documents into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database or bulk export them from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="b4184-104">Este tópico fornece exemplos de ambas as operações.</span><span class="sxs-lookup"><span data-stu-id="b4184-104">This topic provides examples of both.</span></span>  
  
 <span data-ttu-id="b4184-105">Para importar dados em massa de em arquivo de dados para uma tabela ou exibição não particionada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , você pode usar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b4184-105">To bulk import data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or non-partitioned view, you can use the following:</span></span>  
  
-   <span data-ttu-id="b4184-106">utilitário**bcp**</span><span class="sxs-lookup"><span data-stu-id="b4184-106">**bcp** utility</span></span>  
  
     <span data-ttu-id="b4184-107">Você também pode usar o utilitário **bcp** para exportar dados de qualquer lugar de um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em que a instrução SELECT funcionar, incluindo exibições particionadas.</span><span class="sxs-lookup"><span data-stu-id="b4184-107">You can also use the **bcp** utility to export data from anywhere in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that a SELECT statement works, including partitioned views.</span></span>  
  
-   <span data-ttu-id="b4184-108">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="b4184-108">BULK INSERT</span></span>  
  
-   <span data-ttu-id="b4184-109">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="b4184-109">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
  
 <span data-ttu-id="b4184-110">Para obter mais informações, consulte [importar e exportar dados em massa usando o utilitário bcp &#40;SQL Server&#41;](import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md) e [importar dados em massa usando BULK INSERT ou OPENROWSET&#40;BULK... &#41; &#40;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md)SQL Server&#41;.</span><span class="sxs-lookup"><span data-stu-id="b4184-110">For more information, see [Import and Export Bulk Data by Using the bcp Utility &#40;SQL Server&#41;](import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md) and [Import Bulk Data by Using BULK INSERT or OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b4184-111">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b4184-111">Examples</span></span>  
 <span data-ttu-id="b4184-112">Os exemplos são:</span><span class="sxs-lookup"><span data-stu-id="b4184-112">The examples are the following:</span></span>  
  
-   <span data-ttu-id="b4184-113">a.</span><span class="sxs-lookup"><span data-stu-id="b4184-113">A.</span></span> [<span data-ttu-id="b4184-114">Importação em massa de dados XML como um fluxo de bytes binários</span><span class="sxs-lookup"><span data-stu-id="b4184-114">BULK importing XML data as a binary byte stream</span></span>](#binary_byte_stream)  
  
-   <span data-ttu-id="b4184-115">B.</span><span class="sxs-lookup"><span data-stu-id="b4184-115">B.</span></span> [<span data-ttu-id="b4184-116">Importação em massa de dados XML em uma linha existente</span><span class="sxs-lookup"><span data-stu-id="b4184-116">Bulk importing XML data in an existing row</span></span>](#existing_row)  
  
-   <span data-ttu-id="b4184-117">C.</span><span class="sxs-lookup"><span data-stu-id="b4184-117">C.</span></span> [<span data-ttu-id="b4184-118">Importação em massa de dados XML de um arquivo que contém um DTD</span><span class="sxs-lookup"><span data-stu-id="b4184-118">Bulk importing XML data from a file that contains a DTD</span></span>](#file_contains_dtd)  
  
-   <span data-ttu-id="b4184-119">D.</span><span class="sxs-lookup"><span data-stu-id="b4184-119">D.</span></span> [<span data-ttu-id="b4184-120">Especificando o terminador de campo explicitamente usando um arquivo de formato</span><span class="sxs-lookup"><span data-stu-id="b4184-120">Specifying the field terminator explicitly using a format file</span></span>](#field_terminator_in_format_file)  
  
-   <span data-ttu-id="b4184-121">E.</span><span class="sxs-lookup"><span data-stu-id="b4184-121">E.</span></span> [<span data-ttu-id="b4184-122">Exportação em massa de dados XML</span><span class="sxs-lookup"><span data-stu-id="b4184-122">Bulk exporting XML data</span></span>](#bulk_export_xml_data)  
  
###  <a name="a-bulk-importing-xml-data-as-a-binary-byte-stream"></a><a name="binary_byte_stream"></a> <span data-ttu-id="b4184-123">A.</span><span class="sxs-lookup"><span data-stu-id="b4184-123">A.</span></span> <span data-ttu-id="b4184-124">Importação em massa de dados XML como um fluxo de bytes binários</span><span class="sxs-lookup"><span data-stu-id="b4184-124">Bulk importing XML data as a binary byte stream</span></span>  
 <span data-ttu-id="b4184-125">Ao importar dados XML em massa de um arquivo que contém uma declaração de codificação que você deseja aplicar, especifique a opção SINGLE_BLOB na cláusula OPENROWSET (BULK…).</span><span class="sxs-lookup"><span data-stu-id="b4184-125">When you bulk import XML data from a file that contains an encoding declaration that you want to apply, specify the SINGLE_BLOB option in the OPENROWSET(BULK...) clause.</span></span> <span data-ttu-id="b4184-126">A opção SINGLE_BLOB assegura que o analisador XML no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] importe os dados de acordo com o esquema de codificação especificado na declaração XML.</span><span class="sxs-lookup"><span data-stu-id="b4184-126">The SINGLE_BLOB option makes sure that the XML parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] imports the data according to the encoding scheme specified in the XML declaration.</span></span>  
  
#### <a name="sample-table"></a><span data-ttu-id="b4184-127">Tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="b4184-127">Sample Table</span></span>  
 <span data-ttu-id="b4184-128">Para testar o exemplo A, você deve criar a tabela de exemplo `T`.</span><span class="sxs-lookup"><span data-stu-id="b4184-128">To test example A, you must create sample table `T`.</span></span>  
  
```  
USE tempdb  
CREATE TABLE T (IntCol int, XmlCol xml);  
GO  
```  
  
#### <a name="sample-data-file"></a><span data-ttu-id="b4184-129">Arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="b4184-129">Sample Data File</span></span>  
 <span data-ttu-id="b4184-130">Antes de poder executar o exemplo A, você deve criar um arquivo codificado UTF-8 (`C:\SampleFolder\SampleData3.txt`) que contenha a seguinte instância de exemplo que especifica o esquema de codificação `UTF-8` .</span><span class="sxs-lookup"><span data-stu-id="b4184-130">Before you can run example A, you must create a UTF-8 encoded file (`C:\SampleFolder\SampleData3.txt`) that contains the following sample instance that specifies the `UTF-8` encoding scheme.</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<Root>  
          <ProductDescription ProductModelID="5">  
             <Summary>Some Text</Summary>  
          </ProductDescription>  
</Root>  
```  
  
#### <a name="example-a"></a><span data-ttu-id="b4184-131">Exemplo A</span><span class="sxs-lookup"><span data-stu-id="b4184-131">Example A</span></span>  
 <span data-ttu-id="b4184-132">Esse exemplo usa a opção `SINGLE_BLOB` em uma instrução `INSERT ... SELECT * FROM OPENROWSET(BULK...)` para importar dados de um arquivo nomeado como `SampleData3.txt` e inserir uma instância XML na tabela com uma coluna, tabela de exemplo `T`.</span><span class="sxs-lookup"><span data-stu-id="b4184-132">This example uses the `SINGLE_BLOB` option in an `INSERT ... SELECT * FROM OPENROWSET(BULK...)` statement to import data from a file named `SampleData3.txt` and insert an XML instance in the single-column table, sample table `T`.</span></span>  
  
```  
INSERT INTO T(XmlCol)  
SELECT * FROM OPENROWSET(  
   BULK 'c:\SampleFolder\SampleData3.txt',  
   SINGLE_BLOB) AS x;  
```  
  
#### <a name="remarks"></a><span data-ttu-id="b4184-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="b4184-133">Remarks</span></span>  
 <span data-ttu-id="b4184-134">Usando SINGLE_BLOB nesse caso, você pode evitar uma desigualdade entre a codificação do documento XML (como especificado pela declaração de codificação XML) e a cadeia de caracteres da página de código implícita pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="b4184-134">By using SINGLE_BLOB in this case, you can avoid a mismatch between the encoding of the XML document (as specified by the XML encoding declaration) and the string codepage implied by the server.</span></span>  
  
 <span data-ttu-id="b4184-135">Se você usar tipos de dados NCLOB ou CLOB e executar em uma página de código ou conflito de código, você deve adotar um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b4184-135">If you use NCLOB or CLOB data types and run into a codepage or encoding conflict, you must do one of the following:</span></span>  
  
-   <span data-ttu-id="b4184-136">Remova a declaração XML para importar o conteúdo do arquivo de dados XML com êxito.</span><span class="sxs-lookup"><span data-stu-id="b4184-136">Remove the XML declaration to successfully import the contents of the XML data file.</span></span>  
  
-   <span data-ttu-id="b4184-137">Especifique uma página de código na opção CODEPAGE da consulta que corresponda ao esquema de codificação usado na declaração XML.</span><span class="sxs-lookup"><span data-stu-id="b4184-137">Specify a code page in the CODEPAGE option of the query that matches the encoding scheme that is used in the XML declaration.</span></span>  
  
-   <span data-ttu-id="b4184-138">Faça a correspondência ou resolva as definições de ordenação do banco de dados com um esquema de codificação XML não Unicode.</span><span class="sxs-lookup"><span data-stu-id="b4184-138">Match, or resolve, the database collation settings with a non-Unicode XML encoding scheme.</span></span>  
  
 [<span data-ttu-id="b4184-139">&#91;Início&#93;</span><span class="sxs-lookup"><span data-stu-id="b4184-139">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="b-bulk-importing-xml-data-in-an-existing-row"></a><a name="existing_row"></a> <span data-ttu-id="b4184-140">B.</span><span class="sxs-lookup"><span data-stu-id="b4184-140">B.</span></span> <span data-ttu-id="b4184-141">Importação em massa de dados XML em uma linha existente</span><span class="sxs-lookup"><span data-stu-id="b4184-141">Bulk importing XML data in an existing row</span></span>  
 <span data-ttu-id="b4184-142">Este exemplo usa o provedor de conjunto de linhas em massa `OPENROWSET` para adicionar uma instância XML a uma linha ou linhas existentes na tabela de exemplo `T`.</span><span class="sxs-lookup"><span data-stu-id="b4184-142">This example uses the `OPENROWSET` bulk rowset provider to add an XML instance to an existing row or rows in sample table `T`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4184-143">Para executar esse exemplo, você deve completar o teste de script fornecido no exemplo A, que cria a tabela `tempdb.dbo.T` e importa em massa os dados do `SampleData3.txt`.</span><span class="sxs-lookup"><span data-stu-id="b4184-143">To run this example, you must first complete the test script provided in example A. That example creates the `tempdb.dbo.T` table and bulk imports data from `SampleData3.txt`.</span></span>  
  
#### <a name="sample-data-file"></a><span data-ttu-id="b4184-144">Arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="b4184-144">Sample Data File</span></span>  
 <span data-ttu-id="b4184-145">O exemplo B usa uma versão modificada do arquivo de dados de exemplo `SampleData3.txt` do exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="b4184-145">Example B uses a modified version of the `SampleData3.txt` sample data file from the preceding example.</span></span> <span data-ttu-id="b4184-146">Para executar esse exemplo, modifique o conteúdo desse arquivo como indicado abaixo:</span><span class="sxs-lookup"><span data-stu-id="b4184-146">To run this example, modify the content of this file as follows:</span></span>  
  
```  
<Root>  
          <ProductDescription ProductModelID="10">  
             <Summary>Some New Text</Summary>  
          </ProductDescription>  
</Root>  
```  
  
#### <a name="example-b"></a><span data-ttu-id="b4184-147">Exemplo B</span><span class="sxs-lookup"><span data-stu-id="b4184-147">Example B</span></span>  
  
```  
-- Query before update shows initial state of XmlCol values.  
SELECT * FROM T  
UPDATE T  
SET XmlCol =(  
SELECT * FROM OPENROWSET(  
   BULK 'C:\SampleFolder\SampleData3.txt',  
           SINGLE_BLOB  
) AS x  
)  
WHERE IntCol = 1;  
GO  
```  
  
 [<span data-ttu-id="b4184-148">&#91;Início&#93;</span><span class="sxs-lookup"><span data-stu-id="b4184-148">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="c-bulk-importing-xml-data-from-a-file-that-contains-a-dtd"></a><a name="file_contains_dtd"></a> <span data-ttu-id="b4184-149">C.</span><span class="sxs-lookup"><span data-stu-id="b4184-149">C.</span></span> <span data-ttu-id="b4184-150">Importação em massa de dados XML de um arquivo que contém um DTD</span><span class="sxs-lookup"><span data-stu-id="b4184-150">Bulk importing XML data from a file that contains a DTD</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b4184-151">Recomendamos não habilitar o suporte a definições do tipo de documento (DTDs, Document Type Definitions) se não for necessário em seu ambiente XML.</span><span class="sxs-lookup"><span data-stu-id="b4184-151">We recommended that you not enable support for Document Type Definitions (DTDs) if it is not required in your XML environment.</span></span> <span data-ttu-id="b4184-152">Ativar o suporte a DTD aumenta a área da superfície atacável de seu servidor e pode expô-lo a um ataque de negação de serviço.</span><span class="sxs-lookup"><span data-stu-id="b4184-152">Turning on DTD support increases the attackable surface area of your server, and may expose it to a denial-of-service attack.</span></span> <span data-ttu-id="b4184-153">Caso seja necessário habilitar o suporte a DTD, você pode reduzir esse risco de segurança processando somente documentos XML confiáveis.</span><span class="sxs-lookup"><span data-stu-id="b4184-153">If you must enable DTD support, you can reduce this security risk by processing only trusted XML documents.</span></span>  
  
 <span data-ttu-id="b4184-154">Durante uma tentativa de usar um comando [bcp](../../tools/bcp-utility.md) para importar dados XML de um arquivo que contém um DTD, pode ocorrer um erro semelhante ao descrito abaixo:</span><span class="sxs-lookup"><span data-stu-id="b4184-154">During an attempt to use a [bcp](../../tools/bcp-utility.md) command to import XML data from a file that contains a DTD, an error similar to the following can occur:</span></span>  
  
 <span data-ttu-id="b4184-155">"SQLState = 42000, NativeError = 6359"</span><span class="sxs-lookup"><span data-stu-id="b4184-155">"SQLState = 42000, NativeError = 6359"</span></span>  
  
 <span data-ttu-id="b4184-156">"Erro = [Microsoft][SQL Server Native Client][ SQL Server]Não é permitida a análise de XML com DTDs de subconjunto interno.</span><span class="sxs-lookup"><span data-stu-id="b4184-156">"Error = [Microsoft][SQL Server Native Client][ SQL Server]Parsing XML with internal subset DTDs not allowed.</span></span> <span data-ttu-id="b4184-157">Use CONVERT com a opção de estilo 2 para habilitar o suporte a DTD de subconjunto interno limitado."</span><span class="sxs-lookup"><span data-stu-id="b4184-157">Use CONVERT with style option 2 to enable limited internal subset DTD support."</span></span>  
  
 <span data-ttu-id="b4184-158">"Falha na cópia BCP %s"</span><span class="sxs-lookup"><span data-stu-id="b4184-158">"BCP copy %s failed"</span></span>  
  
 <span data-ttu-id="b4184-159">Para resolver esse problema, você pode importar dados XML de um arquivo de dados que contém um DTD usando a função `OPENROWSET(BULK...)` e especificando a opção `CONVERT` na cláusula de comando `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="b4184-159">To work around this problem, you can import XML data from a data file that contains a DTD by using the `OPENROWSET(BULK...)` function and then specifying the `CONVERT` option in the `SELECT` clause of the command.</span></span> <span data-ttu-id="b4184-160">A sintaxe básica do comando é:</span><span class="sxs-lookup"><span data-stu-id="b4184-160">The basic syntax for the command is:</span></span>  
  
 `INSERT ... SELECT CONVERT(...) FROM OPENROWSET(BULK...)`  
  
#### <a name="sample-data-file"></a><span data-ttu-id="b4184-161">Arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="b4184-161">Sample Data File</span></span>  
 <span data-ttu-id="b4184-162">Antes de poder testar esse exemplo de importação em massa, crie um arquivo (`C:\temp\Dtdfile.xml`) que contém a seguinte instância de exemplo:</span><span class="sxs-lookup"><span data-stu-id="b4184-162">Before you can test this bulk import example, create a file (`C:\temp\Dtdfile.xml`) that contains the following sample instance:</span></span>  
  
```  
<!DOCTYPE DOC [<!ATTLIST elem1 attr1 CDATA "defVal1">]><elem1>January</elem1>  
```  
  
#### <a name="sample-table"></a><span data-ttu-id="b4184-163">Tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="b4184-163">Sample Table</span></span>  
 <span data-ttu-id="b4184-164">O exemplo que C usa a tabela de exemplo `T1` , criada pela seguinte instrução `CREATE TABLE` :</span><span class="sxs-lookup"><span data-stu-id="b4184-164">Example C uses the `T1` sample table that is created by the following `CREATE TABLE` statement:</span></span>  
  
```  
USE tempdb;  
CREATE TABLE T1(XmlCol xml);  
GO  
```  
  
#### <a name="example-c"></a><span data-ttu-id="b4184-165">Exemplo C</span><span class="sxs-lookup"><span data-stu-id="b4184-165">Example C</span></span>  
 <span data-ttu-id="b4184-166">Este exemplo usa `OPENROWSET(BULK...)` e especifica a opção `CONVERT` na cláusula `SELECT` para importar os dados XML do `Dtdfile.xml` na tabela de exemplo `T1`.</span><span class="sxs-lookup"><span data-stu-id="b4184-166">This example uses `OPENROWSET(BULK...)` and specifies the `CONVERT` option in the `SELECT` clause to import the XML data from `Dtdfile.xml` into sample table `T1`.</span></span>  
  
```  
INSERT T1  
  SELECT CONVERT(xml, BulkColumn, 2) FROM   
    OPENROWSET(Bulk 'c:\temp\Dtdfile.xml', SINGLE_BLOB) [rowsetresults];  
```  
  
 <span data-ttu-id="b4184-167">Depois que a instrução `INSERT` é executada, o DTD é eliminado do XML e armazenado na tabela `T1` .</span><span class="sxs-lookup"><span data-stu-id="b4184-167">After the `INSERT` statement executes, the DTD is stripped from the XML and stored in the `T1` table.</span></span>  
  
 [<span data-ttu-id="b4184-168">&#91;Início&#93;</span><span class="sxs-lookup"><span data-stu-id="b4184-168">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="d-specifying-the-field-terminator-explicitly-using-a-format-file"></a><a name="field_terminator_in_format_file"></a> <span data-ttu-id="b4184-169">D.</span><span class="sxs-lookup"><span data-stu-id="b4184-169">D.</span></span> <span data-ttu-id="b4184-170">Especificação do terminador de campo que usa explicitamente um arquivo de formato</span><span class="sxs-lookup"><span data-stu-id="b4184-170">Specifying the field terminator explicitly using a format file</span></span>  
 <span data-ttu-id="b4184-171">O exemplo abaixo mostra como importar em massa o seguinte documento XML, `Xmltable.dat`.</span><span class="sxs-lookup"><span data-stu-id="b4184-171">The following example shows how to bulk import the following XML document, `Xmltable.dat`.</span></span>  
  
#### <a name="sample-data-file"></a><span data-ttu-id="b4184-172">Arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="b4184-172">Sample Data File</span></span>  
 <span data-ttu-id="b4184-173">O documento em `Xmltable.dat` contém dois valores XML, um para cada linha.</span><span class="sxs-lookup"><span data-stu-id="b4184-173">The document in `Xmltable.dat` contains two XML values, one for each row.</span></span> <span data-ttu-id="b4184-174">O primeiro valor XML é codificado com UTF-16 e o segundo valor é codificado com UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b4184-174">The first XML value is encoded with UTF-16, and the second value is encoded with UTF-8.</span></span>  
  
 <span data-ttu-id="b4184-175">O conteúdo deste arquivo de dados é mostrado no despejo hexadecimal abaixo:</span><span class="sxs-lookup"><span data-stu-id="b4184-175">The contents of this data file are shown in the following Hex dump:</span></span>  
  
```  
FF FE 3C 00 3F 00 78 00-6D 00 6C 00 20 00 76 00  *..<.?.x.m.l. .v.*  
65 00 72 00 73 00 69 00-6F 00 6E 00 3D 00 22 00  *e.r.s.i.o.n.=.".*  
31 00 2E 00 30 00 22 00-20 00 65 00 6E 00 63 00  *1...0.". .e.n.c.*  
6F 00 64 00 69 00 6E 00-67 00 3D 00 22 00 75 00  *o.d.i.n.g.=.".u.*  
74 00 66 00 2D 00 31 00-36 00 22 00 3F 00 3E 00  *t.f.-.1.6.".?.>.*  
3C 00 72 00 6F 00 6F 00-74 00 3E 00 A2 4F 9C 76  *<.r.o.o.t.>..O.v*  
0C FA 77 E4 80 00 89 00-00 06 90 06 91 2E 9B 2E  *..w.............*  
99 34 A2 34 86 00 83 02-92 20 7F 02 4E C5 E4 A3  *.4.4..... ..N...*  
34 B2 B7 B3 B7 FE F8 FF-F8 00 3C 00 2F 00 72 00  *4.........<./.r.*  
6F 00 6F 00 74 00 3E 00-00 00 00 00 7A EF BB BF  *o.o.t.>.....z...*  
3C 3F 78 6D 6C 20 76 65-72 73 69 6F 6E 3D 22 31  *<?xml version="1*  
2E 30 22 20 65 6E 63 6F-64 69 6E 67 3D 22 75 74  *.0" encoding="ut*  
66 2D 38 22 3F 3E 3C 72-6F 6F 74 3E E4 BE A2 E7  *f-8"?><root>....*  
9A 9C EF A8 8C EE 91 B7-C2 80 C2 89 D8 80 DA 90  *................*  
E2 BA 91 E2 BA 9B E3 92-99 E3 92 A2 C2 86 CA 83  *................*  
E2 82 92 C9 BF EC 95 8E-EA 8F A4 EB 88 B4 EB 8E  *................*  
B7 EF BA B7 EF BF B8 C3-B8 3C 2F 72 6F 6F 74 3E  *.........</root>*  
00 00 00 00 7A                                   *....z*  
```  
  
#### <a name="sample-table"></a><span data-ttu-id="b4184-176">Tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="b4184-176">Sample Table</span></span>  
 <span data-ttu-id="b4184-177">Ao importar ou exportar um documento XML em massa, você deve usar um [terminador de campo](specify-field-and-row-terminators-sql-server.md) , que não pode aparecer em nenhum dos documentos; por exemplo, uma série de quatro nulos (`\0`) seguida pela letra `z`: `\0\0\0\0z`.</span><span class="sxs-lookup"><span data-stu-id="b4184-177">When you bulk import or export an XML document, you should use a [field terminator](specify-field-and-row-terminators-sql-server.md) that cannot possibly appear in any of the documents; for example, a series of four nulls (`\0`) followed by the letter `z`: `\0\0\0\0z`.</span></span>  
  
 <span data-ttu-id="b4184-178">Esse exemplo mostra como usar esse terminador de campo na tabela de exemplo `xTable` .</span><span class="sxs-lookup"><span data-stu-id="b4184-178">This example shows how to use this field terminator for the `xTable` sample table.</span></span> <span data-ttu-id="b4184-179">Para criar essa tabela exemplo, use a seguinte instrução `CREATE TABLE` :</span><span class="sxs-lookup"><span data-stu-id="b4184-179">To create this sample table, use the following `CREATE TABLE` statement:</span></span>  
  
```  
USE tempdb;  
CREATE TABLE xTable (xCol xml);  
GO  
```  
  
#### <a name="sample-format-file"></a><span data-ttu-id="b4184-180">Arquivo de formato de exemplo</span><span class="sxs-lookup"><span data-stu-id="b4184-180">Sample Format File</span></span>  
 <span data-ttu-id="b4184-181">O terminador de campo deve ser especificado no arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="b4184-181">The field terminator must be specified in the format file.</span></span> <span data-ttu-id="b4184-182">O exemplo D usa um arquivo de formato não XML chamado `Xmltable.fmt` que contém:</span><span class="sxs-lookup"><span data-stu-id="b4184-182">Example D uses a non-XML format file named `Xmltable.fmt` that contains the following:</span></span>  
  
```  
9.0  
1  
1       SQLBINARY     0       0       "\0\0\0\0z"    1     xCol         ""  
```  
  
 <span data-ttu-id="b4184-183">Você pode usar esse arquivo de formato para importar documentos XML em massa na tabela `xTable` usando um comando `bcp` ou uma instrução `BULK INSERT` ou `INSERT ... SELECT * FROM OPENROWSET(BULK...)` .</span><span class="sxs-lookup"><span data-stu-id="b4184-183">You can use this format file to bulk import XML documents into the `xTable` table by using a `bcp` command or a `BULK INSERT` or `INSERT ... SELECT * FROM OPENROWSET(BULK...)` statement.</span></span>  
  
#### <a name="example-d"></a><span data-ttu-id="b4184-184">Exemplo D</span><span class="sxs-lookup"><span data-stu-id="b4184-184">Example D</span></span>  
 <span data-ttu-id="b4184-185">Este exemplo usa o arquivo de formato `Xmltable.fmt` em uma instrução `BULK INSERT` para importar o conteúdo de um arquivo de dados XML chamado `Xmltable.dat`.</span><span class="sxs-lookup"><span data-stu-id="b4184-185">This example uses the `Xmltable.fmt` format file in a `BULK INSERT` statement to import the contents of an XML data file named `Xmltable.dat`.</span></span>  
  
```  
BULK INSERT xTable   
FROM 'C:\Xmltable.dat'  
WITH (FORMATFILE = 'C:\Xmltable.fmt');  
GO  
```  
  
 [<span data-ttu-id="b4184-186">&#91;Início&#93;</span><span class="sxs-lookup"><span data-stu-id="b4184-186">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="e-bulk-exporting-xml-data"></a><a name="bulk_export_xml_data"></a> <span data-ttu-id="b4184-187">E.</span><span class="sxs-lookup"><span data-stu-id="b4184-187">E.</span></span> <span data-ttu-id="b4184-188">Exportação em massa de dados XML</span><span class="sxs-lookup"><span data-stu-id="b4184-188">Bulk exporting XML data</span></span>  
 <span data-ttu-id="b4184-189">O exemplo abaixo usa o `bcp` para exportar dados XML em massa da tabela criada no exemplo anterior usando o mesmo arquivo de formato XML.</span><span class="sxs-lookup"><span data-stu-id="b4184-189">The following example uses `bcp` to bulk export XML data from the table that is created in the preceding example by using the same XML format file.</span></span> <span data-ttu-id="b4184-190">No comando `bcp` abaixo, `<server_name>` e `<instance_name>` representam espaços reservados que devem ser substituídos com os valores apropriados:</span><span class="sxs-lookup"><span data-stu-id="b4184-190">In the following `bcp` command, `<server_name>` and `<instance_name>` represent placeholders that must be replaced with appropriate values:</span></span>  
  
```  
bcp bulktest..xTable out a-wn.out -N -T -S<server_name>\<instance_name>  
```  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b4184-191">não salva a codificação XML quando os dados XML são persistentes no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b4184-191">does not save the XML encoding when XML data is persisted in the database.</span></span> <span data-ttu-id="b4184-192">Portanto, a codificação original de campos XML não está disponível quando dados XML são exportados.</span><span class="sxs-lookup"><span data-stu-id="b4184-192">Therefore, the original encoding of XML fields is not available when XML data is exported.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b4184-193">usa a codificação UTF-16 ao exportar dados XML.</span><span class="sxs-lookup"><span data-stu-id="b4184-193">uses UTF-16 encoding when exporting XML data.</span></span>  
  
 [<span data-ttu-id="b4184-194">&#91;Início&#93;</span><span class="sxs-lookup"><span data-stu-id="b4184-194">&#91;Top&#93;</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="b4184-195">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4184-195">See Also</span></span>  
 <span data-ttu-id="b4184-196">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b4184-196">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="b4184-197">[Cláusula SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b4184-197">[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) </span></span>  
 <span data-ttu-id="b4184-198">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b4184-198">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="b4184-199">[Importação e exportação em massa de dados &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b4184-199">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="b4184-200">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b4184-200">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="b4184-201">OPENROWSET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b4184-201">OPENROWSET &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/openrowset-transact-sql)  
  
  
