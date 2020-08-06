---
title: Especificar tipo de armazenamento do arquivo usando bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bcp utility [SQL Server], file storage types
- importing data, file storage types
- native data format [SQL Server]
- file storage types [SQL Server]
- data formats [SQL Server], file storage types
ms.assetid: 85e12df8-1be7-4bdc-aea9-05aade085c06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1f3ad2a94ffe3e0f1db19a8e66f85497e7143dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570015"
---
# <a name="specify-file-storage-type-by-using-bcp-sql-server"></a><span data-ttu-id="56cd9-102">Especificar tipo de armazenamento de arquivo usando bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="56cd9-102">Specify File Storage Type by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="56cd9-103">O *tipo de armazenamento de arquivo* descreve como são armazenados os dados no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="56cd9-103">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="56cd9-104">Podem ser exportados dados para um arquivo de dados como seu tipo de tabela de banco de dados (formato nativo), em sua representação de caractere (formato de caractere), ou como qualquer tipo de dados onde há suporte para conversão implícita; por exemplo, copiando um `smallint` como um `int`.</span><span class="sxs-lookup"><span data-stu-id="56cd9-104">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="56cd9-105">Os tipos de dados definidos pelo usuário como tipos básicos são exportados.</span><span class="sxs-lookup"><span data-stu-id="56cd9-105">User-defined data types are exported as their base types.</span></span>  
  
## <a name="the-bcp-prompt-for-file-storage-type"></a><span data-ttu-id="56cd9-106">Solicitação de bcp para o tipo de armazenamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="56cd9-106">The bcp Prompt for File Storage Type</span></span>  
 <span data-ttu-id="56cd9-107">Se um comando **bcp** interativo contiver a opção **in** ou **out** sem a opção do arquivo de formatos ( **-f**) ou uma opção do formato de dados ( **-n**, **-c**, **-w**ou **-N**), o comando solicitará o tipo de armazenamento de arquivos de cada campo de dados, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="56cd9-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the file storage type of each data field, as follows:</span></span>  
  
 `Enter the file storage type of field <field_name> [<default>]:`  
  
 <span data-ttu-id="56cd9-108">Sua resposta para esta solicitação depende da tarefa que você executa, como segue:</span><span class="sxs-lookup"><span data-stu-id="56cd9-108">Your response to this prompt depends on the task you perform, as follows:</span></span>  
  
-   <span data-ttu-id="56cd9-109">Para exportar dados em massa de uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para um arquivo de dados no armazenamento mais compacto possível (formato de dados nativo), aceite os tipos de armazenamento de arquivos padrão fornecidos pelo **bcp**.</span><span class="sxs-lookup"><span data-stu-id="56cd9-109">To bulk export data from an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in the most compact storage possible (native data format), accept the default file storage types that are provided by **bcp**.</span></span> <span data-ttu-id="56cd9-110">Para obter uma lista de tipos de armazenamento de arquivos nativos, digite "Tipos de Armazenamento de Arquivos Nativos", mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="56cd9-110">For a list of the native file storage types, see "Native File Storage Types," later in this topic.</span></span>  
  
-   <span data-ttu-id="56cd9-111">Para agrupar dados exportados de uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para um arquivo de dados no formato de caractere, especifique `char` como o tipo de armazenamento de arquivo para todas as colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="56cd9-111">To bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in character format, specify `char` as the file storage type for all columns in the table.</span></span>  
  
