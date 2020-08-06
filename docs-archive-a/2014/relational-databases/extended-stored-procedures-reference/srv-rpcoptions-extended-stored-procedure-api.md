---
title: srv_rpcoptions (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcoptions
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcoptions
ms.assetid: dbcce5d1-d5a1-4379-9597-04e43af5923d
author: rothja
ms.author: jroth
ms.openlocfilehash: f5ebe4ab48721002e679ce149293b474a934e348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686270"
---
# <a name="srv_rpcoptions-extended-stored-procedure-api"></a><span data-ttu-id="31fb5-102">srv_rpcoptions (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="31fb5-102">srv_rpcoptions (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="31fb5-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="31fb5-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="31fb5-104">Retorna opções de tempo de execução para o procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="31fb5-104">Returns run-time options for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31fb5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="31fb5-105">Syntax</span></span>  
  
```  
  
DBUSMALLINT srv_rpcoptions ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="31fb5-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="31fb5-106">Arguments</span></span>  
 <span data-ttu-id="31fb5-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="31fb5-107">*srvproc*</span></span>  
 <span data-ttu-id="31fb5-108">É um ponteiro para a estrutura SRV_PROC que é o identificador de uma conexão de cliente específica (neste caso, o identificador que recebeu o procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="31fb5-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="31fb5-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="31fb5-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="31fb5-110">Retornos</span><span class="sxs-lookup"><span data-stu-id="31fb5-110">Returns</span></span>  
 <span data-ttu-id="31fb5-111">Um bitmap que contém os sinalizadores de tempo de execução unidos em um OU lógico para o procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="31fb5-111">A bitmap that contains the run-time flags joined in a logical OR for the current remote stored procedure.</span></span> <span data-ttu-id="31fb5-112">Se não houver um procedimento armazenado remoto atual, será retornado 0 e uma mensagem é gerada.</span><span class="sxs-lookup"><span data-stu-id="31fb5-112">If there is not a current remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31fb5-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="31fb5-113">Remarks</span></span>  
 <span data-ttu-id="31fb5-114">A seguinte tabela descreve cada sinalizador de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="31fb5-114">The following table describes each run-time flag.</span></span>  
  
|<span data-ttu-id="31fb5-115">Sinalizador de tempo de execução</span><span class="sxs-lookup"><span data-stu-id="31fb5-115">Run-time flag</span></span>|<span data-ttu-id="31fb5-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="31fb5-116">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="31fb5-117">SRV_NOMETADATA</span><span class="sxs-lookup"><span data-stu-id="31fb5-117">SRV_NOMETADATA</span></span>|<span data-ttu-id="31fb5-118">O cliente solicitou resultados sem informações de metadados.</span><span class="sxs-lookup"><span data-stu-id="31fb5-118">The client has requested results without metadata information.</span></span> <span data-ttu-id="31fb5-119">Esse sinalizador só é usado quando o cliente está se comunicando com uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31fb5-119">This flag is only used when the client is communicating with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="31fb5-120">Um aplicativo de API de procedimento armazenado estendido não pode omitir informações de metadados.</span><span class="sxs-lookup"><span data-stu-id="31fb5-120">An Extended Stored Procedure API application cannot omit metadata information.</span></span>|  
|<span data-ttu-id="31fb5-121">SRV_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="31fb5-121">SRV_RECOMPILE</span></span>|<span data-ttu-id="31fb5-122">O cliente solicitou a recompilação do procedimento armazenado remoto antes de executá-lo.</span><span class="sxs-lookup"><span data-stu-id="31fb5-122">The client has requested to recompile the remote stored procedure before executing it.</span></span> <span data-ttu-id="31fb5-123">Este sinalizador pode não se aplicar a um aplicativo de API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="31fb5-123">This flag may not apply to an Extended Stored Procedure API application.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="31fb5-124">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="31fb5-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="31fb5-125">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="31fb5-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
