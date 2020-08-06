---
title: srv_paramtype (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramtype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramtype
ms.assetid: badc6d36-8a87-42b5-b28c-9c4f5ded8552
author: rothja
ms.author: jroth
ms.openlocfilehash: 0c4b4006f8214670e3bd2bddfbaabe917fb9d778
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571396"
---
# <a name="srv_paramtype-extended-stored-procedure-api"></a><span data-ttu-id="9fcd6-102">srv_paramtype (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="9fcd6-102">srv_paramtype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9fcd6-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="9fcd6-104">Retorna o tipo de dados de um parâmetro de chamada de procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-104">Returns the data type of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fcd6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9fcd6-105">Syntax</span></span>  
  
```  
  
int srv_paramtype (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="9fcd6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9fcd6-106">Arguments</span></span>  
 <span data-ttu-id="9fcd6-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="9fcd6-107">*srvproc*</span></span>  
 <span data-ttu-id="9fcd6-108">É um ponteiro para a estrutura SRV_PROC que identifica uma conexão de cliente específica (nesse caso, o identificador que recebeu a chamada do procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="9fcd6-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="9fcd6-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="9fcd6-110">*n*</span><span class="sxs-lookup"><span data-stu-id="9fcd6-110">*n*</span></span>  
 <span data-ttu-id="9fcd6-111">Indica o número do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="9fcd6-112">O primeiro parâmetro é 1.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-112">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="9fcd6-113">Retornos</span><span class="sxs-lookup"><span data-stu-id="9fcd6-113">Returns</span></span>  
 <span data-ttu-id="9fcd6-114">Um valor de token para o tipo de dados do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-114">A token value for the data type of the parameter.</span></span> <span data-ttu-id="9fcd6-115">Para obter informações sobre tipos de dados, consulte [Tipos de dados &#40;API de Procedimento Armazenado Estendido&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="9fcd6-115">For information about data types, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="9fcd6-116">Se não houver *n*-ésimo parâmetro nem procedimento armazenado remoto, o valor retornado será -1.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns - 1.</span></span>  
  
 <span data-ttu-id="9fcd6-117">Essa função retornará os valores a seguir, se o parâmetro for um dos [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-117">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="9fcd6-118">Novos tipos de dados</span><span class="sxs-lookup"><span data-stu-id="9fcd6-118">New data types</span></span>|<span data-ttu-id="9fcd6-119">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="9fcd6-119">Return value</span></span>|  
|--------------------|------------------|  
|`BITN`|<span data-ttu-id="9fcd6-120">SRVBIT</span><span class="sxs-lookup"><span data-stu-id="9fcd6-120">SRVBIT</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="9fcd6-121">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="9fcd6-121">VARCHAR</span></span>|  
|`BIGCHAR`|<span data-ttu-id="9fcd6-122">CHAR</span><span class="sxs-lookup"><span data-stu-id="9fcd6-122">CHAR</span></span>|  
|`BIGBINARY`|<span data-ttu-id="9fcd6-123">BINARY</span><span class="sxs-lookup"><span data-stu-id="9fcd6-123">BINARY</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="9fcd6-124">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="9fcd6-124">VARBINARY</span></span>|  
|`NCHAR`|<span data-ttu-id="9fcd6-125">CHAR</span><span class="sxs-lookup"><span data-stu-id="9fcd6-125">CHAR</span></span>|  
|`NVARCHAR`|<span data-ttu-id="9fcd6-126">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="9fcd6-126">VARCHAR</span></span>|  
|`NTEXT`|<span data-ttu-id="9fcd6-127">-1</span><span class="sxs-lookup"><span data-stu-id="9fcd6-127">-1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fcd6-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="9fcd6-128">Remarks</span></span>  
 <span data-ttu-id="9fcd6-129">Quando uma chamada de procedimento armazenado remoto é feita com parâmetros, os parâmetros podem ser passados pelo nome ou pela posição (sem-nome).</span><span class="sxs-lookup"><span data-stu-id="9fcd6-129">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="9fcd6-130">Se a chamada de procedimento armazenado remoto for feita com alguns parâmetros transmitidos pelo nome e outros pela posição, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-130">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="9fcd6-131">O manipulador de SRV_RPC ainda é chamado, mas aparece como se não houvesse parâmetros e **srv_rpcparams** retorna 0.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-131">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9fcd6-132">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="9fcd6-132">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="9fcd6-133">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="9fcd6-133">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fcd6-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9fcd6-134">See Also</span></span>  
 <span data-ttu-id="9fcd6-135">[srv_paraminfo &#40;API de procedimento armazenado estendido&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="9fcd6-135">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="9fcd6-136">srv_rpcparams &#40;API de Procedimento Armazenado Estendido&#41;</span><span class="sxs-lookup"><span data-stu-id="9fcd6-136">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
