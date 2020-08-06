---
title: Usar o formato nativo Unicode para importar ou exportar dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- Unicode [SQL Server], bulk importing and exporting
- data formats [SQL Server], Unicode native
ms.assetid: a6213308-f3d5-406e-9029-19d8bb3367f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beae2f836de16dedf3be6d8c196910c53be02266
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685157"
---
# <a name="use-unicode-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="ec002-102">Usar o formato nativo Unicode para importar ou exportar dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ec002-102">Use Unicode Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="ec002-103">O formato nativo Unicode é útil quando as informações precisam ser copiadas de uma instalação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para outra.</span><span class="sxs-lookup"><span data-stu-id="ec002-103">Unicode native format is helpful when information must be copied from one [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation to another.</span></span> <span data-ttu-id="ec002-104">O uso de formato nativo para dados do tipo não caractere economiza tempo, eliminando a conversão desnecessária de tipos de dados de e para o formato de caractere.</span><span class="sxs-lookup"><span data-stu-id="ec002-104">The use of native format for noncharacter data saves time, eliminating unnecessary conversion of data types to and from character format.</span></span> <span data-ttu-id="ec002-105">O uso de formato de caractere Unicode para obter todos os dados de caractere impede a perda de qualquer caractere estendido durante a transferência de dados em massa entre servidores que usam páginas de código diferentes.</span><span class="sxs-lookup"><span data-stu-id="ec002-105">The use of Unicode character format for all character data prevents loss of any extended characters during bulk transfer of data between servers using different code pages.</span></span> <span data-ttu-id="ec002-106">Um arquivo de dados em formato nativo Unicode pode ser lido por qualquer método de importação em massa.</span><span class="sxs-lookup"><span data-stu-id="ec002-106">A data file in Unicode native format can be read by any bulk-import method.</span></span>  
  
 <span data-ttu-id="ec002-107">O formato nativo Unicode é recomendado para transferir em massa dados entre várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando um arquivo de dados com caracteres estendidos DBCS.</span><span class="sxs-lookup"><span data-stu-id="ec002-107">Unicode native format is recommended for the bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span> <span data-ttu-id="ec002-108">Para obter dados do tipo não caractere, o formato nativo Unicode usa tipos de dados nativos (banco de dados).</span><span class="sxs-lookup"><span data-stu-id="ec002-108">For noncharacter data, Unicode native format uses native (database) data types.</span></span> <span data-ttu-id="ec002-109">Para obter dados de caractere, como `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)`e `ntext`, o formato nativo Unicode usa formato de dados de caractere Unicode.</span><span class="sxs-lookup"><span data-stu-id="ec002-109">For character data, such as `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)`, and `ntext`, the Unicode native format uses Unicode character data format.</span></span>  
  
 <span data-ttu-id="ec002-110">Os dados `sql_variant` que são armazenados como um SQLVARIANT em um arquivo de dados do formato nativo Unicode operam da mesma maneira como em um arquivo de dados do formato nativo, exceto os valores `char` e `varchar` que são convertidos para `nchar` e `nvarchar`os quais dobram a quantidade de espaço de armazenamento exigido para as colunas afetadas.</span><span class="sxs-lookup"><span data-stu-id="ec002-110">The `sql_variant` data that is stored as a SQLVARIANT in a Unicode native-format data file operates in the same manner as it does in a native-format data file, except that `char` and `varchar` values are converted to `nchar` and `nvarchar`, which doubles the amount of storage required for the affected columns.</span></span> <span data-ttu-id="ec002-111">Os metadados originais são preservados e os valores são reconvertidos ao `char` original e ao tipo de dados `varchar` quando importados em massa em uma coluna de tabela.</span><span class="sxs-lookup"><span data-stu-id="ec002-111">The original metadata is preserved, and the values are converted back to their original `char` and `varchar` data type when bulk imported into a table column.</span></span>  
  
## <a name="command-options-for-unicode-native-format"></a><span data-ttu-id="ec002-112">Opções de comando para formato nativo Unicode</span><span class="sxs-lookup"><span data-stu-id="ec002-112">Command Options for Unicode Native Format</span></span>  
 <span data-ttu-id="ec002-113">Você pode importar dados de formato nativo Unicode para uma tabela usando **bcp**, BULK INSERT ou INSERT... Selecione \* de OPENROWSET (bulk...). Para um comando **bcp** ou instrução BULK INSERT, você pode especificar o formato de dados na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="ec002-113">You can import Unicode native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="ec002-114">Para uma instrução INSERT... SELECT \* FROM OPENROWSET(BULK...), é necessário especificar o formato dos dados em um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="ec002-114">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="ec002-115">O formato nativo Unicode é suportado pelas seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="ec002-115">Unicode native format is supported by the following options:</span></span>  
  
