---
title: bcp_init | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_init
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_init function
ms.assetid: 6a25862c-7f31-4873-ab65-30f3abde89d2
author: rothja
ms.author: jroth
ms.openlocfilehash: 72d48b2a07e425e0863084c700c4de93d2776739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572062"
---
# <a name="bcp_init"></a><span data-ttu-id="71f6e-102">bcp_init</span><span class="sxs-lookup"><span data-stu-id="71f6e-102">bcp_init</span></span>
  <span data-ttu-id="71f6e-103">Inicializa a operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="71f6e-103">Initializes the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f6e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="71f6e-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_init (  
HDBC   
hdbc  
,  
LPCTSTR   
szTable  
,  
LPCTSTR   
szDataFile  
,  
LPCTSTR   
szErrorFile  
,  
INT   
eDirection  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="71f6e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="71f6e-105">Arguments</span></span>  
 <span data-ttu-id="71f6e-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="71f6e-106">*hdbc*</span></span>  
 <span data-ttu-id="71f6e-107">É o identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="71f6e-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="71f6e-108">*szTable*</span><span class="sxs-lookup"><span data-stu-id="71f6e-108">*szTable*</span></span>  
 <span data-ttu-id="71f6e-109">É o nome da tabela do banco de dados a ser copiada de ou para.</span><span class="sxs-lookup"><span data-stu-id="71f6e-109">Is the name of the database table to be copied into or out of.</span></span> <span data-ttu-id="71f6e-110">Este nome também pode incluir o nome do banco de dados ou o nome do proprietário.</span><span class="sxs-lookup"><span data-stu-id="71f6e-110">This name can also include the database name or the owner name.</span></span> <span data-ttu-id="71f6e-111">Por exemplo, **pubs. Gracie. titles**, **pubs.. títulos**, **Gracie. titles**e **títulos** são todos nomes de tabelas legais.</span><span class="sxs-lookup"><span data-stu-id="71f6e-111">For example, **pubs.gracie.titles**, **pubs..titles**, **gracie.titles**, and **titles** are all legal table names.</span></span>  
  
 <span data-ttu-id="71f6e-112">Se *eDirection* for DB_OUT, *szTable* também poderá ser o nome de uma exibição de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71f6e-112">If *eDirection* is DB_OUT, *szTable* can also be the name of a database view.</span></span>  
  
 <span data-ttu-id="71f6e-113">Se *eDirection* for DB_OUT e uma instrução SELECT for especificada usando [bcp_control](bcp-control.md) antes que [bcp_exec](bcp-exec.md) seja chamado, **bcp_init**_szTable_ deverá ser definido como NULL.</span><span class="sxs-lookup"><span data-stu-id="71f6e-113">If *eDirection* is DB_OUT and a SELECT statement is specified using [bcp_control](bcp-control.md) before [bcp_exec](bcp-exec.md) is called, **bcp_init**_szTable_ must be set to NULL.</span></span>  
  
 <span data-ttu-id="71f6e-114">*szDataFile*</span><span class="sxs-lookup"><span data-stu-id="71f6e-114">*szDataFile*</span></span>  
 <span data-ttu-id="71f6e-115">É o nome do arquivo de usuário a ser copiado de ou para.</span><span class="sxs-lookup"><span data-stu-id="71f6e-115">Is the name of the user file to be copied into or out of.</span></span> <span data-ttu-id="71f6e-116">Se os dados estiverem sendo copiados diretamente de variáveis usando [bcp_sendrow](bcp-sendrow.md), defina *szDataFile* como nulo.</span><span class="sxs-lookup"><span data-stu-id="71f6e-116">If data is being copied directly from variables by using [bcp_sendrow](bcp-sendrow.md), set *szDataFile* to NULL.</span></span>  
  
 <span data-ttu-id="71f6e-117">*szErrorFile*</span><span class="sxs-lookup"><span data-stu-id="71f6e-117">*szErrorFile*</span></span>  
 <span data-ttu-id="71f6e-118">É o nome do arquivo de erro a ser preenchido com mensagens de progresso, mensagens de erro e cópias das linhas que, por algum motivo, não puderam ser copiadas de um arquivo de usuário para uma tabela.</span><span class="sxs-lookup"><span data-stu-id="71f6e-118">Is the name of the error file to be filled with progress messages, error messages, and copies of any rows that, for any reason, could not be copied from a user file to a table.</span></span> <span data-ttu-id="71f6e-119">Se NULL for passado como *szErrorFile*, nenhum arquivo de erro será usado.</span><span class="sxs-lookup"><span data-stu-id="71f6e-119">If NULL is passed as *szErrorFile*, no error file is used.</span></span>  
  
 <span data-ttu-id="71f6e-120">*eDirection*</span><span class="sxs-lookup"><span data-stu-id="71f6e-120">*eDirection*</span></span>  
 <span data-ttu-id="71f6e-121">É a direção da cópia, DB_IN ou DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="71f6e-121">Is the direction of the copy, either DB_IN or DB_OUT.</span></span> <span data-ttu-id="71f6e-122">DB_IN indica uma cópia de variáveis do programa ou de um arquivo de usuário para uma tabela.</span><span class="sxs-lookup"><span data-stu-id="71f6e-122">DB_IN indicates a copy from program variables or a user file to a table.</span></span> <span data-ttu-id="71f6e-123">DB_OUT indica uma cópia de uma tabela do banco de dados para um arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="71f6e-123">DB_OUT indicates a copy from a database table to a user file.</span></span> <span data-ttu-id="71f6e-124">Especifique um nome de arquivo de usuário com DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="71f6e-124">You must specify a user file name with DB_OUT.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="71f6e-125">Retornos</span><span class="sxs-lookup"><span data-stu-id="71f6e-125">Returns</span></span>  
 <span data-ttu-id="71f6e-126">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="71f6e-126">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71f6e-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="71f6e-127">Remarks</span></span>  
 <span data-ttu-id="71f6e-128">Chame **bcp_init** antes de chamar qualquer outra função de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="71f6e-128">Call **bcp_init** before calling any other bulk-copy function.</span></span> <span data-ttu-id="71f6e-129">**bcp_init** executa as inicializações necessárias para uma cópia em massa de dados entre a estação de trabalho e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71f6e-129">**bcp_init** performs the necessary initializations for a bulk copy of data between the workstation and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="71f6e-130">A função **bcp_init** deve ser fornecida com um identificador de conexão ODBC habilitado para uso com funções de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="71f6e-130">The **bcp_init** function must be provided with an ODBC connection handle enabled for use with bulk copy functions.</span></span> <span data-ttu-id="71f6e-131">Para habilitar o identificador, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_COPT_SS_BCP definido como SQL_BCP_ON em um identificador de conexão alocado, mas não conectado.</span><span class="sxs-lookup"><span data-stu-id="71f6e-131">To enable the handle, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_BCP set to SQL_BCP_ON on an allocated, but not connected, connection handle.</span></span> <span data-ttu-id="71f6e-132">A tentativa de atribuir o atributo em um identificador conectado resulta em erro.</span><span class="sxs-lookup"><span data-stu-id="71f6e-132">Attempting to assign the attribute on a connected handle results in an error.</span></span>  
  
 <span data-ttu-id="71f6e-133">Quando um arquivo de dados é especificado, **bcp_init** examina a estrutura da fonte do banco de dados ou da tabela de destino, não o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="71f6e-133">When a data file is specified, **bcp_init** examines the structure of the database source or target table, not the data file.</span></span> <span data-ttu-id="71f6e-134">**bcp_init** especifica valores de formato de dados para o arquivo de dados com base em cada coluna na tabela de banco de dado, no modo de exibição ou no conjunto de resultados selecionado.</span><span class="sxs-lookup"><span data-stu-id="71f6e-134">**bcp_init** specifies data format values for the data file based on each column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="71f6e-135">Essa especificação inclui o tipo de dados de cada coluna, a presença ou ausência de um indicador de comprimento ou nulo e cadeias de caracteres de bytes de terminador nos dados, além da largura de tipos de dados de comprimento fixo.</span><span class="sxs-lookup"><span data-stu-id="71f6e-135">This specification includes the data type of each column, the presence or absence of a length or null indicator and terminator byte strings in the data, and the width of fixed-length data types.</span></span> <span data-ttu-id="71f6e-136">**bcp_init** define esses valores da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="71f6e-136">**bcp_init** sets these values as follows:</span></span>  
  
