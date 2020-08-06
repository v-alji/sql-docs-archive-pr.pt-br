---
title: Especificar tamanho do campo usando bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- default field lengths
- field length [SQL Server]
- data formats [SQL Server], field length
- bcp utility [SQL Server], field length
ms.assetid: 240f33ca-ef4a-413a-a4de-831885cb505b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 13343b4f3778df1bbe7ef1c99b3d06338f18631c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679357"
---
# <a name="specify-field-length-by-using-bcp-sql-server"></a><span data-ttu-id="39a29-102">Especificar tamanho do campo usando bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="39a29-102">Specify Field Length by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="39a29-103">O tamanho do campo indica o número máximo de caracteres que são exigidos para representar dados em formato de caractere.</span><span class="sxs-lookup"><span data-stu-id="39a29-103">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="39a29-104">O tamanho do campo já será conhecido se os dados forem armazenados no formato nativo; por exemplo, o tipo de dados `int` usa 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="39a29-104">The field length is already known if the data is stored in the native format; for example, the `int` data type takes 4 bytes.</span></span> <span data-ttu-id="39a29-105">Se você indicou 0 para o comprimento do prefixo, o comando **bcp** solicitará o tamanho do campo, os comprimentos do campo padrão e o impacto do tamanho do campo no armazenamento de dados em arquivos de dados que contêm `char` dados.</span><span class="sxs-lookup"><span data-stu-id="39a29-105">If you have indicated 0 for the prefix length, the **bcp** command prompts you for field length, the default field lengths, and the impact of field-length on data storage in data files that contain `char` data.</span></span>  
  
