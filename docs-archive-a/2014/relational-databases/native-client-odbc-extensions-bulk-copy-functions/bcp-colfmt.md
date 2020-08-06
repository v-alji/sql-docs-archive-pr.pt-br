---
title: bcp_colfmt | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colfmt function
ms.assetid: 5c3b6299-80c7-4e84-8e69-4ff33009548e
author: rothja
ms.author: jroth
ms.openlocfilehash: f646f3aaf9a8f640d829020bd6762c07c406b61f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685654"
---
# <a name="bcp_colfmt"></a><span data-ttu-id="81272-102">bcp_colfmt</span><span class="sxs-lookup"><span data-stu-id="81272-102">bcp_colfmt</span></span>
  <span data-ttu-id="81272-103">Especifica o formato de origem ou de destino dos dados em um arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="81272-103">Specifies the source or target format of the data in a user file.</span></span> <span data-ttu-id="81272-104">Quando usado como formato de origem, **bcp_colfmt** especifica o formato de um arquivo de dados existente usado como a fonte de dados em uma cópia em massa para uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81272-104">When used as a source format, **bcp_colfmt** specifies the format of an existing data file used as the source of data in a bulk copy to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="81272-105">Quando usado como formato de destino, o arquivo de dados é criado usando os formatos de coluna especificados com **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="81272-105">When used as a target format, the data file is created using the column formats specified with **bcp_colfmt**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81272-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="81272-106">Syntax</span></span>  
  