-   <span data-ttu-id="71f6e-137">O tipo de dados especificado é o tipo de dados da coluna na tabela, exibição ou conjunto de resultados de SELECT do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71f6e-137">The data type specified is the data type of the column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="71f6e-138">O tipo de dados é enumerado por tipos de dados nativos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especificados em sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="71f6e-138">The data type is enumerated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types specified in sqlncli.h.</span></span> <span data-ttu-id="71f6e-139">Os dados são representados em seu próprio formato de computador.</span><span class="sxs-lookup"><span data-stu-id="71f6e-139">Data itself is represented in its computer form.</span></span> <span data-ttu-id="71f6e-140">Ou seja, os dados de uma coluna de tipo de dados **Integer** são representados por uma sequência de quatro bytes que é Big-ou little-endian com base no computador que criou o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="71f6e-140">That is, data from a column of **integer** data type is represented by a four-byte sequence that is big-or little-endian based on the computer that created the data file.</span></span>  
  
-   <span data-ttu-id="71f6e-141">Se um tipo de dados de banco de dados tiver comprimento fixo, os dados do arquivo de dados também terão comprimento fixo.</span><span class="sxs-lookup"><span data-stu-id="71f6e-141">If a database data type is fixed in length, the data file data is also fixed in length.</span></span> <span data-ttu-id="71f6e-142">As funções de cópia em massa que processam dados (por exemplo, [bcp_exec](bcp-exec.md)) analisam as linhas de dados esperando que o comprimento dos dados no arquivo de dados seja idêntico ao comprimento dos dados especificados na lista de colunas, exibição ou seleção de coluna</span><span class="sxs-lookup"><span data-stu-id="71f6e-142">Bulk-copy functions that process data (for example, [bcp_exec](bcp-exec.md)) parse data rows expecting the length of the data in the data file to be identical to the length of the data specified in the database table, view, or SELECT column list.</span></span> <span data-ttu-id="71f6e-143">Por exemplo, os dados de uma coluna de banco de dado definida como **Char (13)** devem ser representados por 13 caracteres para cada linha de dados no arquivo.</span><span class="sxs-lookup"><span data-stu-id="71f6e-143">For example, data for a database column defined as **char(13)** must be represented by 13 characters for each row of data in the file.</span></span> <span data-ttu-id="71f6e-144">Os dados de comprimento fixo podem ser prefixados com um indicador nulo se a coluna do banco de dados permitir valores nulos.</span><span class="sxs-lookup"><span data-stu-id="71f6e-144">Fixed-length data can be prefixed with a null indicator if the database column allows null values.</span></span>  
  