|<span data-ttu-id="ec002-116">Comando</span><span class="sxs-lookup"><span data-stu-id="ec002-116">Command</span></span>|<span data-ttu-id="ec002-117">Opção</span><span class="sxs-lookup"><span data-stu-id="ec002-117">Option</span></span>|<span data-ttu-id="ec002-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec002-118">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="ec002-119">**bcp**</span><span class="sxs-lookup"><span data-stu-id="ec002-119">**bcp**</span></span>|<span data-ttu-id="ec002-120">**-N**</span><span class="sxs-lookup"><span data-stu-id="ec002-120">**-N**</span></span>|<span data-ttu-id="ec002-121">Faz com que o utilitário **bcp** use o formato nativo Unicode, que usa tipos de dados nativos (banco de dado) para todos os dados não caracteres e formato de dados de caracteres Unicode para todos os dados de caractere (,,,, `char` `nchar` `varchar` `nvarchar` `text` e `ntext` ).</span><span class="sxs-lookup"><span data-stu-id="ec002-121">Causes the **bcp** utility to use the Unicode native format, which uses native (database) data types for all noncharacter data and Unicode character data format for all character (`char`, `nchar`, `varchar`, `nvarchar`, `text`, and `ntext`) data.</span></span>|  
|<span data-ttu-id="ec002-122">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="ec002-122">BULK INSERT</span></span>|<span data-ttu-id="ec002-123">DataFileType **= '** widenative **'**</span><span class="sxs-lookup"><span data-stu-id="ec002-123">DATAFILETYPE **='** widenative **'**</span></span>|<span data-ttu-id="ec002-124">Usa o formato de caractere nativo Unicode na importação de dados em massa.</span><span class="sxs-lookup"><span data-stu-id="ec002-124">Use Unicode native format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="ec002-125">Para obter mais informações, consulte [Utilitário bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) ou [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ec002-125">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec002-126">Como alternativa, você pode especificar a formatação por campo, em um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="ec002-126">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="ec002-127">Para obter mais informações, consulte [Arquivos de formato para importação ou exportação de dados &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ec002-127">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ec002-128">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ec002-128">Examples</span></span>  
 <span data-ttu-id="ec002-129">Os exemplos a seguir demonstram como exportar em massa dados nativos com o **bcp** e importar em massa os mesmos dados com BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="ec002-129">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="ec002-130">Tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="ec002-130">Sample Table</span></span>  
 <span data-ttu-id="ec002-131">Os exemplos exigem que seja criada uma tabela denominada **myTestUniNativeData** no banco de dados de exemplo **AdventureWorks** sob o esquema **dbo**.</span><span class="sxs-lookup"><span data-stu-id="ec002-131">The examples require that a table named **myTestUniNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="ec002-132">Antes de executar os exemplos, é necessário criar essa tabela.</span><span class="sxs-lookup"><span data-stu-id="ec002-132">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="ec002-133">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute:</span><span class="sxs-lookup"><span data-stu-id="ec002-133">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestUniNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="ec002-134">Para preencher esta tabela e exibir o conteúdo resultante, execute as seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="ec002-134">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="ec002-135">Usando o bcp para exportar dados nativos em massa</span><span class="sxs-lookup"><span data-stu-id="ec002-135">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="ec002-136">Para exportar dados da tabela para o arquivo de dados, use **bcp** com a opção **out** e os seguintes qualificadores:</span><span class="sxs-lookup"><span data-stu-id="ec002-136">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="ec002-137">Qualificadores</span><span class="sxs-lookup"><span data-stu-id="ec002-137">Qualifiers</span></span>|<span data-ttu-id="ec002-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec002-138">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="ec002-139">**-N**</span><span class="sxs-lookup"><span data-stu-id="ec002-139">**-N**</span></span>|<span data-ttu-id="ec002-140">Especifica tipos de dados nativos.</span><span class="sxs-lookup"><span data-stu-id="ec002-140">Specifies native data types.</span></span>|  
|<span data-ttu-id="ec002-141">**-T**</span><span class="sxs-lookup"><span data-stu-id="ec002-141">**-T**</span></span>|<span data-ttu-id="ec002-142">Especifica que o utilitário **bcp** se conecta ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com uma conexão confiável usando segurança integrada.</span><span class="sxs-lookup"><span data-stu-id="ec002-142">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="ec002-143">Se **-T** não for especificado, será necessário especificar **-U** e **-P** para que o logon tenha êxito.</span><span class="sxs-lookup"><span data-stu-id="ec002-143">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="ec002-144">O exemplo a seguir exporta dados em massa no formato nativo da tabela `myTestUniNativeData` para um novo arquivo de dados denominado arquivo de dados `myTestUniNativeData-N.Dat`.</span><span class="sxs-lookup"><span data-stu-id="ec002-144">The following example bulk exports data in native format from the `myTestUniNativeData` table into a new data file named `myTestUniNativeData-N.Dat` data file.</span></span> <span data-ttu-id="ec002-145">No prompt de comando do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="ec002-145">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestUniNativeData out C:\myTestUniNativeData-N.Dat -N -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="ec002-146">Usando BULK INSERT para importar dados nativos em massa</span><span class="sxs-lookup"><span data-stu-id="ec002-146">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="ec002-147">Os exemplos a seguir usam BULK INSERT para importar os dados no arquivo de dados `myTestUniNativeData-N.Dat` na tabela `myTestUniNativeData`.</span><span class="sxs-lookup"><span data-stu-id="ec002-147">The following example uses BULK INSERT to import the data in the `myTestUniNativeData-N.Dat` data file into the `myTestUniNativeData` table.</span></span> <span data-ttu-id="ec002-148">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute:</span><span class="sxs-lookup"><span data-stu-id="ec002-148">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestUniNativeData   
    FROM 'C:\myTestUniNativeData-N.Dat'   
   WITH (DATAFILETYPE='widenative');   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ec002-149">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="ec002-149">Related Tasks</span></span>  
 <span data-ttu-id="ec002-150">**Para usar formatos de dados para importação ou exportação em massa**</span><span class="sxs-lookup"><span data-stu-id="ec002-150">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="ec002-151">Importar dados de formato de caractere e nativo de versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ec002-151">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="ec002-152">Usar o formato de caractere para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec002-152">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="ec002-153">Usar o formato nativo para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec002-153">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="ec002-154">Usar o formato de caractere Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ec002-154">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ec002-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ec002-155">See Also</span></span>  
 <span data-ttu-id="ec002-156">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ec002-156">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="ec002-157">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec002-157">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="ec002-158">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec002-158">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="ec002-159">Tipos de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec002-159">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
