---
title: IBCPSession::BCPColumns (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPColumns (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPColumns method
ms.assetid: c338abe8-9e30-4853-a7c6-b1a6c00095e1
author: rothja
ms.author: jroth
ms.openlocfilehash: c842b2a815074c0db7e6ab21e0a85eac68a986a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684694"
---
# <a name="ibcpsessionbcpcolumns-ole-db"></a><span data-ttu-id="4bfab-102">IBCPSession::BCPColumns (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="4bfab-102">IBCPSession::BCPColumns (OLE DB)</span></span>
  <span data-ttu-id="4bfab-103">Define o número de campos que devem ser associados às colunas de uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bfab-103">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bfab-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4bfab-104">Syntax</span></span>  
  
```  
  
HRESULT BCPColumns(   
DBCOUNTITEMnColumns);  
```  
  
## <a name="remarks"></a><span data-ttu-id="4bfab-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="4bfab-105">Remarks</span></span>  
 <span data-ttu-id="4bfab-106">Internamente, ele chama [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) para definir os valores padrão para dados de campo.</span><span class="sxs-lookup"><span data-stu-id="4bfab-106">Internally it calls [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) to set the default values for field data.</span></span> <span data-ttu-id="4bfab-107">Esses valores padrão são obtidos nas informações de coluna do SQL Server que o provedor recupera internamente quando o nome da tabela é especificado por meio de [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="4bfab-107">These default values are obtained from the SQL Server column information that the provider internally retrieves when the table name is specified through [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4bfab-108"> Esse método só pode ser chamado depois que **BCPInit** foi chamado com um nome de arquivo válido.</span><span class="sxs-lookup"><span data-stu-id="4bfab-108">This method can be called only after **BCPInit** has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="4bfab-109">Você só deve chamar esse método se pretender usar um formato de arquivo de usuário diferente do padrão.</span><span class="sxs-lookup"><span data-stu-id="4bfab-109">You should call this method only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="4bfab-110">Para obter mais informações sobre uma descrição do formato de arquivo de usuário padrão, consulte o método **BCPInit** .</span><span class="sxs-lookup"><span data-stu-id="4bfab-110">For more information about a description of the default user-file format, see the **BCPInit** method.</span></span>  
  
 <span data-ttu-id="4bfab-111">Depois de chamar o método **BCPColumns** , você precisa chamar o método **BCPColFmt** para cada coluna no arquivo de usuário para definir completamente um formato de arquivo personalizado.</span><span class="sxs-lookup"><span data-stu-id="4bfab-111">After calling the **BCPColumns** method, you must call the **BCPColFmt** method for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="4bfab-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4bfab-112">Arguments</span></span>  
 <span data-ttu-id="4bfab-113">*nColumns*[in]</span><span class="sxs-lookup"><span data-stu-id="4bfab-113">*nColumns*[in]</span></span>  
 <span data-ttu-id="4bfab-114">O número total de campos no arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="4bfab-114">The total number of fields in the user file.</span></span> <span data-ttu-id="4bfab-115">Mesmo se você estiver se preparando para copiar em massa os dados do arquivo de usuário para uma tabela do SQL Server e não pretender copiar todos os campos no arquivo de usuário, ainda assim será necessário definir o argumento *nColumns* como o número total de campos de arquivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="4bfab-115">Even if you are preparing to bulk copy data from the user file to a SQL Server table and do not intend to copy all fields in the user file, you must still set the *nColumns* argument to the total number of user-file fields.</span></span> <span data-ttu-id="4bfab-116">Os campos ignorados podem ser especificados através de **BCPColFmt**.</span><span class="sxs-lookup"><span data-stu-id="4bfab-116">The skipped fields can then be specified through **BCPColFmt**.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="4bfab-117">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="4bfab-117">Return Code Values</span></span>  
 <span data-ttu-id="4bfab-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="4bfab-118">S_OK</span></span>  
 <span data-ttu-id="4bfab-119">O método foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="4bfab-119">The method succeeded.</span></span>  
  
 <span data-ttu-id="4bfab-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4bfab-120">E_FAIL</span></span>  
 <span data-ttu-id="4bfab-121">Ocorreu um erro específico do provedor; para obter informações detalhadas, use a interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="4bfab-121">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="4bfab-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="4bfab-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="4bfab-123">A chamada para o método era inesperada.</span><span class="sxs-lookup"><span data-stu-id="4bfab-123">The call to the method was unexpected.</span></span> <span data-ttu-id="4bfab-124">Por exemplo, o método **BCPInit** não foi chamado antes da chamada desse método.</span><span class="sxs-lookup"><span data-stu-id="4bfab-124">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="4bfab-125">Também ocorre quando esse método é chamado mais de uma vez para uma operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="4bfab-125">Also occurs when this method is called more than once for a bulk copy operation.</span></span>  
  
 <span data-ttu-id="4bfab-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4bfab-126">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="4bfab-127">Erro de memória insuficiente.</span><span class="sxs-lookup"><span data-stu-id="4bfab-127">Out-of-memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfab-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4bfab-128">See Also</span></span>  
 <span data-ttu-id="4bfab-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="4bfab-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="4bfab-130">Executando operações de cópia em massa</span><span class="sxs-lookup"><span data-stu-id="4bfab-130">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
