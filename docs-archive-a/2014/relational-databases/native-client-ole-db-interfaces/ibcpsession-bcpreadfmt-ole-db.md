---
title: IBCPSession::BCPReadFmt (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPReadFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPReadFmt method
ms.assetid: e2a12050-94e4-48a3-8a48-b780d646f116
author: rothja
ms.author: jroth
ms.openlocfilehash: ca811dceb8ab6771e3bdd6689a8e11eca6a0e3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684689"
---
# <a name="ibcpsessionbcpreadfmt-ole-db"></a><span data-ttu-id="7f454-102">IBCPSession::BCPReadFmt (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7f454-102">IBCPSession::BCPReadFmt (OLE DB)</span></span>
  <span data-ttu-id="7f454-103">Lê informações de formato relativas a cada coluna no arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="7f454-103">Reads format information for each column from the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f454-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7f454-104">Syntax</span></span>  
  
```  
  
HRESULT BCPReadFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="7f454-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="7f454-105">Remarks</span></span>  
 <span data-ttu-id="7f454-106">O método **BCPReadFmt** é usado para ler dados de um arquivo de formato que especifica o formato de dados no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="7f454-106">The **BCPReadFmt** method is used for reading data from a format file that specifies the format of data in the data file.</span></span> <span data-ttu-id="7f454-107">Este método é capaz de detectar a versão correta do arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="7f454-107">This method is capable of detecting the correct version of the format file.</span></span> <span data-ttu-id="7f454-108">Ele pode detectar automaticamente se o arquivo de formato está em xml ou formato de texto de estilo antigo e se comporta adequadamente.</span><span class="sxs-lookup"><span data-stu-id="7f454-108">It can automatically detect whether the format file is in xml or old style text format and behaves accordingly.</span></span> <span data-ttu-id="7f454-109">O BCP do provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client dá suporte às versões 6.0 ou mais recentes dos arquivos de formato.</span><span class="sxs-lookup"><span data-stu-id="7f454-109">The format file versions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider BCP are version 6.0 or newer.</span></span>  
  
 <span data-ttu-id="7f454-110">Depois que o método **BCPReadFmt** lê os valores de formato, ele faz as chamadas apropriadas aos métodos [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) e [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="7f454-110">After the **BCPReadFmt** method reads the format values, it makes the appropriate calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods.</span></span> <span data-ttu-id="7f454-111">Não há necessidade de o usuário analisar um arquivo de formato e fazer essas chamadas.</span><span class="sxs-lookup"><span data-stu-id="7f454-111">There is no need for the user to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="7f454-112">Para salvar um arquivo de formato, chame o método [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="7f454-112">To save a format file, call the [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md) method.</span></span> <span data-ttu-id="7f454-113">As chamadas ao método **BCPReadFmt** podem referenciar formatos salvos.</span><span class="sxs-lookup"><span data-stu-id="7f454-113">Calls to the **BCPReadFmt** method can reference saved formats.</span></span> <span data-ttu-id="7f454-114">Como alternativa, o utilitário de cópia em massa (**bcp**) pode salvar formatos de dados definidos pelo usuário em arquivos que podem ser referenciados pelo método **BCPReadFmt** .</span><span class="sxs-lookup"><span data-stu-id="7f454-114">Alternatively, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by the **BCPReadFmt** method.</span></span>  
  
 <span data-ttu-id="7f454-115">O `BCP_OPTION_DELAYREADFMT` valor do parâmetro *EOption* de [IBCPSession:: BCPControl](ibcpsession-bcpcontrol-ole-db.md) modifica o comportamento de IBCPSession:: BCPReadFmt.</span><span class="sxs-lookup"><span data-stu-id="7f454-115">The `BCP_OPTION_DELAYREADFMT` value of the *eOption* parameter of [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) modifies the behavior of IBCPSession::BCPReadFmt.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="7f454-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7f454-116">Arguments</span></span>  
 <span data-ttu-id="7f454-117">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="7f454-117">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="7f454-118">O caminho e o nome do arquivo que contém os valores de formato do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="7f454-118">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="7f454-119">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="7f454-119">Return Code Values</span></span>  
 <span data-ttu-id="7f454-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f454-120">S_OK</span></span>  
 <span data-ttu-id="7f454-121">O método foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="7f454-121">The method succeeded.</span></span>  
  
 <span data-ttu-id="7f454-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7f454-122">E_FAIL</span></span>  
 <span data-ttu-id="7f454-123">Erro específico do provedor. Para obter informações detalhadas, use a interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="7f454-123">A provider-specific error occurred, for detailed information use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="7f454-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7f454-124">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="7f454-125">Erro de memória insuficiente.</span><span class="sxs-lookup"><span data-stu-id="7f454-125">Out of memory error.</span></span>  
  
 <span data-ttu-id="7f454-126">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="7f454-126">E_UNEXPECTED</span></span>  
 <span data-ttu-id="7f454-127">A chamada para o método era inesperada.</span><span class="sxs-lookup"><span data-stu-id="7f454-127">The call to the method was unexpected.</span></span> <span data-ttu-id="7f454-128">Por exemplo, o método [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) não foi chamado antes desse método.</span><span class="sxs-lookup"><span data-stu-id="7f454-128">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f454-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7f454-129">See Also</span></span>  
 <span data-ttu-id="7f454-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="7f454-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="7f454-131">Executando operações de cópia em massa</span><span class="sxs-lookup"><span data-stu-id="7f454-131">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
