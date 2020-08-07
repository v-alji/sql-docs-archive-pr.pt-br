---
title: Convertendo de DB-Library em cópia em massa ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- converting DB-Library to ODBC bulk copy
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], DB-Library bulk copy
- ODBC, bulk copy operations
- DB-Library bulk copy
ms.assetid: 0bc15bdb-f19f-4537-ac6c-f249f42cf07f
author: rothja
ms.author: jroth
ms.openlocfilehash: 866900606e582f08695fd4695a1098f34fb2b426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576352"
---
# <a name="converting-from-db-library-to-odbc-bulk-copy"></a><span data-ttu-id="343af-102">Convertendo de cópia em massa DB-Library em ODBC</span><span class="sxs-lookup"><span data-stu-id="343af-102">Converting from DB-Library to ODBC Bulk Copy</span></span>
  <span data-ttu-id="343af-103">A conversão de um programa de cópia em massa de biblioteca de banco de BD para ODBC é fácil porque as funções de cópia em massa com suporte do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client são semelhantes às funções de cópia em massa da biblioteca de banco de BD, com as seguintes exceções:</span><span class="sxs-lookup"><span data-stu-id="343af-103">Converting a DB-Library bulk copy program to ODBC is easy because the bulk copy functions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver are similar to the DB-Library bulk copy functions, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="343af-104">Os aplicativos DB-Library passam, para uma estrutura DBPROCESS, um ponteiro como o primeiro parâmetro de funções de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="343af-104">DB-Library applications pass a pointer to a DBPROCESS structure as the first parameter of bulk copy functions.</span></span> <span data-ttu-id="343af-105">Em aplicativos ODBC, o ponteiro DBPROCESS é substituído por um identificador de conexão ODBC.</span><span class="sxs-lookup"><span data-stu-id="343af-105">In ODBC applications, the DBPROCESS pointer is replaced with an ODBC connection handle.</span></span>  
  
-   <span data-ttu-id="343af-106">Os aplicativos de biblioteca de banco de BD chamam **BCP_SETL** antes de se conectar para habilitar operações de cópia em massa em um DBPROCESS.</span><span class="sxs-lookup"><span data-stu-id="343af-106">DB-Library applications call **BCP_SETL** before connecting to enable bulk copy operations on a DBPROCESS.</span></span> <span data-ttu-id="343af-107">Aplicativos ODBC, em vez disso, chamam [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) antes de se conectar para habilitar operações em massa em um identificador de conexão:</span><span class="sxs-lookup"><span data-stu-id="343af-107">ODBC applications instead call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) before connecting to enable bulk operations on a connection handle:</span></span>  
  
    ```  
    SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP,  
        (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
    ```  
  
-   <span data-ttu-id="343af-108">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client não dá suporte a mensagens de biblioteca de BD e manipuladores de erro; você deve chamar **SQLGetDiagRec** para obter erros e mensagens geradas pelas funções de cópia em massa ODBC.</span><span class="sxs-lookup"><span data-stu-id="343af-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support DB-Library message and error handlers; you must call **SQLGetDiagRec** to get errors and messages raised by the ODBC bulk copy functions.</span></span> <span data-ttu-id="343af-109">As versões ODBC das funções de cópia em massa retornam os códigos de retorno padrão da cópia em massa, SUCCEED ou FAILED, e não os códigos de retorno ODBC, como SQL_SUCCESS ou SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="343af-109">The ODBC versions of bulk copy functions return the standard bulk copy return codes of SUCCEED or FAILED, not ODBC-style return codes, such as SQL_SUCCESS or SQL_ERROR.</span></span>  
  