-   <span data-ttu-id="56cd9-112">Para agrupar dados importados para uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de um arquivo de dados, especifique o tipo de armazenamento de arquivo como `char` para tipos armazenados no formato de caractere; e para dados armazenados no formato de tipo de dados nativo, especifique um dos tipos de armazenamento de arquivo como apropriado:</span><span class="sxs-lookup"><span data-stu-id="56cd9-112">To bulk import data to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file, specify the file storage type as `char` for types stored in character format and, for data stored in native data type format, specify one of the file storage types, as appropriate:</span></span>  
  
    |<span data-ttu-id="56cd9-113">tipo de armazenamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="56cd9-113">File storage type</span></span>|<span data-ttu-id="56cd9-114">Digite no prompt de comando</span><span class="sxs-lookup"><span data-stu-id="56cd9-114">Enter at command prompt</span></span>|  
    |-----------------------|-----------------------------|  
    |<span data-ttu-id="56cd9-115">`char` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="56cd9-115">`char` <sup>1</sup></span></span>|<span data-ttu-id="56cd9-116">`c`[`har`]</span><span class="sxs-lookup"><span data-stu-id="56cd9-116">`c`[`har`]</span></span>|  
    |`varchar`|`c[har]`|  
    |`nchar`|`w`|  
    |`nvarchar`|`w`|  
    |<span data-ttu-id="56cd9-117">`text` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="56cd9-117">`text` <sup>2</sup></span></span>|<span data-ttu-id="56cd9-118">`T`[`ext`]</span><span class="sxs-lookup"><span data-stu-id="56cd9-118">`T`[`ext`]</span></span>|  
    |`ntext2`|`W`|  
    |`binary`|`x`|  
    |`varbinary`|`x`|  
    |<span data-ttu-id="56cd9-119">`image` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="56cd9-119">`image` <sup>2</sup></span></span>|<span data-ttu-id="56cd9-120">`I`[`mage`]</span><span class="sxs-lookup"><span data-stu-id="56cd9-120">`I`[`mage`]</span></span>|  
    |`datetime`|<span data-ttu-id="56cd9-121">**d[ate]**</span><span class="sxs-lookup"><span data-stu-id="56cd9-121">**d[ate]**</span></span>|  
    |`smalldatetime`|`D`|  
    |`time`|`te`|  
    |`date`|`de`|  
    |`datetime2`|`d2`|  
    |`datetimeoffset`|`do`|  
    |`decimal`|`n`|  
    |`numeric`|`n`|  
    |`float`|<span data-ttu-id="56cd9-122">**f[loat]**</span><span class="sxs-lookup"><span data-stu-id="56cd9-122">**f[loat]**</span></span>|  
    |`real`|`r`|  
    |`Int`|<span data-ttu-id="56cd9-123">**i[nt]**</span><span class="sxs-lookup"><span data-stu-id="56cd9-123">**i[nt]**</span></span>|  
    |`bigint`|`B[igint]`|  
    |`smallint`|<span data-ttu-id="56cd9-124">**s[mallint]**</span><span class="sxs-lookup"><span data-stu-id="56cd9-124">**s[mallint]**</span></span>|  
    |`tinyint`|<span data-ttu-id="56cd9-125">**t[inyint]**</span><span class="sxs-lookup"><span data-stu-id="56cd9-125">**t[inyint]**</span></span>|  
    |`money`|<span data-ttu-id="56cd9-126">**m[oney]**</span><span class="sxs-lookup"><span data-stu-id="56cd9-126">**m[oney]**</span></span>|  
    |`smallmoney`|`M`|  
    |`bit`|`b[it]`|  
    |`uniqueidentifier`|`u`|  
    |`sql_variant`|`V[ariant]`|  
    |`timestamp`|`x`|  
    |<span data-ttu-id="56cd9-127">`UDT` (um tipo de dados definido pelo usuário)</span><span class="sxs-lookup"><span data-stu-id="56cd9-127">`UDT` (a user-defined data type)</span></span>|`U`|  
    |`XML`|`X`|  
  
     <span data-ttu-id="56cd9-128"><sup>1</sup> a interação do tamanho do campo, do comprimento do prefixo e dos terminadores determina a quantidade de espaço de armazenamento alocada em um arquivo de dados para dados não caracteres que são exportados como o `char` tipo de armazenamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="56cd9-128"><sup>1</sup> The interaction of field length, prefix length, and terminators determines the amount of storage space that is allocated in a data file for noncharacter data that is exported as the `char` file storage type.</span></span>  
  
     <span data-ttu-id="56cd9-129"><sup>2</sup> os `ntext` `text` tipos de dados, e `image` serão removidos em uma versão futura do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56cd9-129"><sup>2</sup> The `ntext`, `text`, and `image` data types will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="56cd9-130">No novo projeto de desenvolvimento, evite usar esses tipos de dados e planeje modificar os aplicativos que atualmente os utilizam.</span><span class="sxs-lookup"><span data-stu-id="56cd9-130">In new development work, avoid using these data types, and plan to modify applications that currently use them.</span></span> <span data-ttu-id="56cd9-131">Use `nvarchar(max)` , `varchar(max)` e `varbinary(max)` em vez disso.</span><span class="sxs-lookup"><span data-stu-id="56cd9-131">Use `nvarchar(max)`, `varchar(max)`, and `varbinary(max)` instead.</span></span>  
  
