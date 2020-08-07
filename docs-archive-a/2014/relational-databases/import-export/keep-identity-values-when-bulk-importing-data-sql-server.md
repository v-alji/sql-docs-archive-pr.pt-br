---
title: Manter valores de identidade ao importar dados em massa (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- identity values [SQL Server], bulk imports
- data formats [SQL Server], identity values
- bulk importing [SQL Server], identity values
ms.assetid: 45894a3f-2d8a-4edd-9568-afa7d0d3061f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07f6714f27f60afda91134034509ff439d92f071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576379"
---
# <a name="keep-identity-values-when-bulk-importing-data-sql-server"></a><span data-ttu-id="7f786-102">Manter valores de identidade ao importar dados em massa (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f786-102">Keep Identity Values When Bulk Importing Data (SQL Server)</span></span>
  <span data-ttu-id="7f786-103">Os arquivos de dados que contêm valores de identidade podem ser importados em massa para uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f786-103">Data files that contain identity values can be bulk imported into an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7f786-104">Por padrão, os valores da coluna de identidade do arquivo de dados que é importado são ignorados e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atribui valores exclusivos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f786-104">By default, the values for the identity column in the data file that is imported are ignored and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns unique values automatically.</span></span> <span data-ttu-id="7f786-105">Os valores exclusivos são baseados nos valores de semente e incremento que são especificados durante a criação da tabela.</span><span class="sxs-lookup"><span data-stu-id="7f786-105">The unique values are based on the seed and increment values that are specified during table creation.</span></span>  
  
 <span data-ttu-id="7f786-106">Se o arquivo de dados não contiver valores para a coluna de identificador na tabela, use um arquivo de formato para especificar que a coluna de identificador na tabela deve ser ignorada durante a importação dos dados.</span><span class="sxs-lookup"><span data-stu-id="7f786-106">If the data file does not contain values for the identifier column in the table, use a format file to specify that the identifier column in the table should be skipped when importing data.</span></span> <span data-ttu-id="7f786-107">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atribui automaticamente valores exclusivos para a coluna.</span><span class="sxs-lookup"><span data-stu-id="7f786-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns unique values for the column automatically.</span></span>  
  
 <span data-ttu-id="7f786-108">Para impedir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a atribuição de valores de identidade durante a importação em massa de linhas de dados, use o qualificador de comando manter identidade apropriado.</span><span class="sxs-lookup"><span data-stu-id="7f786-108">To prevent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from assigning identity values while bulk importing data rows into a table, use the appropriate keep-identity command qualifier.</span></span> <span data-ttu-id="7f786-109">Quando você especificar um qualificador de manter identidade, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa os valores de identidade no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="7f786-109">When you specify a keep-identity qualifier, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the identity values in the data file.</span></span> <span data-ttu-id="7f786-110">Estes qualificadores são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="7f786-110">These qualifiers are as follows:</span></span>  
  
|<span data-ttu-id="7f786-111">Comando</span><span class="sxs-lookup"><span data-stu-id="7f786-111">Command</span></span>|<span data-ttu-id="7f786-112">Qualificador manter identidade</span><span class="sxs-lookup"><span data-stu-id="7f786-112">Keep-identity qualifier</span></span>|<span data-ttu-id="7f786-113">Tipo de qualificador</span><span class="sxs-lookup"><span data-stu-id="7f786-113">Qualifier type</span></span>|  
|-------------|------------------------------|--------------------|  
|`bcp`|<span data-ttu-id="7f786-114">**-E**</span><span class="sxs-lookup"><span data-stu-id="7f786-114">**-E**</span></span>|<span data-ttu-id="7f786-115">Opção</span><span class="sxs-lookup"><span data-stu-id="7f786-115">Switch</span></span>|  
|<span data-ttu-id="7f786-116">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="7f786-116">BULK INSERT</span></span>|<span data-ttu-id="7f786-117">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="7f786-117">KEEPIDENTITY</span></span>|<span data-ttu-id="7f786-118">Argumento</span><span class="sxs-lookup"><span data-stu-id="7f786-118">Argument</span></span>|  
|<span data-ttu-id="7f786-119">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="7f786-119">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="7f786-120">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="7f786-120">KEEPIDENTITY</span></span>|<span data-ttu-id="7f786-121">Dica de tabela</span><span class="sxs-lookup"><span data-stu-id="7f786-121">Table hint</span></span>|  
  
 <span data-ttu-id="7f786-122">Para obter mais informações, consulte [Utilitário bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) e [Dicas de tabela &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span><span class="sxs-lookup"><span data-stu-id="7f786-122">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f786-123">Para criar um número incrementado automaticamente, que possa ser usado em várias tabelas ou ser chamado de aplicativos, sem referenciar tabelas, consulte [Números de Sequência](../sequence-numbers/sequence-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="7f786-123">To create an automatically incrementing number that can be used in multiple tables or that can be called from applications without referencing any table, see [Sequence Numbers](../sequence-numbers/sequence-numbers.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7f786-124">Exemplos</span><span class="sxs-lookup"><span data-stu-id="7f786-124">Examples</span></span>  
 <span data-ttu-id="7f786-125">Os exemplos neste tópico importam dados em massa usando INSERT... Selecione \* de OPENROWSET (BULK...) e mantendo valores padrão.</span><span class="sxs-lookup"><span data-stu-id="7f786-125">The examples in this topic bulk import data using INSERT ... SELECT \* FROM OPENROWSET(BULK...) and keeping default values.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="7f786-126">Tabela de exemplo</span><span class="sxs-lookup"><span data-stu-id="7f786-126">Sample Table</span></span>  
 <span data-ttu-id="7f786-127">Os exemplos de importação em massa requerem que uma tabela denominada tabela **myTestKeepNulls** seja criada no banco de dados do exemplo **AdventureWorks** no esquema **dbo**.</span><span class="sxs-lookup"><span data-stu-id="7f786-127">The bulk-import examples require that a table named **myTestKeepNulls** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="7f786-128">Para criar essa tabela.</span><span class="sxs-lookup"><span data-stu-id="7f786-128">To create this table.</span></span> <span data-ttu-id="7f786-129">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], execute:</span><span class="sxs-lookup"><span data-stu-id="7f786-129">in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT * INTO HumanResources.myDepartment   
   FROM HumanResources.Department  
      WHERE 1=0;  
GO  
SELECT * FROM HumanResources.myDepartment;  
```  
  
 <span data-ttu-id="7f786-130">A tabela **Departamento`myDepartment` na qual o** é baseado tem IDENTITY_INSERT definido como OFF.</span><span class="sxs-lookup"><span data-stu-id="7f786-130">The **Department** table on which `myDepartment` is based has IDENTITY_INSERT is set to OFF.</span></span> <span data-ttu-id="7f786-131">Portanto, para importar dados para uma coluna de identidade, você deve especificar KEEPIDENTITY ou **-E**.</span><span class="sxs-lookup"><span data-stu-id="7f786-131">Therefore, to import data into an identity column you must specify KEEPIDENTITY or **-E**.</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="7f786-132">Arquivo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="7f786-132">Sample Data File</span></span>  
 <span data-ttu-id="7f786-133">O arquivo de dados usado nos exemplos da importação em massa contém massa de dados exportada da tabela `HumanResources.Department` em formato nativo.</span><span class="sxs-lookup"><span data-stu-id="7f786-133">The data file used in the bulk-import examples contains data bulk exported from the `HumanResources.Department` table in native format.</span></span> <span data-ttu-id="7f786-134">Para criar esse arquivo de dados, no prompt de comando do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="7f786-134">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department out myDepartment-n.Dat -n -T  
```  
  
### <a name="sample-format-file"></a><span data-ttu-id="7f786-135">Arquivo de formato de exemplo</span><span class="sxs-lookup"><span data-stu-id="7f786-135">Sample Format File</span></span>  
 <span data-ttu-id="7f786-136">Estes exemplos de importação em massa usam um arquivo de formato XML, `myDepartment-f-x-n.Xml`, que usa formatos de dados nativos.</span><span class="sxs-lookup"><span data-stu-id="7f786-136">This bulk-import examples use an XML format file, `myDepartment-f-x-n.Xml`, which uses native data formats.</span></span> <span data-ttu-id="7f786-137">Esse exemplo usa `bcp` para criar a geração desse arquivo de formato a partir da tabela `HumanResources.Department` do banco de dados `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="7f786-137">This example uses `bcp` to create to generate this format file from the `HumanResources.Department` table of the `AdventureWorks` database.</span></span> <span data-ttu-id="7f786-138">No prompt de comando do Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="7f786-138">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department format nul -n -x -f myDepartment-f-n-x.Xml -T  
```  
  
 <span data-ttu-id="7f786-139">Para obter mais informações sobre como criar um arquivo de formato, consulte [Criar um arquivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7f786-139">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="a-using-bcp-and-keeping-identity-values"></a><span data-ttu-id="7f786-140">a.</span><span class="sxs-lookup"><span data-stu-id="7f786-140">A.</span></span> <span data-ttu-id="7f786-141">Usando bcp e mantendo valores de identidade</span><span class="sxs-lookup"><span data-stu-id="7f786-141">Using bcp and Keeping Identity Values</span></span>  
 <span data-ttu-id="7f786-142">O exemplo a seguir demonstra como manter valores de identidade ao usar o `bcp` para realizar a importação em massa dos dados.</span><span class="sxs-lookup"><span data-stu-id="7f786-142">The following example demonstrates how to keep identity values when using `bcp` to bulk import data.</span></span> <span data-ttu-id="7f786-143">O comando `bcp` usa o arquivo de formato `myDepartment-f-n-x.Xml` e contém as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7f786-143">The `bcp` command uses the format file, `myDepartment-f-n-x.Xml`, and contains the following switches:</span></span>  
  
|<span data-ttu-id="7f786-144">Qualificadores</span><span class="sxs-lookup"><span data-stu-id="7f786-144">Qualifiers</span></span>|<span data-ttu-id="7f786-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="7f786-145">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="7f786-146">**-E**</span><span class="sxs-lookup"><span data-stu-id="7f786-146">**-E**</span></span>|<span data-ttu-id="7f786-147">Especifica que o valor ou valores de identidade no arquivo de dados serão usados para a coluna de identidade.</span><span class="sxs-lookup"><span data-stu-id="7f786-147">Specifies that identity value or values in the data file are to be used for the identity column.</span></span>|  
|<span data-ttu-id="7f786-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="7f786-148">**-T**</span></span>|<span data-ttu-id="7f786-149">Especifica que o `bcp` utilitário se conecta ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com uma conexão confiável.</span><span class="sxs-lookup"><span data-stu-id="7f786-149">Specifies that the `bcp` utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="7f786-150">No prompt de comando do Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="7f786-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myDepartment in C:\myDepartment-n.Dat -f C:\myDepartment-f-n-x.Xml -E -T  
  
```  
  
### <a name="b-using-bulk-insert-and-keeping-identity-values"></a><span data-ttu-id="7f786-151">B.</span><span class="sxs-lookup"><span data-stu-id="7f786-151">B.</span></span> <span data-ttu-id="7f786-152">Usando BULK INSERT e mantendo valores de identidade</span><span class="sxs-lookup"><span data-stu-id="7f786-152">Using BULK INSERT and Keeping Identity Values</span></span>  
 <span data-ttu-id="7f786-153">Os exemplos a seguir usam BULK INSERT para importar em massa dados do arquivo `myDepartment-c.Dat` na tabela `AdventureWorks.HumanResources.myDepartment` .</span><span class="sxs-lookup"><span data-stu-id="7f786-153">The following example uses BULK INSERT to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="7f786-154">A instrução usa o formato de arquivo `myDepartment-f-n-x.Xml` e inclui a opção de KEEPIDENTITY para assegurar que quaisquer valores de identidade no arquivo de dados são retidos.</span><span class="sxs-lookup"><span data-stu-id="7f786-154">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY option to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="7f786-155">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], execute:</span><span class="sxs-lookup"><span data-stu-id="7f786-155">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
BULK INSERT HumanResources.myDepartment  
   FROM 'C:\myDepartment-n.Dat'  
   WITH (  
      KEEPIDENTITY,  
      FORMATFILE='C:\myDepartment-f-n-x.Xml'  
   );  
GO  
SELECT * FROM HumanResources.myDepartment;  
  
```  
  
### <a name="c-using-openrowset-and-keeping-identity-values"></a><span data-ttu-id="7f786-156">C.</span><span class="sxs-lookup"><span data-stu-id="7f786-156">C.</span></span> <span data-ttu-id="7f786-157">Usando OPENROWSET e mantendo valores de identidade</span><span class="sxs-lookup"><span data-stu-id="7f786-157">Using OPENROWSET and Keeping Identity Values</span></span>  
 <span data-ttu-id="7f786-158">O exemplo abaixo usa o provedor de conjunto de linhas OPENROWSET para importar em massa dados do arquivo `myDepartment-c.Dat` na tabela `AdventureWorks.HumanResources.myDepartment` .</span><span class="sxs-lookup"><span data-stu-id="7f786-158">The following example uses the OPENROWSET bulk rowset provider to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="7f786-159">A instrução usa o formato de arquivo `myDepartment-f-n-x.Xml` e inclui a dica de KEEPIDENTITY para assegurar que quaisquer valores de identidade no arquivo de dados são retidos.</span><span class="sxs-lookup"><span data-stu-id="7f786-159">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY hint to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="7f786-160">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], execute:</span><span class="sxs-lookup"><span data-stu-id="7f786-160">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
  
INSERT INTO HumanResources.myDepartment  
   with (KEEPIDENTITY)  
   (DepartmentID, Name, GroupName, ModifiedDate)  
   SELECT *  
      FROM  OPENROWSET(BULK 'C:\myDepartment-n.Dat',  
      FORMATFILE='C:\myDepartment-f-n-x.Xml') as t1;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7f786-161">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="7f786-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7f786-162">Manter valores nulos ou use os valores padrão durante a importação em massa &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-162">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="7f786-163">Preparar dados para exportar ou importar em massa &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-163">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="7f786-164">**Para usar um arquivo de formato**</span><span class="sxs-lookup"><span data-stu-id="7f786-164">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="7f786-165">Criar um arquivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-165">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="7f786-166">Usar um arquivo de formato para importação em massa de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-166">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="7f786-167">Usar um arquivo de formato para mapear colunas de uma tabela para campos de arquivo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-167">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="7f786-168">Usar um arquivo de formato para ignorar um campo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-168">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="7f786-169">Usar um arquivo de formato para ignorar uma coluna de tabela &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-169">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="7f786-170">**Para usar formatos de dados para importação ou exportação em massa**</span><span class="sxs-lookup"><span data-stu-id="7f786-170">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="7f786-171">Importar dados de formato de caractere e nativo de versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="7f786-171">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="7f786-172">Usar o formato de caractere para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-172">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="7f786-173">Usar o formato nativo para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-173">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="7f786-174">Usar o formato de caractere Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-174">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="7f786-175">Usar o formato nativo Unicode para importar ou exportar dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-175">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="7f786-176">**Para especificar formatos de dados para compatibilidade usando bcp**</span><span class="sxs-lookup"><span data-stu-id="7f786-176">**To specify data formats for compatibility when using bcp**</span></span>  
  
1.  [<span data-ttu-id="7f786-177">Especificar terminadores de campo e linha &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-177">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
2.  [<span data-ttu-id="7f786-178">Especificar o tamanho de prefixo em arquivos de dados usando bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-178">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
3.  [<span data-ttu-id="7f786-179">Especificar tipo de armazenamento de arquivo usando bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-179">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="7f786-180">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7f786-180">See Also</span></span>  
 <span data-ttu-id="7f786-181">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7f786-181">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="7f786-182">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="7f786-182">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="7f786-183">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7f786-183">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="7f786-184">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7f786-184">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="7f786-185">Dicas de tabela &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7f786-185">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
