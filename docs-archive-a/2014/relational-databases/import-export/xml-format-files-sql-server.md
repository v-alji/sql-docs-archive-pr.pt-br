---
title: Arquivos de formato XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], XML format files
- bulk importing [SQL Server], format files
- XML format files [SQL Server]
ms.assetid: 69024aad-eeea-4187-8fea-b49bc2359849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cc1e8de30fa582898ef8516b9767dec14c4fa81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581823"
---
# <a name="xml-format-files-sql-server"></a><span data-ttu-id="66fb7-102">Arquivos de formato XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="66fb7-102">XML Format Files (SQL Server)</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="66fb7-103">fornece um esquema XML que define a sintaxe para escrever *arquivos de formato XML* a serem usados para importar dados em massa para uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66fb7-103">provides an XML schema that defines syntax for writing *XML format files* to use for bulk importing data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="66fb7-104">Arquivos no formato XML devem aderir a este esquema que está definido no Schema Definition Language XML (XSDL).</span><span class="sxs-lookup"><span data-stu-id="66fb7-104">XML format files must adhere to this schema, which is defined in the XML Schema Definition Language (XSDL).</span></span> <span data-ttu-id="66fb7-105">Os arquivos de formato XML só têm suporte quando as ferramentas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são instaladas junto com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="66fb7-105">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tools are installed together with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="66fb7-106">Você pode usar um arquivo no formato XML com um comando **bcp**, uma instrução BULK INSERT ou INSERT ... Instrução SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="66fb7-106">You can use an XML format file with a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="66fb7-107">O comando **bcp** permite gerar automaticamente um arquivo no formato XML para uma tabela; para obter mais informações, consulte [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="66fb7-107">The **bcp** command allows you to automatically generate an XML format file for a table; for more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66fb7-108">Há suporte a dois tipos de arquivos de formato de exportação e importação em massa: *arquivos de formato não XML* e *arquivos de formato XML*.</span><span class="sxs-lookup"><span data-stu-id="66fb7-108">Two types of format files are supported for bulk exporting and importing: *non-XML format files* and *XML format files*.</span></span> <span data-ttu-id="66fb7-109">Arquivos de formato XML fornecem uma alternativa flexível e poderosa para arquivos de formato não XML.</span><span class="sxs-lookup"><span data-stu-id="66fb7-109">XML format files provide a flexible and powerful alternative to non-XML format files.</span></span> <span data-ttu-id="66fb7-110">Para obter informações sobre arquivos de formato não XML, veja [Arquivos de formato não XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="66fb7-110">For information about non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="benefits-of-xml-format-files"></a><a name="BenefitsOfXmlFFs"></a> <span data-ttu-id="66fb7-111">Benefícios de arquivos de formato XML</span><span class="sxs-lookup"><span data-stu-id="66fb7-111">Benefits of XML Format Files</span></span>  
  
-   <span data-ttu-id="66fb7-112">Arquivos de formato XML são autodescritivos, o que facilita sua leitura, criação e extensão.</span><span class="sxs-lookup"><span data-stu-id="66fb7-112">XML format files are self-describing, making them easy to read, create, and extend.</span></span> <span data-ttu-id="66fb7-113">Eles são legíveis, tornando fácil compreender como são os dados são interpretados durante operações em massa.</span><span class="sxs-lookup"><span data-stu-id="66fb7-113">They are human readable, making it easy to understand how data is interpreted during bulk operations.</span></span>  
  
-   <span data-ttu-id="66fb7-114">Arquivos no formato XML contêm os tipos de dados das colunas de destino.</span><span class="sxs-lookup"><span data-stu-id="66fb7-114">XML format files contain the data types of target columns.</span></span>  <span data-ttu-id="66fb7-115">A codificação XML descreve claramente os tipos de dados e elementos de dados do arquivo de dados e também o mapeamento entre elementos de dados e colunas de tabela.</span><span class="sxs-lookup"><span data-stu-id="66fb7-115">The XML encoding clearly describes the data types and data elements of the data file and also the mapping between data elements and table columns.</span></span>  
  
     <span data-ttu-id="66fb7-116">Isso permite a separação entre como os dados são representados no arquivo de dados e quais tipos de dados são associados a cada campo no arquivo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-116">This enables separation between how data is represented in the data file and what data type is associated with each field in the file.</span></span> <span data-ttu-id="66fb7-117">Por exemplo, se um arquivo de dados contiver uma representação de caracteres dos dados, o tipo de coluna SQL correspondente será perdido.</span><span class="sxs-lookup"><span data-stu-id="66fb7-117">For example, if a data file contains a character representation of the data, the corresponding SQL column type is lost.</span></span>  
  
-   <span data-ttu-id="66fb7-118">Um arquivo no formato XML permite carregar um campo contendo um único tipo de dado de objeto grande (LOB) de um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-118">An XML format file allows for loading of a field that contains a single large object (LOB) data type from a data file.</span></span>  
  
-   <span data-ttu-id="66fb7-119">Um arquivo de formato XML pode ser aprimorado e ainda permanecer compatível com suas versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="66fb7-119">An XML format file can be enhanced yet remain compatible with its earlier versions.</span></span> <span data-ttu-id="66fb7-120">Além disso, a clareza da codificação XML facilita a criação de arquivos em formatos múltiplos para um determinado arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-120">Furthermore, the clarity of XML encoding facilitates the creation of multiple format files for a given data file.</span></span> <span data-ttu-id="66fb7-121">Isto será útil se você tiver que mapear tudo ou alguns dos campos de dados para colunas em tabelas ou exibições diferentes.</span><span class="sxs-lookup"><span data-stu-id="66fb7-121">This is useful if you have to map all or some of the data fields to columns in different tables or views.</span></span>  
  
-   <span data-ttu-id="66fb7-122">A sintaxe de um arquivo de formato é independente da direção da operação; ou seja, a sintaxe é a mesma para exportação ou importação em massa.</span><span class="sxs-lookup"><span data-stu-id="66fb7-122">The XML syntax is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span>  
  
-   <span data-ttu-id="66fb7-123">Você pode usar arquivos no formato XML para importar em massa dados em tabelas ou visualizações não particionadas e para exportar em massa dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-123">You can use XML format files to bulk import data into tables or non-partitioned views and to bulk export data.</span></span>  
  
-   <span data-ttu-id="66fb7-124">Para a função OPENROWSET (BULK...), a especificação de uma tabela de destino é opcional.</span><span class="sxs-lookup"><span data-stu-id="66fb7-124">For the OPENROWSET(BULK...) function specifying a target table is optional.</span></span> <span data-ttu-id="66fb7-125">Isso ocorre porque a função depende do arquivo de formato XML para ler dados de um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-125">This is because the function relies on the XML format file to read data from a data file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="66fb7-126">Uma tabela de destino é necessária com o comando **bcp** e a instrução BULK INSERT, que usa as colunas da tabela de destino para fazer a conversão do tipo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-126">A target table is necessary with the **bcp** command and the BULK INSERT statement, which uses the target table columns to do the type conversion.</span></span>  
  
##  <a name="structure-of-xml-format-files"></a><a name="StructureOfXmlFFs"></a> <span data-ttu-id="66fb7-127">Estrutura de arquivos no formato não XML</span><span class="sxs-lookup"><span data-stu-id="66fb7-127">Structure of XML Format Files</span></span>  
 <span data-ttu-id="66fb7-128">Como um arquivo de formato não XML, um arquivo de formato XML define o formato e a estrutura dos campos de dados em um arquivo de dados e mapeia esses campos de dados a colunas em uma única tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="66fb7-128">Like a non-XML format file, an XML format file defines the format and structure of the data fields in a data file and maps those data fields to columns in a single target table.</span></span>  
  
 <span data-ttu-id="66fb7-129">Um arquivo de formato XML tem dois componentes principais, \<RECORD> e \<ROW>:</span><span class="sxs-lookup"><span data-stu-id="66fb7-129">An XML format file possesses two main components, \<RECORD> and \<ROW>:</span></span>  
  
-   <span data-ttu-id="66fb7-130">\<RECORD> descreve os dados conforme eles são armazenados no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-130">\<RECORD> describes the data as it is stored in the data file.</span></span>  
  
     <span data-ttu-id="66fb7-131">Cada elemento \<RECORD> contém um conjunto de um ou mais elementos \<FIELD>.</span><span class="sxs-lookup"><span data-stu-id="66fb7-131">Each \<RECORD> element contains a set of one or more \<FIELD> elements.</span></span> <span data-ttu-id="66fb7-132">Estes elementos correspondem a campos no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-132">These elements correspond to fields in the data file.</span></span> <span data-ttu-id="66fb7-133">A sintaxe básica é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="66fb7-133">The basic syntax is as follows:</span></span>  
  
     \<RECORD>  
  
     <span data-ttu-id="66fb7-134">\<FIELD .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="66fb7-134">\<FIELD .../> [ ...*n* ]</span></span>  
  
     \</RECORD>  
  
     <span data-ttu-id="66fb7-135">Cada elemento \<FIELD> descreve o conteúdo de um campo de dados específico.</span><span class="sxs-lookup"><span data-stu-id="66fb7-135">Each \<FIELD> element describes the contents of a specific data field.</span></span> <span data-ttu-id="66fb7-136">Um campo só pode ser mapeado para uma coluna na tabela.</span><span class="sxs-lookup"><span data-stu-id="66fb7-136">A field can only be mapped to one column in the table.</span></span> <span data-ttu-id="66fb7-137">Nem todos os campos precisam ser mapeados para colunas.</span><span class="sxs-lookup"><span data-stu-id="66fb7-137">Not all fields need to be mapped to columns.</span></span>  
  
     <span data-ttu-id="66fb7-138">Um campo em um arquivo de dados pode ser de comprimento fixo/variável ou terminado em caractere.</span><span class="sxs-lookup"><span data-stu-id="66fb7-138">A field in a data file can be either of fixed/variable length or character terminated.</span></span> <span data-ttu-id="66fb7-139">Um *valor de campo* pode ser representado como: um caractere (usando representação do byte único), um caractere largo (usando representação Unicode de dois bytes), formato de banco de dados nativo ou um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-139">A *field value* can be represented as: a character (using single-byte representation), a wide character (using Unicode two-byte representation), native database format, or a file name.</span></span> <span data-ttu-id="66fb7-140">Se um valor de campo for representado como um nome de arquivo, o nome de arquivo apontará ao arquivo que contém o valor de uma coluna de BLOB na tabela destino.</span><span class="sxs-lookup"><span data-stu-id="66fb7-140">If a field value is represented as a file name, the file name points to the file that contains the value of a BLOB column in the target table.</span></span>  
  
