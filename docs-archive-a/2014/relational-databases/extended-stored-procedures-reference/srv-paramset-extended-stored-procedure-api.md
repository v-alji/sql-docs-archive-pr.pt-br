---
title: srv_paramset (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramset
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramset
ms.assetid: 2a509206-a1b8-4b20-b0a2-ef680cef7bd8
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ebe308e5e0c8fc24382582fb71db2f48c77541e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570021"
---
# <a name="srv_paramset-extended-stored-procedure-api"></a><span data-ttu-id="768be-102">srv_paramset (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="768be-102">srv_paramset (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="768be-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="768be-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="768be-104">Define o valor de um parâmetro de retorno de chamada do procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="768be-104">Sets the value of a remote stored procedure call return parameter.</span></span> <span data-ttu-id="768be-105">Esta função foi substituída pela função **srv_paramsetoutput**.</span><span class="sxs-lookup"><span data-stu-id="768be-105">This function has been superseded by the **srv_paramsetoutput** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="768be-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="768be-106">Syntax</span></span>  
  
```  
  
int srv_paramset (  
SRV_PROC *  
srvproc  
,  
int  
n  
,   
void *  
data  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="768be-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="768be-107">Arguments</span></span>  
 <span data-ttu-id="768be-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="768be-108">*srvproc*</span></span>  
 <span data-ttu-id="768be-109">É um ponteiro para a estrutura SRV_PROC que identifica uma conexão de cliente específica (nesse caso, o identificador que recebeu a chamada do procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="768be-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="768be-110">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="768be-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="768be-111">*n*</span><span class="sxs-lookup"><span data-stu-id="768be-111">*n*</span></span>  
 <span data-ttu-id="768be-112">Indica o número do parâmetro a ser definido.</span><span class="sxs-lookup"><span data-stu-id="768be-112">Indicates the number of the parameter to set.</span></span> <span data-ttu-id="768be-113">O primeiro parâmetro é 1.</span><span class="sxs-lookup"><span data-stu-id="768be-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="768be-114">*data*</span><span class="sxs-lookup"><span data-stu-id="768be-114">*data*</span></span>  
 <span data-ttu-id="768be-115">É um ponteiro para o valor dos dados a ser enviado de volta ao cliente como o parâmetro de retorno do procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="768be-115">Is a pointer to the data value to be sent back to the client as the remote stored procedure return parameter.</span></span>  
  
 <span data-ttu-id="768be-116">*Len*</span><span class="sxs-lookup"><span data-stu-id="768be-116">*len*</span></span>  
 <span data-ttu-id="768be-117">Especifica o comprimento dos dados a serem retornados.</span><span class="sxs-lookup"><span data-stu-id="768be-117">Specifies the actual length of the data to be returned.</span></span> <span data-ttu-id="768be-118">Se o tipo de dados do parâmetro tiver um tamanho constante e não permitir valores nulos (por exemplo, *srvbit* ou *srvint1*), *len* será ignorado.</span><span class="sxs-lookup"><span data-stu-id="768be-118">If the data type of the parameter is of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *len* is ignored.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="768be-119">Retornos</span><span class="sxs-lookup"><span data-stu-id="768be-119">Returns</span></span>  
 <span data-ttu-id="768be-120">SUCCEED se o valor do parâmetro tiver sido definido com êxito; caso contrário, FAIL.</span><span class="sxs-lookup"><span data-stu-id="768be-120">SUCCEED if the parameter value was successfully set; otherwise, FAIL.</span></span> <span data-ttu-id="768be-121">FAIL será retornado quando não houver procedimentos armazenados remotos atuais, quando não existir o *n*-ésimo parâmetro de procedimento armazenado remoto, quando o parâmetro não for um parâmetro de retorno e quando o argumento *len* não for válido.</span><span class="sxs-lookup"><span data-stu-id="768be-121">FAIL is returned when there is no current remote stored procedure, when there is no *n*th remote stored procedure parameter, when the parameter is not a return parameter, and when the *len* argument is not legal.</span></span>  
  
 <span data-ttu-id="768be-122">Se *len* for 0, NULL será retornado.</span><span class="sxs-lookup"><span data-stu-id="768be-122">If *len*is 0, it returns NULL.</span></span> <span data-ttu-id="768be-123">Definir *len* como 0 é o único modo de retornar NULL ao cliente.</span><span class="sxs-lookup"><span data-stu-id="768be-123">Setting *len* to 0 is the only way to return NULL to the client.</span></span>  
  
 <span data-ttu-id="768be-124">Essa função retornará os valores a seguir, se o parâmetro for um dos [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="768be-124">This function returns the following values, if the parameter is one of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="768be-125">Novos tipos de dados</span><span class="sxs-lookup"><span data-stu-id="768be-125">New data types</span></span>|<span data-ttu-id="768be-126">Comprimento dos dados de retorno</span><span class="sxs-lookup"><span data-stu-id="768be-126">Return data length</span></span>|  
|--------------------|------------------------|  
|`BITN`|<span data-ttu-id="768be-127">**NULL:** *len* = 0, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-127">**NULL:** *len* = 0, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-128">**ZERO:** N/A</span><span class="sxs-lookup"><span data-stu-id="768be-128">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="768be-129">**>= 255:** N/A</span><span class="sxs-lookup"><span data-stu-id="768be-129">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="768be-130">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="768be-130">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="768be-131">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-131">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="768be-132">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-132">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-133">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-133">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-134">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-134">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGCHAR`|<span data-ttu-id="768be-135">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-135">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="768be-136">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-136">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-137">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-137">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-138">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-138">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGBINARY`|<span data-ttu-id="768be-139">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-139">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="768be-140">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-140">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-141">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-141">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-142">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-142">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="768be-143">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-143">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="768be-144">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-144">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-145">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-145">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-146">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-146">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="768be-147">NCHAR</span><span class="sxs-lookup"><span data-stu-id="768be-147">NCHAR</span></span>|<span data-ttu-id="768be-148">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-148">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="768be-149">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-149">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-150">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-150">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-151">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-151">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="768be-152">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="768be-152">NVARCHAR</span></span>|<span data-ttu-id="768be-153">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-153">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="768be-154">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-154">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-155">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-155">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-156">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="768be-156">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`NTEXT`|<span data-ttu-id="768be-157">**NULL:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-157">**NULL:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-158">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-158">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-159">**>=255:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-159">**>=255:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="768be-160">\*\* \< 255:\*\* *Len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="768be-160">**\<255:** *len* = IG, data = IG, RET = 0</span></span>|  
|<span data-ttu-id="768be-161">RET = Valor de retorno de srv_paramset</span><span class="sxs-lookup"><span data-stu-id="768be-161">RET = Return value of srv_paramset</span></span>||  
|<span data-ttu-id="768be-162">IG = Valor será ignorado</span><span class="sxs-lookup"><span data-stu-id="768be-162">IG = Value will be ignored</span></span>||  
|<span data-ttu-id="768be-163">valid = Qualquer ponteiro válido para dados</span><span class="sxs-lookup"><span data-stu-id="768be-163">valid = Any valid pointer to data</span></span>||  
  
## <a name="remarks"></a><span data-ttu-id="768be-164">Comentários</span><span class="sxs-lookup"><span data-stu-id="768be-164">Remarks</span></span>  
 <span data-ttu-id="768be-165">Os parâmetros contêm dados passados entre os clientes e o aplicativo com procedimentos armazenados remotos.</span><span class="sxs-lookup"><span data-stu-id="768be-165">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="768be-166">O cliente pode especificar certos parâmetros como parâmetros de retorno.</span><span class="sxs-lookup"><span data-stu-id="768be-166">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="768be-167">Esses parâmetros de retorno podem conter valores que o aplicativo servidor Open Data Services devolve ao cliente.</span><span class="sxs-lookup"><span data-stu-id="768be-167">These return parameters can contain values that the Open Data Services server application passes back to the client.</span></span> <span data-ttu-id="768be-168">Usar parâmetros de retorno equivale a passar parâmetros por referência.</span><span class="sxs-lookup"><span data-stu-id="768be-168">Using return parameters is analogous to passing parameters by reference.</span></span>  
  
 <span data-ttu-id="768be-169">Você não pode definir o valor de retorno para um parâmetro que não foi invocado como um parâmetro de retorno.</span><span class="sxs-lookup"><span data-stu-id="768be-169">You cannot set the return value for a parameter that wasn't invoked as a return parameter.</span></span> <span data-ttu-id="768be-170">Use **srv_paramstatus** para determinar como o parâmetro foi invocado.</span><span class="sxs-lookup"><span data-stu-id="768be-170">You can use **srv_paramstatus** to determine how the parameter was invoked.</span></span>  
  
 <span data-ttu-id="768be-171">Esta função define o valor de retorno para um parâmetro, mas não envia o valor de retorno ao cliente.</span><span class="sxs-lookup"><span data-stu-id="768be-171">This function sets the return value for a parameter but it does not actually send the return value to the client.</span></span> <span data-ttu-id="768be-172">Todos os parâmetros de retorno, independentemente se seus valores retornados foram ou não com **srv_paramset**, serão automaticamente enviados ao cliente quando **srv_senddone** for chamado com o sinalizador de status SRV_DONE_FINAL definido.</span><span class="sxs-lookup"><span data-stu-id="768be-172">All return parameters, whether their return values have been set with **srv_paramset** or not, are automatically sent to the client when **srv_senddone** is called with the status flag SRV_DONE_FINAL set.</span></span>  
  
 <span data-ttu-id="768be-173">Quando uma chamada de procedimento armazenado remoto é feita com parâmetros, os parâmetros podem ser passados pelo nome ou pela posição (sem-nome).</span><span class="sxs-lookup"><span data-stu-id="768be-173">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="768be-174">Se a chamada de procedimento armazenado remoto for feita com alguns parâmetros transmitidos pelo nome e outros pela posição, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="768be-174">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="768be-175">O manipulador SRV_RPC ainda é chamado, mas aparece como se não houvesse parâmetros e **srv_rpcparams** retorna 0.</span><span class="sxs-lookup"><span data-stu-id="768be-175">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="768be-176">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="768be-176">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="768be-177">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="768be-177">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="768be-178">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="768be-178">See Also</span></span>  
 [<span data-ttu-id="768be-179">srv_paramsetoutput &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="768be-179">srv_paramsetoutput &#40;Extended Stored Procedure API&#41;</span></span>](srv-paramsetoutput-extended-stored-procedure-api.md)  
  
  
