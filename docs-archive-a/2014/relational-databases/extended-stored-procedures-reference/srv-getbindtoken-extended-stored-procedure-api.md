---
title: srv_getbindtoken (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_getbindtoken
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_getbindtoken
ms.assetid: c947d011-08ac-4fb8-b925-3da6e0999277
author: rothja
ms.author: jroth
ms.openlocfilehash: d42f95c8a7df87f20ebaa30501b96b5f2a00815a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583056"
---
# <a name="srv_getbindtoken-extended-stored-procedure-api"></a><span data-ttu-id="584f3-102">srv_getbindtoken (API de Procedimento Armazenado Estendido)</span><span class="sxs-lookup"><span data-stu-id="584f3-102">srv_getbindtoken (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="584f3-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="584f3-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="584f3-104">Obtém um token de associação da transação na sessão de cliente atual que invoca o procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="584f3-104">Obtains a bind token of the transaction in the current client session that invokes the extended stored procedure.</span></span>  
  
 <span data-ttu-id="584f3-105">O procedimento armazenado estendido pode então usar **sp_bindsession** para associar qualquer sessão nova criada por ele no mesmo servidor à transação existente, de modo que a nova sessão possa compartilhar o mesmo espaço para bloqueio de transação com a sessão de cliente que invocou o procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="584f3-105">The extended stored procedure can then use **sp_bindsession** to bind any new session it creates against the same server to the existing transaction so that the new session can share the same transaction lock space with the client session that invoked the extended stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="584f3-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="584f3-106">Syntax</span></span>  
  
```  
  
int srv_getbindtoken (  
SRV_PROC*  
srvproc  
,  
char*  
bindtoken  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="584f3-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="584f3-107">Arguments</span></span>  
 <span data-ttu-id="584f3-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="584f3-108">*srvproc*</span></span>  
 <span data-ttu-id="584f3-109">É um ponteiro para a estrutura SRV_PROC que atua como identificador de uma conexão de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="584f3-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="584f3-110">A estrutura contém todas as informações que a biblioteca de APIs de Procedimento Armazenado Estendido usa para gerenciar as comunicações e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="584f3-110">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="584f3-111">*bindtoken*</span><span class="sxs-lookup"><span data-stu-id="584f3-111">*bindtoken*</span></span>  
 <span data-ttu-id="584f3-112">É um ponteiro para um buffer em que o token de associação será copiado.</span><span class="sxs-lookup"><span data-stu-id="584f3-112">Is a pointer to a buffer where the bind token will be copied.</span></span> <span data-ttu-id="584f3-113">O token de associação é representado como uma cadeia de caracteres terminada por caractere nulo.</span><span class="sxs-lookup"><span data-stu-id="584f3-113">The bind token is represented as a null-terminated string.</span></span> <span data-ttu-id="584f3-114">O buffer que você especifica deve ter pelo menos 255 bytes.</span><span class="sxs-lookup"><span data-stu-id="584f3-114">The buffer you specify should be at least 255 bytes in length.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="584f3-115">Retornos</span><span class="sxs-lookup"><span data-stu-id="584f3-115">Returns</span></span>  
 <span data-ttu-id="584f3-116">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="584f3-116">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="584f3-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="584f3-117">Remarks</span></span>  
  
### <a name="to-bind-an-extended-stored-procedure-session-to-the-client-session-that-called-it-so-they-share-the-same-transaction-lock-space"></a><span data-ttu-id="584f3-118">Para associar uma sessão de procedimento armazenado estendido à sessão de cliente que a chamou para que compartilhem o mesmo espaço para bloqueio de transação</span><span class="sxs-lookup"><span data-stu-id="584f3-118">To bind an extended stored procedure session to the client session that called it so they share the same transaction lock space</span></span>  
  
1.  <span data-ttu-id="584f3-119">O procedimento armazenado estendido chama **svr_getbindtoken** para obter o token de associação da transação atual na sessão.</span><span class="sxs-lookup"><span data-stu-id="584f3-119">The extended stored procedure calls **svr_getbindtoken** to get the bind token for the current transaction in the session.</span></span> <span data-ttu-id="584f3-120">O token é retornado no parâmetro *bindtoken* especificado.</span><span class="sxs-lookup"><span data-stu-id="584f3-120">The token is returned in the given *bindtoken* parameter.</span></span>  
  
2.  <span data-ttu-id="584f3-121">O procedimento armazenado estendido abre sessão(ões) nova(s) com relação ao mesmo servidor.</span><span class="sxs-lookup"><span data-stu-id="584f3-121">The extended stored procedure opens new session(s) against the same server.</span></span> <span data-ttu-id="584f3-122">Nessa sessão, o procedimento armazenado estendido usa o token de associação com **sp_bindsession** para associar a nova sessão à mesma transação.</span><span class="sxs-lookup"><span data-stu-id="584f3-122">Inside that session, the extended stored procedure uses the bind token with **sp_bindsession** to bind the new session to the same transaction.</span></span> <span data-ttu-id="584f3-123">O procedimento armazenado estendido pode criar várias sessões e associar todas as sessões à mesma transação.</span><span class="sxs-lookup"><span data-stu-id="584f3-123">The extended stored procedure can create multiple sessions and bind all the sessions to the same transaction.</span></span>  
  
3.  <span data-ttu-id="584f3-124">Uma sessão associada é desassociada quando o procedimento armazenado externo é retornado ou quando **sp_bindsession** é chamado com uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="584f3-124">A bound session is unbound when the external stored procedure returns or when **sp_bindsession** is called with an empty string.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="584f3-125">Somente uma sessão associada por vez pode ter acesso a uma conexão compartilhada.</span><span class="sxs-lookup"><span data-stu-id="584f3-125">Only one bound session at a time can have access to a shared connection.</span></span> <span data-ttu-id="584f3-126">Se uma sessão no momento estiver executando uma instrução no servidor ou tiver resultados pendentes no servidor, nenhuma outra sessão que compartilha a mesma conexão associada poderá obter acesso ao servidor enquanto a sessão atual não tiver concluído a execução da instrução atual.</span><span class="sxs-lookup"><span data-stu-id="584f3-126">If one session is currently executing a statement at the server or has results pending from the server, no other sessions sharing the same bound connection can gain access to the server until the current session has finished executing the current statement.</span></span> <span data-ttu-id="584f3-127">Se uma sessão tentar obter acesso à conexão enquanto o servidor está ocupado, será retornado um erro para a sessão conflitante indicando que a conexão está sendo usada e que a sessão deve tentar novamente mais tarde.</span><span class="sxs-lookup"><span data-stu-id="584f3-127">If a session attempts to gain access to the connection while the server is busy, an error is returned to the conflicting session indicating the connection is in use and the session should retry later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="584f3-128">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="584f3-128">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="584f3-129">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="584f3-129">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="584f3-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="584f3-130">See Also</span></span>  
 <span data-ttu-id="584f3-131">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="584f3-131">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span></span>  
 [<span data-ttu-id="584f3-132">sp_getbindtoken &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="584f3-132">sp_getbindtoken &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql)  
  
  
