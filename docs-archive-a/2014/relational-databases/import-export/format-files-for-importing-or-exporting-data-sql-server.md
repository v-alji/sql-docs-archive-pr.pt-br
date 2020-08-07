---
title: Arquivos de formato para importação ou exportação de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], format files
- bulk importing [SQL Server], format files
- format files [SQL Server]
ms.assetid: b7b97d68-4336-4091-aee4-1941fab568e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1143690f0322fef2612fde51eebcb7427ee237ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576388"
---
# <a name="format-files-for-importing-or-exporting-data-sql-server"></a><span data-ttu-id="71d64-102">Arquivos de formato para importação ou exportação de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="71d64-102">Format Files for Importing or Exporting Data (SQL Server)</span></span>
  <span data-ttu-id="71d64-103">Na importação de dados em massa para uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou na exportação em massa de dados de uma tabela, você pode usar um *arquivo de formato* para armazenar todas as informações necessárias para exportar ou importar dados em massa.</span><span class="sxs-lookup"><span data-stu-id="71d64-103">When you bulk import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or bulk export data from a table, you can use a *format file* to store all the format information that is required to bulk export or bulk import data.</span></span> <span data-ttu-id="71d64-104">Isso inclui informações de formato para cada campo em um arquivo de dados relativo para essa tabela.</span><span class="sxs-lookup"><span data-stu-id="71d64-104">This includes format information for each field in a data file relative to that table.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="71d64-105">dá suporte a dois tipos de arquivos de formato: arquivos de formatos XML e de formato não XML.</span><span class="sxs-lookup"><span data-stu-id="71d64-105">supports two types of format files: XML formats and non-XML format files.</span></span> <span data-ttu-id="71d64-106">Os arquivos de formato XML e não XML contêm descrições de cada campo de um arquivo de dados, e arquivos de formato XML também contêm descrições das colunas das tabelas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="71d64-106">Both non-XML format files and XML format files contain descriptions of every field in a data file, and XML format files also contain descriptions of the corresponding table columns.</span></span> <span data-ttu-id="71d64-107">Geralmente, arquivos de formato XML e não XML são intercambiáveis.</span><span class="sxs-lookup"><span data-stu-id="71d64-107">Generally, XML and non-XML format files are interchangeable.</span></span> <span data-ttu-id="71d64-108">Entretanto, recomendamos que você use a sintaxe XML para novos arquivos de formato porque eles oferecem diversas vantagens em relação aos arquivos de formato não XML.</span><span class="sxs-lookup"><span data-stu-id="71d64-108">However, we recommend that you use the XML syntax for new format files because they provide several advantages over non-XML format files.</span></span> <span data-ttu-id="71d64-109">Para obter mais informações, veja [Arquivos de formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="71d64-109">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 
  
##  <a name="benefits-of-format-files"></a><a name="Benefits"></a> <span data-ttu-id="71d64-110">Benefícios de arquivos de formato</span><span class="sxs-lookup"><span data-stu-id="71d64-110">Benefits of Format Files</span></span>  
  
-   <span data-ttu-id="71d64-111">Fornece um sistema flexível para gravar arquivos de dados que exigem pouca ou nenhuma edição para estar em conformidade com outros formatos de dados ou para ler arquivos de dados de outro software.</span><span class="sxs-lookup"><span data-stu-id="71d64-111">Provides a flexible system for writing data files that requires little or no editing to comply with other data formats or to read data files from other software.</span></span>  
  
-   <span data-ttu-id="71d64-112">Habilita-o a importar dados em massa sem precisar adicionar ou excluir dados desnecessários, nem reordenar dados existentes no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="71d64-112">Enables you to bulk import data without having to add or delete unnecessary data or to reorder existing data in the data file.</span></span> <span data-ttu-id="71d64-113">Os arquivos de formato são particularmente úteis quando existe uma incompatibilidade entre campos no arquivo de dados e as colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="71d64-113">Format files are particularly useful when a mismatch exists between fields in the data file and columns in the table.</span></span>  
  
##  <a name="examples-of-format-files"></a><a name="ExamplesOfFFs"></a> <span data-ttu-id="71d64-114">Exemplos de arquivos de formato</span><span class="sxs-lookup"><span data-stu-id="71d64-114">Examples of Format Files</span></span>  
 <span data-ttu-id="71d64-115">Os exemplos abaixo mostram o layout de um arquivo de formato não XML e de um arquivo de formato XML.</span><span class="sxs-lookup"><span data-stu-id="71d64-115">The following examples show the layout of a non-XML format file and of an XML format file.</span></span> <span data-ttu-id="71d64-116">Esses arquivos de formato correspondem à tabela `HumanResources.myTeam` no banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71d64-116">These format files correspond to the `HumanResources.myTeam` table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="71d64-117">Essa tabela contém quatro colunas: `EmployeeID`, `Name`, `Title`e `ModifiedDate`.</span><span class="sxs-lookup"><span data-stu-id="71d64-117">This table contains four columns: `EmployeeID`, `Name`, `Title`, and `ModifiedDate`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71d64-118">Para obter informações sobre essa tabela e como criá-la, veja [Tabela de exemplo HumanResources.myTeam &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="71d64-118">For information about this table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
### <a name="a-using-a-non-xml-format-file"></a><span data-ttu-id="71d64-119">a.</span><span class="sxs-lookup"><span data-stu-id="71d64-119">A.</span></span> <span data-ttu-id="71d64-120">Usando um arquivo de formato não XML</span><span class="sxs-lookup"><span data-stu-id="71d64-120">Using a non-XML format file</span></span>  
 <span data-ttu-id="71d64-121">O arquivo de formato não XML seguinte usa o formato de dados nativo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a tabela `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="71d64-121">The following non-XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="71d64-122">Esse arquivo de formato foi criado usando o comando `bcp` a seguir.</span><span class="sxs-lookup"><span data-stu-id="71d64-122">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Fmt -n -T   
The contents of this format file are as follows: 9.0  
4  
1       SQLSMALLINT   0       2       ""   1     EmployeeID               ""  
2       SQLNCHAR      2       100     ""   2     Name                     SQL_Latin1_General_CP1_CI_AS  
3       SQLNCHAR      2       100     ""   3     Title                    SQL_Latin1_General_CP1_CI_AS  
4       SQLNCHAR      2       100     ""   4     Background               SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="71d64-123">Para obter mais informações, veja [Arquivos de formato não XML &#40;SQL Server&#41;](non-xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="71d64-123">For more information, see [Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md).</span></span>  
  
 
  
### <a name="b-using-an-xml-format-file"></a><span data-ttu-id="71d64-124">B.</span><span class="sxs-lookup"><span data-stu-id="71d64-124">B.</span></span> <span data-ttu-id="71d64-125">Usando um arquivo de formato XML</span><span class="sxs-lookup"><span data-stu-id="71d64-125">Using an XML format file</span></span>  
 <span data-ttu-id="71d64-126">O seguinte arquivo de formato XML usa o formato de dados nativo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a tabela `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="71d64-126">The following XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="71d64-127">Esse arquivo de formato foi criado usando o comando `bcp` a seguir.</span><span class="sxs-lookup"><span data-stu-id="71d64-127">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Xml -x -n -T   
```  
  
 <span data-ttu-id="71d64-128">O arquivo de formato contém:</span><span class="sxs-lookup"><span data-stu-id="71d64-128">The format file contains:</span></span>  
  
```  
 <?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="EmployeeID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Name" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Title" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Background" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="71d64-129">Para obter mais informações, veja [Arquivos de formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="71d64-129">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="when-is-a-format-file-required"></a><a name="WhenFFrequired"></a> <span data-ttu-id="71d64-130">Quando um arquivo de formato é necessário?</span><span class="sxs-lookup"><span data-stu-id="71d64-130">When Is a Format File Required?</span></span>  
 <span data-ttu-id="71d64-131">Uma instrução INSERT... A instrução SELECT \* FROM OPENROWSET (BULK...) sempre requer um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="71d64-131">An INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement always requires a format file.</span></span>  
  
-   <span data-ttu-id="71d64-132">Para **bcp** ou BULK INSERT, em situações simples, usar um arquivo de formato é opcional e raramente necessário.</span><span class="sxs-lookup"><span data-stu-id="71d64-132">For **bcp** or BULK INSERT, in simple situations, using a format file is optional and rarely necessary.</span></span> <span data-ttu-id="71d64-133">No entanto, em situações complexas de importação em massa, um arquivo de formato é frequentemente necessário.</span><span class="sxs-lookup"><span data-stu-id="71d64-133">However, for complex bulk-import situations, a format file is frequently required.</span></span>  
  
 <span data-ttu-id="71d64-134">Os arquivos de formato serão necessários se:</span><span class="sxs-lookup"><span data-stu-id="71d64-134">Format files are required if:</span></span>  
  
-   <span data-ttu-id="71d64-135">O mesmo arquivo de dados for usado como origem para diversas tabelas que têm esquemas diferentes.</span><span class="sxs-lookup"><span data-stu-id="71d64-135">The same data file is used as a source for multiple tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="71d64-136">O arquivo de dados tiver um número diferente de campos do número de colunas da tabela de destino; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="71d64-136">The data file has a different number of fields that the target table has columns; for example:</span></span>  
  
    -   <span data-ttu-id="71d64-137">A tabela de destino contém pelo menos uma coluna para a qual há um valor padrão definido ou é permitido NULL.</span><span class="sxs-lookup"><span data-stu-id="71d64-137">The target table contains at least one column for which either a default value is defined or NULL is allowed.</span></span>  
  
    -   <span data-ttu-id="71d64-138">Os usuários não têm permissões SELECT/INSERT em uma ou mais colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="71d64-138">The users do not have SELECT/INSERT permissions on one or more columns in the table.</span></span>  
  
    -   <span data-ttu-id="71d64-139">Um único arquivo de dados é usado com duas ou mais tabelas que têm esquemas diferentes.</span><span class="sxs-lookup"><span data-stu-id="71d64-139">A single data file is used with two or more tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="71d64-140">A ordem de colunas é diferente para o arquivo de dados e a tabela.</span><span class="sxs-lookup"><span data-stu-id="71d64-140">The column order is different for the data file and table.</span></span>  
  
-   <span data-ttu-id="71d64-141">Os caracteres de terminação ou o comprimento dos prefixos diferem entre as colunas do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="71d64-141">The terminating characters or prefix lengths differ among the columns of the data file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71d64-142">Na ausência de um arquivo de formato, se um comando **bcp** especificar uma opção de formato de dados ( **-n**, **-c**, **-w**ou **-N**), ou uma operação BULK INSERT especificar a opção DATAFILETYPE, o formato de dados especificado será usado como o método padrão de interpretação dos campos do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="71d64-142">In the absence of a format file, if a **bcp** command specifies a data-format switch (**-n**, **-c**, **-w**, or **-N**) or a BULK INSERT operation specifies the DATAFILETYPE option, the specified data format is used as the default method of interpreting the fields of the data file.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="71d64-143">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="71d64-143">Related Tasks</span></span>  
  
-   [<span data-ttu-id="71d64-144">Criar um arquivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71d64-144">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="71d64-145">Usar um arquivo de formato para importação em massa de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71d64-145">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="71d64-146">Usar um arquivo de formato para ignorar uma coluna de tabela &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71d64-146">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="71d64-147">Usar um arquivo de formato para ignorar um campo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71d64-147">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="71d64-148">Usar um arquivo de formato para mapear colunas de uma tabela para campos de arquivo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71d64-148">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="71d64-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71d64-149">See Also</span></span>  
 <span data-ttu-id="71d64-150">[Arquivos de formato não XML &#40;SQL Server&#41;](non-xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="71d64-150">[Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md) </span></span>  
 <span data-ttu-id="71d64-151">[Arquivos de formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="71d64-151">[XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="71d64-152">Formatos de dados para importação ou exportação em massa &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71d64-152">Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;</span></span>](data-formats-for-bulk-import-or-bulk-export-sql-server.md)  
  
  
