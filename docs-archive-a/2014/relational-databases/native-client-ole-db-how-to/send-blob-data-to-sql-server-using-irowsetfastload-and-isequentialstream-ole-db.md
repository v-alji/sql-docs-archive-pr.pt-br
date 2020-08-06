---
title: Enviar dados de BLOB para o SQL SERVER usando IROWSETFASTLOAD e ISEQUENTIALSTREAM (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: cb022814-a86b-425d-9b24-eaac20ab664e
author: rothja
ms.author: jroth
ms.openlocfilehash: 647d1bd9d0f0aaa34393b2b7e53e9eb5e0bad1bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679339"
---
# <a name="send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db"></a><span data-ttu-id="9623d-102">Enviar dados BLOB ao SQL SERVER usando IROWSETFASTLOAD e ISEQUENTIALSTREAM (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="9623d-102">Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM (OLE DB)</span></span>
  <span data-ttu-id="9623d-103">Este exemplo mostra como usar IRowsetFastLoad para o fluxo de dados BLOB de comprimento variável por linha.</span><span class="sxs-lookup"><span data-stu-id="9623d-103">This sample shows how to use IRowsetFastLoad to stream varying length BLOB data per row.</span></span>  
  
 <span data-ttu-id="9623d-104">Por padrão, este exemplo mostra como usar IRowsetFastLoad para enviar dados BLOB de comprimento variável por linha usando associações embutidas.</span><span class="sxs-lookup"><span data-stu-id="9623d-104">By default, this sample shows how to use IRowsetFastLoad to send variable length BLOB data per row by using in-line bindings.</span></span> <span data-ttu-id="9623d-105">Os dados BLOB embutidos devem se ajustar à memória disponível.</span><span class="sxs-lookup"><span data-stu-id="9623d-105">The in-line BLOB data must fit in available memory.</span></span> <span data-ttu-id="9623d-106">Este método é executado melhor quando os dados BLOB têm menos de alguns megabytes, pois não há sobrecarga de fluxo adicional.</span><span class="sxs-lookup"><span data-stu-id="9623d-106">This method performs best when the BLOB data is less than a few megabytes, because there is no additional stream overhead.</span></span> <span data-ttu-id="9623d-107">Para dados com mais de alguns megabytes, principalmente dados que não estejam disponíveis em um bloco, o acesso de fluxo fornece desempenho melhor.</span><span class="sxs-lookup"><span data-stu-id="9623d-107">For data larger than a few megabytes, especially data that is not available in a block, streaming provides better performance.</span></span>  
  
 <span data-ttu-id="9623d-108">No código-fonte, quando você remover o comentário #define USE_ISEQSTREAM, o exemplo usará ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="9623d-108">In the source code, when you uncomment #define USE_ISEQSTREAM , the sample will use ISequentialStream.</span></span> <span data-ttu-id="9623d-109">A implementação de fluxo é definida na amostra e pode enviar qualquer tamanho de dados BLOB simplesmente alterando MAX_BLOB.</span><span class="sxs-lookup"><span data-stu-id="9623d-109">The stream implementation is defined in the sample, and can send any size BLOB data simply by changing MAX_BLOB .</span></span> <span data-ttu-id="9623d-110">Os dados de fluxo não têm que se ajustar à memória ou estar disponíveis em um bloco.</span><span class="sxs-lookup"><span data-stu-id="9623d-110">Stream data does not have to fit in memory or be available in one block.</span></span> <span data-ttu-id="9623d-111">Para chamar esse provedor, use IRowsetFastLoad::InsertRow.</span><span class="sxs-lookup"><span data-stu-id="9623d-111">You call this provider by using IRowsetFastLoad::InsertRow.</span></span> <span data-ttu-id="9623d-112">Passe um ponteiro usando IRowsetFastLoad::InsertRow para a implementação de fluxo no buffer de dados (deslocamento rgBinding.obValue) junto com a quantidade de dados disponível para leitura do fluxo.</span><span class="sxs-lookup"><span data-stu-id="9623d-112">Pass a pointer using IRowsetFastLoad::InsertRow to the stream implementation in the data buffer (rgBinding.obValue offset) along with the amount of data available to read from the stream.</span></span> <span data-ttu-id="9623d-113">Alguns provedores talvez não tenham que saber o comprimento dos dados quando a associação ocorre.</span><span class="sxs-lookup"><span data-stu-id="9623d-113">Some providers might not have to know the length of the data when binding occurs.</span></span> <span data-ttu-id="9623d-114">Nesse caso, o comprimento poderá ser omitido da associação.</span><span class="sxs-lookup"><span data-stu-id="9623d-114">In this case, the length can be omitted from the binding.</span></span>  
  
 <span data-ttu-id="9623d-115">A amostra não usa a interface de fluxo do provedor para gravar dados no provedor.</span><span class="sxs-lookup"><span data-stu-id="9623d-115">The sample does not use the provider's stream interface to write data to the provider.</span></span> <span data-ttu-id="9623d-116">Em vez disso, o exemplo passa um ponteiro ao objeto de fluxo que o provedor consumirá para ler os dados.</span><span class="sxs-lookup"><span data-stu-id="9623d-116">Instead, the sample passes a pointer to the stream object that the provider will consume to read the data.</span></span> <span data-ttu-id="9623d-117">Normalmente, os provedores Microsoft (SQLOLEDB e SQLNCLI) lerão dados em partes de 1024 bytes do objeto até que todo os dados sejam processados.</span><span class="sxs-lookup"><span data-stu-id="9623d-117">Typically, Microsoft providers (SQLOLEDB and SQLNCLI) will read data in 1024-byte chunks from the object until all data has been processed.</span></span> <span data-ttu-id="9623d-118">Nem SQLOLEDB nem SQLNCLI têm implementações completas para permitir ao consumidor gravar dados no objeto de fluxo do provedor.</span><span class="sxs-lookup"><span data-stu-id="9623d-118">Neither SQLOLEDB nor SQLNCLI have full implementations for allowing the consumer to write data to the provider's stream object.</span></span> <span data-ttu-id="9623d-119">Somente dados de comprimento zero podem ser enviados pelo objeto de fluxo do provedor.</span><span class="sxs-lookup"><span data-stu-id="9623d-119">Only zero length data can be sent through the provider's stream object.</span></span>  
  
 <span data-ttu-id="9623d-120">O objeto ISequentialStream implementado pelo consumidor pode ser usado com dados de conjunto de linhas (IRowsetChange::InsertRow, IRowsetChange::SetData) e com parâmetros associando-se um parâmetro como DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="9623d-120">The consumer-implemented ISequentialStream object can be used with rowset data (IRowsetChange::InsertRow, IRowsetChange::SetData) and with parameters by binding a parameter as DBTYPE_IUNKNOWN.</span></span>  
  
 <span data-ttu-id="9623d-121">Como DBTYPE_IUNKNOWN é especificado como o tipo de dados na associação, ele deve corresponder ao tipo da coluna ou parâmetro de destino.</span><span class="sxs-lookup"><span data-stu-id="9623d-121">Because DBTYPE_IUNKNOWN is specified as the data type in the binding, it must match the type of the column or target parameter.</span></span> <span data-ttu-id="9623d-122">As conversões não são possíveis durante o envio de dados por meio de ISequentialStream a partir de interfaces de conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="9623d-122">Conversions are not possible when sending data through ISequentialStream from rowset interfaces.</span></span> <span data-ttu-id="9623d-123">Para parâmetros, evite usar ICommandWithParameters::SetParameterInfo e especifique um tipo diferente para forçar uma conversão; isso exigirá que o provedor armazene em cache todos os dados BLOB localmente, para convertê-los antes do envio ao SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9623d-123">For parameters, you should avoid using ICommandWithParameters::SetParameterInfo and specify a different type to force a conversion; this would require the provider to cache all the BLOB data locally, to convert it before sending to SQL Server.</span></span> <span data-ttu-id="9623d-124">Armazenar em cache um BLOB grande e convertê-lo localmente não fornece um bom desempenho.</span><span class="sxs-lookup"><span data-stu-id="9623d-124">Caching a large BLOB and converting it locally does not provide good performance.</span></span>  
  
 <span data-ttu-id="9623d-125">Para obter mais informações, confira [BLOBs e objetos OLE](../native-client-ole-db-blobs/blobs-and-ole-objects.md).</span><span class="sxs-lookup"><span data-stu-id="9623d-125">For more information, see [BLOBs and OLE Objects](../native-client-ole-db-blobs/blobs-and-ole-objects.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9623d-126">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="9623d-126">When possible, use Windows Authentication.</span></span> <span data-ttu-id="9623d-127">Se a Autenticação do Windows não estiver disponível, solicite aos usuários que digitem suas credenciais em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="9623d-127">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="9623d-128">Evite armazenar as credenciais em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="9623d-128">Avoid storing credentials in a file.</span></span> <span data-ttu-id="9623d-129">Se for necessário manter as credenciais, criptografe-as com a [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="9623d-129">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9623d-130">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9623d-130">Example</span></span>  
 <span data-ttu-id="9623d-131">Execute a primeira listagem de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) para criar a tabela usada pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9623d-131">Execute the first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to create the table used by the application.</span></span>  
  
 <span data-ttu-id="9623d-132">Compile com ole32.lib oleaut32.lib e execute a seguinte listagem de código C++.</span><span class="sxs-lookup"><span data-stu-id="9623d-132">Compile with ole32.lib oleaut32.lib and execute the following C++ code listing.</span></span> <span data-ttu-id="9623d-133">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="9623d-133">This application connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="9623d-134">Em alguns sistemas operacionais Windows, será necessário alterar (localhost) ou (local) para o nome de sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9623d-134">On some Windows operating systems, you will need to change (localhost) or (local) to the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="9623d-135">Para se conectar a uma instância nomeada, altere a cadeia de conexão de L"(local)" para L"(local)\\\name", em que name é a instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="9623d-135">To connect to a named instance, change the connection string from L"(local)" to L"(local)\\\name" , where name is the named instance.</span></span> <span data-ttu-id="9623d-136">Por padrão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="9623d-136">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express installs to a named instance.</span></span> <span data-ttu-id="9623d-137">Verifique se a variável de ambiente INCLUDE inclui o diretório que contém sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="9623d-137">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
 <span data-ttu-id="9623d-138">Execute a terceira listagem de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) para excluir a tabela usada pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9623d-138">Execute the third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to delete the table used by the application.</span></span>  
  