## <a name="native-file-storage-types"></a><span data-ttu-id="56cd9-132">Tipos de armazenamento de arquivos nativos</span><span class="sxs-lookup"><span data-stu-id="56cd9-132">Native File Storage Types</span></span>  
 <span data-ttu-id="56cd9-133">Cada tipo de armazenamento de arquivo nativo é registrado no arquivo de formato como um tipo de dados do arquivo host correspondente.</span><span class="sxs-lookup"><span data-stu-id="56cd9-133">Each native file storage type is recorded in the format file as a corresponding host file data type.</span></span>  
  
|<span data-ttu-id="56cd9-134">tipo de armazenamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="56cd9-134">File storage type</span></span>|<span data-ttu-id="56cd9-135">Tipo de dados do arquivo host</span><span class="sxs-lookup"><span data-stu-id="56cd9-135">Host file data type</span></span>|  
|-----------------------|-------------------------|  
|<span data-ttu-id="56cd9-136">`char` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="56cd9-136">`char` <sup>1</sup></span></span>|<span data-ttu-id="56cd9-137">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="56cd9-137">SQLCHAR</span></span>|  
|`varchar`|<span data-ttu-id="56cd9-138">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="56cd9-138">SQLCHAR</span></span>|  
|`nchar`|<span data-ttu-id="56cd9-139">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="56cd9-139">SQLNCHAR</span></span>|  
|`nvarchar`|<span data-ttu-id="56cd9-140">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="56cd9-140">SQLNCHAR</span></span>|  
|<span data-ttu-id="56cd9-141">`text` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="56cd9-141">`text` <sup>2</sup></span></span>|<span data-ttu-id="56cd9-142">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="56cd9-142">SQLCHAR</span></span>|  
|<span data-ttu-id="56cd9-143">`ntext` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="56cd9-143">`ntext` <sup>2</sup></span></span>|<span data-ttu-id="56cd9-144">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="56cd9-144">SQLNCHAR</span></span>|  
|`binary`|<span data-ttu-id="56cd9-145">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="56cd9-145">SQLBINARY</span></span>|  
|`varbinary`|<span data-ttu-id="56cd9-146">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="56cd9-146">SQLBINARY</span></span>|  
|<span data-ttu-id="56cd9-147">`image` <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="56cd9-147">`image` <sup>2</sup></span></span>|<span data-ttu-id="56cd9-148">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="56cd9-148">SQLBINARY</span></span>|  
|`datetime`|<span data-ttu-id="56cd9-149">SQLDATETIME</span><span class="sxs-lookup"><span data-stu-id="56cd9-149">SQLDATETIME</span></span>|  
|`smalldatetime`|<span data-ttu-id="56cd9-150">SQLDATETIM4</span><span class="sxs-lookup"><span data-stu-id="56cd9-150">SQLDATETIM4</span></span>|  
|`decimal`|<span data-ttu-id="56cd9-151">SQLDECIMAL</span><span class="sxs-lookup"><span data-stu-id="56cd9-151">SQLDECIMAL</span></span>|  
|`numeric`|<span data-ttu-id="56cd9-152">SQLNUMERIC</span><span class="sxs-lookup"><span data-stu-id="56cd9-152">SQLNUMERIC</span></span>|  
|`float`|<span data-ttu-id="56cd9-153">SQLFLT8</span><span class="sxs-lookup"><span data-stu-id="56cd9-153">SQLFLT8</span></span>|  
|`real`|<span data-ttu-id="56cd9-154">SQLFLT4</span><span class="sxs-lookup"><span data-stu-id="56cd9-154">SQLFLT4</span></span>|  
|`int`|<span data-ttu-id="56cd9-155">SQLINT</span><span class="sxs-lookup"><span data-stu-id="56cd9-155">SQLINT</span></span>|  
|`bigint`|<span data-ttu-id="56cd9-156">SQLBIGINT</span><span class="sxs-lookup"><span data-stu-id="56cd9-156">SQLBIGINT</span></span>|  
|`smallint`|<span data-ttu-id="56cd9-157">SQLSMALLINT</span><span class="sxs-lookup"><span data-stu-id="56cd9-157">SQLSMALLINT</span></span>|  
|`tinyint`|<span data-ttu-id="56cd9-158">SQLTINYINT</span><span class="sxs-lookup"><span data-stu-id="56cd9-158">SQLTINYINT</span></span>|  
|`money`|<span data-ttu-id="56cd9-159">SQLMONEY</span><span class="sxs-lookup"><span data-stu-id="56cd9-159">SQLMONEY</span></span>|  
|`smallmoney`|<span data-ttu-id="56cd9-160">SQLMONEY4</span><span class="sxs-lookup"><span data-stu-id="56cd9-160">SQLMONEY4</span></span>|  
|`bit`|<span data-ttu-id="56cd9-161">SQLBIT</span><span class="sxs-lookup"><span data-stu-id="56cd9-161">SQLBIT</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="56cd9-162">SQLUNIQUEID</span><span class="sxs-lookup"><span data-stu-id="56cd9-162">SQLUNIQUEID</span></span>|  
|`sql_variant`|<span data-ttu-id="56cd9-163">SQLVARIANT</span><span class="sxs-lookup"><span data-stu-id="56cd9-163">SQLVARIANT</span></span>|  
|`timestamp`|<span data-ttu-id="56cd9-164">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="56cd9-164">SQLBINARY</span></span>|  
|<span data-ttu-id="56cd9-165">UDT (um tipo de dados definido pelo usuário)</span><span class="sxs-lookup"><span data-stu-id="56cd9-165">UDT (a user-defined data type)</span></span>|<span data-ttu-id="56cd9-166">SQLUDT</span><span class="sxs-lookup"><span data-stu-id="56cd9-166">SQLUDT</span></span>|  
  
 <span data-ttu-id="56cd9-167"><sup>1</sup> arquivos de dados que são armazenados em formato de caractere usam `char` como o tipo de armazenamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="56cd9-167"><sup>1</sup> Data files that are stored in character format use `char` as the file storage type.</span></span> <span data-ttu-id="56cd9-168">Então, para arquivos de dados de caractere, SQLCHAR é o único tipo de dados que aparece em um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="56cd9-168">Therefore, for character data files, SQLCHAR is the only data type that appears in a format file.</span></span>  
  
 <span data-ttu-id="56cd9-169"><sup>2</sup> você não pode importar dados em massa para as `text` `ntext` colunas, e `image` que têm valores padrão.</span><span class="sxs-lookup"><span data-stu-id="56cd9-169"><sup>2</sup> You cannot bulk import data into `text`, `ntext`, and `image` columns that have DEFAULT values.</span></span>  
  
