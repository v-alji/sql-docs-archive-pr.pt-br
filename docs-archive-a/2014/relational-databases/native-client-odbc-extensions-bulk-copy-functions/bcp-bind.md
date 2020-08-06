---
title: bcp_bind | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_bind
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_bind function
ms.assetid: 6e335a5c-64b2-4bcf-a88f-35dc9393f329
author: rothja
ms.author: jroth
ms.openlocfilehash: db0a58398bf47bd0bb96bd1ef587d41890ed8461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679942"
---
# <a name="bcp_bind"></a><span data-ttu-id="55ec9-102">bcp_bind</span><span class="sxs-lookup"><span data-stu-id="55ec9-102">bcp_bind</span></span>
  <span data-ttu-id="55ec9-103">Associa dados de uma variável de programa a uma coluna de tabela para cópia em massa no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55ec9-103">Binds data from a program variable to a table column for bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ec9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="55ec9-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_bind (  
HDBC   
hdbc  
,   
LPCBYTE   
pData  
,  
INT   
cbIndicator  
,  
DBINT   
cbData  
,  
LPCBYTE   
pTerm  
,  
INT   
cbTerm  
,  
INT   
eDataType  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="55ec9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="55ec9-105">Arguments</span></span>  
 <span data-ttu-id="55ec9-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="55ec9-106">*hdbc*</span></span>  
 <span data-ttu-id="55ec9-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="55ec9-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="55ec9-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="55ec9-108">*pData*</span></span>  
 <span data-ttu-id="55ec9-109">É um ponteiro para os dados copiados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-109">Is a pointer to the data copied.</span></span> <span data-ttu-id="55ec9-110">Se *eDataType* for o SQLTEXT, o SQLNTEXT, o SQLXML, o SQLUDT, o SQLCHARACTER, o SQLVARCHAR, o SQLVARBINARY, o SqlBinary, o SQLNCHAR ou o SQLIMAGE, *pData* poderá ser nulo.</span><span class="sxs-lookup"><span data-stu-id="55ec9-110">If *eDataType* is SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR or SQLIMAGE, *pData* can be NULL.</span></span> <span data-ttu-id="55ec9-111">Um *pData* nulo indica que valores de dados longos serão enviados para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em partes usando [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="55ec9-111">A NULL *pData* indicates that long data values will be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in chunks using [bcp_moretext](bcp-moretext.md).</span></span> <span data-ttu-id="55ec9-112">O usuário só deve definir *pData* como nulo se a coluna correspondente ao campo associado ao usuário for uma coluna BLOB, caso contrário **bcp_bind** falhará.</span><span class="sxs-lookup"><span data-stu-id="55ec9-112">The user should only set *pData* to NULL if the column corresponding to the user bound field is a BLOB column otherwise **bcp_bind** will fail.</span></span>  
  
 <span data-ttu-id="55ec9-113">Se houve indicadores presentes nos dados, eles aparecerão na memória diretamente antes dos dados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-113">If indicators are present in the data, they appear in memory directly before the data.</span></span> <span data-ttu-id="55ec9-114">O parâmetro *pData* aponta para a variável de indicador nesse caso, e a largura do indicador, o parâmetro *cbIndicator* , é usada pela cópia em massa para resolver os dados do usuário corretamente.</span><span class="sxs-lookup"><span data-stu-id="55ec9-114">The *pData* parameter points to the indicator variable in this case, and the width of the indicator, the *cbIndicator* parameter, is used by bulk copy to address user data correctly.</span></span>  
  
 <span data-ttu-id="55ec9-115">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="55ec9-115">*cbIndicator*</span></span>  
 <span data-ttu-id="55ec9-116">É o comprimento, em bytes, de um indicador de comprimento ou nulo para os dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="55ec9-116">Is the length, in bytes, of a length or null indicator for the column's data.</span></span> <span data-ttu-id="55ec9-117">Os valores de comprimento de indicador válidos são 0 (quando nenhum indicador é usado), 1, 2, 4 ou 8.</span><span class="sxs-lookup"><span data-stu-id="55ec9-117">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span> <span data-ttu-id="55ec9-118">Os indicadores aparecem na memória diretamente antes de qualquer dado.</span><span class="sxs-lookup"><span data-stu-id="55ec9-118">Indicators appear in memory directly before any data.</span></span> <span data-ttu-id="55ec9-119">Por exemplo, a definição do tipo de estrutura a seguir poderia ser usada para inserir valores inteiros em uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando a cópia em massa:</span><span class="sxs-lookup"><span data-stu-id="55ec9-119">For example, the following structure type definition could be used to insert integer values into an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table using bulk copy:</span></span>  
  
```  
typedef struct tagBCPBOUNDINT  
    {  
    int iIndicator;  
    int Value;  
    } BCPBOUNDINT;  
```  
  
 <span data-ttu-id="55ec9-120">No caso de exemplo, o parâmetro *pData* seria definido como o endereço de uma instância declarada da estrutura, o endereço do membro da estrutura BCPBOUNDINT *iIndicator* .</span><span class="sxs-lookup"><span data-stu-id="55ec9-120">In the example case, the *pData* parameter would be set to the address of a declared instance of the structure, the address of the BCPBOUNDINT *iIndicator* structure member.</span></span> <span data-ttu-id="55ec9-121">O parâmetro *cbIndicator* seria definido como o tamanho de um inteiro (sizeof (int)) e o parâmetro *cbData* seria definido novamente como o tamanho de um inteiro (sizeof (int)).</span><span class="sxs-lookup"><span data-stu-id="55ec9-121">The *cbIndicator* parameter would be set to the size of an integer (sizeof(int)), and the *cbData* parameter would again be set to the size of an integer (sizeof(int)).</span></span> <span data-ttu-id="55ec9-122">Para copiar em massa uma linha para o servidor que contém um valor nulo para a coluna associada, o valor do membro *iIndicator* da instância deve ser definido como SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="55ec9-122">To bulk copy a row to the server containing a NULL value for the bound column, the value of the instance's *iIndicator* member should be set to SQL_NULL_DATA.</span></span>  
  
 <span data-ttu-id="55ec9-123">*cbData*</span><span class="sxs-lookup"><span data-stu-id="55ec9-123">*cbData*</span></span>  
 <span data-ttu-id="55ec9-124">É a contagem de bytes de dados na variável de programa, não incluindo o comprimento de qualquer terminador ou indicador de comprimento ou nulo.</span><span class="sxs-lookup"><span data-stu-id="55ec9-124">Is the count of bytes of data in the program variable, not including the length of any length or null indicator or terminator.</span></span>  
  
 <span data-ttu-id="55ec9-125">Definir *cbData* como SQL_NULL_DATA significa que todas as linhas copiadas para o servidor contêm um valor nulo para a coluna.</span><span class="sxs-lookup"><span data-stu-id="55ec9-125">Setting *cbData* to SQL_NULL_DATA signifies that all rows copied to the server contain a NULL value for the column.</span></span>  
  
 <span data-ttu-id="55ec9-126">Definir *cbData* como SQL_VARLEN_DATA indica que o sistema usará um terminador de cadeia de caracteres ou outro método para determinar o comprimento dos dados copiados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-126">Setting *cbData* to SQL_VARLEN_DATA indicates that the system will use a string terminator, or other method, to determine the length of data copied.</span></span>  
  
 <span data-ttu-id="55ec9-127">Para tipos de dados de comprimento fixo, como inteiros, o tipo de dados indica o comprimento dos dados para o sistema.</span><span class="sxs-lookup"><span data-stu-id="55ec9-127">For fixed-length data types, such as integers, the data type indicates the length of the data to the system.</span></span> <span data-ttu-id="55ec9-128">Portanto, para tipos de dados de comprimento fixo, *cbData* pode ser SQL_VARLEN_DATA com segurança ou o comprimento dos dados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-128">Therefore, for fixed-length data types, *cbData* can safely be SQL_VARLEN_DATA or the length of the data.</span></span>  
  
 <span data-ttu-id="55ec9-129">Para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados Binary e de caractere, *cbData* pode ser SQL_VARLEN_DATA, SQL_NULL_DATA, algum valor positivo ou 0.</span><span class="sxs-lookup"><span data-stu-id="55ec9-129">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, some positive value, or 0.</span></span> <span data-ttu-id="55ec9-130">Se *cbData* for SQL_VARLEN_DATA, o sistema usará um indicador de comprimento/nulo (se presente) ou uma sequência de terminador para determinar o comprimento dos dados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-130">If *cbData* is SQL_VARLEN_DATA, the system uses either a length/null indicator (if present) or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="55ec9-131">Se os dois forem fornecidos, o sistema irá usar aquele que resulta na menos quantidade de dados sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-131">If both are supplied, the system uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="55ec9-132">Se *cbData* for SQL_VARLEN_DATA, o tipo de dados da coluna será um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo de caractere ou binário e nem um indicador de comprimento nem uma sequência de terminador será especificado, o sistema retornará uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="55ec9-132">If *cbData* is SQL_VARLEN_DATA, the data type of the column is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="55ec9-133">Se *cbData* for 0 ou um valor positivo, o sistema usará *cbData* como o comprimento dos dados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-133">If *cbData* is 0 or a positive value, the system uses *cbData* as the data length.</span></span> <span data-ttu-id="55ec9-134">No entanto, se, além de um valor positivo de *cbData* , um indicador de comprimento ou uma sequência de terminador for fornecida, o sistema determinará o comprimento dos dados usando o método que resultará na menor quantidade de dados sendo copiados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-134">However, if, in addition to a positive *cbData* value, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="55ec9-135">O valor do parâmetro *cbData* representa a contagem de bytes de dados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-135">The *cbData* parameter value represents the count of bytes of data.</span></span> <span data-ttu-id="55ec9-136">Se os dados de caractere forem representados por caracteres largos Unicode, um valor de parâmetro *cbData* positivo representará o número de caracteres multiplicado pelo tamanho em bytes de cada caractere.</span><span class="sxs-lookup"><span data-stu-id="55ec9-136">If character data is represented by Unicode wide characters, then a positive *cbData* parameter value represents the number of characters multiplied by the size in bytes of each character.</span></span>  
  
 <span data-ttu-id="55ec9-137">*pTerm*</span><span class="sxs-lookup"><span data-stu-id="55ec9-137">*pTerm*</span></span>  
 <span data-ttu-id="55ec9-138">É um ponteiro para o padrão de bytes, se houver, que marca o fim desta variável de programa.</span><span class="sxs-lookup"><span data-stu-id="55ec9-138">Is a pointer to the byte pattern, if any, that marks the end of this program variable.</span></span> <span data-ttu-id="55ec9-139">Por exemplo, geralmente, as cadeias de caracteres C ANSI e MBCS têm um terminador com 1 byte (\0).</span><span class="sxs-lookup"><span data-stu-id="55ec9-139">For example, ANSI and MBCS C strings usually have a 1-byte terminator (\0).</span></span>  
  
 <span data-ttu-id="55ec9-140">Se não houver um terminador para a variável, defina *pTerm* como NULL.</span><span class="sxs-lookup"><span data-stu-id="55ec9-140">If there is no terminator for the variable, set *pTerm* to NULL.</span></span>  
  
 <span data-ttu-id="55ec9-141">Você pode usar uma cadeia de caracteres vazia ("") para designar o terminador nulo C como o terminador de variável do programa.</span><span class="sxs-lookup"><span data-stu-id="55ec9-141">You can use an empty string ("") to designate the C null terminator as the program-variable terminator.</span></span> <span data-ttu-id="55ec9-142">Como a cadeia de caracteres vazia terminada em nulo constitui um único byte (o próprio byte do terminador), defina *cbTerm* como 1.</span><span class="sxs-lookup"><span data-stu-id="55ec9-142">Because the null-terminated empty string constitutes a single byte (the terminator byte itself), set *cbTerm* to 1.</span></span> <span data-ttu-id="55ec9-143">Por exemplo, para indicar que a cadeia de caracteres em *szName* é terminada em nulo e que o terminador deve ser usado para indicar o comprimento:</span><span class="sxs-lookup"><span data-stu-id="55ec9-143">For example, to indicate that the string in *szName* is null-terminated and that the terminator should be used to indicate the length:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,  
   SQL_VARLEN_DATA, "", 1,  
   SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="55ec9-144">Um formulário não finalizado deste exemplo pode indicar que 15 caracteres sejam copiados da variável *szName* para a segunda coluna da tabela vinculada:</span><span class="sxs-lookup"><span data-stu-id="55ec9-144">A nonterminated form of this example could indicate that 15 characters be copied from the *szName* variable to the second column of the bound table:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0, 15,   
   NULL, 0, SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="55ec9-145">A API de cópia em massa executa a conversão de caracteres Unicode em MBCS conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="55ec9-145">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="55ec9-146">Verifique se a cadeia de caracteres de bytes de terminador e o comprimento da cadeia de caracteres de bytes estão definidos corretamente.</span><span class="sxs-lookup"><span data-stu-id="55ec9-146">Make sure that both the terminator byte string and the length of the byte string are set correctly.</span></span> <span data-ttu-id="55ec9-147">Por exemplo, para indicar que a cadeia de caracteres em *szName* é uma cadeia de caracteres Unicode largo, terminada pelo valor de terminador NULL Unicode:</span><span class="sxs-lookup"><span data-stu-id="55ec9-147">For example, to indicate that the string in *szName* is a Unicode wide character string, terminated by the Unicode null terminator value:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,   
   SQL_VARLEN_DATA, L"",  
   sizeof(WCHAR), SQLNCHAR, 2)  