## <a name="the-bcp-prompt-for-field-length"></a><span data-ttu-id="39a29-106">O bcp solicita um tamanho de campo</span><span class="sxs-lookup"><span data-stu-id="39a29-106">The bcp Prompt for Field Length</span></span>  
 <span data-ttu-id="39a29-107">Se um comando **bcp** interativo contiver a opção **in** ou **out** sem a opção do arquivo de formatos ( **-f**) ou uma opção do formato de dados ( **-n**, **-c**, **-w** ou **-N**), o comando solicitará o comprimento de campo de cada campo de dados, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="39a29-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the field length of each data field, as follows:</span></span>  
  
 `Enter length of field <field_name> [<default>]:`  
  
 <span data-ttu-id="39a29-108">Para obter um exemplo que mostra esse prompt no contexto, veja [Especificar formatos de dados para compatibilidade usando bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="39a29-108">For an example that shows this prompt in context, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39a29-109">Depois que você especificar interativamente todos os campos em um comando **bcp**, o comando solicitará que salve suas respostas para cada campo em um arquivo de formato não XML.</span><span class="sxs-lookup"><span data-stu-id="39a29-109">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="39a29-110">Para obter mais informações sobre arquivos de formato não XML, veja [Arquivos de formato não XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="39a29-110">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 <span data-ttu-id="39a29-111">A solicitação do comprimento do campo pelo comando **bcp** depende de vários fatores:</span><span class="sxs-lookup"><span data-stu-id="39a29-111">Whether a **bcp** command prompts for field length depends on several factors, as follows:</span></span>  
  
-   <span data-ttu-id="39a29-112">Quando você copiar tipos de dados que não são de comprimento fixo e especificar um comprimento de prefixo 0, o **bcp** solicitará um comprimento de campo.</span><span class="sxs-lookup"><span data-stu-id="39a29-112">When you copy data types that are not of fixed length and you specify a prefix length of 0, **bcp** prompts for a field length.</span></span>  
  
-   <span data-ttu-id="39a29-113">Quando dados que não contêm caracteres são convertidos em dados de caracteres, o **bcp** sugere um comprimento de campo padrão grande o suficiente para armazenar os dados.</span><span class="sxs-lookup"><span data-stu-id="39a29-113">When converting noncharacter data to character data, **bcp** suggests a default field length large enough to store the data.</span></span>  
  
-   <span data-ttu-id="39a29-114">Se o tipo de armazenamento de arquivos for não caractere, o comando **bcp** não solicitará um comprimento de campo.</span><span class="sxs-lookup"><span data-stu-id="39a29-114">If the file storage type is noncharacter, the **bcp** command does not prompt for a field length.</span></span> <span data-ttu-id="39a29-115">Os dados são armazenados no formato de representação de dados nativo (formato nativo) do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39a29-115">The data is stored in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data representation (native format).</span></span>  
  
## <a name="using-default-field-lengths"></a><span data-ttu-id="39a29-116">Usando tamanhos de campo padrão</span><span class="sxs-lookup"><span data-stu-id="39a29-116">Using Default Field Lengths</span></span>  
 <span data-ttu-id="39a29-117">Geralmente, o [!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda que você aceite os valores padrão sugeridos pelo **bcp**para o comprimento de campo.</span><span class="sxs-lookup"><span data-stu-id="39a29-117">Generally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you accept the **bcp**-suggested default values for the field length.</span></span> <span data-ttu-id="39a29-118">Quando um arquivo de dados de modo de caractere é criado, usar o tamanho do campo padrão assegura que os dados não serão truncados e que não ocorram erros de estouro numéricos.</span><span class="sxs-lookup"><span data-stu-id="39a29-118">When a character mode data file is created, using the default field length ensures that data is not truncated and that numeric overflow errors do not occur.</span></span>  
  
 <span data-ttu-id="39a29-119">Se você especificar um tamanho do campo incorreto, poderão ocorrer problemas.</span><span class="sxs-lookup"><span data-stu-id="39a29-119">If you specify a field length that is incorrect, problems can occur.</span></span> <span data-ttu-id="39a29-120">Por exemplo, se você copiar dados numéricos e especificar um tamanho do campo muito curto para obter os dados, o utilitário do **bcp** imprimirá uma mensagem de estouro e não copiará os dados.</span><span class="sxs-lookup"><span data-stu-id="39a29-120">For instance, if you copy numeric data and you specify a field length that is too short for the data, the **bcp** utility prints an overflow message and does not copy the data.</span></span> <span data-ttu-id="39a29-121">Além disso, se você exportar `datetime` dados e especificar um tamanho de campo inferior a 26 bytes para a cadeia de caracteres, o utilitário **bcp** truncará os dados sem uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="39a29-121">Also, if you export `datetime` data and specify a field length of less than 26 bytes for the character string, the **bcp** utility truncates the data without an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="39a29-122">Quando a opção de tamanho padrão é usada, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] espera ler uma cadeia de caracteres inteira.</span><span class="sxs-lookup"><span data-stu-id="39a29-122">When the default size option is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expects to read an entire string.</span></span> <span data-ttu-id="39a29-123">Em algumas situações, o uso de um tamanho do campo padrão pode conduzir a um erro "fim de arquivo inesperado".</span><span class="sxs-lookup"><span data-stu-id="39a29-123">In some situations, use of a default field length can lead to an "unexpected end of file" error.</span></span> <span data-ttu-id="39a29-124">Normalmente, esse erro ocorre com os `money` `datetime` tipos de dados e quando apenas parte do campo esperado ocorre no arquivo de dados; por exemplo, quando um `datetime` valor de *mm* / *DD* / *AA* é especificado sem o componente de tempo e é, portanto, menor que o tamanho esperado de 24 caracteres de um `datetime` valor no `char` formato.</span><span class="sxs-lookup"><span data-stu-id="39a29-124">Typically, this error occurs with the `money` and `datetime` data types when only part of the expected field occurs in the data file; for example, when a `datetime` value of *mm*/*dd*/*yy* is specified without the time component and is, therefore, shorter than the expected 24 character length of a `datetime` value in `char` format.</span></span> <span data-ttu-id="39a29-125">Para evitar esse tipo de erro, use terminadores de campos ou campos de dados de comprimento fixo ou altere o tamanho do campo padrão especificando outro valor.</span><span class="sxs-lookup"><span data-stu-id="39a29-125">To avoid this type of error, use field terminators or fixed-length data fields, or change the default field length by specifying another value.</span></span>  
  
### <a name="default-field-lengths-for-character-file-storage"></a><span data-ttu-id="39a29-126">Tamanhos do campo padrão para armazenamento de arquivo de caractere</span><span class="sxs-lookup"><span data-stu-id="39a29-126">Default Field Lengths for Character File Storage</span></span>  
 <span data-ttu-id="39a29-127">A tabela a seguir lista os tamanhos dos campos padrão para obter os dados a serem armazenados como armazenamento de arquivo de caractere.</span><span class="sxs-lookup"><span data-stu-id="39a29-127">The following table lists the default field lengths for data to be stored as a character-file storage type.</span></span> <span data-ttu-id="39a29-128">Dados anuláveis são do mesmo comprimento que dados de não anuláveis.</span><span class="sxs-lookup"><span data-stu-id="39a29-128">Nullable data is the same length as nonnull data.</span></span>  
  
|<span data-ttu-id="39a29-129">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="39a29-129">Data type</span></span>|<span data-ttu-id="39a29-130">Comprimento padrão (caracteres)</span><span class="sxs-lookup"><span data-stu-id="39a29-130">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`char`|<span data-ttu-id="39a29-131">Comprimento definido para a coluna</span><span class="sxs-lookup"><span data-stu-id="39a29-131">Length defined for the column</span></span>|  
|`varchar`|<span data-ttu-id="39a29-132">Comprimento definido para a coluna</span><span class="sxs-lookup"><span data-stu-id="39a29-132">Length defined for the column</span></span>|  
|`nchar`|<span data-ttu-id="39a29-133">Duas vezes o comprimento definido para a coluna</span><span class="sxs-lookup"><span data-stu-id="39a29-133">Twice the length defined for the column</span></span>|  
|`nvarchar`|<span data-ttu-id="39a29-134">Duas vezes o comprimento definido para a coluna</span><span class="sxs-lookup"><span data-stu-id="39a29-134">Twice the length defined for the column</span></span>|  
|`Text`|<span data-ttu-id="39a29-135">0</span><span class="sxs-lookup"><span data-stu-id="39a29-135">0</span></span>|  
|`ntext`|<span data-ttu-id="39a29-136">0</span><span class="sxs-lookup"><span data-stu-id="39a29-136">0</span></span>|  
|`bit`|<span data-ttu-id="39a29-137">1</span><span class="sxs-lookup"><span data-stu-id="39a29-137">1</span></span>|  
|`binary`|<span data-ttu-id="39a29-138">Duas vezes o comprimento definido para a coluna + 1</span><span class="sxs-lookup"><span data-stu-id="39a29-138">Twice the length defined for the column + 1</span></span>|  
|`varbinary`|<span data-ttu-id="39a29-139">Duas vezes o comprimento definido para a coluna + 1</span><span class="sxs-lookup"><span data-stu-id="39a29-139">Twice the length defined for the column + 1</span></span>|  
|`image`|<span data-ttu-id="39a29-140">0</span><span class="sxs-lookup"><span data-stu-id="39a29-140">0</span></span>|  
|`datetime`|<span data-ttu-id="39a29-141">24</span><span class="sxs-lookup"><span data-stu-id="39a29-141">24</span></span>|  
|`smalldatetime`|<span data-ttu-id="39a29-142">24</span><span class="sxs-lookup"><span data-stu-id="39a29-142">24</span></span>|  
|`float`|<span data-ttu-id="39a29-143">30</span><span class="sxs-lookup"><span data-stu-id="39a29-143">30</span></span>|  
|`real`|<span data-ttu-id="39a29-144">30</span><span class="sxs-lookup"><span data-stu-id="39a29-144">30</span></span>|  
|`int`|<span data-ttu-id="39a29-145">12</span><span class="sxs-lookup"><span data-stu-id="39a29-145">12</span></span>|  
|`bigint`|<span data-ttu-id="39a29-146">19</span><span class="sxs-lookup"><span data-stu-id="39a29-146">19</span></span>|  
|`smallint`|<span data-ttu-id="39a29-147">7</span><span class="sxs-lookup"><span data-stu-id="39a29-147">7</span></span>|  
|`tinyint`|<span data-ttu-id="39a29-148">5</span><span class="sxs-lookup"><span data-stu-id="39a29-148">5</span></span>|  
|`money`|<span data-ttu-id="39a29-149">30</span><span class="sxs-lookup"><span data-stu-id="39a29-149">30</span></span>|  
|`smallmoney`|<span data-ttu-id="39a29-150">30</span><span class="sxs-lookup"><span data-stu-id="39a29-150">30</span></span>|  
|`decimal`|<span data-ttu-id="39a29-151">41\*</span><span class="sxs-lookup"><span data-stu-id="39a29-151">41\*</span></span>|  
|`numeric`|<span data-ttu-id="39a29-152">41\*</span><span class="sxs-lookup"><span data-stu-id="39a29-152">41\*</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="39a29-153">37</span><span class="sxs-lookup"><span data-stu-id="39a29-153">37</span></span>|  
|`timestamp`|<span data-ttu-id="39a29-154">17</span><span class="sxs-lookup"><span data-stu-id="39a29-154">17</span></span>|  
|`varchar(max)`|<span data-ttu-id="39a29-155">0</span><span class="sxs-lookup"><span data-stu-id="39a29-155">0</span></span>|  
|`varbinary(max)`|<span data-ttu-id="39a29-156">0</span><span class="sxs-lookup"><span data-stu-id="39a29-156">0</span></span>|  
|`nvarchar(max)`|<span data-ttu-id="39a29-157">0</span><span class="sxs-lookup"><span data-stu-id="39a29-157">0</span></span>|  
|<span data-ttu-id="39a29-158">UDT</span><span class="sxs-lookup"><span data-stu-id="39a29-158">UDT</span></span>|<span data-ttu-id="39a29-159">Comprimento da coluna UDT (termo definido pelo usuário)</span><span class="sxs-lookup"><span data-stu-id="39a29-159">Length of the user-defined term (UDT) column</span></span>|  
|<span data-ttu-id="39a29-160">XML</span><span class="sxs-lookup"><span data-stu-id="39a29-160">XML</span></span>|<span data-ttu-id="39a29-161">0</span><span class="sxs-lookup"><span data-stu-id="39a29-161">0</span></span>|  
  
 <span data-ttu-id="39a29-162">\*Para obter mais informações sobre `decimal` os `numeric` tipos de dados e, consulte [decimal e numérico &#40;&#41;Transact-SQL ](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="39a29-162">\*For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39a29-163">Uma coluna do tipo `tinyint` pode ter valores de 0 a 255; o número de máximo de caracteres necessários para representar qualquer número naquele intervalo é três (representando valores de 100 a 255).</span><span class="sxs-lookup"><span data-stu-id="39a29-163">A column of type `tinyint` can have values from 0 through 255; the maximum number of characters that are needed to represent any number in that range is three (representing values 100 through 255).</span></span>  
  
### <a name="default-field-lengths-for-native-file-storage"></a><span data-ttu-id="39a29-164">Tamanhos do campo padrão para armazenamento de arquivo nativo</span><span class="sxs-lookup"><span data-stu-id="39a29-164">Default Field Lengths for Native File Storage</span></span>  
 <span data-ttu-id="39a29-165">A tabela seguinte lista os tamanhos dos campos padrão para os dados a serem armazenados como um tipo de armazenamento de arquivo nativo.</span><span class="sxs-lookup"><span data-stu-id="39a29-165">The following table lists the default field lengths for data to be stored as native file storage type.</span></span> <span data-ttu-id="39a29-166">Dados anuláveis são do mesmo comprimento que dados de não anuláveis e os dados de caractere sempre são armazenados em formato de caractere.</span><span class="sxs-lookup"><span data-stu-id="39a29-166">Nullable data is the same length as nonnull data, and character data is always stored in character format.</span></span>  
  
|<span data-ttu-id="39a29-167">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="39a29-167">Data type</span></span>|<span data-ttu-id="39a29-168">Comprimento padrão (caracteres)</span><span class="sxs-lookup"><span data-stu-id="39a29-168">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`bit`|<span data-ttu-id="39a29-169">1</span><span class="sxs-lookup"><span data-stu-id="39a29-169">1</span></span>|  
|`binary`|<span data-ttu-id="39a29-170">Comprimento definido para a coluna</span><span class="sxs-lookup"><span data-stu-id="39a29-170">Length defined for the column</span></span>|  
|`varbinary`|<span data-ttu-id="39a29-171">Comprimento definido para a coluna</span><span class="sxs-lookup"><span data-stu-id="39a29-171">Length defined for the column</span></span>|  
|`image`|<span data-ttu-id="39a29-172">0</span><span class="sxs-lookup"><span data-stu-id="39a29-172">0</span></span>|  
|`datetime`|<span data-ttu-id="39a29-173">8</span><span class="sxs-lookup"><span data-stu-id="39a29-173">8</span></span>|  
|`smalldatetime`|<span data-ttu-id="39a29-174">4</span><span class="sxs-lookup"><span data-stu-id="39a29-174">4</span></span>|  
|`float`|<span data-ttu-id="39a29-175">8</span><span class="sxs-lookup"><span data-stu-id="39a29-175">8</span></span>|  
|`real`|<span data-ttu-id="39a29-176">4</span><span class="sxs-lookup"><span data-stu-id="39a29-176">4</span></span>|  
|`int`|<span data-ttu-id="39a29-177">4</span><span class="sxs-lookup"><span data-stu-id="39a29-177">4</span></span>|  
|`bigint`|<span data-ttu-id="39a29-178">8</span><span class="sxs-lookup"><span data-stu-id="39a29-178">8</span></span>|  
|`smallint`|<span data-ttu-id="39a29-179">2</span><span class="sxs-lookup"><span data-stu-id="39a29-179">2</span></span>|  
|`tinyint`|<span data-ttu-id="39a29-180">1</span><span class="sxs-lookup"><span data-stu-id="39a29-180">1</span></span>|  
|`money`|<span data-ttu-id="39a29-181">8</span><span class="sxs-lookup"><span data-stu-id="39a29-181">8</span></span>|  
|`smallmoney`|<span data-ttu-id="39a29-182">4</span><span class="sxs-lookup"><span data-stu-id="39a29-182">4</span></span>|  
|<span data-ttu-id="39a29-183">`decimal` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="39a29-183">`decimal` <sup>1</sup></span></span>|<sup>*</sup>|  
|<span data-ttu-id="39a29-184">`numeric` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="39a29-184">`numeric` <sup>1</sup></span></span>|<sup>*</sup>|  
|`uniqueidentifier`|<span data-ttu-id="39a29-185">16</span><span class="sxs-lookup"><span data-stu-id="39a29-185">16</span></span>|  
|`timestamp`|<span data-ttu-id="39a29-186">8</span><span class="sxs-lookup"><span data-stu-id="39a29-186">8</span></span>|  
  
 <span data-ttu-id="39a29-187"><sup>1</sup> para obter mais informações sobre `decimal` os `numeric` tipos de dados e, consulte [decimal e numérico &#40;&#41;Transact-SQL ](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="39a29-187"><sup>1</sup> For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
 <span data-ttu-id="39a29-188">Em todos os casos anteriores, para criar um arquivo de dados para recarregar posteriormente no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que mantenha o espaço de armazenamento em um mínimo, use um prefixo de comprimento com o tipo de armazenamento de arquivo padrão e o tamanho do campo padrão.</span><span class="sxs-lookup"><span data-stu-id="39a29-188">In all of the preceding cases, to create a data file for later reloading into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that keeps the storage space to a minimum, use a length prefix with the default file storage type and the default field length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a29-189">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39a29-189">See Also</span></span>  
 <span data-ttu-id="39a29-190">[Utilitário bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="39a29-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="39a29-191">[Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="39a29-191">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="39a29-192">[Especificar terminadores de campo e linha &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="39a29-192">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 <span data-ttu-id="39a29-193">[Especificar o tamanho de prefixo em arquivos de dados usando bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="39a29-193">[Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="39a29-194">[Especificar tipo de armazenamento de arquivo usando bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="39a29-194">[Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md) </span></span>  
 [<span data-ttu-id="39a29-195">Manter valores nulos ou use os valores padrão durante a importação em massa &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="39a29-195">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
  
