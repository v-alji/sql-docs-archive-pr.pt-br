---
title: Usar um arquivo de formato para ignorar uma coluna de tabela (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- skipping columns when importing
- format files [SQL Server], skipping columns
ms.assetid: 30e0e7b9-d131-46c7-90a4-6ccf77e3d4f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 153ef21209ff4261020e26aca3bc52d28dc852a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584135"
---
# <a name="use-a-format-file-to-skip-a-table-column-sql-server"></a><span data-ttu-id="7430b-102">Usar um arquivo de formato para ignorar uma coluna de tabela (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7430b-102">Use a Format File to Skip a Table Column (SQL Server)</span></span>
  <span data-ttu-id="7430b-103">Este tópico descreve arquivos de formato.</span><span class="sxs-lookup"><span data-stu-id="7430b-103">This topic describes format files.</span></span> <span data-ttu-id="7430b-104">Você pode usar um arquivo de formato para ignorar a importação de uma coluna de tabela, quando o campo não existir no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="7430b-104">You can use a format file to skip importing a table column when the field does not exist in the data file.</span></span> <span data-ttu-id="7430b-105">Um arquivo de dados só poderá conter um número menor de campos que o número de colunas na tabela, se as colunas ignoradas forem anuláveis e/ou possuírem valor padrão.</span><span class="sxs-lookup"><span data-stu-id="7430b-105">A data file can contain fewer fields than the number of columns in the table only if the skipped columns are nullable and/or have default value.</span></span>

## <a name="sample-table-and-data-file"></a><span data-ttu-id="7430b-106">Tabela e arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="7430b-106">Sample Table and Data File</span></span>
 <span data-ttu-id="7430b-107">Os exemplos a seguir requerem uma tabela chamada `myTestSkipCol` , no banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] , no esquema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="7430b-107">The following examples require a table named `myTestSkipCol` in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="7430b-108">Crie essa tabela como se segue:</span><span class="sxs-lookup"><span data-stu-id="7430b-108">Create this table as follows:</span></span>

```
USE AdventureWorks2012;
GO
CREATE TABLE myTestSkipCol 
   (
   Col1 smallint,
   Col2 nvarchar(50) NULL,
   Col3 nvarchar(50) not NULL
   );
GO
```

 <span data-ttu-id="7430b-109">Os exemplos seguintes usam um arquivo de dados de exemplo `myTestSkipCol2.dat`com somente dois campos, ainda que a tabela correspondente tenha três colunas:</span><span class="sxs-lookup"><span data-stu-id="7430b-109">The following examples use a sample data file, `myTestSkipCol2.dat`, which contains only two fields, although the corresponding table contains three columns:</span></span>

```
1,DataForColumn3
1,DataForColumn3
1,DataForColumn3

```

 <span data-ttu-id="7430b-110">Para importar dados em massa do `myTestSkipCol2.dat` para a tabela `myTestSkipCol` , o arquivo de formato deve mapear o primeiro campo de dados para `Col1`, o segundo campo para `Col3`e ignorar a `Col2`.</span><span class="sxs-lookup"><span data-stu-id="7430b-110">To bulk import data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the format file must map the first data field to `Col1`, the second field to `Col3`, skipping `Col2`.</span></span>

