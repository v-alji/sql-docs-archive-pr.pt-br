---
title: IBCPSession::BCPExec (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPExec (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPExec method
ms.assetid: 0f4ebb63-cf03-4e53-846e-6c3021cde007
author: rothja
ms.author: jroth
ms.openlocfilehash: 1452888e046b6223c64a6cdf6fe09b074b815702
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679336"
---
# <a name="ibcpsessionbcpexec-ole-db"></a><span data-ttu-id="4e2d4-102">IBCPSession::BCPExec (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="4e2d4-102">IBCPSession::BCPExec (OLE DB)</span></span>
  <span data-ttu-id="4e2d4-103">Executa a operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-103">Performs the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e2d4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4e2d4-104">Syntax</span></span>  
  
```  
  
HRESULT BCPExec(   
DBROWCOUNT *pRowsCopied);  
```  
  
## <a name="remarks"></a><span data-ttu-id="4e2d4-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="4e2d4-105">Remarks</span></span>  
 <span data-ttu-id="4e2d4-106">O método **BCPExec** copia os dados de um arquivo de usuário para uma tabela de banco de dados ou vice-versa, dependendo do valor do parâmetro *eDirection* usado com o método [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="4e2d4-106">The **BCPExec** method copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter used with the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="4e2d4-107">Antes de chamar **BCPExec**, chame o método **BCPInit** com um nome de arquivo de usuário válido.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-107">Before calling **BCPExec**, call the **BCPInit** method with a valid user file name.</span></span> <span data-ttu-id="4e2d4-108">Caso isso não seja feito, será gerado um erro.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-108">Failure to do so results in an error.</span></span> <span data-ttu-id="4e2d4-109">A única exceção será se uma consulta for usada para uma operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-109">The only exception is if a query is to be used for a bulk copy out operation.</span></span> <span data-ttu-id="4e2d4-110">Nesse caso, especifique NULL para o nome da tabela no método **BCPInit** e, depois, especifique a consulta usando a opção BCP_OPTION_HINTS.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-110">In that case specify NULL for the table name in the **BCPInit** method and then specify the query using the BCP_OPTION_HINTS option.</span></span>  
  
 <span data-ttu-id="4e2d4-111">O método **BCPExec** é o único método de cópia em massa que provavelmente permanecerá pendente durante qualquer intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-111">The **BCPExec** method is the only bulk copy method that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="4e2d4-112">Ele é, portanto, o único método de cópia em massa que oferece suporte ao modo assíncrono.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-112">It is therefore the only bulk copy method that supports asynchronous mode.</span></span> <span data-ttu-id="4e2d4-113">Para usar o modo assíncrono, defina a propriedade de sessão SSPROP_ASYNCH_BULKCOPY específica do provedor como VARIANT_TRUE antes de chamar o método **BCPExec** .</span><span class="sxs-lookup"><span data-stu-id="4e2d4-113">To use asynchronous mode, set the provider specific session property SSPROP_ASYNCH_BULKCOPY to VARIANT_TRUE before calling the **BCPExec** method.</span></span> <span data-ttu-id="4e2d4-114">Essa propriedade está disponível no conjunto de propriedades DBPROPSET_SQLSERVERSESSION.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-114">This property is available in the DBPROPSET_SQLSERVERSESSION property set.</span></span> <span data-ttu-id="4e2d4-115">Para testar a conclusão, chame o método **BCPExec** com os mesmos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-115">To test for completion, call the **BCPExec** method with the same parameters.</span></span> <span data-ttu-id="4e2d4-116">Se a cópia em massa ainda não estiver concluída, o método **BCPExec** retornará DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-116">If the bulk copy has not yet completed, the **BCPExec** method returns DB_S_ASYNCHRONOUS.</span></span> <span data-ttu-id="4e2d4-117">Ele também retornará, no argumento *pRowsCopied* , uma contagem de status do número de linhas que foram enviadas para o servidor ou recebidas dele.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-117">It also returns in the *pRowsCopied* argument a status count of the number of rows that have been sent to or received from the server.</span></span> <span data-ttu-id="4e2d4-118">As linhas enviadas para o servidor não serão confirmadas até que o fim de um lote seja atingido.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-118">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="4e2d4-119">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4e2d4-119">Arguments</span></span>  
 <span data-ttu-id="4e2d4-120">*pRowsCopied*[out]</span><span class="sxs-lookup"><span data-stu-id="4e2d4-120">*pRowsCopied*[out]</span></span>  
 <span data-ttu-id="4e2d4-121">Um ponteiro para uma DWORD.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-121">A pointer to a DWORD.</span></span> <span data-ttu-id="4e2d4-122">O método **BCPExec** preenche a método com o número de linhas copiadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-122">The **BCPExec** method fills the DWORD with the number of rows successfully copied.</span></span> <span data-ttu-id="4e2d4-123">Se o argumento *pRowsCopied* for definido como NULL, ele será ignorado pelo método **BCPExec** .</span><span class="sxs-lookup"><span data-stu-id="4e2d4-123">If the *pRowsCopied* argument is set to NULL, it is ignored by the **BCPExec** method.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="4e2d4-124">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="4e2d4-124">Return Code Values</span></span>  
 <span data-ttu-id="4e2d4-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e2d4-125">S_OK</span></span>  
 <span data-ttu-id="4e2d4-126">O método foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-126">The method succeeded.</span></span>  
  
 <span data-ttu-id="4e2d4-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4e2d4-127">E_FAIL</span></span>  
 <span data-ttu-id="4e2d4-128">Ocorreu um erro específico do provedor; para obter informações detalhadas, use a interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="4e2d4-128">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="4e2d4-129">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="4e2d4-129">E_UNEXPECTED</span></span>  
 <span data-ttu-id="4e2d4-130">A chamada para o método era inesperada.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-130">The call to the method was unexpected.</span></span> <span data-ttu-id="4e2d4-131">Por exemplo, o método **BCPInit** não foi chamado antes da chamada desse método.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-131">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="4e2d4-132">Também ocorrerá se a operação for anulada com a opção BCP_OPTION_ABORT e o método **BCPExec** for chamado depois.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-132">Also occurs if the operation has been aborted through using the BCP_OPTION_ABORT option, and the **BCPExec** method was called afterwards.</span></span>  
  
 <span data-ttu-id="4e2d4-133">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4e2d4-133">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="4e2d4-134">Erro de memória insuficiente.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-134">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="4e2d4-135">DB_S_ENDOFROWSET</span><span class="sxs-lookup"><span data-stu-id="4e2d4-135">DB_S_ENDOFROWSET</span></span>  
 <span data-ttu-id="4e2d4-136">A operação de cópia em massa terminou e toda a transferência de dados foi concluída.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-136">The bulk copy operation finished, and all the data transfer was completed.</span></span>  
  
 <span data-ttu-id="4e2d4-137">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="4e2d4-137">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="4e2d4-138">O lote atual de linhas foi copiado.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-138">The current batch of rows has been copied.</span></span> <span data-ttu-id="4e2d4-139">Chame o método **BCPExec** novamente para transferir o próximo lote.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-139">Call the **BCPExec** method again to transfer the next batch.</span></span>  
  
 <span data-ttu-id="4e2d4-140">DB_S_ERRORSOCCURRED</span><span class="sxs-lookup"><span data-stu-id="4e2d4-140">DB_S_ERRORSOCCURRED</span></span>  
 <span data-ttu-id="4e2d4-141">Ocorreram erros durante a operação de cópia em massa e algumas linhas podem não ter sido copiadas.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-141">Errors occurred during the bulk copy operation, and some rows might not have been copied.</span></span> <span data-ttu-id="4e2d4-142">O número de erros ainda é menor do que o máximo de erros permitido.</span><span class="sxs-lookup"><span data-stu-id="4e2d4-142">The number of errors is still less than the maximum errors allowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2d4-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e2d4-143">See Also</span></span>  
 <span data-ttu-id="4e2d4-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="4e2d4-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="4e2d4-145">Executando operações de cópia em massa</span><span class="sxs-lookup"><span data-stu-id="4e2d4-145">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