```  
  
RETCODE bcp_colfmt (  
HDBC   
hdbc  
,  
INT  
idxUserDataCol  
,  
BYTE   
eUserDataType  
,  
INT   
cbIndicator  
,  
DBINT   
cbUserData  
,  
LPCBYTE   
pUserDataTerm  
,  
INT   
cbUserDataTerm  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="81272-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="81272-107">Arguments</span></span>  
 <span data-ttu-id="81272-108">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="81272-108">*hdbc*</span></span>  
 <span data-ttu-id="81272-109">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="81272-109">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="81272-110">*idxUserDataCol*</span><span class="sxs-lookup"><span data-stu-id="81272-110">*idxUserDataCol*</span></span>  
 <span data-ttu-id="81272-111">É o número de coluna ordinal no arquivo de dados de usuário para o qual o formato está sendo especificado.</span><span class="sxs-lookup"><span data-stu-id="81272-111">Is the ordinal column number in the user data file for which the format is being specified.</span></span> <span data-ttu-id="81272-112">A primeira coluna é 1.</span><span class="sxs-lookup"><span data-stu-id="81272-112">The first column is 1.</span></span>  
  
 <span data-ttu-id="81272-113">*eUserDataType*</span><span class="sxs-lookup"><span data-stu-id="81272-113">*eUserDataType*</span></span>  
 <span data-ttu-id="81272-114">É o tipo de dados desta coluna no arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="81272-114">Is the data type of this column in the user file.</span></span> <span data-ttu-id="81272-115">Se diferente do tipo de dados da coluna correspondente na tabela do banco de dados (*idxServerColumn*), a cópia em massa converterá os dados, caso seja possível.</span><span class="sxs-lookup"><span data-stu-id="81272-115">If different from the data type of the corresponding column in the database table (*idxServerColumn*), bulk copy converts the data if possible.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="81272-116">introduziu o suporte para os tokens de tipo de dados SQLXML e SQLUDT no parâmetro *eUserDataType* .</span><span class="sxs-lookup"><span data-stu-id="81272-116">introduced support for SQLXML and SQLUDT data type tokens in the *eUserDataType* parameter.</span></span>  
  
 <span data-ttu-id="81272-117">O parâmetro *eUserDataType* é enumerado pelos tokens de tipo de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em sqlncli.h e não pelos enumeradores de tipo de dados ODBC C.</span><span class="sxs-lookup"><span data-stu-id="81272-117">The *eUserDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="81272-118">Por exemplo, você pode especificar uma cadeia de caracteres, o tipo ODBC SQL_C_CHAR, usando o tipo SQLCHARACTER específico do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81272-118">For example, you can specify a character string, ODBC type SQL_C_CHAR, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLCHARACTER.</span></span>  
  
 <span data-ttu-id="81272-119">Para especificar a representação de dados padrão do tipo de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , defina esse parâmetro como 0.</span><span class="sxs-lookup"><span data-stu-id="81272-119">To specify the default data representation for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, set this parameter to 0.</span></span>  
  
 <span data-ttu-id="81272-120">Para uma cópia em massa fora do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um arquivo, quando *eUserDataType* for SQLDECIMAL ou SQLNUMERIC:</span><span class="sxs-lookup"><span data-stu-id="81272-120">For a bulk copy out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into a file, when *eUserDataType* is SQLDECIMAL or SQLNUMERIC:</span></span>  
  
-   <span data-ttu-id="81272-121">Se a coluna de origem não for **decimal** ou **numeric**, a precisão e a escala padrão serão usadas.</span><span class="sxs-lookup"><span data-stu-id="81272-121">If the source column is not **decimal** or **numeric**, the default precision and scale are used.</span></span>  
  
-   <span data-ttu-id="81272-122">Se a coluna de origem for **decimal** ou **numeric**, a precisão e a escala da coluna de origem serão usadas.</span><span class="sxs-lookup"><span data-stu-id="81272-122">If the source column is **decimal** or **numeric**, the precision and scale of the source column are used.</span></span>  
  
 <span data-ttu-id="81272-123">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="81272-123">*cbIndicator*</span></span>  
 <span data-ttu-id="81272-124">É o comprimento, em bytes, de um indicador de comprimento/nulo nos dados de coluna.</span><span class="sxs-lookup"><span data-stu-id="81272-124">Is the length, in bytes, of a length/null indicator within the column data.</span></span> <span data-ttu-id="81272-125">Os valores de comprimento de indicador válidos são 0 (quando nenhum indicador é usado), 1, 2, 4 ou 8.</span><span class="sxs-lookup"><span data-stu-id="81272-125">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span>  
  
 <span data-ttu-id="81272-126">Para especificar o uso do indicador de cópia em massa padrão, defina esse parâmetro como SQL_VARLEN_DATA.</span><span class="sxs-lookup"><span data-stu-id="81272-126">To specify default bulk copy indicator usage, set this parameter to SQL_VARLEN_DATA.</span></span>  
  
 <span data-ttu-id="81272-127">Os indicadores aparecem na memória diretamente antes de quaisquer dados, e no arquivo de dados diretamente antes dos dados aos quais se aplicam.</span><span class="sxs-lookup"><span data-stu-id="81272-127">Indicators appear in memory directly before any data, and in the data file directly before the data to which they apply.</span></span>  
  
 <span data-ttu-id="81272-128">Se for usada mais de uma maneira de especificar um comprimento de coluna de arquivo de dados (como um indicador e um comprimento de coluna máximo ou um indicador e uma sequência de terminador), a cópia em massa escolherá aquela que resultar na menor quantidade de dados sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="81272-128">If more than one means of specifying a data file column length is used (such as an indicator and a maximum column length, or an indicator and a terminator sequence), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="81272-129">Os arquivos de dados gerados pela cópia em massa quando nenhuma intervenção de usuário ajusta o formato dos dados contêm indicadores quando os dados de coluna podem variar em comprimento ou a coluna pode aceitar NULL como valor.</span><span class="sxs-lookup"><span data-stu-id="81272-129">Data files generated by bulk copy when no user intervention adjusts the format of the data contain indicators when the column data can vary in length or the column can accept NULL as a value.</span></span>  
  
 <span data-ttu-id="81272-130">*cbUserData*</span><span class="sxs-lookup"><span data-stu-id="81272-130">*cbUserData*</span></span>  
 <span data-ttu-id="81272-131">É o comprimento máximo, em bytes, dos dados dessa coluna no arquivo de usuário, sem incluir o comprimento de qualquer indicador de comprimento ou terminador.</span><span class="sxs-lookup"><span data-stu-id="81272-131">Is the maximum length, in bytes, of this column's data in the user file, not including the length of any length indicator or terminator.</span></span>  
  
 <span data-ttu-id="81272-132">A definição de *cbUserData* como SQL_NULL_DATA indica que todos os valores na coluna de arquivo de dados são ou deveriam ser definidos como NULL.</span><span class="sxs-lookup"><span data-stu-id="81272-132">Setting *cbUserData* to SQL_NULL_DATA indicates that all values in the data file column are, or should be set to NULL.</span></span>  
  
 <span data-ttu-id="81272-133">A definição de *cbUserData* como SQL_VARLEN_DATA indica que o sistema deve determinar o comprimento dos dados em cada coluna.</span><span class="sxs-lookup"><span data-stu-id="81272-133">Setting *cbUserData* to SQL_VARLEN_DATA indicates that the system should determine the length of data in each column.</span></span> <span data-ttu-id="81272-134">Para algumas colunas, isso poderia significar que um indicador de comprimento/nulo é gerado para anteceder os dados em uma cópia do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ou que o indicador é esperado nos dados copiados para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81272-134">For some columns, this could mean that a length/null indicator is generated to precede data on a copy from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or that the indicator is expected in data copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="81272-135">Para os tipos de dados binary e character do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , *cbUserData* pode ser SQL_VARLEN_DATA, SQL_NULL_DATA, 0 ou algum valor positivo.</span><span class="sxs-lookup"><span data-stu-id="81272-135">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbUserData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, 0, or some positive value.</span></span> <span data-ttu-id="81272-136">Se *cbUserData* for SQL_VARLEN_DATA, o sistema usará o indicador de comprimento, se houver, ou uma sequência de terminador para determinar o comprimento dos dados.</span><span class="sxs-lookup"><span data-stu-id="81272-136">If *cbUserData* is SQL_VARLEN_DATA, the system uses either the length indicator, if present, or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="81272-137">Se forem fornecidos um indicador de comprimento e uma sequência de terminador, a cópia em massa usará aquele que resultar na menor quantidade de dados sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="81272-137">If both a length indicator and a terminator sequence are supplied, bulk copy uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="81272-138">Se *cbUserData* for SQL_VARLEN_DATA, o tipo de dados for um tipo binary ou character do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e nem um indicador de comprimento nem uma sequência de terminador forem especificados, o sistema retornará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="81272-138">If *cbUserData* is SQL_VARLEN_DATA, the data type is an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="81272-139">Se *cbUserData* for 0 ou um valor positivo, o sistema usará *cbUserData* como o comprimento de dados máximo.</span><span class="sxs-lookup"><span data-stu-id="81272-139">If *cbUserData* is 0 or a positive value, the system uses *cbUserData* as the maximum data length.</span></span> <span data-ttu-id="81272-140">Entretanto, se, além de um *cbUserData*positivo, for fornecido um indicador de comprimento ou uma sequência de terminador, o sistema determinará o comprimento dos dados usando o método que resulta na menor quantidade de dados sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="81272-140">However, if, in addition to a positive *cbUserData*, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="81272-141">O valor *cbUserData* representa a contagem de bytes dos dados.</span><span class="sxs-lookup"><span data-stu-id="81272-141">The *cbUserData* value represents the count of bytes of data.</span></span> <span data-ttu-id="81272-142">Se dados de caracteres forem representados por caracteres que abrangem Unicode, um valor de parâmetro *cbUserData* positivo representará o número de caracteres multiplicado pelo tamanho, em bytes, de cada caractere.</span><span class="sxs-lookup"><span data-stu-id="81272-142">If character data is represented by Unicode wide characters, then a positive *cbUserData* parameter value represents the number of characters multiplied by the size, in bytes, of each character.</span></span>  
  
 <span data-ttu-id="81272-143">*pUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="81272-143">*pUserDataTerm*</span></span>  
 <span data-ttu-id="81272-144">É a sequência de terminador a ser usada para esta coluna.</span><span class="sxs-lookup"><span data-stu-id="81272-144">Is the terminator sequence to be used for this column.</span></span> <span data-ttu-id="81272-145">Este parâmetro é útil principalmente para tipos de dados character porque todos os outros tipos têm comprimento fixo ou, no caso de dados binary, exigem um indicador de comprimento que permite registrar com precisão o número de bytes presentes.</span><span class="sxs-lookup"><span data-stu-id="81272-145">This parameter is useful mainly for character data types because all other types are of fixed length or, in the case of binary data, require an indicator of length to accurately record the number of bytes present.</span></span>  
  
 <span data-ttu-id="81272-146">Para evitar encerrar os dados extraídos ou indicar que os dados em um arquivo de usuário não foram encerrados, defina este parâmetro como NULL.</span><span class="sxs-lookup"><span data-stu-id="81272-146">To avoid terminating extracted data, or to indicate that data in a user file is not terminated, set this parameter to NULL.</span></span>  
  
 <span data-ttu-id="81272-147">Se for usada mais de uma maneira de especificar um comprimento de coluna de arquivo de usuário (como um terminador e um indicador de comprimento ou um terminador e um comprimento de coluna máximo), a cópia em massa escolherá aquela que resultar na menor quantidade de dados sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="81272-147">If more than one means of specifying a user-file column length is used (such as a terminator and a length indicator, or a terminator and a maximum column length), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="81272-148">A API de cópia em massa executa a conversão de caracteres Unicode em MBCS conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="81272-148">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="81272-149">É necessário tomar cuidado para garantir que tanto a cadeia de caracteres de bytes do terminador quanto o comprimento da cadeia de caracteres de bytes estejam definidos corretamente.</span><span class="sxs-lookup"><span data-stu-id="81272-149">Care must be taken to ensure that both the terminator byte string and the length of the byte string are set correctly.</span></span>  
  
 <span data-ttu-id="81272-150">*cbUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="81272-150">*cbUserDataTerm*</span></span>  
 <span data-ttu-id="81272-151">É o comprimento, em bytes, da sequência de terminador a ser usada para esta coluna.</span><span class="sxs-lookup"><span data-stu-id="81272-151">Is the length, in bytes, of the terminator sequence to be used for this column.</span></span> <span data-ttu-id="81272-152">Se nenhum terminador estiver presente ou for desejado nos dados, defina esse valor como 0.</span><span class="sxs-lookup"><span data-stu-id="81272-152">If no terminator is present or desired in the data, set this value to 0.</span></span>  
  
 <span data-ttu-id="81272-153">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="81272-153">*idxServerCol*</span></span>  
 <span data-ttu-id="81272-154">É a posição ordinal da coluna na tabela do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="81272-154">Is the ordinal position of the column in the database table.</span></span> <span data-ttu-id="81272-155">O número da primeira coluna é 1.</span><span class="sxs-lookup"><span data-stu-id="81272-155">The first column number is 1.</span></span> <span data-ttu-id="81272-156">A posição ordinal de uma coluna é relatada por [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="81272-156">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
 <span data-ttu-id="81272-157">Se esse valor for 0, a cópia em massa irá ignorar a coluna no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="81272-157">If this value is 0, bulk copy ignores the column in the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="81272-158">Retornos</span><span class="sxs-lookup"><span data-stu-id="81272-158">Returns</span></span>  
 <span data-ttu-id="81272-159">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="81272-159">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81272-160">Comentários</span><span class="sxs-lookup"><span data-stu-id="81272-160">Remarks</span></span>  
 <span data-ttu-id="81272-161">A função **bcp_colfmt** permite especificar o formato do arquivo de usuário para cópias em massa.</span><span class="sxs-lookup"><span data-stu-id="81272-161">The **bcp_colfmt** function allows you to specify the user-file format for bulk copies.</span></span> <span data-ttu-id="81272-162">Para cópia em massa, um formato contém as seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="81272-162">For bulk copy, a format contains the following parts:</span></span>  
  
-   <span data-ttu-id="81272-163">Um mapeamento de colunas do arquivo de usuário para colunas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="81272-163">A mapping from user-file columns to database columns.</span></span>  
  
-   <span data-ttu-id="81272-164">O tipo de dados de cada coluna do arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="81272-164">The data type of each user-file column.</span></span>  
  
-   <span data-ttu-id="81272-165">O comprimento do indicador opcional para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="81272-165">The length of the optional indicator for each column.</span></span>  
  
-   <span data-ttu-id="81272-166">O comprimento máximo dos dados por coluna do arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="81272-166">The maximum length of data per user-file column.</span></span>  
  
-   <span data-ttu-id="81272-167">A sequência de bytes de encerramento opcional para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="81272-167">The optional terminating byte sequence for each column.</span></span>  
  
-   <span data-ttu-id="81272-168">O comprimento da sequência de bytes de encerramento opcional.</span><span class="sxs-lookup"><span data-stu-id="81272-168">The length of the optional terminating byte sequence.</span></span>  
  
 <span data-ttu-id="81272-169">Cada chamada de **bcp_colfmt** especifica o formato de uma coluna do arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="81272-169">Each call to **bcp_colfmt** specifies the format for one user-file column.</span></span> <span data-ttu-id="81272-170">Por exemplo, para alterar as configurações padrão de três colunas em um arquivo de dados de usuário de cinco colunas, primeiro chame [bcp_columns](bcp-columns.md)**(5)** e, em seguida, chame **bcp_colfmt** cinco vezes, sendo três dessas chamadas para definir seu formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="81272-170">For example, to change the default settings for three columns in a five-column user data file, first call [bcp_columns](bcp-columns.md)**(5)**, and then call **bcp_colfmt** five times, with three of those calls setting your custom format.</span></span> <span data-ttu-id="81272-171">Para as duas chamadas restantes, defina *eUserDataType* como 0 e defina *cbIndicator*, *cbUserData*e *cbUserDataTerm* respectivamente como 0, SQL_VARLEN_DATA e 0.</span><span class="sxs-lookup"><span data-stu-id="81272-171">For the remaining two calls, set *eUserDataType* to 0, and set *cbIndicator*, *cbUserData*, and *cbUserDataTerm* to 0, SQL_VARLEN_DATA, and 0 respectively.</span></span> <span data-ttu-id="81272-172">Esse procedimento copia todas as cinco colunas, três com seu formato personalizado e duas com o formato padrão.</span><span class="sxs-lookup"><span data-stu-id="81272-172">This procedure copies all five columns, three with your customized format and two with the default format.</span></span>  
  
 <span data-ttu-id="81272-173">Para *cbIndicator*, um valor 8 indica que agora um tipo de valor grande é válido.</span><span class="sxs-lookup"><span data-stu-id="81272-173">For *cbIndicator*, a value of 8 to indicate a large value type is now valid.</span></span> <span data-ttu-id="81272-174">Se o prefixo for especificado para um campo cuja coluna correspondente é um novo tipo max, ele poderá ser definido somente como 8.</span><span class="sxs-lookup"><span data-stu-id="81272-174">If the prefix is specified for a field whose corresponding column is a new max type, it can only be set to 8.</span></span> <span data-ttu-id="81272-175">Para obter detalhes, consulte [bcp_bind](bcp-bind.md).</span><span class="sxs-lookup"><span data-stu-id="81272-175">For details, see [bcp_bind](bcp-bind.md).</span></span>  
  
 <span data-ttu-id="81272-176">A função **bcp_columns** deve ser chamada antes de qualquer chamada de **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="81272-176">The **bcp_columns** function must be called before any calls to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="81272-177">Chame **bcp_colfmt** uma vez para cada coluna no arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="81272-177">You must call **bcp_colfmt** once for each column in the user file.</span></span>  
  
 <span data-ttu-id="81272-178">Chamar **bcp_colfmt** mais de uma vez para qualquer coluna do arquivo de usuário gera um erro.</span><span class="sxs-lookup"><span data-stu-id="81272-178">Calling **bcp_colfmt** more than once for any user-file column causes an error.</span></span>  
  
 <span data-ttu-id="81272-179">Você não precisa copiar todos os dados de um arquivo de usuário para a tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81272-179">You do not need to copy all data in a user file to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="81272-180">Para ignorar uma coluna, especifique o formato dos dados para a coluna, definindo o parâmetro *idxServerCol* como 0.</span><span class="sxs-lookup"><span data-stu-id="81272-180">To skip a column, specify the format of the data for the column, setting the *idxServerCol* parameter to 0.</span></span> <span data-ttu-id="81272-181">Se desejar ignorar uma coluna, especifique seu tipo.</span><span class="sxs-lookup"><span data-stu-id="81272-181">If you want to skip a column, you must specify its type.</span></span>  
  
 <span data-ttu-id="81272-182">A função [bcp_writefmt](bcp-writefmt.md) pode ser usada para persistir a especificação de formato.</span><span class="sxs-lookup"><span data-stu-id="81272-182">The [bcp_writefmt](bcp-writefmt.md) function can be used to persist the format specification.</span></span>  
  
## <a name="bcp_colfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="81272-183">Suporte do bcp_colfmt a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="81272-183">bcp_colfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="81272-184">Para obter informações sobre os tipos usados com o parâmetro *eUserDataType* para tipos de data/hora, consulte [alterações de cópia em massa para tipos de data e hora aprimorados &#40;OLE DB e ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="81272-184">For information aboutt he types used with the *eUserDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="81272-185">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="81272-185">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81272-186">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81272-186">See Also</span></span>  
 [<span data-ttu-id="81272-187">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="81272-187">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