## <a name="using-a-non-xml-format-file"></a><span data-ttu-id="7430b-111">Usando um arquivo de formato não XML</span><span class="sxs-lookup"><span data-stu-id="7430b-111">Using a Non-XML Format File</span></span>
 <span data-ttu-id="7430b-112">É possível modificar um arquivo de formato não XML para ignorar uma coluna de tabela.</span><span class="sxs-lookup"><span data-stu-id="7430b-112">You can modify a non-XML format file to skip a table column.</span></span> <span data-ttu-id="7430b-113">Em geral, isso envolve o uso do utilitário **bcp** para criar um arquivo de formato não XML padrão e a modificação do arquivo padrão em um editor de texto.</span><span class="sxs-lookup"><span data-stu-id="7430b-113">Typically, this involves using the **bcp** utility to create a default non-XML format file and the modifying the default file in a text editor.</span></span> <span data-ttu-id="7430b-114">O arquivo de formato modificado deve mapear cada campo existente para sua coluna de tabela correspondente e indicar qual, ou quais, coluna de tabela deve ser ignorada.</span><span class="sxs-lookup"><span data-stu-id="7430b-114">The modified format file must map each existing fields to its corresponding table column and indicate which table column or columns to skip.</span></span> <span data-ttu-id="7430b-115">Há duas alternativas para se modificar um arquivo de dados não XML padrão.</span><span class="sxs-lookup"><span data-stu-id="7430b-115">Two alternatives exist for modifying a default non-XML data file.</span></span> <span data-ttu-id="7430b-116">Ambas indicam que o campo de dados não existe no arquivo de dados e que nenhum dado será inserido na coluna de tabela correspondente.</span><span class="sxs-lookup"><span data-stu-id="7430b-116">Either alternative indicates that the data field does not exist in the data file and that no data will be inserted into the corresponding table column.</span></span>

### <a name="creating-a-default-non-xml-format-file"></a><span data-ttu-id="7430b-117">Criando um arquivo de formato não XML padrão</span><span class="sxs-lookup"><span data-stu-id="7430b-117">Creating a Default Non-XML Format File</span></span>
 <span data-ttu-id="7430b-118">Este tópico usa o arquivo de formato não XML padrão criado para a tabela de exemplo `myTestSkipCol` , usando o seguinte comando **bcp** :</span><span class="sxs-lookup"><span data-stu-id="7430b-118">This topic uses the default non-XML format file that was created for the `myTestSkipCol` sample table by using the following **bcp** command:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.fmt -c -T
