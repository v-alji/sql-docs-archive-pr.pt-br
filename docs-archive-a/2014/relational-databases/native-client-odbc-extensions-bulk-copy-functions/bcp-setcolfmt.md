---
title: bcp_setcolfmt | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_setcolfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_setcolfmt function
ms.assetid: afb47987-39e7-4079-ad66-e0abf4d4c72b
author: rothja
ms.author: jroth
ms.openlocfilehash: bb3b1da62ab4e98ed4497dd11fcc20163025058b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575103"
---
# <a name="bcp_setcolfmt"></a><span data-ttu-id="fe9e3-102">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="fe9e3-102">bcp_setcolfmt</span></span>
  <span data-ttu-id="fe9e3-103">A função **bcp_setcolfmt** substitui [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="fe9e3-103">The **bcp_setcolfmt** function supersedes the [bcp_colfmt](bcp-colfmt.md).</span></span> <span data-ttu-id="fe9e3-104">Ao especificar a ordenação de coluna, a função **bcp_setcolfmt** precisa ser usada.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-104">In specifying the column collation, the **bcp_setcolfmt** function must be used.</span></span> <span data-ttu-id="fe9e3-105">É possível usar[bcp_setbulkmode](bcp-setbulkmode.md) para especificar mais de um formato de coluna.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-105">[bcp_setbulkmode](bcp-setbulkmode.md) can be used to specify more than one column format.</span></span>  
  
 <span data-ttu-id="fe9e3-106">Essa função oferece uma abordagem flexível à especificação do formato de coluna em uma operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-106">This function provides a flexible approach to specifying the column format in a bulk copy operation.</span></span> <span data-ttu-id="fe9e3-107">Ela é usada para definir atributos de formato de coluna individuais.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-107">It is used to set individual column format attributes.</span></span> <span data-ttu-id="fe9e3-108">Cada chamada para **bcp_setcolfmt** define um atributo de formato de coluna.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-108">Each call to **bcp_setcolfmt** sets one column format attribute.</span></span>  
  
 <span data-ttu-id="fe9e3-109">A função **bcp_setcolfmt** especifica o formato de origem ou destino dos dados em um arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-109">The **bcp_setcolfmt** function specifies the source or target format of the data in a user file.</span></span> <span data-ttu-id="fe9e3-110">Quando usada como formato de origem, **bcp_setcolfmt** especifica o formato de um arquivo de dados existente usado como fonte de dados em uma cópia em massa para uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe9e3-110">When used as a source format, **bcp_setcolfmt** specifies the format of an existing data file used as a data source of data in a bulk copy to a table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fe9e3-111">Quando usado como um formato de destino, o arquivo de dados é criado usando os formatos de coluna especificados com **bcp_setcolfmt**.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-111">When used as a target format, the data file is created using the column formats specified with **bcp_setcolfmt**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe9e3-112">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fe9e3-112">Syntax</span></span>  
  
```  
  
RETCODE bcp_setcolfmt (  
HDBC   
hdbc  
,  
INT   
field  
,  
INT   
property  
,  
void*   
pValue  
,  
INT   
cbValue  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="fe9e3-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fe9e3-113">Arguments</span></span>  
 <span data-ttu-id="fe9e3-114">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="fe9e3-114">*hdbc*</span></span>  
 <span data-ttu-id="fe9e3-115">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-115">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="fe9e3-116">*campo*</span><span class="sxs-lookup"><span data-stu-id="fe9e3-116">*field*</span></span>  
 <span data-ttu-id="fe9e3-117">É o número de coluna ordinal para o qual a propriedade está sendo definida.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-117">Is the ordinal column number for which the property is being set.</span></span>  
  
 <span data-ttu-id="fe9e3-118">*property*</span><span class="sxs-lookup"><span data-stu-id="fe9e3-118">*property*</span></span>  
 <span data-ttu-id="fe9e3-119">É um das constantes de propriedade.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-119">Is one of the property constants.</span></span> <span data-ttu-id="fe9e3-120">As constantes de propriedade são definidas nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-120">Property constants are defined in this table.</span></span>  
  
|<span data-ttu-id="fe9e3-121">Propriedade</span><span class="sxs-lookup"><span data-stu-id="fe9e3-121">Property</span></span>|<span data-ttu-id="fe9e3-122">Valor</span><span class="sxs-lookup"><span data-stu-id="fe9e3-122">Value</span></span>|<span data-ttu-id="fe9e3-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="fe9e3-123">Description</span></span>|  
|--------------|-----------|-----------------|  
|<span data-ttu-id="fe9e3-124">BCP_FMT_TYPE</span><span class="sxs-lookup"><span data-stu-id="fe9e3-124">BCP_FMT_TYPE</span></span>|<span data-ttu-id="fe9e3-125">BYTE</span><span class="sxs-lookup"><span data-stu-id="fe9e3-125">BYTE</span></span>|<span data-ttu-id="fe9e3-126">É o tipo de dados desta coluna no arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-126">Is the data type of this column in the user file.</span></span> <span data-ttu-id="fe9e3-127">Se for diferente do tipo de dados da coluna correspondente na tabela do banco de dados, a cópia em massa converterá os dados se possível.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-127">If different from the data type of the corresponding column in the database table, bulk copy converts the data if possible.</span></span><br /><br /> <span data-ttu-id="fe9e3-128">O parâmetro BCP_FMT_TYPE é enumerado pelos tokens de tipo de dados do SQL Server em sqlncli.h, e não nos enumeradores de tipo de dados ODBC C.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-128">The BCP_FMT_TYPE parameter is enumerated by the SQL Server data type tokens in sqlncli.h, rather than the ODBC C data type enumerators.</span></span> <span data-ttu-id="fe9e3-129">Por exemplo, você pode especificar uma cadeia de caracteres, o tipo ODBC SQL_C_CHAR, usando o tipo SQLCHARACTER específico do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe9e3-129">For example, you can specify a character string, ODBC type SQL_C_CHAR, using the SQLCHARACTER type specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="fe9e3-130">Para especificar a representação de dados padrão do tipo de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , defina esse parâmetro como 0.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-130">To specify the default data representation for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, set this parameter to 0.</span></span><br /><br /> <span data-ttu-id="fe9e3-131">Para uma cópia em massa do SQL Server para um arquivo, quando BCP_FMT_TYPE for SQLDECIMAL ou SQLNUMERIC:</span><span class="sxs-lookup"><span data-stu-id="fe9e3-131">For a bulk copy out of SQL Server into a file, when BCP_FMT_TYPE is SQLDECIMAL or SQLNUMERIC:</span></span><br /><br /> <span data-ttu-id="fe9e3-132">-Se a coluna de origem não for **decimal** ou **numeric**, a precisão e a escala padrão serão usadas.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-132">-   If the source column is not **decimal** or **numeric**, the default precision and scale are used.</span></span><br /><span data-ttu-id="fe9e3-133">-Se a coluna de origem for **decimal** ou **numeric**, a precisão e a escala da coluna de origem serão usadas.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-133">-   If the source column is **decimal** or **numeric**, the precision and scale of the source column are used.</span></span>|  
|<span data-ttu-id="fe9e3-134">BCP_FMT_INDICATOR_LEN</span><span class="sxs-lookup"><span data-stu-id="fe9e3-134">BCP_FMT_INDICATOR_LEN</span></span>|<span data-ttu-id="fe9e3-135">INT</span><span class="sxs-lookup"><span data-stu-id="fe9e3-135">INT</span></span>|<span data-ttu-id="fe9e3-136">É o comprimento em bytes do indicador (prefixo).</span><span class="sxs-lookup"><span data-stu-id="fe9e3-136">Is the length in bytes of the indicator (prefix).</span></span><br /><br /> <span data-ttu-id="fe9e3-137">É o comprimento, em bytes, de um indicador de comprimento/nulo nos dados de coluna.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-137">It is the length, in bytes, of a length/null indicator within the column data.</span></span> <span data-ttu-id="fe9e3-138">Os valores de comprimento de indicador válidos são 0 (quando nenhum indicador é usado), 1, 2 ou 4.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-138">Valid indicator length values are 0 (when using no indicator), 1, 2, or 4.</span></span><br /><br /> <span data-ttu-id="fe9e3-139">Para especificar o uso do indicador de cópia em massa padrão, defina esse parâmetro como SQL_VARLEN_DATA.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-139">To specify default bulk copy indicator usage, set this parameter to SQL_VARLEN_DATA.</span></span><br /><br /> <span data-ttu-id="fe9e3-140">Os indicadores aparecem na memória diretamente antes de quaisquer dados, e no arquivo de dados diretamente antes dos dados aos quais se aplicam.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-140">Indicators appear in memory directly before any data, and in the data file directly before the data to which they apply.</span></span><br /><br /> <span data-ttu-id="fe9e3-141">Se for usada mais de uma maneira de especificar um comprimento de coluna de arquivo de dados (como um indicador e um comprimento de coluna máximo ou um indicador e uma sequência de terminador), a cópia em massa escolherá aquela que resultar na menor quantidade de dados sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-141">If more than one means of specifying a data file column length is used (such as an indicator and a maximum column length, or an indicator and a terminator sequence), bulk copy chooses the one that results in the least amount of data being copied.</span></span><br /><br /> <span data-ttu-id="fe9e3-142">Os arquivos de dados gerados pela cópia em massa quando nenhuma intervenção de usuário ajusta o formato dos dados contêm indicadores quando os dados de coluna podem variar em comprimento ou a coluna pode aceitar NULL como valor.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-142">Data files generated by bulk copy when no user intervention adjusts the format of the data contain indicators when the column data can vary in length or the column can accept NULL as a value.</span></span>|  
|<span data-ttu-id="fe9e3-143">BCP_FMT_DATA_LEN</span><span class="sxs-lookup"><span data-stu-id="fe9e3-143">BCP_FMT_DATA_LEN</span></span>|<span data-ttu-id="fe9e3-144">DBINT</span><span class="sxs-lookup"><span data-stu-id="fe9e3-144">DBINT</span></span>|<span data-ttu-id="fe9e3-145">É o comprimento em bytes dos dados (comprimento da coluna).</span><span class="sxs-lookup"><span data-stu-id="fe9e3-145">Is the length in bytes of the data (column length)</span></span><br /><br /> <span data-ttu-id="fe9e3-146">É o comprimento máximo, em bytes, dos dados dessa coluna no arquivo de usuário, sem incluir o comprimento de qualquer indicador de comprimento ou terminador.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-146">It is the maximum length, in bytes, of this column's data in the user file, not including the length of any length indicator or terminator.</span></span><br /><br /> <span data-ttu-id="fe9e3-147">A definição de BCP_FMT_DATA_LEN como SQL_NULL_DATA indica que todos os valores na coluna de arquivo de dados são, ou deveriam ser, definidos como NULL.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-147">Setting BCP_FMT_DATA_LEN to SQL_NULL_DATA indicates that all values in the data file column are, or should be set to, NULL.</span></span><br /><br /> <span data-ttu-id="fe9e3-148">A definição de BCP_FMT_DATA_LEN como SQL_VARLEN_DATA indica que o sistema deveria determinar o comprimento dos dados em cada coluna.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-148">Setting BCP_FMT_DATA_LEN to SQL_VARLEN_DATA indicates that the system should determine the length of data in each column.</span></span> <span data-ttu-id="fe9e3-149">Para algumas colunas, isso poderia significar que um indicador de comprimento/nulo é gerado para anteceder os dados em uma cópia do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ou que o indicador é esperado nos dados copiados para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe9e3-149">For some columns, this could mean that a length/null indicator is generated to precede data on a copy from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or that the indicator is expected in data copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="fe9e3-150">Para tipos de dados binários e de caractere do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , BCP_FMT_DATA_LEN pode ser SQL_VARLEN_DATA, SQL_NULL_DATA, 0 ou algum valor positivo.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-150">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, BCP_FMT_DATA_LEN can be SQL_VARLEN_DATA, SQL_NULL_DATA, 0, or some positive value.</span></span> <span data-ttu-id="fe9e3-151">Se BCP_FMT_DATA_LEN for SQL_VARLEN_DATA, o sistema usará o indicador de comprimento, se estiver presente, ou uma sequência de terminador para determinar o comprimento dos dados.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-151">If BCP_FMT_DATA_LEN is SQL_VARLEN_DATA, the system uses either the length indicator, if present, or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="fe9e3-152">Se forem fornecidos um indicador de comprimento e uma sequência de terminador, a cópia em massa usará aquele que resultar na menor quantidade de dados sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-152">If both a length indicator and a terminator sequence are supplied, bulk copy uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="fe9e3-153">Se BCP_FMT_DATA_LEN for SQL_VARLEN_DATA, o tipo de dados for um tipo binário ou de caractere do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e nem um indicador de comprimento nem uma sequência de terminador for especificado, o sistema retornará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-153">If BCP_FMT_DATA_LEN is SQL_VARLEN_DATA, the data type is an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span><br /><br /> <span data-ttu-id="fe9e3-154">Se BCP_FMT_DATA_LEN for 0 ou um valor positivo, o sistema usará BCP_FMT_DATA_LEN como o comprimento de dados máximo.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-154">If BCP_FMT_DATA_LEN is 0 or a positive value, the system uses BCP_FMT_DATA_LEN as the maximum data length.</span></span> <span data-ttu-id="fe9e3-155">Entretanto, se, além de um BCP_FMT_DATA_LEN positivo, for fornecido um indicador de comprimento ou uma sequência de terminador, o sistema determinará o comprimento dos dados usando o método que resultar na menor quantidade de dados sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-155">However, if, in addition to a positive BCP_FMT_DATA_LEN, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span><br /><br /> <span data-ttu-id="fe9e3-156">O valor BCP_FMT_DATA_LEN representa a contagem de bytes dos dados.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-156">The BCP_FMT_DATA_LEN value represents the count of bytes of data.</span></span> <span data-ttu-id="fe9e3-157">Se os dados de caractere forem representados por caracteres que abranjam Unicode, um valor de parâmetro BCP_FMT_DATA_LEN positivo representará a quantidade de caracteres multiplicada pelo tamanho, em bytes, de cada caractere.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-157">If character data is represented by Unicode wide characters, then a positive BCP_FMT_DATA_LEN parameter value represents the number of characters multiplied by the size, in bytes, of each character.</span></span>|  
|<span data-ttu-id="fe9e3-158">BCP_FMT_TERMINATOR</span><span class="sxs-lookup"><span data-stu-id="fe9e3-158">BCP_FMT_TERMINATOR</span></span>|<span data-ttu-id="fe9e3-159">LPCBYTE</span><span class="sxs-lookup"><span data-stu-id="fe9e3-159">LPCBYTE</span></span>|<span data-ttu-id="fe9e3-160">Ponteiro para a sequência de terminador (ANSI ou Unicode, conforme apropriado) a ser usado para esta coluna.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-160">Pointer to the terminator sequence (either ANSI or Unicode as appropriate) to be used for this column.</span></span> <span data-ttu-id="fe9e3-161">Este parâmetro é útil principalmente para tipos de dados character porque todos os outros tipos têm comprimento fixo ou, no caso de dados binary, exigem um indicador de comprimento que permite registrar com precisão o número de bytes presentes.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-161">This parameter is useful mainly for character data types because all other types are of fixed length or, in the case of binary data, require an indicator of length to accurately record the number of bytes present.</span></span><br /><br /> <span data-ttu-id="fe9e3-162">Para evitar encerrar os dados extraídos ou indicar que os dados em um arquivo de usuário não foram encerrados, defina este parâmetro como NULL.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-162">To avoid terminating extracted data, or to indicate that data in a user file is not terminated, set this parameter to NULL.</span></span><br /><br /> <span data-ttu-id="fe9e3-163">Se for usada mais de uma maneira de especificar um comprimento de coluna de arquivo de usuário (como um terminador e um indicador de comprimento ou um terminador e um comprimento de coluna máximo), a cópia em massa escolherá aquela que resultar na menor quantidade de dados sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-163">If more than one means of specifying a user-file column length is used (such as a terminator and a length indicator, or a terminator and a maximum column length), bulk copy chooses the one that results in the least amount of data being copied.</span></span><br /><br /> <span data-ttu-id="fe9e3-164">A API de cópia em massa executa a conversão de caracteres Unicode em MBCS conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-164">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="fe9e3-165">É necessário tomar cuidado para garantir que tanto a cadeia de caracteres de bytes do terminador quanto o comprimento da cadeia de caracteres de bytes estejam definidos corretamente.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-165">Care must be taken to ensure that both the terminator byte string and the length of the byte string are set correctly.</span></span>|  
|<span data-ttu-id="fe9e3-166">BCP_FMT_SERVER_COL</span><span class="sxs-lookup"><span data-stu-id="fe9e3-166">BCP_FMT_SERVER_COL</span></span>|<span data-ttu-id="fe9e3-167">INT</span><span class="sxs-lookup"><span data-stu-id="fe9e3-167">INT</span></span>|<span data-ttu-id="fe9e3-168">Posição ordinal da coluna no banco de dados</span><span class="sxs-lookup"><span data-stu-id="fe9e3-168">Ordinal position of the column in the database</span></span>|  
|<span data-ttu-id="fe9e3-169">BCP_FMT_COLLATION</span><span class="sxs-lookup"><span data-stu-id="fe9e3-169">BCP_FMT_COLLATION</span></span>|<span data-ttu-id="fe9e3-170">LPCSTR</span><span class="sxs-lookup"><span data-stu-id="fe9e3-170">LPCSTR</span></span>|<span data-ttu-id="fe9e3-171">Nome da ordenação.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-171">Collation name.</span></span>|  
  
 <span data-ttu-id="fe9e3-172">*Valores*</span><span class="sxs-lookup"><span data-stu-id="fe9e3-172">*pValue*</span></span>  
 <span data-ttu-id="fe9e3-173">É o ponteiro para o valor que será associado a *property*.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-173">Is the pointer to the value to associate to the *property*.</span></span> <span data-ttu-id="fe9e3-174">Ele permite que cada propriedade de formato de coluna seja definida individualmente.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-174">It allows each column format property to be set individually.</span></span>  
  
 <span data-ttu-id="fe9e3-175">*cbvalue*</span><span class="sxs-lookup"><span data-stu-id="fe9e3-175">*cbvalue*</span></span>  
 <span data-ttu-id="fe9e3-176">É o comprimento do buffer da propriedade em bytes.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-176">Is the length of the property buffer in bytes.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="fe9e3-177">Retornos</span><span class="sxs-lookup"><span data-stu-id="fe9e3-177">Returns</span></span>  
 <span data-ttu-id="fe9e3-178">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-178">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe9e3-179">Comentários</span><span class="sxs-lookup"><span data-stu-id="fe9e3-179">Remarks</span></span>  
 <span data-ttu-id="fe9e3-180">Esta função substitui a função **bcp_colfmt** .</span><span class="sxs-lookup"><span data-stu-id="fe9e3-180">This function supersedes the **bcp_colfmt** function.</span></span> <span data-ttu-id="fe9e3-181">É oferecida toda a funcionalidade de **bcp_colfmt** na função **bcp_setcolfmt** .</span><span class="sxs-lookup"><span data-stu-id="fe9e3-181">All the functionality of **bcp_colfmt** is provided in **bcp_setcolfmt** function.</span></span> <span data-ttu-id="fe9e3-182">Além disso, também há suporte à ordenação de coluna.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-182">In addition, support for column collation is also provided.</span></span> <span data-ttu-id="fe9e3-183">É recomendável que os atributos de formato de coluna a seguir sejam definidos nesta ordem:</span><span class="sxs-lookup"><span data-stu-id="fe9e3-183">It is recommended that the following column format attributes be set in the order given below:</span></span>  
  
 <span data-ttu-id="fe9e3-184">BCP_FMT_SERVER_COL</span><span class="sxs-lookup"><span data-stu-id="fe9e3-184">BCP_FMT_SERVER_COL</span></span>  
  
 <span data-ttu-id="fe9e3-185">BCP_FMT_DATA_LEN</span><span class="sxs-lookup"><span data-stu-id="fe9e3-185">BCP_FMT_DATA_LEN</span></span>  
  
 <span data-ttu-id="fe9e3-186">BCP_FMT_TYPE</span><span class="sxs-lookup"><span data-stu-id="fe9e3-186">BCP_FMT_TYPE</span></span>  
  
 <span data-ttu-id="fe9e3-187">A função **bcp_setcolfmt** permite especificar o formato do arquivo de usuário para cópias em massa.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-187">The **bcp_setcolfmt** function allows you to specify the user-file format for bulk copies.</span></span> <span data-ttu-id="fe9e3-188">Para cópia em massa, um formato contém as seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="fe9e3-188">For bulk copy, a format contains the following parts:</span></span>  
  
-   <span data-ttu-id="fe9e3-189">Um mapeamento de colunas do arquivo de usuário para colunas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-189">A mapping from user-file columns to database columns.</span></span>  
  
-   <span data-ttu-id="fe9e3-190">O tipo de dados de cada coluna do arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-190">The data type of each user-file column.</span></span>  
  
-   <span data-ttu-id="fe9e3-191">O comprimento do indicador opcional para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-191">The length of the optional indicator for each column.</span></span>  
  
-   <span data-ttu-id="fe9e3-192">O comprimento máximo dos dados por coluna do arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-192">The maximum length of data per user-file column.</span></span>  
  
-   <span data-ttu-id="fe9e3-193">A sequência de bytes de encerramento opcional para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-193">The optional terminating byte sequence for each column.</span></span>  
  
-   <span data-ttu-id="fe9e3-194">O comprimento da sequência de bytes de encerramento opcional.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-194">The length of the optional terminating byte sequence.</span></span>  
  
 <span data-ttu-id="fe9e3-195">Cada chamada para **bcp_setcolfmt** especifica o formato para uma coluna do arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-195">Each call to **bcp_setcolfmt** specifies the format for one user-file column.</span></span> <span data-ttu-id="fe9e3-196">Por exemplo, para alterar as configurações padrão para três colunas em um arquivo de dados de usuário de cinco colunas, primeiro chame [bcp_columns](bcp-columns.md)**(5)** e **bcp_setcolfmt** cinco vezes, sendo três dessas chamadas para definir o seu formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-196">For example, to change the default settings for three columns in a five-column user data file, first call [bcp_columns](bcp-columns.md)**(5)**, and then call **bcp_setcolfmt** five times, with three of those calls setting your custom format.</span></span> <span data-ttu-id="fe9e3-197">Para as duas chamadas restantes, defina BCP_FMT_TYPE como 0 e defina BCP_FMT_INDICATOR_LENGTH, BCP_FMT_DATA_LEN e *cbValue* como 0, SQL_VARLEN_DATA e 0, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-197">For the remaining two calls, set BCP_FMT_TYPE to 0, and set BCP_FMT_INDICATOR_LENGTH, BCP_FMT_DATA_LEN, and *cbValue* to 0, SQL_VARLEN_DATA, and 0 respectively.</span></span> <span data-ttu-id="fe9e3-198">Esse procedimento copia todas as cinco colunas, três com seu formato personalizado e duas com o formato padrão.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-198">This procedure copies all five columns, three with your customized format and two with the default format.</span></span>  
  
 <span data-ttu-id="fe9e3-199">A função **bcp_columns** deve ser chamada antes de chamar **bcp_setcolfmt**.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-199">The **bcp_columns** function must be called before calling **bcp_setcolfmt**.</span></span>  
  
 <span data-ttu-id="fe9e3-200">Você deve chamar **bcp_setcolfmt** uma vez para cada propriedade de cada coluna no arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-200">You must call **bcp_setcolfmt** once for each property of each column in the user file.</span></span>  
  
 <span data-ttu-id="fe9e3-201">Você não precisa copiar todos os dados em um arquivo de usuário para a tabela do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-201">You do not need to copy all data in a user file to the SQL Server table.</span></span> <span data-ttu-id="fe9e3-202">Para ignorar uma coluna, especifique o formato dos dados para a coluna, definindo o parâmetro BCP_FMT_SERVER_COL como 0.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-202">To skip a column, specify the format of the data for the column, setting the BCP_FMT_SERVER_COL parameter to 0.</span></span> <span data-ttu-id="fe9e3-203">Se desejar ignorar uma coluna, especifique seu tipo.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-203">If you want to skip a column, you must specify its type.</span></span>  
  
 <span data-ttu-id="fe9e3-204">A função [bcp_writefmt](bcp-writefmt.md) pode ser usada para persistir a especificação de formato.</span><span class="sxs-lookup"><span data-stu-id="fe9e3-204">The [bcp_writefmt](bcp-writefmt.md) function can be used to persist the format specification.</span></span>  
  
## <a name="bcp_setcolfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="fe9e3-205">Suporte do bcp_setcolfmt a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="fe9e3-205">bcp_setcolfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="fe9e3-206">Os tipos usados com a propriedade BCP_FMT_TYPE para tipos de data/hora são conforme especificado em [alterações de cópia em massa para tipos de data e hora aprimorados &#40;OLE DB e&#41;ODBC ](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="fe9e3-206">The types used with the BCP_FMT_TYPE property for date/time types are as specified in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="fe9e3-207">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="fe9e3-207">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe9e3-208">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fe9e3-208">See Also</span></span>  
 [<span data-ttu-id="fe9e3-209">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="fe9e3-209">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  