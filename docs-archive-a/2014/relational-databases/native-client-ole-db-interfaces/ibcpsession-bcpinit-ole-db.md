---
title: IBCPSession::BCPInit (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPInit (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPInit method
ms.assetid: 583096d7-da34-49be-87fd-31210aac81aa
author: rothja
ms.author: jroth
ms.openlocfilehash: 25a01c71811de9d47ce01714402460bb53d4c70e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679932"
---
# <a name="ibcpsessionbcpinit-ole-db"></a><span data-ttu-id="4ca39-102">IBCPSession::BCPInit (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="4ca39-102">IBCPSession::BCPInit (OLE DB)</span></span>
  <span data-ttu-id="4ca39-103">Inicializa a estrutura de cópia em massa, executa alguma verificação de erros, verifica se os nomes dos arquivos de formato e de dados estão corretos e, então, os abre.</span><span class="sxs-lookup"><span data-stu-id="4ca39-103">Initializes the bulk copy structure, performs some error checking, verifies that the data and format file names are correct, and then opens them.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca39-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4ca39-104">Syntax</span></span>  
  
```  
  
HRESULT BCPInit(   
const wchar_t *pwszTable,  
const wchar_t *pwszDataFile,  
const wchar_t *pwszErrorFile,  
inteDirection);  
```  
  
## <a name="remarks"></a><span data-ttu-id="4ca39-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="4ca39-105">Remarks</span></span>  
 <span data-ttu-id="4ca39-106">O método **BCPInit** deve ser chamado antes de qualquer outro método de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="4ca39-106">The **BCPInit** method should be called before any other bulk-copy method.</span></span> <span data-ttu-id="4ca39-107">O método **BCPInit** executa as inicializações necessárias para uma cópia em massa de dados entre a estação de trabalho e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ca39-107">The **BCPInit** method performs the necessary initializations for a bulk copy of data between the workstation and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4ca39-108">O método **BCPInit** examina a estrutura da tabela de origem ou de destino do banco de dados, não o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="4ca39-108">The **BCPInit** method examines the structure of the database source or target table, not the data file.</span></span> <span data-ttu-id="4ca39-109">Ele especifica valores de formato de dados para o arquivo de dados com base em cada coluna na tabela, exibição ou conjunto de resultados SELECT do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ca39-109">It specifies data format values for the data file based on each column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="4ca39-110">Essa especificação inclui o tipo de dados de cada coluna, a presença ou ausência de um indicador de comprimento ou nulo e cadeias de caracteres de bytes de terminador nos dados, além da largura de tipos de dados de comprimento fixo.</span><span class="sxs-lookup"><span data-stu-id="4ca39-110">This specification includes the data type of each column, the presence or absence of a length or null indicator and terminator byte strings in the data, and the width of fixed-length data types.</span></span> <span data-ttu-id="4ca39-111">O método **BCPInit** define esses valores da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4ca39-111">The **BCPInit** method sets these values as follows:</span></span>  
  
-   <span data-ttu-id="4ca39-112">O tipo de dados especificado é o tipo de dados da coluna na tabela, exibição ou conjunto de resultados de SELECT do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ca39-112">The data type specified is the data type of the column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="4ca39-113">O tipo de dados é enumerado por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados nativos especificados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] arquivo de cabeçalho nativo do cliente (sqlncli. h).</span><span class="sxs-lookup"><span data-stu-id="4ca39-113">The data type is enumerated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types specified in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client header file (sqlncli.h).</span></span> <span data-ttu-id="4ca39-114">Seus valores estão no padrão de BCP_TYPE_XXX.</span><span class="sxs-lookup"><span data-stu-id="4ca39-114">Their values are in the pattern of BCP_TYPE_XXX.</span></span> <span data-ttu-id="4ca39-115">Os dados são representados em seu formato de computador.</span><span class="sxs-lookup"><span data-stu-id="4ca39-115">The data is represented in its computer form.</span></span> <span data-ttu-id="4ca39-116">Ou seja, os dados de uma coluna com o tipo de dados inteiro são representados por uma sequência de quatro bytes baseado em big ou little endian no computador que criou o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="4ca39-116">That is, data from a column of integer data type is represented by a four-byte sequence that is big-or little-endian based on the computer that created the data file.</span></span>  
  
-   <span data-ttu-id="4ca39-117">Se um tipo de dados de banco de dados tiver comprimento fixo, os dados do arquivo de dados também terão comprimento fixo.</span><span class="sxs-lookup"><span data-stu-id="4ca39-117">If a database data type is fixed in length, the data file data is also fixed in length.</span></span> <span data-ttu-id="4ca39-118">Os métodos de cópia em massa que processam dados (por exemplo, [IBCPSession::BCPExec](ibcpsession-bcpexec-ole-db.md)) analisam as linhas de dados esperando que o tamanho dos dados no arquivo de dados seja idêntico ao tamanho dos dados especificados na tabela, na exibição ou na lista de colunas SELECT do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ca39-118">Bulk-copy methods that process data (for example, [IBCPSession::BCPExec](ibcpsession-bcpexec-ole-db.md)) parse data rows expecting the length of the data in the data file to be identical to the length of the data specified in the database table, view, or SELECT column list.</span></span> <span data-ttu-id="4ca39-119">Por exemplo, os dados de uma coluna de banco de dados definida como `char(13)` devem ser representados por 13 caracteres para cada linha de dados no arquivo.</span><span class="sxs-lookup"><span data-stu-id="4ca39-119">For example, data for a database column defined as `char(13)` must be represented by 13 characters for each row of data in the file.</span></span> <span data-ttu-id="4ca39-120">Os dados de comprimento fixo podem ser prefixados com um indicador nulo se a coluna do banco de dados permitir valores nulos.</span><span class="sxs-lookup"><span data-stu-id="4ca39-120">Fixed-length data can be prefixed with a null indicator if the database column allows null values.</span></span>  
  
-   <span data-ttu-id="4ca39-121">Ao copiar dados para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o arquivo de dados deve ter dados em cada coluna na tabela do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ca39-121">When copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data file must have data for each column in the database table.</span></span> <span data-ttu-id="4ca39-122">Ao copiar dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], os dados de todas as colunas na tabela, exibição ou conjunto de resultados de SELECT do banco de dados são copiados para o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="4ca39-122">When copying data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data from all columns in the database table, view, or SELECT result set are copied to the data file.</span></span>  
  
-   <span data-ttu-id="4ca39-123">Ao copiar dados para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a posição ordinal de uma coluna no arquivo de dados deve ser idêntica à posição ordinal da coluna na tabela do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ca39-123">When copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the ordinal position of a column in the data file must be identical to the ordinal position of the column in the database table.</span></span> <span data-ttu-id="4ca39-124">Ao copiar dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o método **BCPExec** coloca os dados com base na posição ordinal da coluna na tabela de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ca39-124">When copying data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the **BCPExec** method places data based on the ordinal position of the column in the database table.</span></span>  
  
-   <span data-ttu-id="4ca39-125">Se um tipo de dados do banco de dados tiver comprimento variável (por exemplo, `varbinary(22)`) ou se uma coluna do banco de dados puder conter valores nulos, os dados nos arquivos de dados serão prefixados com um indicador de comprimento/nulo.</span><span class="sxs-lookup"><span data-stu-id="4ca39-125">If a database data type is variable in length (for example, `varbinary(22)`) or if a database column can contain null values, data in the data file is prefixed by a length/null indicator.</span></span> <span data-ttu-id="4ca39-126">A largura do indicador varia dependendo do tipo de dados e da versão da cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="4ca39-126">The width of the indicator varies based on the data type and version of bulk copy.</span></span> <span data-ttu-id="4ca39-127">A opção BCP_OPTION_FILEFMT do método [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) oferece compatibilidade entre arquivos de dados de cópia em massa anteriores e servidores que executam versões posteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] indicando quando a largura dos indicadores nos dados é mais estreita que o esperado.</span><span class="sxs-lookup"><span data-stu-id="4ca39-127">The [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) method option BCP_OPTION_FILEFMT provides compatibility between earlier bulk-copy data files and servers running later versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by indicating when the width of indicators in the data is narrower than expected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ca39-128">Para alterar os valores de formato de dados especificados para um arquivo de dados, use os métodos [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) e [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="4ca39-128">To change the data format values specified for a data file, use the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods.</span></span>  
  
 <span data-ttu-id="4ca39-129">É possível otimizar cópias em massa para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para tabelas que não contêm índices, definindo a opção de banco de dados **select into/bulkcopy**.</span><span class="sxs-lookup"><span data-stu-id="4ca39-129">Bulk copies to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be optimized for tables that do not contain indexes by setting the database option **select into/bulkcopy**.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="4ca39-130">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4ca39-130">Arguments</span></span>  
 <span data-ttu-id="4ca39-131">*pwszTable*[in]</span><span class="sxs-lookup"><span data-stu-id="4ca39-131">*pwszTable*[in]</span></span>  
 <span data-ttu-id="4ca39-132">O nome da tabela do banco de dados a ser copiada de ou para.</span><span class="sxs-lookup"><span data-stu-id="4ca39-132">The name of the database table to be copied into or out of.</span></span> <span data-ttu-id="4ca39-133">O nome pode incluir o nome do banco de dados ou o nome do proprietário.</span><span class="sxs-lookup"><span data-stu-id="4ca39-133">The name can include the database name or the owner name.</span></span> <span data-ttu-id="4ca39-134">Por exemplo, "pubs.username.titles", "pubs..titles", "username.titles".</span><span class="sxs-lookup"><span data-stu-id="4ca39-134">For example, "pubs.username.titles", "pubs..titles", "username.titles".</span></span>  
  
 <span data-ttu-id="4ca39-135">Se o argumento eDirection for definido como BCP_DIRECTION_OUT, o argumento pwszTable poderá ser o nome de uma exibição do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4ca39-135">If the eDirection argument is set to BCP_DIRECTION_OUT, the pwszTable argument can be the name of a database view.</span></span>  
  
 <span data-ttu-id="4ca39-136">Se o argumento eDirection for definido como BCP_DIRECTION_OUT e uma instrução SELECT for especificada usando o método **BCPControl** antes de o método **BCPExec** ser chamado, o argumento *pwszTable* precisará ser definido como NULL.</span><span class="sxs-lookup"><span data-stu-id="4ca39-136">If the eDirection argument is set to BCP_DIRECTION_OUT and a SELECT statement is specified using the **BCPControl** method before the **BCPExec** method is called, the *pwszTable* argument must be set to NULL.</span></span>  
  
 <span data-ttu-id="4ca39-137">*pwszDataFile*[in]</span><span class="sxs-lookup"><span data-stu-id="4ca39-137">*pwszDataFile*[in]</span></span>  
 <span data-ttu-id="4ca39-138">O nome do arquivo do usuário a ser copiado de ou para.</span><span class="sxs-lookup"><span data-stu-id="4ca39-138">The name of the user file to be copied into or out of.</span></span>  
  
 <span data-ttu-id="4ca39-139">*pwszErrorFile*[in]</span><span class="sxs-lookup"><span data-stu-id="4ca39-139">*pwszErrorFile*[in]</span></span>  
 <span data-ttu-id="4ca39-140">O nome do arquivo de erro a ser preenchido com mensagens de progresso, mensagens de erro e cópias das linhas que não puderam ser copiadas de um arquivo do usuário para uma tabela.</span><span class="sxs-lookup"><span data-stu-id="4ca39-140">The name of the error file to be filled with progress messages, error messages, and copies of any rows that could not be copied from a user file to a table.</span></span> <span data-ttu-id="4ca39-141">Se o argumento *pwszErrorFile* for definido como NULL, nenhum arquivo de erro será usado.</span><span class="sxs-lookup"><span data-stu-id="4ca39-141">If the *pwszErrorFile* argument is set to NULL, no error file is used.</span></span>  
  
 <span data-ttu-id="4ca39-142">*eDirection*[in]</span><span class="sxs-lookup"><span data-stu-id="4ca39-142">*eDirection*[in]</span></span>  
 <span data-ttu-id="4ca39-143">A direção da operação de cópia, BCP_DIRECTION_IN ou _OUT de BCP_DIRECTION.</span><span class="sxs-lookup"><span data-stu-id="4ca39-143">The direction of the copy operation, either BCP_DIRECTION_IN or BCP_DIRECTION _OUT.</span></span> <span data-ttu-id="4ca39-144">BCP_DIRECTION _IN indica uma cópia de um arquivo do usuário para uma tabela do banco de dados; BCP_DIRECTION _OUT indica uma cópia de uma tabela do banco de dados para um arquivo do usuário.</span><span class="sxs-lookup"><span data-stu-id="4ca39-144">BCP_DIRECTION _IN indicates a copy from a user file to a database table; BCP_DIRECTION _OUT indicates a copy from a database table to a user file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="4ca39-145">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="4ca39-145">Return Code Values</span></span>  
 <span data-ttu-id="4ca39-146">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ca39-146">S_OK</span></span>  
 <span data-ttu-id="4ca39-147">O método foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="4ca39-147">The method succeeded.</span></span>  
  
 <span data-ttu-id="4ca39-148">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ca39-148">E_FAIL</span></span>  
 <span data-ttu-id="4ca39-149">Ocorreu um erro específico do provedor ' para obter informações detalhadas, use a interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="4ca39-149">A provider specific error occurred' for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="4ca39-150">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4ca39-150">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="4ca39-151">Erro de memória insuficiente.</span><span class="sxs-lookup"><span data-stu-id="4ca39-151">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="4ca39-152">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4ca39-152">E_INVALIDARG</span></span>  
 <span data-ttu-id="4ca39-153">Um ou mais dos argumentos não foi especificado corretamente.</span><span class="sxs-lookup"><span data-stu-id="4ca39-153">One or more of the arguments was not correctly specified.</span></span> <span data-ttu-id="4ca39-154">Por exemplo, foi especificado um nome de arquivo inválido.</span><span class="sxs-lookup"><span data-stu-id="4ca39-154">For example, an invalid file name was given.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca39-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4ca39-155">See Also</span></span>  
 <span data-ttu-id="4ca39-156">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="4ca39-156">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="4ca39-157">Executando operações de cópia em massa</span><span class="sxs-lookup"><span data-stu-id="4ca39-157">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