```

 <span data-ttu-id="7430b-119">O comando anterior cria um arquivo de formato não XML, `myTestSkipCol_Default.fmt`.</span><span class="sxs-lookup"><span data-stu-id="7430b-119">The previous command creates a non-XML format file, `myTestSkipCol_Default.fmt`.</span></span> <span data-ttu-id="7430b-120">Esse arquivo de formato é denominado *arquivo de formato padrão* , pois esse é o formato gerado pelo **bcp**.</span><span class="sxs-lookup"><span data-stu-id="7430b-120">This format file is called a *default format file* because it is the form generated by **bcp**.</span></span> <span data-ttu-id="7430b-121">Geralmente, um arquivo de formato padrão descreve uma correspondência um-para-um entre campos de arquivo de dados e colunas de tabela.</span><span class="sxs-lookup"><span data-stu-id="7430b-121">Typically, a default format file describes a one-to-one correspondence between data-file fields and table columns.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="7430b-122">Talvez seja preciso especificar o nome da instância do servidor ao qual você está conectando.</span><span class="sxs-lookup"><span data-stu-id="7430b-122">You might have to specify the name of the server instance to which you are connecting.</span></span> <span data-ttu-id="7430b-123">Talvez também seja preciso especificar o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="7430b-123">Also, you might have to specify the user name and password.</span></span> <span data-ttu-id="7430b-124">Para obter mais informações, consulte [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="7430b-124">For more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>

 <span data-ttu-id="7430b-125">A ilustração a seguir exibe os valores nesses exemplos de arquivos de formato padrão.</span><span class="sxs-lookup"><span data-stu-id="7430b-125">The following illustration shows the values in this sample default format files.</span></span> <span data-ttu-id="7430b-126">A ilustração também mostra o nome de cada campo do arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="7430b-126">The illustration also shows the name of each format-file field.</span></span>

 <span data-ttu-id="7430b-127">![arquivo de formato não XML padrão para myTestSkipCol](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "arquivo de formato não XML padrão para myTestSkipCol")</span><span class="sxs-lookup"><span data-stu-id="7430b-127">![default non-XML format file for myTestSkipCol](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "default non-XML format file for myTestSkipCol")</span></span>

> [!NOTE]
>  <span data-ttu-id="7430b-128">Para obter mais informações sobre campos de arquivo de formato, consulte [Arquivos de formato não XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7430b-128">For more information about the format-file fields, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="methods-for-modifying-a-non-xml-format-file"></a><span data-ttu-id="7430b-129">Métodos para modificar um arquivo de formato não XML</span><span class="sxs-lookup"><span data-stu-id="7430b-129">Methods for Modifying a Non-XML Format File</span></span>
 <span data-ttu-id="7430b-130">Para ignorar uma coluna de tabela, edite o arquivo de formato não XML padrão e modifique o arquivo, recorrendo a um dos seguintes métodos alternativos:</span><span class="sxs-lookup"><span data-stu-id="7430b-130">To skip a table column, edit the default non-XML format file and modify the file by using one of the following alternative methods:</span></span>

-   <span data-ttu-id="7430b-131">O método preferencial compreende três etapas básicas.</span><span class="sxs-lookup"><span data-stu-id="7430b-131">The preferred method involves three basic steps.</span></span> <span data-ttu-id="7430b-132">Primeiro, exclua qualquer linha do arquivo de formato que descreva um campo ausente do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="7430b-132">First, delete any format-file row that describes a field that is missing from the data file.</span></span> <span data-ttu-id="7430b-133">Então, reduza o valor da "Ordem do campo de arquivo host" de cada linha do arquivo de formato que segue uma linha excluída.</span><span class="sxs-lookup"><span data-stu-id="7430b-133">Then, reduce the "Host file field order" value of each format-file row that follows a deleted row.</span></span> <span data-ttu-id="7430b-134">A meta são valores sequenciais "Ordem do campo de arquivo host", de 1 a *n*que reflitam a posição atual de cada campo de dados no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="7430b-134">The goal is sequential "Host file field order" values, 1 through *n*, that reflect the actual position of each data field in the data file.</span></span> <span data-ttu-id="7430b-135">Finalmente, reduza o valor no campo "Número de colunas" para refletir o número real de campos no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="7430b-135">Finally, reduce the value in the "Number of columns" field to reflect the actual number of fields in the data file.</span></span>

     <span data-ttu-id="7430b-136">O exemplo a seguir foi baseado no arquivo de formato padrão para a tabela `myTestSkipCol` , criada anteriormente neste tópico, em "Criando um arquivo de formato não XML padrão".</span><span class="sxs-lookup"><span data-stu-id="7430b-136">The following example is based on the default format file for the `myTestSkipCol` table, which is created in "Creating a Default Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="7430b-137">Este arquivo de formato modificado mapeia o primeiro campo de dados para a `Col1`, ignora a `Col2`e mapeia o segundo campo de dados para a `Col3`.</span><span class="sxs-lookup"><span data-stu-id="7430b-137">This modified format file maps the first data field to `Col1`, skips `Col2`, and maps the second data field to `Col3`.</span></span> <span data-ttu-id="7430b-138">A linha da `Col2` foi excluída.</span><span class="sxs-lookup"><span data-stu-id="7430b-138">The row for `Col2` has been deleted.</span></span> <span data-ttu-id="7430b-139">Outras modificações estão indicadas em negrito:</span><span class="sxs-lookup"><span data-stu-id="7430b-139">Other modifications are indicated in bold:</span></span>

    ```
    9.0
    2
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

