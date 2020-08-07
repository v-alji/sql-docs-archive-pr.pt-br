---
title: srv_paramdata (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramdata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramdata
ms.assetid: 3104514d-b404-47c9-b6d7-928106384874
author: rothja
ms.author: jroth
ms.openlocfilehash: 092ca5b811a12c3e6b199a6041ce6e4f8e02f4b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576395"
---
# <a name="srv_paramdata-extended-stored-procedure-api"></a><span data-ttu-id="b79bd-102">srv_paramdata (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="b79bd-102">srv_paramdata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="b79bd-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="b79bd-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="b79bd-104">Retorna o valor de um parâmetro de chamada de procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="b79bd-104">Returns the value of a remote stored procedure call parameter.</span></span> <span data-ttu-id="b79bd-105">Essa função foi substituída pela função **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="b79bd-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b79bd-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b79bd-106">Syntax</span></span>  
  
```  
  
void * srv_paramdata (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="b79bd-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b79bd-107">Arguments</span></span>  
 <span data-ttu-id="b79bd-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="b79bd-108">*srvproc*</span></span>  
 <span data-ttu-id="b79bd-109">É um ponteiro para a estrutura SRV_PROC que identifica uma conexão de cliente específica (nesse caso, o identificador que recebeu a chamada do procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="b79bd-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="b79bd-110">A estrutura contém informações que a biblioteca do procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="b79bd-110">The structure contains information the Extended Stored Procedure library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="b79bd-111">*n*</span><span class="sxs-lookup"><span data-stu-id="b79bd-111">*n*</span></span>  
 <span data-ttu-id="b79bd-112">É o número do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b79bd-112">Is the number of the parameter.</span></span> <span data-ttu-id="b79bd-113">O primeiro parâmetro equivale ao número 1.</span><span class="sxs-lookup"><span data-stu-id="b79bd-113">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="b79bd-114">Retornos</span><span class="sxs-lookup"><span data-stu-id="b79bd-114">Returns</span></span>  
 <span data-ttu-id="b79bd-115">Um ponteiro para o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b79bd-115">A pointer to the parameter value.</span></span> <span data-ttu-id="b79bd-116">Se o *n*-ésimo parâmetro for NULL, se não houver *n*-ésimo parâmetro ou não houver procedimento armazenado remoto, retornará NULL.</span><span class="sxs-lookup"><span data-stu-id="b79bd-116">If the *n*th parameter is NULL, there is no *n*th parameter, or there is no remote stored procedure, returns NULL.</span></span> <span data-ttu-id="b79bd-117">Se o valor do parâmetro for uma cadeia de caracteres, ele não pode terminar com caractere nulo.</span><span class="sxs-lookup"><span data-stu-id="b79bd-117">If the parameter value is a string, it might not be null-terminated.</span></span> <span data-ttu-id="b79bd-118">Use **srv_paramlen** para determinar o tamanho da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b79bd-118">Use **srv_paramlen** to determine the length of the string.</span></span>  
  
 <span data-ttu-id="b79bd-119">Essa função retornará os valores a seguir, se o parâmetro for um dos [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="b79bd-119">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="b79bd-120">Os dados de ponteiro indicam se o ponteiro para o tipo de dados é válido (VP), NULL ou não aplicável (N/A) e o conteúdo dos dados apontados.</span><span class="sxs-lookup"><span data-stu-id="b79bd-120">Pointer data includes whether the pointer for the data type is valid (VP), NULL, or not applicable (N/A), and the contents of the data pointed to.</span></span>  
  
|<span data-ttu-id="b79bd-121">Novos tipos de dados</span><span class="sxs-lookup"><span data-stu-id="b79bd-121">New data types</span></span>|<span data-ttu-id="b79bd-122">Comprimento dos dados de entrada</span><span class="sxs-lookup"><span data-stu-id="b79bd-122">Input data length</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="b79bd-123">BITN</span><span class="sxs-lookup"><span data-stu-id="b79bd-123">BITN</span></span>|<span data-ttu-id="b79bd-124">**NULL:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="b79bd-124">**NULL:** VP, NULL</span></span><br /><br /> <span data-ttu-id="b79bd-125">**ZERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="b79bd-125">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="b79bd-126">**>= 255:** N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-126">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="b79bd-127">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-127">**<255:** N/A</span></span>|  
|<span data-ttu-id="b79bd-128">BIGVARCHAR</span><span class="sxs-lookup"><span data-stu-id="b79bd-128">BIGVARCHAR</span></span>|<span data-ttu-id="b79bd-129">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-129">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="b79bd-130">**ZERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="b79bd-130">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="b79bd-131">**>=255:** VP, 255 chars</span><span class="sxs-lookup"><span data-stu-id="b79bd-131">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="b79bd-132">**<255:** VP, dados reais</span><span class="sxs-lookup"><span data-stu-id="b79bd-132">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="b79bd-133">BIGCHAR</span><span class="sxs-lookup"><span data-stu-id="b79bd-133">BIGCHAR</span></span>|<span data-ttu-id="b79bd-134">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-134">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="b79bd-135">**ZERO:** VP, 255 espaços</span><span class="sxs-lookup"><span data-stu-id="b79bd-135">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="b79bd-136">**>=255:** VP, 255 chars</span><span class="sxs-lookup"><span data-stu-id="b79bd-136">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="b79bd-137">**<255:** VP, dados reais + preenchimento (até 255)</span><span class="sxs-lookup"><span data-stu-id="b79bd-137">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="b79bd-138">BIGBINARY</span><span class="sxs-lookup"><span data-stu-id="b79bd-138">BIGBINARY</span></span>|<span data-ttu-id="b79bd-139">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-139">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="b79bd-140">**ZERO:** VP, 255 0x00</span><span class="sxs-lookup"><span data-stu-id="b79bd-140">**ZERO:** VP, 255 0x00</span></span><br /><br /> <span data-ttu-id="b79bd-141">**>=255:** VP, 255 bytes</span><span class="sxs-lookup"><span data-stu-id="b79bd-141">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="b79bd-142">**<255:** VP, dados reais + preenchimento (até 255)</span><span class="sxs-lookup"><span data-stu-id="b79bd-142">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="b79bd-143">BIGVARBINARY</span><span class="sxs-lookup"><span data-stu-id="b79bd-143">BIGVARBINARY</span></span>|<span data-ttu-id="b79bd-144">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-144">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="b79bd-145">**ZERO:** VP, 0x00</span><span class="sxs-lookup"><span data-stu-id="b79bd-145">**ZERO:** VP, 0x00</span></span><br /><br /> <span data-ttu-id="b79bd-146">**>=255:** VP, 255 bytes</span><span class="sxs-lookup"><span data-stu-id="b79bd-146">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="b79bd-147">**<255:** VP, dados reais</span><span class="sxs-lookup"><span data-stu-id="b79bd-147">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="b79bd-148">NCHAR</span><span class="sxs-lookup"><span data-stu-id="b79bd-148">NCHAR</span></span>|<span data-ttu-id="b79bd-149">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-149">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="b79bd-150">**ZERO:** VP, 255 espaços</span><span class="sxs-lookup"><span data-stu-id="b79bd-150">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="b79bd-151">**>=255:** VP, 255 chars</span><span class="sxs-lookup"><span data-stu-id="b79bd-151">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="b79bd-152">**<255:** VP, dados reais + preenchimento (até 255)</span><span class="sxs-lookup"><span data-stu-id="b79bd-152">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="b79bd-153">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="b79bd-153">NVARCHAR</span></span>|<span data-ttu-id="b79bd-154">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-154">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="b79bd-155">**ZERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="b79bd-155">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="b79bd-156">**>=255:** VP, 255 chars</span><span class="sxs-lookup"><span data-stu-id="b79bd-156">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="b79bd-157">**<255:** VP, dados reais</span><span class="sxs-lookup"><span data-stu-id="b79bd-157">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="b79bd-158">NTEXT</span><span class="sxs-lookup"><span data-stu-id="b79bd-158">NTEXT</span></span>|<span data-ttu-id="b79bd-159">**NULL:** N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-159">**NULL:** N/A</span></span><br /><br /> <span data-ttu-id="b79bd-160">**ZERO:** N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-160">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="b79bd-161">**>= 255:** N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-161">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="b79bd-162">\*\* \< 255:\*\* N/A</span><span class="sxs-lookup"><span data-stu-id="b79bd-162">**\<255:** N/A</span></span>|  
  
 <span data-ttu-id="b79bd-163">\* Os dados não terminam em nulo; nenhum aviso é emitido no truncamento de dados >255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b79bd-163">\*   data is not null-terminated; no warning is issued on truncation for data >255 characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b79bd-164">Comentários</span><span class="sxs-lookup"><span data-stu-id="b79bd-164">Remarks</span></span>  
 <span data-ttu-id="b79bd-165">Se você souber o nome do parâmetro, poderá usar **srv_paramnumber** para obter o número do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b79bd-165">If you know the parameter name, you can use **srv_paramnumber** to get the parameter number.</span></span> <span data-ttu-id="b79bd-166">Para determinar se um parâmetro é NULL, use **srv_paramlen**.</span><span class="sxs-lookup"><span data-stu-id="b79bd-166">To determine whether a parameter is NULL, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="b79bd-167">Quando uma chamada de procedimento armazenado remoto for feita com parâmetros, os parâmetros poderão ser passados pelo nome ou pela posição (sem-nome).</span><span class="sxs-lookup"><span data-stu-id="b79bd-167">When a remote stored procedure call is made with parameters, the parameters can be passed by name or by position (unnamed).</span></span> <span data-ttu-id="b79bd-168">Se a chamada de procedimento armazenado remoto for feita com alguns parâmetros transmitidos pelo nome e outros pela posição, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="b79bd-168">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="b79bd-169">Em caso de erro, o manipulador SRV_RPC ainda será chamado, mas aparecerá como se não houvesse parâmetros e **srv_rpcparams** retornará 0.</span><span class="sxs-lookup"><span data-stu-id="b79bd-169">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b79bd-170">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="b79bd-170">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="b79bd-171">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="b79bd-171">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79bd-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b79bd-172">See Also</span></span>  
 [<span data-ttu-id="b79bd-173">srv_rpcparams &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="b79bd-173">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
