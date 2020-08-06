---
title: Usar o formato nativo para importar ou exportar dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- data formats [SQL Server], native
ms.assetid: eb279b2f-0f1f-428f-9b8f-2a7fc495b79f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab42ba3eb6468aac3da2fa780d371818c8776690
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685164"
---
# <a name="use-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="3ffc7-102">Usar o formato nativo para importar ou exportar dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3ffc7-102">Use Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="3ffc7-103">O formato nativo é recomendado quando você transfere dados em massa entre várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando um arquivo de dados que não contém nenhum conjunto de caracteres estendidos ou DBCS (Conjunto de caracteres de byte duplo).</span><span class="sxs-lookup"><span data-stu-id="3ffc7-103">Native format is recommended when you bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using a data file that does not contain any extended/double-byte character set (DBCS) characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3ffc7-104">Para transferir dados em massa entre várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando um arquivo de dados com caracteres estendidos ou DBCS, use o formato nativo Unicode.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-104">To bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters, you should use the Unicode native format.</span></span> <span data-ttu-id="3ffc7-105">Para obter mais informações, veja [Usar o formato nativo Unicode para importar ou exportar dados &#40;SQL Server&#41;](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3ffc7-105">For more information, see [Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="3ffc7-106">O formato nativo mantém os tipos de dados nativos de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-106">Native format maintains the native data types of a database.</span></span> <span data-ttu-id="3ffc7-107">O formato nativo é planejado para transferência de dados em alta velocidade de dados entre tabelas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ffc7-107">Native format is intended for high-speed data transfer of data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="3ffc7-108">Se você usar um arquivo de formato, as tabelas de origem e destino não precisarão ser idênticas.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-108">If you use a format file, the source and target tables do not need to be identical.</span></span> <span data-ttu-id="3ffc7-109">A transferência de dados envolve duas etapas:</span><span class="sxs-lookup"><span data-stu-id="3ffc7-109">The data transfer involves two steps:</span></span>  
  
1.  <span data-ttu-id="3ffc7-110">A exportação de dados em massa de uma tabela de origem para um arquivo de dados</span><span class="sxs-lookup"><span data-stu-id="3ffc7-110">Bulk exporting the data from a source table into a data file</span></span>  
  
2.  <span data-ttu-id="3ffc7-111">A exportação de dados em massa do arquivo de dados para uma tabela de origem</span><span class="sxs-lookup"><span data-stu-id="3ffc7-111">Bulk importing the data from the data file into the target table</span></span>  
  
 <span data-ttu-id="3ffc7-112">O uso de formato nativo entre tabelas idênticas evita conversão desnecessária de tipos de dados do e para formato de caractere, economizando tempo e espaço.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-112">The use of native format between identical tables avoids unnecessary conversion of data types to and from character format, saving time and space.</span></span> <span data-ttu-id="3ffc7-113">Porém, para alcançar a taxa de transferência otimizada são executadas algumas verificações referentes à formatação dos dados.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-113">To achieve the optimum transfer rate, however, few checks are performed regarding data formatting.</span></span> <span data-ttu-id="3ffc7-114">Para evitar problemas com os dados carregados, consulte a lista de restrições a seguir.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-114">To prevent problems with the loaded data, see the following restrictions list.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="3ffc7-115">Restrições</span><span class="sxs-lookup"><span data-stu-id="3ffc7-115">Restrictions</span></span>  
 <span data-ttu-id="3ffc7-116">Para importar dados em formato nativo com êxito, garanta que:</span><span class="sxs-lookup"><span data-stu-id="3ffc7-116">To import data in native format successfully, ensure that:</span></span>  
  
-   <span data-ttu-id="3ffc7-117">O arquivo de dados está em formato nativo.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-117">The data file is in native format.</span></span>  
  
