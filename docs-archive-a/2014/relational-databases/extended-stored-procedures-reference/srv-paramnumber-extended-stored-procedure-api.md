---
title: srv_paramnumber (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramnumber
ms.assetid: d7a6dbff-71d9-4297-8a4f-bfd2876fe204
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e621101c909ef251c40f38713e438d8e40d08a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576392"
---
# <a name="srv_paramnumber-extended-stored-procedure-api"></a><span data-ttu-id="a5ad6-102">srv_paramnumber (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="a5ad6-102">srv_paramnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="a5ad6-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="a5ad6-104">Retorna o número de um parâmetro de chamada de procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-104">Returns the number of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ad6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a5ad6-105">Syntax</span></span>  
  
```  
  
int srv_paramnumber (  
SRV_PROC *  
srvproc  
,  
DBCHAR *  
name  
,   
int  
namelen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a5ad6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a5ad6-106">Arguments</span></span>  
 <span data-ttu-id="a5ad6-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="a5ad6-107">*srvproc*</span></span>  
 <span data-ttu-id="a5ad6-108">É um ponteiro para a estrutura SRV_PROC que identifica uma conexão de cliente específica (nesse caso, o identificador que recebeu a chamada do procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="a5ad6-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="a5ad6-110">*name*</span><span class="sxs-lookup"><span data-stu-id="a5ad6-110">*name*</span></span>  
 <span data-ttu-id="a5ad6-111">É um ponteiro para o *name* do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-111">Is a pointer to the parameter *name*.</span></span>  
  
 <span data-ttu-id="a5ad6-112">*namelen*</span><span class="sxs-lookup"><span data-stu-id="a5ad6-112">*namelen*</span></span>  
 <span data-ttu-id="a5ad6-113">É o tamanho total de *name*.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-113">Is the length of *name*.</span></span> <span data-ttu-id="a5ad6-114">Se *name* terminar em nulo, defina *namelen* como SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-114">If *name* is null-terminated, set *namelen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="a5ad6-115">Retornos</span><span class="sxs-lookup"><span data-stu-id="a5ad6-115">Returns</span></span>  
 <span data-ttu-id="a5ad6-116">O número do parâmetro nomeado.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-116">The parameter number of the named parameter.</span></span> <span data-ttu-id="a5ad6-117">O primeiro parâmetro é 1.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-117">The first parameter is 1.</span></span> <span data-ttu-id="a5ad6-118">Se não houver nenhum parâmetro nomeado como *name* ou nenhum procedimento armazenado remoto, 0 será retornado e uma mensagem será gerada.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-118">If there is no parameter named *name* or no remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5ad6-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="a5ad6-119">Remarks</span></span>  
 <span data-ttu-id="a5ad6-120">Quando uma chamada de procedimento armazenado remoto é feita com parâmetros, os parâmetros podem ser passados pelo nome ou pela posição (sem-nome).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-120">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="a5ad6-121">Se a chamada de procedimento armazenado remoto for feita com alguns parâmetros transmitidos pelo nome e outros pela posição, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-121">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="a5ad6-122">O manipulador SRV_RPC ainda é chamado, mas aparece como se não houvesse parâmetros e **srv_rpcparams** retorna 0.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-122">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a5ad6-123">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="a5ad6-123">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="a5ad6-124">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="a5ad6-124">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ad6-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a5ad6-125">See Also</span></span>  
 [<span data-ttu-id="a5ad6-126">srv_rpcparams &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ad6-126">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
