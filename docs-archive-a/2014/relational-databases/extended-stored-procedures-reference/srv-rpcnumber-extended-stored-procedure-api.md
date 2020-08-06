---
title: srv_rpcnumber (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcnumber
ms.assetid: 3094085e-fe9e-423d-bf87-7852352c2d26
author: rothja
ms.author: jroth
ms.openlocfilehash: 25f30f8288125cf64d6b10a867d6af03c0f8ee91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685703"
---
# <a name="srv_rpcnumber-extended-stored-procedure-api"></a><span data-ttu-id="2d89e-102">srv_rpcnumber (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="2d89e-102">srv_rpcnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="2d89e-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="2d89e-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="2d89e-104">Retorna o componente de número da chamada do procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="2d89e-104">Returns the number component for the current remote stored procedure call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d89e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2d89e-105">Syntax</span></span>  
  
```  
  
int srv_rpcnumber ( SRV_PROC *  
srvproc   
)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2d89e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2d89e-106">Arguments</span></span>  
 <span data-ttu-id="2d89e-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="2d89e-107">*srvproc*</span></span>  
 <span data-ttu-id="2d89e-108">É um ponteiro para a estrutura SRV_PROC que é o identificador de uma conexão de cliente específica (neste caso, o identificador que recebeu o procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="2d89e-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="2d89e-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="2d89e-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="2d89e-110">Retornos</span><span class="sxs-lookup"><span data-stu-id="2d89e-110">Returns</span></span>  
 <span data-ttu-id="2d89e-111">O componente de número do procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="2d89e-111">The number component for the current remote stored procedure.</span></span> <span data-ttu-id="2d89e-112">Se o cliente não usar um componente de número ao executar o procedimento armazenado remoto ou se não houver procedimento armazenado remoto atual, ele retornará - 1.</span><span class="sxs-lookup"><span data-stu-id="2d89e-112">If the client does not use a number component when running the remote stored procedure or if there is no current remote stored procedure, it returns - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d89e-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="2d89e-113">Remarks</span></span>  
 <span data-ttu-id="2d89e-114">Esta função retorna apenas o componente de número do procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="2d89e-114">This function returns only the number component of the remote stored procedure.</span></span> <span data-ttu-id="2d89e-115">Ela não inclui os especificadores opcionais para proprietário, nome do procedimento armazenado remoto e nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2d89e-115">It does not include the optional specifiers for owner, remote stored procedure name, and database name.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2d89e-116">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="2d89e-116">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="2d89e-117">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="2d89e-117">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
