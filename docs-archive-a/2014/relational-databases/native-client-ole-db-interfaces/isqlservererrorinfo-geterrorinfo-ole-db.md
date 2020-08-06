---
title: ISQLServerErrorInfo::GetErrorInfo (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISQLServerErrorInfo::GetErrorInfo (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetErrorInfo method
ms.assetid: 83265c9c-eaf9-41f0-9f73-b0ae0972f0d5
author: rothja
ms.author: jroth
ms.openlocfilehash: c3e325cd99276e04a178b89c19b233289edc09fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681647"
---
# <a name="isqlservererrorinfogeterrorinfo-ole-db"></a><span data-ttu-id="c067b-102">ISQLServerErrorInfo::GetErrorInfo (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="c067b-102">ISQLServerErrorInfo::GetErrorInfo (OLE DB)</span></span>
  <span data-ttu-id="c067b-103">Retorna um ponteiro para uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estrutura SSERRORINFO do provedor de OLE DB de cliente nativo que contém os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] detalhes do erro.</span><span class="sxs-lookup"><span data-stu-id="c067b-103">Returns a pointer to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider SSERRORINFO structure containing the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error details.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c067b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c067b-104">Syntax</span></span>  
  
```  
  
   HRESULT GetErrorInfo(  
SSERRORINFO**ppSSErrorInfo,  
OLECHAR**ppErrorStrings);  
```  
  
## <a name="arguments"></a><span data-ttu-id="c067b-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c067b-105">Arguments</span></span>  
 <span data-ttu-id="c067b-106">*ppSSErrorInfo*[out]</span><span class="sxs-lookup"><span data-stu-id="c067b-106">*ppSSErrorInfo*[out]</span></span>  
 <span data-ttu-id="c067b-107">Um ponteiro para uma estrutura SSERRORINFO.</span><span class="sxs-lookup"><span data-stu-id="c067b-107">A pointer to a SSERRORINFO structure.</span></span> <span data-ttu-id="c067b-108">Se o método falhar ou se não houver informações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associadas ao erro, o provedor não alocará nenhuma memória e garantirá que o argumento *ppSSErrorInfo* seja um ponteiro nulo na saída.</span><span class="sxs-lookup"><span data-stu-id="c067b-108">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with the error, the provider does not allocate any memory, and ensures that the *ppSSErrorInfo* argument is a null pointer on output.</span></span>  
  
 <span data-ttu-id="c067b-109">*ppErrorStrings*[out]</span><span class="sxs-lookup"><span data-stu-id="c067b-109">*ppErrorStrings*[out]</span></span>  
 <span data-ttu-id="c067b-110">Um ponteiro para um ponteiro de cadeia de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="c067b-110">A pointer to a Unicode character-string pointer.</span></span> <span data-ttu-id="c067b-111">Se o método falhar ou se não houver informações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associadas a um erro, o provedor não alocará nenhuma memória e garantirá que o argumento *ppErrorStrings* seja um ponteiro nulo na saída.</span><span class="sxs-lookup"><span data-stu-id="c067b-111">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with an error, the provider does not allocate any memory, and ensures that the *ppErrorStrings* argument is a null pointer on output.</span></span> <span data-ttu-id="c067b-112">A liberação do argumento *ppErrorStrings* com o método **IMalloc::Free** libera os três membros de cadeia de caracteres individuais da estrutura SSERRORINFO retornada, pois a memória é alocada em um bloco.</span><span class="sxs-lookup"><span data-stu-id="c067b-112">Freeing the *ppErrorStrings* argument with the **IMalloc::Free** method frees the three individual string members of the returned SSERRORINFO structure, as the memory is allocated in a block.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="c067b-113">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="c067b-113">Return Code Values</span></span>  
 <span data-ttu-id="c067b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c067b-114">S_OK</span></span>  
 <span data-ttu-id="c067b-115">O método foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="c067b-115">The method succeeded.</span></span>  
  
 <span data-ttu-id="c067b-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c067b-116">E_INVALIDARG</span></span>  
 <span data-ttu-id="c067b-117">O argumento *ppSSErrorInfo* ou *ppErrorStrings* foi NULL.</span><span class="sxs-lookup"><span data-stu-id="c067b-117">Either the *ppSSErrorInfo* or the *ppErrorStrings* argument was NULL.</span></span>  
  
 <span data-ttu-id="c067b-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c067b-118">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="c067b-119">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não pôde alocar memória suficiente para concluir a solicitação.</span><span class="sxs-lookup"><span data-stu-id="c067b-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider could not allocate sufficient memory to complete the request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c067b-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="c067b-120">Remarks</span></span>  
 <span data-ttu-id="c067b-121">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo aloca memória para as cadeias de caracteres SSERRORINFO e OLECHAR retornadas por meio dos ponteiros passados pelo consumidor.</span><span class="sxs-lookup"><span data-stu-id="c067b-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider allocates memory for the SSERRORINFO and OLECHAR strings returned through the pointers passed by the consumer.</span></span> <span data-ttu-id="c067b-122">O consumidor precisará desalocar essa memória usando o método **IMalloc::Free** quando não for mais necessário acessar os dados de erro.</span><span class="sxs-lookup"><span data-stu-id="c067b-122">The consumer must deallocate this memory by using the **IMalloc::Free** method when it no longer requires access to the error data.</span></span>  
  
 <span data-ttu-id="c067b-123">A estrutura SSERRORINFO é definida da seguintes maneira:</span><span class="sxs-lookup"><span data-stu-id="c067b-123">The SSERRORINFO structure is defined as follows:</span></span>  
  
```  
typedef struct tagSSErrorInfo  
   {  
   LPOLESTR pwszMessage;  
   LPOLESTR pwszServer;  
   LPOLESTR pwszProcedure;  
   LONG lNative;  
   BYTE bState;  
   BYTE bClass;  
   WORD wLineNumber;  
   }  
SSERRORINFO;  
```  
  
|<span data-ttu-id="c067b-124">Membro</span><span class="sxs-lookup"><span data-stu-id="c067b-124">Member</span></span>|<span data-ttu-id="c067b-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="c067b-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c067b-126">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="c067b-126">*pwszMessage*</span></span>|<span data-ttu-id="c067b-127">A mensagem de erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c067b-127">The error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c067b-128">A mensagem é retornada por meio do método **IErrorInfo::GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="c067b-128">The message is returned through the **IErrorInfo::GetDescription** method.</span></span>|  
|<span data-ttu-id="c067b-129">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="c067b-129">*pwszServer*</span></span>|<span data-ttu-id="c067b-130">O nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na qual o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="c067b-130">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which the error occurred.</span></span>|  
|<span data-ttu-id="c067b-131">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="c067b-131">*pwszProcedure*</span></span>|<span data-ttu-id="c067b-132">O nome do procedimento armazenado que gera o erro, se o erro ocorreu em um procedimento armazenado; caso contrário, uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="c067b-132">The name of the stored procedure generating the error if the error occurred in a stored procedure; otherwise, an empty string.</span></span>|  
|<span data-ttu-id="c067b-133">*lNative*</span><span class="sxs-lookup"><span data-stu-id="c067b-133">*lNative*</span></span>|<span data-ttu-id="c067b-134">O número de erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c067b-134">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number.</span></span> <span data-ttu-id="c067b-135">O número do erro é idêntico àquele retornado no parâmetro *plNativeError* do método **ISQLErrorInfo::GetSQLInfo**.</span><span class="sxs-lookup"><span data-stu-id="c067b-135">The error number is identical to that returned in the *plNativeError* parameter of the **ISQLErrorInfo::GetSQLInfo** method.</span></span>|  
|<span data-ttu-id="c067b-136">*bState*</span><span class="sxs-lookup"><span data-stu-id="c067b-136">*bState*</span></span>|<span data-ttu-id="c067b-137">O estado do erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c067b-137">The state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="c067b-138">*bClass*</span><span class="sxs-lookup"><span data-stu-id="c067b-138">*bClass*</span></span>|<span data-ttu-id="c067b-139">A severidade do erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c067b-139">The severity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="c067b-140">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="c067b-140">*wLineNumber*</span></span>|<span data-ttu-id="c067b-141">Quando aplicável, a linha de um procedimento armazenado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que gerou a mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="c067b-141">When applicable, the line of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure that generated the error message.</span></span> <span data-ttu-id="c067b-142">Se nenhum procedimento estiver envolvido, o valor padrão será 1.</span><span class="sxs-lookup"><span data-stu-id="c067b-142">If no procedure is involved, the default value is 1.</span></span>|  
  
 <span data-ttu-id="c067b-143">Os ponteiros nos endereços de referência da estrutura na cadeia de caracteres retornada no argumento *ppErrorStrings*.</span><span class="sxs-lookup"><span data-stu-id="c067b-143">Pointers in the structure reference addresses in the string returned in the *ppErrorStrings* argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c067b-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c067b-144">See Also</span></span>  
 <span data-ttu-id="c067b-145">[ISQLServerErrorInfo &#40;OLE DB&#41;](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="c067b-145">[ISQLServerErrorInfo &#40;OLE DB&#41;](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span></span>  
 [<span data-ttu-id="c067b-146">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c067b-146">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