-   <span data-ttu-id="343af-110">Os valores especificados para o parâmetro DB-Library [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)*varlen* são interpretados de forma diferente do parâmetro_cbData_ do ODBC **bcp_bind**.</span><span class="sxs-lookup"><span data-stu-id="343af-110">The values specified for the DB-Library [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)*varlen* parameter are interpreted differently than the ODBC **bcp_bind**_cbData_ parameter.</span></span>  
  
    |<span data-ttu-id="343af-111">Condição indicada</span><span class="sxs-lookup"><span data-stu-id="343af-111">Condition indicated</span></span>|<span data-ttu-id="343af-112">DB-valor de *varlen* da biblioteca</span><span class="sxs-lookup"><span data-stu-id="343af-112">DB-Library *varlen* value</span></span>|<span data-ttu-id="343af-113">Valor de *CBDATA* ODBC</span><span class="sxs-lookup"><span data-stu-id="343af-113">ODBC *cbData* value</span></span>|  
    |-------------------------|--------------------------------|-------------------------|  
    |<span data-ttu-id="343af-114">Valores nulos fornecidos</span><span class="sxs-lookup"><span data-stu-id="343af-114">Null values supplied</span></span>|<span data-ttu-id="343af-115">0</span><span class="sxs-lookup"><span data-stu-id="343af-115">0</span></span>|<span data-ttu-id="343af-116">-1 (SQL_NULL_DATA)</span><span class="sxs-lookup"><span data-stu-id="343af-116">-1 (SQL_NULL_DATA)</span></span>|  
    |<span data-ttu-id="343af-117">Dados de variável fornecidos</span><span class="sxs-lookup"><span data-stu-id="343af-117">Variable data supplied</span></span>|<span data-ttu-id="343af-118">-1</span><span class="sxs-lookup"><span data-stu-id="343af-118">-1</span></span>|<span data-ttu-id="343af-119">-10 (SQL_VARLEN_DATA)</span><span class="sxs-lookup"><span data-stu-id="343af-119">-10 (SQL_VARLEN_DATA)</span></span>|  
    |<span data-ttu-id="343af-120">Cadeia binária ou de caracteres de comprimento zero</span><span class="sxs-lookup"><span data-stu-id="343af-120">Zero length character or binary string</span></span>|<span data-ttu-id="343af-121">NA</span><span class="sxs-lookup"><span data-stu-id="343af-121">NA</span></span>|<span data-ttu-id="343af-122">0</span><span class="sxs-lookup"><span data-stu-id="343af-122">0</span></span>|  
  
     <span data-ttu-id="343af-123">Na biblioteca de banco de dados, um valor de *varlen* de-1 indica que os dados de comprimento variável estão sendo fornecidos, que no *cbData* ODBC é interpretado para significar que apenas valores nulos estão sendo fornecidos.</span><span class="sxs-lookup"><span data-stu-id="343af-123">In DB-Library, a *varlen* value of -1 indicates that variable length data is being supplied, which in the ODBC *cbData* is interpreted to mean that only NULL values are being supplied.</span></span> <span data-ttu-id="343af-124">Altere as especificações de-1 de *varlen* da biblioteca de banco de forma para SQL_VARLEN_DATA e quaisquer especificações de *varlen* de 0 para SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="343af-124">Change any DB-Library *varlen* specifications of -1 to SQL_VARLEN_DATA and any *varlen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="343af-125">O arquivo \*\* \_ colfmt bcp\**da biblioteca DB_ \_ Collen_ e o ODBC [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)*cbUserData\* têm o mesmo problema que os parâmetros_varlen_ **bcp_bind**e *cbData* indicados acima.</span><span class="sxs-lookup"><span data-stu-id="343af-125">The DB-Library **bcp\_colfmt**_file\_collen_ and the ODBC [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)*cbUserData* have the same issue as the **bcp_bind**_varlen_ and *cbData* parameters noted above.</span></span> <span data-ttu-id="343af-126">Altere todas as especificações de *file_collen* de biblioteca de banco de BD de-1 para SQL_VARLEN_DATA e quaisquer *file_collen* especificações de 0 a SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="343af-126">Change any DB-Library *file_collen* specifications of -1 to SQL_VARLEN_DATA and any *file_collen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="343af-127">O parâmetro *iValue* da função ODBC [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) é um ponteiro void.</span><span class="sxs-lookup"><span data-stu-id="343af-127">The *iValue* parameter of the ODBC [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) function is a void pointer.</span></span> <span data-ttu-id="343af-128">Em DB-Library, *iValue* era um número inteiro.</span><span class="sxs-lookup"><span data-stu-id="343af-128">In DB-Library, *iValue* was an integer.</span></span> <span data-ttu-id="343af-129">Converta os valores para o *IVALUE* ODBC em void \*.</span><span class="sxs-lookup"><span data-stu-id="343af-129">Cast the values for the ODBC *iValue* to void \*.</span></span>  
  
