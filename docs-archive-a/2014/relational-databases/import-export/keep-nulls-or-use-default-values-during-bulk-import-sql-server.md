---
title: Manter valores nulos ou usar os valores padrão durante a importação em massa (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], null values
- bulk importing [SQL Server], default values
- data formats [SQL Server], null values
- bulk rowset providers [SQL Server]
- bcp utility [SQL Server], null values
- BULK INSERT statement
- default values
- OPENROWSET function, bulk importing
- data formats [SQL Server], default values
ms.assetid: 6b91d762-337b-4345-a159-88abb3e64a81
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 856aa12f6ad5e5094324e0df65941bc63d611451
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685172"
---
# <a name="keep-nulls-or-use-default-values-during-bulk-import-sql-server"></a><span data-ttu-id="b57b3-102">Manter valores nulos ou use os valores padrão durante a importação em massa (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b57b3-102">Keep Nulls or Use Default Values During Bulk Import (SQL Server)</span></span>
  <span data-ttu-id="b57b3-103">Por padrão, quando os dados são importados para uma tabela, o comando **bcp** e a instrução BULK INSERT observam os padrões definidos para as colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="b57b3-103">By default, when data is imported into a table, the **bcp** command and BULK INSERT statement observe any defaults that are defined for the columns in the table.</span></span> <span data-ttu-id="b57b3-104">Por exemplo, se houver um campo nulo em um arquivo de dados, o valor padrão para a coluna será carregado no campo nulo.</span><span class="sxs-lookup"><span data-stu-id="b57b3-104">For example, if there is a null field in a data file, the default value for the column is loaded instead.</span></span> <span data-ttu-id="b57b3-105">O comando **bcp** e a instrução BULK INSERT permitem que você especifique a retenção de campos nulos.</span><span class="sxs-lookup"><span data-stu-id="b57b3-105">The **bcp** command and BULK INSERT statement both allow you to specify that nulls values be retained.</span></span>  
  
 <span data-ttu-id="b57b3-106">Em contraste, uma instrução INSERT regular retém o valor nulo em vez de inserir um valor padrão.</span><span class="sxs-lookup"><span data-stu-id="b57b3-106">In contrast, a regular INSERT statement retains the null value instead of inserting a default value.</span></span> <span data-ttu-id="b57b3-107">A instrução INSERT ... SELECT \* FROM OPENROWSET(BULK...) fornece o mesmo comportamento básico de INSERT regular, mas, além disso, dá suporte a uma dica de tabela para inserir os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="b57b3-107">The INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement provides the same basic behavior as regular INSERT but additionally supports a table hint for inserting the default values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b57b3-108">Para arquivos de formato de exemplo que ignoram uma coluna de tabela, veja [Usar um arquivo de formato para ignorar uma coluna de tabela &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b57b3-108">For sample format files that skip a table column, see [Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md).</span></span>  
  
## <a name="sample-table-and-data-file"></a><span data-ttu-id="b57b3-109">Tabela e arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="b57b3-109">Sample Table and Data File</span></span>  
 <span data-ttu-id="b57b3-110">Para executar os exemplos neste tópico, é necessário criar uma tabela e um arquivo de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="b57b3-110">To run the examples in this topic, you need to create a sample table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="b57b3-111">Tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="b57b3-111">Sample Table</span></span>  
 <span data-ttu-id="b57b3-112">Os exemplos requerem que uma tabela denominada **MyTestDefaultCol2** seja criada no banco de dados de exemplo **AdventureWorks** no esquema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="b57b3-112">The examples require that a table named **MyTestDefaultCol2** be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="b57b3-113">Para criar esta tabela, no Editor de Consultas do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , execute:</span><span class="sxs-lookup"><span data-stu-id="b57b3-113">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE MyTestDefaultCol2   
(Col1 smallint,  
Col2 nvarchar(50) DEFAULT 'Default value of Col2',  
Col3 nvarchar(50)   
);  
GO  
  