## <a name="additional-considerations-for-file-storage-types"></a><span data-ttu-id="56cd9-170">Considerações adicionais para tipos de armazenamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="56cd9-170">Additional Considerations for File Storage Types</span></span>  
 <span data-ttu-id="56cd9-171">Quando você agrupa dados exportados de uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para um arquivo de dados:</span><span class="sxs-lookup"><span data-stu-id="56cd9-171">When you bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file:</span></span>  
  
-   <span data-ttu-id="56cd9-172">Você sempre pode especificar `char` como o tipo de armazenamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="56cd9-172">You can always specify `char` as the file storage type.</span></span>  
  
-   <span data-ttu-id="56cd9-173">Se você inserir um tipo de armazenamento de arquivo que representa uma conversão implícita inválida, o **bcp** falhará; por exemplo, embora você possa especificar `int` para `smallint` dados, se você especificar `smallint` for `int` data, resultado de estouro de erros.</span><span class="sxs-lookup"><span data-stu-id="56cd9-173">If you enter a file storage type that represents an invalid implicit conversion, **bcp** fails; for example, though you can specify `int` for `smallint` data, if you specify `smallint` for `int` data, overflow errors result.</span></span>  
  
-   <span data-ttu-id="56cd9-174">Quando tipos de dados que não são de caractere, como `float`, `money`, `datetime` ou `int`, são armazenados como seus tipos de bancos de dados, os dados são gravados para o arquivo de dados no formato nativo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56cd9-174">When noncharacter data types such as `float`, `money`, `datetime`, or `int` are stored as their database types, the data is written to the data file in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56cd9-175">Depois que você especificar interativamente todos os campos em um comando **bcp**, o comando solicitará que salve suas respostas para cada campo em um arquivo de formato não XML.</span><span class="sxs-lookup"><span data-stu-id="56cd9-175">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="56cd9-176">Para obter mais informações sobre arquivos de formato não XML, veja [Arquivos de formato não XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="56cd9-176">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cd9-177">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="56cd9-177">See Also</span></span>  
 <span data-ttu-id="56cd9-178">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="56cd9-178">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="56cd9-179">[Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="56cd9-179">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="56cd9-180">[Especificar tamanho do campo usando bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="56cd9-180">[Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="56cd9-181">[Especificar terminadores de campo e linha &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="56cd9-181">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 [<span data-ttu-id="56cd9-182">Especificar o tamanho de prefixo em arquivos de dados usando bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="56cd9-182">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
  
