---
title: srv_rpcowner (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcowner
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcowner
ms.assetid: e81a60e6-14ea-47bc-a11c-3d7635344447
author: rothja
ms.author: jroth
ms.openlocfilehash: f903870d0ee01256addb1557eb7e9123853b39e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686269"
---
# <a name="srv_rpcowner-extended-stored-procedure-api"></a><span data-ttu-id="4f842-102">srv_rpcowner (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="4f842-102">srv_rpcowner (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="4f842-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="4f842-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="4f842-104">Retorna o componente proprietário de procedimento para o procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="4f842-104">Returns the owner component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f842-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4f842-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcowner (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="4f842-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4f842-106">Arguments</span></span>  
 <span data-ttu-id="4f842-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="4f842-107">*srvproc*</span></span>  
 <span data-ttu-id="4f842-108">É um ponteiro para a estrutura SRV_PROC que é o identificador de uma conexão de cliente específica (neste caso, o identificador que recebeu o procedimento armazenado remoto).</span><span class="sxs-lookup"><span data-stu-id="4f842-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="4f842-109">A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="4f842-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="4f842-110">*Len*</span><span class="sxs-lookup"><span data-stu-id="4f842-110">*len*</span></span>  
 <span data-ttu-id="4f842-111">É um ponteiro para uma variável inteira que recebe o comprimento do nome do proprietário.</span><span class="sxs-lookup"><span data-stu-id="4f842-111">Is a pointer to an integer variable that receives the length of the owner name.</span></span> <span data-ttu-id="4f842-112">O parâmetro *len* pode ser NULL, caso em que o tamanho do componente do proprietário não é retornado.</span><span class="sxs-lookup"><span data-stu-id="4f842-112">The parameter *len* can be NULL, in which case the length of the owner component is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="4f842-113">Retornos</span><span class="sxs-lookup"><span data-stu-id="4f842-113">Returns</span></span>  
 <span data-ttu-id="4f842-114">Um ponteiro DBCHAR ponteiro para o componente do proprietário com terminação nula para o procedimento armazenado remoto atual.</span><span class="sxs-lookup"><span data-stu-id="4f842-114">A DBCHAR pointer to the null-terminated owner component for the current remote stored procedure.</span></span> <span data-ttu-id="4f842-115">Se não houver um procedimento armazenado remoto atual, NULL será retornado e *len* será definido como -1.</span><span class="sxs-lookup"><span data-stu-id="4f842-115">If there is no current remote stored procedure, NULL is returned and *len* is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f842-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="4f842-116">Remarks</span></span>  
 <span data-ttu-id="4f842-117">Essa função retorna apenas o componente proprietário do procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="4f842-117">This function returns only the owner component of the remote stored procedure.</span></span> <span data-ttu-id="4f842-118">Ela não inclui os especificadores opcionais para nome, nome de procedimento armazenado remoto e número de procedimento armazenado remoto.</span><span class="sxs-lookup"><span data-stu-id="4f842-118">It does not include the optional specifiers for name, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4f842-119">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="4f842-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="4f842-120">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="4f842-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
