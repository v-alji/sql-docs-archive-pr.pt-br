---
title: srv_wsendmsg (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_wsendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_wsendmsg
ms.assetid: f2153076-32c9-4a52-8e1b-fc9618153543
author: rothja
ms.author: jroth
ms.openlocfilehash: 4cc915cce0befccb5c5af58e703c11b750af855b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685699"
---
# <a name="srv_wsendmsg-extended-stored-procedure-api"></a><span data-ttu-id="6b32f-102">srv_wsendmsg (API do procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="6b32f-102">srv_wsendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="6b32f-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="6b32f-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="6b32f-104">Envia uma mensagem de Unicode ao cliente.</span><span class="sxs-lookup"><span data-stu-id="6b32f-104">Sends a Unicode message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b32f-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6b32f-105">Syntax</span></span>  
  
```  
  
int srv_wsendmsg(SRV_PROC *   
srvproc  
, int   
msgnum  
, int   
severity  
, WCHAR *   
message  
, int   
msglen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="6b32f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6b32f-106">Arguments</span></span>  
 <span data-ttu-id="6b32f-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="6b32f-107">*srvproc*</span></span>  
 <span data-ttu-id="6b32f-108">É um ponteiro para a estrutura SRV_PROC que atua como identificador de uma conexão de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="6b32f-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="6b32f-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="6b32f-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="6b32f-110">*Msgnum*</span><span class="sxs-lookup"><span data-stu-id="6b32f-110">*Msgnum*</span></span>  
 <span data-ttu-id="6b32f-111">É um número de mensagem de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="6b32f-111">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="6b32f-112">*Gravidade*</span><span class="sxs-lookup"><span data-stu-id="6b32f-112">*Severity*</span></span>  
 <span data-ttu-id="6b32f-113">Especifica a gravidade do erro.</span><span class="sxs-lookup"><span data-stu-id="6b32f-113">Specifies the severity of the error.</span></span> <span data-ttu-id="6b32f-114">Uma gravidade menor ou igual a 10 é considerada uma mensagem informativa. Caso contrário, trata-se de um erro.</span><span class="sxs-lookup"><span data-stu-id="6b32f-114">A severity less than or equal to 10 is considered an informational message; otherwise, it is an error.</span></span>  
  
 <span data-ttu-id="6b32f-115">*message*</span><span class="sxs-lookup"><span data-stu-id="6b32f-115">*message*</span></span>  
 <span data-ttu-id="6b32f-116">É um ponteiro para a cadeia de caracteres de Unicode que será enviada ao cliente.</span><span class="sxs-lookup"><span data-stu-id="6b32f-116">Is a pointer to a Unicode string to be sent to the client.</span></span>  
  
 <span data-ttu-id="6b32f-117">*msglen*</span><span class="sxs-lookup"><span data-stu-id="6b32f-117">*msglen*</span></span>  
 <span data-ttu-id="6b32f-118">Especifica o comprimento, em caracteres, de *message*.</span><span class="sxs-lookup"><span data-stu-id="6b32f-118">Specifies the length, in characters, of *message*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="6b32f-119">Retornos</span><span class="sxs-lookup"><span data-stu-id="6b32f-119">Returns</span></span>  
 <span data-ttu-id="6b32f-120">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="6b32f-120">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b32f-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="6b32f-121">Remarks</span></span>  
 <span data-ttu-id="6b32f-122">Use esta função para enviar mensagens em Unicode.</span><span class="sxs-lookup"><span data-stu-id="6b32f-122">Use this function to send messages in Unicode.</span></span> <span data-ttu-id="6b32f-123">É semelhante a **srv_sendmsg**, mas a mensagem que envia é uma cadeia de caracteres de WCHAR em vez de uma cadeia de caracteres de DBCHAR.</span><span class="sxs-lookup"><span data-stu-id="6b32f-123">It is similar to **srv_sendmsg**, but the message it sends is a WCHAR string rather than type DBCHAR string.</span></span> <span data-ttu-id="6b32f-124">Observe que o comprimento da mensagem é informado em caracteres, e não em bytes, e que *msglen* nunca será igual a SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="6b32f-124">Note that message length is reported in characters rather than bytes, and *msglen* will never be equal to SRV_NULLTERM.</span></span>  
  
 <span data-ttu-id="6b32f-125">A função retorna FAIL quando</span><span class="sxs-lookup"><span data-stu-id="6b32f-125">The function returns FAIL when</span></span>  
  
-   <span data-ttu-id="6b32f-126">O *msglen* fornecido não está no intervalo de 0-32242.</span><span class="sxs-lookup"><span data-stu-id="6b32f-126">The *msglen* given is not in the range of 0-32242.</span></span>  
  
-   <span data-ttu-id="6b32f-127">O *msglen* fornecido é 0, mas o ponteiro de mensagem é o NULL.</span><span class="sxs-lookup"><span data-stu-id="6b32f-127">The *msglen* given is 0 but the message pointer is NULL.</span></span>  
  
-   <span data-ttu-id="6b32f-128">Ocorre um erro ao enviar a mensagem de erro na rede.</span><span class="sxs-lookup"><span data-stu-id="6b32f-128">There is error when sending the error message through network.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6b32f-129">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="6b32f-129">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="6b32f-130">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="6b32f-130">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b32f-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6b32f-131">See Also</span></span>  
 [<span data-ttu-id="6b32f-132">srv_sendmsg &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="6b32f-132">srv_sendmsg &#40;Extended Stored Procedure API&#41;</span></span>](srv-sendmsg-extended-stored-procedure-api.md)  
  
  