```  
  
 <span data-ttu-id="b57b3-114">Observe que a segunda coluna de tabela, `Col2`, tem um valor padrão.</span><span class="sxs-lookup"><span data-stu-id="b57b3-114">Notice that the second table column, `Col2`, has a default value.</span></span>  
  
### <a name="sample-format-file"></a><span data-ttu-id="b57b3-115">Arquivo de formato de exemplo</span><span class="sxs-lookup"><span data-stu-id="b57b3-115">Sample Format File</span></span>  
 <span data-ttu-id="b57b3-116">Alguns dos exemplos de importação em massa usam um formato de arquivo não XML, `MyTestDefaultCol2-f-c.Fmt` que correspondem exatamente à tabela `MyTestDefaultCol2`.</span><span class="sxs-lookup"><span data-stu-id="b57b3-116">Some of the bulk-import examples use a non-XML format file, `MyTestDefaultCol2-f-c.Fmt` that corresponds exactly to the `MyTestDefaultCol2` table.</span></span> <span data-ttu-id="b57b3-117">Para criar esse arquivo de formato, no prompt de comando do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="b57b3-117">To create this format file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 format nul -c -f C:\MyTestDefaultCol2-f-c.Fmt -t, -r\n -T  
  
```  
  
 <span data-ttu-id="b57b3-118">Para obter mais informações sobre como criar arquivos de formato, veja [Criar um arquivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b57b3-118">For more information about creating format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="b57b3-119">Arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="b57b3-119">Sample Data File</span></span>  
 <span data-ttu-id="b57b3-120">O exemplo usa um arquivo de dados de exemplo, `MyTestEmptyField2-c.Dat`, que não contém nenhum valor no segundo campo.</span><span class="sxs-lookup"><span data-stu-id="b57b3-120">The example uses a sample data file, `MyTestEmptyField2-c.Dat`, that contains no values in the second field.</span></span> <span data-ttu-id="b57b3-121">O arquivo de dados `MyTestEmptyField2-c.Dat` contém os registros a seguir.</span><span class="sxs-lookup"><span data-stu-id="b57b3-121">The `MyTestEmptyField2-c.Dat` data file contains the following records.</span></span>  
  
```  
1,,DataField3  
2,,DataField3  
  
```  
  
## <a name="keeping-null-values-with-bcp-or-bulk-insert"></a><span data-ttu-id="b57b3-122">Mantendo valores nulos com bcp ou BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="b57b3-122">Keeping Null Values with bcp or BULK INSERT</span></span>  
 <span data-ttu-id="b57b3-123">Os qualificadores a seguir especificam que um campo vazio no arquivo de dados retém seu valor nulo durante a operação de importação em massa, em vez de herdar um valor padrão (se houver) para as colunas de tabela.</span><span class="sxs-lookup"><span data-stu-id="b57b3-123">The following qualifiers specify that an empty field in the data file retains its null value during the bulk-import operation, rather than inheriting a default value (if any) for the table columns.</span></span>  
  
|<span data-ttu-id="b57b3-124">Comando</span><span class="sxs-lookup"><span data-stu-id="b57b3-124">Command</span></span>|<span data-ttu-id="b57b3-125">Qualificador</span><span class="sxs-lookup"><span data-stu-id="b57b3-125">Qualifier</span></span>|<span data-ttu-id="b57b3-126">Tipo de qualificador</span><span class="sxs-lookup"><span data-stu-id="b57b3-126">Qualifier type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="b57b3-127">**bcp**</span><span class="sxs-lookup"><span data-stu-id="b57b3-127">**bcp**</span></span>|`-k`|<span data-ttu-id="b57b3-128">Opção</span><span class="sxs-lookup"><span data-stu-id="b57b3-128">Switch</span></span>|  
|<span data-ttu-id="b57b3-129">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="b57b3-129">BULK INSERT</span></span>|<span data-ttu-id="b57b3-130">KEEPNULLS<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b57b3-130">KEEPNULLS<sup>1</sup></span></span>|<span data-ttu-id="b57b3-131">Argumento</span><span class="sxs-lookup"><span data-stu-id="b57b3-131">Argument</span></span>|  
  
 <span data-ttu-id="b57b3-132"><sup>1</sup> para BULK INSERT, se os valores padrão não estiverem disponíveis, a coluna da tabela deverá ser definida para permitir valores nulos.</span><span class="sxs-lookup"><span data-stu-id="b57b3-132"><sup>1</sup> For BULK INSERT, if default values are not available, the table column must be defined to allow null values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b57b3-133">Esses qualificadores desabilitam a verificação de definições DEFAULT em uma tabela por esses comandos de importação em massa.</span><span class="sxs-lookup"><span data-stu-id="b57b3-133">These qualifiers disable checking of DEFAULT definitions on a table by these bulk-import commands.</span></span> <span data-ttu-id="b57b3-134">No entanto, para qualquer instrução INSERT simultânea, são previstas definições DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="b57b3-134">However, for any concurrent INSERT statements, DEFAULT definitions are expected.</span></span>  
  
 <span data-ttu-id="b57b3-135">Para obter mais informações, veja [Utilitário bcp](../../tools/bcp-utility.md) e [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b57b3-135">For more information, see [bcp Utility](../../tools/bcp-utility.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b57b3-136">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b57b3-136">Examples</span></span>  
 <span data-ttu-id="b57b3-137">Os exemplos nesta seção efetuam a importação em massa usando **bcp** ou BULK INSERT e mantêm valores nulos.</span><span class="sxs-lookup"><span data-stu-id="b57b3-137">The examples in this section bulk import using **bcp** or BULK INSERT and keep null values.</span></span>  
  
 <span data-ttu-id="b57b3-138">A segunda coluna de tabela, **Col2**, tem um valor padrão.</span><span class="sxs-lookup"><span data-stu-id="b57b3-138">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="b57b3-139">O campo correspondente do arquivo de dados contém uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="b57b3-139">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="b57b3-140">Por padrão, quando **bcp** ou BULK INSERT é usado para importar dados desse arquivo de dados para a tabela **MyTestDefaultCol2** , o valor padrão de **Col2** é inserido, produzindo o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="b57b3-140">By default, when **bcp** or BULK INSERT is used to import data from this data file into the **MyTestDefaultCol2** table, the default value of **Col2** is inserted, producing the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`Default value of Col2`|`DataField3`|  
|`2`|`Default value of Col2`|`DataField3`|  
  
 <span data-ttu-id="b57b3-141">Para inserir " `NULL` " em vez de " `Default value of Col2` ", você precisa usar a `-k` opção switch ou KEEPNULL, conforme demonstrado nos exemplos de **bcp** e BULK INSERT a seguir.</span><span class="sxs-lookup"><span data-stu-id="b57b3-141">To insert "`NULL`" instead of "`Default value of Col2`", you need to use the `-k` switch or KEEPNULL option, as demonstrated in the following **bcp** and BULK INSERT examples.</span></span>  
  
#### <a name="using-bcp-and-keeping-null-values"></a><span data-ttu-id="b57b3-142">Usando bcp e mantendo valores nulos</span><span class="sxs-lookup"><span data-stu-id="b57b3-142">Using bcp and Keeping Null Values</span></span>  
 <span data-ttu-id="b57b3-143">O exemplo a seguir demonstra como manter valores nulos em um comando **bcp** .</span><span class="sxs-lookup"><span data-stu-id="b57b3-143">The following example demonstrates how to keep null values in a **bcp** command.</span></span> <span data-ttu-id="b57b3-144">O comando **bcp** contém as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b57b3-144">The **bcp** command contains the following switches:</span></span>  
  
|<span data-ttu-id="b57b3-145">Opção</span><span class="sxs-lookup"><span data-stu-id="b57b3-145">Switch</span></span>|<span data-ttu-id="b57b3-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="b57b3-146">Description</span></span>|  
|------------|-----------------|  
|`-f`|<span data-ttu-id="b57b3-147">Especifica que o comando está usando um arquivo de formato...</span><span class="sxs-lookup"><span data-stu-id="b57b3-147">Specifies that the command is using a format file..</span></span>|  
|`-k`|<span data-ttu-id="b57b3-148">Especifica que colunas vazias devem reter um valor nulo durante a operação, em vez de qualquer valor padrão nas colunas inseridas.</span><span class="sxs-lookup"><span data-stu-id="b57b3-148">Specifies that empty columns should retain a null value during the operation, rather than have any default values for the columns inserted.</span></span>|  
|`-T`|<span data-ttu-id="b57b3-149">Especifica que o utilitário bcp faz conexão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio de uma conexão confiável.</span><span class="sxs-lookup"><span data-stu-id="b57b3-149">Specifies that the bcp utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="b57b3-150">No prompt de comando do Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="b57b3-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 in C:\MyTestEmptyField2-c.Dat -f C:\MyTestDefaultCol2-f-c.Fmt -k -T  
  
```  
  
#### <a name="using-bulk-insert-and-keeping-null-values"></a><span data-ttu-id="b57b3-151">Usando BULK INSERT e mantendo valores nulos</span><span class="sxs-lookup"><span data-stu-id="b57b3-151">Using BULK INSERT and Keeping Null Values</span></span>  
 <span data-ttu-id="b57b3-152">O exemplo a seguir demonstra como usar a opção KEEPNULLS em uma instrução BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="b57b3-152">The following example demonstrates how to use the KEEPNULLS option in a BULK INSERT statement.</span></span> <span data-ttu-id="b57b3-153">De uma ferramenta de consulta, como o Editor de Consultas do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], execute:</span><span class="sxs-lookup"><span data-stu-id="b57b3-153">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT MyTestDefaultCol2  
   FROM 'C:\MyTestEmptyField2-c.Dat'  
   WITH (  
      DATAFILETYPE = 'char',  
      FIELDTERMINATOR = ',',  
      KEEPNULLS  
   );  
GO  
  
```  
  
## <a name="keeping-default-values-with-insert--select--from-openrowsetbulk"></a><span data-ttu-id="b57b3-154">Mantendo valores padrão com INSERT... SELECIONAR \* DE OPENROWSET (BULK...)</span><span class="sxs-lookup"><span data-stu-id="b57b3-154">Keeping Default Values with INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
 <span data-ttu-id="b57b3-155">Por padrão, todas as colunas não especificadas na operação de carregamento em massa são definidas como NULL por INSERT... SELECIONE \* DE OPENROWSET (BULK...). No entanto, você pode especificar que, para um campo vazio no arquivo de dados, a coluna da tabela correspondente use seu valor padrão (se houver).</span><span class="sxs-lookup"><span data-stu-id="b57b3-155">By default, any columns that are not specified in the bulk-load operation are set to NULL by INSERT ... SELECT \* FROM OPENROWSET(BULK...). However, you can specify that for an empty field in the data file, the corresponding table column uses its default value (if any).</span></span> <span data-ttu-id="b57b3-156">Para usar valores padrão, especifique a seguinte dica de tabela:</span><span class="sxs-lookup"><span data-stu-id="b57b3-156">To use default values, specify the following table hint:</span></span>  
  
|<span data-ttu-id="b57b3-157">Comando</span><span class="sxs-lookup"><span data-stu-id="b57b3-157">Command</span></span>|<span data-ttu-id="b57b3-158">Qualificador</span><span class="sxs-lookup"><span data-stu-id="b57b3-158">Qualifier</span></span>|<span data-ttu-id="b57b3-159">Tipo de qualificador</span><span class="sxs-lookup"><span data-stu-id="b57b3-159">Qualifier Type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="b57b3-160">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="b57b3-160">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="b57b3-161">WITH(KEEPDEFAULTS)</span><span class="sxs-lookup"><span data-stu-id="b57b3-161">WITH(KEEPDEFAULTS)</span></span>|<span data-ttu-id="b57b3-162">Dica de tabela</span><span class="sxs-lookup"><span data-stu-id="b57b3-162">Table hint</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="b57b3-163">para obter mais informações, consulte [inserir &#40;&#41;Transact-SQL ](/sql/t-sql/statements/insert-transact-sql), [selecione &#40;&#41;Transact-sql ](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)e [dicas de tabela &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span><span class="sxs-lookup"><span data-stu-id="b57b3-163">for more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b57b3-164">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b57b3-164">Examples</span></span>  
 <span data-ttu-id="b57b3-165">O seguinte inserir... SELECT \* do exemplo de OPENROWSET (BULK...) importa dados em massa e mantém os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="b57b3-165">The following INSERT ... SELECT \* FROM OPENROWSET(BULK...) example bulk imports data and keeps the default values.</span></span>  
  
 <span data-ttu-id="b57b3-166">Para executar os exemplos, é necessário criar a tabela de exemplo **MyTestDefaultCol2** , o arquivo de dados `MyTestEmptyField2-c.Dat` e usar um arquivo de formato `MyTestDefaultCol2-f-c.Fmt`.</span><span class="sxs-lookup"><span data-stu-id="b57b3-166">To run the examples, you need to create the **MyTestDefaultCol2** sample table, the `MyTestEmptyField2-c.Dat` data file, and use a format file, `MyTestDefaultCol2-f-c.Fmt`.</span></span> <span data-ttu-id="b57b3-167">Para obter informações sobre como criar esses exemplos, consulte "Tabela e arquivo de dados de exemplo", anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="b57b3-167">For information on creating these samples, see "Sample Table and Data File," earlier in this topic.</span></span>  
  
 <span data-ttu-id="b57b3-168">A segunda coluna de tabela, **Col2**, tem um valor padrão.</span><span class="sxs-lookup"><span data-stu-id="b57b3-168">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="b57b3-169">O campo correspondente do arquivo de dados contém uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="b57b3-169">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="b57b3-170">Quando inserir... SELECIONAR \* de OPENROWSET (bulk...) importar os campos desse arquivo de dados para a tabela **MyTestDefaultCol2** , por padrão, NULL é inserido em **Col2** em vez do valor padrão.</span><span class="sxs-lookup"><span data-stu-id="b57b3-170">When INSERT ... SELECT \* FROM OPENROWSET(BULK...) import the fields of this data file into the **MyTestDefaultCol2** table, by default, NULL is inserted into **Col2** instead of the default value.</span></span> <span data-ttu-id="b57b3-171">Esse comportamento padrão produz o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="b57b3-171">This default behavior produces the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`NULL`|`DataField3`|  
|`2`|`NULL`|`DataField3`|  
  
 <span data-ttu-id="b57b3-172">Para inserir o valor padrão "`Default value of Col2`" no lugar de "`NULL`" é necessário usar a dica de tabela KEEPDEFAULTS, como demonstrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="b57b3-172">To insert the default value, "`Default value of Col2`", instead of "`NULL`", you need to use KEEPDEFAULTS table hint, as demonstrated in the following example.</span></span> <span data-ttu-id="b57b3-173">De uma ferramenta de consulta, como o Editor de Consultas do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], execute:</span><span class="sxs-lookup"><span data-stu-id="b57b3-173">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
INSERT INTO MyTestDefaultCol2  
    WITH (KEEPDEFAULTS)  
    SELECT *  
      FROM OPENROWSET(BULK  'C:\MyTestEmptyField2-c.Dat',  
      FORMATFILE='C:\MyTestDefaultCol2-f-c.Fmt'       
      ) as t1 ;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b57b3-174">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="b57b3-174">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b57b3-175">Manter valores de identidade ao importar dados em massa &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-175">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="b57b3-176">Preparar dados para exportar ou importar em massa &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-176">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="b57b3-177">**Para usar um arquivo de formato**</span><span class="sxs-lookup"><span data-stu-id="b57b3-177">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="b57b3-178">Criar um arquivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-178">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="b57b3-179">Usar um arquivo de formato para importação em massa de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-179">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="b57b3-180">Usar um arquivo de formato para mapear colunas de uma tabela para campos de arquivo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-180">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="b57b3-181">Usar um arquivo de formato para ignorar um campo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-181">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="b57b3-182">Usar um arquivo de formato para ignorar uma coluna de tabela &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-182">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="b57b3-183">**Para usar formatos de dados para importação ou exportação em massa**</span><span class="sxs-lookup"><span data-stu-id="b57b3-183">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="b57b3-184">Importar dados de formato de caractere e nativo de versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="b57b3-184">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="b57b3-185">Usar o formato de caractere para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-185">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="b57b3-186">Usar o formato nativo para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-186">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="b57b3-187">Usar o formato de caractere Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="b57b3-188">Usar o formato nativo Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="b57b3-189">**Para especificar formatos de dados para compatibilidade usando bcp**</span><span class="sxs-lookup"><span data-stu-id="b57b3-189">**To specify data formats for compatibility when using bcp**</span></span>  
  
-   [<span data-ttu-id="b57b3-190">Especificar terminadores de campo e linha &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-190">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="b57b3-191">Especificar o tamanho de prefixo em arquivos de dados usando bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-191">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="b57b3-192">Especificar tipo de armazenamento de arquivo usando bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-192">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="b57b3-193">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b57b3-193">See Also</span></span>  
 <span data-ttu-id="b57b3-194">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b57b3-194">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="b57b3-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b57b3-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="b57b3-196">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b57b3-196">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="b57b3-197">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b57b3-197">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="b57b3-198">Dicas de tabela &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b57b3-198">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
