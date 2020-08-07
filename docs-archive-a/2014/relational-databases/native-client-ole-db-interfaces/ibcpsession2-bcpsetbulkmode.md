---
title: IBCPSession2::BCPSetBulkMode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BCPSetBulkMode function
ms.assetid: babba19f-e67b-450c-b0e6-523a0f9d23ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 9605ff9b8effde1b4a77ba0d8554c719a8a8d1e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582445"
---
# <a name="ibcpsession2bcpsetbulkmode"></a><span data-ttu-id="e7d2e-102">IBCPSession2::BCPSetBulkMode</span><span class="sxs-lookup"><span data-stu-id="e7d2e-102">IBCPSession2::BCPSetBulkMode</span></span>
  <span data-ttu-id="e7d2e-103">IBCPSession2::BCPSetBulkMode fornece uma alternativa para [IBCPSession::BCPColFmt &#40;OLE DB&#41;](ibcpsession-bcpcolfmt-ole-db.md) para especificar o formato da coluna.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-103">IBCPSession2::BCPSetBulkMode provides an alternative to [IBCPSession::BCPColFmt &#40;OLE DB&#41;](ibcpsession-bcpcolfmt-ole-db.md) for specifying the column format.</span></span> <span data-ttu-id="e7d2e-104">Ao contrário de IBCPSession::BCPColFmt, que define atributos de formato de coluna individuais, IBCPSession2::BCPSetBulkMode define todos os atributos.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-104">Unlike IBCPSession::BCPColFmt, which sets individual column format attributes, IBCPSession2::BCPSetBulkMode sets all attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d2e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e7d2e-105">Syntax</span></span>  
  
```  
  
HRESULT BCPSetBulkMode (  
      int property,  
   void * pField,  
   int cbField,  
   void * pRow,  
   int cbRow  
);  
```  
  
## <a name="arguments"></a><span data-ttu-id="e7d2e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e7d2e-106">Arguments</span></span>  
 <span data-ttu-id="e7d2e-107">*property*</span><span class="sxs-lookup"><span data-stu-id="e7d2e-107">*property*</span></span>  
 <span data-ttu-id="e7d2e-108">Uma constante do tipo BYTE.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-108">A constant of type BYTE.</span></span> <span data-ttu-id="e7d2e-109">Consulte a tabela na seção Comentários para obter a lista das constantes.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-109">See the table in the Remarks section for a list of the constants.</span></span>  
  
 <span data-ttu-id="e7d2e-110">*pField*</span><span class="sxs-lookup"><span data-stu-id="e7d2e-110">*pField*</span></span>  
 <span data-ttu-id="e7d2e-111">O ponteiro para o valor de terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-111">The pointer to the field terminator value.</span></span>  
  
 <span data-ttu-id="e7d2e-112">cbField</span><span class="sxs-lookup"><span data-stu-id="e7d2e-112">cbField</span></span>  
 <span data-ttu-id="e7d2e-113">O comprimento em bytes do valor de terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-113">The length in bytes of the field terminator value.</span></span>  
  
 <span data-ttu-id="e7d2e-114">pRow</span><span class="sxs-lookup"><span data-stu-id="e7d2e-114">pRow</span></span>  
 <span data-ttu-id="e7d2e-115">O ponteiro para o valor de terminador de linha.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-115">The pointer to the row terminator value.</span></span>  
  
 <span data-ttu-id="e7d2e-116">cbRow</span><span class="sxs-lookup"><span data-stu-id="e7d2e-116">cbRow</span></span>  
 <span data-ttu-id="e7d2e-117">O comprimento (em bytes) do valor de terminador de linha.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-117">The length in bytes of the row terminator value.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e7d2e-118">Retornos</span><span class="sxs-lookup"><span data-stu-id="e7d2e-118">Returns</span></span>  
 <span data-ttu-id="e7d2e-119">IBCPSession2::BCPSetBulkMode pode retornar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e7d2e-119">IBCPSession2::BCPSetBulkMode can return one of the following:</span></span>  
  
|||  
|-|-|  
|`S_OK`|<span data-ttu-id="e7d2e-120">O método foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-120">The method succeeded.</span></span>|  
|`E_FAIL`|<span data-ttu-id="e7d2e-121">Erro específico do provedor. Para obter informações detalhadas, use a interface ISQLServerErrorInfo.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-121">A provider specific error occurred, for detailed information use the ISQLServerErrorInfo interface.</span></span>|  
|`E_UNEXPECTED`|<span data-ttu-id="e7d2e-122">A chamada para o método era inesperada.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-122">The call to the method was unexpected.</span></span> <span data-ttu-id="e7d2e-123">Por exemplo, o `IBCPSession2::BCPInit` método não foi chamado antes de chamar IBCPSession2:: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-123">For example, the `IBCPSession2::BCPInit` method was not called before calling IBCPSession2::BCPSetBulkMode.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="e7d2e-124">O argumento era inválido.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-124">The argument was invalid.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="e7d2e-125">Erro de memória insuficiente.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-125">Out of memory error.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7d2e-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="e7d2e-126">Remarks</span></span>  
 <span data-ttu-id="e7d2e-127">IBCPSession2::BCPSetBulkMode pode ser usado para copiar em massa de uma consulta ou de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-127">IBCPSession2::BCPSetBulkMode can be used to bulk copy out of either a query or a table.</span></span> <span data-ttu-id="e7d2e-128">Quando IBCPSession2::BCPSetBulkMode é usado para fazer cópias em massa de uma instrução de consulta, ele precisa ser chamado antes de `IBCPSession::BCPControl(BCP_OPTIONS_HINTS, ...)` para especificar a instrução de consulta.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-128">When IBCPSession2::BCPSetBulkMode is used to bulk copy out of a query statement, it must be called before calling `IBCPSession::BCPControl(BCP_OPTIONS_HINTS, ...)` to specify the query statement.</span></span>  
  
 <span data-ttu-id="e7d2e-129">Evite combinar a sintaxe de chamada RPC com a sintaxe de consulta em lotes (`{rpc func};SELECT * from Tbl`, por exemplo) no texto de um único comando.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-129">You should avoid combining RPC call syntax with batch query syntax (`{rpc func};SELECT * from Tbl`, for example) in a single command text.</span></span>  <span data-ttu-id="e7d2e-130">Isto fará ICommandPrepare::Prepare retornar um erro e impedirá você de recuperar metadados.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-130">This will cause ICommandPrepare::Prepare to return an error and prevent you from retrieving metadata.</span></span> <span data-ttu-id="e7d2e-131">Use a sintaxe de ODBC CALL (`{call func}; SELECT * from Tbl`, por exemplo) se precisar combinar a execução de procedimentos armazenados e a consulta em lotes no texto de um único comando.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-131">Use ODBC CALL syntax (`{call func}; SELECT * from Tbl`, for example) if you need to combine stored procedure execution and batch query in a single command text.</span></span>  
  
 <span data-ttu-id="e7d2e-132">A tabela a seguir lista as constantes do parâmetro *property* .</span><span class="sxs-lookup"><span data-stu-id="e7d2e-132">The following table lists the constants for the *property* parameter.</span></span>  
  
|<span data-ttu-id="e7d2e-133">Propriedade</span><span class="sxs-lookup"><span data-stu-id="e7d2e-133">Property</span></span>|<span data-ttu-id="e7d2e-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="e7d2e-134">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e7d2e-135">BCP_OUT_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="e7d2e-135">BCP_OUT_CHARACTER_MODE</span></span>|<span data-ttu-id="e7d2e-136">Especifica o modo de saída de caractere.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-136">Specifies character output mode.</span></span><br /><br /> <span data-ttu-id="e7d2e-137">Corresponde à opção-c em BCP.EXE e a IBCPSession:: BCPColFmt com a propriedade *eUserDataType* definida como `BCP_TYPE_SQLCHARACTER` .</span><span class="sxs-lookup"><span data-stu-id="e7d2e-137">Corresponds to the -c option in BCP.EXE, and to IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLCHARACTER`.</span></span>|  
|<span data-ttu-id="e7d2e-138">BCP_OUT_WIDE_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="e7d2e-138">BCP_OUT_WIDE_CHARACTER_MODE</span></span>|<span data-ttu-id="e7d2e-139">Especifica o modo de saída de Unicode.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-139">Specifies Unicode output mode.</span></span><br /><br /> <span data-ttu-id="e7d2e-140">Corresponde à opção-w em BCP.EXE e IBCPSession:: BCPColFmt com a propriedade *eUserDataType* definida como `BCP_TYPE_SQLNCHAR` .</span><span class="sxs-lookup"><span data-stu-id="e7d2e-140">Corresponds to the -w option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLNCHAR`.</span></span>|  
|<span data-ttu-id="e7d2e-141">BCP_OUT_NATIVE_TEXT_MODE</span><span class="sxs-lookup"><span data-stu-id="e7d2e-141">BCP_OUT_NATIVE_TEXT_MODE</span></span>|<span data-ttu-id="e7d2e-142">Especifica tipos nativos para tipos de não caracteres e Unicode para tipos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-142">Specifies native types for non-character types and Unicode for character types.</span></span><br /><br /> <span data-ttu-id="e7d2e-143">Corresponde à opção-N em BCP.EXE e IBCPSession:: BCPColFmt com a propriedade *eUserDataType* definida como `BCP_TYPE_SQLNCHAR` se o tipo de coluna for uma cadeia de caracteres ou `BCP_TYPE_DEFAULT` se não for uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-143">Corresponds to the -N option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLNCHAR` if the column type is a string or `BCP_TYPE_DEFAULT` if not a string.</span></span>|  
|<span data-ttu-id="e7d2e-144">BCP_OUT_NATIVE_MODE</span><span class="sxs-lookup"><span data-stu-id="e7d2e-144">BCP_OUT_NATIVE_MODE</span></span>|<span data-ttu-id="e7d2e-145">Especifica tipos de bancos de dados nativos.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-145">Specifies native database types.</span></span><br /><br /> <span data-ttu-id="e7d2e-146">Corresponde à opção-n em BCP.EXE e IBCPSession:: BCPColFmt com a propriedade *eUserDataType* definida como `BCP_TYPE_DEFAULT` .</span><span class="sxs-lookup"><span data-stu-id="e7d2e-146">Corresponds to the -n option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_DEFAULT`.</span></span>|  
  
 <span data-ttu-id="e7d2e-147">Você pode chamar as opções IBCPSession::BCPControl e IBCPSession2::BCPSetBulkMode para IBCPSession::BCPControl que não entram em conflito com IBCPSession2::BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-147">You can call IBCPSession::BCPControl and IBCPSession2::BCPSetBulkMode for IBCPSession::BCPControl options that do not conflict with IBCPSession2::BCPSetBulkMode.</span></span> <span data-ttu-id="e7d2e-148">Por exemplo, você pode chamar IBCPSession:: BCPControl com `BCP_OPTION_FIRST` e IBCPSession2:: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-148">For example, you can call IBCPSession::BCPControl with `BCP_OPTION_FIRST` and IBCPSession2::BCPSetBulkMode.</span></span>  
  
 <span data-ttu-id="e7d2e-149">Você não pode chamar IBCPSession:: BCPControl com `BCP_OPTION_TEXTFILE` e IBCPSession2:: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-149">You cannot call IBCPSession::BCPControl with `BCP_OPTION_TEXTFILE` and IBCPSession2::BCPSetBulkMode.</span></span>  
  
 <span data-ttu-id="e7d2e-150">Se você tentar chamar IBCPSession2::BCPSetBulkMode com uma sequência de chamadas de função que inclui IBCPSession::BCPColFmt, IBCPSession::BCPControl e IBCPSession::BCPReadFmt, uma das chamadas de função retornará uma falha de erro de sequência.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-150">If you attempt to call IBCPSession2::BCPSetBulkMode with a sequence of function calls that includes IBCPSession::BCPColFmt, IBCPSession::BCPControl, and IBCPSession::BCPReadFmt, one of the function calls will return a sequence error failure.</span></span> <span data-ttu-id="e7d2e-151">Se você optar por corrigir a falha, chame IBCPSession::BCPInit para redefinir as configurações e recomeçar.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-151">If you choose to correct the failure, call IBCPSession::BCPInit to reset the settings and start over.</span></span>  
  
 <span data-ttu-id="e7d2e-152">A tabela a seguir apresenta alguns exemplos de chamadas de funções que resultam em um erro de sequência de função:</span><span class="sxs-lookup"><span data-stu-id="e7d2e-152">The following table presents some examples of function calls that result in a function sequence error:</span></span>  
  
 <span data-ttu-id="e7d2e-153">Sequência de chamada</span><span class="sxs-lookup"><span data-stu-id="e7d2e-153">Call sequence</span></span>  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_IN);  
