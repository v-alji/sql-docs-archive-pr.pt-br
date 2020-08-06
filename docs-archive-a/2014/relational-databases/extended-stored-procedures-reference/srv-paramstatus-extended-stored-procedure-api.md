---
title: srv_paramstatus (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramstatus
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramstatus
ms.assetid: 86cecd45-0b09-42e9-8152-32a12a1c2b7a
author: rothja
ms.author: jroth
ms.openlocfilehash: d89d4ccbb6a97ff47669ad4ed9c0b4c22ac934eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678736"
---
# <a name="srv_paramstatus-extended-stored-procedure-api"></a><span data-ttu-id="492b4-102">srv_paramstatus (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="492b4-102">srv_paramstatus (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="492b4-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="492b4-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="492b4-104">Retorna o status de um parâmetro de chamada de procedimento armazenado remoto específico.</span><span class="sxs-lookup"><span data-stu-id="492b4-104">Returns the status of a particular remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="492b4-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="492b4-105">Syntax</span></span>  
  
```  
  
int srv_paramstatus (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="492b4-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="492b4-106">Arguments</span></span>  
 <span data-ttu-id="492b4-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="492b4-107">*srvproc*</span></span>  
 <span data-ttu-id="492b4-108">É um ponteiro para a estrutura SRV_PROC que identifica uma conexão de cliente específica (nesse caso, o identificador que recebeu a chamada do procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="492b4-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="492b4-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="492b4-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="492b4-110">*n*</span><span class="sxs-lookup"><span data-stu-id="492b4-110">*n*</span></span>  
 <span data-ttu-id="492b4-111">Indica o número do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="492b4-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="492b4-112">O primeiro parâmetro equivale ao número 1.</span><span class="sxs-lookup"><span data-stu-id="492b4-112">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="492b4-113">Retornos</span><span class="sxs-lookup"><span data-stu-id="492b4-113">Returns</span></span>  
 <span data-ttu-id="492b4-114">Um `int` que contém sinalizadores de status para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="492b4-114">An `int` that contains status flags for the parameter.</span></span> <span data-ttu-id="492b4-115">Atualmente, há só um sinalizador: se bit 0 for definido como 1, o parâmetro será um parâmetro de retorno.</span><span class="sxs-lookup"><span data-stu-id="492b4-115">Currently, there is only one flag: If bit 0 is set to 1, the parameter is a return parameter.</span></span> <span data-ttu-id="492b4-116">Se não houver *n*-ésimo parâmetro nem procedimento armazenado remoto, o valor retornado será -1.</span><span class="sxs-lookup"><span data-stu-id="492b4-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="492b4-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="492b4-117">Remarks</span></span>  
 <span data-ttu-id="492b4-118">Esta rotina retorna os sinalizadores de status para um parâmetro de chamada de procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="492b4-118">This routine returns the status flags for a remote stored procedure call parameter.</span></span>  
  
 <span data-ttu-id="492b4-119">Os parâmetros contêm dados passados entre os clientes e o aplicativo com procedimentos armazenados remotos.</span><span class="sxs-lookup"><span data-stu-id="492b4-119">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="492b4-120">O cliente pode especificar certos parâmetros como parâmetros de retorno.</span><span class="sxs-lookup"><span data-stu-id="492b4-120">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="492b4-121">Esses parâmetros de retorno podem conter valores que o aplicativo devolve ao cliente.</span><span class="sxs-lookup"><span data-stu-id="492b4-121">These return parameters can contain values that the application passes back to the client.</span></span>  
  
 <span data-ttu-id="492b4-122">Atualmente, o único sinalizador de status é um que indica se o parâmetro é um parâmetro de retorno.</span><span class="sxs-lookup"><span data-stu-id="492b4-122">Currently, the only status flag is one that indicates whether the parameter is a return parameter.</span></span>  
  
 <span data-ttu-id="492b4-123">Quando uma chamada de procedimento armazenado remoto é feita com parâmetros, os parâmetros podem ser passados pelo nome ou pela posição (sem-nome).</span><span class="sxs-lookup"><span data-stu-id="492b4-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="492b4-124">Se a chamada de procedimento armazenado remoto for feita com alguns parâmetros transmitidos pelo nome e outros pela posição, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="492b4-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="492b4-125">Se ocorrer um erro, o manipulador de SRV_RPC ainda será chamado, mas aparecerá como se não houvesse parâmetros e **srv_rpcparams** retornará 0.</span><span class="sxs-lookup"><span data-stu-id="492b4-125">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="492b4-126">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="492b4-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="492b4-127">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="492b4-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="492b4-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="492b4-128">See Also</span></span>  
 [<span data-ttu-id="492b4-129">srv_rpcparams &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="492b4-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
