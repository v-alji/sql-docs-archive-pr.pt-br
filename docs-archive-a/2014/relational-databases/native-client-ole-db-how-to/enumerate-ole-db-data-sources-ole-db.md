---
title: Enumerar fontes de dados OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [OLE DB]
ms.assetid: ba240060-3237-4fb8-b2fb-b87fda2b1e7a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1173feef8de657c43563b40bec763f81d630014e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684708"
---
# <a name="enumerate-ole-db-data-sources-ole-db"></a><span data-ttu-id="b8961-102">Enumerar fontes de dados OLE DB (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="b8961-102">Enumerate OLE DB Data Sources (OLE DB)</span></span>
  <span data-ttu-id="b8961-103">Este exemplo mostra como usar o objeto enumerador para listar as fontes de dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b8961-103">This sample shows how to use the enumerator object to list the data sources available.</span></span>  
  
 <span data-ttu-id="b8961-104">Para listar as fontes de dados visíveis para o enumerador SQLOLEDB, o consumidor chama o método [ISourcesRowset::GetSourcesRowset](https://go.microsoft.com/fwlink/?LinkId=120312) .</span><span class="sxs-lookup"><span data-stu-id="b8961-104">To list the data sources visible to the SQLOLEDB enumerator, the consumer calls the [ISourcesRowset::GetSourcesRowset](https://go.microsoft.com/fwlink/?LinkId=120312) method.</span></span> <span data-ttu-id="b8961-105">Esse método retorna um conjunto de linhas de informações sobre as fontes de dados visíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="b8961-105">This method returns a rowset of information about the currently visible data sources.</span></span>  
  
 <span data-ttu-id="b8961-106">Dependendo da biblioteca de rede usada, o domínio apropriado é pesquisado em busca das fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="b8961-106">Depending on the network library used, the appropriate domain is searched for the data sources.</span></span> <span data-ttu-id="b8961-107">Para pipes nomeados, é o domínio no qual o cliente fez logon.</span><span class="sxs-lookup"><span data-stu-id="b8961-107">For named pipes, it is the domain to which the client is logged on.</span></span> <span data-ttu-id="b8961-108">Para AppleTalk, é a zona padrão.</span><span class="sxs-lookup"><span data-stu-id="b8961-108">For AppleTalk, it is the default zone.</span></span> <span data-ttu-id="b8961-109">Para SPX/IPX, é a lista de instalações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encontradas no bindery.</span><span class="sxs-lookup"><span data-stu-id="b8961-109">For SPX/IPX, it is the list of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installations found in the bindery.</span></span> <span data-ttu-id="b8961-110">Para Banyan VINES, são as instalações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encontradas na rede local.</span><span class="sxs-lookup"><span data-stu-id="b8961-110">For Banyan VINES, it is the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installations found on the local network.</span></span> <span data-ttu-id="b8961-111">Soquetes TCP/IP e de protocolos múltiplos não são suportados.</span><span class="sxs-lookup"><span data-stu-id="b8961-111">Multiprotocol and TCP/IP sockets are not supported.</span></span>  
  
 <span data-ttu-id="b8961-112">Quando o servidor é desativado ou ativado, pode levar alguns minutos para atualizar as informações nesses domínios.</span><span class="sxs-lookup"><span data-stu-id="b8961-112">When the server is turned off or on, it can take few minutes to update the information in these domains.</span></span>  
  
 <span data-ttu-id="b8961-113">Este exemplo exige o banco de dados de exemplo AdventureWorks, que pode ser baixado na home page de [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) (em inglês).</span><span class="sxs-lookup"><span data-stu-id="b8961-113">This sample requires the AdventureWorks sample database, which you can download from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b8961-114">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="b8961-114">When possible, use Windows Authentication.</span></span> <span data-ttu-id="b8961-115">Se a Autenticação do Windows não estiver disponível, solicite aos usuários que digitem suas credenciais em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="b8961-115">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="b8961-116">Evite armazenar as credenciais em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b8961-116">Avoid storing credentials in a file.</span></span> <span data-ttu-id="b8961-117">Se for necessário manter as credenciais, criptografe-as com a [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="b8961-117">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-enumerate-ole-db-data-sources"></a><span data-ttu-id="b8961-118">Para enumerar fontes de dados OLE DB</span><span class="sxs-lookup"><span data-stu-id="b8961-118">To enumerate OLE DB data sources</span></span>  
  
1.  <span data-ttu-id="b8961-119">Recupere o conjunto de linhas de origem chamando `ISourceRowset::GetSourcesRowset`.</span><span class="sxs-lookup"><span data-stu-id="b8961-119">Retrieve the source rowset by calling `ISourceRowset::GetSourcesRowset`.</span></span>  
  
2.  <span data-ttu-id="b8961-120">Encontre a descrição do conjunto de linhas de enumeradores chamando `GetColumnInfo::IColumnInfo`.</span><span class="sxs-lookup"><span data-stu-id="b8961-120">Find the description of the enumerators rowset by calling `GetColumnInfo::IColumnInfo`.</span></span>  
  
3.  <span data-ttu-id="b8961-121">Crie as estruturas de associação a partir das informações de coluna.</span><span class="sxs-lookup"><span data-stu-id="b8961-121">Create the binding structures from the column information.</span></span>  
  
4.  <span data-ttu-id="b8961-122">Crie o acessador de conjunto de linhas chamando `IAccessor::CreateAccessor`.</span><span class="sxs-lookup"><span data-stu-id="b8961-122">Create the rowset accessor by calling `IAccessor::CreateAccessor`.</span></span>  
  
5.  <span data-ttu-id="b8961-123">Busque as linhas chamando `IRowset::GetNextRows`.</span><span class="sxs-lookup"><span data-stu-id="b8961-123">Fetch the rows by calling `IRowset::GetNextRows`.</span></span>  
  
6.  <span data-ttu-id="b8961-124">Recupere os dados da cópia da linha do conjunto de linhas chamando `IRowset::GetData` e processe-os.</span><span class="sxs-lookup"><span data-stu-id="b8961-124">Retrieve data from the rowset's copy of the row by calling `IRowset::GetData`, and process it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8961-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b8961-125">Example</span></span>  
 <span data-ttu-id="b8961-126">Compile com ole32.lib e execute a seguinte listagem de código C++.</span><span class="sxs-lookup"><span data-stu-id="b8961-126">Compile with ole32.lib and execute the following C++ code listing.</span></span> <span data-ttu-id="b8961-127">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="b8961-127">This application connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="b8961-128">Em alguns sistemas operacionais Windows, será necessário alterar (localhost) ou (local) para o nome de sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8961-128">On some Windows operating systems, you will need to change (localhost) or (local) to the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="b8961-129">Para se conectar a uma instância nomeada, altere a cadeia de conexão de L"(local)" para L"(local)\\\name", em que name é a instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="b8961-129">To connect to a named instance, change the connection string from L"(local)" to L"(local)\\\name" , where name is the named instance.</span></span> <span data-ttu-id="b8961-130">Por padrão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="b8961-130">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express installs to a named instance.</span></span> <span data-ttu-id="b8961-131">Verifique se a variável de ambiente INCLUDE inclui o diretório que contém sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="b8961-131">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
```  
// compile with: ole32.lib  
#define UNICODE  
#define _UNICODE  
#define DBINITCONSTANTS  
#define INITGUID  
#define OLEDBVER 0x0250   // to include correct interfaces  
  
#include <windows.h>  
#include <stddef.h>  
#include <oledb.h>  
#include <oledberr.h>  
#include <sqlncli.h>  
#include <stdio.h>  
  
#define NUMROWS_CHUNK  5  
  
// AdjustLen supports binding on four-byte boundaries.  
_inline DBLENGTH AdjustLen(DBLENGTH cb) {   
   return ( (cb + 3) & ~3 );  
}  
  
// Get the characteristics of the rowset (the IColumnsInfo interface).  
HRESULT GetColumnInfo ( IRowset* pIRowset,   
                        DBORDINAL* pnCols,   
                        DBCOLUMNINFO** ppColumnsInfo,  
                        OLECHAR** ppColumnStrings ) {  
   IColumnsInfo* pIColumnsInfo;  
   HRESULT hr;  
  
   *pnCols = 0;  
   if (FAILED(pIRowset->QueryInterface(IID_IColumnsInfo, (void**) &pIColumnsInfo)))  
      return (E_FAIL);  
  
   hr = pIColumnsInfo->GetColumnInfo(pnCols, ppColumnsInfo, ppColumnStrings);  
  
   if (FAILED(hr)) {}   /* Process error */   
  
   pIColumnsInfo->Release();  
   return (hr);  
}  
  
// Create binding structures from column information. Binding structures  
// will be used to create an accessor that allows row value retrieval.  
void CreateDBBindings ( DBORDINAL nCols,   
                        DBCOLUMNINFO* pColumnsInfo,   
                        DBBINDING** ppDBBindings,  
                        BYTE** ppRowValues ) {  
   ULONG nCol;  
   DBLENGTH cbRow = 0;  
   DBLENGTH cbCol;  
   DBBINDING* pDBBindings;  
   BYTE* pRowValues;  
  
   pDBBindings = new DBBINDING[nCols];  
   if (!(pDBBindings /* = new DBBINDING[nCols] */ ))  
      return;  
  
   for ( nCol = 0 ; nCol < nCols ; nCol++ ) {  
      pDBBindings[nCol].iOrdinal = nCol + 1;  
      pDBBindings[nCol].pTypeInfo = NULL;  
      pDBBindings[nCol].pObject = NULL;  
      pDBBindings[nCol].pBindExt = NULL;  
      pDBBindings[nCol].dwPart = DBPART_VALUE;  
      pDBBindings[nCol].dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
      pDBBindings[nCol].eParamIO = DBPARAMIO_NOTPARAM;  
      pDBBindings[nCol].dwFlags = 0;  
      pDBBindings[nCol].wType = pColumnsInfo[nCol].wType;  
      pDBBindings[nCol].bPrecision = pColumnsInfo[nCol].bPrecision;  
      pDBBindings[nCol].bScale = pColumnsInfo[nCol].bScale;  
  
      cbCol = pColumnsInfo[nCol].ulColumnSize;  
  
      switch (pColumnsInfo[nCol].wType) {  
      case DBTYPE_STR: {  
            cbCol += 1;  
            break;  
         }  
  
      case DBTYPE_WSTR: {  
            cbCol = (cbCol + 1) * sizeof(WCHAR);  
            break;  
         }  
  
      default:  
         break;  
      }  
  
      pDBBindings[nCol].obValue = cbRow;  
      pDBBindings[nCol].cbMaxLen = cbCol;  
      cbRow += AdjustLen(cbCol);  
   }  
  
   pRowValues = new BYTE[cbRow];  
   *ppDBBindings = pDBBindings;  
   *ppRowValues = pRowValues;  
}  
  
int main() {  
   ISourcesRowset* pISourceRowset = NULL;      
   IRowset* pIRowset = NULL;          
   IAccessor* pIAccessor = NULL;  
   DBBINDING* pDBBindings = NULL;              
  
   HROW* pRows = new HROW[500];      
   HACCESSOR hAccessorRetrieve = NULL;          
   ULONG DSSeqNumber = 0;  
  
   HRESULT hr;  
   DBORDINAL nCols;  
   DBCOLUMNINFO* pColumnsInfo = NULL;  
   OLECHAR* pColumnStrings = NULL;  
   DBBINDSTATUS* pDBBindStatus = NULL;  
  
   BYTE* pRowValues = NULL;  
   DBCOUNTITEM cRowsObtained;  
   ULONG iRow;  
   char* pMultiByte = NULL;  
   short* psSourceType = NULL;  
   BYTE* pDatasource = NULL;  
  
   if (!pRows)  
      return (0);  
  
   // Initialize COM library.  
   CoInitialize(NULL);  
  
   // Initialize the enumerator.  
   if (FAILED(CoCreateInstance(CLSID_SQLNCLI11_ENUMERATOR,   
                               NULL,  
                               CLSCTX_INPROC_SERVER,   
                               IID_ISourcesRowset,   
                               (void**)&pISourceRowset))) {  
      // Process error.  
      return TRUE;  
   }  
  
   // Retrieve the source rowset.  
   hr = pISourceRowset->GetSourcesRowset(NULL, IID_IRowset, 0, NULL, (IUnknown**)&pIRowset);  
  
   pISourceRowset->Release();  
   if (FAILED(hr)) {  
      // Process error.  
      return TRUE;  
   }  
  
   // Get the description of the enumerator's rowset.  
   if (FAILED(hr = GetColumnInfo(pIRowset, &nCols, &pColumnsInfo, &pColumnStrings))) {  
      // Process error.  
      goto SAFE_EXIT;  
   }  
  
   // Create the binding structures.  
   CreateDBBindings(nCols, pColumnsInfo, &pDBBindings, &pRowValues);  
   pDBBindStatus = new DBBINDSTATUS[nCols];  
  
   if (sizeof(TCHAR) != sizeof(WCHAR))  
      pMultiByte = new char[pDBBindings[0].cbMaxLen];  
  
   if (FAILED(pIRowset->QueryInterface(IID_IAccessor, (void**)&pIAccessor))) {  
      // Process error.  
      goto SAFE_EXIT;  
   }  
  
   // Create the rowset accessor.  
   if (FAILED(hr = pIAccessor->CreateAccessor(DBACCESSOR_ROWDATA,   
                                              nCols,  
                                              pDBBindings,   
                                              0,   
                                              &hAccessorRetrieve,   
                                              pDBBindStatus))) {  
      // Process error.  
      goto SAFE_EXIT;  
   }  
  
   // Process all the rows, NUMROWS_CHUNK rows at a time.  
   while (SUCCEEDED(hr)) {  
      hr = pIRowset->GetNextRows(NULL, 0, NUMROWS_CHUNK, &cRowsObtained, &pRows);  
      if( FAILED(hr)) {  
         // process error  
      }  
      if (cRowsObtained == 0 || FAILED(hr))  
         break;  
  
      for (iRow = 0 ; iRow < cRowsObtained ; iRow++) {  
         // Get the rowset data.  
         if (SUCCEEDED(hr = pIRowset->GetData(pRows[iRow], hAccessorRetrieve, pRowValues))) {  
            psSourceType = (short *)(pRowValues + pDBBindings[3].obValue);  
  
            if (*psSourceType == DBSOURCETYPE_DATASOURCE) {  
               DSSeqNumber = DSSeqNumber + 1;   // Data source counter.  
               pDatasource = (pRowValues + pDBBindings[0].obValue);  
  
               if ( sizeof(TCHAR) != sizeof(WCHAR) ) {  
                  WideCharToMultiByte(CP_ACP,   
                                      0,  
                                      (WCHAR*)pDatasource,   
                                      -1,   
                                      pMultiByte,  
                                      static_cast<int>(pDBBindings[0].cbMaxLen),   
                                      NULL,   
                                      NULL);  
  
                  printf( "DataSource# %d\tName: %S\n",   
                          DSSeqNumber,   
                          (WCHAR *) pMultiByte );  
               }  
               else {  
                  printf( "DataSource# %d\tName: %S\n",   
                          DSSeqNumber,   
                          (WCHAR *) pDatasource );  
               }  
            }  
         }  
      }  
      pIRowset->ReleaseRows(cRowsObtained, pRows, NULL, NULL, NULL);  
   }  
  
   // Release COM library.  
   CoUninitialize();  
  
SAFE_EXIT:  
   // Do the clean-up.  
   return TRUE;  
}  
```  
  
  
