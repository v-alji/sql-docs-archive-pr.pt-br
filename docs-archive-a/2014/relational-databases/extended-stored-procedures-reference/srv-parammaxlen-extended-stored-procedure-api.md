---
title: srv_parammaxlen (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_parammaxlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_parammaxlen
ms.assetid: 49bfc29d-f76a-4963-b0e6-b8532dfda850
author: rothja
ms.author: jroth
ms.openlocfilehash: b289743b3de4b115a67a029dcc0261854ee3a40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685709"
---
# <a name="srv_parammaxlen-extended-stored-procedure-api"></a><span data-ttu-id="25dbc-102">srv_parammaxlen (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="25dbc-102">srv_parammaxlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="25dbc-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="25dbc-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="25dbc-104">Retorna o comprimento máximo de dados de um parâmetro de chamada de procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="25dbc-104">Returns the maximum data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="25dbc-105">Essa função foi substituída pela função **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="25dbc-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25dbc-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="25dbc-106">Syntax</span></span>  
  
```  
  
int srv_parammaxlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="25dbc-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="25dbc-107">Arguments</span></span>  
 <span data-ttu-id="25dbc-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="25dbc-108">*srvproc*</span></span>  
 <span data-ttu-id="25dbc-109">É um ponteiro para a estrutura SRV_PROC que identifica uma conexão de cliente específica (nesse caso, o identificador que recebeu a chamada do procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="25dbc-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="25dbc-110">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="25dbc-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="25dbc-111">*n*</span><span class="sxs-lookup"><span data-stu-id="25dbc-111">*n*</span></span>  
 <span data-ttu-id="25dbc-112">Indica o número do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="25dbc-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="25dbc-113">O primeiro parâmetro é 1.</span><span class="sxs-lookup"><span data-stu-id="25dbc-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="25dbc-114">Retornos</span><span class="sxs-lookup"><span data-stu-id="25dbc-114">Returns</span></span>  
 <span data-ttu-id="25dbc-115">O comprimento máximo, em bytes, dos dados do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="25dbc-115">The maximum length, in bytes, of the parameter data.</span></span> <span data-ttu-id="25dbc-116">Se não houver *n*-ésimo parâmetro nem procedimento armazenado remoto, o valor retornado será -1.</span><span class="sxs-lookup"><span data-stu-id="25dbc-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
 <span data-ttu-id="25dbc-117">Essa função retornará os valores a seguir, se o parâmetro for um dos tipos de dados a seguir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25dbc-117">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
|<span data-ttu-id="25dbc-118">Novos tipos de dados</span><span class="sxs-lookup"><span data-stu-id="25dbc-118">New data types</span></span>|<span data-ttu-id="25dbc-119">Comprimento dos dados de entrada</span><span class="sxs-lookup"><span data-stu-id="25dbc-119">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="25dbc-120">**NULL:** 1</span><span class="sxs-lookup"><span data-stu-id="25dbc-120">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="25dbc-121">**Zero:** 1</span><span class="sxs-lookup"><span data-stu-id="25dbc-121">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="25dbc-122">**>= 255:** N/A</span><span class="sxs-lookup"><span data-stu-id="25dbc-122">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="25dbc-123">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="25dbc-123">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="25dbc-124">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-124">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-125">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-125">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-126">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-126">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-127">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-127">**<255:** 255</span></span>|  
|`BIGCHAR`|<span data-ttu-id="25dbc-128">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-128">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-129">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-129">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-130">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-130">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-131">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-131">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="25dbc-132">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-132">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-133">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-133">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-134">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-134">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-135">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-135">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="25dbc-136">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-136">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-137">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-137">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-138">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-138">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-139">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-139">**<255:** 255</span></span>|  
|`NCHAR`|<span data-ttu-id="25dbc-140">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-140">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-141">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-141">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-142">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-142">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-143">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-143">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="25dbc-144">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-144">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-145">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-145">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-146">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-146">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="25dbc-147">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="25dbc-147">**<255:** 255</span></span>|  
|`NTEXT`|<span data-ttu-id="25dbc-148">**Nulo:** -1</span><span class="sxs-lookup"><span data-stu-id="25dbc-148">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="25dbc-149">**ZERO:** -1</span><span class="sxs-lookup"><span data-stu-id="25dbc-149">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="25dbc-150">**>= 255:** -1</span><span class="sxs-lookup"><span data-stu-id="25dbc-150">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="25dbc-151">\*\* \< 255:\*\* -1</span><span class="sxs-lookup"><span data-stu-id="25dbc-151">**\<255:** -1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25dbc-152">Comentários</span><span class="sxs-lookup"><span data-stu-id="25dbc-152">Remarks</span></span>  
 <span data-ttu-id="25dbc-153">Cada parâmetro de procedimento armazenado remoto tem um comprimento de dados real e um máximo.</span><span class="sxs-lookup"><span data-stu-id="25dbc-153">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="25dbc-154">Para tipos de dados padrão de comprimento fixo que não permitem valores nulos, os comprimentos real e máximo são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="25dbc-154">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="25dbc-155">Para tipos de dados de comprimento de variável, os comprimentos podem variar.</span><span class="sxs-lookup"><span data-stu-id="25dbc-155">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="25dbc-156">Por exemplo, um parâmetro declarado como **varchar(30)** pode ter dados de apenas 10 bytes de comprimento.</span><span class="sxs-lookup"><span data-stu-id="25dbc-156">For example, a parameter declared as **varchar(30)** can have data that is only 10 bytes long.</span></span> <span data-ttu-id="25dbc-157">O comprimento real do parâmetro é 10 e seu comprimento máximo é 30.</span><span class="sxs-lookup"><span data-stu-id="25dbc-157">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="25dbc-158">A função **srv_parammaxlen** obtém o tamanho máximo de dados de um procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="25dbc-158">The **srv_parammaxlen** function gets the maximum data length of a remote stored procedure.</span></span> <span data-ttu-id="25dbc-159">Para obter o tamanho real de um parâmetro, use **srv_paramlen**.</span><span class="sxs-lookup"><span data-stu-id="25dbc-159">To obtain the actual length of a parameter, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="25dbc-160">Quando uma chamada de procedimento armazenado remoto é feita com parâmetros, os parâmetros podem ser passados pelo nome ou pela posição (sem-nome).</span><span class="sxs-lookup"><span data-stu-id="25dbc-160">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="25dbc-161">Se a chamada de procedimento armazenado remoto for feita com alguns parâmetros transmitidos pelo nome e outros pela posição, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="25dbc-161">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="25dbc-162">O manipulador SRV_RPC ainda é chamado, mas aparece como se não houvesse parâmetros e **srv_rpcparams** retorna 0.</span><span class="sxs-lookup"><span data-stu-id="25dbc-162">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="25dbc-163">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="25dbc-163">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="25dbc-164">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="25dbc-164">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25dbc-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25dbc-165">See Also</span></span>  
 <span data-ttu-id="25dbc-166">[srv_paraminfo &#40;API de procedimento armazenado estendido&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="25dbc-166">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="25dbc-167">srv_rpcparams &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="25dbc-167">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
