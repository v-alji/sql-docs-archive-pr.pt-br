---
title: bcp_setbulkmode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bcp_setbulkmode function
ms.assetid: de56f206-1f7e-4c03-bf22-da9c7f9f4433
author: rothja
ms.author: jroth
ms.openlocfilehash: 1b7a68dfb3c868422b2e01cccf511a623d3afe52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575104"
---
# <a name="bcp_setbulkmode"></a><span data-ttu-id="cdc81-102">bcp_setbulkmode</span><span class="sxs-lookup"><span data-stu-id="cdc81-102">bcp_setbulkmode</span></span>
  <span data-ttu-id="cdc81-103">bcp_setbulkmode permite especificar o formato de coluna em uma operação de cópia em massa, definindo todos os atributos de coluna em uma única chamada de função.</span><span class="sxs-lookup"><span data-stu-id="cdc81-103">bcp_setbulkmode lets you specify the column format in a bulk copy operation, setting all the column attributes in a single function call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdc81-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cdc81-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_setbulkmode (  
   HDBC   
hdbc  
,  
   INT   
property  
,  
   void *   
pField  
,  
   INT   
cbField  
,  
   void *   
pRow  
,  
   INT   
cbRow  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cdc81-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cdc81-105">Arguments</span></span>  
 <span data-ttu-id="cdc81-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="cdc81-106">*hdbc*</span></span>  
 <span data-ttu-id="cdc81-107">O identificador de conexão ODBC habilitado para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="cdc81-107">The bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="cdc81-108">*property*</span><span class="sxs-lookup"><span data-stu-id="cdc81-108">*property*</span></span>  
 <span data-ttu-id="cdc81-109">Uma constante do tipo BYTE.</span><span class="sxs-lookup"><span data-stu-id="cdc81-109">A constant of type BYTE.</span></span> <span data-ttu-id="cdc81-110">Consulte a tabela na seção Comentários para obter a lista das constantes.</span><span class="sxs-lookup"><span data-stu-id="cdc81-110">See the table in the Remarks section for a list of the constants.</span></span>  
  
 <span data-ttu-id="cdc81-111">*pField*</span><span class="sxs-lookup"><span data-stu-id="cdc81-111">*pField*</span></span>  
 <span data-ttu-id="cdc81-112">O ponteiro para o valor de terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="cdc81-112">The pointer to the field terminator value.</span></span>  
  
 <span data-ttu-id="cdc81-113">*cbField*</span><span class="sxs-lookup"><span data-stu-id="cdc81-113">*cbField*</span></span>  
 <span data-ttu-id="cdc81-114">O comprimento (em bytes) do valor de terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="cdc81-114">The length (in bytes) of the field terminator value.</span></span>  
  
 <span data-ttu-id="cdc81-115">*pRow*</span><span class="sxs-lookup"><span data-stu-id="cdc81-115">*pRow*</span></span>  
 <span data-ttu-id="cdc81-116">O ponteiro para o valor de terminador de linha.</span><span class="sxs-lookup"><span data-stu-id="cdc81-116">The pointer to the row terminator value.</span></span>  
  
 <span data-ttu-id="cdc81-117">*cbRow*</span><span class="sxs-lookup"><span data-stu-id="cdc81-117">*cbRow*</span></span>  
 <span data-ttu-id="cdc81-118">O comprimento (em bytes) do valor de terminador de linha.</span><span class="sxs-lookup"><span data-stu-id="cdc81-118">The length in bytes of the row terminator value.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cdc81-119">Retornos</span><span class="sxs-lookup"><span data-stu-id="cdc81-119">Returns</span></span>  
 <span data-ttu-id="cdc81-120">SUCCEED ou FAIL</span><span class="sxs-lookup"><span data-stu-id="cdc81-120">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdc81-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="cdc81-121">Remarks</span></span>  
 <span data-ttu-id="cdc81-122">bcp_setbulkmode pode ser usada para cópia em massa de uma consulta ou de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="cdc81-122">bcp_setbulkmode can be used to bulk copy out of either a query or a table.</span></span> <span data-ttu-id="cdc81-123">Quando bcp_setbulkmode é usado para copiar em massa uma instrução de consulta, ela deve ser chamada antes de chamar bcp_control com BCP_HINT.</span><span class="sxs-lookup"><span data-stu-id="cdc81-123">When bcp_setbulkmode is used to bulk copy out a query statement, it must be called before calling bcp_control with BCP_HINT.</span></span>  
  
 <span data-ttu-id="cdc81-124">bcp_setbulkmode é uma alternativa ao uso de [bcp_setcolfmt](bcp-setcolfmt.md) e [bcp_columns](bcp-columns.md), que permite apenas especificar o formato de uma coluna por chamada de função.</span><span class="sxs-lookup"><span data-stu-id="cdc81-124">bcp_setbulkmode is an alternative to using [bcp_setcolfmt](bcp-setcolfmt.md) and [bcp_columns](bcp-columns.md), which only let you specify the format of one column per function call.</span></span>  
  
 <span data-ttu-id="cdc81-125">A tabela a seguir lista as constantes do parâmetro *property* .</span><span class="sxs-lookup"><span data-stu-id="cdc81-125">The following table lists the constants for the *property* parameter.</span></span>  
  
|<span data-ttu-id="cdc81-126">Propriedade</span><span class="sxs-lookup"><span data-stu-id="cdc81-126">Property</span></span>|<span data-ttu-id="cdc81-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="cdc81-127">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="cdc81-128">BCP_OUT_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="cdc81-128">BCP_OUT_CHARACTER_MODE</span></span>|<span data-ttu-id="cdc81-129">Especifica o modo de saída de caractere.</span><span class="sxs-lookup"><span data-stu-id="cdc81-129">Specifies character output mode.</span></span><br /><br /> <span data-ttu-id="cdc81-130">Corresponde à opção-c em BCP.EXE e a bcp_setcolfmt com a `BCP_FMT_TYPE` propriedade definida como `SQLCHARACTER` .</span><span class="sxs-lookup"><span data-stu-id="cdc81-130">Corresponds to the -c option in BCP.EXE, and to bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLCHARACTER`.</span></span>|  
|<span data-ttu-id="cdc81-131">BCP_OUT_WIDE_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="cdc81-131">BCP_OUT_WIDE_CHARACTER_MODE</span></span>|<span data-ttu-id="cdc81-132">Especifica o modo de saída de Unicode.</span><span class="sxs-lookup"><span data-stu-id="cdc81-132">Specifies Unicode output mode.</span></span><br /><br /> <span data-ttu-id="cdc81-133">Corresponde à opção-w em BCP.EXE e bcp_setcolfmt com a `BCP_FMT_TYPE` propriedade definida como `SQLNCHAR` .</span><span class="sxs-lookup"><span data-stu-id="cdc81-133">Corresponds to the -w option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLNCHAR`.</span></span>|  
|<span data-ttu-id="cdc81-134">BCP_OUT_NATIVE_TEXT_MODE</span><span class="sxs-lookup"><span data-stu-id="cdc81-134">BCP_OUT_NATIVE_TEXT_MODE</span></span>|<span data-ttu-id="cdc81-135">Especifica tipos nativos para tipos de não caracteres e Unicode para tipos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="cdc81-135">Specifies native types for non-character types and Unicode for character types.</span></span><br /><br /> <span data-ttu-id="cdc81-136">Corresponde à opção-N em BCP.EXE e bcp_setcolfmt com a `BCP_FMT_TYPE` propriedade definida como `SQLNCHAR` se o tipo de coluna for uma cadeia de caracteres (padrão se não for uma cadeia de caracteres).</span><span class="sxs-lookup"><span data-stu-id="cdc81-136">Corresponds to the -N option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLNCHAR` if the column type is a string (default if not a string).</span></span>|  
|<span data-ttu-id="cdc81-137">BCP_OUT_NATIVE_MODE</span><span class="sxs-lookup"><span data-stu-id="cdc81-137">BCP_OUT_NATIVE_MODE</span></span>|<span data-ttu-id="cdc81-138">Especifica tipos de bancos de dados nativos.</span><span class="sxs-lookup"><span data-stu-id="cdc81-138">Specifies native database types.</span></span><br /><br /> <span data-ttu-id="cdc81-139">Corresponde à opção-n em BCP.EXE e bcp_setcolfmt com `BCP_FMT_TYPE` a propriedade definida como o padrão.</span><span class="sxs-lookup"><span data-stu-id="cdc81-139">Corresponds to the -n option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to the default.</span></span>|  
  
 <span data-ttu-id="cdc81-140">Você não deve usar bcp_setbulkmode com uma sequência de chamadas de função que inclua bcp_setcolfmt, bcp_control e bcp_readfmt.</span><span class="sxs-lookup"><span data-stu-id="cdc81-140">You should not use bcp_setbulkmode with a sequence of function calls that includes bcp_setcolfmt, bcp_control, and bcp_readfmt.</span></span> <span data-ttu-id="cdc81-141">Por exemplo, você não deve chamar bcp_control (BCPTEXTFILE) e bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="cdc81-141">For example, you should not call bcp_control(BCPTEXTFILE) and bcp_setbulkmode.</span></span>  
  
 <span data-ttu-id="cdc81-142">Você pode chamar bcp_control e bcp_setbulkmode para bcp_control opções que não entram em conflito com bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="cdc81-142">You can call bcp_control and bcp_setbulkmode for bcp_control options that do not conflict with bcp_setbulkmode.</span></span> <span data-ttu-id="cdc81-143">Por exemplo, você pode chamar bcp_control (BCPFIRST) e bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="cdc81-143">For example, you can call bcp_control(BCPFIRST) and bcp_setbulkmode.</span></span>  
  
 <span data-ttu-id="cdc81-144">Se você tentar chamar bcp_setbulkmode com uma sequência de chamadas de função que inclui bcp_setcolfmt, bcp_control e bcp_readfmt, uma das chamadas de função retornará uma falha de erro de sequência.</span><span class="sxs-lookup"><span data-stu-id="cdc81-144">If you attempt to call bcp_setbulkmode with a sequence of function calls that includes bcp_setcolfmt, bcp_control, and bcp_readfmt, one of the function calls will return a sequence error failure.</span></span> <span data-ttu-id="cdc81-145">Se você optar por corrigir a falha, Chame bcp_init para redefinir todas as configurações e recomeçar.</span><span class="sxs-lookup"><span data-stu-id="cdc81-145">If you choose to correct the failure, call bcp_init to reset all the settings and start over.</span></span>  
  
 <span data-ttu-id="cdc81-146">A tabela a seguir apresenta alguns exemplos de chamadas de funções que resultam em um erro de sequência de função:</span><span class="sxs-lookup"><span data-stu-id="cdc81-146">The following table presents some examples of function calls that result in a function sequence error:</span></span>  
  
 <span data-ttu-id="cdc81-147">Sequência de chamada</span><span class="sxs-lookup"><span data-stu-id="cdc81-147">Call sequence</span></span>  
  
```  
bcp_init("table", DB_IN);  
bcp_setbulkmode();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_setbulkmode();  
bcp_readfmt();  
```  
  
```  
bcp_init(NULL, DB_OUT);  
bcp_control(BCPHINTS, "select ...");  
bcp_setbulkmode();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_setbulkmode();  
bcp_setcolfmt();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_readfmt();  
bcp_setcolfmt();  
```  
  
```  
bcp_init(NULL, DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_setbulkmode();  
bcp_control(BCPHINTS, "select ...");  
bcp_readfmt();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_columns();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_setcolfmt();  
```  
  
## <a name="example"></a><span data-ttu-id="cdc81-148">Exemplo</span><span class="sxs-lookup"><span data-stu-id="cdc81-148">Example</span></span>  
 <span data-ttu-id="cdc81-149">O exemplo a seguir cria quatro arquivos usando diferentes configurações de bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="cdc81-149">The following sample creates four files using different settings of bcp_setbulkmode.</span></span>  
  
```  
// compile with: sqlncli11.lib odbc32.lib  
  
#include <windows.h>  
#include <stdio.h>  
#include <tchar.h>  
#include <sqlext.h>  
#include "sqlncli.h"  
  
// Global variables  
SQLHENV g_hEnv = NULL;  
SQLHDBC g_hDbc = NULL;  
  
void ODBCCleanUp() {  
   if (g_hDbc) {  
      SQLDisconnect(g_hDbc);  
      SQLFreeHandle(SQL_HANDLE_DBC, g_hDbc);  
      g_hDbc = NULL;  
   }  
   if (g_hEnv) {  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      g_hEnv = NULL;  
   }  
}  
  
BOOL MakeODBCConnection(TCHAR * pszServer) {  
   TCHAR szConnectionString[500];  
   TCHAR szOutConnectionString[500];  
   SQLSMALLINT iLen;  
   SQLRETURN rc;  
  
   _sntprintf_s(szConnectionString, 500, TEXT("DRIVER={SQL Server Native Client 11.0};Server=%s;Trusted_connection=yes;"), pszServer);  
   rc = SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HANDLE,&g_hEnv);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLAllocHandle(SQL_HANDLE_ENV...) failed\n");  
      return false;  
   }  
   rc = SQLSetEnvAttr(g_hEnv,SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, SQL_IS_UINTEGER);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLSetEnvAttr failed\n");  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      return false;  
   }  
   rc = SQLAllocHandle( SQL_HANDLE_DBC, g_hEnv , &g_hDbc);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLAllocHandle(SQL_HANDLE_DBC...) failed\n");  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      return false;  
   }  
   // Enable BCP  
   rc = SQLSetConnectAttr(g_hDbc, SQL_COPT_SS_BCP, (SQLPOINTER)SQL_BCP_ON, SQL_IS_INTEGER);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLSetConnectAttr(.. SQL_COPT_SS_BCP, (SQLPOINTER)SQL_BCP_ON ...) failed\n");  
      ODBCCleanUp();  
      return false;  
   }  
   // connecting ...  
   rc = SQLDriverConnect(g_hDbc,NULL, (SQLTCHAR*)szConnectionString, SQL_NTS, (SQLTCHAR*)szOutConnectionString, 500, &iLen, SQL_DRIVER_NOPROMPT);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLDriverConnect(SQL_HANDLE_DBC...) failed\n");  
      ODBCCleanUp();  
      return false;  
   }  
   return true;  
}  
  
BOOL BCPSetBulkMode(TCHAR * pszServer, TCHAR * pszQureryOut, char BCPType, TCHAR * pszDataFile) {  
   SQLRETURN rc;  
  
   if (!MakeODBCConnection(pszServer))  
      return false;  
   rc = bcp_init(g_hDbc, NULL, pszDataFile, NULL, DB_OUT);   // bcp init for queryout  
   if (SUCCEED != rc) {  
      printf("bcp_init failed\n");  
      ODBCCleanUp();  
      return false;  
   }  
   // setbulkmode  
   char ColTerm[] = "\t";  
   char RowTerm[] = "\r\n";  
   wchar_t wColTerm[] = L"\t";  
   wchar_t wRowTerm[] = L"\r\n";  
   BYTE * pColTerm = NULL;  
   int cbColTerm = NULL;  
   BYTE * pRowTerm = 0;  
   int cbRowTerm = 0;  
   int bulkmode = -1;  
  
   if (BCPType == 'c') {   // bcp -c  
      pColTerm = (BYTE*)ColTerm;  
      pRowTerm = (BYTE*)RowTerm;  
      cbColTerm = 1;  
      cbRowTerm = 2;  
      bulkmode = BCP_OUT_CHARACTER_MODE;  
   }  
   else  
      if (BCPType == 'w') {   // bcp -w   
         pColTerm = (BYTE*)wColTerm;  
         pRowTerm = (BYTE*)wRowTerm;  
         cbColTerm = 2;  
         cbRowTerm = 4;  
         bulkmode = BCP_OUT_WIDE_CHARACTER_MODE;  
      }  
      else  
         if (BCPType == 'n')   // bcp -n  
            bulkmode = BCP_OUT_NATIVE_MODE;  
         else  
            if (BCPType == 'N')   // bcp -n  
               bulkmode = BCP_OUT_NATIVE_TEXT_MODE;  
            else {  
               printf("unknown bcp mode\n");  
               ODBCCleanUp();  
               return false;  
            }  
            rc = bcp_setbulkmode(g_hDbc, bulkmode, pColTerm, cbColTerm, pRowTerm, cbRowTerm);  
            if (SUCCEED != rc) {  
               printf("bcp_setbulkmode failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            // set queryout TSQL statement  
            rc = bcp_control(g_hDbc, BCPHINTS , pszQureryOut);  
            if (SUCCEED != rc) {  
               printf("bcp_control(..BCP_OPTION_HINTS..) failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            // bcp copy  
            DBINT nRowsInserted = 0;  
            rc = bcp_exec(g_hDbc, &nRowsInserted);  
            if (SUCCEED != rc) {  
               printf("bcp_exec failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            printf("bcp done\n");  
            ODBCCleanUp();  
            return true;  
}  
  
int main() {  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -c test', 1,2") , 'c', TEXT("bcpc.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -w test', 1,2") , 'w', TEXT("bcpw.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -c test', 1,2") , 'n', TEXT("bcpn.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -w test', 1,2") , 'N', TEXT("bcp_N.dat"));  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdc81-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cdc81-150">See Also</span></span>  
 [<span data-ttu-id="cdc81-151">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="cdc81-151">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