```  
  
 <span data-ttu-id="55ec9-148">Se a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] coluna associada for um caractere largo, nenhuma conversão será executada em [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="55ec9-148">If the bound [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is wide character, no conversion is performed on [bcp_sendrow](bcp-sendrow.md).</span></span> <span data-ttu-id="55ec9-149">Se a coluna do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for do tipo caractere do MBCS, a conversão de caracteres largo em caracteres multibyte será executada conforme os dados são enviados para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55ec9-149">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is an MBCS character type, wide character to multibyte character conversion is performed as the data is sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="55ec9-150">*cbTerm*</span><span class="sxs-lookup"><span data-stu-id="55ec9-150">*cbTerm*</span></span>  
 <span data-ttu-id="55ec9-151">É a contagem de bytes presentes no terminador da variável de programa, se houver.</span><span class="sxs-lookup"><span data-stu-id="55ec9-151">Is the count of bytes present in the terminator for the program variable, if any.</span></span> <span data-ttu-id="55ec9-152">Se não houver um terminador para a variável, defina *cbTerm* como 0.</span><span class="sxs-lookup"><span data-stu-id="55ec9-152">If there is no terminator for the variable, set *cbTerm* to 0.</span></span>  
  
 <span data-ttu-id="55ec9-153">*eDataType*</span><span class="sxs-lookup"><span data-stu-id="55ec9-153">*eDataType*</span></span>  
 <span data-ttu-id="55ec9-154">É o tipo de dados C da variável de programa.</span><span class="sxs-lookup"><span data-stu-id="55ec9-154">Is the C data type of the program variable.</span></span> <span data-ttu-id="55ec9-155">Os dados na variável de programa são convertidos para o tipo da coluna do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-155">The data in the program variable is converted to the type of the database column.</span></span> <span data-ttu-id="55ec9-156">Se esse parâmetro for 0, nenhuma conversão será executada.</span><span class="sxs-lookup"><span data-stu-id="55ec9-156">If this parameter is 0, no conversion is performed.</span></span>  
  
 <span data-ttu-id="55ec9-157">O parâmetro *eDataType* é enumerado pelos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tokens de tipo de dados em sqlncli. h, não os enumeradores de tipo de dados ODBC C.</span><span class="sxs-lookup"><span data-stu-id="55ec9-157">The *eDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="55ec9-158">Por exemplo, você pode especificar um inteiro de dois bytes, ODBC tipo SQL_C_SHORT, usando o tipo SQLINT2 específico do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55ec9-158">For example, you can specify a two-byte integer, ODBC type SQL_C_SHORT, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLINT2.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="55ec9-159">introduziu o suporte para os tokens de tipo de dados SQLXML e SQLUDT no parâmetro *`eDataType`* .</span><span class="sxs-lookup"><span data-stu-id="55ec9-159">introduced support for SQLXML and SQLUDT data type tokens in the *`eDataType`* paramenter.</span></span>  
  
 <span data-ttu-id="55ec9-160">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="55ec9-160">*idxServerCol*</span></span>  
 <span data-ttu-id="55ec9-161">É a posição ordinal da coluna na tabela do banco de dados na qual os dados são copiados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-161">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="55ec9-162">A primeira coluna em uma tabela é a coluna 1.</span><span class="sxs-lookup"><span data-stu-id="55ec9-162">The first column in a table is column 1.</span></span> <span data-ttu-id="55ec9-163">A posição ordinal de uma coluna é relatada por [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="55ec9-163">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="55ec9-164">Retornos</span><span class="sxs-lookup"><span data-stu-id="55ec9-164">Returns</span></span>  
 <span data-ttu-id="55ec9-165">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="55ec9-165">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55ec9-166">Comentários</span><span class="sxs-lookup"><span data-stu-id="55ec9-166">Remarks</span></span>  
 <span data-ttu-id="55ec9-167">Use **bcp_bind** para uma maneira rápida e eficiente de copiar dados de uma variável de programa para uma tabela no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55ec9-167">Use **bcp_bind** for a fast, efficient way to copy data from a program variable into a table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="55ec9-168">Chame [bcp_init](bcp-init.md) antes de chamar esta ou qualquer outra função de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="55ec9-168">Call [bcp_init](bcp-init.md) before calling this or any other bulk-copy function.</span></span> <span data-ttu-id="55ec9-169">Chamar **bcp_init** define a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela de destino para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="55ec9-169">Calling **bcp_init** sets the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] target table for bulk copy.</span></span> <span data-ttu-id="55ec9-170">Ao chamar **bcp_init** para uso com **bcp_bind** e [bcp_sendrow](bcp-sendrow.md), o parâmetro **bcp_init** _szDataFile_ , que indica o arquivo de dados, é definido como nulo; o parâmetro **bcp_init**_eDirection_ é definido como DB_IN.</span><span class="sxs-lookup"><span data-stu-id="55ec9-170">When calling **bcp_init** for use with **bcp_bind** and [bcp_sendrow](bcp-sendrow.md), the **bcp_init** _szDataFile_ parameter, indicating the data file, is set to NULL; the **bcp_init**_eDirection_ parameter is set to DB_IN.</span></span>  
  
 <span data-ttu-id="55ec9-171">Faça uma chamada de **bcp_bind** separada para cada coluna na [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela na qual você deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="55ec9-171">Make a separate **bcp_bind** call for every column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into which you want to copy.</span></span> <span data-ttu-id="55ec9-172">Depois que as chamadas de **bcp_bind** necessárias tiverem sido feitas, chame **bcp_sendrow** para enviar uma linha de dados de suas variáveis de programa para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55ec9-172">After the necessary **bcp_bind** calls have been made, then call **bcp_sendrow** to send a row of data from your program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="55ec9-173">Reassociar uma coluna não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="55ec9-173">Rebinding a column is not supported.</span></span>  
  
 <span data-ttu-id="55ec9-174">Sempre que você quiser [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] confirmar as linhas já recebidas, chame [bcp_batch](bcp-batch.md).</span><span class="sxs-lookup"><span data-stu-id="55ec9-174">Whenever you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to commit the rows already received, call [bcp_batch](bcp-batch.md).</span></span> <span data-ttu-id="55ec9-175">Por exemplo, chame **bcp_batch** uma vez para cada 1000 linhas inseridas ou em qualquer outro intervalo.</span><span class="sxs-lookup"><span data-stu-id="55ec9-175">For example, call **bcp_batch** once for every 1000 rows inserted or at any other interval.</span></span>  
  
 <span data-ttu-id="55ec9-176">Quando não houver mais linhas a serem inseridas, chame [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="55ec9-176">When there are no more rows to be inserted, call [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="55ec9-177">Caso isso não seja feito, será gerado um erro.</span><span class="sxs-lookup"><span data-stu-id="55ec9-177">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="55ec9-178">As configurações de parâmetro de controle, especificadas com [bcp_control](bcp-control.md), não têm efeito sobre transferências de linha **bcp_bind** .</span><span class="sxs-lookup"><span data-stu-id="55ec9-178">Control parameter settings, specified with [bcp_control](bcp-control.md), have no effect on **bcp_bind** row transfers.</span></span>  
  
 <span data-ttu-id="55ec9-179">Se *pData* para uma coluna for definido como NULL porque seu valor será fornecido por chamadas para [bcp_moretext](bcp-moretext.md), qualquer coluna subsequente com *eDataType* definida como SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary, SQLNCHAR ou SQLIMAGE também deverá ser associada a *pData* definido como NULL e seus valores também deverão ser fornecidos por chamadas para `bcp_moretext` .</span><span class="sxs-lookup"><span data-stu-id="55ec9-179">If *pData* for a column is set to NULL because its value will be supplied by calls to [bcp_moretext](bcp-moretext.md), any subsequent columns with *eDataType* set to SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR, or SQLIMAGE must also be bound with *pData* set to NULL, and their values must also be supplied by calls to `bcp_moretext`.</span></span>  
  
 <span data-ttu-id="55ec9-180">Para novos tipos de valor grande, como `varchar(max)` , `varbinary(max)` ou `nvarchar(max)` , você pode usar sqldigit, SQLVARCHAR, SQLVARBINARY, SqlBinary e SQLNCHAR como indicadores de tipo no parâmetro *eDataType* .</span><span class="sxs-lookup"><span data-stu-id="55ec9-180">For new large value types, such as `varchar(max)`, `varbinary(max)`, or `nvarchar(max)`, you can use SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, and SQLNCHAR as type indicators in the *eDataType* parameter.</span></span>  
  
 <span data-ttu-id="55ec9-181">Se *cbTerm* não for 0, qualquer valor (1, 2, 4 ou 8) será válido para o prefixo (*cbIndicator*).</span><span class="sxs-lookup"><span data-stu-id="55ec9-181">If *cbTerm* is not 0, any value (1, 2, 4, or 8) is valid for the prefix (*cbIndicator*).</span></span> <span data-ttu-id="55ec9-182">Nessa situação, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client pesquisará o terminador, calculará o comprimento dos dados em relação ao terminador (*i*) e definirá *cbData* como o valor menor de i e o valor do prefixo.</span><span class="sxs-lookup"><span data-stu-id="55ec9-182">In this situation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will search for the terminator, calculate data length with respect to the terminator (*i*), and set the *cbData* to the smaller value of i and the value of prefix.</span></span>  
  
 <span data-ttu-id="55ec9-183">Se *cbTerm* for 0 e *cbIndicator* (o prefixo) não for 0, *cbIndicator* deverá ser 8.</span><span class="sxs-lookup"><span data-stu-id="55ec9-183">If *cbTerm* is 0 and *cbIndicator* (the prefix) is not 0, *cbIndicator* must be 8.</span></span> <span data-ttu-id="55ec9-184">O prefixo de 8 bytes pode ter os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="55ec9-184">The 8 byte prefix can take the following values:</span></span>  
  
-   <span data-ttu-id="55ec9-185">0xFFFFFFFFFFFFFFFF significa um valor nulo para o campo</span><span class="sxs-lookup"><span data-stu-id="55ec9-185">0xFFFFFFFFFFFFFFFF means a null value for the field</span></span>  
  
-   <span data-ttu-id="55ec9-186">0xFFFFFFFFFFFFFFFE é tratado como um valor de prefixo especial usado para enviar dados em partes para o servidor de forma eficiente.</span><span class="sxs-lookup"><span data-stu-id="55ec9-186">0xFFFFFFFFFFFFFFFE is treated as a special prefix value which is used for efficiently sending data in chunks to the server.</span></span> <span data-ttu-id="55ec9-187">O formato dos dados com este prefixo especial é:</span><span class="sxs-lookup"><span data-stu-id="55ec9-187">The format of data with this special prefix is:</span></span>  
  
-   <span data-ttu-id="55ec9-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK> em que:</span><span class="sxs-lookup"><span data-stu-id="55ec9-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK> where:</span></span>  
  
-   <span data-ttu-id="55ec9-189">SPECIAL_PREFIX é 0xFFFFFFFFFFFFFFFE</span><span class="sxs-lookup"><span data-stu-id="55ec9-189">SPECIAL_PREFIX is 0xFFFFFFFFFFFFFFFE</span></span>  
  
-   <span data-ttu-id="55ec9-190">DATA_CHUNK é um prefixo de 4 bytes que contém o comprimento da parte, seguido dos dados reais cujo comprimento é especificado no prefixo de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="55ec9-190">DATA_CHUNK is a 4 byte prefix containing length of the chunk,followed by the actual data whose length is specified in the 4 byte prefix.</span></span>  
  
-   <span data-ttu-id="55ec9-191">ZERO_CHUNK é um valor de 4 bytes que contém todos os zeros (00000000) que indicam o final dos dados.</span><span class="sxs-lookup"><span data-stu-id="55ec9-191">ZERO_CHUNK is a 4 byte value containing all zeros (00000000) indicating the end of data.</span></span>  
  
-   <span data-ttu-id="55ec9-192">Qualquer outro comprimento de 8 bytes válido é tratado como um comprimento de dados normal.</span><span class="sxs-lookup"><span data-stu-id="55ec9-192">Any other valid 8 byte length is treated as a regular data length.</span></span>  
  
 <span data-ttu-id="55ec9-193">Chamar [bcp_columns](bcp-columns.md) ao usar **bcp_bind** resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="55ec9-193">Calling [bcp_columns](bcp-columns.md) when using **bcp_bind** results in an error.</span></span>  
  
## <a name="bcp_bind-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="55ec9-194">Suporte do bcp_bind a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="55ec9-194">bcp_bind Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="55ec9-195">Para obter informações sobre os tipos usados com o parâmetro *eDataType* para tipos de data/hora, consulte [alterações de cópia em massa para tipos de data e hora aprimorados &#40;OLE DB e ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="55ec9-195">For information about the types used with the *eDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="55ec9-196">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="55ec9-196">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="55ec9-197">Exemplo</span><span class="sxs-lookup"><span data-stu-id="55ec9-197">Example</span></span>  
  
```  
#include sql.h  
#include sqlext.h  
#include odbcss.h  
// Variables like henv not specified.  
HDBC      hdbc;  
char         szCompanyName[MAXNAME];  
DBINT      idCompany;  
DBINT      nRowsProcessed;  
DBBOOL      bMoreData;  
char*      pTerm = "\t\t";  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source; return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bcp.   
if (bcp_init(hdbc, "comdb..accounts_info", NULL, NULL  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idCompany, 0, sizeof(DBINT), NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_bind(hdbc, (LPCBYTE) szCompanyName, 0, SQL_VARLEN_DATA,  
   (LPCBYTE) pTerm, strnlen(pTerm, sizeof(pTerm)), SQLCHARACTER, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
while (TRUE)  
   {  
   // Retrieve and process program data.   
   if ((bMoreData = getdata(&idCompany, szCompanyName)) == TRUE)  
      {  
      // Send the data.   
      if (bcp_sendrow(hdbc) == FAIL)  
         {  
         // Raise error and return.  
         return;  
         }  
      }  
   else  
      {  
      // Break out of loop.  
      break;  
      }  
   }  
  
// Terminate the bulk copy operation.  
if ((nRowsProcessed = bcp_done(hdbc)) == -1)  
   {  
   printf_s("Bulk-copy unsuccessful.\n");  
   return;  
   }  
  
printf_s("%ld rows copied.\n", nRowsProcessed);  
```  
  
## <a name="see-also"></a><span data-ttu-id="55ec9-198">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55ec9-198">See Also</span></span>  
 [<span data-ttu-id="55ec9-199">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="55ec9-199">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