-   <span data-ttu-id="343af-130">A opção **BCP_CONTROL** BCPMAXERRS especifica quantas linhas individuais podem ter erros antes de uma operação de cópia em massa falhar.</span><span class="sxs-lookup"><span data-stu-id="343af-130">The **bcp_control** option BCPMAXERRS specifies how many individual rows can have errors before a bulk copy operation fails.</span></span> <span data-ttu-id="343af-131">O padrão para BCPMAXERRS é 0 (falha no primeiro erro) na versão da biblioteca DB do **bcp_control** e 10 na versão do ODBC.</span><span class="sxs-lookup"><span data-stu-id="343af-131">The default for BCPMAXERRS is 0 (fail on first error) in the DB-Library version of **bcp_control** and 10 in the ODBC version.</span></span> <span data-ttu-id="343af-132">Os aplicativos de biblioteca de banco de BD que dependem do padrão de 0 para encerrar uma operação de cópia em massa devem ser alterados para chamar o **BCP_CONTROL** ODBC para definir BCPMAXERRS como 0.</span><span class="sxs-lookup"><span data-stu-id="343af-132">DB-Library applications that depend on the default of 0 to terminate a bulk copy operation must be changed to call the ODBC **bcp_control** to set BCPMAXERRS to 0.</span></span>  
  
-   <span data-ttu-id="343af-133">A função de **BCP_CONTROL** ODBC dá suporte às seguintes opções não suportadas pela versão da biblioteca de banco de bd do **bcp_control**:</span><span class="sxs-lookup"><span data-stu-id="343af-133">The ODBC **bcp_control** function supports the following options not supported by the DB-Library version of **bcp_control**:</span></span>  
  
    -   <span data-ttu-id="343af-134">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="343af-134">BCPODBC</span></span>  
  
         <span data-ttu-id="343af-135">Quando definido como TRUE, especifica que os valores **DateTime** e **smalldatetime** salvos no formato de caractere terão o prefixo e o sufixo da sequência de saída do carimbo de data e hora do ODBC.</span><span class="sxs-lookup"><span data-stu-id="343af-135">When set to TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will have the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="343af-136">Isso se aplica apenas a operações BCP_OUT.</span><span class="sxs-lookup"><span data-stu-id="343af-136">This only applies to BCP_OUT operations.</span></span>  
  
         <span data-ttu-id="343af-137">Com BCPODBC definido como FALSE, um valor **DateTime** convertido em uma cadeia de caracteres é resultado como:</span><span class="sxs-lookup"><span data-stu-id="343af-137">With BCPODBC set to FALSE, a **datetime** value converted to a character string is output as:</span></span>  
  
        ```  
        1997-01-01 00:00:00.000  
        ```  
  
         <span data-ttu-id="343af-138">Com BCPODBC definido como TRUE, o mesmo valor **DateTime** é output as:</span><span class="sxs-lookup"><span data-stu-id="343af-138">With BCPODBC set to TRUE, the same **datetime** value is output as:</span></span>  
  
        ```  
        {ts '1997-01-01 00:00:00.000' }  
        ```  
  
    -   <span data-ttu-id="343af-139">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="343af-139">BCPKEEPIDENTITY</span></span>  
  
         <span data-ttu-id="343af-140">Quando definido como TRUE, especifica que as funções de cópia em massa inserem valores de dados fornecidos para colunas com restrições de identidade.</span><span class="sxs-lookup"><span data-stu-id="343af-140">When set to TRUE, specifies that bulk copy functions insert data values supplied for columns with identity constraints.</span></span> <span data-ttu-id="343af-141">Se essa opção não for definida, novos valores de identidade serão gerados para as linhas inseridas.</span><span class="sxs-lookup"><span data-stu-id="343af-141">If this is not set, new identity values are generated for the inserted rows.</span></span>  
  
    -   <span data-ttu-id="343af-142">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="343af-142">BCPHINTS</span></span>  
  
         <span data-ttu-id="343af-143">Especifica várias otimizações de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="343af-143">Specifies various bulk copy optimizations.</span></span> <span data-ttu-id="343af-144">Essa opção não pode ser usada na versão 6.5 nem em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="343af-144">This option cannot be used on 6.5 or earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="343af-145">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="343af-145">BCPFILECP</span></span>  
  
         <span data-ttu-id="343af-146">Especifica a página de código do arquivo de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="343af-146">Specifies the code page of the bulk copy file.</span></span>  
  
    -   <span data-ttu-id="343af-147">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="343af-147">BCPUNICODEFILE</span></span>  
  
         <span data-ttu-id="343af-148">Especifica que um arquivo de cópia em massa em modo de caractere é um arquivo Unicode.</span><span class="sxs-lookup"><span data-stu-id="343af-148">Specifies that a character mode bulk copy file is a Unicode file.</span></span>  
  
