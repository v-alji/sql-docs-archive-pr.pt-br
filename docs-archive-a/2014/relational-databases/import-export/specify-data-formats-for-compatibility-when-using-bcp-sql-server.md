---
title: Especificar formatos de dados para compatibilidade usando bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], compatibility
- bulk importing [SQL Server], compatibility
- compatibility [SQL Server], data formats
- data formats [SQL Server], compatibility
- bcp utility [SQL Server], compatibility
ms.assetid: cd5fc8c8-eab1-4165-9468-384f31e53f0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d12456760f32ddbd8cc434d474aebb0e0ecf141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684228"
---
# <a name="specify-data-formats-for-compatibility-when-using-bcp-sql-server"></a><span data-ttu-id="326f8-102">Especificar formatos de dados para compatibilidade usando bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="326f8-102">Specify Data Formats for Compatibility when Using bcp (SQL Server)</span></span>
  <span data-ttu-id="326f8-103">Este tópico descreve os atributos de formato de dados, os prompts específicos de campo e o armazenamento de dados campo por campo em um arquivo de formato não XML do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `bcp` comando.</span><span class="sxs-lookup"><span data-stu-id="326f8-103">This topic describes the data-format attributes, field-specific prompts, and storing field-by-field data in a non-xml format file of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`bcp` command.</span></span> <span data-ttu-id="326f8-104">Conhecê-los pode ser útil para exportar dados em massa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para importação em massa para outro programa, como outro programa de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="326f8-104">Understanding these can be helpful when you bulk export [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data for bulk import into another program, such as another database program.</span></span> <span data-ttu-id="326f8-105">Os formatos de dados padrão (nativo, caractere ou Unicode) na tabela de fonte poderiam ser incompatíveis com o layout de dados esperado por outro programa. Se uma incompatibilidade existir, quando você exportar os dados você deve descrever o layout dos dados.</span><span class="sxs-lookup"><span data-stu-id="326f8-105">The default data formats (native, character, or Unicode) in the source table might be incompatible with the data layout expected by the other program If an incompatibility exists, when you export the data, you must describe the data layout.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="326f8-106">Se você não estiver familiarizado com os formatos de dados para importar ou exportar dados, veja [Formatos de dados para importação ou exportação em massa &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="326f8-106">If you are unfamiliar with data formats for importing or exporting data, see [Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span></span>  
  
 <span data-ttu-id="326f8-107">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="326f8-107">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="326f8-108">Atributos de formato de dados BCP</span><span class="sxs-lookup"><span data-stu-id="326f8-108">bcp Data-Format Attributes</span></span>](#bcpDataFormatAttr)  
  
-   [<span data-ttu-id="326f8-109">Visão geral dos prompts específicos de campo</span><span class="sxs-lookup"><span data-stu-id="326f8-109">Overview of the Field-Specific Prompts</span></span>](#FieldSpecificPrompts)  
  
-   [<span data-ttu-id="326f8-110">Armazenando dados Field-by-Field em um arquivo de formato não XML</span><span class="sxs-lookup"><span data-stu-id="326f8-110">Storing Field-by-Field Data in a Non-XML Format File</span></span>](#FieldByFieldNonXmlFF)  
  
-   [<span data-ttu-id="326f8-111">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="326f8-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="bcp-data-format-attributes"></a><a name="bcpDataFormatAttr"></a> <span data-ttu-id="326f8-112">Atributos bcp Data-Format</span><span class="sxs-lookup"><span data-stu-id="326f8-112">bcp Data-Format Attributes</span></span>  
 <span data-ttu-id="326f8-113">O comando `bcp` permite especificar a estrutura de cada campo em um arquivo de dados quanto aos atributos de formato de dados a seguir:</span><span class="sxs-lookup"><span data-stu-id="326f8-113">The `bcp` command allows you to specify the structure of each field in a data file in terms of the following data-format attributes:</span></span>  
  
-   <span data-ttu-id="326f8-114">tipo de armazenamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="326f8-114">File storage type</span></span>  
  
     <span data-ttu-id="326f8-115">O *tipo de armazenamento de arquivo* descreve como são armazenados os dados no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="326f8-115">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="326f8-116">Podem ser exportados dados para um arquivo de dados como seu tipo de tabela de banco de dados (formato nativo), em sua representação de caractere (formato de caractere), ou como qualquer tipo de dados onde há suporte para conversão implícita; por exemplo, copiando um `smallint` como um `int`.</span><span class="sxs-lookup"><span data-stu-id="326f8-116">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="326f8-117">Os tipos de dados definidos pelo usuário como tipos básicos são exportados.</span><span class="sxs-lookup"><span data-stu-id="326f8-117">User-defined data types are exported as their base types.</span></span> <span data-ttu-id="326f8-118">Para obter mais informações, veja [Especificar tipo de armazenamento de arquivo usando bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="326f8-118">For more information, see [Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="326f8-119">Comprimento do prefixo</span><span class="sxs-lookup"><span data-stu-id="326f8-119">Prefix length</span></span>  
  
     <span data-ttu-id="326f8-120">Para fornecer o armazenamento de arquivo mais compacto para a exportação de dados em massa em formato nativo para um arquivo de dados, o comando `bcp` precede cada campo com um ou mais caracteres que indica o comprimento do campo.</span><span class="sxs-lookup"><span data-stu-id="326f8-120">To provide the most compact file storage for the bulk export of data in native format to a data file, the `bcp` command precedes each field with one or more characters that indicates the length of the field.</span></span> <span data-ttu-id="326f8-121">Esses caracteres são chamados *caracteres de prefixo de comprimento*.</span><span class="sxs-lookup"><span data-stu-id="326f8-121">These characters are called *length prefix characters*.</span></span> <span data-ttu-id="326f8-122">Para obter mais informações, veja [Especificar o tamanho de prefixo em arquivos de dados usando bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="326f8-122">For more information, see [Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="326f8-123">Tamanho do campo</span><span class="sxs-lookup"><span data-stu-id="326f8-123">Field length</span></span>  
  
     <span data-ttu-id="326f8-124">O tamanho do campo indica o número máximo de caracteres que são exigidos para representar dados em formato de caractere.</span><span class="sxs-lookup"><span data-stu-id="326f8-124">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="326f8-125">O tamanho do campo já é conhecido se os dados forem armazenados no formato nativo.</span><span class="sxs-lookup"><span data-stu-id="326f8-125">The field length is already known if the data is stored in the native format.</span></span> <span data-ttu-id="326f8-126">Para obter mais informações, veja [Especificar tamanho do campo usando bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="326f8-126">For more information, see [Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="326f8-127">Terminador de campo</span><span class="sxs-lookup"><span data-stu-id="326f8-127">Field terminator</span></span>  
  
     <span data-ttu-id="326f8-128">Para campos de dados de caractere, caracteres terminadores opcionais permitem marcar o término de cada campo em um arquivo de dados (usando um *terminador de campo*) e o término de cada linha (usando um *terminador de linha*).</span><span class="sxs-lookup"><span data-stu-id="326f8-128">For character data fields, optional terminating characters allow you to mark the end of each field in a data file (using a *field terminator*) and the end of each row (using a *row terminator*).</span></span> <span data-ttu-id="326f8-129">Os caracteres terminadores são um modo de indicar aos programas de leitura o arquivo de dados onde um campo ou uma linha termina, e a outra começa.</span><span class="sxs-lookup"><span data-stu-id="326f8-129">Terminating characters are one way to indicate to programs reading the data file where one field or row ends and another begins.</span></span> <span data-ttu-id="326f8-130">Para obter mais informações, veja [Especificar terminadores de campo e linha &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="326f8-130">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
##  <a name="overview-of-the-field-specific-prompts"></a><a name="FieldSpecificPrompts"></a> <span data-ttu-id="326f8-131">Visão geral dos prompts de campo específicos</span><span class="sxs-lookup"><span data-stu-id="326f8-131">Overview of the Field-Specific Prompts</span></span>  
 <span data-ttu-id="326f8-132">Se um `bcp` comando interativo contiver a opção **in** ou **out** , mas também não contiver a opção de arquivo de formato (**-f**) ou uma opção de formato de dados (**-n**, **-c**, **-w**ou **-n**), cada coluna na tabela de origem ou de destino, o comando solicitará cada um dos atributos anteriores, por sua vez.</span><span class="sxs-lookup"><span data-stu-id="326f8-132">If an interactive `bcp` command contains the **in** or **out** option but does not also contain either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**),  each column in the source or target table, the command prompts for each of the preceding attributes, in turn.</span></span> <span data-ttu-id="326f8-133">Em cada prompt, o comando `bcp` fornece um valor padrão baseado no tipo de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da coluna de tabela.</span><span class="sxs-lookup"><span data-stu-id="326f8-133">In each prompt, the `bcp` command provides a default value based on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the table column.</span></span> <span data-ttu-id="326f8-134">Aceitar o valor padrão de todos os prompts gera o mesmo resultado de especificar o formato nativo ( **-n**) na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="326f8-134">Accepting the default value for all of the prompts produces the same result as specifying native format (**-n**) on the command line.</span></span> <span data-ttu-id="326f8-135">Cada prompt exibe um valor padrão entre colchetes: [*default*].</span><span class="sxs-lookup"><span data-stu-id="326f8-135">Each prompt displays a default value in brackets: [*default*].</span></span> <span data-ttu-id="326f8-136">Pressionando ENTER aceita o padrão exibido.</span><span class="sxs-lookup"><span data-stu-id="326f8-136">Pressing ENTER accepts the displayed default.</span></span> <span data-ttu-id="326f8-137">Para especificar um valor diferente do padrão, insira o valor novo no prompt.</span><span class="sxs-lookup"><span data-stu-id="326f8-137">To specify a value other than the default, enter the new value at the prompt.</span></span>  
  
### <a name="example"></a><span data-ttu-id="326f8-138">Exemplo</span><span class="sxs-lookup"><span data-stu-id="326f8-138">Example</span></span>  
 <span data-ttu-id="326f8-139">Os exemplos a seguir usam o comando `bcp` para exportar em massa dados da tabela `HumanResources.myTeam` para o arquivo `myTeam.txt` interativamente.</span><span class="sxs-lookup"><span data-stu-id="326f8-139">The following example uses the `bcp` command to bulk export data from the `HumanResources.myTeam` table interactively to the `myTeam.txt` file.</span></span> <span data-ttu-id="326f8-140">Antes de executar o exemplo, é necessário criar essa tabela.</span><span class="sxs-lookup"><span data-stu-id="326f8-140">Before you can run the example, you must create this table.</span></span> <span data-ttu-id="326f8-141">Para obter informações sobre a tabela e como criá-la, veja [Tabela de exemplo HumanResources.myTeam &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="326f8-141">For information about the table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
 <span data-ttu-id="326f8-142">O comando não especifica nem um arquivo de formato nem um tipo de dados, fazendo com que o `bcp` solicite informações de formato de dados.</span><span class="sxs-lookup"><span data-stu-id="326f8-142">The command specifies neither a format file nor a data type, causing `bcp` to prompt for data-format information.</span></span> <span data-ttu-id="326f8-143">No prompt de comando do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="326f8-143">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam out myTeam.txt -T  
```  
  
 <span data-ttu-id="326f8-144">Para cada coluna, o bcp solicita os valores de campo específicos.</span><span class="sxs-lookup"><span data-stu-id="326f8-144">For each column, bcp prompts for field-specific values.</span></span> <span data-ttu-id="326f8-145">O exemplo seguinte mostra os prompts de campo especifico para as colunas `EmployeeID` e `Name` da tabela e sugere o tipo de armazenamento de arquivo padrão (o formato nativo) para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="326f8-145">The following example shows the field-specific prompts for the `EmployeeID` and `Name` columns of the table, and suggests the default file storage type (the native format) for each column.</span></span> <span data-ttu-id="326f8-146">Os comprimentos dos prefixos do `EmployeeID` e coluna `Name` são 0 e 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="326f8-146">The prefix lengths of the `EmployeeID` and `Name` column are 0 and 2, respectively.</span></span> <span data-ttu-id="326f8-147">O usuário especifica uma vírgula (`,`) como terminador de cada campo.</span><span class="sxs-lookup"><span data-stu-id="326f8-147">The user specifies a comma (`,`) as the terminator of each field.</span></span>  
  
 `Enter the file storage type of field EmployeeID [smallint]:`  
  
 `Enter prefix-length of field EmployeeID [0]:`  
  
 `Enter field terminator [none]:,`  
  
 `Enter the file storage type of field Name [nvarchar]:`  
  
 `Enter prefix length of field Name [2]:`  
  
 `Enter field terminator [none]:,`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 <span data-ttu-id="326f8-148">São exibidos prompts equivalentes (quando necessário) para cada uma das colunas de tabela em ordem.</span><span class="sxs-lookup"><span data-stu-id="326f8-148">Equivalent prompts (as needed) are displayed for each of the table columns in order.</span></span>  
  
##  <a name="storing-field-by-field-data-in-a-non-xml-format-file"></a><a name="FieldByFieldNonXmlFF"></a> <span data-ttu-id="326f8-149">Armazenando dados campo por campo em um arquivo de formato não XML</span><span class="sxs-lookup"><span data-stu-id="326f8-149">Storing Field-by-Field Data in a Non-XML Format File</span></span>  
 <span data-ttu-id="326f8-150">Após todas as colunas de tabela serem especificadas, o comando `bcp` solicita que você gere um arquivo de formato não XML que armazena a informações campo por campo fornecidas (veja o exemplo anterior) opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="326f8-150">After all of the table columns are specified, the `bcp` command prompts you to optionally generate a non-XML format file that stores the field-by-field information just supplied (see the preceding example).</span></span> <span data-ttu-id="326f8-151">Se você escolher gerar um arquivo de formato, você poderá sempre que exportar dados fora daquela tabela ou importar dados estruturados em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="326f8-151">If you choose to generate a format file, you can whenever you export data out of that table or import like-structured data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="326f8-152">Você pode usar o arquivo de formato para importação em massa de um arquivo de dados em uma instância [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para exportar dados em massa da tabela sem precisar especificar o formato.</span><span class="sxs-lookup"><span data-stu-id="326f8-152">You can use the format file to bulk import data from the data file into an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to bulk export data from the table, without needing to respecify the format.</span></span> <span data-ttu-id="326f8-153">Para obter mais informações, consulte [Arquivos de formato para importação ou exportação de dados &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="326f8-153">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="326f8-154">O exemplo a seguir cria um arquivo de formato nomeado não XML `myFormatFile.fmt`:</span><span class="sxs-lookup"><span data-stu-id="326f8-154">The following example creates a non-XML format file named `myFormatFile.fmt`:</span></span>  
  
 `Do you want to save this format information in a file? [Y/n] y`  
  
 `Host filename: [bcp.fmt]myFormatFile.fmt`  
  
 <span data-ttu-id="326f8-155">O nome padrão para o arquivo de formato é bcp.fmt, mas você poderá especificar um nome de arquivo diferente se você preferir.</span><span class="sxs-lookup"><span data-stu-id="326f8-155">The default name for the format file is bcp.fmt, but you can specify a different file name if you choose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="326f8-156">Para um arquivo de dados que usa um único formato de dados para seu tipo de armazenamento de arquivos, como caractere ou formato nativo, você pode criar um arquivo de formato rapidamente sem exportar ou importar dados usando a opção **format** .</span><span class="sxs-lookup"><span data-stu-id="326f8-156">For a data file that uses a single data format for its file-storage type, such as character or native format, you can quickly create a format file without exporting or importing data by using the **format** option.</span></span> <span data-ttu-id="326f8-157">Esta abordagem tem a vantagem de ser fácil e de lhe permitir criar um arquivo formato XML ou um não XML.</span><span class="sxs-lookup"><span data-stu-id="326f8-157">This approach has the advantages of being easy and of allowing you to create either an XML format file or a non-XML format file.</span></span> <span data-ttu-id="326f8-158">Para obter mais informações, consulte [Criar um arquivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="326f8-158">For more information, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="326f8-159">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="326f8-159">Related Tasks</span></span>  
  
-   [<span data-ttu-id="326f8-160">Especificar tipo de armazenamento de arquivo usando bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="326f8-160">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="326f8-161">Especificar o tamanho de prefixo em arquivos de dados usando bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="326f8-161">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="326f8-162">Especificar tamanho do campo usando bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="326f8-162">Specify Field Length by Using bcp &#40;SQL Server&#41;</span></span>](specify-field-length-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="326f8-163">Especificar terminadores de campo e linha &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="326f8-163">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="326f8-164">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="326f8-164">Related Content</span></span>  
 <span data-ttu-id="326f8-165">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="326f8-165">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="326f8-166">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="326f8-166">See Also</span></span>  
 <span data-ttu-id="326f8-167">[Importação e exportação em massa de dados &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="326f8-167">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="326f8-168">[Formatos de dados para importação ou exportação em massa &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="326f8-168">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 <span data-ttu-id="326f8-169">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="326f8-169">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="326f8-170">Tipos de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="326f8-170">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
