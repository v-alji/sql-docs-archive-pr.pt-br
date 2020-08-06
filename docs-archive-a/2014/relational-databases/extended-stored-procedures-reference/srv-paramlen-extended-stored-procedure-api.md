---
title: srv_paramlen (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramlen
ms.assetid: d1fe92ff-cad6-4396-8216-125e5642e81e
author: rothja
ms.author: jroth
ms.openlocfilehash: fc2a0fa7f8409767a2afaa9c4c621ea72732b701
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685711"
---
# <a name="srv_paramlen-extended-stored-procedure-api"></a><span data-ttu-id="69e60-102">srv_paramlen (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="69e60-102">srv_paramlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="69e60-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="69e60-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="69e60-104">Retorna o comprimento de dados de um parâmetro de chamada de procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="69e60-104">Returns the data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="69e60-105">Essa função foi substituída pela função **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="69e60-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e60-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="69e60-106">Syntax</span></span>  
  
```  
  
int srv_paramlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="69e60-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="69e60-107">Arguments</span></span>  
 <span data-ttu-id="69e60-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="69e60-108">*srvproc*</span></span>  
 <span data-ttu-id="69e60-109">É um ponteiro para a estrutura SRV_PROC que identifica uma conexão de cliente específica (nesse caso, o identificador que recebeu a chamada do procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="69e60-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="69e60-110">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="69e60-110">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="69e60-111">*n*</span><span class="sxs-lookup"><span data-stu-id="69e60-111">*n*</span></span>  
 <span data-ttu-id="69e60-112">Indica o número do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="69e60-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="69e60-113">O primeiro parâmetro é 1.</span><span class="sxs-lookup"><span data-stu-id="69e60-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="69e60-114">Retornos</span><span class="sxs-lookup"><span data-stu-id="69e60-114">Returns</span></span>  
 <span data-ttu-id="69e60-115">O comprimento real, em bytes, dos dados do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="69e60-115">The actual length, in bytes, of the parameter data.</span></span> <span data-ttu-id="69e60-116">Se não houver *n*-ésimo parâmetro nem procedimento armazenado remoto, o valor retornado será -1.</span><span class="sxs-lookup"><span data-stu-id="69e60-116">If there is no *n*th parameter or there is no remote stored procedure, it returns -1.</span></span> <span data-ttu-id="69e60-117">Se o *n*-ésimo parâmetro for NULL, retornará 0.</span><span class="sxs-lookup"><span data-stu-id="69e60-117">If the *n*th parameter is NULL, it returns 0.</span></span>  
  
 <span data-ttu-id="69e60-118">Essa função retornará os seguintes valores, se o parâmetro for um dos seguintes [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] tipos de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="69e60-118">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] system data types.</span></span>  
  
|<span data-ttu-id="69e60-119">Novos tipos de dados</span><span class="sxs-lookup"><span data-stu-id="69e60-119">New data types</span></span>|<span data-ttu-id="69e60-120">Comprimento dos dados de entrada</span><span class="sxs-lookup"><span data-stu-id="69e60-120">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="69e60-121">**NULL:** 1</span><span class="sxs-lookup"><span data-stu-id="69e60-121">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="69e60-122">**Zero:** 1</span><span class="sxs-lookup"><span data-stu-id="69e60-122">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="69e60-123">**>= 255:** N/A</span><span class="sxs-lookup"><span data-stu-id="69e60-123">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="69e60-124">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="69e60-124">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="69e60-125">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="69e60-125">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="69e60-126">**Zero:** 1</span><span class="sxs-lookup"><span data-stu-id="69e60-126">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="69e60-127">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-127">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="69e60-128">\**<255:\*\*\*len* real</span><span class="sxs-lookup"><span data-stu-id="69e60-128">**<255:** actual *len*</span></span>|  
|`BIGCHAR`|<span data-ttu-id="69e60-129">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="69e60-129">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="69e60-130">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-130">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="69e60-131">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-131">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="69e60-132">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-132">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="69e60-133">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="69e60-133">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="69e60-134">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-134">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="69e60-135">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-135">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="69e60-136">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-136">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="69e60-137">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="69e60-137">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="69e60-138">**Zero:** 1</span><span class="sxs-lookup"><span data-stu-id="69e60-138">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="69e60-139">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-139">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="69e60-140">\**<255:\*\*\*len* real</span><span class="sxs-lookup"><span data-stu-id="69e60-140">**<255:** actual *len*</span></span>|  
|`NCHAR`|<span data-ttu-id="69e60-141">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="69e60-141">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="69e60-142">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-142">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="69e60-143">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-143">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="69e60-144">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-144">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="69e60-145">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="69e60-145">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="69e60-146">**Zero:** 1</span><span class="sxs-lookup"><span data-stu-id="69e60-146">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="69e60-147">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="69e60-147">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="69e60-148">\**<255:\*\*\*len* real</span><span class="sxs-lookup"><span data-stu-id="69e60-148">**<255:** actual *len*</span></span>|  
|`NTEXT`|<span data-ttu-id="69e60-149">**Nulo:** -1</span><span class="sxs-lookup"><span data-stu-id="69e60-149">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="69e60-150">**ZERO:** -1</span><span class="sxs-lookup"><span data-stu-id="69e60-150">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="69e60-151">**>= 255:** -1</span><span class="sxs-lookup"><span data-stu-id="69e60-151">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="69e60-152">**<255:** -1</span><span class="sxs-lookup"><span data-stu-id="69e60-152">**<255:** -1</span></span>|  
  
 <span data-ttu-id="69e60-153">\*   *len* real = tamanho da cadeia de caracteres de vários bytes (cch)</span><span class="sxs-lookup"><span data-stu-id="69e60-153">\*   actual *len* = Length of multibyte character string (cch)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69e60-154">Comentários</span><span class="sxs-lookup"><span data-stu-id="69e60-154">Remarks</span></span>  
 <span data-ttu-id="69e60-155">Cada parâmetro de procedimento armazenado remoto tem um comprimento de dados real e um máximo.</span><span class="sxs-lookup"><span data-stu-id="69e60-155">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="69e60-156">Para tipos de dados padrão de comprimento fixo que não permitem valores nulos, os comprimentos real e máximo são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="69e60-156">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="69e60-157">Para tipos de dados de comprimento de variável, os comprimentos podem variar.</span><span class="sxs-lookup"><span data-stu-id="69e60-157">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="69e60-158">Por exemplo, um parâmetro declarado como `varchar(30)` pode ter dados de apenas 10 bytes de comprimento.</span><span class="sxs-lookup"><span data-stu-id="69e60-158">For example, a parameter declared as `varchar(30)` can have data that is only 10 bytes long.</span></span> <span data-ttu-id="69e60-159">O comprimento real do parâmetro é 10 e seu comprimento máximo é 30.</span><span class="sxs-lookup"><span data-stu-id="69e60-159">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="69e60-160">A função **srv_paramlen** obtém o tamanho real de dados, em bytes, de um procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="69e60-160">The **srv_paramlen** function gets the actual data length, in bytes, of a remote stored procedure.</span></span> <span data-ttu-id="69e60-161">Para obter o tamanho máximo de dados de um parâmetro, use **srv_parammaxlen**.</span><span class="sxs-lookup"><span data-stu-id="69e60-161">To obtain the maximum data length of a parameter, use **srv_parammaxlen**.</span></span>  
  
 <span data-ttu-id="69e60-162">Quando uma chamada de procedimento armazenado remoto é feita com parâmetros, os parâmetros podem ser passados pelo nome ou pela posição (sem-nome).</span><span class="sxs-lookup"><span data-stu-id="69e60-162">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="69e60-163">Se a chamada de procedimento armazenado remoto for feita com alguns parâmetros transmitidos pelo nome e outros pela posição, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="69e60-163">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="69e60-164">O manipulador de SRV_RPC ainda é chamado, mas aparece como se não houvesse parâmetros e **srv_rpcparams** retorna 0.</span><span class="sxs-lookup"><span data-stu-id="69e60-164">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="69e60-165">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="69e60-165">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="69e60-166">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="69e60-166">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e60-167">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="69e60-167">See Also</span></span>  
 <span data-ttu-id="69e60-168">[srv_paraminfo &#40;API de procedimento armazenado estendido&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="69e60-168">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="69e60-169">srv_rpcparams &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="69e60-169">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