BCPSetBulkMode();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPSetBulkMode();  
BCPReadFmt();  
```  
  
```  
BCPInit(NULL, "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_HINTS, "select ...");  
BCPSetBulkMode();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPSetBulkMode();  
BCPColFmt();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPReadFmt();  
BCPColFmt();  
```  
  
```  
BCPInit(NULL, "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPSetBulkMode();  
BCPControl(BCP_OPTION_HINTS, "select ...");  
BCPReadFmt();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPColumns();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPSetColFmt();  
```  
  
## <a name="example"></a><span data-ttu-id="e7d2e-154">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e7d2e-154">Example</span></span>  
 <span data-ttu-id="e7d2e-155">O exemplo a seguir cria quatro arquivos usando diferentes configurações de IBCPSession2::BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="e7d2e-155">The following sample creates four files using different settings of IBCPSession2::BCPSetBulkMode.</span></span>  
  
```  
  
// compile with: sqlncli11.lib oleaut32.lib ole32.lib  
  
#include <stdio.h>  
#include "sqlncli.h"  
  
IDBInitialize*  g_pIDBInitialize = NULL;  
IBCPSession2 * g_pIBcpSession = NULL;  
class COLEDBPropSet : public DBPROPSET {  
public:  
   COLEDBPropSet() {  
      rgProperties = NULL;  
      cProperties = 0;  
   };  
   COLEDBPropSet(const GUID& guid) {  
      rgProperties = NULL;  
      cProperties = 0;  
      guidPropertySet = guid;  
   };  
   ~COLEDBPropSet() {  
      for ( ULONG i = 0 ; i < cProperties ; i++ )  
         VariantClear(&rgProperties[i].vValue);  
      CoTaskMemFree(rgProperties);  
   }  
   void SetGUID(const GUID& guid) {  
      guidPropertySet = guid;  
   };  
   bool AddProperty(DWORD dwPropertyID, bool bValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID = dwPropertyID;  
      rgProperties[cProperties].vValue.vt = VT_BOOL;  
      rgProperties[cProperties].vValue.boolVal = (bValue) ? VARIANT_TRUE : VARIANT_FALSE;  
      cProperties++;  
      return true;  
   };  
   bool AddProperty(DWORD dwPropertyID, long nValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID  = dwPropertyID;  
      rgProperties[cProperties].vValue.vt     = VT_I4;  
      rgProperties[cProperties].vValue.lVal   = nValue;  
      cProperties++;  
      return true;  
   };  
   bool AddProperty(DWORD dwPropertyID,LPCWSTR szValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID = dwPropertyID;  
      rgProperties[cProperties].vValue.vt = VT_BSTR;  
      rgProperties[cProperties].vValue.bstrVal = SysAllocString(szValue);  
      cProperties++;  
      return true;  
   };  
   bool Add() {  
      DBPROP* p = (DBPROP*)CoTaskMemRealloc(rgProperties, (cProperties + 1) * sizeof(DBPROP));  
      if (p != NULL) {  
         rgProperties = p;  
         rgProperties[cProperties].dwOptions = DBPROPOPTIONS_REQUIRED;  
         rgProperties[cProperties].colid = DB_NULLID;  
         rgProperties[cProperties].vValue.vt = VT_EMPTY;  
         return true;  
      }  
      else  
         return false;  
   };  
};  
  
void OLEDBCleanUp() {  
   if (g_pIDBInitialize) {  
      g_pIDBInitialize->Release();  
      g_pIDBInitialize = NULL;  
   }  
   if (g_pIBcpSession) {  
      g_pIBcpSession->Release();  
      g_pIBcpSession = NULL;  
   }  
}  
  
BOOL MakeOLEDBConnect(LPWSTR  pServer) {  
   BOOL ret = true;  
   IDBProperties * pIDBProperties = NULL;  
   IDBCreateSession * pIDBCreateSession = NULL;  
   COLEDBPropSet PropSet(DBPROPSET_DBINIT);  
   COLEDBPropSet BcpProperty(DBPROPSET_SQLSERVERDATASOURCE);  
   try {  
      HRESULT hr = CoInitializeEx(NULL,COINIT_MULTITHREADED);   
      hr = CoCreateInstance(SQLNCLI_CLSID, NULL, CLSCTX_INPROC_SERVER, IID_IDBInitialize, (LPVOID *)&g_pIDBInitialize);  
      if (FAILED(hr)) {  
         printf("CoCreateInstance failed\n");  
         return false;  
      }  
      PropSet.AddProperty(DBPROP_INIT_DATASOURCE, (LPWSTR)pServer);  
      PropSet.AddProperty(DBPROP_AUTH_INTEGRATED, L"SSPI");  
      hr = g_pIDBInitialize->QueryInterface(IID_IDBProperties, (void**) &pIDBProperties);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->QueryInterface(IID_IDBProperties...) failed\n");  
         throw false;  
      }  
      hr = pIDBProperties->SetProperties(1, &PropSet);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->SetProperties(...) failed\n");  
         throw false;  
      }  
      hr = g_pIDBInitialize->Initialize();  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->Initialize() failed\n");  
         throw false;  
      }  
      BcpProperty.AddProperty(SSPROP_ENABLEFASTLOAD, true);  
      BcpProperty.AddProperty(SSPROP_ENABLEBULKCOPY, true);  
      hr = pIDBProperties->SetProperties(1, &BcpProperty);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->SetProperties() for bcp failed\n");  
         throw false;  
      }  
      hr = g_pIDBInitialize->QueryInterface(IID_IDBCreateSession, (void**) &pIDBCreateSession);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->QueryInterface(IID_IDBCreateSession..) failed\n");  
         throw false;  
      }  
  
      hr = pIDBCreateSession->CreateSession(NULL, IID_IBCPSession2, (IUnknown**) &g_pIBcpSession);  
      if (FAILED(hr)) {  
         printf("g_pIDBCreateSession->CreateSession() failed\n");  
         throw false;  
      }  
   }  
   catch(...) {  
      ret = false;  
   }  
   if (pIDBProperties)  
      pIDBProperties->Release();  
   if (pIDBCreateSession)  
      pIDBCreateSession->Release();  
   return ret;  
}  
  