-   <span data-ttu-id="7430b-140">Como alternativa para ignorar uma coluna de tabela, é possível modificar a definição da linha do arquivo de formato que corresponde à coluna de tabela.</span><span class="sxs-lookup"><span data-stu-id="7430b-140">Alternatively, to skip a table column, you can modify the definition of the format-file row that corresponds to the table column.</span></span> <span data-ttu-id="7430b-141">Nessa linha do arquivo de formato, os valores "comprimento do prefixo", "comprimento dos dados do arquivo host" e "ordem da coluna do servidor" devem ser definidos como 0.</span><span class="sxs-lookup"><span data-stu-id="7430b-141">In this format-file row, the "prefix length," "host file data length," and "server column order" values must be set to 0.</span></span> <span data-ttu-id="7430b-142">Além disso, o campos "terminador" e "ordenação de colunas" devem ser definidos como "" (NULO).</span><span class="sxs-lookup"><span data-stu-id="7430b-142">Also, the "terminator" and "column collation" fields must be set to "" (NULL).</span></span>

     <span data-ttu-id="7430b-143">O valor "nome da coluna de servidor" requer uma cadeia de caracteres não vazios, ainda que o nome de coluna em si não seja necessário.</span><span class="sxs-lookup"><span data-stu-id="7430b-143">The "server column name" value requires a nonblank string, though the actual column name is not necessary.</span></span> <span data-ttu-id="7430b-144">Os campos de formato restantes requerem seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="7430b-144">The remaining format fields require their default values.</span></span>

     <span data-ttu-id="7430b-145">O exemplo a seguir também é derivado do arquivo de formato padrão da tabela `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="7430b-145">The following example is also derived from the default format file for the `myTestSkipCol` table.</span></span> <span data-ttu-id="7430b-146">Os valores que devem ser 0 ou NULL estão indicados em negrito.</span><span class="sxs-lookup"><span data-stu-id="7430b-146">Values that must be 0 or NULL are indicated in bold.</span></span>

    ```
    9.0
    3
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       00""0     Col2         ""
    3       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

### <a name="examples"></a><span data-ttu-id="7430b-147">Exemplos</span><span class="sxs-lookup"><span data-stu-id="7430b-147">Examples</span></span>
 <span data-ttu-id="7430b-148">Os exemplos a seguir também são baseados na tabela de exemplo `myTestSkipCol` e no arquivo de dados de exemplo `myTestSkipCol2.dat` criados anteriormente neste tópico, em "Tabela de exemplo e arquivo de dados".</span><span class="sxs-lookup"><span data-stu-id="7430b-148">The following examples are also based on the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span>

#### <a name="using-bulk-insert"></a><span data-ttu-id="7430b-149">Usando BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="7430b-149">Using BULK INSERT</span></span>
 <span data-ttu-id="7430b-150">Esse exemplo funciona usando qualquer um dos arquivos de formato não XML modificados criados anteriormente neste tópico, em "Métodos para modificar um arquivo de formato não XML".</span><span class="sxs-lookup"><span data-stu-id="7430b-150">This example works by using either of the modified non-XML format files created in "Methods for Modifying a Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="7430b-151">Nesse exemplo, o nome do arquivo de formato modificado é `C:\myTestSkipCol2.fmt`.</span><span class="sxs-lookup"><span data-stu-id="7430b-151">In this example, the modified format file is named `C:\myTestSkipCol2.fmt`.</span></span> <span data-ttu-id="7430b-152">Para usar o `BULK INSERT` para importar em massa o arquivo de dados `myTestSkipCol2.dat` , no Editor de Consultas [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute o código a seguir:</span><span class="sxs-lookup"><span data-stu-id="7430b-152">To use `BULK INSERT` to bulk import the `myTestSkipCol2.dat` data file, in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
BULK INSERT myTestSkipCol 
   FROM 'C:\myTestSkipCol2.dat' 
   WITH (FORMATFILE = 'C:\myTestSkipCol2.fmt');
