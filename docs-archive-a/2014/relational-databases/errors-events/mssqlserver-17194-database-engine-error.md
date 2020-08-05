---
title: MSSQLSERVER_17194 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "17194"
helpviewer_keywords:
- 17194 (Database Engine error)
ms.assetid: 0d03eb20-28a7-4ceb-8903-7f9420a620f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3f56a104841c4825bba1f60b3588fadd63555c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573085"
---
# <a name="mssqlserver_17194"></a><span data-ttu-id="d7ca6-102">MSSQLSERVER_17194</span><span class="sxs-lookup"><span data-stu-id="d7ca6-102">MSSQLSERVER_17194</span></span>
    
## <a name="details"></a><span data-ttu-id="d7ca6-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d7ca6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7ca6-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="d7ca6-104">Product Name</span></span>|<span data-ttu-id="d7ca6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d7ca6-105">SQL Server</span></span>|  
|<span data-ttu-id="d7ca6-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="d7ca6-106">Event ID</span></span>|<span data-ttu-id="d7ca6-107">17194</span><span class="sxs-lookup"><span data-stu-id="d7ca6-107">17194</span></span>|  
|<span data-ttu-id="d7ca6-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="d7ca6-108">Event Source</span></span>|<span data-ttu-id="d7ca6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d7ca6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d7ca6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d7ca6-110">Component</span></span>|<span data-ttu-id="d7ca6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d7ca6-111">SQLEngine</span></span>|  
|<span data-ttu-id="d7ca6-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="d7ca6-112">Symbolic Name</span></span>||  
|<span data-ttu-id="d7ca6-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="d7ca6-113">Message Text</span></span>|<span data-ttu-id="d7ca6-114">O servidor não pôde carregar a biblioteca de provedores de SSL necessária para logon. A conexão foi fechada.</span><span class="sxs-lookup"><span data-stu-id="d7ca6-114">The server was unable to load the SSL provider library needed to log in; the connection has been closed.</span></span> <span data-ttu-id="d7ca6-115">O SSL é usado para criptografar a sequência de logon ou todas as comunicações dependendo de como o administrador configurou o servidor.</span><span class="sxs-lookup"><span data-stu-id="d7ca6-115">SSL is used to encrypt either the login sequence or all communications, depending on how the administrator has configured the server.</span></span> <span data-ttu-id="d7ca6-116">Consulte os Manuais Online para obter informações sobre esta mensagem de erro:  0xXXXX.</span><span class="sxs-lookup"><span data-stu-id="d7ca6-116">See Books Online for information on this error message:  0xXXXX.</span></span> <span data-ttu-id="d7ca6-117">[CLIENTE: 11.11.11.11]</span><span class="sxs-lookup"><span data-stu-id="d7ca6-117">[CLIENT: 11.11.11.11]</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d7ca6-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="d7ca6-118">Explanation</span></span>  
 <span data-ttu-id="d7ca6-119">Este erro indica que o cliente fechou a conexão.</span><span class="sxs-lookup"><span data-stu-id="d7ca6-119">This error indicates that the client has closed the connection.</span></span> <span data-ttu-id="d7ca6-120">Este erro pode ocorrer porque o tempo limite da conexão expirou.</span><span class="sxs-lookup"><span data-stu-id="d7ca6-120">This error could occur because the connection time-out has expired.</span></span> <span data-ttu-id="d7ca6-121">A mensagem de erro exibe um valor do sistema operacional que descreve o problema subjacente.</span><span class="sxs-lookup"><span data-stu-id="d7ca6-121">The error message displays a value from the operating system that describes the underlying problem.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d7ca6-122">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="d7ca6-122">User Action</span></span>  
 <span data-ttu-id="d7ca6-123">Se o código de erro da mensagem for 0x2746 (valor decimal 10054), isso significa que a conexão foi redefinida pelo cliente, normalmente devido a um tempo limite. Para resolver o erro, aumente o tempo limite da conexão no cliente ou o programa de chamada.</span><span class="sxs-lookup"><span data-stu-id="d7ca6-123">If the error code in the message is 0x2746 (decimal value 10054), this means that the connection was reset by the client, typically because of a time-out. To resolve the error, increase the connection time-out on the client or calling program.</span></span>  
  
 <span data-ttu-id="d7ca6-124">Para determinar uma solução possível para outros valores da mensagem de erro, use o comando **net helpmsg** do sistema operacional e especifique o valor decimal do código de erro.</span><span class="sxs-lookup"><span data-stu-id="d7ca6-124">To determine a possible solution for other error message values, use the operating system command **net helpmsg** and specify the decimal value of the error code.</span></span>  
  
 <span data-ttu-id="d7ca6-125">Para obter mais informações sobre como se conectar a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Configuração de rede do servidor](../../database-engine/configure-windows/server-network-configuration.md) e [Configuração de rede do cliente](../../database-engine/configure-windows/client-network-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="d7ca6-125">For more information about how to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Server Network Configuration](../../database-engine/configure-windows/server-network-configuration.md) and [Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="d7ca6-126">Somente interno</span><span class="sxs-lookup"><span data-stu-id="d7ca6-126">Internal-Only</span></span>  
  
