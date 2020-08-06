---
title: Usar o formato de caractere Unicode para importar ou exportar dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], Unicode character
- Unicode [SQL Server], bulk importing and exporting
ms.assetid: 74342a11-c1c0-4746-b482-7f3537744a70
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 520ce1b4eed8dc11d6d3fe038969257aea1e90fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685162"
---
# <a name="use-unicode-character-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="4304e-102">Usar o formato de caractere Unicode para importar ou exportar dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4304e-102">Use Unicode Character Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="4304e-103">O formato de caractere Unicode é recomendado para transferir em massa dados entre várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando um arquivo de dados com caracteres estendidos DBCS.</span><span class="sxs-lookup"><span data-stu-id="4304e-103">Unicode character format is recommended for bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended/DBCS characters.</span></span> <span data-ttu-id="4304e-104">O formato de dados de caractere Unicode permite exportar dados de um servidor usando uma página de código que difere da página de código usada pelo cliente que está executando a operação.</span><span class="sxs-lookup"><span data-stu-id="4304e-104">The Unicode character data format allows data to be exported from a server by using a code page that differs from the code page used by the client that is performing the operation.</span></span> <span data-ttu-id="4304e-105">Em tais casos, o uso do formato de caractere Unicode tem as seguintes vantagens:</span><span class="sxs-lookup"><span data-stu-id="4304e-105">In such cases, use of Unicode character format has the following advantages:</span></span>  
  
-   <span data-ttu-id="4304e-106">Se os dados de origem e destino forem tipos de dados Unicode, o uso do formato de caractere Unicode preservará todos os dados de caractere.</span><span class="sxs-lookup"><span data-stu-id="4304e-106">If the source and destination data are Unicode data types, use of Unicode character format preserves all of the character data.</span></span>  
  