-   <span data-ttu-id="66fb7-141">\<ROW> descreve como construir linhas de dados de um arquivo de dados quando os dados são importados em uma tabela [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66fb7-141">\<ROW> describes how to construct data rows from a data file when the data from the file is imported into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
     <span data-ttu-id="66fb7-142">Um elemento \<ROW> contém um conjunto de elementos \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="66fb7-142">A \<ROW> element contains a set of \<COLUMN> elements.</span></span> <span data-ttu-id="66fb7-143">Esses elementos correspondem a colunas de tabela.</span><span class="sxs-lookup"><span data-stu-id="66fb7-143">These elements correspond to table columns.</span></span> <span data-ttu-id="66fb7-144">A sintaxe básica é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="66fb7-144">The basic syntax is as follows:</span></span>  
  
     \<ROW>  
  
     <span data-ttu-id="66fb7-145">\<COLUMN .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="66fb7-145">\<COLUMN .../> [ ...*n* ]</span></span>  
  
     \</ROW>  
  
     <span data-ttu-id="66fb7-146">Cada elemento \<COLUMN> só pode ser mapeado para um campo do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-146">Each \<COLUMN> element can be mapped to only one field in the data file.</span></span> <span data-ttu-id="66fb7-147">A ordem dos elementos \<COLUMN> no elemento \<ROW> define a ordem em que eles são retornados pela operação em massa.</span><span class="sxs-lookup"><span data-stu-id="66fb7-147">The order of the \<COLUMN> elements in the \<ROW> element defines the order in which they are returned by the bulk operation.</span></span> <span data-ttu-id="66fb7-148">O arquivo de formato XML atribui a cada elemento \<COLUMN> um nome local que não tem nenhuma relação com a coluna na tabela de destino de uma operação de importação em massa.</span><span class="sxs-lookup"><span data-stu-id="66fb7-148">The XML format file assigns each \<COLUMN> element a local name that has no relationship to the column in the target table of a bulk import operation.</span></span>  
  
##  <a name="schema-syntax-for-xml-format-files"></a><a name="SchemaSyntax"></a> <span data-ttu-id="66fb7-149">Sintaxe de esquema para arquivos de formato XML</span><span class="sxs-lookup"><span data-stu-id="66fb7-149">Schema Syntax for XML Format Files</span></span>  
 <span data-ttu-id="66fb7-150">Esta seção contém um resumo dos elementos e atributos do esquema XML para arquivos no formato XML.</span><span class="sxs-lookup"><span data-stu-id="66fb7-150">This section contains a summary of the elements and attributes of the XML schema for XML format files.</span></span> <span data-ttu-id="66fb7-151">A sintaxe de um arquivo de formato é independente da direção da operação; ou seja, a sintaxe é a mesma para exportação ou importação em massa.</span><span class="sxs-lookup"><span data-stu-id="66fb7-151">The syntax of a format file is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span> <span data-ttu-id="66fb7-152">Esta seção também considera como a importação em massa usa os elementos \<ROW> e \<COLUMN>, e como colocar o valor de xsi:type de um elemento em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-152">This section also considers how bulk import uses the \<ROW> and \<COLUMN> elements and how to put the xsi:type value of an element into a data set.</span></span>  
  
 <span data-ttu-id="66fb7-153">Para ver como a sintaxe corresponde aos arquivos de formato XML atuais, consulte [Arquivos de formato XML de exemplo](#SampleXmlFFs), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="66fb7-153">To see how the syntax corresponds to actual XML format files, see [Sample XML Format Files](#SampleXmlFFs), later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66fb7-154">Você pode modificar um arquivo de formato para importar em massa de um arquivo de dados no qual o número e/ou a ordem dos campos difere do número e/ou da ordem das colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="66fb7-154">You can modify a format file to let you bulk import from a data file in which the number and/or order of the fields differ from the number and/or order of table columns.</span></span> <span data-ttu-id="66fb7-155">Para obter mais informações, consulte [Arquivos de formato para importação ou exportação de dados &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="66fb7-155">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
  
  
###  <a name="basic-syntax-of-the-xml-schema"></a><a name="BasicSyntax"></a> <span data-ttu-id="66fb7-156">Sintaxe básica de esquema XML</span><span class="sxs-lookup"><span data-stu-id="66fb7-156">Basic Syntax of the XML Schema</span></span>  
 <span data-ttu-id="66fb7-157">Essas instruções de sintaxe só mostram os elementos (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW> e \<COLUMN>) e os atributos básicos deles.</span><span class="sxs-lookup"><span data-stu-id="66fb7-157">This syntax statements show only the elements (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW>, and \<COLUMN>) and their basic attributes.</span></span>  
  
 \<BCPFORMAT ...>  
  
 \<RECORD>  
  
 <span data-ttu-id="66fb7-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span><span class="sxs-lookup"><span data-stu-id="66fb7-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span></span>  
  
 />  
  
 \</RECORD>  
  
 \<ROW>  
  
 <span data-ttu-id="66fb7-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span><span class="sxs-lookup"><span data-stu-id="66fb7-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span></span>  
  
 />  
  
 \</ROW>  
  
 \</BCPFORMAT>  
  
> [!NOTE]  
>  <span data-ttu-id="66fb7-160">Atributos adicionais associados ao valor de xsi:type em um elemento \<FIELD> ou \<COLUMN> são descritos posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="66fb7-160">Additional attributes that are associated with the value of the xsi:type in a \<FIELD> or \<COLUMN> element are described later in this topic.</span></span>  
  

  
####  <a name="schema-elements"></a><a name="SchemaElements"></a> <span data-ttu-id="66fb7-161">Elementos de esquema</span><span class="sxs-lookup"><span data-stu-id="66fb7-161">Schema Elements</span></span>  
 <span data-ttu-id="66fb7-162">Esta seção resume a finalidade de cada elemento que o esquema XML define para os arquivos de formato XML.</span><span class="sxs-lookup"><span data-stu-id="66fb7-162">This section summarizes the purpose of each element that the XML schema defines for XML format files.</span></span> <span data-ttu-id="66fb7-163">Os atributos são descritos em seções separadas posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="66fb7-163">The attributes are described in separate sections later in this topic.</span></span>  
  
 \<BCPFORMAT>  
 <span data-ttu-id="66fb7-164">É o elemento de formato de arquivo que define a estrutura do registro de um determinado arquivo de dados e sua correspondência às colunas de uma linha de tabela na tabela.</span><span class="sxs-lookup"><span data-stu-id="66fb7-164">Is the format-file element that defines the record structure of a given data file and its correspondence to the columns of a table row in the table.</span></span>  
  
 \<RECORD .../>  
 <span data-ttu-id="66fb7-165">Define um elemento complexo que contém um ou mais elementos \<FIELD>.</span><span class="sxs-lookup"><span data-stu-id="66fb7-165">Defines a complex element containing one or more \<FIELD> elements.</span></span> <span data-ttu-id="66fb7-166">A ordem na qual os campos são declarados no arquivo de formato é a ordem na qual esses campos aparecem no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-166">The order in which the fields are declared in the format file is the order in which those fields appear in the data file.</span></span>  
  
 \<FIELD .../>  
 <span data-ttu-id="66fb7-167">Define um campo no arquivo de dados que contém dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-167">Defines a field in data file, which contains data.</span></span>  
  
 <span data-ttu-id="66fb7-168">Os atributos desse elemento são discutidos em [Atributos do elemento \<FIELD>](#AttrOfFieldElement), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="66fb7-168">The attributes of this element are discussed in [Attributes of the \<FIELD> Element](#AttrOfFieldElement), later in this topic.</span></span>  
  
 \<ROW .../>  
 <span data-ttu-id="66fb7-169">Define um elemento complexo que contém um ou mais elementos \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="66fb7-169">Defines a complex element containing one or more \<COLUMN> elements.</span></span> <span data-ttu-id="66fb7-170">A ordem dos elementos \<COLUMN> não depende da ordem dos elementos \<FIELD> em uma definição RECORD.</span><span class="sxs-lookup"><span data-stu-id="66fb7-170">The order of the \<COLUMN> elements is independent of the order of \<FIELD> elements in a RECORD definition.</span></span> <span data-ttu-id="66fb7-171">Ao contrário, a ordem dos elementos \<COLUMN> em um arquivo de formato determina a ordem da coluna do conjunto de linhas resultante.</span><span class="sxs-lookup"><span data-stu-id="66fb7-171">Rather, the order of the \<COLUMN> elements in a format file determines the column order of the resultant rowset.</span></span> <span data-ttu-id="66fb7-172">Os campos de dados são carregados na ordem na qual os elementos correspondentes \<COLUMN> são declarados no elemento \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="66fb7-172">Data fields are loaded in the order in which the corresponding \<COLUMN> elements are declared in the \<COLUMN> element.</span></span>  
  
 <span data-ttu-id="66fb7-173">Para obter mais informações, veja [Como a importação em massa usa o elemento \<ROW>](#HowUsesROW), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="66fb7-173">For more information, see [How Bulk Import Uses the \<ROW> Element](#HowUsesROW), later in this topic.</span></span>  
  
 \<COLUMN>  
 <span data-ttu-id="66fb7-174">Define uma coluna como um elemento (\<COLUMN>).</span><span class="sxs-lookup"><span data-stu-id="66fb7-174">Defines a column as an element (\<COLUMN>).</span></span> <span data-ttu-id="66fb7-175">Cada elemento \<COLUMN> corresponde a um elemento \<FIELD> (cuja ID é especificada no atributo SOURCE do elemento \<COLUMN>).</span><span class="sxs-lookup"><span data-stu-id="66fb7-175">Each \<COLUMN> element corresponds to a \<FIELD> element (whose ID is specified in the SOURCE attribute of the \<COLUMN> element).</span></span>  
  
 <span data-ttu-id="66fb7-176">Os atributos desse elemento são discutidos em [Atributos do elemento \<COLUMN>](#AttrOfColumnElement), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="66fb7-176">The attributes of this element are discussed in [Attributes of the \<COLUMN> Element](#AttrOfColumnElement), later in this topic.</span></span> <span data-ttu-id="66fb7-177">Veja também, [Como a importação em massa usa o elemento \<COLUMN>](#HowUsesColumn), mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="66fb7-177">Also see, [How Bulk Import Uses the \<COLUMN> Element](#HowUsesColumn), later in this topic.</span></span>  
  
 \</BCPFORMAT>  
 <span data-ttu-id="66fb7-178">Obrigatório para finalizar o arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="66fb7-178">Required to end the format file.</span></span>  
  
####  <a name="attributes-of-the-field-element"></a><span data-ttu-id="66fb7-179">Atributos <a name="AttrOfFieldElement"></a> do elemento \<FIELD></span><span class="sxs-lookup"><span data-stu-id="66fb7-179"><a name="AttrOfFieldElement"></a> Attributes of the \<FIELD> Element</span></span>  
 <span data-ttu-id="66fb7-180">Esta seção descreve os atributos do elemento \<FIELD>, que são resumidos na seguinte sintaxe de esquema:</span><span class="sxs-lookup"><span data-stu-id="66fb7-180">This section describes the attributes of the \<FIELD> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="66fb7-181">Valores de <FIELD</span><span class="sxs-lookup"><span data-stu-id="66fb7-181"><FIELD</span></span>  
  
 <span data-ttu-id="66fb7-182">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-182">ID **="*`fieldID`*"**</span></span>  
  
 <span data-ttu-id="66fb7-183">xsi **:** Type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-183">xsi **:** type **="*`fieldType`*"**</span></span>  
  
 <span data-ttu-id="66fb7-184">[ LENGTH **="*`n`*"** ]</span><span class="sxs-lookup"><span data-stu-id="66fb7-184">[ LENGTH **="*`n`*"** ]</span></span>  
  
 <span data-ttu-id="66fb7-185">[PREFIX_LENGTH **= " *`p`* "** ]</span><span class="sxs-lookup"><span data-stu-id="66fb7-185">[ PREFIX_LENGTH **="*`p`*"** ]</span></span>  
  
 <span data-ttu-id="66fb7-186">[MAX_LENGTH **= " *`m`* "** ]</span><span class="sxs-lookup"><span data-stu-id="66fb7-186">[ MAX_LENGTH **="*`m`*"** ]</span></span>  
  
 <span data-ttu-id="66fb7-187">[COLLATION **= " *`collationName`* "** ]</span><span class="sxs-lookup"><span data-stu-id="66fb7-187">[ COLLATION **="*`collationName`*"** ]</span></span>  
  
 <span data-ttu-id="66fb7-188">[TERMINAdor **= " *`terminator`* "** ]</span><span class="sxs-lookup"><span data-stu-id="66fb7-188">[ TERMINATOR **="*`terminator`*"** ]</span></span>  
  
 />  
  
 <span data-ttu-id="66fb7-189">Cada elemento \<FIELD> é independente dos outros.</span><span class="sxs-lookup"><span data-stu-id="66fb7-189">Each \<FIELD> element is independent of the others.</span></span> <span data-ttu-id="66fb7-190">Um campo é descrito em termos dos seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="66fb7-190">A field is described in terms of the following attributes:</span></span>  
  
|<span data-ttu-id="66fb7-191">Atributo FIELD</span><span class="sxs-lookup"><span data-stu-id="66fb7-191">FIELD Attribute</span></span>|<span data-ttu-id="66fb7-192">Descrição</span><span class="sxs-lookup"><span data-stu-id="66fb7-192">Description</span></span>|<span data-ttu-id="66fb7-193">Opcional /</span><span class="sxs-lookup"><span data-stu-id="66fb7-193">Optional /</span></span><br /><br /> <span data-ttu-id="66fb7-194">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="66fb7-194">Required</span></span>|  
|---------------------|-----------------|------------------------------|  
|<span data-ttu-id="66fb7-195">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-195">ID **="*`fieldID`*"**</span></span>|<span data-ttu-id="66fb7-196">Especifica o nome lógico do campo no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-196">Specifies the logical name of the field in the data file.</span></span> <span data-ttu-id="66fb7-197">A ID de um campo é a chave para fazer referência ao campo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-197">The ID of a field is the key used to refer to the field.</span></span><br /><br /> <span data-ttu-id="66fb7-198"><ID do campo **= " *`fieldID`* "**/> mapeia para <origem da coluna **= " *`fieldID`* "**/></span><span class="sxs-lookup"><span data-stu-id="66fb7-198"><FIELD ID **="*`fieldID`*"**/> maps to <COLUMN SOURCE **="*`fieldID`*"**/></span></span>|<span data-ttu-id="66fb7-199">Necessária</span><span class="sxs-lookup"><span data-stu-id="66fb7-199">Required</span></span>|  
|<span data-ttu-id="66fb7-200">xsi: Type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-200">xsi:type **="*`fieldType`*"**</span></span>|<span data-ttu-id="66fb7-201">Essa é uma construção XML (usada como um atributo) que identifica o tipo da instância do elemento.</span><span class="sxs-lookup"><span data-stu-id="66fb7-201">This is an XML construct (used like an attribute) that identifies the type of the instance of the element.</span></span> <span data-ttu-id="66fb7-202">O valor de *fieldType* determina de quais atributos opcionais (abaixo) você necessita em determinada instância.</span><span class="sxs-lookup"><span data-stu-id="66fb7-202">The value of *fieldType* determines which of the optional attributes (below) you need in a given instance.</span></span>|<span data-ttu-id="66fb7-203">Obrigatório (dependendo do tipo de dados)</span><span class="sxs-lookup"><span data-stu-id="66fb7-203">Required (depending on the data type)</span></span>|  
|<span data-ttu-id="66fb7-204">COMPRIMENTO **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-204">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="66fb7-205">Esse atributo define o comprimento de uma instância de um tipo de dados de comprimento fixo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-205">This attribute defines the length for an instance of a fixed-length data type.</span></span><br /><br /> <span data-ttu-id="66fb7-206">O valor de *n* deve ser um inteiro positivo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-206">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="66fb7-207">Opcional, a menos que exigido pelo valor xsi:type</span><span class="sxs-lookup"><span data-stu-id="66fb7-207">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="66fb7-208">PREFIX_LENGTH **= " *`p`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-208">PREFIX_LENGTH **="*`p`*"**</span></span>|<span data-ttu-id="66fb7-209">Esse atributo define o comprimento do prefixo para uma representação de dados binária.</span><span class="sxs-lookup"><span data-stu-id="66fb7-209">This attribute defines the prefix length for a binary data representation.</span></span> <span data-ttu-id="66fb7-210">O valor PREFIX_LENGTH, *p*, deve ser um dos seguintes: 1, 2, 4 ou 8.</span><span class="sxs-lookup"><span data-stu-id="66fb7-210">The PREFIX_LENGTH value, *p*, must be one of the following: 1, 2, 4, or 8.</span></span>|<span data-ttu-id="66fb7-211">Opcional, a menos que exigido pelo valor xsi:type</span><span class="sxs-lookup"><span data-stu-id="66fb7-211">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="66fb7-212">MAX_LENGTH **= " *`m`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-212">MAX_LENGTH **="*`m`*"**</span></span>|<span data-ttu-id="66fb7-213">Esse atributo é o número máximo de bytes que pode ser armazenado em um determinado campo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-213">This attribute is the maximum number of bytes that can be stored in a given field.</span></span> <span data-ttu-id="66fb7-214">Sem uma tabela de destino, o comprimento máximo da coluna é conhecido.</span><span class="sxs-lookup"><span data-stu-id="66fb7-214">Without a target table, the column max-length is not known.</span></span> <span data-ttu-id="66fb7-215">O atributo MAX_LENGTH restringe o comprimento máximo de uma coluna de caracteres de saída, limitando o armazenamento alocado para o valor da coluna.</span><span class="sxs-lookup"><span data-stu-id="66fb7-215">The MAX_LENGTH attribute restricts the maximum length of an output character column, limiting the storage allocated for the column value.</span></span> <span data-ttu-id="66fb7-216">Isso é especialmente conveniente ao usar a opção BULK da função OPENROWSET em uma cláusula SELECT FROM.</span><span class="sxs-lookup"><span data-stu-id="66fb7-216">This is especially convenient when using the OPENROWSET function's BULK option in a SELECT FROM clause.</span></span><br /><br /> <span data-ttu-id="66fb7-217">O valor de *m* deve ser um inteiro positivo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-217">The value of *m* must be a positive integer.</span></span> <span data-ttu-id="66fb7-218">Por padrão, o comprimento máximo é 8.000 caracteres para uma coluna **char** e 4.000 caracteres para uma coluna **nchar** .</span><span class="sxs-lookup"><span data-stu-id="66fb7-218">By default, the maximum length is 8000 characters for a **char** column and 4000 characters for an **nchar** column.</span></span>|<span data-ttu-id="66fb7-219">Opcional</span><span class="sxs-lookup"><span data-stu-id="66fb7-219">Optional</span></span>|  
|<span data-ttu-id="66fb7-220">COLLATION **= " *`collationName`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-220">COLLATION **="*`collationName`*"**</span></span>|<span data-ttu-id="66fb7-221">COLLATION só é permitido para campos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="66fb7-221">COLLATION is only allowed for character fields.</span></span> <span data-ttu-id="66fb7-222">Para obter uma lista dos nomes de ordenação do SQL, veja [Nome de ordenação do SQL Server &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="66fb7-222">For a list of the SQL collation names, see [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql).</span></span>|<span data-ttu-id="66fb7-223">Opcional</span><span class="sxs-lookup"><span data-stu-id="66fb7-223">Optional</span></span>|  
|<span data-ttu-id="66fb7-224">TERMINAdor **= " *`terminator`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-224">TERMINATOR **= "*`terminator`*"**</span></span>|<span data-ttu-id="66fb7-225">Esse atributo especifica o terminador de um campo de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-225">This attribute specifies the terminator of a data field.</span></span> <span data-ttu-id="66fb7-226">O terminador pode ser qualquer caractere.</span><span class="sxs-lookup"><span data-stu-id="66fb7-226">The terminator can be any character.</span></span> <span data-ttu-id="66fb7-227">O terminador deve ser um caractere exclusivo que não faça parte dos dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-227">The terminator must be a unique character that is not part of the data.</span></span><br /><br /> <span data-ttu-id="66fb7-228">Por padrão, o terminador de campo é o caractere de tabulação (representado como \t).</span><span class="sxs-lookup"><span data-stu-id="66fb7-228">By default, the field terminator is the tab character (represented as \t).</span></span> <span data-ttu-id="66fb7-229">Para representar uma marca de parágrafo, use \r\n.</span><span class="sxs-lookup"><span data-stu-id="66fb7-229">To represent a paragraph mark, use \r\n.</span></span>|<span data-ttu-id="66fb7-230">Usado somente com um xsi:type de dados de caracteres, que requer esse atributo</span><span class="sxs-lookup"><span data-stu-id="66fb7-230">Used only with an xsi:type of character data, which requires this attribute</span></span>|  
  
#####  <a name="xsitype-values-of-the-field-element"></a><span data-ttu-id="66fb7-231">Valores <a name="XsiTypeValuesOfFIELD"></a> Xsi:type do elemento \<FIELD></span><span class="sxs-lookup"><span data-stu-id="66fb7-231"><a name="XsiTypeValuesOfFIELD"></a> Xsi:type values of the \<FIELD> Element</span></span>  
 <span data-ttu-id="66fb7-232">O valor de xsi:type é uma construção XML (usada como um atributo) que identifica o tipo de dados de uma instância de um elemento.</span><span class="sxs-lookup"><span data-stu-id="66fb7-232">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="66fb7-233">Para obter informações sobre como usar o valor de xsi:type, consulte "Colocando o valor de xsi:type em um conjunto de dados", posteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="66fb7-233">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="66fb7-234">O valor de xsi:type do elemento \<FIELD> dá suporte aos tipos de dados a seguir.</span><span class="sxs-lookup"><span data-stu-id="66fb7-234">The xsi:type value of the \<FIELD> element supports the following data types.</span></span>  
  
|<span data-ttu-id="66fb7-235">Valores de \<FIELD> xsi:type</span><span class="sxs-lookup"><span data-stu-id="66fb7-235">\<FIELD> xsi:type values</span></span>|<span data-ttu-id="66fb7-236">Atributos XML obrigatórios</span><span class="sxs-lookup"><span data-stu-id="66fb7-236">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="66fb7-237">para tipo de dados</span><span class="sxs-lookup"><span data-stu-id="66fb7-237">for Data Type</span></span>|<span data-ttu-id="66fb7-238">Atributos XML opcionais</span><span class="sxs-lookup"><span data-stu-id="66fb7-238">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="66fb7-239">para tipo de dados</span><span class="sxs-lookup"><span data-stu-id="66fb7-239">for Data Type</span></span>|  
|-------------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="66fb7-240">**NativeFixed**</span><span class="sxs-lookup"><span data-stu-id="66fb7-240">**NativeFixed**</span></span>|`LENGTH`|<span data-ttu-id="66fb7-241">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="66fb7-241">None.</span></span>|  
|<span data-ttu-id="66fb7-242">**NativePrefix**</span><span class="sxs-lookup"><span data-stu-id="66fb7-242">**NativePrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="66fb7-243">MAX_LENGTH</span><span class="sxs-lookup"><span data-stu-id="66fb7-243">MAX_LENGTH</span></span>|  
|<span data-ttu-id="66fb7-244">**CharFixed**</span><span class="sxs-lookup"><span data-stu-id="66fb7-244">**CharFixed**</span></span>|`LENGTH`|<span data-ttu-id="66fb7-245">COLLATION</span><span class="sxs-lookup"><span data-stu-id="66fb7-245">COLLATION</span></span>|  
|<span data-ttu-id="66fb7-246">**NCharFixed**</span><span class="sxs-lookup"><span data-stu-id="66fb7-246">**NCharFixed**</span></span>|`LENGTH`|<span data-ttu-id="66fb7-247">COLLATION</span><span class="sxs-lookup"><span data-stu-id="66fb7-247">COLLATION</span></span>|  
|<span data-ttu-id="66fb7-248">**CharPrefix**</span><span class="sxs-lookup"><span data-stu-id="66fb7-248">**CharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="66fb7-249">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="66fb7-249">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="66fb7-250">**NCharPrefix**</span><span class="sxs-lookup"><span data-stu-id="66fb7-250">**NCharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="66fb7-251">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="66fb7-251">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="66fb7-252">**CharTerm**</span><span class="sxs-lookup"><span data-stu-id="66fb7-252">**CharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="66fb7-253">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="66fb7-253">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="66fb7-254">**NCharTerm**</span><span class="sxs-lookup"><span data-stu-id="66fb7-254">**NCharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="66fb7-255">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="66fb7-255">MAX_LENGTH, COLLATION</span></span>|  
  
 <span data-ttu-id="66fb7-256">Para obter mais informações sobre tipos de dados do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], confira [Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="66fb7-256">For more information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
####  <a name="attributes-of-the-column-element"></a><span data-ttu-id="66fb7-257">Atributos <a name="AttrOfColumnElement"></a> do elemento \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="66fb7-257"><a name="AttrOfColumnElement"></a> Attributes of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="66fb7-258">Esta seção descreve os atributos do elemento \<COLUMN>, que são resumidos na seguinte sintaxe de esquema:</span><span class="sxs-lookup"><span data-stu-id="66fb7-258">This section describes the attributes of the \<COLUMN> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="66fb7-259">\<COLUMN</span><span class="sxs-lookup"><span data-stu-id="66fb7-259">\<COLUMN</span></span>  
  
 <span data-ttu-id="66fb7-260">SOURCE = "*fieldID*"</span><span class="sxs-lookup"><span data-stu-id="66fb7-260">SOURCE = "*fieldID*"</span></span>  
  
 <span data-ttu-id="66fb7-261">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="66fb7-261">NAME = "*columnName*"</span></span>  
  
 <span data-ttu-id="66fb7-262">xsi:type = "*columnType*"</span><span class="sxs-lookup"><span data-stu-id="66fb7-262">xsi:type = "*columnType*"</span></span>  
  
 <span data-ttu-id="66fb7-263">[ LENGTH = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="66fb7-263">[ LENGTH = "*n*" ]</span></span>  
  
 <span data-ttu-id="66fb7-264">[ PRECISION = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="66fb7-264">[ PRECISION = "*n*" ]</span></span>  
  
 <span data-ttu-id="66fb7-265">[ SCALE = "*value*" ]</span><span class="sxs-lookup"><span data-stu-id="66fb7-265">[ SCALE = "*value*" ]</span></span>  
  
 <span data-ttu-id="66fb7-266">[ NULLABLE = { "YES"</span><span class="sxs-lookup"><span data-stu-id="66fb7-266">[ NULLABLE = { "YES"</span></span>  
  
 <span data-ttu-id="66fb7-267">"NO" } ]</span><span class="sxs-lookup"><span data-stu-id="66fb7-267">"NO" } ]</span></span>  
  
 />  
  
 <span data-ttu-id="66fb7-268">Um campo é mapeado para uma coluna na tabela de destino usando os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="66fb7-268">A field is mapped to a column in the target table using the following attributes:</span></span>  
  
|<span data-ttu-id="66fb7-269">Atributo COLUMN</span><span class="sxs-lookup"><span data-stu-id="66fb7-269">COLUMN Attribute</span></span>|<span data-ttu-id="66fb7-270">Descrição</span><span class="sxs-lookup"><span data-stu-id="66fb7-270">Description</span></span>|<span data-ttu-id="66fb7-271">Opcional /</span><span class="sxs-lookup"><span data-stu-id="66fb7-271">Optional /</span></span><br /><br /> <span data-ttu-id="66fb7-272">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="66fb7-272">Required</span></span>|  
|----------------------|-----------------|------------------------------|  
|<span data-ttu-id="66fb7-273">ORIGEM **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-273">SOURCE **="*`fieldID`*"**</span></span>|<span data-ttu-id="66fb7-274">Especifica a ID do campo que é mapeado para a coluna.</span><span class="sxs-lookup"><span data-stu-id="66fb7-274">Specifies the ID of the field being mapped to the column.</span></span><br /><br /> <span data-ttu-id="66fb7-275"><coluna Source **= " *`fieldID`* "**/> mapeia para <campo ID **= " *`fieldID`* "**/></span><span class="sxs-lookup"><span data-stu-id="66fb7-275"><COLUMN SOURCE **="*`fieldID`*"**/> maps to <FIELD ID **="*`fieldID`*"**/></span></span>|<span data-ttu-id="66fb7-276">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="66fb7-276">Required</span></span>|  
|<span data-ttu-id="66fb7-277">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="66fb7-277">NAME = "*columnName*"</span></span>|<span data-ttu-id="66fb7-278">Especifica o nome da coluna no conjunto de linhas representado pelo arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="66fb7-278">Specifies the name of the column in the row set represented by the format file.</span></span> <span data-ttu-id="66fb7-279">Esse nome de coluna é usado para identificar a coluna no conjunto de resultados e não precisa corresponder ao nome da coluna usado na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="66fb7-279">This column name is used to identify the column in the result set, and it need not correspond to the column name used in the target table.</span></span>|<span data-ttu-id="66fb7-280">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="66fb7-280">Required</span></span>|  
|<span data-ttu-id="66fb7-281">xsi **:** Type **= " *`ColumnType`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-281">xsi **:** type **="*`ColumnType`*"**</span></span>|<span data-ttu-id="66fb7-282">Essa é uma construção XML (usada como um atributo) que identifica o tipo de dados da instância do elemento.</span><span class="sxs-lookup"><span data-stu-id="66fb7-282">This is an XML construct (used like an attribute) that identifies the data type of the instance of the element.</span></span> <span data-ttu-id="66fb7-283">O valor de *ColumnType* determina de quais atributos opcionais (abaixo) você necessita em uma determinada instância.</span><span class="sxs-lookup"><span data-stu-id="66fb7-283">The value of *ColumnType* determines which of the optional attributes (below) you need in a given instance.</span></span><br /><br /> <span data-ttu-id="66fb7-284">Observação: os valores possíveis de *ColumnType* e seus atributos associados são listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="66fb7-284">Note: The possible values of *ColumnType* and their associated attributes are listed in the next table.</span></span>|<span data-ttu-id="66fb7-285">Opcional</span><span class="sxs-lookup"><span data-stu-id="66fb7-285">Optional</span></span>|  
|<span data-ttu-id="66fb7-286">COMPRIMENTO **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-286">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="66fb7-287">Define o comprimento de uma instância de um tipo de dados de comprimento fixo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-287">Defines the length for an instance of a fixed-length data type.</span></span> <span data-ttu-id="66fb7-288">LENGTH só é usado quando xsi:type é um tipo de dados de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="66fb7-288">LENGTH is used only when the xsi:type is a string data type.</span></span><br /><br /> <span data-ttu-id="66fb7-289">O valor de *n* deve ser um inteiro positivo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-289">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="66fb7-290">Opcional (disponível somente se xsi:type for um tipo de dados de cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="66fb7-290">Optional (available only if the xsi:type is a string data type)</span></span>|  
|<span data-ttu-id="66fb7-291">PRECISION **="*`n`*"**</span><span class="sxs-lookup"><span data-stu-id="66fb7-291">PRECISION **="*`n`*"**</span></span>|<span data-ttu-id="66fb7-292">Indica o número de dígitos em um número.</span><span class="sxs-lookup"><span data-stu-id="66fb7-292">Indicates the number of digits in a number.</span></span> <span data-ttu-id="66fb7-293">Por exemplo, o número 123,45 tem uma precisão de 5.</span><span class="sxs-lookup"><span data-stu-id="66fb7-293">For example, the number 123.45 has a precision of 5.</span></span><br /><br /> <span data-ttu-id="66fb7-294">O valor deve ser um inteiro positivo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-294">The value must be a positive integer.</span></span>|<span data-ttu-id="66fb7-295">Opcional (disponível somente se xsi:type for um tipo de dados de número variável)</span><span class="sxs-lookup"><span data-stu-id="66fb7-295">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="66fb7-296">SCALE **= " *`int`* "**</span><span class="sxs-lookup"><span data-stu-id="66fb7-296">SCALE **="*`int`*"**</span></span>|<span data-ttu-id="66fb7-297">Indica o número de dígitos à direita da casa decimal em um número.</span><span class="sxs-lookup"><span data-stu-id="66fb7-297">Indicates the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="66fb7-298">Por exemplo, o número 123,45 tem uma escala de 2.</span><span class="sxs-lookup"><span data-stu-id="66fb7-298">For example, the number 123.45 has a scale of 2.</span></span><br /><br /> <span data-ttu-id="66fb7-299">O valor deve ser um inteiro.</span><span class="sxs-lookup"><span data-stu-id="66fb7-299">The value must be an integer.</span></span>|<span data-ttu-id="66fb7-300">Opcional (disponível somente se xsi:type for um tipo de dados de número variável)</span><span class="sxs-lookup"><span data-stu-id="66fb7-300">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="66fb7-301">NULLABLE **=** { **"** YES **"**</span><span class="sxs-lookup"><span data-stu-id="66fb7-301">NULLABLE **=** { **"** YES **"**</span></span><br /><br /> <span data-ttu-id="66fb7-302">**"** NO **"** }</span><span class="sxs-lookup"><span data-stu-id="66fb7-302">**"** NO **"** }</span></span>|<span data-ttu-id="66fb7-303">Indica se uma coluna pode assumir valores NULL.</span><span class="sxs-lookup"><span data-stu-id="66fb7-303">Indicates whether a column can assume NULL values.</span></span> <span data-ttu-id="66fb7-304">Esse atributo é completamente independente de FIELDS.</span><span class="sxs-lookup"><span data-stu-id="66fb7-304">This attribute is completely independent of FIELDS.</span></span> <span data-ttu-id="66fb7-305">Porém, se uma coluna não for NULLABLE e campo especificar NULL (não especificando nenhum valor), ocorrerá erro em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="66fb7-305">However, if a column is not NULLABLE and field specifies NULL (by not specifying any value), a run-time error results.</span></span><br /><br /> <span data-ttu-id="66fb7-306">O atributo NULLABLE será usado apenas se você executar uma instrução SELECT FROM OPENROWSET (BULK...) simples.</span><span class="sxs-lookup"><span data-stu-id="66fb7-306">The NULLABLE attribute is used only if you do a plain SELECT FROM OPENROWSET(BULK...) statement.</span></span>|<span data-ttu-id="66fb7-307">Opcional (disponível para qualquer tipo de dados)</span><span class="sxs-lookup"><span data-stu-id="66fb7-307">Optional (available for any data type)</span></span>|  
  
#####  <a name="xsitype-values-of-the-column-element"></a><span data-ttu-id="66fb7-308">Valores <a name="XsiTypeValuesOfCOLUMN"></a> Xsi:type do elemento \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="66fb7-308"><a name="XsiTypeValuesOfCOLUMN"></a> Xsi:type values of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="66fb7-309">O valor de xsi:type é uma construção XML (usada como um atributo) que identifica o tipo de dados de uma instância de um elemento.</span><span class="sxs-lookup"><span data-stu-id="66fb7-309">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="66fb7-310">Para obter informações sobre como usar o valor de xsi:type, consulte "Colocando o valor de xsi:type em um conjunto de dados", posteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="66fb7-310">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="66fb7-311">O elemento \<COLUMN> dá suporte a tipos de dados SQL nativos, do seguinte modo:</span><span class="sxs-lookup"><span data-stu-id="66fb7-311">The \<COLUMN> element supports native SQL data types, as follows:</span></span>  
  
|<span data-ttu-id="66fb7-312">Categoria do tipo</span><span class="sxs-lookup"><span data-stu-id="66fb7-312">Type Category</span></span>|<span data-ttu-id="66fb7-313">Tipos de dados \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="66fb7-313">\<COLUMN> Data Types</span></span>|<span data-ttu-id="66fb7-314">Atributos XML obrigatórios</span><span class="sxs-lookup"><span data-stu-id="66fb7-314">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="66fb7-315">para tipo de dados</span><span class="sxs-lookup"><span data-stu-id="66fb7-315">for Data Type</span></span>|<span data-ttu-id="66fb7-316">Atributos XML opcionais</span><span class="sxs-lookup"><span data-stu-id="66fb7-316">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="66fb7-317">para tipo de dados</span><span class="sxs-lookup"><span data-stu-id="66fb7-317">for Data Type</span></span>|  
|-------------------|---------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="66fb7-318">Correção</span><span class="sxs-lookup"><span data-stu-id="66fb7-318">Fixed</span></span>|<span data-ttu-id="66fb7-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT`, e `SQLUNIQUEID`</span><span class="sxs-lookup"><span data-stu-id="66fb7-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT`, and `SQLUNIQUEID`</span></span>|<span data-ttu-id="66fb7-320">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="66fb7-320">None.</span></span>|<span data-ttu-id="66fb7-321">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="66fb7-321">NULLABLE</span></span>|  
|<span data-ttu-id="66fb7-322">Número variável</span><span class="sxs-lookup"><span data-stu-id="66fb7-322">Variable Number</span></span>|<span data-ttu-id="66fb7-323">`SQLDECIMAL` e `SQLNUMERIC`</span><span class="sxs-lookup"><span data-stu-id="66fb7-323">`SQLDECIMAL` and `SQLNUMERIC`</span></span>|<span data-ttu-id="66fb7-324">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="66fb7-324">None.</span></span>|<span data-ttu-id="66fb7-325">NULLABLE, PRECISION, SCALE</span><span class="sxs-lookup"><span data-stu-id="66fb7-325">NULLABLE, PRECISION, SCALE</span></span>|  
|<span data-ttu-id="66fb7-326">LOB</span><span class="sxs-lookup"><span data-stu-id="66fb7-326">LOB</span></span>|<span data-ttu-id="66fb7-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT` e `SQLUDT`</span><span class="sxs-lookup"><span data-stu-id="66fb7-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT`, and `SQLUDT`</span></span>|<span data-ttu-id="66fb7-328">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="66fb7-328">None.</span></span>|<span data-ttu-id="66fb7-329">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="66fb7-329">NULLABLE</span></span>|  
|<span data-ttu-id="66fb7-330">LOB caractere</span><span class="sxs-lookup"><span data-stu-id="66fb7-330">Character LOB</span></span>|`SQLNTEXT`|<span data-ttu-id="66fb7-331">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="66fb7-331">None.</span></span>|<span data-ttu-id="66fb7-332">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="66fb7-332">NULLABLE</span></span>|  
|<span data-ttu-id="66fb7-333">Cadeia de caracteres binária</span><span class="sxs-lookup"><span data-stu-id="66fb7-333">Binary string</span></span>|<span data-ttu-id="66fb7-334">`SQLBINARY` e `SQLVARYBIN`</span><span class="sxs-lookup"><span data-stu-id="66fb7-334">`SQLBINARY` and `SQLVARYBIN`</span></span>|<span data-ttu-id="66fb7-335">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="66fb7-335">None.</span></span>|<span data-ttu-id="66fb7-336">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="66fb7-336">NULLABLE, LENGTH</span></span>|  
|<span data-ttu-id="66fb7-337">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="66fb7-337">Character string</span></span>|<span data-ttu-id="66fb7-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR` e `SQLNVARCHAR`</span><span class="sxs-lookup"><span data-stu-id="66fb7-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR`, and `SQLNVARCHAR`</span></span>|<span data-ttu-id="66fb7-339">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="66fb7-339">None.</span></span>|<span data-ttu-id="66fb7-340">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="66fb7-340">NULLABLE, LENGTH</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="66fb7-341">Para exportar ou importar dados SQLXML em massa, use um dos tipos de dados a seguir em seu arquivo de formato: SQLCHAR ou SQLVARYCHAR (os dados são enviados na página de código do cliente ou na página de código implícita pela ordenação), SQLNCHAR ou SQLNVARCHAR (os dados são enviados como Unicode), ou SQLBINARY ou SQLVARYBIN (os dados são enviados sem nenhuma conversão).</span><span class="sxs-lookup"><span data-stu-id="66fb7-341">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
 <span data-ttu-id="66fb7-342">Para obter mais informações sobre os tipo de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , veja [Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="66fb7-342">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
###  <a name="how-bulk-import-uses-the-row-element"></a><a name="HowUsesROW"></a> <span data-ttu-id="66fb7-343">Como a importação em massa usa o elemento \<ROW></span><span class="sxs-lookup"><span data-stu-id="66fb7-343">How Bulk Import Uses the \<ROW> Element</span></span>  
 <span data-ttu-id="66fb7-344">O elemento \<ROW> é ignorado em alguns contextos.</span><span class="sxs-lookup"><span data-stu-id="66fb7-344">The \<ROW> element is ignored in some contexts.</span></span> <span data-ttu-id="66fb7-345">O elemento \<ROW> afeta uma operação de importação em massa dependendo de como a operação é executada:</span><span class="sxs-lookup"><span data-stu-id="66fb7-345">Whether the \<ROW> element affects a bulk-import operation depends on how the operation is performed:</span></span>  
  
-   <span data-ttu-id="66fb7-346">o comando **bcp**</span><span class="sxs-lookup"><span data-stu-id="66fb7-346">the **bcp** command</span></span>  
  
     <span data-ttu-id="66fb7-347">Quando os dados são carregados em uma tabela de destino, o **bcp** ignora o componente \<ROW>.</span><span class="sxs-lookup"><span data-stu-id="66fb7-347">When data is loaded into a target table, **bcp** ignores the \<ROW> component.</span></span> <span data-ttu-id="66fb7-348">Em vez disso, o **bcp** carrega os dados com base nos tipos de coluna da tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="66fb7-348">Instead, **bcp** loads the data based on the column types of the target table.</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)] <span data-ttu-id="66fb7-349">Instruções (BULK INSERT e o provedor de conjuntos de linhas em massa OPENROWSET)</span><span class="sxs-lookup"><span data-stu-id="66fb7-349">statements (BULK INSERT and OPENROWSET's Bulk rowset provider)</span></span>  
  
     <span data-ttu-id="66fb7-350">Ao importar dados em massa para uma tabela, as instruções [!INCLUDE[tsql](../../../includes/tsql-md.md)] usam o componente \<ROW> para gerar o conjunto de linhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="66fb7-350">When bulk importing data into a table, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements use the \<ROW> component to generate the input rowset.</span></span> <span data-ttu-id="66fb7-351">Além disso, as instruções [!INCLUDE[tsql](../../../includes/tsql-md.md)] executam conversões de tipo apropriadas com base nos tipos de coluna especificados em \<ROW> e na coluna correspondente na tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="66fb7-351">Also, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements perform appropriate type conversions based on the column types specified under \<ROW> and the corresponding column in the target table.</span></span> <span data-ttu-id="66fb7-352">Se houver uma incompatibilidade entre os tipos de coluna como especificado no arquivo de formato e na tabela de destino, ocorrerá uma conversão extra de tipo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-352">If a mismatch exists between column types as specified in the format file and in the target table, an extra type conversion occurs.</span></span> <span data-ttu-id="66fb7-353">Essa conversão extra do tipo pode levar a alguma discrepância (ou seja, uma perda de precisão) de comportamento no provedor do conjunto de linhas em massa do BULK INSERT ou do OPENROWSET quando comparado com o **bcp**.</span><span class="sxs-lookup"><span data-stu-id="66fb7-353">This extra type conversion may lead to some discrepancy (that is, a loss of precision) in behavior in BULK INSERT or OPENROWSET's Bulk rowset provider as compared to **bcp**.</span></span>  
  
     <span data-ttu-id="66fb7-354">As informações no elemento \<ROW> permitem construir uma linha sem precisar de informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="66fb7-354">The information in the \<ROW> element allows a row to be constructed without requiring any additional information.</span></span> <span data-ttu-id="66fb7-355">Por isso, você pode gerar um conjunto de linhas com a instrução SELECT (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span><span class="sxs-lookup"><span data-stu-id="66fb7-355">For this reason, you can generate a rowset using a SELECT statement (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="66fb7-356">A cláusula OPENROWSET BULK requer um arquivo de formato (observe que a conversão do tipo de dados de campo ao tipo de dados de uma coluna só é disponibilizada com um arquivo de formato XML).</span><span class="sxs-lookup"><span data-stu-id="66fb7-356">The OPENROWSET BULK clause requires a format file (note that converting from the data type of the field to the data type of a column is available only with an XML format file).</span></span>  
  
###  <a name="how-bulk-import-uses-the-column-element"></a><a name="HowUsesColumn"></a> <span data-ttu-id="66fb7-357">Como a importação em massa usa o elemento \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="66fb7-357">How Bulk Import Uses the \<COLUMN> Element</span></span>  
 <span data-ttu-id="66fb7-358">Para importar dados em massa em uma tabela, os elementos \<COLUMN> em um arquivo de formato mapeiam um campo de arquivo de dados para as colunas da tabela, especificando:</span><span class="sxs-lookup"><span data-stu-id="66fb7-358">For bulk importing data into a table, the \<COLUMN> elements in a format file map a data-file field to table columns by specifying:</span></span>  
  
-   <span data-ttu-id="66fb7-359">A posição de cada campo dentro de uma linha no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-359">The position of each field within a row in the data file.</span></span>  
  
-   <span data-ttu-id="66fb7-360">O tipo de coluna usado para converter o tipo de dados de campo ao tipo de dados de coluna desejado.</span><span class="sxs-lookup"><span data-stu-id="66fb7-360">The column type, which is used to convert the field data type to the desired column data type.</span></span>  
  
 <span data-ttu-id="66fb7-361">Se nenhuma coluna for mapeada para um campo, o campo não será copiado na(s) linha(s) gerada(s).</span><span class="sxs-lookup"><span data-stu-id="66fb7-361">If no column is mapped to a field, the field is not copied into the generated row(s).</span></span> <span data-ttu-id="66fb7-362">Esse comportamento permite que um arquivo de dados gere linhas com colunas diferentes (em tabelas diferentes).</span><span class="sxs-lookup"><span data-stu-id="66fb7-362">This behavior allows a data file to generate rows with different columns (in different tables).</span></span>  
  
 <span data-ttu-id="66fb7-363">Do mesmo modo, para exportar dados em massa de uma tabela, cada \<COLUMN> no arquivo de formato mapeia a coluna da linha da tabela de entrada para o seu campo correspondente no arquivo de dados de saída.</span><span class="sxs-lookup"><span data-stu-id="66fb7-363">Similarly, for bulk exporting data from a table, each \<COLUMN> in the format file maps the column from the input table row to its corresponding field in the output data file.</span></span>  
  
###  <a name="putting-the-xsitype-value-into-a-data-set"></a><a name="PutXsiTypeValueIntoDataSet"></a> <span data-ttu-id="66fb7-364">Colocando o valor de xsi:type em um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="66fb7-364">Putting the xsi:type Value into a Data Set</span></span>  
 <span data-ttu-id="66fb7-365">Quando um documento XML é validado com a linguagem XSD (XML Schema Definition), o valor de xsi:type não é colocado no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-365">When an XML document is validated through the XML Schema Definition (XSD) language, the xsi:type value is not put into the data set.</span></span> <span data-ttu-id="66fb7-366">Porém, você pode colocar a informações de xsi:type no conjunto de dados carregando o arquivo de formato XML em um documento XML (por exemplo, `myDoc`), como ilustrado no snippet de código seguinte:</span><span class="sxs-lookup"><span data-stu-id="66fb7-366">However, you can put the xsi:type information into the data set by loading the XML format file into an XML document (for example, `myDoc`), as illustrated in the following code snippet:</span></span>  
  
```  
...;  
myDoc.LoadXml(xmlFormat);  
XmlNodeList ColumnList = myDoc.GetElementsByTagName("COLUMN");  
for(int i=0;i<ColumnList.Count;i++)  
{  
   Console.Write("COLUMN: xsi:type=" +ColumnList[i].Attributes["type",  
      "http://www.w3.org/2001/XMLSchema-instance"].Value+"\n");  
}  
```  
  
##  <a name="sample-xml-format-files"></a><a name="SampleXmlFFs"></a> <span data-ttu-id="66fb7-367">Arquivos de formato XML de exemplo</span><span class="sxs-lookup"><span data-stu-id="66fb7-367">Sample XML Format Files</span></span>  
 <span data-ttu-id="66fb7-368">Esta seção contém informações sobre como usar arquivos no formato XML em uma variedade de casos, inclusive um exemplo de [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66fb7-368">This section contains information on using XML format files in a variety of cases, including an [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66fb7-369">Nos arquivos de dados mostrados nos exemplos a seguir, `<tab>` indica um caractere de tabulação em um arquivo de dados e `<return>` indica um retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="66fb7-369">In the data files shown in the following examples, `<tab>` indicates a tab character in a data file, and `<return>` indicates a carriage return.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="66fb7-370">Para obter informações sobre como criar arquivos de formato, veja [Criar um arquivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="66fb7-370">For information about how to create format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="a-ordering-character-data-fields-the-same-as-table-columns"></a><a name="OrderCharFieldsSameAsCols"></a> <span data-ttu-id="66fb7-371">A.</span><span class="sxs-lookup"><span data-stu-id="66fb7-371">A.</span></span> <span data-ttu-id="66fb7-372">Ordenar campos de dados de caracteres da mesma forma que colunas de tabelas</span><span class="sxs-lookup"><span data-stu-id="66fb7-372">Ordering character-data fields the same as table columns</span></span>  
 <span data-ttu-id="66fb7-373">O exemplo a seguir mostra um arquivo de formato XML que descreve um arquivo de dados com três campos de dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="66fb7-373">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="66fb7-374">O arquivo de formato mapeia o arquivo de dados para uma tabela que contém três colunas.</span><span class="sxs-lookup"><span data-stu-id="66fb7-374">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="66fb7-375">Os campos de dados correspondem um a um às colunas da tabela.</span><span class="sxs-lookup"><span data-stu-id="66fb7-375">The data fields correspond one-to-one with the columns of the table.</span></span>  
  
 <span data-ttu-id="66fb7-376">**Tabela (linha):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="66fb7-376">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="66fb7-377">**Arquivo de dados (registro):** Age\<tab>Firstname\<tab>Lastname\<return></span><span class="sxs-lookup"><span data-stu-id="66fb7-377">**Data file (record):** Age\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="66fb7-378">O arquivo de formato XML a seguir grava do arquivo de dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="66fb7-378">The following XML format file reads from the data file to the table.</span></span>  
  
 <span data-ttu-id="66fb7-379">No elemento `<RECORD>` , o arquivo de formato representa os valores de dados em todos os três campos como dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="66fb7-379">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span> <span data-ttu-id="66fb7-380">Para cada campo, o atributo `TERMINATOR` indica o terminador que segue o valor dos dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-380">For each field, the `TERMINATOR` attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="66fb7-381">Os campos de dados correspondem um a um às colunas da tabela.</span><span class="sxs-lookup"><span data-stu-id="66fb7-381">The data fields correspond one-to-one with the columns of the table.</span></span> <span data-ttu-id="66fb7-382">No elemento `<ROW>` , o arquivo de formato mapeia a coluna `Age` para o primeiro campo, a coluna `FirstName` para o segundo campo e a coluna `LastName` para o terceiro campo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-382">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the second field, and the column `LastName` to the third field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>   
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="2" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="3" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="66fb7-383">Para obter um exemplo equivalente de [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , veja [Criar um arquivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="66fb7-383">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="b-ordering-data-fields-and-table-columns-differently"></a><a name="OrderFieldsAndColsDifferently"></a> <span data-ttu-id="66fb7-384">B.</span><span class="sxs-lookup"><span data-stu-id="66fb7-384">B.</span></span> <span data-ttu-id="66fb7-385">Ordenar campos de dados e colunas de tabela diferentemente</span><span class="sxs-lookup"><span data-stu-id="66fb7-385">Ordering data fields and table columns differently</span></span>  
 <span data-ttu-id="66fb7-386">O exemplo a seguir mostra um arquivo de formato XML que descreve um arquivo de dados com três campos de dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="66fb7-386">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="66fb7-387">O arquivo de formato mapeia o arquivo de dados para uma tabela que contém três colunas ordenadas diferentemente dos campos do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-387">The format file maps the data file to a table that contains three columns that are ordered differently from the fields of the data file.</span></span>  
  
 <span data-ttu-id="66fb7-388">**Tabela (linha):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="66fb7-388">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="66fb7-389">**Arquivo de dados** (registro): Age\<tab>Lastname\<tab>Firstname\<return></span><span class="sxs-lookup"><span data-stu-id="66fb7-389">**Data file** (record): Age\<tab>Lastname\<tab>Firstname\<return></span></span>  
  
 <span data-ttu-id="66fb7-390">No elemento `<RECORD>` , o arquivo de formato representa os valores de dados em todos os três campos como dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="66fb7-390">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span>  
  
 <span data-ttu-id="66fb7-391">No elemento `<ROW>` , o arquivo de formato mapeia a coluna `Age` para o primeiro campo, a coluna `FirstName` para o terceiro campo e a coluna `LastName` para o segundo campo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-391">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the second field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="2" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="66fb7-392">Para obter um exemplo equivalente de [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , veja [Usar um arquivo de formato para mapear colunas de uma tabela para campos de arquivo de dados &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="66fb7-392">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span></span>  
  
### <a name="c-omitting-a-data-field"></a><span data-ttu-id="66fb7-393">C.</span><span class="sxs-lookup"><span data-stu-id="66fb7-393">C.</span></span> <span data-ttu-id="66fb7-394">Omitir um campo de dados</span><span class="sxs-lookup"><span data-stu-id="66fb7-394">Omitting a data field</span></span>  
 <span data-ttu-id="66fb7-395">O exemplo a seguir mostra um arquivo de formato XML que descreve um arquivo de dados com quatro campos de dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="66fb7-395">The following example shows an XML format file that describes a data file containing four fields of character data.</span></span> <span data-ttu-id="66fb7-396">O arquivo de formato mapeia o arquivo de dados para uma tabela que contém três colunas.</span><span class="sxs-lookup"><span data-stu-id="66fb7-396">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="66fb7-397">O segundo campo de dados não corresponde a nenhuma coluna de tabela.</span><span class="sxs-lookup"><span data-stu-id="66fb7-397">The second data field does not correspond to any table column.</span></span>  
  
 <span data-ttu-id="66fb7-398">**Tabela (linha):** Person (Age int, FirstName Varchar(20), LastName Varchar(30))</span><span class="sxs-lookup"><span data-stu-id="66fb7-398">**Table (row):** Person (Age int, FirstName Varchar(20), LastName Varchar(30))</span></span>  
  
 <span data-ttu-id="66fb7-399">**Arquivo de dados (registro):** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span><span class="sxs-lookup"><span data-stu-id="66fb7-399">**Data file (record):** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="66fb7-400">No elemento `<RECORD>` , o arquivo de formato representa os valores de dados em todos os quatro campos como dados de caractere.</span><span class="sxs-lookup"><span data-stu-id="66fb7-400">In the `<RECORD>` element, the format file represents the data values in all four fields as character data.</span></span> <span data-ttu-id="66fb7-401">Para cada campo, o atributo TERMINATOR indica o terminador que segue o valor dos dados.</span><span class="sxs-lookup"><span data-stu-id="66fb7-401">For each field, the TERMINATOR attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="66fb7-402">No elemento `<ROW>` , o arquivo de formato mapeia a coluna `Age` para o primeiro campo, a coluna `FirstName` para o terceiro campo e a coluna `LastName` para o quarto campo.</span><span class="sxs-lookup"><span data-stu-id="66fb7-402">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the fourth field.</span></span>  
  
```  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="10"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="4" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="66fb7-403">Para obter um exemplo equivalente de [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , veja [Usar um arquivo de formato para ignorar um campo de dados &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="66fb7-403">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md).</span></span>  
  
###  <a name="d-mapping-field-xsitype-to-column-xsitype"></a><a name="MapXSItype"></a> <span data-ttu-id="66fb7-404">D.</span><span class="sxs-lookup"><span data-stu-id="66fb7-404">D.</span></span> <span data-ttu-id="66fb7-405">Mapeando \<FIELD> xsi:type para \<COLUMN> xsi:type</span><span class="sxs-lookup"><span data-stu-id="66fb7-405">Mapping \<FIELD> xsi:type to \<COLUMN> xsi:type</span></span>  
 <span data-ttu-id="66fb7-406">O exemplo a seguir mostra tipos diferentes de campos e seu mapeamento para colunas.</span><span class="sxs-lookup"><span data-stu-id="66fb7-406">The following example shows different types of fields and their mappings to columns.</span></span>  
  
```  
<?xml version = "1.0"?>  
<BCPFORMAT  
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   <RECORD>  
      <FIELD xsi:type="CharTerm" ID="C1" TERMINATOR="\t"   
            MAX_LENGTH="4"/>  
      <FIELD xsi:type="CharFixed" ID="C2" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="CharPrefix" ID="C3" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharTerm" ID="C4" TERMINATOR="\t"   
         MAX_LENGTH="4"/>  
      <FIELD xsi:type="NCharFixed" ID="C5" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharPrefix" ID="C6" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NativeFixed" ID="C7" LENGTH="4"/>  
   </RECORD>  
   <ROW>  
      <COLUMN SOURCE="C1" NAME="Age" xsi:type="SQLTINYINT"/>  
      <COLUMN SOURCE="C2" NAME="FirstName" xsi:type="SQLVARYCHAR"   
      LENGTH="16" NULLABLE="NO"/>  
      <COLUMN SOURCE="C3" NAME="LastName" />  
      <COLUMN SOURCE="C4" NAME="Salary" xsi:type="SQLMONEY"/>  
      <COLUMN SOURCE="C5" NAME="Picture" xsi:type="SQLIMAGE"/>  
      <COLUMN SOURCE="C6" NAME="Bio" xsi:type="SQLTEXT"/>  
      <COLUMN SOURCE="C7" NAME="Interest"xsi:type="SQLDECIMAL"   
      PRECISION="5" SCALE="3"/>  
   </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="e-mapping-xml-data-to-a-table"></a><a name="MapXMLDataToTbl"></a> <span data-ttu-id="66fb7-407">E.</span><span class="sxs-lookup"><span data-stu-id="66fb7-407">E.</span></span> <span data-ttu-id="66fb7-408">Mapear dados XML para uma tabela</span><span class="sxs-lookup"><span data-stu-id="66fb7-408">Mapping XML data to a table</span></span>  
 <span data-ttu-id="66fb7-409">O exemplo a seguir cria uma tabela de duas colunas vazias (`t_xml`), na qual a primeira coluna mapeia para o tipo de dados `int` e a segunda coluna mapeia para o tipo de dados `xml` .</span><span class="sxs-lookup"><span data-stu-id="66fb7-409">The following example creates an empty two-column table (`t_xml`), in which the first column maps to the `int` data type and the second column maps to the `xml` data type.</span></span>  
  
```  
CREATE TABLE t_xml (c1 int, c2 xml)  
```  
  
 <span data-ttu-id="66fb7-410">O arquivo de formato XML a seguir carrega um arquivo de dados na tabela `t_xml`.</span><span class="sxs-lookup"><span data-stu-id="66fb7-410">The following XML format file would load a data file into table `t_xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" PREFIX_LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="8"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="c1" xsi:type="SQLINT"/>  
  <COLUMN SOURCE="2" NAME="c2" xsi:type="SQLNCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="f-importing-fixed-length-or-fixed-width-fields"></a><a name="ImportFixedFields"></a> <span data-ttu-id="66fb7-411">F.</span><span class="sxs-lookup"><span data-stu-id="66fb7-411">F.</span></span> <span data-ttu-id="66fb7-412">Importar campos de comprimento fixo ou de largura fixa</span><span class="sxs-lookup"><span data-stu-id="66fb7-412">Importing fixed-length or fixed-width fields</span></span>  
 <span data-ttu-id="66fb7-413">O exemplo a seguir descreve campos fixos de `10` ou de `6` caracteres cada.</span><span class="sxs-lookup"><span data-stu-id="66fb7-413">The following example describes fixed fields of `10` or `6` characters each.</span></span> <span data-ttu-id="66fb7-414">O arquivo de formato representa o comprimento/largura desses campos como `LENGTH="10"` e `LENGTH="6"`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="66fb7-414">The format file represents these field lengths/widths as `LENGTH="10"` and `LENGTH="6"`, respectively.</span></span> <span data-ttu-id="66fb7-415">Cada linha dos arquivos de dados termina com uma combinação de alimentação de linha de retorno de carro, {CR}{LF}, que o arquivo de formato representa como `TERMINATOR="\r\n"`.</span><span class="sxs-lookup"><span data-stu-id="66fb7-415">Every row of the data files ends with a carriage return-line feed combination, {CR}{LF}, which the format file represents as `TERMINATOR="\r\n"`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT  
       xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharFixed" LENGTH="10"/>  
    <FIELD ID="2" xsi:type="CharFixed" LENGTH="6"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="C1" xsi:type="SQLINT" />  
    <COLUMN SOURCE="2" NAME="C2" xsi:type="SQLINT" />  
  </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="additional-examples"></a><a name="AdditionalExamples"></a> <span data-ttu-id="66fb7-416">Exemplos adicionais</span><span class="sxs-lookup"><span data-stu-id="66fb7-416">Additional Examples</span></span>  
 <span data-ttu-id="66fb7-417">Para obter exemplos adicionais de arquivos de formato não XML e arquivos de formato XML, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="66fb7-417">For additional examples of both non-XML format files and XML format files, see the following topics:</span></span>  
  
-   [<span data-ttu-id="66fb7-418">Usar um arquivo de formato para ignorar uma coluna de tabela &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb7-418">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="66fb7-419">Usar um arquivo de formato para ignorar um campo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb7-419">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="66fb7-420">Usar um arquivo de formato para mapear colunas de uma tabela para campos de arquivo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb7-420">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="66fb7-421">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="66fb7-421">Related Tasks</span></span>  
  
-   [<span data-ttu-id="66fb7-422">Criar um arquivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb7-422">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="66fb7-423">Usar um arquivo de formato para importação em massa de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb7-423">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="66fb7-424">Usar um arquivo de formato para ignorar uma coluna de tabela &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb7-424">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="66fb7-425">Usar um arquivo de formato para ignorar um campo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb7-425">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="66fb7-426">Usar um arquivo de formato para mapear colunas de uma tabela para campos de arquivo de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb7-426">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="66fb7-427">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="66fb7-427">Related Content</span></span>  
 <span data-ttu-id="66fb7-428">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="66fb7-428">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66fb7-429">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="66fb7-429">See Also</span></span>  
 <span data-ttu-id="66fb7-430">[Importação e exportação em massa de dados &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="66fb7-430">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="66fb7-431">[Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="66fb7-431">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="66fb7-432">[Arquivos de formato não XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="66fb7-432">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="66fb7-433">Arquivos de formato para importação ou exportação de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66fb7-433">Format Files for Importing or Exporting Data &#40;SQL Server&#41;</span></span>](format-files-for-importing-or-exporting-data-sql-server.md)  
  
  
