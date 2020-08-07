---
title: IBCPSession::BCPWriteFmt (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPWriteFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPWriteFmt method
ms.assetid: add50425-2ed6-411a-a391-4ce63c364892
author: rothja
ms.author: jroth
ms.openlocfilehash: ee4dcb5809c0f0fbb6d3f7aba6f4af5f6991e0e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582446"
---
# <a name="ibcpsessionbcpwritefmt-ole-db"></a><span data-ttu-id="1c519-102">IBCPSession::BCPWriteFmt (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="1c519-102">IBCPSession::BCPWriteFmt (OLE DB)</span></span>
  <span data-ttu-id="1c519-103">Grava informações de formato relativas a cada coluna no arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="1c519-103">Writes format information for each column to the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c519-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1c519-104">Syntax</span></span>  
  
```  
  
HRESULT BCPWriteFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="1c519-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="1c519-105">Remarks</span></span>  
 <span data-ttu-id="1c519-106">O arquivo de formato especifica o formato de dados de um arquivo de dados criado por cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="1c519-106">The format file specifies the data format of a data file created by bulk copy.</span></span> <span data-ttu-id="1c519-107">As chamadas aos métodos [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) e [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) definem o formato do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="1c519-107">Calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods define the format of the data file.</span></span> <span data-ttu-id="1c519-108">O método **BCPWriteFmt** salva essa definição no arquivo referenciado pelo argumento pwszFormatFile.</span><span class="sxs-lookup"><span data-stu-id="1c519-108">The **BCPWriteFmt** method saves this definition in the file referenced by the pwszFormatFile argument.</span></span>  
  
 <span data-ttu-id="1c519-109">O método **BCPWriteFmt** pode salvar os arquivos de formato em xml ou formato de texto.</span><span class="sxs-lookup"><span data-stu-id="1c519-109">The **BCPWriteFmt** method can save the format files in either xml or text format.</span></span> <span data-ttu-id="1c519-110">Isso precisa ser indicado usando a opção de controle BCP_OPTION_XML com o método [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="1c519-110">This must be indicated by using the BCP_OPTION_XML control option with the [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="1c519-111">Para carregar um arquivo de formato salvo, use o método [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="1c519-111">To load a saved format file, use the [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md) method.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="1c519-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1c519-112">Arguments</span></span>  
 <span data-ttu-id="1c519-113">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="1c519-113">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="1c519-114">O caminho e o nome do arquivo que contém os valores de formato do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="1c519-114">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="1c519-115">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="1c519-115">Return Code Values</span></span>  
 <span data-ttu-id="1c519-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c519-116">S_OK</span></span>  
 <span data-ttu-id="1c519-117">O método foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="1c519-117">The method succeeded.</span></span>  
  
 <span data-ttu-id="1c519-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1c519-118">E_FAIL</span></span>  
 <span data-ttu-id="1c519-119">Ocorreu um erro específico do provedor; para obter informações detalhadas, use a interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="1c519-119">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="1c519-120">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1c519-120">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="1c519-121">Erro de memória insuficiente.</span><span class="sxs-lookup"><span data-stu-id="1c519-121">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="1c519-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="1c519-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="1c519-123">A chamada para o método era inesperada.</span><span class="sxs-lookup"><span data-stu-id="1c519-123">The call to the method was unexpected.</span></span> <span data-ttu-id="1c519-124">Por exemplo, o método [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) não foi chamado antes desse método.</span><span class="sxs-lookup"><span data-stu-id="1c519-124">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c519-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1c519-125">See Also</span></span>  
 <span data-ttu-id="1c519-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="1c519-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="1c519-127">Executando operações de cópia em massa</span><span class="sxs-lookup"><span data-stu-id="1c519-127">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
