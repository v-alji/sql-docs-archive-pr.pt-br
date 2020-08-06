---
title: Especificar terminadores de campo e linha (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bcp utility [SQL Server], terminators
- field terminators [SQL Server]
- data formats [SQL Server], terminators
- row terminators [SQL Server]
- terminators [SQL Server]
ms.assetid: f68b6782-f386-4947-93c4-e89110800704
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 548beeae68f5585c5cf2ba56b67027532ab43b71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685167"
---
# <a name="specify-field-and-row-terminators-sql-server"></a><span data-ttu-id="15880-102">Especificar terminadores de campo e linha (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="15880-102">Specify Field and Row Terminators (SQL Server)</span></span>
  <span data-ttu-id="15880-103">Para campos de dados de caracteres, caracteres de terminação opcionais permitem marcar o término de cada campo em um arquivo de dados com um *terminador de campo* e o término de cada linha com um *terminador de linha*.</span><span class="sxs-lookup"><span data-stu-id="15880-103">For character data fields, optional terminating characters allow you to mark the end of each field in a data file with a *field terminator* and the end of each row with a *row terminator*.</span></span> <span data-ttu-id="15880-104">Os caracteres terminadores são um modo de indicar aos programas que leem o arquivo de dados onde um campo ou uma linha termina, e onde outro campo ou outra linha começa.</span><span class="sxs-lookup"><span data-stu-id="15880-104">Terminating characters are one way to indicate to programs that read the data file where one field or row ends and another field or row begins.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15880-105">Quando você usa formato nativo ou nativo Unicode, usa prefixos de comprimento em vez de terminadores de campo.</span><span class="sxs-lookup"><span data-stu-id="15880-105">When you use native or Unicode native format, use length prefixes rather than field terminators.</span></span> <span data-ttu-id="15880-106">Dados de formato nativo podem conflituar com terminadores, pois um arquivo de dados de formato nativo é armazenado no formato de dados binário interno do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15880-106">Native format data can conflict with terminators because a native-format data file is stored in the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internal binary data format.</span></span>  
  
## <a name="characters-supported-as-terminators"></a><span data-ttu-id="15880-107">Caracteres que têm suporte como terminadores</span><span class="sxs-lookup"><span data-stu-id="15880-107">Characters Supported As Terminators</span></span>  
 <span data-ttu-id="15880-108">O comando **bcp** , a instrução BULK INSERT e o provedor de conjunto de linhas em massa OPENROWSET oferecem suporte a uma variedade de caracteres como terminadores de campo ou de linha e sempre procura a primeira instância de cada terminador.</span><span class="sxs-lookup"><span data-stu-id="15880-108">The **bcp** command, BULK INSERT statement, and the OPENROWSET bulk rowset provider support a variety of characters as field or row terminators and always look for the first instance of each terminator.</span></span> <span data-ttu-id="15880-109">A tabela a seguir lista os caracteres que têm suporte para terminadores.</span><span class="sxs-lookup"><span data-stu-id="15880-109">The following table lists the supported characters for terminators.</span></span>  
  
|<span data-ttu-id="15880-110">Caractere terminador</span><span class="sxs-lookup"><span data-stu-id="15880-110">Terminating character</span></span>|<span data-ttu-id="15880-111">Indicado por</span><span class="sxs-lookup"><span data-stu-id="15880-111">Indicated by</span></span>|  
|---------------------------|------------------|  
|<span data-ttu-id="15880-112">Tab</span><span class="sxs-lookup"><span data-stu-id="15880-112">Tab</span></span>|<span data-ttu-id="15880-113">\t</span><span class="sxs-lookup"><span data-stu-id="15880-113">\t</span></span><br /><br /> <span data-ttu-id="15880-114">Esse é o terminador de campo padrão.</span><span class="sxs-lookup"><span data-stu-id="15880-114">This is the default field terminator.</span></span>|  
|<span data-ttu-id="15880-115">Caractere de nova linha</span><span class="sxs-lookup"><span data-stu-id="15880-115">Newline character</span></span>|<span data-ttu-id="15880-116">\n</span><span class="sxs-lookup"><span data-stu-id="15880-116">\n</span></span><br /><br /> <span data-ttu-id="15880-117">Esse é o terminador de linha padrão.</span><span class="sxs-lookup"><span data-stu-id="15880-117">This is the default row terminator.</span></span>|  
|<span data-ttu-id="15880-118">Retorno de carro/avanço de linha</span><span class="sxs-lookup"><span data-stu-id="15880-118">Carriage return/line feed</span></span>|<span data-ttu-id="15880-119">\r</span><span class="sxs-lookup"><span data-stu-id="15880-119">\r</span></span>|  
|<span data-ttu-id="15880-120">Barra invertida<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="15880-120">Backslash<sup>1</sup></span></span>|\\\|  
|<span data-ttu-id="15880-121">Terminador nulo (terminador não visível)<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="15880-121">Null terminator (nonvisible terminator)<sup>2</sup></span></span>|<span data-ttu-id="15880-122">\0</span><span class="sxs-lookup"><span data-stu-id="15880-122">\0</span></span>|  
|<span data-ttu-id="15880-123">Qualquer caractere imprimível (caracteres de controle não são imprimíveis, exceto nulo, tabulação, nova linha e retorno de carro)</span><span class="sxs-lookup"><span data-stu-id="15880-123">Any printable character (control characters are not printable, except null, tab, newline, and carriage return)</span></span>|<span data-ttu-id="15880-124">(\*, A, t, l, etc.)</span><span class="sxs-lookup"><span data-stu-id="15880-124">(\*, A, t, l, and so on)</span></span>|  
|<span data-ttu-id="15880-125">Cadeia de caracteres de até 10 caracteres imprimíveis, incluindo alguns ou todos os terminadores listados anteriormente</span><span class="sxs-lookup"><span data-stu-id="15880-125">String of up to 10 printable characters, including some or all of the terminators listed earlier</span></span>|<span data-ttu-id="15880-126">(\*\*\t\*\*, end, !!!!!!!!!!, \t-\n e assim por diante)</span><span class="sxs-lookup"><span data-stu-id="15880-126">(\*\*\t\*\*, end, !!!!!!!!!!, \t-\n, and so on)</span></span>|  
  
 <span data-ttu-id="15880-127"><sup>1</sup> somente os caracteres t, n, r, 0 e ' \ 0 ' funcionam com o caractere de escape de barra invertida para produzir um caractere de controle.</span><span class="sxs-lookup"><span data-stu-id="15880-127"><sup>1</sup> Only the t, n, r, 0 and '\0' characters work with the backslash escape character to produce a control character.</span></span>  
  
 <span data-ttu-id="15880-128"><sup>2</sup> embora o caractere de controle nulo (\ 0) não esteja visível quando impresso, ele é um caractere distinto no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="15880-128"><sup>2</sup> Even though the null control character (\0) is not visible when printed, it is a distinct character in the data file.</span></span> <span data-ttu-id="15880-129">Isso significa que usar o caractere de controle nulo como um terminador de campo ou de linha é diferente de não ter nenhum terminador de campo ou de linha.</span><span class="sxs-lookup"><span data-stu-id="15880-129">This means that using the null control character as a field or row terminator is different than having no field or row terminator at all.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15880-130">Se um caractere terminador ocorrer dentro dos dados, ele será interpretado como um terminador, não como dados, e os dados depois daquele caractere serão interpretados como sendo parte do próximo campo ou registro.</span><span class="sxs-lookup"><span data-stu-id="15880-130">If a terminator character occurs within the data, it is interpreted as a terminator, not as data, and the data after that character is interpreted as belonging to the next field or record.</span></span> <span data-ttu-id="15880-131">Portanto, escolha seus terminadores cuidadosamente para ter certeza de que eles nunca aparecerão em seus dados.</span><span class="sxs-lookup"><span data-stu-id="15880-131">Therefore, choose your terminators carefully to make sure that they never appear in your data.</span></span> <span data-ttu-id="15880-132">Por exemplo, um terminador de campo de alternativo baixo não seria uma boa escolha para um terminador de campo se os dados contiverem esse alternativo baixo.</span><span class="sxs-lookup"><span data-stu-id="15880-132">For example, a low surrogate field terminator would not be a good choice for a field terminator if the data contains that low surrogate.</span></span>  
  
## <a name="using-row-terminators"></a><span data-ttu-id="15880-133">Usando terminadores de linha</span><span class="sxs-lookup"><span data-stu-id="15880-133">Using Row Terminators</span></span>  
 <span data-ttu-id="15880-134">O terminador de linha pode ser o mesmo caractere que o terminador do último campo.</span><span class="sxs-lookup"><span data-stu-id="15880-134">The row terminator can be the same character as the terminator for the last field.</span></span> <span data-ttu-id="15880-135">Porém, geralmente um terminador de linha distinto é útil.</span><span class="sxs-lookup"><span data-stu-id="15880-135">Generally, however, a distinct row terminator is useful.</span></span> <span data-ttu-id="15880-136">Por exemplo, para produzir saída tabular, termine o último campo de cada linha com o caractere de nova linha (\n) e todos os outros campos com o caractere de tabulação (\t).</span><span class="sxs-lookup"><span data-stu-id="15880-136">For example, to produce tabular output, terminate the last field in each row with the newline character (\n) and all other fields with the tab character (\t).</span></span> <span data-ttu-id="15880-137">Para colocar cada registro de dados em sua própria linha no arquivo de dados, especifique a combinação \r\n como terminador de linha.</span><span class="sxs-lookup"><span data-stu-id="15880-137">To place each data record on its own line in the data file, specify the combination \r\n as the row terminator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15880-138">Quando você usa **bcp** de forma interativa e especifica \n (nova linha) como terminador de linha, o **bcp** automaticamente o prefixa com um caractere \r (retorno de carro), o que resulta em um terminador de linha \r\n.</span><span class="sxs-lookup"><span data-stu-id="15880-138">When you use **bcp** interactively and specify \n (newline) as the row terminator, **bcp** automatically prefixes it with a \r (carriage return) character, which results in a row terminator of \r\n.</span></span>  
  
## <a name="specifying-terminators-for-bulk-export"></a><span data-ttu-id="15880-139">Especificando terminadores para exportação em massa</span><span class="sxs-lookup"><span data-stu-id="15880-139">Specifying Terminators for Bulk Export</span></span>  
 <span data-ttu-id="15880-140">Quando você exporta `char` ou dados em massa `nchar` e deseja usar um terminador não padrão, deve especificar o terminador para o comando **bcp** .</span><span class="sxs-lookup"><span data-stu-id="15880-140">When you bulk export `char` or `nchar` data, and want to use a non-default terminator, you must specify the terminator to the **bcp** command.</span></span> <span data-ttu-id="15880-141">Você pode especificar terminadores em qualquer uma das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="15880-141">You can specify terminators in any of the following ways:</span></span>  
  
-   <span data-ttu-id="15880-142">Com um arquivo de formato que especifica o terminador campo por campo.</span><span class="sxs-lookup"><span data-stu-id="15880-142">With a format file that specifies the terminator on a field-by-field basis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15880-143">Para obter informações sobre como usar arquivos de formato, veja [Arquivos de formato para importação ou exportação de dados &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="15880-143">For information about how to use format files, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
-   <span data-ttu-id="15880-144">Sem um arquivo de formato, existem as seguintes alternativas:</span><span class="sxs-lookup"><span data-stu-id="15880-144">Without a format file, the following alternatives exist:</span></span>  
  
    -   <span data-ttu-id="15880-145">Usar a opção **-t** para especificar o terminador de linha para todos os campos, exceto para o último campo na linha, e usar a opção **-r** para especificar um terminador de linha.</span><span class="sxs-lookup"><span data-stu-id="15880-145">Using the **-t** switch to specify the row terminator for all the fields except the last field in the row and using the **-r** switch to specify a row terminator.</span></span>  
  
    -   <span data-ttu-id="15880-146">Usar uma opção de formato de caractere ( **-c** ou **-w**) sem a opção **-t** , o que define o terminador de campo como o caractere de tabulação, \t.</span><span class="sxs-lookup"><span data-stu-id="15880-146">Using a character-format switch (**-c** or **-w**) without the **-t** switch, which sets the field terminator to the tab character, \t.</span></span> <span data-ttu-id="15880-147">Isso é o mesmo que especificar **-t**\t.</span><span class="sxs-lookup"><span data-stu-id="15880-147">This is the same as specifying **-t**\t.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="15880-148">Se você especificar a opção **-n** (dados nativos) ou **-N** (dados nativos Unicode), os terminadores não serão inseridos.</span><span class="sxs-lookup"><span data-stu-id="15880-148">If you specify the **-n** (native data) or **-N** (Unicode native) switch, terminators are not inserted.</span></span>  
  
    -   <span data-ttu-id="15880-149">Se um comando interativo **bcp** contiver a opção **in** ou **out** sem a opção de arquivo de formato ( **-f**) ou uma opção de formato de dados ( **-n**, **-c**, **-w**ou **-N**) e você tiver escolhido não identificar os tamanhos de prefixo e de campo, o comando solicitará o terminador de campo de cada campo com um padrão nenhum:</span><span class="sxs-lookup"><span data-stu-id="15880-149">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), and you have chosen not to specify prefix length and field length, the command prompts for the field terminator of each field, with a default of none:</span></span>  
  
         `Enter field terminator [none]:`  
  
         <span data-ttu-id="15880-150">Geralmente, o padrão é uma escolha adequada.</span><span class="sxs-lookup"><span data-stu-id="15880-150">Generally, the default is a suitable choice.</span></span> <span data-ttu-id="15880-151">No entanto, para campos de dados `char` ou `nchar`, consulte a seguinte subseção, "Diretrizes para uso de terminadores".</span><span class="sxs-lookup"><span data-stu-id="15880-151">However, for `char` or `nchar` data fields, see the following subsection, "Guidelines for Using Terminators."</span></span> <span data-ttu-id="15880-152">Para obter um exemplo que mostra esse prompt no contexto, veja [Especificar formatos de dados para compatibilidade usando bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="15880-152">For an example that shows this prompt in context, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="15880-153">Depois que você especificar interativamente todos os campos em um comando **bcp**, o comando solicitará que salve suas respostas para cada campo em um arquivo de formato não XML.</span><span class="sxs-lookup"><span data-stu-id="15880-153">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="15880-154">Para obter mais informações sobre arquivos de formato não XML, veja [Arquivos de formato não XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="15880-154">For more information about non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="guidelines-for-using-terminators"></a><span data-ttu-id="15880-155">Diretrizes para uso de terminadores</span><span class="sxs-lookup"><span data-stu-id="15880-155">Guidelines for Using Terminators</span></span>  
 <span data-ttu-id="15880-156">Em algumas situações, um terminador é útil para um campo de dados `char` ou `nchar`.</span><span class="sxs-lookup"><span data-stu-id="15880-156">In some situations, a terminator is useful for a `char` or `nchar` data field.</span></span> <span data-ttu-id="15880-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="15880-157">For example:</span></span>  
  
-   <span data-ttu-id="15880-158">Para uma coluna de dados que contém um valor nulo em um arquivo de dados que será importado em um programa que não entende as informações de comprimento de prefixo.</span><span class="sxs-lookup"><span data-stu-id="15880-158">For a data column that contains a null value in a data file that will be imported into a program that does not understand the prefix length information.</span></span>  
  
     <span data-ttu-id="15880-159">Qualquer coluna de dados que contenha um valor nulo é considerada de comprimento variável.</span><span class="sxs-lookup"><span data-stu-id="15880-159">Any data column that contains a null value is considered variable length.</span></span> <span data-ttu-id="15880-160">Na ausência de comprimentos de prefixos, um terminador é necessário para identificar o término de um campo nulo, com a certeza de que os dados são corretamente interpretados.</span><span class="sxs-lookup"><span data-stu-id="15880-160">In the absence of prefix lengths, a terminator is necessary to identify the end of a null field, making sure that the data is correctly interpreted.</span></span>  
  
-   <span data-ttu-id="15880-161">Para uma coluna longa de comprimento fixo cujo espaço é apenas parcialmente usado por várias linhas.</span><span class="sxs-lookup"><span data-stu-id="15880-161">For a long fixed-length column whose space is only partially used by many rows.</span></span>  
  
     <span data-ttu-id="15880-162">Nessa situação, especificar um terminador pode minimizar o espaço de armazenamento, permitindo que o campo seja tratado como um campo de comprimento variável.</span><span class="sxs-lookup"><span data-stu-id="15880-162">In this situation, specifying a terminator can minimize storage space allowing the field to be treated as a variable-length field.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="15880-163">Exemplos</span><span class="sxs-lookup"><span data-stu-id="15880-163">Examples</span></span>  
 <span data-ttu-id="15880-164">Este exemplo exporta os dados em massa da tabela `AdventureWorks``HumanResources.Department` para o arquivo de dados `Department-c-t.txt` usando o formato de caractere, com uma vírgula como terminador de campo e o caractere de nova linha (\n) como terminador de linha.</span><span class="sxs-lookup"><span data-stu-id="15880-164">This example bulk exports the data from the `AdventureWorks``HumanResources.Department` table to the `Department-c-t.txt` data file using character format, with a comma as a field terminator and the newline character (\n) as the row terminator.</span></span>  
  
 <span data-ttu-id="15880-165">O comando **bcp** contém as opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="15880-165">The **bcp** command contains the following switches.</span></span>  
  
|<span data-ttu-id="15880-166">Opção</span><span class="sxs-lookup"><span data-stu-id="15880-166">Switch</span></span>|<span data-ttu-id="15880-167">Descrição</span><span class="sxs-lookup"><span data-stu-id="15880-167">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="15880-168">**-c**</span><span class="sxs-lookup"><span data-stu-id="15880-168">**-c**</span></span>|<span data-ttu-id="15880-169">Especifica que os campos de dados sejam carregados como dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="15880-169">Specifies that the data fields be loaded as character data.</span></span>|  
|<span data-ttu-id="15880-170">**-t** `,`</span><span class="sxs-lookup"><span data-stu-id="15880-170">**-t** `,`</span></span>|<span data-ttu-id="15880-171">Especifica uma vírgula (,) como terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="15880-171">Specifies a comma (,) as the field terminator.</span></span>|  
|<span data-ttu-id="15880-172">**-r** \n</span><span class="sxs-lookup"><span data-stu-id="15880-172">**-r** \n</span></span>|<span data-ttu-id="15880-173">Especifica o terminador de linha como um caractere de nova linha.</span><span class="sxs-lookup"><span data-stu-id="15880-173">Specifies the row terminator as a newline character.</span></span> <span data-ttu-id="15880-174">Esse é o terminador de linha padrão, portanto especificá-lo é opcional.</span><span class="sxs-lookup"><span data-stu-id="15880-174">This is the default row terminator, so specifying it is optional.</span></span>|  
|<span data-ttu-id="15880-175">**-T**</span><span class="sxs-lookup"><span data-stu-id="15880-175">**-T**</span></span>|<span data-ttu-id="15880-176">Especifica que o utilitário **bcp** se conecta ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com uma conexão confiável usando segurança integrada.</span><span class="sxs-lookup"><span data-stu-id="15880-176">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="15880-177">Se **-T** não for especificado, será necessário especificar **-U** e **-P** para que o logon tenha êxito.</span><span class="sxs-lookup"><span data-stu-id="15880-177">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="15880-178">Para obter mais informações, consulte [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="15880-178">For more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
 <span data-ttu-id="15880-179">No prompt de comando do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, digite:</span><span class="sxs-lookup"><span data-stu-id="15880-179">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department out C:\myDepartment-c-t.txt -c -t, -r \n -T  
```  
  
 <span data-ttu-id="15880-180">Isso cria `Department-c-t.txt`que contém 16 registros com quatro campos cada.</span><span class="sxs-lookup"><span data-stu-id="15880-180">This creates `Department-c-t.txt`, which contains 16 records with four fields each.</span></span> <span data-ttu-id="15880-181">Os campos estão separados por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="15880-181">The fields are separated by a comma.</span></span>  
  
## <a name="specifying-terminators-for-bulk-import"></a><span data-ttu-id="15880-182">Especificando terminadores para importação em massa</span><span class="sxs-lookup"><span data-stu-id="15880-182">Specifying Terminators for Bulk Import</span></span>  
 <span data-ttu-id="15880-183">Quando você importa em massa dados `char` ou `nchar`, o comando de importação em massa deve reconhecer os terminadores usados no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="15880-183">When you bulk import `char` or `nchar` data, the bulk-import command must recognize the terminators that are used in the data file.</span></span> <span data-ttu-id="15880-184">A especificação dos terminadores depende do comando de importação em massa, como segue:</span><span class="sxs-lookup"><span data-stu-id="15880-184">How terminators can be specified depends on the bulk-import command, as follows:</span></span>  
  
-   <span data-ttu-id="15880-185">**bcp**</span><span class="sxs-lookup"><span data-stu-id="15880-185">**bcp**</span></span>  
  
     <span data-ttu-id="15880-186">A especificação de terminadores para uma operação de importação usa a mesma sintaxe que uma operação de exportação.</span><span class="sxs-lookup"><span data-stu-id="15880-186">Specifying terminators for an import operation uses the same syntax as for an export operation.</span></span> <span data-ttu-id="15880-187">Para obter mais informações, consulte "Especificando terminadores para exportação em massa", anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="15880-187">For more information, see "Specifying Terminators for Bulk Export," earlier in this topic.</span></span>  
  
-   <span data-ttu-id="15880-188">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="15880-188">BULK INSERT</span></span>  
  
     <span data-ttu-id="15880-189">Os terminadores podem ser especificados para campos individuais em um arquivo de formato ou para o arquivo de dados inteiro usando os qualificadores mostrados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="15880-189">Terminators can be specified for individual fields in a format file or for the whole data file by using the qualifiers shown in the following table.</span></span>  
  
    |<span data-ttu-id="15880-190">Qualificador</span><span class="sxs-lookup"><span data-stu-id="15880-190">Qualifier</span></span>|<span data-ttu-id="15880-191">Descrição</span><span class="sxs-lookup"><span data-stu-id="15880-191">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="15880-192">FIELDTERMINATOR **= ' *`field_terminator`* '**</span><span class="sxs-lookup"><span data-stu-id="15880-192">FIELDTERMINATOR **='*`field_terminator`*'**</span></span>|<span data-ttu-id="15880-193">Especifica o terminador de campo a ser usado em arquivos de dados de caracteres e caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="15880-193">Specifies the field terminator to be used for character and Unicode character data files.</span></span><br /><br /> <span data-ttu-id="15880-194">O padrão é \t (caractere de tabulação).</span><span class="sxs-lookup"><span data-stu-id="15880-194">The default is \t (tab character).</span></span>|  
    |<span data-ttu-id="15880-195">Objectterminador **= ' *`row_terminator`* '**</span><span class="sxs-lookup"><span data-stu-id="15880-195">ROWTERMINATOR **='*`row_terminator`*'**</span></span>|<span data-ttu-id="15880-196">Especifica o terminador de linha a ser usado em arquivos de dados de caracteres e caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="15880-196">Specifies the row terminator to be used for character and Unicode character data files.</span></span><br /><br /> <span data-ttu-id="15880-197">O padrão é \n (caractere de nova linha).</span><span class="sxs-lookup"><span data-stu-id="15880-197">The default is \n (newline character).</span></span>|  
  
     <span data-ttu-id="15880-198">Para obter mais informações, veja [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15880-198">For more information, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
-   <span data-ttu-id="15880-199">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="15880-199">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
  
     <span data-ttu-id="15880-200">Para o provedor de conjunto de linhas em massa OPENROWSET, podem ser especificados terminadores somente no arquivo de formato (que é necessário, exceto para tipos de dados de objeto grande).</span><span class="sxs-lookup"><span data-stu-id="15880-200">For the OPENROWSET bulk rowset provider, terminators can be specified only in the format file (which is required except for large-object data types).</span></span> <span data-ttu-id="15880-201">Se um arquivo de dados de caracteres usar um terminador não padrão, ele deverá ser definido no arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="15880-201">If a character data file uses a non-default terminator, it must be defined in the format file.</span></span> <span data-ttu-id="15880-202">Para obter mais informações, veja [Criar um arquivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md) e [Usar um arquivo de formato para importação de dados em massa &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="15880-202">For more information, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md) and [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
     <span data-ttu-id="15880-203">Para obter mais informações sobre a cláusula OPENROWSET BULK, veja [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15880-203">For more information about the OPENROWSET BULK clause, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="15880-204">Exemplos</span><span class="sxs-lookup"><span data-stu-id="15880-204">Examples</span></span>  
 <span data-ttu-id="15880-205">Os exemplos nesta seção importam em massa dados de caracteres do arquivo de dados `Department-c-t.txt` criado no exemplo anterior na tabela `myDepartment` no banco de dados de exemplo [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15880-205">The examples in this section bulk import character data form the `Department-c-t.txt` data file created in the preceding example into the `myDepartment` table in the [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] sample database.</span></span> <span data-ttu-id="15880-206">Antes de executar os exemplos, é necessário criar essa tabela.</span><span class="sxs-lookup"><span data-stu-id="15880-206">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="15880-207">Para criar essa tabela no esquema **dbo** , no Editor de Consultas [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="15880-207">To create this table under the **dbo** schema, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DROP TABLE myDepartment;  
CREATE TABLE myDepartment   
(DepartmentID smallint,  
Name nvarchar(50),  
GroupName nvarchar(50) NULL,  
ModifiedDate datetime not NULL CONSTRAINT DF_AddressType_ModifiedDate DEFAULT (GETDATE())  
);  
GO  
  
```  
  
#### <a name="a-using-bcp-to-interactively-specify-terminators"></a><span data-ttu-id="15880-208">a.</span><span class="sxs-lookup"><span data-stu-id="15880-208">A.</span></span> <span data-ttu-id="15880-209">Usando bcp para especificar terminadores interativamente</span><span class="sxs-lookup"><span data-stu-id="15880-209">Using bcp to interactively specify terminators</span></span>  
 <span data-ttu-id="15880-210">O exemplo a seguir importa em massa o arquivo de dados `Department-c-t.txt` usando um comando `bcp` .</span><span class="sxs-lookup"><span data-stu-id="15880-210">The following example bulk imports the `Department-c-t.txt` data file using a `bcp` command.</span></span> <span data-ttu-id="15880-211">Esse comando usa as mesmas opções de comando que o comando de exportação em massa.</span><span class="sxs-lookup"><span data-stu-id="15880-211">This command uses the same command switches as the bulk export command.</span></span> <span data-ttu-id="15880-212">Para obter mais informações, consulte "Especificando terminadores para exportação em massa", anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="15880-212">For more information, see "Specifying Terminators for Bulk Export," earlier in this topic.</span></span>  
  
 <span data-ttu-id="15880-213">No prompt de comando do Windows, insira:</span><span class="sxs-lookup"><span data-stu-id="15880-213">At the Windows command prompt enter:</span></span>  
  
```  
bcp AdventureWorks..myDepartment in C:\myDepartment-c-t.txt -c -t , -r \n -T  
```  
  
#### <a name="b-using-bulk-insert-to-interactively-specify-terminators"></a><span data-ttu-id="15880-214">B.</span><span class="sxs-lookup"><span data-stu-id="15880-214">B.</span></span> <span data-ttu-id="15880-215">Usando BULK INSERT para especificar terminadores interativamente</span><span class="sxs-lookup"><span data-stu-id="15880-215">Using BULK INSERT to interactively specify terminators</span></span>  
 <span data-ttu-id="15880-216">O exemplo a seguir importa em massa o arquivo de dados `Department-c-t.txt` usando uma instrução `BULK INSERT` que usa os qualificadores mostrados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="15880-216">The following example bulk imports the `Department-c-t.txt` data file using a `BULK INSERT` statement that uses the qualifiers shown in the following table.</span></span>  
  
|<span data-ttu-id="15880-217">Opção</span><span class="sxs-lookup"><span data-stu-id="15880-217">Option</span></span>|<span data-ttu-id="15880-218">Atributo</span><span class="sxs-lookup"><span data-stu-id="15880-218">Attribute</span></span>|  
|------------|---------------|  
|<span data-ttu-id="15880-219">DataFileType **= ' `char` '**</span><span class="sxs-lookup"><span data-stu-id="15880-219">DATAFILETYPE **='`char`'**</span></span>|<span data-ttu-id="15880-220">Especifica que os campos de dados sejam carregados como dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="15880-220">Specifies that the data fields be loaded as character data.</span></span>|  
|<span data-ttu-id="15880-221">FIELDTERMINATOR **='** `,` **'**</span><span class="sxs-lookup"><span data-stu-id="15880-221">FIELDTERMINATOR **='**`,`**'**</span></span>|<span data-ttu-id="15880-222">Especifica uma vírgula (`,`) como terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="15880-222">Specifies a comma (`,`) as the field terminator.</span></span>|  
|<span data-ttu-id="15880-223">ROWTERMINATOR **='** `\n` **'**</span><span class="sxs-lookup"><span data-stu-id="15880-223">ROWTERMINATOR **='**`\n`**'**</span></span>|<span data-ttu-id="15880-224">Especifica o terminador de linha como um caractere de nova linha.</span><span class="sxs-lookup"><span data-stu-id="15880-224">Specifies the row terminator as a newline character.</span></span>|  
  
 <span data-ttu-id="15880-225">No Editor de Consultas do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , execute o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="15880-225">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myDepartment FROM 'C:\myDepartment-c-t.txt'  
   WITH (  
      DATAFILETYPE = 'char',  
      FIELDTERMINATOR = ',',  
      ROWTERMINATOR = '\n'  
);  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="15880-226">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15880-226">See Also</span></span>  
 <span data-ttu-id="15880-227">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="15880-227">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="15880-228">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15880-228">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="15880-229">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15880-229">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="15880-230">[Especificar tamanho do campo usando bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15880-230">[Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="15880-231">[Especificar o tamanho de prefixo em arquivos de dados usando bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15880-231">[Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span></span>  
 [<span data-ttu-id="15880-232">Especificar tipo de armazenamento de arquivo usando bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="15880-232">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
  
