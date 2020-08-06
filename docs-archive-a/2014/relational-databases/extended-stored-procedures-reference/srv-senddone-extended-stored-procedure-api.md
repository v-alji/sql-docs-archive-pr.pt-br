---
title: srv_senddone (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_senddone
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_senddone
ms.assetid: 1fc4f1d5-56d4-43f6-b5e4-0c0cc295cba3
author: rothja
ms.author: jroth
ms.openlocfilehash: 877acdc1b666c7f4cbaab737590a1c55e474eb05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686265"
---
# <a name="srv_senddone-extended-stored-procedure-api"></a><span data-ttu-id="5a59e-102">srv_senddone (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="5a59e-102">srv_senddone (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="5a59e-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="5a59e-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="5a59e-104">Envia uma mensagem de conclusão de resultado para o cliente.</span><span class="sxs-lookup"><span data-stu-id="5a59e-104">Sends a result completion message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a59e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5a59e-105">Syntax</span></span>  
  
```  
  
int srv_senddone (  
SRV_PROC *  
srvproc  
,  
DBUSMALLINT   
status  
,  
DBUSMALLINT  
info  
,  
DBINT  
count   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="5a59e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5a59e-106">Arguments</span></span>  
 <span data-ttu-id="5a59e-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="5a59e-107">*srvproc*</span></span>  
 <span data-ttu-id="5a59e-108">É um ponteiro para a estrutura SRV_PROC que é o identificador de uma conexão de cliente específica (neste caso, o identificador que recebeu a solicitação de linguagem).</span><span class="sxs-lookup"><span data-stu-id="5a59e-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="5a59e-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="5a59e-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="5a59e-110">*status*</span><span class="sxs-lookup"><span data-stu-id="5a59e-110">*status*</span></span>  
 <span data-ttu-id="5a59e-111">É um campo de 2 bytes para vários sinalizadores *status* .</span><span class="sxs-lookup"><span data-stu-id="5a59e-111">Is a 2-byte field for various *status* flags.</span></span> <span data-ttu-id="5a59e-112">Vários sinalizadores podem ser definidos usando os operadores lógicos AND e OR com valores de sinalizador *status* .</span><span class="sxs-lookup"><span data-stu-id="5a59e-112">Multiple flags can be set by using the AND and OR logical operators with *status* flag values.</span></span> <span data-ttu-id="5a59e-113">A seguinte tabela lista os possíveis sinalizadores *status* .</span><span class="sxs-lookup"><span data-stu-id="5a59e-113">The following table lists possible *status* flags.</span></span>  
  
|<span data-ttu-id="5a59e-114">Sinalizador de status</span><span class="sxs-lookup"><span data-stu-id="5a59e-114">Status flag</span></span>|<span data-ttu-id="5a59e-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="5a59e-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5a59e-116">SRV_DONE_COUNT</span><span class="sxs-lookup"><span data-stu-id="5a59e-116">SRV_DONE_COUNT</span></span>|<span data-ttu-id="5a59e-117">O parâmetro *count* contém uma contagem válida.</span><span class="sxs-lookup"><span data-stu-id="5a59e-117">The *count* parameter contains a valid count.</span></span>|  
|<span data-ttu-id="5a59e-118">SRV_DONE_ERROR</span><span class="sxs-lookup"><span data-stu-id="5a59e-118">SRV_DONE_ERROR</span></span>|<span data-ttu-id="5a59e-119">O comando do cliente atual recebeu um erro.</span><span class="sxs-lookup"><span data-stu-id="5a59e-119">The current client command received an error.</span></span>|  
  
 <span data-ttu-id="5a59e-120">*informações*</span><span class="sxs-lookup"><span data-stu-id="5a59e-120">*info*</span></span>  
 <span data-ttu-id="5a59e-121">É um campo reservado de 2 bytes.</span><span class="sxs-lookup"><span data-stu-id="5a59e-121">Is a reserved, 2-byte field.</span></span> <span data-ttu-id="5a59e-122">Defina o valor como 0.</span><span class="sxs-lookup"><span data-stu-id="5a59e-122">Set this value to 0.</span></span>  
  
 <span data-ttu-id="5a59e-123">*contagem*</span><span class="sxs-lookup"><span data-stu-id="5a59e-123">*count*</span></span>  
 <span data-ttu-id="5a59e-124">É um campo de 4 bytes usado para indicar uma contagem do conjunto de resultados atual.</span><span class="sxs-lookup"><span data-stu-id="5a59e-124">Is a 4-byte field used to indicate a count for the current result set.</span></span> <span data-ttu-id="5a59e-125">Se o sinalizador SRV_DONE_COUNT for definido no campo *status* , *count* manterá uma contagem válida.</span><span class="sxs-lookup"><span data-stu-id="5a59e-125">If the SRV_DONE_COUNT flag is set in the *status* field, *count* holds a valid count.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="5a59e-126">Retornos</span><span class="sxs-lookup"><span data-stu-id="5a59e-126">Returns</span></span>  
 <span data-ttu-id="5a59e-127">SUCCEED ou FAIL</span><span class="sxs-lookup"><span data-stu-id="5a59e-127">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a59e-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="5a59e-128">Remarks</span></span>  
 <span data-ttu-id="5a59e-129">Uma solicitação do cliente pode fazer com que o servidor execute vários comandos e retorne vários conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="5a59e-129">A client request can cause the server to execute a number of commands and to return a number of result sets.</span></span> <span data-ttu-id="5a59e-130">Para cada conjunto de resultados, **srv_senddone** deve retornar uma mensagem de conclusão de resultado para o cliente.</span><span class="sxs-lookup"><span data-stu-id="5a59e-130">For each result set, **srv_senddone** must return a result completion message to the client.</span></span>  
  
 <span data-ttu-id="5a59e-131">O campo *count* indica o número de linhas afetadas por um comando.</span><span class="sxs-lookup"><span data-stu-id="5a59e-131">The *count* field indicates the number of rows affected by a command.</span></span> <span data-ttu-id="5a59e-132">Se o campo *count* contiver uma contagem, o sinalizador SRV_DONE_COUNT deverá ser definido no campo *status* .</span><span class="sxs-lookup"><span data-stu-id="5a59e-132">If the *count* field contains a count, the SRV_DONE_COUNT flag should be set in the *status* field.</span></span> <span data-ttu-id="5a59e-133">Essa configuração permite ao cliente distinguir entre um valor *count* igual a 0 e um campo não usado *count* .</span><span class="sxs-lookup"><span data-stu-id="5a59e-133">This setting allows the client to distinguish between a *count* value of 0 and an unused *count* field.</span></span>  
  
 <span data-ttu-id="5a59e-134">Não chame **srv_senddone** no manipulador SRV_CONNECT.</span><span class="sxs-lookup"><span data-stu-id="5a59e-134">Do not call **srv_senddone** from the SRV_CONNECT handler.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5a59e-135">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="5a59e-135">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="5a59e-136">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="5a59e-136">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
