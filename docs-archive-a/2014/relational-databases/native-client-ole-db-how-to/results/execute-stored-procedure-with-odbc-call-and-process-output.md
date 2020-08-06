---
title: Executar um procedimento armazenado (usando sintaxe de chamada ODBC) e processar códigos de retorno e parâmetros de saída (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC]
- ODBC CALL syntax
ms.assetid: 921a24d1-ea09-4a3c-980a-4dcbd0a43d31
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d862c2feed8a8f3678c0b9150021bee56dbeb0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679351"
---
# <a name="execute-a-stored-procedure-using-odbc-call-syntax-and-process-return-codes-and-output-parameters-ole-db"></a><span data-ttu-id="48117-102">Executar um procedimento armazenado (usando sintaxe ODBC CALL) e processar códigos de retorno e parâmetros de saída (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="48117-102">Execute a Stored Procedure (Using ODBC CALL Syntax) and Process Return Codes and Output Parameters (OLE DB)</span></span>
  <span data-ttu-id="48117-103">Os procedimentos armazenados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] podem ter códigos de retorno e parâmetros de saída inteiros.</span><span class="sxs-lookup"><span data-stu-id="48117-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stored procedures can have integer return codes and output parameters.</span></span> <span data-ttu-id="48117-104">Os códigos de retorno e os parâmetros de saída são enviados no último pacote do servidor e, portanto, não estão disponíveis para o aplicativo enquanto o conjunto de linhas não é completamente liberado.</span><span class="sxs-lookup"><span data-stu-id="48117-104">The return codes and output parameters are sent in the last packet from the server and are therefore not available to the application until the rowset is completely released.</span></span> <span data-ttu-id="48117-105">Se o comando retornar vários resultados, os dados dos parâmetros de saída estarão disponíveis quando `IMultipleResults::GetResult` retornar DB_S_NORESULT ou a interface `IMultipleResults` for completamente liberada, o que ocorrer primeiro.</span><span class="sxs-lookup"><span data-stu-id="48117-105">If the command returns multiple results, output parameter data is available when `IMultipleResults::GetResult` returns DB_S_NORESULT or the `IMultipleResults` interface is completely released, whichever occurs first.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="48117-106">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="48117-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="48117-107">Se a Autenticação do Windows não estiver disponível, solicite aos usuários que digitem suas credenciais em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="48117-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="48117-108">Evite armazenar as credenciais em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="48117-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="48117-109">Se você precisar manter as credenciais, deverá criptografá-las com a [API de criptografia do Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="48117-109">If you must persist credentials, you should encrypt them with the [Win32 Crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-process-return-codes-and-output-parameters"></a><span data-ttu-id="48117-110">Para processar códigos de retorno e parâmetros de saída</span><span class="sxs-lookup"><span data-stu-id="48117-110">To process return codes and output parameters</span></span>  
  
1.  <span data-ttu-id="48117-111">Construa uma instrução SQL que use a sequência de escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="48117-111">Construct an SQL statement that uses the ODBC CALL escape sequence.</span></span> <span data-ttu-id="48117-112">A instrução deve usar marcadores de parâmetro para cada entrada/saída e parâmetro de saída e também para o valor retornado do procedimento (se houver).</span><span class="sxs-lookup"><span data-stu-id="48117-112">The statement should use parameter markers for each input/output and output parameter, and for the procedure return value (if any).</span></span> <span data-ttu-id="48117-113">Para parâmetros de entrada, você pode usar os marcadores de parâmetro ou codificar os valores.</span><span class="sxs-lookup"><span data-stu-id="48117-113">For input parameters, you can use the parameter markers, or hard code the values.</span></span>  
  
2.  <span data-ttu-id="48117-114">Crie um conjunto de associações (um para cada criador de parâmetro) usando uma matriz de estrutura DBBINDING.</span><span class="sxs-lookup"><span data-stu-id="48117-114">Create a set of bindings (one for each parameter maker) by using an array of DBBINDING structure.</span></span>  
  
3.  <span data-ttu-id="48117-115">Crie um acessador para os parâmetros definidos usando o método `IAccessor::CreateAccessor`.</span><span class="sxs-lookup"><span data-stu-id="48117-115">Create an accessor for the defined parameters by using the `IAccessor::CreateAccessor` method.</span></span> <span data-ttu-id="48117-116">O `CreateAccessor` cria um acessador a partir de um conjunto de associações.</span><span class="sxs-lookup"><span data-stu-id="48117-116">`CreateAccessor` creates an accessor from a set of bindings.</span></span>  
  
4.  <span data-ttu-id="48117-117">Preencha a estrutura DBPARAMS.</span><span class="sxs-lookup"><span data-stu-id="48117-117">Fill in the DBPARAMS structure.</span></span>  
  
5.  <span data-ttu-id="48117-118">Chame o comando `Execute` (neste caso, uma chamada para um procedimento armazenado).</span><span class="sxs-lookup"><span data-stu-id="48117-118">Call the `Execute` command (in this case, a call to a stored procedure).</span></span>  
  
6.  <span data-ttu-id="48117-119">Processe o conjunto de linhas e libere-o usando o método `IRowset::Release`.</span><span class="sxs-lookup"><span data-stu-id="48117-119">Process the rowset and release it by using the `IRowset::Release` method.</span></span>  
  
7.  <span data-ttu-id="48117-120">Processe os valores de código de retorno e de parâmetro de saída recebidos do procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="48117-120">Process the return code and output parameter values received from the stored procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48117-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="48117-121">Example</span></span>  
 <span data-ttu-id="48117-122">O exemplo mostra o processamento de um conjunto de linhas, de um código de retorno e de um parâmetro de saída.</span><span class="sxs-lookup"><span data-stu-id="48117-122">The example shows processing a rowset, a return code, and an output parameter.</span></span> <span data-ttu-id="48117-123">Conjuntos de resultados não são processados.</span><span class="sxs-lookup"><span data-stu-id="48117-123">Result sets are not processed.</span></span> <span data-ttu-id="48117-124">Este exemplo não tem suporte em IA64.</span><span class="sxs-lookup"><span data-stu-id="48117-124">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="48117-125">Este exemplo exige o banco de dados de exemplo AdventureWorks, que pode ser baixado na home page de [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) (em inglês).</span><span class="sxs-lookup"><span data-stu-id="48117-125">This sample requires the AdventureWorks sample database, which you can download from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.</span></span>  
  
 <span data-ttu-id="48117-126">Execute a primeira listagem de código ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) para criar o procedimento armazenado usado pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="48117-126">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the stored procedure used by the application.</span></span>  
  
 <span data-ttu-id="48117-127">Compile com ole32.lib oleaut32.lib e execute a segunda listagem de código (C++).</span><span class="sxs-lookup"><span data-stu-id="48117-127">Compile with ole32.lib oleaut32.lib and execute the second (C++) code listing.</span></span> <span data-ttu-id="48117-128">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="48117-128">This application connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="48117-129">Em alguns sistemas operacionais Windows, será necessário alterar (localhost) ou (local) para o nome de sua instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48117-129">On some Windows operating systems, you will need to change (localhost) or (local) to the name of your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="48117-130">Para se conectar a uma instância nomeada, altere a cadeia de conexão de L"(local)" para L"(local)\\\name", em que name é a instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="48117-130">To connect to a named instance, change the connection string from L"(local)" to L"(local)\\\name" , where name is the named instance.</span></span> <span data-ttu-id="48117-131">Por padrão, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Express é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="48117-131">By default, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Express installs to a named instance.</span></span> <span data-ttu-id="48117-132">Verifique se a variável de ambiente INCLUDE inclui o diretório que contém sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="48117-132">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
 <span data-ttu-id="48117-133">Execute a terceira listagem de código ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) para excluir o procedimento armazenado usado pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="48117-133">Execute the third ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the stored procedure used by the application.</span></span>  
  
