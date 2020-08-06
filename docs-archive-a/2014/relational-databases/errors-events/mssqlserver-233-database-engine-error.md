---
title: MSSQLSERVER_233 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "233"
helpviewer_keywords:
- 233 (Database Engine error)
ms.assetid: 201665dc-7ac8-4c19-90d3-33354c5caa72
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c51fac7c0af16c520d7cf5538e512912e62cf87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679971"
---
# <a name="mssqlserver_233"></a><span data-ttu-id="790f1-102">MSSQLSERVER_233</span><span class="sxs-lookup"><span data-stu-id="790f1-102">MSSQLSERVER_233</span></span>
    
## <a name="details"></a><span data-ttu-id="790f1-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="790f1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="790f1-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="790f1-104">Product Name</span></span>|<span data-ttu-id="790f1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="790f1-105">SQL Server</span></span>|  
|<span data-ttu-id="790f1-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="790f1-106">Event ID</span></span>|<span data-ttu-id="790f1-107">233</span><span class="sxs-lookup"><span data-stu-id="790f1-107">233</span></span>|  
|<span data-ttu-id="790f1-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="790f1-108">Event Source</span></span>|<span data-ttu-id="790f1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="790f1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="790f1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="790f1-110">Component</span></span>|<span data-ttu-id="790f1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="790f1-111">SQLEngine</span></span>|  
|<span data-ttu-id="790f1-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="790f1-112">Symbolic Name</span></span>||  
|<span data-ttu-id="790f1-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="790f1-113">Message Text</span></span>|<span data-ttu-id="790f1-114">Uma conexão com o servidor foi estabelecida com êxito, mas ocorreu um erro durante o processo de logon.</span><span class="sxs-lookup"><span data-stu-id="790f1-114">A connection was successfully established with the server, but then an error occurred during the login process.</span></span> <span data-ttu-id="790f1-115">(provedor: Provedor de Memória Compartilhada, erro: 0 – Nenhum processo está na outra extremidade do pipe.) (Microsoft SQL Server, Erro: 233)</span><span class="sxs-lookup"><span data-stu-id="790f1-115">(provider: Shared Memory Provider, error: 0 - No process is on the other end of the pipe.) (Microsoft SQL Server, Error: 233)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="790f1-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="790f1-116">Explanation</span></span>  
 <span data-ttu-id="790f1-117">O cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode se conectar com o servidor.</span><span class="sxs-lookup"><span data-stu-id="790f1-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="790f1-118">Esse erro pode ocorrer porque o servidor não está configurado para aceitar conexões remotas.</span><span class="sxs-lookup"><span data-stu-id="790f1-118">This error could occur because the server is not configured to accept remote connections.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="790f1-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="790f1-119">User Action</span></span>  
 <span data-ttu-id="790f1-120">Use a ferramenta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager para permitir que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aceite conexões remotas.</span><span class="sxs-lookup"><span data-stu-id="790f1-120">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790f1-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="790f1-121">See Also</span></span>  
 <span data-ttu-id="790f1-122">[Protocolos de rede e bibliotecas de rede](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="790f1-122">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="790f1-123">[Configuração de rede do cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="790f1-123">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="790f1-124">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="790f1-124">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="790f1-125">Habilitar ou desabilitar um protocolo de rede do servidor</span><span class="sxs-lookup"><span data-stu-id="790f1-125">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
