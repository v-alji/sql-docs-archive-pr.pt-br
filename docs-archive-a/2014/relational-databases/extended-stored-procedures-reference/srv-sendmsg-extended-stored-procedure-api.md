---
title: srv_sendmsg (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendmsg
ms.assetid: efcb50b9-f8ff-4121-bf67-05830171b928
author: rothja
ms.author: jroth
ms.openlocfilehash: 0821ad88f48313cfadea634a489def9b242a49f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686263"
---
# <a name="srv_sendmsg-extended-stored-procedure-api"></a><span data-ttu-id="2f93e-102">srv_sendmsg (API do procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="2f93e-102">srv_sendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="2f93e-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="2f93e-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="2f93e-104">Envia uma mensagem ao cliente.</span><span class="sxs-lookup"><span data-stu-id="2f93e-104">Sends a message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f93e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2f93e-105">Syntax</span></span>  
  
```  
  
int srv_sendmsg (  
SRV_PROC *  
srvproc  
,  
int  
msgtype  
,  
DBINT  
msgnum  
,  
DBTINYINT  
class  
,   
DBTINYINT  
state  
,  
DBCHAR *  
rpcname  
,  
int   
rpcnamelen  
,  
DBUSMALLINT  
linenum  
,  
DBCHAR *  
message  
,  
int  
msglen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f93e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2f93e-106">Arguments</span></span>  
 <span data-ttu-id="2f93e-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="2f93e-107">*srvproc*</span></span>  
 <span data-ttu-id="2f93e-108">É um ponteiro para a estrutura SRV_PROC que é o identificador de uma conexão de cliente específica (neste caso, o identificador que recebeu a solicitação de linguagem).</span><span class="sxs-lookup"><span data-stu-id="2f93e-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="2f93e-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="2f93e-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="2f93e-110">*msgtype*</span><span class="sxs-lookup"><span data-stu-id="2f93e-110">*msgtype*</span></span>  
 <span data-ttu-id="2f93e-111">É SRV_MSG_INFO ou SRV_MSG_ERROR, dependendo se o servidor está enviando uma mensagem informativa ou de erro.</span><span class="sxs-lookup"><span data-stu-id="2f93e-111">Is either SRV_MSG_INFO or SRV_MSG_ERROR, depending on whether the server is sending an informational or error message.</span></span>  
  
 <span data-ttu-id="2f93e-112">*msgnum*</span><span class="sxs-lookup"><span data-stu-id="2f93e-112">*msgnum*</span></span>  
 <span data-ttu-id="2f93e-113">É um número de mensagem de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="2f93e-113">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="2f93e-114">*class*</span><span class="sxs-lookup"><span data-stu-id="2f93e-114">*class*</span></span>  
 <span data-ttu-id="2f93e-115">Especifica a gravidade do erro.</span><span class="sxs-lookup"><span data-stu-id="2f93e-115">Specifies the error severity.</span></span> <span data-ttu-id="2f93e-116">Uma gravidade menor ou igual a 10 é considerada uma mensagem informativa.</span><span class="sxs-lookup"><span data-stu-id="2f93e-116">A severity less than or equal to 10 is considered an informational message.</span></span>  
  
 <span data-ttu-id="2f93e-117">*state*</span><span class="sxs-lookup"><span data-stu-id="2f93e-117">*state*</span></span>  
 <span data-ttu-id="2f93e-118">Fornece o número do estado de erro para a mensagem atual.</span><span class="sxs-lookup"><span data-stu-id="2f93e-118">Provides the error state number for the current message.</span></span> <span data-ttu-id="2f93e-119">O número do estado de erro fornece informações sobre o contexto do erro.</span><span class="sxs-lookup"><span data-stu-id="2f93e-119">The error state number provides information about the context of the error.</span></span> <span data-ttu-id="2f93e-120">Os números de estado válidos variam de 0 a 255.</span><span class="sxs-lookup"><span data-stu-id="2f93e-120">Valid state numbers are from 0 through 255.</span></span>  
  
 <span data-ttu-id="2f93e-121">*rpcname*</span><span class="sxs-lookup"><span data-stu-id="2f93e-121">*rpcname*</span></span>  
 <span data-ttu-id="2f93e-122">Atualmente ele não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="2f93e-122">Is currently not supported.</span></span>  
  
 <span data-ttu-id="2f93e-123">*rpcnamelen*</span><span class="sxs-lookup"><span data-stu-id="2f93e-123">*rpcnamelen*</span></span>  
 <span data-ttu-id="2f93e-124">Atualmente ele não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="2f93e-124">Is currently not supported.</span></span>  
  
 <span data-ttu-id="2f93e-125">*linenum*</span><span class="sxs-lookup"><span data-stu-id="2f93e-125">*linenum*</span></span>  
 <span data-ttu-id="2f93e-126">É o número da linha no lote de comando de linguagem onde a mensagem é aplicada.</span><span class="sxs-lookup"><span data-stu-id="2f93e-126">Is the line number in the language command batch where the message applies.</span></span> <span data-ttu-id="2f93e-127">Os números da linha iniciam em 1.</span><span class="sxs-lookup"><span data-stu-id="2f93e-127">Line numbers start at 1.</span></span> <span data-ttu-id="2f93e-128">Se *linenum* não se aplicar à mensagem, defina-o como 0.</span><span class="sxs-lookup"><span data-stu-id="2f93e-128">If *linenum* does not apply to the message, set to 0.</span></span>  
  
 <span data-ttu-id="2f93e-129">*message*</span><span class="sxs-lookup"><span data-stu-id="2f93e-129">*message*</span></span>  
 <span data-ttu-id="2f93e-130">É um ponteiro para a cadeia de caracteres que será enviada ao cliente.</span><span class="sxs-lookup"><span data-stu-id="2f93e-130">Is a pointer to the character string to be sent to the client.</span></span>  
  
 <span data-ttu-id="2f93e-131">*msglen*</span><span class="sxs-lookup"><span data-stu-id="2f93e-131">*msglen*</span></span>  
 <span data-ttu-id="2f93e-132">Especifica o tamanho, em bytes, de *message*.</span><span class="sxs-lookup"><span data-stu-id="2f93e-132">Specifies the length, in bytes, of *message*.</span></span> <span data-ttu-id="2f93e-133">Se *message* terminar em nulo, defina *msglen* como SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="2f93e-133">If *message* is null-terminated, set *msglen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="2f93e-134">Retornos</span><span class="sxs-lookup"><span data-stu-id="2f93e-134">Returns</span></span>  
 <span data-ttu-id="2f93e-135">SUCCEED ou FAIL</span><span class="sxs-lookup"><span data-stu-id="2f93e-135">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f93e-136">Comentários</span><span class="sxs-lookup"><span data-stu-id="2f93e-136">Remarks</span></span>  
 <span data-ttu-id="2f93e-137">Essa função envia mensagens de erro ou informativas ao cliente.</span><span class="sxs-lookup"><span data-stu-id="2f93e-137">This function sends error or informational messages to the client.</span></span> <span data-ttu-id="2f93e-138">Ela é chamada uma vez para cada mensagem que será enviada.</span><span class="sxs-lookup"><span data-stu-id="2f93e-138">It is called once for each message to be sent.</span></span>  
  
 <span data-ttu-id="2f93e-139">É possível enviar mensagens ao cliente com **srv_sendmsg** em qualquer ordem antes ou depois que todas as linhas (se houver) tiverem sido enviadas com **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="2f93e-139">Messages can be sent to the client with **srv_sendmsg** in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="2f93e-140">Todas as mensagens, se houver, devem ser enviadas ao cliente antes do envio do status de conclusão com **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="2f93e-140">All messages, if any, must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
 <span data-ttu-id="2f93e-141">Para enviar mensagens em Unicode, use **srv_wsendmsg** no lugar de **srv_sendmsg**.</span><span class="sxs-lookup"><span data-stu-id="2f93e-141">To send messages in Unicode, use **srv_wsendmsg** rather than **srv_sendmsg**.</span></span>  
  
 <span data-ttu-id="2f93e-142">Para obter mais informações, consulte [Páginas de código do servidor e dados Unicode](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="2f93e-142">For more information see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f93e-143">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="2f93e-143">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="2f93e-144">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="2f93e-144">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
