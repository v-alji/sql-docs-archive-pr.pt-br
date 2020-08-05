---
title: Interface IMDEmbedded | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 9dba8c68-4bef-4c2b-815c-c286f1a1939b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 331f8c33f7748e6591acd6d6ecda7a03ef7d8137
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572236"
---
# <a name="imdembedded-interface"></a><span data-ttu-id="a5634-102">Interface IMDEmbedded</span><span class="sxs-lookup"><span data-stu-id="a5634-102">IMDEmbedded Interface</span></span>
  <span data-ttu-id="a5634-103">A interface IMDEmbedded é uma interface pública usada para gerenciar um banco de dados do PowerPivot inserido ou um banco de dados modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="a5634-103">The IMDEmbedded interface is a public interface used to manage an embedded PowerPivot database or a tabular model database.</span></span> <span data-ttu-id="a5634-104">A interface herda da interface `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="a5634-104">The interface inherits from the `IPersistStream` interface.</span></span> <span data-ttu-id="a5634-105">A interface permite as seguintes operações:</span><span class="sxs-lookup"><span data-stu-id="a5634-105">The interface allows for the following operations:</span></span>  
  
-   <span data-ttu-id="a5634-106">Obter um identificador do fluxo inserido no documento contêiner.</span><span class="sxs-lookup"><span data-stu-id="a5634-106">Get an identifier to the embedded stream in the container document.</span></span>  
  
-   <span data-ttu-id="a5634-107">Definir a URL do documento contêiner.</span><span class="sxs-lookup"><span data-stu-id="a5634-107">Set the URL of the containing document.</span></span>  
  
-   <span data-ttu-id="a5634-108">Definir um sinalizador para indicar se o aplicativo inserido está em um ambiente hospedado.</span><span class="sxs-lookup"><span data-stu-id="a5634-108">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
-   <span data-ttu-id="a5634-109">Definir o caminho para os arquivos temporários usados pelo aplicativo inserido.</span><span class="sxs-lookup"><span data-stu-id="a5634-109">Set the path to temporary files used by the embedding application.</span></span>  
  
-   <span data-ttu-id="a5634-110">Cancelar a operação inserida atual.</span><span class="sxs-lookup"><span data-stu-id="a5634-110">Cancel the current embedded operation.</span></span>  
  
-   <span data-ttu-id="a5634-111">Obter o tamanho estimado (em bytes) do fluxo para salvar o objeto inserido.</span><span class="sxs-lookup"><span data-stu-id="a5634-111">Get the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="a5634-112">Herdado de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="a5634-112">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="a5634-113">Verificar se o banco de dados inserido foi alterado após ser salvo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="a5634-113">Verify if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="a5634-114">Herdado de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="a5634-114">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="a5634-115">Carregar o banco de dados inserido para o mecanismo local ou em processo.</span><span class="sxs-lookup"><span data-stu-id="a5634-115">Load the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="a5634-116">Herdado de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="a5634-116">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="a5634-117">Salvar o banco de dados local ou em processo para o fluxo inserido no documento contêiner.</span><span class="sxs-lookup"><span data-stu-id="a5634-117">Save the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="a5634-118">Herdado de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="a5634-118">Inherited from `IPersistStream`.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a5634-119">Referência</span><span class="sxs-lookup"><span data-stu-id="a5634-119">Reference</span></span>  
 <span data-ttu-id="a5634-120">A referência a seguir documenta a `IMDEmbedded` interface como apresentada no arquivo de cabeçalho **Msmd. h** .</span><span class="sxs-lookup"><span data-stu-id="a5634-120">The following reference documents the `IMDEmbedded` interface as presented in **msmd.h** header file.</span></span>  
  
### <a name="source-file-pxoembeddeddataidl"></a><span data-ttu-id="a5634-121">Arquivo de origem: PXOEmbeddedData.idl</span><span class="sxs-lookup"><span data-stu-id="a5634-121">Source file: PXOEmbeddedData.idl</span></span>  
  
```  
[  
  local,                            
  object,                           
  uuid(6B6691CF-5453-41c2-ADD9-4F320B7FD421),                       
  pointer_default(unique)           
]  
interface IMDEmbeddedData : IPersistStream  
{  
 [id(1), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in] BOOL in_fIsHosted);  
  
 [id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
  
 [id(3), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
  
 [id(4), helpstring("Set the path used by the embedding application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
  
 [id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
};  
```  
  
### <a name="imdembeddeddatagetstreamidentifier"></a><span data-ttu-id="a5634-122">IMDEmbeddedData::GetStreamIdentifier</span><span class="sxs-lookup"><span data-stu-id="a5634-122">IMDEmbeddedData::GetStreamIdentifier</span></span>  
  
```  
HRESULT GetStreamIdentifier (  
    [out, retval] BSTR * out_pbstrStreamId  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="a5634-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5634-123">Description</span></span>  
 <span data-ttu-id="a5634-124">Obtém o identificador usado pelo aplicativo de host para o fluxo inserido no documento contêiner.</span><span class="sxs-lookup"><span data-stu-id="a5634-124">Gets the identifier used by the host application to the embedded stream in the container document.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="a5634-125">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a5634-125">Parameters</span></span>  
 <span data-ttu-id="a5634-126">*out_pbstrStreamId*</span><span class="sxs-lookup"><span data-stu-id="a5634-126">*out_pbstrStreamId*</span></span>  
 <span data-ttu-id="a5634-127">Especifica o local do identificador de fluxo.</span><span class="sxs-lookup"><span data-stu-id="a5634-127">Specifies the location of the stream identifier.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="a5634-128">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="a5634-128">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="a5634-129">O identificador de fluxo foi retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="a5634-129">The stream identifier was successfully returned.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="a5634-130">Não há nenhum identificador de fluxo.</span><span class="sxs-lookup"><span data-stu-id="a5634-130">There is no stream identifier.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="a5634-131">Erro ao acessar o identificador de fluxo.</span><span class="sxs-lookup"><span data-stu-id="a5634-131">An error occurred accessing the stream identifier.</span></span>  
  
#### <a name="remarks"></a><span data-ttu-id="a5634-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="a5634-132">Remarks</span></span>  
 <span data-ttu-id="a5634-133">Para verificar se a conexão atual contém um banco de dados inserido, o usuário deve verificar o valor da propriedade DBPROP_MSMD_EMBEDDED_DATA nas propriedades de conexão OLE DB.</span><span class="sxs-lookup"><span data-stu-id="a5634-133">To verify if the current connection contains an embedded database, the user should check the value of the DBPROP_MSMD_EMBEDDED_DATA property from the OLE DB connection properties.</span></span>  
  
 <span data-ttu-id="a5634-134">Os valores possíveis para DBPROP_MSMD_EMBEDDED_DATA são:</span><span class="sxs-lookup"><span data-stu-id="a5634-134">The possible values for DBPROP_MSMD_EMBEDDED_DATA are:</span></span>  
  
|<span data-ttu-id="a5634-135">Nome</span><span class="sxs-lookup"><span data-stu-id="a5634-135">Name</span></span>|<span data-ttu-id="a5634-136">Valor</span><span class="sxs-lookup"><span data-stu-id="a5634-136">Value</span></span>|<span data-ttu-id="a5634-137">Definição</span><span class="sxs-lookup"><span data-stu-id="a5634-137">Definition</span></span>|  
|----------|-----------|----------------|  
|<span data-ttu-id="a5634-138">DBPROPVAL_EMBED_NONE</span><span class="sxs-lookup"><span data-stu-id="a5634-138">DBPROPVAL_EMBED_NONE</span></span>|<span data-ttu-id="a5634-139">0x00</span><span class="sxs-lookup"><span data-stu-id="a5634-139">0x00</span></span>|<span data-ttu-id="a5634-140">Nenhum banco de dados inserido disponível</span><span class="sxs-lookup"><span data-stu-id="a5634-140">No embedded database available</span></span>|  
|<span data-ttu-id="a5634-141">DBPROPVAL_EMBED_EMBEDDED</span><span class="sxs-lookup"><span data-stu-id="a5634-141">DBPROPVAL_EMBED_EMBEDDED</span></span>|<span data-ttu-id="a5634-142">0x01</span><span class="sxs-lookup"><span data-stu-id="a5634-142">0x01</span></span>|<span data-ttu-id="a5634-143">O aplicativo atual contém o banco de dados inserido</span><span class="sxs-lookup"><span data-stu-id="a5634-143">The current application contains the embedded database</span></span>|  
|<span data-ttu-id="a5634-144">DBPROPVAL_EMBED_LINKED</span><span class="sxs-lookup"><span data-stu-id="a5634-144">DBPROPVAL_EMBED_LINKED</span></span>|<span data-ttu-id="a5634-145">0x02</span><span class="sxs-lookup"><span data-stu-id="a5634-145">0x02</span></span>|<span data-ttu-id="a5634-146">O banco de dados inserido está hospedado em um aplicativo remoto (p. ex., SharePoint Server)</span><span class="sxs-lookup"><span data-stu-id="a5634-146">The embedded database is hosted in a remote application (i.e. SharePoint Server)</span></span>|  
  
#### <a name="source"></a><span data-ttu-id="a5634-147">Fonte</span><span class="sxs-lookup"><span data-stu-id="a5634-147">Source</span></span>  
  
```  
[id(1), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
```  
  
### <a name="imdembeddeddatasetcontainerurl"></a><span data-ttu-id="a5634-148">IMDEmbeddedData::SetContainerURL</span><span class="sxs-lookup"><span data-stu-id="a5634-148">IMDEmbeddedData::SetContainerURL</span></span>  
  
```  
HRESULT SetContainerURL (  
    [in] BSTR in_bstrURL  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="a5634-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5634-149">Description</span></span>  
 <span data-ttu-id="a5634-150">Define a URL para o arquivo que contém o fluxo inserido.</span><span class="sxs-lookup"><span data-stu-id="a5634-150">Sets the URL for the file containing the embedded stream.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="a5634-151">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a5634-151">Parameters</span></span>  
 <span data-ttu-id="a5634-152">*in_bstrURL*</span><span class="sxs-lookup"><span data-stu-id="a5634-152">*in_bstrURL*</span></span>  
 <span data-ttu-id="a5634-153">Especifica a URL para o documento contêiner.</span><span class="sxs-lookup"><span data-stu-id="a5634-153">Specifies the URL for the containing document.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="a5634-154">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="a5634-154">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="a5634-155">A URL do contêiner foi definida com êxito.</span><span class="sxs-lookup"><span data-stu-id="a5634-155">The container URL was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="a5634-156">Erro ao definir a URL do contêiner.</span><span class="sxs-lookup"><span data-stu-id="a5634-156">An error occurred while setting the container URL.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="a5634-157">Fonte</span><span class="sxs-lookup"><span data-stu-id="a5634-157">Source</span></span>  
  
```  
[id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
```  
  
### <a name="imdembeddeddatasethosted"></a><span data-ttu-id="a5634-158">IMDEmbeddedData::SetHosted</span><span class="sxs-lookup"><span data-stu-id="a5634-158">IMDEmbeddedData::SetHosted</span></span>  
  
```  
HRESULT SetHosted (  
    [in] BOOL in_fIsHosted  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="a5634-159">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5634-159">Description</span></span>  
 <span data-ttu-id="a5634-160">Definir um sinalizador para indicar se o aplicativo inserido está em um ambiente hospedado.</span><span class="sxs-lookup"><span data-stu-id="a5634-160">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="a5634-161">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a5634-161">Parameters</span></span>  
 <span data-ttu-id="a5634-162">*in_ftHosted*</span><span class="sxs-lookup"><span data-stu-id="a5634-162">*in_ftHosted*</span></span>  
 <span data-ttu-id="a5634-163">TRUE se o chamador estiver hospedado em um aplicativo de serviço (como o IIS).</span><span class="sxs-lookup"><span data-stu-id="a5634-163">TRUE if caller is in a hosted in a service application (like IIS).</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="a5634-164">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="a5634-164">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="a5634-165">O sinalizador foi definido com êxito.</span><span class="sxs-lookup"><span data-stu-id="a5634-165">The flag was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="a5634-166">Erro ao definir o sinalizador.</span><span class="sxs-lookup"><span data-stu-id="a5634-166">An error occurred while setting the flag.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="a5634-167">Fonte</span><span class="sxs-lookup"><span data-stu-id="a5634-167">Source</span></span>  
  
```  
[id(5), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in]  BOOL in_fIsHosted);  
```  
  
### <a name="imdembeddeddatasettempdirpath"></a><span data-ttu-id="a5634-168">IMDEmbeddedData::SetTempDirPath</span><span class="sxs-lookup"><span data-stu-id="a5634-168">IMDEmbeddedData::SetTempDirPath</span></span>  
  
```  
HRESULT SetTempDirPath (  
    [in] BSTR in_bstrPath  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="a5634-169">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5634-169">Description</span></span>  
 <span data-ttu-id="a5634-170">Definir o caminho para os arquivos temporários usados pelo aplicativo inserido.</span><span class="sxs-lookup"><span data-stu-id="a5634-170">Set the path to temporary files used by the embedding application.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="a5634-171">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a5634-171">Parameters</span></span>  
 <span data-ttu-id="a5634-172">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="a5634-172">*in_bstrPath*</span></span>  
 <span data-ttu-id="a5634-173">O caminho usado pelo aplicativo de host para arquivos temporários.</span><span class="sxs-lookup"><span data-stu-id="a5634-173">The path used by the host application for temporary files.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="a5634-174">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="a5634-174">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="a5634-175">O diretório de arquivos temporários foi definido com êxito.</span><span class="sxs-lookup"><span data-stu-id="a5634-175">The temporary file directory was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="a5634-176">Erro ao definir o caminho.</span><span class="sxs-lookup"><span data-stu-id="a5634-176">An error occurred while setting the path.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="a5634-177">Fonte</span><span class="sxs-lookup"><span data-stu-id="a5634-177">Source</span></span>  
  
```  
[id(4), helpstring("Set the path used by the host application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
```  
  
### <a name="imdembeddeddatacancel"></a><span data-ttu-id="a5634-178">IMDEmbeddedData::Cancel</span><span class="sxs-lookup"><span data-stu-id="a5634-178">IMDEmbeddedData::Cancel</span></span>  
  
```  
HRESULT Cancel ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="a5634-179">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5634-179">Description</span></span>  
 <span data-ttu-id="a5634-180">Cancela a operação de banco de dados inserida atual.</span><span class="sxs-lookup"><span data-stu-id="a5634-180">Cancels the current embedded database operation</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="a5634-181">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a5634-181">Parameters</span></span>  
 <span data-ttu-id="a5634-182">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a5634-182">None.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="a5634-183">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="a5634-183">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="a5634-184">A operação foi cancelada com êxito.</span><span class="sxs-lookup"><span data-stu-id="a5634-184">The operation was successfully cancelled.</span></span>  
  
 `DB_E_CANTCANCEL`  
 <span data-ttu-id="a5634-185">Nenhuma operação cancelável está em andamento atualmente.</span><span class="sxs-lookup"><span data-stu-id="a5634-185">No cancellable operation is currently in progress.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="a5634-186">Erro ao cancelar a operação inserida.</span><span class="sxs-lookup"><span data-stu-id="a5634-186">An error occurred while cancelling the embedded operation.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="a5634-187">Fonte</span><span class="sxs-lookup"><span data-stu-id="a5634-187">Source</span></span>  
  
```  
[id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
```  
  
### <a name="imdembeddeddatagetsizemax-ipersiststreamgetsizemax"></a><span data-ttu-id="a5634-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span><span class="sxs-lookup"><span data-stu-id="a5634-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span></span>  
  
```  
HRESULT GetSizeMax (  
    [out] ULARGE_INTEGER * out_pcbSize  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="a5634-189">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5634-189">Description</span></span>  
 <span data-ttu-id="a5634-190">Obtém o tamanho estimado (em bytes) do fluxo para salvar o objeto inserido.</span><span class="sxs-lookup"><span data-stu-id="a5634-190">Gets the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="a5634-191">Herdado de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="a5634-191">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="a5634-192">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a5634-192">Parameters</span></span>  
 <span data-ttu-id="a5634-193">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="a5634-193">*in_bstrPath*</span></span>  
 <span data-ttu-id="a5634-194">O tamanho estimado (em bytes) da imagem de banco de dados inserida.</span><span class="sxs-lookup"><span data-stu-id="a5634-194">The estimated size (in bytes) of the embedded database image.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="a5634-195">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="a5634-195">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="a5634-196">O tamanho foi obtido com êxito.</span><span class="sxs-lookup"><span data-stu-id="a5634-196">The size was successfully obtained.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="a5634-197">Erro ao obter o tamanho.</span><span class="sxs-lookup"><span data-stu-id="a5634-197">An error occurred while obtaining the size.</span></span>  
  
### <a name="imdembeddeddataisdirty-ipersiststreamisdirty"></a><span data-ttu-id="a5634-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span><span class="sxs-lookup"><span data-stu-id="a5634-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span></span>  
  
```  
HRESULT IsDirty ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="a5634-199">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5634-199">Description</span></span>  
 <span data-ttu-id="a5634-200">Verifica se o banco de dados inserido foi alterado após ser salvo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="a5634-200">Verifies if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="a5634-201">Herdado de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="a5634-201">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="a5634-202">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a5634-202">Parameters</span></span>  
 <span data-ttu-id="a5634-203">none</span><span class="sxs-lookup"><span data-stu-id="a5634-203">none</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="a5634-204">Valor(es) de retorno</span><span class="sxs-lookup"><span data-stu-id="a5634-204">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="a5634-205">O banco de dados foi alterado desde que foi salvo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="a5634-205">The database has changed since it was last saved.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="a5634-206">O banco de dados não foi alterado desde que foi salvo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="a5634-206">The database has not changed since it was last saved.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="a5634-207">Erro ao obter o estado do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a5634-207">An error occurred while obtaining the database state.</span></span>  
  
### <a name="imdembeddeddataload-ipersiststreamload"></a><span data-ttu-id="a5634-208">IMDEmbeddedData::Load (IPersistStream::Load)</span><span class="sxs-lookup"><span data-stu-id="a5634-208">IMDEmbeddedData::Load (IPersistStream::Load)</span></span>  
  
```  
HRESULT Load (   
    [in] IStream * in_pStm   
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="a5634-209">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5634-209">Description</span></span>  
 <span data-ttu-id="a5634-210">Carrega o banco de dados inserido para o mecanismo local ou em processo.</span><span class="sxs-lookup"><span data-stu-id="a5634-210">Loads the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="a5634-211">Herdado de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="a5634-211">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="a5634-212">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a5634-212">Parameters</span></span>  
 <span data-ttu-id="a5634-213">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="a5634-213">*in_pStm*</span></span>  
 <span data-ttu-id="a5634-214">Um ponteiro para uma interface de fluxo da qual deverá ser carregado o banco de dados inserido.</span><span class="sxs-lookup"><span data-stu-id="a5634-214">A pointer to a stream interface from where to load the embedded database.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="a5634-215">Valor(es) de retorno</span><span class="sxs-lookup"><span data-stu-id="a5634-215">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="a5634-216">O banco de dados foi carregado com êxito.</span><span class="sxs-lookup"><span data-stu-id="a5634-216">The database was successfully loaded.</span></span>  
  
 `E_OUTOFMEMORY`  
 <span data-ttu-id="a5634-217">Memória insuficiente para carregar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a5634-217">Not enough memory to load the database.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="a5634-218">Erro diferente de `E_OUTOFMEMORY` ao carregar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a5634-218">An error occurred while loading the database, different than `E_OUTOFMEMORY`.</span></span>  
  
### <a name="imdembeddeddatasave-ipersiststreamsave"></a><span data-ttu-id="a5634-219">IMDEmbeddedData::Save (IPersistStream::Save)</span><span class="sxs-lookup"><span data-stu-id="a5634-219">IMDEmbeddedData::Save (IPersistStream::Save)</span></span>  
  
```  
HRESULT Save (   
    [in] IStream * in_pStm,  
    [in] BOOL in_fClearDirty  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="a5634-220">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5634-220">Description</span></span>  
 <span data-ttu-id="a5634-221">Salva o banco de dados local ou em processo para o fluxo inserido no documento contêiner.</span><span class="sxs-lookup"><span data-stu-id="a5634-221">Saves the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="a5634-222">Herdado de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="a5634-222">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="a5634-223">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a5634-223">Parameters</span></span>  
 <span data-ttu-id="a5634-224">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="a5634-224">*in_pStm*</span></span>  
 <span data-ttu-id="a5634-225">Um ponteiro para uma interface de fluxo na qual deverá ser salvo o banco de dados inserido.</span><span class="sxs-lookup"><span data-stu-id="a5634-225">A pointer to a stream interface to where to save the embedded database.</span></span>  
  
 <span data-ttu-id="a5634-226">*in_fClearDirty*</span><span class="sxs-lookup"><span data-stu-id="a5634-226">*in_fClearDirty*</span></span>  
 <span data-ttu-id="a5634-227">Um sinalizador que indica se o sinalizador sujo deve ser limpo após esta operação.</span><span class="sxs-lookup"><span data-stu-id="a5634-227">A flag that indicates whether the dirty flag should be cleared after this operation.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="a5634-228">Valor(es) de retorno</span><span class="sxs-lookup"><span data-stu-id="a5634-228">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="a5634-229">O banco de dados foi salvo com êxito.</span><span class="sxs-lookup"><span data-stu-id="a5634-229">The database was successfully saved.</span></span>  
  
 `STG_E_CANTSAVE`  
 <span data-ttu-id="a5634-230">Erro diferente de `STG_E_MEDIUMFULL` ao salvar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a5634-230">An error occurred while saving the database, different than `STG_E_MEDIUMFULL`.</span></span>  
  
 `STG_E_MEDIUMFULL`  
 <span data-ttu-id="a5634-231">Não foi possível salvar o banco de dados porque não há espaço remanescente no dispositivo de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="a5634-231">The database could not be saved because there is no space left on the storage device.</span></span>  
  
  