```  
use master  
create table fltest(col1 int, col2 int, col3 image)  
```  
  
```  
// compile with: ole32.lib oleaut32.lib  
#include <windows.h>  
  
#define DBINITCONSTANTS   // Must be defined to initialize constants in oledb.h  
#define INITGUID                
  
#include <sqloledb.h>  
#include <oledb.h>  
#include <msdasc.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <conio.h>  
  
#define MAX_BLOB  200   // For stream binding this can be any size, but for inline it must fit in memory  
#define MAX_ROWS  100  
  
#define SAFE_RELEASE(p) { \  
   if (p) { \  
      (p)->Release(); \  
      (p)=NULL; \  
   } \  
}  
  
#ifdef USE_ISEQSTREAM  
// ISequentialStream implementation for streaming data  
class MySequentialStream : public ISequentialStream {  
  
private:  
   ULONG m_ulRefCount;  
   ULONG m_ulBufSize;  
   ULONG m_ulReadSize;  
   ULONG m_ulBytesLeft;  
   ULONG m_ulReadPos;  
   BYTE * m_pSrcData;  
   BYTE * m_pReadPtr;  
   BOOL m_fWasRead;  
  
public:  
  
   MySequentialStream() {  
      m_ulRefCount = 1;  
      m_ulBufSize = 0;  
      m_ulReadSize = 0;  
      m_ulBytesLeft = 0;  
      m_ulReadPos = 0;  
      m_pSrcData = NULL;  
      m_pReadPtr = NULL;  
      m_fWasRead = FALSE;  
   }  
  
   ~MySequentialStream() {}  
  
   virtual ULONG STDMETHODCALLTYPE AddRef() {  
      return ++m_ulRefCount;  
   }  
  
   virtual ULONG STDMETHODCALLTYPE Release() {  
      --m_ulRefCount;  
      if (m_ulRefCount == 0) {  
         delete this;  
         return 0;  
      }  
      return m_ulRefCount;  
   }  
  
   virtual HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void ** ppvObj) {  
      if (!ppvObj)  
         return E_INVALIDARG;  
      else  
         *ppvObj = NULL;  
  
      if (riid != IID_ISequentialStream && riid != IID_IUnknown)  
         return E_NOINTERFACE;  
  
      AddRef();  
      *ppvObj = this;  
      return S_OK;  
   }  
  
   HRESULT Init(const void * pSrcData, const ULONG ulBufSize, const ULONG ulReadSize) {  
      if (NULL == pSrcData)  
         return E_INVALIDARG;  
  
      // Data length must be non-zero  
      if (0 == ulBufSize)  
         return E_INVALIDARG;  
  
      m_ulBufSize = ulBufSize;  
      m_ulReadSize = ulReadSize;  
      m_pSrcData = (BYTE *)pSrcData;  
      m_pReadPtr = m_pSrcData;  
      m_ulBytesLeft = m_ulReadSize;  
      m_ulReadPos = 0;  
      m_fWasRead = FALSE;  
  
      return S_OK;  
   }  
  
   // Can't write data to SQL Server providers (SQLOLEDB/SQLNCLI).  Instead, they read from our object.  
   virtual HRESULT STDMETHODCALLTYPE Write(const void *, ULONG, ULONG * ) {  
      return E_NOTIMPL;  
   }  
  
   // This implementation simply copies data from the source buffer in whatever size requested.  
   // But you can do anything here such as reading from a file, reading from a different rowset, stream, etc.  
   virtual HRESULT STDMETHODCALLTYPE Read(void * pv, ULONG cb, ULONG * pcbRead) {  
      ULONG ulBytesWritten = 0;  
      ULONG ulCBToWrite = cb;  
      ULONG ulCBToCopy;  
      BYTE * pvb = (BYTE *)pv;  
  
      m_fWasRead = TRUE;  
  
      if (NULL == m_pSrcData)  
         return E_FAIL;  
  
      if (NULL == pv)  
         return STG_E_INVALIDPOINTER;  
  
      while (ulBytesWritten < ulCBToWrite && m_ulBytesLeft) {  
         // Make sure we don't write more than our max read size or the size they asked for  
         ulCBToCopy = min(m_ulBytesLeft, cb);  
  
         // Make sure we don't read past the end of the internal buffer  
         ulCBToCopy = min(m_ulBufSize - m_ulReadPos, ulCBToCopy);  
  
         memcpy(pvb, m_pReadPtr + m_ulReadPos, ulCBToCopy);  
         pvb += ulCBToCopy;  
         ulBytesWritten += ulCBToCopy;  
         m_ulBytesLeft -= ulCBToCopy;  
         cb -= ulCBToCopy;  
  
         // Wrap reads around the src buffer  
         m_ulReadPos += ulCBToCopy;  
         if (m_ulReadPos >= m_ulBufSize)  
            m_ulReadPos = 0;  
      }  
  
      if (pcbRead)  
         *pcbRead = ulBytesWritten;  
  
      return S_OK;  
   }  
};  
  
#endif // USE_ISEQSTREAM  
  
HRESULT SetFastLoadProperty(IDBInitialize * pIDBInitialize) {  
   HRESULT hr = S_OK;  
   IDBProperties * pIDBProps = NULL;  
   DBPROP rgProps[1];  
   DBPROPSET PropSet;  
  
   VariantInit(&rgProps[0].vValue);  
  
   rgProps[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
   rgProps[0].colid = DB_NULLID;  
   rgProps[0].vValue.vt = VT_BOOL;  
   rgProps[0].dwPropertyID = SSPROP_ENABLEFASTLOAD;  
  
   rgProps[0].vValue.boolVal = VARIANT_TRUE;  
  
   PropSet.rgProperties = rgProps;  
   PropSet.cProperties = 1;  
   PropSet.guidPropertySet = DBPROPSET_SQLSERVERDATASOURCE;  
  
   if (SUCCEEDED(hr = pIDBInitialize->QueryInterface(IID_IDBProperties, (LPVOID *)&pIDBProps))) {  
      hr = pIDBProps->SetProperties(1, &PropSet);  
   }  
  
   VariantClear(&rgProps[0].vValue);   
  
   if (pIDBProps)  
      pIDBProps->Release();  
  
   return hr;  
}  
  
void wmain() {  
   // Setup the initialization options  
   ULONG cProperties = 0;  
   DBPROP rgProperties[10];  
   ULONG cPropSets = 0;  
   DBPROPSET rgPropSets[1];  
   LPWSTR pwszProgID = L"SQLOLEDB";  
   LPWSTR pwszDataSource = NULL;  
   LPWSTR pwszUserID = NULL;  
   LPWSTR pwszPassword = NULL;  
   LPWSTR pwszProviderString = L"server=(local);trusted_connection=yes;";  
  
   IDBInitialize * pIDBInitialize = NULL;  
   IDBCreateSession * pIDBCrtSess = NULL;  
   IOpenRowset * pIOpenRowset = NULL;  
   IDBCreateCommand * pIDBCrtCmd = NULL;  
   ICommandText * pICmdText = NULL;  
   IAccessor * pIAccessor = NULL;  
   IRowsetFastLoad * pIRowsetFastLoad = NULL;  
   IDBProperties * pIDBProperties = NULL;  
   DBBINDING rgBinding[3];  
   DBBINDSTATUS rgStatus[3];  
   ULONG ulOffset = 0;  
   HACCESSOR hAcc = DB_NULL_HACCESSOR;  
   BYTE * pData = NULL;  
   ULONG iRow = 0;  
   LPWSTR pwszTableName = L"fltest";  
   DBID TableID;  
  
   HRESULT hr;  
  
#ifdef USE_ISEQSTREAM  
   BYTE bSrcBuf[1024];   // A buffer to hold our data for streaming  
   memset((void *)&bSrcBuf, 0xAB, sizeof(bSrcBuf));   // Stream data value 0xAB  
   MySequentialStream * pMySeqStream = new MySequentialStream();  
   DBOBJECT MyObject = {STGM_READ, IID_ISequentialStream};   // NULL pObject implies STGM_READ and IID_IUnknown, but not recommended  
#endif  
  
   memset(rgBinding, 0, ( sizeof(rgBinding) / sizeof(rgBinding[0])) * sizeof(DBBINDING) );  
   TableID.eKind = DBKIND_NAME;  
   TableID.uName.pwszName = pwszTableName;  
  
   // Col1  
   rgBinding[0].iOrdinal = 1;  
   rgBinding[0].wType = DBTYPE_I4;  
   rgBinding[0].obStatus = ulOffset;  
   ulOffset+=sizeof(DBSTATUS);  
   rgBinding[0].obLength = ulOffset;  
   ulOffset+=sizeof(DBLENGTH);  
   rgBinding[0].obValue = ulOffset;  
   ulOffset += sizeof(LONG);  
   rgBinding[0].cbMaxLen = sizeof(LONG);  
   rgBinding[0].dwPart = DBPART_VALUE | DBPART_STATUS | DBPART_LENGTH;  
   rgBinding[0].eParamIO = DBPARAMIO_NOTPARAM;  
   rgBinding[0].dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
  
   //Col2  
   rgBinding[1].iOrdinal = 2;  
   rgBinding[1].wType = DBTYPE_I4;  
   rgBinding[1].obStatus = ulOffset;  
   ulOffset+=sizeof(DBSTATUS);  
   rgBinding[1].obLength = ulOffset;  
   ulOffset+=sizeof(DBLENGTH);  
   rgBinding[1].obValue = ulOffset;  
   ulOffset += sizeof(LONG);  
   rgBinding[1].cbMaxLen = sizeof(LONG);  
   rgBinding[1].dwPart = DBPART_VALUE | DBPART_STATUS | DBPART_LENGTH;  
   rgBinding[1].eParamIO = DBPARAMIO_NOTPARAM;  
   rgBinding[1].dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
  
   //Col3  
   rgBinding[2].iOrdinal = 3;  
   rgBinding[2].obStatus = ulOffset;  
   ulOffset+=sizeof(DBSTATUS);  
   rgBinding[2].obLength = ulOffset;  
   ulOffset+=sizeof(DBLENGTH);  
   rgBinding[2].obValue = ulOffset;  
   rgBinding[2].dwPart = DBPART_VALUE | DBPART_STATUS | DBPART_LENGTH;   // DBPART_LENGTH not needed for providers that don't require length  
   rgBinding[2].eParamIO = DBPARAMIO_NOTPARAM;  
   rgBinding[2].dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
  
#ifdef USE_ISEQSTREAM  
   rgBinding[2].wType = DBTYPE_IUNKNOWN;  
   ulOffset += sizeof(ISequentialStream *);   // Technically should be sizeof(MySequentialStream *), but who's counting?  
   rgBinding[2].cbMaxLen = sizeof(ISequentialStream *);  
   rgBinding[2].pObject = &MyObject;  
#else  
   rgBinding[2].wType = DBTYPE_BYTES;  
   ulOffset += MAX_BLOB;  
   rgBinding[2].cbMaxLen = MAX_BLOB;  
#endif  
  
   // Set init props  
   for ( ULONG i = 0 ; i < sizeof(rgProperties) / sizeof(rgProperties[0]) ; i++ )  
      VariantInit(&rgProperties[i].vValue);  
  
   // Obtain the provider's clsid  
   CLSID clsidProv;  
   hr = CLSIDFromProgID(pwszProgID, &clsidProv);  
  
   // Get our initial connection  
   CoInitialize(NULL);  
  
   if (SUCCEEDED(hr))  
      hr = CoCreateInstance(clsidProv, NULL, CLSCTX_ALL, IID_IDBInitialize,(void **)&pIDBInitialize);  
  
   if (SUCCEEDED(hr))  
      hr = pIDBInitialize->QueryInterface(IID_IDBProperties, (void **)&pIDBProperties);  
  
   // DBPROP_INIT_DATASOURCE  
   if (pwszDataSource) {  
      rgProperties[cProperties].dwPropertyID    = DBPROP_INIT_DATASOURCE;  
      rgProperties[cProperties].dwOptions       = DBPROPOPTIONS_REQUIRED;  
      rgProperties[cProperties].dwStatus        = DBPROPSTATUS_OK;  
      rgProperties[cProperties].colid           = DB_NULLID;  
      rgProperties[cProperties].vValue.vt       = VT_BSTR;  
      V_BSTR(&rgProperties[cProperties].vValue) = SysAllocString(pwszDataSource);                 
      cProperties++;  
   }  
  
   // DBPROP_AUTH_USERID  
   if (pwszUserID) {  
      rgProperties[cProperties].dwPropertyID    = DBPROP_AUTH_USERID;  
      rgProperties[cProperties].dwOptions       = DBPROPOPTIONS_REQUIRED;  
      rgProperties[cProperties].dwStatus        = DBPROPSTATUS_OK;  
      rgProperties[cProperties].colid           = DB_NULLID;  
      rgProperties[cProperties].vValue.vt       = VT_BSTR;  
      V_BSTR(&rgProperties[cProperties].vValue) = SysAllocString(pwszUserID);  
      cProperties++;  
   }  
  
   // DBPROP_AUTH_PASSWORD  
   if (pwszPassword) {  
      rgProperties[cProperties].dwPropertyID    = DBPROP_AUTH_PASSWORD;  
      rgProperties[cProperties].dwOptions       = DBPROPOPTIONS_REQUIRED;  
      rgProperties[cProperties].dwStatus        = DBPROPSTATUS_OK;  
      rgProperties[cProperties].colid           = DB_NULLID;  
      rgProperties[cProperties].vValue.vt       = VT_BSTR;  
      V_BSTR(&rgProperties[cProperties].vValue) = SysAllocString(pwszPassword);  
      cProperties++;  
   }  
  
   // DBPROP_INIT_PROVIDERSTRING  
   if (pwszProviderString) {  
      rgProperties[cProperties].dwPropertyID    = DBPROP_INIT_PROVIDERSTRING;  
      rgProperties[cProperties].dwOptions       = DBPROPOPTIONS_REQUIRED;  
      rgProperties[cProperties].dwStatus        = DBPROPSTATUS_OK;  
      rgProperties[cProperties].colid           = DB_NULLID;  
      rgProperties[cProperties].vValue.vt       = VT_BSTR;  
      V_BSTR(&rgProperties[cProperties].vValue) = SysAllocString(pwszProviderString);  
      cProperties++;  
   }  
  
   if (cProperties) {  
      rgPropSets[cPropSets].cProperties = cProperties;  
      rgPropSets[cPropSets].rgProperties = rgProperties;  
      rgPropSets[cPropSets].guidPropertySet = DBPROPSET_DBINIT;  
      cPropSets++;  
   }  
  
   // Initialize  
   if (SUCCEEDED(hr))  
      hr = pIDBProperties->SetProperties(cPropSets, rgPropSets);  
  
   if (SUCCEEDED(hr))  
      hr = pIDBInitialize->Initialize();  
  
   if (SUCCEEDED(hr)) {  
      printf("\tConnected!\r\n");  
   }  
   else  
      printf("Unable to connect\r\n");  
  
   // Set fastload prop  
   if (SUCCEEDED(hr))  
      hr = SetFastLoadProperty(pIDBInitialize);  
  
   if (SUCCEEDED(hr))  
      hr = pIDBInitialize->QueryInterface(IID_IDBCreateSession, (void **)&pIDBCrtSess);  
  
   if (SUCCEEDED(hr))  
      hr = pIDBCrtSess->CreateSession(NULL, IID_IOpenRowset, (IUnknown **)&pIOpenRowset);  
  
   if (SUCCEEDED(hr))  
      hr = pIOpenRowset->OpenRowset(NULL, &TableID, NULL, IID_IRowsetFastLoad, 0, NULL, (IUnknown **)&pIRowsetFastLoad);  
  
   if (SUCCEEDED(hr))  
      hr = pIRowsetFastLoad->QueryInterface(IID_IAccessor, (void **)&pIAccessor);  
  
   if (SUCCEEDED(hr))  
      hr = pIAccessor->CreateAccessor(DBACCESSOR_ROWDATA, 3, rgBinding, ulOffset, &hAcc, (DBBINDSTATUS *)&rgStatus);  
  
   if (SUCCEEDED(hr)) {  
      pData = (BYTE *)malloc(ulOffset);  
  
      for (iRow = 0 ; iRow < MAX_ROWS ; iRow++) {  
         // Column 1 data          
         *(DBSTATUS *)(pData + rgBinding[0].obStatus) = DBSTATUS_S_OK;  
         *(DBLENGTH *)(pData + rgBinding[0].obLength) = 1234567;   // Ignored for I4 data  
         *(LONG *)(pData + rgBinding[0].obValue) = iRow;  
  
         // Column 2 data          
         *(DBSTATUS *)(pData + rgBinding[1].obStatus) = DBSTATUS_S_OK;  
         *(DBLENGTH *)(pData + rgBinding[1].obLength) = 1234567;   // Ignored for I4 data  
         *(LONG *)(pData + rgBinding[1].obValue) = iRow + 1;  
  
         // Column 3 data          
         *(DBSTATUS *)(pData + rgBinding[2].obStatus) = DBSTATUS_S_OK;  
         *(DBLENGTH *)(pData + rgBinding[2].obLength) = MAX_BLOB/(iRow + 1);   // Not needed for providers that don't require length  
#ifdef USE_ISEQSTREAM  
         // DBLENGTH is used to tell the provider how much BLOB data to expect from the stream, not required  
         // if provider supports sending data without length  
         *(ISequentialStream **)(pData+rgBinding[2].obValue) = (ISequentialStream *)pMySeqStream;   
         pMySeqStream->Init((void *)&bSrcBuf, sizeof(bSrcBuf), MAX_BLOB / (iRow + 1));   // Here we set the size we will let the provider read  
         pMySeqStream->AddRef();   // The provider releases the object, so we addref it so it doesn't get destructed  
#else  
         memset(pData + rgBinding[2].obValue, 0, MAX_BLOB);   // Not strictly necessary  
         memset(pData + rgBinding[2].obValue, 0x23, MAX_BLOB / (iRow + 1));   
#endif  
         if (SUCCEEDED(hr))  
            hr = pIRowsetFastLoad->InsertRow(hAcc, pData);  
      }  
   }  
  
   if (SUCCEEDED(hr))  
      hr = pIRowsetFastLoad->Commit(TRUE);  
  
   if (hAcc)  
      pIAccessor->ReleaseAccessor(hAcc, NULL);  
  
   SAFE_RELEASE(pIDBInitialize);  
   SAFE_RELEASE(pIDBCrtSess);  
   SAFE_RELEASE(pIOpenRowset);  
   SAFE_RELEASE(pIDBCrtCmd);  
   SAFE_RELEASE(pICmdText);  
   SAFE_RELEASE(pIAccessor);  
   SAFE_RELEASE(pIRowsetFastLoad);  
   SAFE_RELEASE(pIDBProperties);  
#ifdef USE_ISEQSTREAM  
   SAFE_RELEASE(pMySeqStream);  
#endif  
  
   if (pData)  
      free(pData);  
  
   CoUninitialize();  
}  
```  
  
```  
use master  
drop table fltest  
```  
  
  