-   <span data-ttu-id="71f6e-145">Quando a sequência de bytes de terminador é definida, o comprimento da sequência de bytes de terminador é definido como 0.</span><span class="sxs-lookup"><span data-stu-id="71f6e-145">When terminator-byte sequence is defined, the length of the terminator-byte sequence is set to 0.</span></span>  
  
-   <span data-ttu-id="71f6e-146">Ao copiar para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o arquivo de dados deve ter dados em cada coluna na tabela do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71f6e-146">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data file must have data for each column in the database table.</span></span> <span data-ttu-id="71f6e-147">Ao copiar do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], os dados de todas as colunas na tabela, exibição ou conjunto de resultados de SELECT do banco de dados são copiados para o arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="71f6e-147">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data from all columns in the database table, view, or SELECT result set are copied to the data file.</span></span>  
  
-   <span data-ttu-id="71f6e-148">Ao copiar para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a posição ordinal de uma coluna no arquivo de dados deve ser idêntica à posição ordinal da coluna na tabela do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71f6e-148">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the ordinal position of a column in the data file must be identical to the ordinal position of the column in the database table.</span></span> <span data-ttu-id="71f6e-149">Ao copiar de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , **bcp_exec** coloca os dados com base na posição ordinal da coluna na tabela do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71f6e-149">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp_exec** places data based on the ordinal position of the column in the database table.</span></span>  
  