GO
SELECT * FROM myTestSkipCol;
GO
```

## <a name="using-an-xml-format-file"></a><span data-ttu-id="7430b-153">Usando um arquivo de formato XML</span><span class="sxs-lookup"><span data-stu-id="7430b-153">Using an XML Format File</span></span>
 <span data-ttu-id="7430b-154">Com um arquivo de formato XML, não é possível ignorar uma coluna durante a importação direta para uma tabela usando um comando **bcp** ou uma instrução BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="7430b-154">With an XML format file, you cannot skip a column when you are importing directly into a table by using a **bcp** command or a BULK INSERT statement.</span></span> <span data-ttu-id="7430b-155">No entanto, é possível realizar a importação para todas as colunas de uma tabela, exceto para a última.</span><span class="sxs-lookup"><span data-stu-id="7430b-155">However, you can import into all but the last column of a table.</span></span> <span data-ttu-id="7430b-156">Se for preciso ignorar alguma que não a última coluna, crie uma exibição da tabela de destino que contenha apenas as colunas contidas no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="7430b-156">If you have to skip any but the last column, you must create a view of the target table that contains only the columns contained in the data file.</span></span> <span data-ttu-id="7430b-157">Depois, importe em massa os dados desse arquivo para a exibição.</span><span class="sxs-lookup"><span data-stu-id="7430b-157">Then, you can bulk import data from that file into the view.</span></span>

 <span data-ttu-id="7430b-158">Para usar um arquivo de formato XML para ignorar uma coluna de tabela usando OPENROWSET(BULK...), é necessário fornecer uma lista explícita de colunas na lista de seleção e também na tabela de destino, como se segue:</span><span class="sxs-lookup"><span data-stu-id="7430b-158">To use an XML format file to skip a table column by using OPENROWSET(BULK...), you have to provide explicit list of columns in the select list and also in the target table, as follows:</span></span>

 <span data-ttu-id="7430b-159">INSERT ...<column_list> SELECT <column_list> FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="7430b-159">INSERT ...<column_list> SELECT <column_list> FROM OPENROWSET(BULK...)</span></span>

### <a name="creating-a-default-xml-format-file"></a><span data-ttu-id="7430b-160">Criando um arquivo de formato XML padrão</span><span class="sxs-lookup"><span data-stu-id="7430b-160">Creating a Default XML Format File</span></span>
 <span data-ttu-id="7430b-161">Os exemplos dos arquivos de formato modificados se baseiam na tabela de exemplo `myTestSkipCol` e no arquivo de dados criado anteriormente neste tópico, em "Tabela de exemplo e arquivo de dados".</span><span class="sxs-lookup"><span data-stu-id="7430b-161">The examples of modified format files are based on the `myTestSkipCol` sample table and data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="7430b-162">O comando **bcp** a seguir cria um arquivo de formato XML padrão para a tabela `myTestSkipCol` :</span><span class="sxs-lookup"><span data-stu-id="7430b-162">The following **bcp** command creates a default XML format file for the `myTestSkipCol` table:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.xml -c -x -T
```

 <span data-ttu-id="7430b-163">O arquivo de formato não XML padrão resultante descreve uma correspondência um-para-um entre campos de arquivo de dados e colunas de tabela, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7430b-163">The resulting default non-XML format file describes a one-to-one correspondence between data-file fields and table columns, as follows:</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

