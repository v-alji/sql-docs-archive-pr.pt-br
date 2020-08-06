---
title: srv_sendrow (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendrow
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendrow
ms.assetid: a08f608a-10e6-4bff-9b48-0d02e8026cdb
author: rothja
ms.author: jroth
ms.openlocfilehash: df40348b8792a70f84719abfb42152fda9487e6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686262"
---
# <a name="srv_sendrow-extended-stored-procedure-api"></a><span data-ttu-id="25005-102">srv_sendrow (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="25005-102">srv_sendrow (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="25005-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="25005-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="25005-104">Transmite uma linha de dados ao cliente.</span><span class="sxs-lookup"><span data-stu-id="25005-104">Transmits a row of data to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25005-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="25005-105">Syntax</span></span>  
  
```  
  
int srv_sendrow ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="25005-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="25005-106">Arguments</span></span>  
 <span data-ttu-id="25005-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="25005-107">*srvproc*</span></span>  
 <span data-ttu-id="25005-108">É um ponteiro para a estrutura SRV_PROC que é o identificador de uma conexão de cliente específica (neste caso, o identificador que recebeu a solicitação de linguagem).</span><span class="sxs-lookup"><span data-stu-id="25005-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="25005-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="25005-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="25005-110">Retornos</span><span class="sxs-lookup"><span data-stu-id="25005-110">Returns</span></span>  
 <span data-ttu-id="25005-111">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="25005-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25005-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="25005-112">Remarks</span></span>  
 <span data-ttu-id="25005-113">A função **srv_sendrow** é chamada uma vez para cada linha enviada ao cliente.</span><span class="sxs-lookup"><span data-stu-id="25005-113">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="25005-114">Todas as linhas devem ser enviadas ao cliente antes de qualquer mensagem, valor de status ou status de conclusão ser enviado com **srv_sendmsg**, **srv_status**ou **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="25005-114">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, **srv_status**, or **srv_senddone**.</span></span>  
  
 <span data-ttu-id="25005-115">O envio de uma linha que não tenha tido todas as suas colunas definidas com **srv_describe** faz com que o aplicativo da API de Procedimento Armazenado Estendido crie uma mensagem de erro informativa e retorne FAIL ao cliente.</span><span class="sxs-lookup"><span data-stu-id="25005-115">Sending a row that has not had all its columns defined with **srv_describe** causes the Extended Stored Procedure API application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="25005-116">Neste caso, a linha não é enviada.</span><span class="sxs-lookup"><span data-stu-id="25005-116">In this case, the row is not sent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25005-117">A API de Procedimento Armazenado Estendido não dá suporte ao envio de linhas computadas ao cliente.</span><span class="sxs-lookup"><span data-stu-id="25005-117">The Extended Stored Procedure API does not support sending compute rows to the client.</span></span> <span data-ttu-id="25005-118">Além disso, se uma linha que contenha dados `ntext`, `text` ou `image` for enviada ao cliente, o ponteiro de texto e o carimbo de data/hora de texto não serão incluídos.</span><span class="sxs-lookup"><span data-stu-id="25005-118">Also, if a row containing `ntext`, `text`, or `image` data is sent to the client, the text pointer and text timestamp are not included.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="25005-119">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="25005-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="25005-120">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="25005-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25005-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25005-121">See Also</span></span>  
 [<span data-ttu-id="25005-122">srv_describe &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="25005-122">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