-   <span data-ttu-id="343af-149">A função de **BCP_COLFMT** ODBC não dá suporte ao indicador de *file_type* de SQLCHAR porque está em conflito com o TYPEDEF SQLCHAR do ODBC.</span><span class="sxs-lookup"><span data-stu-id="343af-149">The ODBC **bcp_colfmt** function does not support the *file_type* indicator of SQLCHAR because it conflicts with the ODBC SQLCHAR typedef.</span></span> <span data-ttu-id="343af-150">Use SQLCHARACTER em vez de **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="343af-150">Use SQLCHARACTER instead for **bcp_colfmt**.</span></span>  
  
-   <span data-ttu-id="343af-151">Nas versões ODBC das funções de cópia em massa, o formato para trabalhar com valores **DateTime** e **smalldatetime** em cadeias de caracteres é o formato ODBC de aaaa-mm-dd hh: mm: SS. SSS; os valores **smalldatetime** usam o formato ODBC de aaaa-mm-dd hh: mm: SS.</span><span class="sxs-lookup"><span data-stu-id="343af-151">In the ODBC versions of bulk copy functions, the format for working with **datetime** and **smalldatetime** values in character strings is the ODBC format of yyyy-mm-dd hh:mm:ss.sss; **smalldatetime** values use the ODBC format of yyyy-mm-dd hh:mm:ss.</span></span>  
  
     <span data-ttu-id="343af-152">As versões da biblioteca de banco de BD das funções de cópia em massa aceitam valores **DateTime** e **smalldatetime** em cadeias de caracteres usando vários formatos:</span><span class="sxs-lookup"><span data-stu-id="343af-152">The DB-Library versions of the bulk copy functions accept **datetime** and **smalldatetime** values in character strings using several formats:</span></span>  
  
    -   <span data-ttu-id="343af-153">O formato padrão é *Mmm dd aaaa hh: mmxx* , em que *XX* é AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="343af-153">The default format is *mmm dd yyyy hh:mmxx* where *xx* is either AM or PM.</span></span>  
  
    -   <span data-ttu-id="343af-154">cadeias de caracteres **DateTime** e **smalldatetime** em qualquer formato com suporte pela função **DBConvert** do DB-Library.</span><span class="sxs-lookup"><span data-stu-id="343af-154">**datetime** and **smalldatetime** character strings in any format supported by the DB-Library **dbconvert** function.</span></span>  
  
    -   <span data-ttu-id="343af-155">Quando a caixa **usar configurações internacionais** é marcada na guia **Opções** da biblioteca de banco de dados do utilitário de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rede do cliente, as funções de cópia em massa da biblioteca de banco de dados também aceitam datas no formato de data regional definido para a configuração de localidade do registro do computador cliente.</span><span class="sxs-lookup"><span data-stu-id="343af-155">When the **Use international settings** box is checked on the DB-Library **Options** tab of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility, the DB-Library bulk copy functions also accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
     <span data-ttu-id="343af-156">As funções de cópia em massa da biblioteca DB não aceitam os formatos ODBC **DateTime** e **smalldatetime** .</span><span class="sxs-lookup"><span data-stu-id="343af-156">The DB-Library bulk copy functions do not accept the ODBC **datetime** and **smalldatetime** formats.</span></span>  
  
     <span data-ttu-id="343af-157">Se o atributo da instrução SQL_SOPT_SS_REGIONALIZE estiver definido como SQL_RE_ON, as funções de cópia em massa do ODBC aceitarão datas no formato de data regional definido para a configuração de localidade do registro do computador cliente.</span><span class="sxs-lookup"><span data-stu-id="343af-157">If the SQL_SOPT_SS_REGIONALIZE statement attribute is set to SQL_RE_ON, the ODBC bulk copy functions accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
-   <span data-ttu-id="343af-158">Ao gerar valores **monetários** no formato de caractere, as funções de cópia em massa ODBC fornecem quatro dígitos de precisão e nenhum separador de vírgula; As versões de biblioteca do banco de BD fornecem apenas dois dígitos de precisão e incluem os separadores de vírgula.</span><span class="sxs-lookup"><span data-stu-id="343af-158">When outputting **money** values in character format, ODBC bulk copy functions supply four digits of precision and no comma separators; DB-Library versions only supply two digits of precision and include the comma separators.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="343af-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="343af-159">See Also</span></span>  
 <span data-ttu-id="343af-160">[Executando operações de cópia em massa &#40;&#41;ODBC](performing-bulk-copy-operations-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="343af-160">[Performing Bulk Copy Operations &#40;ODBC&#41;](performing-bulk-copy-operations-odbc.md) </span></span>  
 [<span data-ttu-id="343af-161">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="343af-161">Bulk Copy Functions</span></span>](../native-client-odbc-extensions-bulk-copy-functions/sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
