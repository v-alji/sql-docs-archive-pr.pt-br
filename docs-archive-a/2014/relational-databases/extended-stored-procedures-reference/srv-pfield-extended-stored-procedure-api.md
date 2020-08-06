---
title: srv_pfield (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfield
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfield
ms.assetid: a61e4c1f-e65b-48ea-a7d1-3e1544af389d
author: rothja
ms.author: jroth
ms.openlocfilehash: 90680d59dbf36ad3f713fd7a09d07553890a8668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685706"
---
# <a name="srv_pfield-extended-stored-procedure-api"></a><span data-ttu-id="aebec-102">srv_pfield (API de procedimento armazenado estendido)</span><span class="sxs-lookup"><span data-stu-id="aebec-102">srv_pfield (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="aebec-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="aebec-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="aebec-104">Retorna informações sobre uma conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aebec-104">Returns information about a database connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aebec-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aebec-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_pfield (  
SRV_PROC *  
srvproc  
,  
int   
field  
,  
int *  
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="aebec-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="aebec-106">Arguments</span></span>  
 <span data-ttu-id="aebec-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="aebec-107">*srvproc*</span></span>  
 <span data-ttu-id="aebec-108">Ponteiro que identifica uma conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aebec-108">Pointer identifying a database connection.</span></span>  
  
 <span data-ttu-id="aebec-109">*campo*</span><span class="sxs-lookup"><span data-stu-id="aebec-109">*field*</span></span>  
 <span data-ttu-id="aebec-110">Especifica dados na conexão que será retornada.</span><span class="sxs-lookup"><span data-stu-id="aebec-110">Specifies data on the connection to return.</span></span>  
  
|<span data-ttu-id="aebec-111">Valor</span><span class="sxs-lookup"><span data-stu-id="aebec-111">Value</span></span>|<span data-ttu-id="aebec-112">Retornos</span><span class="sxs-lookup"><span data-stu-id="aebec-112">Returns</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="aebec-113">SRV_APPLNAME</span><span class="sxs-lookup"><span data-stu-id="aebec-113">SRV_APPLNAME</span></span>|<span data-ttu-id="aebec-114">O nome dó aplicativo fornecido pelo cliente quando estabeleceu a conexão.</span><span class="sxs-lookup"><span data-stu-id="aebec-114">The application name provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="aebec-115">SRV_BCPFLAG</span><span class="sxs-lookup"><span data-stu-id="aebec-115">SRV_BCPFLAG</span></span>|<span data-ttu-id="aebec-116">Um sinalizador que será TRUE se o cliente estiver se preparando para uma operação de cópia em massa; caso contrário, será FALSE.</span><span class="sxs-lookup"><span data-stu-id="aebec-116">A flag that is TRUE if the client is preparing for a bulk copy operation; otherwise, FALSE.</span></span>|  
|<span data-ttu-id="aebec-117">SRV_CLIB</span><span class="sxs-lookup"><span data-stu-id="aebec-117">SRV_CLIB</span></span>|<span data-ttu-id="aebec-118">O nome da biblioteca que permite ao cliente falar com um servidor.</span><span class="sxs-lookup"><span data-stu-id="aebec-118">The name of the library that enables the client to talk to a server.</span></span>|  
|<span data-ttu-id="aebec-119">SRV_CPID</span><span class="sxs-lookup"><span data-stu-id="aebec-119">SRV_CPID</span></span>|<span data-ttu-id="aebec-120">A ID de processo de cliente no computador original de cliente.</span><span class="sxs-lookup"><span data-stu-id="aebec-120">The client process ID on the client source computer.</span></span>|  
|<span data-ttu-id="aebec-121">SRV_HOST</span><span class="sxs-lookup"><span data-stu-id="aebec-121">SRV_HOST</span></span>|<span data-ttu-id="aebec-122">O nome do computador do cliente fornecido pelo cliente quando estabeleceu a conexão.</span><span class="sxs-lookup"><span data-stu-id="aebec-122">The name of the client's machine provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="aebec-123">SRV_LIBVERS</span><span class="sxs-lookup"><span data-stu-id="aebec-123">SRV_LIBVERS</span></span>|<span data-ttu-id="aebec-124">A versão da biblioteca do cliente.</span><span class="sxs-lookup"><span data-stu-id="aebec-124">The version of the client library.</span></span>|  
|<span data-ttu-id="aebec-125">SRV_LSECURE</span><span class="sxs-lookup"><span data-stu-id="aebec-125">SRV_LSECURE</span></span>|<span data-ttu-id="aebec-126">Um sinalizador.</span><span class="sxs-lookup"><span data-stu-id="aebec-126">A flag.</span></span> <span data-ttu-id="aebec-127">TRUE se a conexão usava segurança integrada para fazer logon.</span><span class="sxs-lookup"><span data-stu-id="aebec-127">TRUE if the connection used integrated security to login.</span></span>|  
|<span data-ttu-id="aebec-128">SRV_NETWORK_MODULE</span><span class="sxs-lookup"><span data-stu-id="aebec-128">SRV_NETWORK_MODULE</span></span>|<span data-ttu-id="aebec-129">O nome da DLL de Biblioteca de Rede usado pela conexão.</span><span class="sxs-lookup"><span data-stu-id="aebec-129">The name of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="aebec-130">SRV_NETWORK_VERSION</span><span class="sxs-lookup"><span data-stu-id="aebec-130">SRV_NETWORK_VERSION</span></span>|<span data-ttu-id="aebec-131">A versão da DLL de Biblioteca de Rede usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="aebec-131">The version of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="aebec-132">SRV_NETWORK_CONNECTION</span><span class="sxs-lookup"><span data-stu-id="aebec-132">SRV_NETWORK_CONNECTION</span></span>|<span data-ttu-id="aebec-133">A cadeia de conexão passada para a DLL de Net-Library usada para a conexão *srvproc* atual.</span><span class="sxs-lookup"><span data-stu-id="aebec-133">The connection string passed to the Net-Library DLL used for the current *srvproc* connection.</span></span>|  
|<span data-ttu-id="aebec-134">SRV_PIPEHANDLE</span><span class="sxs-lookup"><span data-stu-id="aebec-134">SRV_PIPEHANDLE</span></span>|<span data-ttu-id="aebec-135">Uma cadeia de caracteres que contém o controle de pipe de um cliente conectado ou NULL se o cliente estiver conectado em uma rede que não usa pipes nomeados.</span><span class="sxs-lookup"><span data-stu-id="aebec-135">A string containing the pipe handle of a connected client, or NULL if the client is connected on a network that does not use named pipes.</span></span> <span data-ttu-id="aebec-136">Para usar esse controle como um controle de pipe válido com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, converta essa cadeia de caracteres em um inteiro.</span><span class="sxs-lookup"><span data-stu-id="aebec-136">To use this handle as a valid pipe handle with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, convert this string to an integer.</span></span>|  
|<span data-ttu-id="aebec-137">SRV_RMTSERVER</span><span class="sxs-lookup"><span data-stu-id="aebec-137">SRV_RMTSERVER</span></span>|<span data-ttu-id="aebec-138">O servidor do qual o processo de cliente fez logon.</span><span class="sxs-lookup"><span data-stu-id="aebec-138">The server from which the client process is logged in.</span></span> <span data-ttu-id="aebec-139">Se o logon for de um cliente, esse valor será uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="aebec-139">If the login is from a client, this value is an empty string.</span></span>|  
|<span data-ttu-id="aebec-140">SRV_ROWSENT</span><span class="sxs-lookup"><span data-stu-id="aebec-140">SRV_ROWSENT</span></span>|<span data-ttu-id="aebec-141">O número de linhas já enviadas por *srvproc* para o conjunto atual de resultados.</span><span class="sxs-lookup"><span data-stu-id="aebec-141">The number of rows already sent by *srvproc* for the current set of results.</span></span>|  
|<span data-ttu-id="aebec-142">SRV_SPID</span><span class="sxs-lookup"><span data-stu-id="aebec-142">SRV_SPID</span></span>|<span data-ttu-id="aebec-143">A ID de thread do servidor do *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="aebec-143">The server thread ID of the *srvproc*.</span></span> <span data-ttu-id="aebec-144">Para obter procedimentos armazenados estendidos, esse valor será igual à coluna **kpid** de **sys.sysprocesses** e pode mudar ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="aebec-144">For extended stored procedures, this value is the same as the **kpid** column of **sys.sysprocesses**, and it can change over time.</span></span>|  
|<span data-ttu-id="aebec-145">SRV_SPROC_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="aebec-145">SRV_SPROC_CODEPAGE</span></span>|<span data-ttu-id="aebec-146">Página de código que o servidor usa para interpretar dados multibyte.</span><span class="sxs-lookup"><span data-stu-id="aebec-146">Codepage that the server uses to interpret multbyte data.</span></span>|  
|<span data-ttu-id="aebec-147">SRV_STATUS</span><span class="sxs-lookup"><span data-stu-id="aebec-147">SRV_STATUS</span></span>|<span data-ttu-id="aebec-148">O status atual de *srvproc*: em execução ou fechado</span><span class="sxs-lookup"><span data-stu-id="aebec-148">The current status of *srvproc*: running or closed</span></span>|  
|<span data-ttu-id="aebec-149">SRV_TYPE</span><span class="sxs-lookup"><span data-stu-id="aebec-149">SRV_TYPE</span></span>|<span data-ttu-id="aebec-150">O tipo de conexão de *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="aebec-150">The connection type of *srvproc*.</span></span> <span data-ttu-id="aebec-151">Se o servidor for retornado, *srvproc* será proveniente de uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aebec-151">If server is returned, *srvproc* is from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aebec-152">Se o cliente for retornado, *srvproc* será proveniente de um cliente ODBC ou DB-Library.</span><span class="sxs-lookup"><span data-stu-id="aebec-152">If client is returned, *srvproc* is from a DB-Library or ODBC client.</span></span>|  
|<span data-ttu-id="aebec-153">SRV_USER</span><span class="sxs-lookup"><span data-stu-id="aebec-153">SRV_USER</span></span>|<span data-ttu-id="aebec-154">O nome do usuário da conexão.</span><span class="sxs-lookup"><span data-stu-id="aebec-154">The user name of the connection.</span></span>|  
|||  
  
 <span data-ttu-id="aebec-155">*Len*</span><span class="sxs-lookup"><span data-stu-id="aebec-155">*len*</span></span>  
 <span data-ttu-id="aebec-156">É um ponteiro para uma variável **int** que contém o tamanho do valor de *field* retornado.</span><span class="sxs-lookup"><span data-stu-id="aebec-156">Is a pointer to an **int** variable that contains the length of the returned *field* value.</span></span> <span data-ttu-id="aebec-157">Se *len* for NULL, o tamanho da cadeia de caracteres não será retornado.</span><span class="sxs-lookup"><span data-stu-id="aebec-157">If *len* is NULL, the length of the string is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="aebec-158">Retornos</span><span class="sxs-lookup"><span data-stu-id="aebec-158">Returns</span></span>  
 <span data-ttu-id="aebec-159">Um ponteiro para uma cadeia de caracteres terminada por caractere nulo que contém o valor atual do campo especificado na estrutura SRV_PROC.</span><span class="sxs-lookup"><span data-stu-id="aebec-159">A pointer to a null-terminated string containing the current value for the specified field in the SRV_PROC structure.</span></span> <span data-ttu-id="aebec-160">Se o campo for vazio, um ponteiro válido para uma cadeia de caracteres vazia será retornado e *len* conterá 0.</span><span class="sxs-lookup"><span data-stu-id="aebec-160">If the field is empty, a valid pointer to an empty string is returned and *len* contains 0.</span></span> <span data-ttu-id="aebec-161">Se o campo for desconhecido, NULL será retornado e *len* conterá o valor -1.</span><span class="sxs-lookup"><span data-stu-id="aebec-161">If the field is unknown, NULL is returned and *len* contains the value -1.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aebec-162">Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="aebec-162">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="aebec-163">Para obter informações sobre análise e teste de segurança, consulte a [ 	Central de Desenvolvedores de Segurança](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="aebec-163">For information about security review and testing, see the [Security Developer Center](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
