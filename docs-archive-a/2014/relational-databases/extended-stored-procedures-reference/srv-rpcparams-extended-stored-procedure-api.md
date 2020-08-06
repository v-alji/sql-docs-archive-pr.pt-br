---
title: srv_rpcparams (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcparams
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcparams
ms.assetid: 96a5e6f6-d320-4623-b96e-0a856e3abebb
author: rothja
ms.author: jroth
ms.openlocfilehash: 443b9ea8a67341afdb92f0c384148c8b1b42f752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686266"
---
# <a name="srv_rpcparams-extended-stored-procedure-api"></a><span data-ttu-id="a2811-102">srv_rpcparams (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="a2811-102">srv_rpcparams (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="a2811-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="a2811-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="a2811-104">Retorna o número de parâmetros para o procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="a2811-104">Returns the number of parameters for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2811-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a2811-105">Syntax</span></span>  
  
```  
  
int srv_rpcparams ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a2811-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a2811-106">Arguments</span></span>  
 <span data-ttu-id="a2811-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="a2811-107">*srvproc*</span></span>  
 <span data-ttu-id="a2811-108">É um ponteiro para a estrutura SRV_PROC que é o identificador de uma conexão de cliente específica (neste caso, o identificador que recebeu o procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="a2811-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="a2811-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="a2811-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="a2811-110">Retornos</span><span class="sxs-lookup"><span data-stu-id="a2811-110">Returns</span></span>  
 <span data-ttu-id="a2811-111">O número de parâmetros no procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="a2811-111">The number of parameters in the remote stored procedure.</span></span> <span data-ttu-id="a2811-112">Se não houver nenhum parâmetro no procedimento armazenado remoto ou se não houver nenhum procedimento armazenado remoto atual, -1 será retornado e ocorrerá um erro de informação.</span><span class="sxs-lookup"><span data-stu-id="a2811-112">If there are no parameters in the remote stored procedure or if there is not a current remote stored procedure, -1 is returned and an information error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2811-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="a2811-113">Remarks</span></span>  
 <span data-ttu-id="a2811-114">Esta função retorna o número de parâmetros no procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="a2811-114">This function returns the number of parameters in the current remote stored procedure.</span></span> <span data-ttu-id="a2811-115">Normalmente é chamado do procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="a2811-115">It is usually called from the remote stored procedure.</span></span>  
  
 <span data-ttu-id="a2811-116">Quando uma chamada de procedimento armazenado remoto é feita com parâmetros, os parâmetros podem ser passados pelo nome ou pela posição (sem-nome).</span><span class="sxs-lookup"><span data-stu-id="a2811-116">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="a2811-117">Se a chamada de procedimento armazenado remoto tiver sido feita com alguns parâmetros passados pelo nome e outros pela posição, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="a2811-117">If the remote stored procedure call was made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="a2811-118">Quando esse erro ocorrer, o manipulador de procedimento armazenado remoto será chamado, mas não receberá os parâmetros e **srv_rpcparams** retornará 0.</span><span class="sxs-lookup"><span data-stu-id="a2811-118">When this error occurs, the remote stored procedure handler is called, but it does not receive the parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a2811-119">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="a2811-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="a2811-120">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="a2811-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