> [!NOTE]
>  <span data-ttu-id="7430b-164">Para obter informações sobre a estrutura de arquivos de formato XML, consulte [Arquivos de formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7430b-164">For information about the structure of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="examples"></a><span data-ttu-id="7430b-165">Exemplos</span><span class="sxs-lookup"><span data-stu-id="7430b-165">Examples</span></span>
 <span data-ttu-id="7430b-166">Os exemplos desta seção usam a tabela de exemplo `myTestSkipCol` e o arquivo de dados de exemplo `myTestSkipCol2.dat` criados anteriormente neste tópico, em "Tabela de exemplo e arquivo de dados".</span><span class="sxs-lookup"><span data-stu-id="7430b-166">The examples in this section use the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="7430b-167">Para importar os dados de `myTestSkipCol2.dat` para a tabela `myTestSkipCol` , os exemplos usam o seguinte arquivo de formato XML modificado, `myTestSkipCol2-x.xml`.</span><span class="sxs-lookup"><span data-stu-id="7430b-167">To import the data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the examples use the following modified XML format file, `myTestSkipCol2-x.xml`.</span></span> <span data-ttu-id="7430b-168">A base para isso é o arquivo de formato criado anteriormente neste tópico, em "Criando um arquivo de formato XML padrão".</span><span class="sxs-lookup"><span data-stu-id="7430b-168">This is based on the format file that is created in "Creating a Default XML Format File," earlier in this topic.</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

#### <a name="using-openrowsetbulk"></a><span data-ttu-id="7430b-169">Usando OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="7430b-169">Using OPENROWSET(BULK...)</span></span>
 <span data-ttu-id="7430b-170">O exemplo a seguir usa o provedor de conjunto de linhas em massa `OPENROWSET` e o arquivo de formato `myTestSkipCol2.xml` .</span><span class="sxs-lookup"><span data-stu-id="7430b-170">The following example uses the `OPENROWSET` bulk rowset provider and the `myTestSkipCol2.xml` format file.</span></span> <span data-ttu-id="7430b-171">O exemplo importa em massa o arquivo de dados `myTestSkipCol2.dat` para a tabela `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="7430b-171">The example bulk imports the `myTestSkipCol2.dat` data file into the `myTestSkipCol` table.</span></span> <span data-ttu-id="7430b-172">A instrução contém uma lista explícita de colunas na lista de seleção e também na tabela de destino, como exigido.</span><span class="sxs-lookup"><span data-stu-id="7430b-172">The statement contains an explicit list of columns in the select list and also in the target table, as required.</span></span>

 <span data-ttu-id="7430b-173">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="7430b-173">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
INSERT INTO myTestSkipCol
  (Col1,Col3)
    SELECT Col1,Col3
      FROM  OPENROWSET(BULK  'C:\myTestSkipCol2.Dat',
      FORMATFILE='C:\myTestSkipCol2.Xml'  
       ) as t1 ;
GO
```

#### <a name="using-bulk-import-on-a-view"></a><span data-ttu-id="7430b-174">Usando o BULK IMPORT em uma exibição</span><span class="sxs-lookup"><span data-stu-id="7430b-174">Using BULK IMPORT on a View</span></span>
 <span data-ttu-id="7430b-175">O exemplo a seguir cria o `v_myTestSkipCol` na tabela `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="7430b-175">The following example creates the `v_myTestSkipCol` on the `myTestSkipCol` table.</span></span> <span data-ttu-id="7430b-176">Essa exibição ignora a segunda coluna da tabela, `Col2`.</span><span class="sxs-lookup"><span data-stu-id="7430b-176">This view skips the second table column, `Col2`.</span></span> <span data-ttu-id="7430b-177">O exemplo usa o `BULK INSERT` para importar o arquivo de dados `myTestSkipCol2.dat` para essa exibição.</span><span class="sxs-lookup"><span data-stu-id="7430b-177">The example then uses `BULK INSERT` to import the `myTestSkipCol2.dat` data file into this view.</span></span>

 <span data-ttu-id="7430b-178">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="7430b-178">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
CREATE VIEW v_myTestSkipCol AS
    SELECT Col1,Col3
    FROM myTestSkipCol;
GO

USE AdventureWorks2012;
GO
BULK INSERT v_myTestSkipCol
FROM 'C:\myTestSkipCol2.dat'
WITH (FORMATFILE='C:\myTestSkipCol2.xml');
GO
```

## <a name="see-also"></a><span data-ttu-id="7430b-179">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7430b-179">See Also</span></span>
 <span data-ttu-id="7430b-180">[utilitário bcp](../../tools/bcp-utility.md) [BULK INSERT &#40;transact-sql&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) [usar um arquivo de formato para ignorar um campo de dados &#40;](use-a-format-file-to-skip-a-data-field-sql-server.md) SQL Server [usar um arquivo de formato para mapear colunas de tabela para campos de arquivo de dados&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md) &#40;SQL Server [usar um arquivo de formato para importar dados em massa&#41;](use-a-format-file-to-bulk-import-data-sql-server.md) &#40;SQL Server</span><span class="sxs-lookup"><span data-stu-id="7430b-180">[bcp Utility](../../tools/bcp-utility.md) [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md) [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md) [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md)</span></span>