BOOL BCPSetBulkMode(LPWSTR pszServer, LPTSTR pszQureryOut, char BCPType, LPWSTR pszDataFile) {  
   HRESULThr;  
   if (!MakeOLEDBConnect(pszServer))  
      return false;  
   hr = g_pIBcpSession->BCPInit(NULL, pszDataFile, NULL, BCP_DIRECTION_OUT );   // bcp init for queryout  
   if (FAILED(hr)) {  
      printf("BCP init failed\n");  
      OLEDBCleanUp();  
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
  
   if(BCPType == 'c') {   // bcp -c  
      pColTerm = (BYTE*)ColTerm;  
      pRowTerm = (BYTE*)RowTerm;  
      cbColTerm = 1;  
      cbRowTerm = 2;  
      bulkmode = BCP_OUT_CHARACTER_MODE;  
   }  
   else  
      if(BCPType == 'w') {   // bcp -w  
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
               OLEDBCleanUp();  
               return false;  
            }  
            hr = g_pIBcpSession->BCPSetBulkMode(bulkmode, pColTerm, cbColTerm, pRowTerm, cbRowTerm);  
            if (FAILED(hr)) {  
               printf("BCPSetBulkMode failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
  
            // set queryout TSQL statement  
            hr = g_pIBcpSession->BCPControl(BCP_OPTION_HINTS, pszQureryOut);  
            if (FAILED(hr)) {  
               printf("BCPControl failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            // bcp copy  
            DBROWCOUNT nRowsInserted = 0;  
            hr = g_pIBcpSession->BCPExec(&nRowsInserted);  
            if (FAILED(hr)) {  
               printf("BCPExec failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            printf("bcp done\n");  
            OLEDBCleanUp();  
            return true;  
}  
  
int main() {  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -c test', 1,2") , 'c', L"bcpc.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -w test', 1,2") , 'w', L"bcpw.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -c test', 1,2") , 'n', L"bcpn.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -w test', 1,2") , 'N', L"bcp_N.dat");  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7d2e-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7d2e-156">See Also</span></span>  
 [<span data-ttu-id="e7d2e-157">IBCPSession2 &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e7d2e-157">IBCPSession2 &#40;OLE DB&#41;</span></span>](ibcpsession2-ole-db.md)  
  
  
