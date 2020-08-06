---
title: srv_paramname (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramname
ms.assetid: 1a53d707-7b06-49cc-a0df-ac727cfe953f
author: rothja
ms.author: jroth
ms.openlocfilehash: 2227ac3d46efe7d09abc05964248229f3533d42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685708"
---
# <a name="srv_paramname-extended-stored-procedure-api"></a><span data-ttu-id="0d09d-102">srv_paramname (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="0d09d-102">srv_paramname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="0d09d-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="0d09d-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="0d09d-104">Retorna o nome de um parâmetro de chamada de procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="0d09d-104">Returns the name of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d09d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0d09d-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_paramname (  
SRV_PROC * srvproc,intn, int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d09d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0d09d-106">Arguments</span></span>  
 <span data-ttu-id="0d09d-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="0d09d-107">*srvproc*</span></span>  
 <span data-ttu-id="0d09d-108">É um ponteiro para a estrutura SRV_PROC que identifica uma conexão de cliente específica (nesse caso, o identificador que recebeu a chamada do procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="0d09d-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="0d09d-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="0d09d-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="0d09d-110">*n*</span><span class="sxs-lookup"><span data-stu-id="0d09d-110">*n*</span></span>  
 <span data-ttu-id="0d09d-111">Indica o número do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0d09d-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="0d09d-112">O primeiro parâmetro é 1.</span><span class="sxs-lookup"><span data-stu-id="0d09d-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="0d09d-113">*Len*</span><span class="sxs-lookup"><span data-stu-id="0d09d-113">*len*</span></span>  
 <span data-ttu-id="0d09d-114">Fornece um ponteiro para uma variável `int` que contém o comprimento, em bytes, do nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0d09d-114">Provides a pointer to an `int` variable that contains the length, in bytes, of the parameter name.</span></span> <span data-ttu-id="0d09d-115">Se *len* for NULL, o tamanho do nome do parâmetro do procedimento armazenado remoto não será retornado.</span><span class="sxs-lookup"><span data-stu-id="0d09d-115">If *len* is NULL, the length of the remote stored procedure parameter name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="0d09d-116">Retornos</span><span class="sxs-lookup"><span data-stu-id="0d09d-116">Returns</span></span>  
 <span data-ttu-id="0d09d-117">Um ponteiro para uma cadeia de caracteres com terminação nula que contém o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0d09d-117">A pointer to a null-terminated character string that contains the parameter name.</span></span> <span data-ttu-id="0d09d-118">O tamanho do nome do parâmetro é armazenado em *len*.</span><span class="sxs-lookup"><span data-stu-id="0d09d-118">The length of the parameter name is stored in *len*.</span></span> <span data-ttu-id="0d09d-119">Se não houver *n*-ésimo parâmetro nem um procedimento armazenado remoto, será retornado NULL, *len* será definido como -1 e uma mensagem de erro informativa será enviada.</span><span class="sxs-lookup"><span data-stu-id="0d09d-119">If there is no *n*th parameter or no remote stored procedure, it returns NULL, *len* is set to -1, and an informational error message is sent.</span></span> <span data-ttu-id="0d09d-120">Se o nome do parâmetro for o NULL, *len* será definido como 0 e uma cadeia de caracteres vazia que termina em nulo será retornada.</span><span class="sxs-lookup"><span data-stu-id="0d09d-120">If the parameter name is NULL, *len* is set to 0 and a null-terminated empty string is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d09d-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="0d09d-121">Remarks</span></span>  
 <span data-ttu-id="0d09d-122">Essa função obtém o nome de um parâmetro de chamada de procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="0d09d-122">This function gets the name of a remote stored procedure call parameter.</span></span> <span data-ttu-id="0d09d-123">Quando uma chamada de procedimento armazenado remoto é feita com parâmetros, os parâmetros podem ser passados pelo nome ou pela posição (sem-nome).</span><span class="sxs-lookup"><span data-stu-id="0d09d-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="0d09d-124">Se a chamada de procedimento armazenado remoto for feita com alguns parâmetros transmitidos pelo nome e outros pela posição, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="0d09d-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="0d09d-125">O manipulador SRV_RPC ainda é chamado, mas aparece como se não houvesse parâmetros e **srv_rpcparams** retorna 0.</span><span class="sxs-lookup"><span data-stu-id="0d09d-125">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0d09d-126">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="0d09d-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="0d09d-127">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="0d09d-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d09d-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0d09d-128">See Also</span></span>  
 [<span data-ttu-id="0d09d-129">srv_rpcparams &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="0d09d-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