```  
USE AdventureWorks  
if exists (SELECT * FROM sys.objects WHERE object_id = OBJECT_ID(N'[myProc]'))  
   DROP PROCEDURE myProc  
GO  
  
CREATE PROCEDURE myProc   
    @inparam nvarchar(5),,  
    @outparam int OUTPUT  
  
AS  
SELECT Color, ListPrice   
FROM Production.Product WHERE Size > @inparam  
SELECT @outparam = 100  
  
IF  (@outparam > 0)  
    RETURN 999  
ELSE  
    RETURN 888  
GO  
```  
  
```  
// compile with: ole32.lib oleaut32.lib  
void InitializeAndEstablishConnection();  
  
#define UNICODE  
#define DBINITCONSTANTS  
#define INITGUID  
#define OLEDBVER 0x0250   // to include correct interfaces  
  
#include <windows.h>  
#include <stdio.h>  
#include <stddef.h>  
#include <iostream>  
#include <oledb.h>  
#include <oledberr.h>  
#include <SQLNCLI.h>  
  
using namespace std;  
  
IDBInitialize* pIDBInitialize = NULL;  
IDBCreateSession* pIDBCreateSession = NULL;  
IDBCreateCommand* pIDBCreateCommand = NULL;  
ICommandText* pICommandText = NULL;  
  
IRowset* pIRowset = NULL;  
ICommandWithParameters* pICommandWithParams = NULL;  
IAccessor* pIAccessor = NULL;  
IDBProperties* pIDBProperties = NULL;  
  
WCHAR* pStringsBuffer;  
DBBINDING* pBindings;  
const ULONG nInitProps = 4;  
DBPROP InitProperties[nInitProps];  
  
const ULONG nPropSet = 1;  
DBPROPSET rgInitPropSet[nPropSet];  
HRESULT hr;  
HACCESSOR hAccessor;  
  
const ULONG nParams = 3;   // Number of parameters in the command  
DBPARAMBINDINFO ParamBindInfo[nParams];  
ULONG i;  
ULONG cbColOffset = 0;  
  
ULONG ParamOrdinals[nParams];  
DBROWCOUNT cNumRows = 0;  
DBPARAMS Params;  
  
// Declare an array of DBBINDING structures, one for each parameter in the command.  
DBBINDING acDBBinding[nParams];  
DBBINDSTATUS acDBBindStatus[nParams];  
  
// The following buffer is used to store parameter values.  
typedef struct tagSPROCPARAMS {  
   long lReturnValue;  
   long outParam;  
   long inParam;  
} SPROCPARAMS;  
  
int main() {  
   // The command to execute.  
   WCHAR* wCmdString = L"{? = call myProc(?,?)}";  
  
   SPROCPARAMS sprocparams = {0,0,14};  
  
   // All the initialization activities in a separate function.  
   InitializeAndEstablishConnection();  
  
   // Create a new activity from the data source object.  
   if ( FAILED(pIDBInitialize->QueryInterface( IID_IDBCreateSession,   
      (void**) &pIDBCreateSession))) {  
         cout << "Failed to access IDBCreateSession interface.\n";  
         goto EXIT;  
   }  
   if (FAILED(pIDBCreateSession->CreateSession( NULL, IID_IDBCreateCommand,   
      (IUnknown**) &pIDBCreateCommand))) {  
         cout << "pIDBCreateSession->CreateSession failed.\n";  
      goto EXIT;  
   }  
  
   // Create a Command object.  
   if (FAILED(pIDBCreateCommand->CreateCommand(NULL, IID_ICommandText,   
      (IUnknown**) &pICommandText))) {  
         cout << "Failed to access ICommand interface.\n";  
         goto EXIT;  
   }  
  
   // Set the command text.  
   if (FAILED(pICommandText->SetCommandText(DBGUID_DBSQL, wCmdString))) {  
      cout << "Failed to set command text.\n";  
      goto EXIT;  
   }  
   // No need to describe command parameters (parameter name, data type  
   // etc) in DBPARAMBINDINFO structure and then SetParameterInfo(). The  
   // provider obtains this information by calling appropriate helper  
   // function.  
  
   // Describe the consumer buffer by filling in the array of DBBINDING structures.    
   // Each binding associates a single parameter to the consumer's buffer.  
   for ( i = 0 ; i < nParams ; i++ ) {  
      acDBBinding[i].obLength = 0;  
      acDBBinding[i].obStatus = 0;  
      acDBBinding[i].pTypeInfo = NULL;  
      acDBBinding[i].pObject = NULL;  
      acDBBinding[i].pBindExt = NULL;  
      acDBBinding[i].dwPart = DBPART_VALUE;  
      acDBBinding[i].dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
      acDBBinding[i].dwFlags = 0;  
      acDBBinding[i].bScale = 0;  
   }   // end for  
  
   acDBBinding[0].iOrdinal = 1;  
   acDBBinding[0].obValue = offsetof(SPROCPARAMS, lReturnValue);  
   acDBBinding[0].eParamIO = DBPARAMIO_OUTPUT;  
   acDBBinding[0].cbMaxLen = sizeof(long);  
   acDBBinding[0].wType = DBTYPE_I4;  
   acDBBinding[0].bPrecision = 11;  
  
   acDBBinding[1].iOrdinal = 2;  
   acDBBinding[1].obValue = offsetof(SPROCPARAMS, inParam);  
   acDBBinding[1].eParamIO = DBPARAMIO_INPUT;  
   acDBBinding[1].cbMaxLen = sizeof(long);  
   acDBBinding[1].wType = DBTYPE_I4;  
   acDBBinding[1].bPrecision = 11;  
  
   acDBBinding[2].iOrdinal = 3;  
   acDBBinding[2].obValue = offsetof(SPROCPARAMS, outParam);  
   acDBBinding[2].eParamIO = DBPARAMIO_OUTPUT;  
   acDBBinding[2].cbMaxLen = sizeof(long);  
   acDBBinding[2].wType = DBTYPE_I4;  
   acDBBinding[2].bPrecision = 11;  
  
   // Create an accessor from the above set of bindings.  
   hr = pICommandText->QueryInterface( IID_IAccessor, (void**)&pIAccessor);  
   if (FAILED(hr))  
      cout << "Failed to get IAccessor interface.\n";  
  
   hr = pIAccessor->CreateAccessor( DBACCESSOR_PARAMETERDATA,   
                                    nParams,         
                                    acDBBinding,   
                                    sizeof(SPROCPARAMS),   
                                    &hAccessor,  
                                    acDBBindStatus);  
   if (FAILED(hr))  
      cout << "Failed to create accessor for the defined parameters.\n";  
  
   // Fill in DBPARAMS structure for the command execution. This structure   
   // specifies the parameter values in the command and is then passed to Execute.  
   Params.pData = &sprocparams;  
   Params.cParamSets = 1;  
   Params.hAccessor = hAccessor;  
  
   // Execute the command.  
   if ( FAILED(hr = pICommandText->Execute( NULL,   
                                            IID_IRowset,   
                                            &Params,   
                                            &cNumRows,   
                                            (IUnknown **) &pIRowset))) {  
      cout << "Failed to execute command.\n";  
      goto EXIT;  
   }  
  
   printf("After command execution but before rowset processing.\n\n");  
   printf("  Return value = %d\n", sprocparams.lReturnValue);  
   printf("  Output parameter value = %d\n", sprocparams.outParam);  
   printf("  These are the same default values set in the application.\n\n\n");  
  
   // Result set is not important in this example; release it without processing.  
   pIRowset->Release();  
  
   printf("After processing the result set...\n");  
   printf("  Return value = %d\n", sprocparams.lReturnValue);  
   printf("  Output parameter value = %d\n\n", sprocparams.outParam);  
  
   // Release memory.  
   pIAccessor->ReleaseAccessor(hAccessor, NULL);  
   pIAccessor->Release();  
   pICommandText->Release();  
   pIDBCreateCommand->Release();  
   pIDBCreateSession->Release();      
   if (FAILED(pIDBInitialize->Uninitialize()))  
      // Uninitialize is not required, but it fails if an interface  
      // has not been released.  This can be used for debugging.  
      cout << "Problem uninitializing.\n";  
  
   pIDBInitialize->Release();  
  
   CoUninitialize();  
   return 0;  
  
EXIT:  
   if (pIAccessor != NULL)  
      pIAccessor->Release();  
   if (pICommandText != NULL)  
      pICommandText->Release();  
   if (pIDBCreateCommand != NULL)  
      pIDBCreateCommand->Release();  
   if (pIDBCreateSession != NULL)  
      pIDBCreateSession->Release();  
   if (pIDBInitialize != NULL)  
      if (FAILED(pIDBInitialize->Uninitialize()))  
         // Uninitialize is not required, but it fails if an  
         // interface has not been released.  This can be used for debugging.  
         cout << "Problem in uninitializing.\n";  
      pIDBInitialize->Release();  
  
   CoUninitialize();  
};  
  
void InitializeAndEstablishConnection() {      
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQL Server Native Client OLE DB provider.      
   hr = CoCreateInstance( CLSID_SQLNCLI11,   
                          NULL,   
                          CLSCTX_INPROC_SERVER,  
                          IID_IDBInitialize,   
                          (void **) &pIDBInitialize);  
   if (FAILED(hr))  
      cout << "Failed in CoCreateInstance().\n";  
  
   // Initialize the property values needed to establish the connection.  
   for ( i = 0 ; i < nInitProps ; i++ )  
      VariantInit(&InitProperties[i].vValue);  
  
   // Specify server name.  
   InitProperties[0].dwPropertyID = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt = VT_BSTR;  
  
   // Replace "MySqlServer" with proper value.  
   InitProperties[0].vValue.bstrVal = SysAllocString(L"(local)");  
   InitProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid = DB_NULLID;  
  
   // Specify database name.  
   InitProperties[1].dwPropertyID = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt = VT_BSTR;  
   InitProperties[1].vValue.bstrVal = SysAllocString(L"AdventureWorks");  
   InitProperties[1].dwOptions = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid = DB_NULLID;  
  
   InitProperties[2].dwPropertyID = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt = VT_BSTR;  
   InitProperties[2].vValue.bstrVal = SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid = DB_NULLID;  
  
   // Now that properties are set, construct the DBPROPSET structure  
   // (rgInitPropSet).  The DBPROPSET structure is used to pass an array  
   // of DBPROP structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties = 4;  
   rgInitPropSet[0].rgProperties = InitProperties;  
  
   // Set initialization properties.  
   hr = pIDBInitialize->QueryInterface(IID_IDBProperties, (void **)&pIDBProperties);  
   if (FAILED(hr))  
      cout << "Failed to obtain IDBProperties interface.\n";  
  
   hr = pIDBProperties->SetProperties(nPropSet, rgInitPropSet);  
   if (FAILED(hr))  
      cout << "Failed to set initialization properties.\n";  
  
   pIDBProperties->Release();  
  
   // Now establish a connection to the data source.  
   if (FAILED(pIDBInitialize->Initialize()))  
      cout << "Problem in initializing.\n";  
}  
```  
  
```  
USE AdventureWorks  
DROP PROCEDURE myProc  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="48117-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48117-134">See Also</span></span>  
 [<span data-ttu-id="48117-135">Tópicos de instruções sobre o processamento de resultados &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="48117-135">Processing Results How-to Topics &#40;OLE DB&#41;</span></span>](processing-results-how-to-topics-ole-db.md)  
  
  
