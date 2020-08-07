---
title: bcp_control | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_control
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_control function
ms.assetid: 32187282-1385-4c52-9134-09f061eb44f5
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ea5d60da8069707a53f3bdf2de53345cd11090f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568539"
---
# <a name="bcp_control"></a><span data-ttu-id="ff191-102">bcp_control</span><span class="sxs-lookup"><span data-stu-id="ff191-102">bcp_control</span></span>
  <span data-ttu-id="ff191-103">Altera as configurações padrão de vários parâmetros de controle para uma cópia em massa entre um arquivo e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff191-103">Changes the default settings for various control parameters for a bulk copy between a file and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff191-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ff191-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_control (  
HDBC   
hdbc  
,  
INT   
eOption  
,  
void*   
iValue  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ff191-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ff191-105">Arguments</span></span>  
 <span data-ttu-id="ff191-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="ff191-106">*hdbc*</span></span>  
 <span data-ttu-id="ff191-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="ff191-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="ff191-108">*eOption*</span><span class="sxs-lookup"><span data-stu-id="ff191-108">*eOption*</span></span>  
 <span data-ttu-id="ff191-109">É um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="ff191-109">Is one of the following:</span></span>  
  
 <span data-ttu-id="ff191-110">BCPABORT</span><span class="sxs-lookup"><span data-stu-id="ff191-110">BCPABORT</span></span>  
 <span data-ttu-id="ff191-111">Para uma operação de cópia em massa que já está em andamento.</span><span class="sxs-lookup"><span data-stu-id="ff191-111">Stops a bulk-copy operation that is already in progress.</span></span> <span data-ttu-id="ff191-112">Chame **bcp_control** com um *eOption* de BCPABORT de outro thread para interromper uma operação de cópia em massa em execução.</span><span class="sxs-lookup"><span data-stu-id="ff191-112">Call **bcp_control** with an *eOption* of BCPABORT from another thread to stop a running bulk copy operation.</span></span> <span data-ttu-id="ff191-113">O parâmetro *iValue* é ignorado.</span><span class="sxs-lookup"><span data-stu-id="ff191-113">The *iValue* parameter is ignored.</span></span>  
  
 <span data-ttu-id="ff191-114">BCPBATCH</span><span class="sxs-lookup"><span data-stu-id="ff191-114">BCPBATCH</span></span>  
 <span data-ttu-id="ff191-115">É o número de linhas por lote.</span><span class="sxs-lookup"><span data-stu-id="ff191-115">Is the number of rows per batch.</span></span> <span data-ttu-id="ff191-116">O padrão é 0, que indica todas as linhas de uma tabela, quando os dados estão sendo extraídos, ou todas as linhas no arquivo de dados do usuário, quando os dados estão sendo copiados para um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff191-116">The default is 0, which indicates either all rows in a table, when data is being extracted, or all rows in the user data file, when data is being copied to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ff191-117">Um valor menor que 1 redefine BCPBATCH para o padrão.</span><span class="sxs-lookup"><span data-stu-id="ff191-117">A value less than 1 resets BCPBATCH to the default.</span></span>  
  
 <span data-ttu-id="ff191-118">BCPDELAYREADFMT</span><span class="sxs-lookup"><span data-stu-id="ff191-118">BCPDELAYREADFMT</span></span>  
 <span data-ttu-id="ff191-119">Um booliano, se definido como true, fará com que [bcp_readfmt](bcp-readfmt.md) seja lido na execução.</span><span class="sxs-lookup"><span data-stu-id="ff191-119">A Boolean, if set to true, will cause [bcp_readfmt](bcp-readfmt.md) to read at execution.</span></span> <span data-ttu-id="ff191-120">Se for false (o padrão), bcp_readfmt lerá imediatamente o arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="ff191-120">If false (the default), bcp_readfmt will immediately read the format file.</span></span> <span data-ttu-id="ff191-121">Ocorrerá um erro de sequência se BCPDELAYREADFMT for true e você chamar bcp_columns ou bcp_setcolfmt.</span><span class="sxs-lookup"><span data-stu-id="ff191-121">A sequence error will occur if BCPDELAYREADFMT is true and you call bcp_columns or bcp_setcolfmt.</span></span>  
  
 <span data-ttu-id="ff191-122">Um erro de sequência também ocorrerá se você chamar `bcp_control(hdbc,` BCPDELAYREADFMT `, (void *)FALSE)` depois `bcp_control(hdbc,` de chamar BCPDELAYREADFMT `, (void *)TRUE)` e bcp_writefmt.</span><span class="sxs-lookup"><span data-stu-id="ff191-122">A sequence error will also occur if you call `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)FALSE)` after calling `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)TRUE)` and bcp_writefmt.</span></span>  
  
 <span data-ttu-id="ff191-123">Para obter mais informações, veja [Descoberta de metadados](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="ff191-123">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="ff191-124">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="ff191-124">BCPFILECP</span></span>  
 <span data-ttu-id="ff191-125">*iValue* contém o número da página de código para o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="ff191-125">*iValue* contains the number of the code page for the data file.</span></span> <span data-ttu-id="ff191-126">Você pode especificar o número da página de código, como 1252 ou 850, ou como um destes valores:</span><span class="sxs-lookup"><span data-stu-id="ff191-126">You can specify the number of the code page, such as 1252 or 850, or one of these values:</span></span>  
  
 <span data-ttu-id="ff191-127">BCPFILE_ACP: os dados no arquivo estão no Microsoft Windows??</span><span class="sxs-lookup"><span data-stu-id="ff191-127">BCPFILE_ACP: data in the file is in the Microsoft Windows??</span></span> <span data-ttu-id="ff191-128">página de código do cliente.</span><span class="sxs-lookup"><span data-stu-id="ff191-128">code page of the client.</span></span>  
  
 <span data-ttu-id="ff191-129">BCPFILE_OEMCP: os dados do arquivo estão na página de código OEM do cliente (padrão).</span><span class="sxs-lookup"><span data-stu-id="ff191-129">BCPFILE_OEMCP: data in the file is in the OEM code page of the client (default).</span></span>  
  
 <span data-ttu-id="ff191-130">BCPFILE_RAW: os dados do arquivo estão na página de código do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff191-130">BCPFILE_RAW: data in the file is in the code page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ff191-131">BCPFILEFMT</span><span class="sxs-lookup"><span data-stu-id="ff191-131">BCPFILEFMT</span></span>  
 <span data-ttu-id="ff191-132">O número de versão do formato de arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="ff191-132">The version number of the data file format.</span></span> <span data-ttu-id="ff191-133">Pode ser 80 ([!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]), 90 ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]), 100 ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]), 110 ([!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]) ou 120 ([!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ff191-133">This can be 80 ([!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]), 90 ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]), 100 ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]), 110 ([!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]), or 120 ([!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="ff191-134">120 é o padrão.</span><span class="sxs-lookup"><span data-stu-id="ff191-134">120 is the default.</span></span> <span data-ttu-id="ff191-135">Isso é útil para exportar e importar dados em formatos que tinham suporte em versões anteriores do servidor.</span><span class="sxs-lookup"><span data-stu-id="ff191-135">This is useful for exporting and importing data in formats that were supported by earlier version of the server.</span></span> <span data-ttu-id="ff191-136">Por exemplo, para importar dados que foram obtidos de uma coluna de texto em um [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] servidor em uma coluna **varchar (max)** em um [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] servidor ou posterior, você deve especificar 80.</span><span class="sxs-lookup"><span data-stu-id="ff191-136">For example, to import data that was obtained from a text column in a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server into a **varchar(max)** column in a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later server, you should specify 80.</span></span> <span data-ttu-id="ff191-137">Da mesma forma, se você especificar 80 ao exportar dados de uma coluna **varchar (max)** , ele será salvo da mesma forma que as colunas de texto são salvas no [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] formato e pode ser importado para uma coluna de texto de um [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] servidor.</span><span class="sxs-lookup"><span data-stu-id="ff191-137">Similarly, if you specify 80 when exporting data from a **varchar(max)** column, it will be saved just like text columns are saved in the [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] format, and can be imported into a text column of a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server.</span></span>  
  
 <span data-ttu-id="ff191-138">BCPFIRST</span><span class="sxs-lookup"><span data-stu-id="ff191-138">BCPFIRST</span></span>  
 <span data-ttu-id="ff191-139">É a primeira linha de dados a ser copiada em um arquivo ou tabela.</span><span class="sxs-lookup"><span data-stu-id="ff191-139">Is the first row of data to file or table to copy.</span></span> <span data-ttu-id="ff191-140">O padrão é 1; um valor menor que 1 redefine essa opção para seu valor padrão.</span><span class="sxs-lookup"><span data-stu-id="ff191-140">The default is 1; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="ff191-141">BCPFIRSTEX</span><span class="sxs-lookup"><span data-stu-id="ff191-141">BCPFIRSTEX</span></span>  
 <span data-ttu-id="ff191-142">Para operações de saída BCP, especifica a primeira linha da tabela do banco de dados a ser copiada no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="ff191-142">For BCP out operations, specifies the first row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="ff191-143">Para BCP em operações, especifica a primeira linha do arquivo de dados a ser copiada na tabela de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ff191-143">For BCP in operations, specifies the first row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="ff191-144">Espera-se que o parâmetro *iValue* seja o endereço de um inteiro de 64 bits assinado contendo o valor.</span><span class="sxs-lookup"><span data-stu-id="ff191-144">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="ff191-145">O valor máximo que pode ser passado a BCPFIRSTEX é 2^63-1.</span><span class="sxs-lookup"><span data-stu-id="ff191-145">The maximum value that can be passed to BCPFIRSTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="ff191-146">BCPFMTXML</span><span class="sxs-lookup"><span data-stu-id="ff191-146">BCPFMTXML</span></span>  
 <span data-ttu-id="ff191-147">Especifica que o arquivo de formato gerado deve estar no formato XML.</span><span class="sxs-lookup"><span data-stu-id="ff191-147">Specifies that the format file generated should be in XML format.</span></span> <span data-ttu-id="ff191-148">Eles está desativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="ff191-148">It is off by default.</span></span>  
  
 <span data-ttu-id="ff191-149">Os arquivos de formato XML apresentam maior flexibilidade, mas com alguns restrições adicionadas.</span><span class="sxs-lookup"><span data-stu-id="ff191-149">XML format files provide greater flexibility but with some added constraints.</span></span> <span data-ttu-id="ff191-150">Por exemplo, você não pode especificar o prefixo e o terminador para um campo simultaneamente, o que era possível nos arquivos de formato mais antigos.</span><span class="sxs-lookup"><span data-stu-id="ff191-150">For example, you can not specify the prefix and terminator for a field simultaneously, which was possible in older format files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff191-151">Os arquivos de formato XML só são suportados quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é instalado junto com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="ff191-151">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed along with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="ff191-152">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="ff191-152">BCPHINTS</span></span>  
 <span data-ttu-id="ff191-153">*iValue* contém um ponteiro de cadeia de caracteres SQLTCHAR.</span><span class="sxs-lookup"><span data-stu-id="ff191-153">*iValue* contains an SQLTCHAR character string pointer.</span></span> <span data-ttu-id="ff191-154">A cadeia de caracteres endereçada especifica dicas de processamento da cópia em massa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou uma instrução Transact-SQL que retorna um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="ff191-154">The string addressed specifies either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk-copy processing hints or a Transact-SQL statement that returns a result set.</span></span> <span data-ttu-id="ff191-155">Se uma instrução Transact-SQL especificada retornar mais de um conjunto de resultados, todos os conjuntos de resultados depois do primeiro serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="ff191-155">If a Transact-SQL statement is specified that returns more than one result set, all result sets after the first are ignored.</span></span> <span data-ttu-id="ff191-156">Para obter mais informações sobre dicas de processamento de cópia em massa, consulte [utilitário bcp](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ff191-156">For more information about bulk-copy processing hints, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
 <span data-ttu-id="ff191-157">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="ff191-157">BCPKEEPIDENTITY</span></span>  
 <span data-ttu-id="ff191-158">Quando *iValue* é true, especifica que as funções de cópia em massa inserem valores de dados fornecidos para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] colunas definidas com uma restrição de identidade.</span><span class="sxs-lookup"><span data-stu-id="ff191-158">When *iValue* is TRUE, specifies that bulk copy functions insert data values supplied for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns defined with an identity constraint.</span></span> <span data-ttu-id="ff191-159">O arquivo de entrada deve fornecer valores para as colunas de identidade.</span><span class="sxs-lookup"><span data-stu-id="ff191-159">The input file must supply values for the identity columns.</span></span> <span data-ttu-id="ff191-160">Se essa opção não for definida, novos valores de identidade serão gerados para as linhas inseridas.</span><span class="sxs-lookup"><span data-stu-id="ff191-160">If this is not set, new identity values are generated for the inserted rows.</span></span> <span data-ttu-id="ff191-161">Quaisquer dados contidos no arquivo para as colunas de identidade serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="ff191-161">Any data present in the file for the identity columns is ignored.</span></span>  
  
 <span data-ttu-id="ff191-162">BCPKEEPNULLS</span><span class="sxs-lookup"><span data-stu-id="ff191-162">BCPKEEPNULLS</span></span>  
 <span data-ttu-id="ff191-163">Especifica se valores de dados vazios no arquivo serão convertidos em valores NULL na tabela [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff191-163">Specifies whether empty data values in the file will be converted to NULL values in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="ff191-164">Quando *iValue* for true, os valores vazios serão convertidos em NULL na [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela.</span><span class="sxs-lookup"><span data-stu-id="ff191-164">When *iValue* is TRUE, empty values will be converted to NULL in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="ff191-165">O padrão será converter valores vazios em um valor padrão para a coluna na tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se houver um padrão.</span><span class="sxs-lookup"><span data-stu-id="ff191-165">The default is for empty values to be converted to a default value for the column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table if a default exists.</span></span>  
  
 <span data-ttu-id="ff191-166">BCPLAST</span><span class="sxs-lookup"><span data-stu-id="ff191-166">BCPLAST</span></span>  
 <span data-ttu-id="ff191-167">É a última linha a ser copiada.</span><span class="sxs-lookup"><span data-stu-id="ff191-167">Is the last row to copy.</span></span> <span data-ttu-id="ff191-168">O padrão é copiar todas as linhas; um valor menor que 1 redefine essa opção para seu padrão.</span><span class="sxs-lookup"><span data-stu-id="ff191-168">The default is to copy all rows; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="ff191-169">BCPLASTEX</span><span class="sxs-lookup"><span data-stu-id="ff191-169">BCPLASTEX</span></span>  
 <span data-ttu-id="ff191-170">Para operações de saída BCP, especifica a última linha da tabela do banco de dados a ser copiada no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="ff191-170">For BCP out operations, specifies the last row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="ff191-171">Para BCP em operações, especifica a última linha do arquivo de dados a ser copiada na tabela do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ff191-171">For BCP in operations, specifies the last row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="ff191-172">Espera-se que o parâmetro *iValue* seja o endereço de um inteiro de 64 bits assinado contendo o valor.</span><span class="sxs-lookup"><span data-stu-id="ff191-172">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="ff191-173">O valor de máximo que pode ser passado para BCPLASTEX é 2^63-1.</span><span class="sxs-lookup"><span data-stu-id="ff191-173">The maximum value that can be passed to BCPLASTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="ff191-174">BCPMAXERRS</span><span class="sxs-lookup"><span data-stu-id="ff191-174">BCPMAXERRS</span></span>  
 <span data-ttu-id="ff191-175">É o número de erros permitido antes de ocorrer uma falha na operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="ff191-175">Is the number of errors allowed before the bulk copy operation fails.</span></span> <span data-ttu-id="ff191-176">O padrão é 10; um valor menor que 1 redefine essa opção como seu padrão.</span><span class="sxs-lookup"><span data-stu-id="ff191-176">The default is 10; a value less than 1 resets this option to its default.</span></span> <span data-ttu-id="ff191-177">A cópia em massa impõe um máximo de 65.535 erros.</span><span class="sxs-lookup"><span data-stu-id="ff191-177">Bulk copy imposes a maximum of 65,535 errors.</span></span> <span data-ttu-id="ff191-178">Uma tentativa de definir esta opção como um valor maior que 65.535 resulta na definição da opção como 65.535.</span><span class="sxs-lookup"><span data-stu-id="ff191-178">An attempt to set this option to a value larger than 65,535 results in the option being set to 65,535.</span></span>  
  
 <span data-ttu-id="ff191-179">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="ff191-179">BCPODBC</span></span>  
 <span data-ttu-id="ff191-180">Quando TRUE, especifica que os valores **DateTime** e **smalldatetime** salvos no formato de caractere usarão o prefixo e o sufixo da sequência de saída do carimbo de data e hora do ODBC.</span><span class="sxs-lookup"><span data-stu-id="ff191-180">When TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will use the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="ff191-181">A opção BCPODBC só se aplica a BCP_OUT.</span><span class="sxs-lookup"><span data-stu-id="ff191-181">The BCPODBC option only applies to BCP_OUT.</span></span>  
  
 <span data-ttu-id="ff191-182">Quando for falso, um valor **DateTime** que representa 1º de janeiro de 1997 será convertido para a cadeia de caracteres: 1997-01-01 00:00:00.000.</span><span class="sxs-lookup"><span data-stu-id="ff191-182">When FALSE, a **datetime** value representing January 1, 1997 is converted to the character string: 1997-01-01 00:00:00.000.</span></span> <span data-ttu-id="ff191-183">Quando TRUE, o mesmo valor **DateTime** é representado como: {ts ' 1997-01-01 00:00:00.000 '}.</span><span class="sxs-lookup"><span data-stu-id="ff191-183">When TRUE, the same **datetime** value is represented as: {ts '1997-01-01 00:00:00.000'}.</span></span>  
  
 <span data-ttu-id="ff191-184">BCPROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="ff191-184">BCPROWCOUNT</span></span>  
 <span data-ttu-id="ff191-185">Retorna o número de linhas afetadas pela operação BCP atual (ou última).</span><span class="sxs-lookup"><span data-stu-id="ff191-185">Returns the number of rows affected by the current (or last) BCP operation.</span></span>  
  
 <span data-ttu-id="ff191-186">BCPTEXTFILE</span><span class="sxs-lookup"><span data-stu-id="ff191-186">BCPTEXTFILE</span></span>  
 <span data-ttu-id="ff191-187">Quando TRUE, especifica que o arquivo de dados é um arquivo de texto, em vez de um arquivo binário.</span><span class="sxs-lookup"><span data-stu-id="ff191-187">When TRUE, specifies that the data file is a text file, rather than a binary file.</span></span> <span data-ttu-id="ff191-188">Se o arquivo for um arquivo de texto, BCP determinará se ele é ou não Unicode, verificando o marcador de bytes Unicode nos dois primeiros bytes do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="ff191-188">If the file is a text file, BCP determines whether or not it is Unicode by checking the Unicode byte marker in the first two bytes of the data file.</span></span>  
  
 <span data-ttu-id="ff191-189">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="ff191-189">BCPUNICODEFILE</span></span>  
 <span data-ttu-id="ff191-190">Quando TRUE, especifica que o arquivo de entrada é um arquivo Unicode.</span><span class="sxs-lookup"><span data-stu-id="ff191-190">When TRUE, specifies the input file is a Unicode file.</span></span>  
  
 <span data-ttu-id="ff191-191">*iValue*</span><span class="sxs-lookup"><span data-stu-id="ff191-191">*iValue*</span></span>  
 <span data-ttu-id="ff191-192">É o valor para o *eOption*especificado.</span><span class="sxs-lookup"><span data-stu-id="ff191-192">Is the value for the specified *eOption*.</span></span> <span data-ttu-id="ff191-193">*iValue* é uma conversão de valor inteiro (LONGLONG) em um ponteiro void para permitir a expansão futura para valores de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="ff191-193">*iValue* is an integer (LONGLONG) value cast to a void pointer to allow for future expansion to 64 bit values.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ff191-194">Retornos</span><span class="sxs-lookup"><span data-stu-id="ff191-194">Returns</span></span>  
 <span data-ttu-id="ff191-195">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="ff191-195">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff191-196">Comentários</span><span class="sxs-lookup"><span data-stu-id="ff191-196">Remarks</span></span>  
 <span data-ttu-id="ff191-197">Esta função define vários parâmetros de controle para operações de cópia em massa, incluindo o número de erros permitido antes do cancelamento de uma cópia em massa, os número da primeira e da última linhas a serem copiadas de um arquivo de dados e o tamanho do lote.</span><span class="sxs-lookup"><span data-stu-id="ff191-197">This function sets various control parameters for bulk-copy operations, including the number of errors allowed before canceling a bulk copy, the numbers of the first and last rows to copy from a data file, and the batch size.</span></span>  
  
 <span data-ttu-id="ff191-198">Esta função é usada também para especificar a instrução SELECT durante uma operação de cópia em massa de saída do conjunto de resultados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de uma SELECT.</span><span class="sxs-lookup"><span data-stu-id="ff191-198">This function is also used to specify the SELECT statement when bulk copying out from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] the result set of a SELECT.</span></span> <span data-ttu-id="ff191-199">Defina *eOption* como BCPHINTS e defina *iValue* para ter um ponteiro para uma cadeia de caracteres SQLTCHAR contendo a instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="ff191-199">Set *eOption* to BCPHINTS and set *iValue* to have a pointer to an SQLTCHAR string containing the SELECT statement.</span></span>  
  
 <span data-ttu-id="ff191-200">Esses parâmetros de controle só são úteis ao fazer cópias entre um arquivo de usuário e uma tabela [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff191-200">These control parameters are only meaningful when copying between a user file and an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="ff191-201">As configurações de parâmetros de controle não têm nenhum efeito sobre as linhas copiadas para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="ff191-201">Control parameter settings have no effect on rows copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff191-202">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ff191-202">Example</span></span>  
  
```  
// Variables like henv not specified.  
SQLHDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("address"), _T("address.add"), _T("addr.err"),  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the number of rows per batch.   
if (bcp_control(hdbc, BCPBATCH, (void*) 1000) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set file column count.   
if (bcp_columns(hdbc, 1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the file format.   
if (bcp_colfmt(hdbc, 1, 0, 0, SQL_VARLEN_DATA, '\n', 1, 1)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
printf_s("%ld rows processed by bulk copy.", nRowsProcessed);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff191-203">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ff191-203">See Also</span></span>  
 [<span data-ttu-id="ff191-204">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="ff191-204">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