-   <span data-ttu-id="71f6e-150">Se um tipo de dado de banco de dados for variável em comprimento (por exemplo, **varbinary (22)**) ou se uma coluna Database puder conter valores nulos, os dados no arquivo de dados serão prefixados por um indicador de comprimento/nulo.</span><span class="sxs-lookup"><span data-stu-id="71f6e-150">If a database data type is variable in length (for example, **varbinary(22)**) or if a database column can contain null values, data in the data file is prefixed by a length/null indicator.</span></span> <span data-ttu-id="71f6e-151">A largura do indicador varia dependendo do tipo de dados e da versão da cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="71f6e-151">The width of the indicator varies based on the data type and version of bulk copy.</span></span>  
  
 <span data-ttu-id="71f6e-152">Para alterar os valores de formato de dados especificados para um arquivo de dados, chame [bcp_columns](bcp-columns.md) e [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="71f6e-152">To change data format values specified for a data file, call [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
 <span data-ttu-id="71f6e-153">As cópias em massa para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem ser otimizadas para tabelas que não contêm índices, definindo o modelo de recuperação de banco de dados como SIMPLE ou BULK_LOGGED.</span><span class="sxs-lookup"><span data-stu-id="71f6e-153">Bulk copies to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be optimized for tables that do not contain indexes by setting the database recovery model to SIMPLE or BULK_LOGGED.</span></span> <span data-ttu-id="71f6e-154">Para obter mais informações, consulte [pré-requisitos para log mínimo em importação em massa](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) e [alterar banco de dados](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="71f6e-154">For more information, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) and [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="71f6e-155">Se nenhum arquivo de dados for usado, você deverá chamar [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) para especificar o formato e o local na memória dos dados fsor cada coluna e, em seguida, copiar as linhas de dados para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [bcp_sendrow](bcp-sendrow.md)usando.</span><span class="sxs-lookup"><span data-stu-id="71f6e-155">If no data file is used, you must call [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) to specify the format and location in memory of the data fsor each column, then copy data rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71f6e-156">Exemplo</span><span class="sxs-lookup"><span data-stu-id="71f6e-156">Example</span></span>  
 <span data-ttu-id="71f6e-157">Este exemplo mostra como usar a função ODBC bcp_init com um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="71f6e-157">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
 <span data-ttu-id="71f6e-158">Antes de compilar e executar o código C++, você precisa fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="71f6e-158">Before you compile and run the C++ code, you need to do the following:</span></span>  
  
-   <span data-ttu-id="71f6e-159">Crie uma fonte de dados ODBC chamada Teste.</span><span class="sxs-lookup"><span data-stu-id="71f6e-159">Create an ODBC data source called Test.</span></span> <span data-ttu-id="71f6e-160">Você pode associar essa fonte de dados a qualquer banco de dados.</span><span class="sxs-lookup"><span data-stu-id="71f6e-160">You can associate this data source with any database.</span></span>  
  
-   <span data-ttu-id="71f6e-161">Execute o seguinte [!INCLUDE[tsql](../../includes/tsql-md.md)] no banco de dados:</span><span class="sxs-lookup"><span data-stu-id="71f6e-161">Run the following [!INCLUDE[tsql](../../includes/tsql-md.md)] on the database:</span></span>  
  
    ```  
    CREATE TABLE BCPDate (cola int, colb datetime);  
    ```  
  
-   <span data-ttu-id="71f6e-162">No diretório onde você executará o aplicativo, adicione um arquivo chamado Bcpfmt.fmt e adicione isto ao arquivo:</span><span class="sxs-lookup"><span data-stu-id="71f6e-162">In the directory where you will run the application, add a file called Bcpfmt.fmt, and add this to the file:</span></span>  
  
    ```  
    8.0  
    2  
    1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
    2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
    ```  
  
-   <span data-ttu-id="71f6e-163">No diretório onde você executará o aplicativo, adicione um arquivo chamado Bcpodbc.bcp e adicione isto ao arquivo:</span><span class="sxs-lookup"><span data-stu-id="71f6e-163">In the directory where you will run the application, add a file called Bcpodbc.bcp, and add this to the file:</span></span>  
  
    ```  
    1  
    2  
    ```  
  
 <span data-ttu-id="71f6e-164">Agora você está pronto para compilar e executar o código C++.</span><span class="sxs-lookup"><span data-stu-id="71f6e-164">Now you are ready to compile and run the C++ code.</span></span>  
  
```  
// compile with: odbc32.lib sqlncli11.lib  
#include <stdio.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;   
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
   SDWORD cRows;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle, set BCP mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security. Create SQL Server DSN using Windows NT authentication.  
   retcode = SQLConnect(hdbc1, (UCHAR*)"Test", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Read the format file.  
   retcode = bcp_readfmt(hdbc1, "BCPFMT.fmt");  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_readfmt(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied in = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="71f6e-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71f6e-165">See Also</span></span>  
 [<span data-ttu-id="71f6e-166">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="71f6e-166">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