-   <span data-ttu-id="4304e-107">se os dados de origem e destino não forem tipos de dados Unicode, o uso do formato de caractere Unicode minimizará a perda de caracteres estendidos nos dados de origem que não poderão ser representados no destino.</span><span class="sxs-lookup"><span data-stu-id="4304e-107">if the source and destination data are not Unicode data types, use of Unicode character format minimizes the loss of extended characters in the source data that cannot be represented at the destination.</span></span>  
  
 <span data-ttu-id="4304e-108">Os arquivos de dados em formato de caractere Unicode seguem as convenções para arquivos Unicode.</span><span class="sxs-lookup"><span data-stu-id="4304e-108">Unicode character format data files follow the conventions for Unicode files.</span></span> <span data-ttu-id="4304e-109">Os primeiros dois bytes do arquivo são números hexadecimais, 0xFFFE.</span><span class="sxs-lookup"><span data-stu-id="4304e-109">The first two bytes of the file are hexadecimal numbers, 0xFFFE.</span></span> <span data-ttu-id="4304e-110">Esses bytes servem como marcas de ordem do byte, especificando se o byte de ordem alta é armazenado em primeiro ou por último no arquivo.</span><span class="sxs-lookup"><span data-stu-id="4304e-110">These bytes serve as byte-order marks, specifying whether the high-order byte is stored first or last in the file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4304e-111">Para trabalhar com um arquivo de dados de caractere Unicode, todos os campos de entrada devem ser cadeias de caracteres de texto Unicode (isto é, sejam cadeias de caracteres Unicode de tamanho fixo ou terminadas por caractere).</span><span class="sxs-lookup"><span data-stu-id="4304e-111">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
 <span data-ttu-id="4304e-112">Os dados `sql_variant` que são armazenados em um arquivo de dados no formato de caractere Unicode operam da mesma maneira que operam em um arquivo de dados no formato de caractere, exceto que os dados são armazenados como `nchar` em vez de dados `char`.</span><span class="sxs-lookup"><span data-stu-id="4304e-112">The `sql_variant` data that is stored in a Unicode character-format data file operates in the same way it operates in a character-format data file, except that the data is stored as `nchar` instead of `char` data.</span></span> <span data-ttu-id="4304e-113">Para obter mais informações sobre formato de caractere, consulte [Suporte a ordenação e Unicode](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="4304e-113">For more information about character format, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="4304e-114">Para usar um campo ou terminador de linha diferente do padrão que é fornecido com formato de caractere Unicode, veja [Especificar terminadores de campo e linha &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4304e-114">To use a field or row terminator other than the default that is provided with Unicode character format, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
## <a name="command-options-for-unicode-character-format"></a><span data-ttu-id="4304e-115">Opções de comando para formato de caractere Unicode</span><span class="sxs-lookup"><span data-stu-id="4304e-115">Command Options for Unicode Character Format</span></span>  
 <span data-ttu-id="4304e-116">Você pode importar dados de formato de caractere Unicode para uma tabela usando **bcp**, BULK INSERT ou INSERT... Selecione \* de OPENROWSET (bulk...). Para um comando **bcp** ou instrução BULK INSERT, você pode especificar o formato de dados na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="4304e-116">You can import Unicode character format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="4304e-117">Para uma instrução INSERT... SELECT \* FROM OPENROWSET(BULK...), é necessário especificar o formato dos dados em um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="4304e-117">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="4304e-118">Há suporte ao formato de caractere Unicode nas seguintes opções da linha de comando:</span><span class="sxs-lookup"><span data-stu-id="4304e-118">Unicode character format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="4304e-119">Comando</span><span class="sxs-lookup"><span data-stu-id="4304e-119">Command</span></span>|<span data-ttu-id="4304e-120">Opção</span><span class="sxs-lookup"><span data-stu-id="4304e-120">Option</span></span>|<span data-ttu-id="4304e-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="4304e-121">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="4304e-122">**bcp**</span><span class="sxs-lookup"><span data-stu-id="4304e-122">**bcp**</span></span>|<span data-ttu-id="4304e-123">**-w**</span><span class="sxs-lookup"><span data-stu-id="4304e-123">**-w**</span></span>|<span data-ttu-id="4304e-124">Usa o formato de caractere Unicode.</span><span class="sxs-lookup"><span data-stu-id="4304e-124">Uses the Unicode character format.</span></span>|  
|<span data-ttu-id="4304e-125">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="4304e-125">BULK INSERT</span></span>|<span data-ttu-id="4304e-126">DataFileType **= '** widechar **'**</span><span class="sxs-lookup"><span data-stu-id="4304e-126">DATAFILETYPE **='** widechar **'**</span></span>|<span data-ttu-id="4304e-127">Usa o formato de caractere Unicode na importação em massa de dados.</span><span class="sxs-lookup"><span data-stu-id="4304e-127">Uses Unicode character format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="4304e-128">Para obter mais informações, consulte [Utilitário bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) ou [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4304e-128">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4304e-129">Como alternativa, você pode especificar a formatação por campo, em um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="4304e-129">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="4304e-130">Para obter mais informações, consulte [Arquivos de formato para importação ou exportação de dados &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4304e-130">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4304e-131">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4304e-131">Examples</span></span>  
 <span data-ttu-id="4304e-132">Os exemplos a seguir demonstram como exportar em massa dados de caractere Unicode usando **bcp** e importar em massa os mesmos dados usando BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="4304e-132">The following examples demonstrate how to bulk export Unicode character data using **bcp** and to bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="4304e-133">Tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="4304e-133">Sample Table</span></span>  
 <span data-ttu-id="4304e-134">Os exemplos requerem que uma tabela denominada tabela `myTestUniCharData` seja criada no banco de dados de exemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] no esquema `dbo` .</span><span class="sxs-lookup"><span data-stu-id="4304e-134">The examples require that a table named `myTestUniCharData` table be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="4304e-135">Antes de executar os exemplos, é necessário criar essa tabela.</span><span class="sxs-lookup"><span data-stu-id="4304e-135">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="4304e-136">Para criar esta tabela, no Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute:</span><span class="sxs-lookup"><span data-stu-id="4304e-136">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestUniCharData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="4304e-137">Para preencher esta tabela e exibir o conteúdo resultante, execute as seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="4304e-137">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniCharData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3')   
        ,(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
  
```  
  
### <a name="using-bcp-to-bulk-export-unicode-character-data"></a><span data-ttu-id="4304e-138">Usando o bcp para exportar em massa dados de caractere Unicode</span><span class="sxs-lookup"><span data-stu-id="4304e-138">Using bcp to Bulk Export Unicode Character Data</span></span>  
 <span data-ttu-id="4304e-139">Para exportar dados da tabela para o arquivo de dados, use **bcp** com a opção **out** e os seguintes qualificadores:</span><span class="sxs-lookup"><span data-stu-id="4304e-139">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="4304e-140">Qualificadores</span><span class="sxs-lookup"><span data-stu-id="4304e-140">Qualifiers</span></span>|<span data-ttu-id="4304e-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="4304e-141">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="4304e-142">**-w**</span><span class="sxs-lookup"><span data-stu-id="4304e-142">**-w**</span></span>|<span data-ttu-id="4304e-143">Especifica o formato de caractere Unicode.</span><span class="sxs-lookup"><span data-stu-id="4304e-143">Specifies Unicode character format.</span></span>|  
|<span data-ttu-id="4304e-144">**-t** `,`</span><span class="sxs-lookup"><span data-stu-id="4304e-144">**-t** `,`</span></span>|<span data-ttu-id="4304e-145">Especifica uma vírgula (`,`) como terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="4304e-145">Specifies a comma (`,`) as the field terminator.</span></span><br /><br /> <span data-ttu-id="4304e-146">Observação: o terminador de campo padrão é a guia caractere Unicode (\t).</span><span class="sxs-lookup"><span data-stu-id="4304e-146">Note: The default field terminator is the tab Unicode character (\t).</span></span> <span data-ttu-id="4304e-147">Para obter mais informações, veja [Especificar terminadores de campo e linha &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4304e-147">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>|  
|<span data-ttu-id="4304e-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="4304e-148">**-T**</span></span>|<span data-ttu-id="4304e-149">Especifica que o utilitário **bcp** se conecta ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com uma conexão confiável usando segurança integrada.</span><span class="sxs-lookup"><span data-stu-id="4304e-149">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="4304e-150">Se **-T** não for especificado, será necessário especificar **-U** e **-P** para que o logon tenha êxito.</span><span class="sxs-lookup"><span data-stu-id="4304e-150">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="4304e-151">O exemplo seguinte exporta em massa dados em formato de caractere Unicode da tabela `myTestUniCharData` em um arquivo de dados novo nomeado arquivo de dados `myTestUniCharData-w.Dat` que usa a vírgula (`,`) como terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="4304e-151">The following example bulk exports data in Unicode character format from the `myTestUniCharData` table into a new data file named `myTestUniCharData-w.Dat` data file that uses the comma (`,`) as the field terminator.</span></span> <span data-ttu-id="4304e-152">No prompt de comando do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="4304e-152">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestUniCharData out C:\myTestUniCharData-w.Dat -w -t, -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-unicode-character-data"></a><span data-ttu-id="4304e-153">Usando BULK INSERT para importar em massa dados de caractere Unicode</span><span class="sxs-lookup"><span data-stu-id="4304e-153">Using BULK INSERT to Bulk Import Unicode Character Data</span></span>  
 <span data-ttu-id="4304e-154">O exemplo a seguir usa `BULK INSERT` para importar os dados no arquivo de dados `myTestUniCharData-w.Dat` para a tabela `myTestUniCharData`.</span><span class="sxs-lookup"><span data-stu-id="4304e-154">The following example uses `BULK INSERT` to import the data in the `myTestUniCharData-w.Dat` data file into the `myTestUniCharData` table.</span></span> <span data-ttu-id="4304e-155">O terminador de campo de não padrão (`,`) deve ser declarado na instrução.</span><span class="sxs-lookup"><span data-stu-id="4304e-155">The nondefault field terminator (`,`) must be declared in the statement.</span></span> <span data-ttu-id="4304e-156">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute:</span><span class="sxs-lookup"><span data-stu-id="4304e-156">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BULK INSERT myTestUniCharData   
   FROM 'C:\myTestUniCharData-w.Dat'   
   WITH (  
      DATAFILETYPE='widechar',  
      FIELDTERMINATOR=','  
   );   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4304e-157">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="4304e-157">Related Tasks</span></span>  
 <span data-ttu-id="4304e-158">**Para usar formatos de dados para importação ou exportação em massa**</span><span class="sxs-lookup"><span data-stu-id="4304e-158">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="4304e-159">Importar dados de formato de caractere e nativo de versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="4304e-159">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="4304e-160">Usar o formato de caractere para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4304e-160">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="4304e-161">Usar o formato nativo para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4304e-161">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="4304e-162">Usar o formato nativo Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4304e-162">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="4304e-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4304e-163">See Also</span></span>  
 <span data-ttu-id="4304e-164">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="4304e-164">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="4304e-165">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4304e-165">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="4304e-166">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4304e-166">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="4304e-167">[Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4304e-167">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="4304e-168">Suporte a ordenações e a Unicode</span><span class="sxs-lookup"><span data-stu-id="4304e-168">Collation and Unicode Support</span></span>](../collations/collation-and-unicode-support.md)  
  
  
