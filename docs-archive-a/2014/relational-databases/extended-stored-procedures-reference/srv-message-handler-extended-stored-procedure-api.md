---
title: srv_message_handler (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_message_handler
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_message_handler
ms.assetid: 41bcd057-436f-4fa8-8293-fc8057a30877
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e7b6472ed4fabb6dc2d545eb51a1e026635ce19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571399"
---
# <a name="srv_message_handler-extended-stored-procedure-api"></a><span data-ttu-id="7a3dc-102">srv_message_handler (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="7a3dc-102">srv_message_handler (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="7a3dc-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="7a3dc-104">Chama o manipulador de mensagens instalado da API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-104">Calls the installed Extended Stored Procedure API message handler.</span></span> <span data-ttu-id="7a3dc-105">Essa função geralmente é usada para chamar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de um procedimento armazenado estendido para registrar um erro (definido pelo procedimento armazenado estendido) no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] arquivo de log de erros ou no [!INCLUDE[msCoName](../../includes/msconame-md.md)] log de aplicativos do Windows.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-105">This function is usually used to call [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from an extended stored procedure to log an error (defined by the extended stored procedure) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log file or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a3dc-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7a3dc-106">Syntax</span></span>  
  
```  
  
int srv_message_handler (  
SRV_PROC *  
srvproc  
,  
int  
errornum  
,  
BYTE   
severity  
,  
BYTE  
state  
,  
int  
oserrnum  
,  
char *  
errtext  
,  
int  
errtextlen  
,  
char *  
oserrtext  
,  
int  
oserrtextlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7a3dc-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7a3dc-107">Arguments</span></span>  
 <span data-ttu-id="7a3dc-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="7a3dc-108">*srvproc*</span></span>  
 <span data-ttu-id="7a3dc-109">É um ponteiro para a estrutura SRV_PROC que atua como identificador de uma conexão de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="7a3dc-110">O parâmetro *srvproc* contém informações usadas para gerenciar a comunicação e os dados entre o aplicativo e o cliente.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-110">The *srvproc* parameter contains information that is used to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="7a3dc-111">*errornum*</span><span class="sxs-lookup"><span data-stu-id="7a3dc-111">*errornum*</span></span>  
 <span data-ttu-id="7a3dc-112">É um número de erro definido pelo procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-112">Is an error number defined by the extended stored procedure.</span></span> <span data-ttu-id="7a3dc-113">Esse número deve ser de 50.001 a 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-113">This number must be from 50,001 through 2,147,483,647.</span></span>  
  
 <span data-ttu-id="7a3dc-114">*severity*</span><span class="sxs-lookup"><span data-stu-id="7a3dc-114">*severity*</span></span>  
 <span data-ttu-id="7a3dc-115">É um valor de severidade padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o erro.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-115">Is a standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] severity value for the error.</span></span> <span data-ttu-id="7a3dc-116">Esse número deve ser de 0 por 24.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-116">This number must be from 0 through 24.</span></span>  
  
 <span data-ttu-id="7a3dc-117">*state*</span><span class="sxs-lookup"><span data-stu-id="7a3dc-117">*state*</span></span>  
 <span data-ttu-id="7a3dc-118">É um valor de estado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o erro.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-118">Is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] state value for the error.</span></span>  
  
 <span data-ttu-id="7a3dc-119">*oserrnum*</span><span class="sxs-lookup"><span data-stu-id="7a3dc-119">*oserrnum*</span></span>  
 <span data-ttu-id="7a3dc-120">É o número de erro do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-120">Is the operating-system error number.</span></span> <span data-ttu-id="7a3dc-121">Esse argumento é ignorado.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-121">This argument is ignored.</span></span>  
  
 <span data-ttu-id="7a3dc-122">*errtext*</span><span class="sxs-lookup"><span data-stu-id="7a3dc-122">*errtext*</span></span>  
 <span data-ttu-id="7a3dc-123">É a descrição do erro *errornum* do procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-123">Is the description of the extended stored procedure error *errornum*.</span></span>  
  
 <span data-ttu-id="7a3dc-124">*errtextlen*</span><span class="sxs-lookup"><span data-stu-id="7a3dc-124">*errtextlen*</span></span>  
 <span data-ttu-id="7a3dc-125">É o tamanho da cadeia de caracteres de erro *errtext* do procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-125">Is the length of the extended stored procedure error string *errtext*.</span></span>  
  
 <span data-ttu-id="7a3dc-126">*oserrtext*</span><span class="sxs-lookup"><span data-stu-id="7a3dc-126">*oserrtext*</span></span>  
 <span data-ttu-id="7a3dc-127">É a descrição do erro *oserrnum* do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-127">Is the description of the operating-system error *oserrnum*.</span></span> <span data-ttu-id="7a3dc-128">Esse argumento é ignorado.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-128">This argument is ignored.</span></span>  
  
 <span data-ttu-id="7a3dc-129">*oserrtextlen*</span><span class="sxs-lookup"><span data-stu-id="7a3dc-129">*oserrtextlen*</span></span>  
 <span data-ttu-id="7a3dc-130">É o tamanho da cadeia de caracteres de erro *oserrtext* do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-130">Is the length of the operating-system error string *oserrtext*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="7a3dc-131">Retornos</span><span class="sxs-lookup"><span data-stu-id="7a3dc-131">Returns</span></span>  
 <span data-ttu-id="7a3dc-132">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-132">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a3dc-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="7a3dc-133">Remarks</span></span>  
 <span data-ttu-id="7a3dc-134">A função **srv_message_handler** permite que um procedimento armazenado estendido seja integrado aos recursos de log de erros centralizado e relatório do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a3dc-134">The **srv_message_handler** function enables an extended stored procedure to integrate with the centralized error logging and reporting features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7a3dc-135">Os alertas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem ser estabelecidos para eventos de procedimentos armazenados estendidos e o SQL Server Agent fará o monitoramento das condições desses alertas.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts can be established for events from extended stored procedures, and SQL Server Agent will monitor for these alert conditions.</span></span>  
  
 <span data-ttu-id="7a3dc-136">Se a mensagem de erro for mais longa, ela será truncada para 412 bytes.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-136">If the error message is longer, it is truncated to 412 bytes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7a3dc-137">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-137">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="7a3dc-138">Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="7a3dc-138">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