-   <span data-ttu-id="3ffc7-118">A tabela de destino deve ser compatível com o arquivo de dados (com o número correto de colunas, tipo de dados, comprimento, status NULL, e assim sucessivamente) ou você deve usar um arquivo de formato para mapear cada campo para suas colunas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-118">Either the target table must be compatible with the data file (having the correct number of columns, data type, length, NULL status, and so forth), or you must use a format file to map each field to its corresponding columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3ffc7-119">Se você importar dados de um arquivo que não corresponde à tabela de destino, a operação de importação poderá ter sucesso, mas os valores de dados inseridos na tabela de destino poderão estar incorretos.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-119">If you import data from a file that is mismatched with the target table, the import operation might succeed but the data values inserted into the target table are likely to be incorrect.</span></span> <span data-ttu-id="3ffc7-120">Isso porque os dados do arquivo são interpretados usando o formato da tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-120">This is because the data from the file is interpreted by using the format of the target table.</span></span> <span data-ttu-id="3ffc7-121">Portanto, qualquer resultado divergente resultará na inserção de valores incorretos.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-121">Therefore, any mismatch results in the insertion of incorrect values.</span></span> <span data-ttu-id="3ffc7-122">Porém, em nenhuma circunstância tal divergência pode causar inconsistências lógicas ou físicas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-122">However, under no circumstances can such a mismatch cause logical or physical inconsistencies in the database.</span></span>  
  
     <span data-ttu-id="3ffc7-123">Para obter informações sobre como usar arquivos de formato, veja [Arquivos de formato para importação ou exportação de dados &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3ffc7-123">For information on using format files, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="3ffc7-124">Uma importação bem-sucedida não corromperá a tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-124">A successful import will not corrupt the target table.</span></span>  
  
## <a name="how-bcp-handles-data-in-native-format"></a><span data-ttu-id="3ffc7-125">Como o bcp trata dados no formato nativo</span><span class="sxs-lookup"><span data-stu-id="3ffc7-125">How bcp Handles Data in Native Format</span></span>  
 <span data-ttu-id="3ffc7-126">Esta seção discute considerações especiais sobre como o utilitário **bcp** exporta e importa dados em formato nativo.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-126">This section discusses special considerations for how the **bcp** utility exports and imports data in native format.</span></span>  
  
-   <span data-ttu-id="3ffc7-127">Dados não caracteres</span><span class="sxs-lookup"><span data-stu-id="3ffc7-127">Noncharacter data</span></span>  
  
     <span data-ttu-id="3ffc7-128">O utilitário bcp usa o formato de dados binário interno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para gravar dados não caracteres de uma tabela para um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-128">The bcp utility uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internal binary data format to write noncharacter data from a table to a data file.</span></span>  
  
-   <span data-ttu-id="3ffc7-129">Dados `char` ou `varchar`</span><span class="sxs-lookup"><span data-stu-id="3ffc7-129">`char` or `varchar` data</span></span>  
  
     <span data-ttu-id="3ffc7-130">No início de cada `char` campo ou `varchar` , o **bcp** adiciona o comprimento do prefixo.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-130">At the beginning of each `char` or `varchar` field, **bcp** adds the prefix length.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3ffc7-131">Quando o modo nativo é usado, por padrão, o utilitário **bcp** converte caracteres de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para caracteres OEM antes de copiá-los para um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-131">When native mode is used, by default, the **bcp** utility converts characters from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to OEM characters before it copies them to a data file.</span></span> <span data-ttu-id="3ffc7-132">O utilitário **bcp** converte os caracteres de um arquivo de dados em caracteres ANSI antes de importá-los em uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-132">The **bcp** utility converts characters from a data file to ANSI characters before it bulk imports them into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="3ffc7-133">Durante essas conversões, podem ser perdidos dados de caractere estendidos.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-133">During these conversions, extended character data can be lost.</span></span> <span data-ttu-id="3ffc7-134">Para caracteres estendidos, use o formato nativo Unicode ou especifique uma página de código.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-134">For extended characters, either use Unicode native format or specify a code page.</span></span>  
  
-   <span data-ttu-id="3ffc7-135">Dados `sql_variant`</span><span class="sxs-lookup"><span data-stu-id="3ffc7-135">`sql_variant` data</span></span>  
  
     <span data-ttu-id="3ffc7-136">Se dados `sql_variant` forem armazenados como SQLVARIANT em um arquivo de dados do formato nativo, os dados manterão todas as suas características.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-136">If `sql_variant` data is stored as a SQLVARIANT in a native-format data file, the data maintains all of its characteristics.</span></span> <span data-ttu-id="3ffc7-137">Os metadados que registram o tipo de dados de cada valor de dado são armazenados com os valores de dados.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-137">The metadata that records the data type of each data value is stored along with the data value.</span></span> <span data-ttu-id="3ffc7-138">Esses metadados são usados para recriar o valor de dado com o mesmo tipo de dados em uma coluna `sql_variant` de destino.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-138">This metadata is used to re-create the data value with the same data type in a destination `sql_variant` column.</span></span>  
  
     <span data-ttu-id="3ffc7-139">Se o tipo de dados da coluna de destino não for `sql_variant`, cada valor dos dados será convertido no tipo de dados da coluna de destino, seguindo as regras normais de conversão de dados implícita.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-139">If the data type of the destination column is not `sql_variant`, each data value is converted to the data type of the destination column, following the normal rules of implicit data conversion.</span></span> <span data-ttu-id="3ffc7-140">Se ocorrer um erro durante a conversão dos dados, o lote atual será revertido.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-140">If an error occurs during data conversion, the current batch is rolled back.</span></span> <span data-ttu-id="3ffc7-141">Qualquer valor `char` e `varchar` transferido entre colunas `sql_variant` pode ter problemas de conversão de página de código.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-141">Any `char` and `varchar` values that are transferred between `sql_variant` columns may have code page conversion issues.</span></span>  
  
     <span data-ttu-id="3ffc7-142">Para obter mais informações sobre conversão de dados, consulte [Conversão de tipo de dados &#40;Mecanismo do Banco de Dados &#41;](/sql/t-sql/data-types/data-type-conversion-database-engine).</span><span class="sxs-lookup"><span data-stu-id="3ffc7-142">For more information about data conversion, see [Data Type Conversion &#40;Database Engine&#41;](/sql/t-sql/data-types/data-type-conversion-database-engine).</span></span>  
  
## <a name="command-options-for-native-format"></a><span data-ttu-id="3ffc7-143">Opções de comando para formato nativo</span><span class="sxs-lookup"><span data-stu-id="3ffc7-143">Command Options for Native Format</span></span>  
 <span data-ttu-id="3ffc7-144">Você pode importar dados de formato nativo para uma tabela usando **bcp**, BULK INSERT ou INSERT... Selecione \* de OPENROWSET (bulk...). Para um comando **bcp** ou instrução BULK INSERT, você pode especificar o formato de dados na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-144">You can import native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="3ffc7-145">Para uma instrução INSERT... SELECT \* FROM OPENROWSET(BULK...), é necessário especificar o formato dos dados em um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-145">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="3ffc7-146">O formato nativo tem suporte nas seguintes opções de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="3ffc7-146">Native format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="3ffc7-147">Comando</span><span class="sxs-lookup"><span data-stu-id="3ffc7-147">Command</span></span>|<span data-ttu-id="3ffc7-148">Opção</span><span class="sxs-lookup"><span data-stu-id="3ffc7-148">Option</span></span>|<span data-ttu-id="3ffc7-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="3ffc7-149">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="3ffc7-150">**bcp**</span><span class="sxs-lookup"><span data-stu-id="3ffc7-150">**bcp**</span></span>|<span data-ttu-id="3ffc7-151">**-n**</span><span class="sxs-lookup"><span data-stu-id="3ffc7-151">**-n**</span></span>|<span data-ttu-id="3ffc7-152">Faz com que o utilitário **bcp** use os tipos de dados nativos dos dados. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3ffc7-152">Causes the **bcp** utility to use the native data types of the data.<sup>1</sup></span></span>|  
|<span data-ttu-id="3ffc7-153">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="3ffc7-153">BULK INSERT</span></span>|<span data-ttu-id="3ffc7-154">DataFileType **= '** nativo **'**</span><span class="sxs-lookup"><span data-stu-id="3ffc7-154">DATAFILETYPE **='** native **'**</span></span>|<span data-ttu-id="3ffc7-155">Usa o tipo de dados nativo ou nativo largo.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-155">Uses the native or wide native data types of the data.</span></span> <span data-ttu-id="3ffc7-156">Observe que DATAFILETYPE não será necessário se um arquivo de formato especificar os tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-156">Note that DATAFILETYPE is not needed if a format file specifies the data types.</span></span>|  
  
 <span data-ttu-id="3ffc7-157"><sup>1</sup> para carregar dados nativos (**-n**) em um formato compatível com versões anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clientes, use a opção **-V** .</span><span class="sxs-lookup"><span data-stu-id="3ffc7-157"><sup>1</sup> To load native (**-n**) data to a format compatible with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients, use the **-V** switch.</span></span> <span data-ttu-id="3ffc7-158">Para obter mais informações, consulte [Importar dados de formato de caractere e nativo de versões anteriores do SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3ffc7-158">For more information, see [Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span></span>  
  
 <span data-ttu-id="3ffc7-159">Para obter mais informações, consulte [Utilitário bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) ou [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3ffc7-159">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3ffc7-160">Como alternativa, você pode especificar a formatação por campo, em um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-160">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="3ffc7-161">Para obter mais informações, consulte [Arquivos de formato para importação ou exportação de dados &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3ffc7-161">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3ffc7-162">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3ffc7-162">Examples</span></span>  
 <span data-ttu-id="3ffc7-163">Os exemplos a seguir demonstram como exportar em massa dados nativos com o **bcp** e importar em massa os mesmos dados com BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-163">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="3ffc7-164">Tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="3ffc7-164">Sample Table</span></span>  
 <span data-ttu-id="3ffc7-165">Os exemplos exigem que uma tabela denominada **myTestNativeData** seja criada no banco de dados de exemplo **AdventureWorks** no esquema **dbo**.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-165">The examples require that a table named **myTestNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="3ffc7-166">Antes de executar os exemplos, é necessário criar essa tabela.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-166">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="3ffc7-167">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute:</span><span class="sxs-lookup"><span data-stu-id="3ffc7-167">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="3ffc7-168">Para preencher esta tabela e exibir o conteúdo resultante, execute as seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="3ffc7-168">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="3ffc7-169">Usando o bcp para exportar dados nativos em massa</span><span class="sxs-lookup"><span data-stu-id="3ffc7-169">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="3ffc7-170">Para exportar dados da tabela para o arquivo de dados, use **bcp** com a opção **out** e os seguintes qualificadores:</span><span class="sxs-lookup"><span data-stu-id="3ffc7-170">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="3ffc7-171">Qualificadores</span><span class="sxs-lookup"><span data-stu-id="3ffc7-171">Qualifiers</span></span>|<span data-ttu-id="3ffc7-172">Descrição</span><span class="sxs-lookup"><span data-stu-id="3ffc7-172">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="3ffc7-173">**-n**</span><span class="sxs-lookup"><span data-stu-id="3ffc7-173">**-n**</span></span>|<span data-ttu-id="3ffc7-174">Especifica tipos de dados nativos.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-174">Specifies native data types.</span></span>|  
|<span data-ttu-id="3ffc7-175">**-T**</span><span class="sxs-lookup"><span data-stu-id="3ffc7-175">**-T**</span></span>|<span data-ttu-id="3ffc7-176">Especifica que o utilitário **bcp** se conecta ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com uma conexão confiável usando segurança integrada.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-176">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="3ffc7-177">Se **-T** não for especificado, será necessário especificar **-U** e **-P** para que o logon tenha êxito.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-177">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="3ffc7-178">O exemplo a seguir exporta dados em massa no formato nativo da tabela `myTestNativeData` para um novo arquivo de dados denominado arquivo de dados `myTestNativeData-n.Dat`.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-178">The following example bulk exports data in native format from the `myTestNativeData` table into a new data file named `myTestNativeData-n.Dat` data file.</span></span> <span data-ttu-id="3ffc7-179">No prompt de comando do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="3ffc7-179">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestNativeData out C:\myTestNativeData-n.Dat -n -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="3ffc7-180">Usando BULK INSERT para importar dados nativos em massa</span><span class="sxs-lookup"><span data-stu-id="3ffc7-180">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="3ffc7-181">Os exemplos a seguir usam BULK INSERT para importar os dados no arquivo de dados `myTestNativeData-n.Dat` na tabela `myTestNativeData`.</span><span class="sxs-lookup"><span data-stu-id="3ffc7-181">The following example uses BULK INSERT to import the data in the `myTestNativeData-n.Dat` data file into the `myTestNativeData` table.</span></span> <span data-ttu-id="3ffc7-182">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute:</span><span class="sxs-lookup"><span data-stu-id="3ffc7-182">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestNativeData   
    FROM 'C:\myTestNativeData-n.Dat'   
   WITH (DATAFILETYPE='native');   
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3ffc7-183">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="3ffc7-183">Related Tasks</span></span>  
 <span data-ttu-id="3ffc7-184">**Para usar formatos de dados para importação ou exportação em massa**</span><span class="sxs-lookup"><span data-stu-id="3ffc7-184">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="3ffc7-185">Importar dados de formato de caractere e nativo de versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ffc7-185">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="3ffc7-186">Usar o formato de caractere para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3ffc7-186">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="3ffc7-187">Usar o formato de caractere Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3ffc7-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="3ffc7-188">Usar o formato nativo Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3ffc7-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="3ffc7-189">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ffc7-189">See Also</span></span>  
 <span data-ttu-id="3ffc7-190">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="3ffc7-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="3ffc7-191">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3ffc7-191">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="3ffc7-192">[Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3ffc7-192">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="3ffc7-193">[sql_variant &#40;Transact-SQL&#41;](/sql/t-sql/data-types/sql-variant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3ffc7-193">[sql_variant &#40;Transact-SQL&#41;](/sql/t-sql/data-types/sql-variant-transact-sql) </span></span>  
 <span data-ttu-id="3ffc7-194">[Importar dados de formato de caractere e nativo de versões anteriores do SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3ffc7-194">[Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span></span>  
 <span data-ttu-id="3ffc7-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3ffc7-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="3ffc7-196">Usar o formato nativo Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3ffc7-196">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
  
