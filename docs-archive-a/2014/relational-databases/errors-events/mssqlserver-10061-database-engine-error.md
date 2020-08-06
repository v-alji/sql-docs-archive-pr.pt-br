---
title: MSSQLSERVER_10061 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10061"
helpviewer_keywords:
- 10061 (Database Engine error)
ms.assetid: 729602f3-08df-474c-8740-8dea13c1eee3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0c866bd8dce01f65036f1d508a94252a97613424
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682256"
---
# <a name="mssqlserver_10061"></a><span data-ttu-id="e9322-102">MSSQLSERVER_10061</span><span class="sxs-lookup"><span data-stu-id="e9322-102">MSSQLSERVER_10061</span></span>
    
## <a name="details"></a><span data-ttu-id="e9322-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e9322-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e9322-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="e9322-104">Product Name</span></span>|<span data-ttu-id="e9322-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9322-105">SQL Server</span></span>|  
|<span data-ttu-id="e9322-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e9322-106">Event ID</span></span>|<span data-ttu-id="e9322-107">10061</span><span class="sxs-lookup"><span data-stu-id="e9322-107">10061</span></span>|  
|<span data-ttu-id="e9322-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="e9322-108">Event Source</span></span>|<span data-ttu-id="e9322-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e9322-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e9322-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e9322-110">Component</span></span>|<span data-ttu-id="e9322-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e9322-111">SQLEngine</span></span>|  
|<span data-ttu-id="e9322-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="e9322-112">Symbolic Name</span></span>||  
|<span data-ttu-id="e9322-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="e9322-113">Message Text</span></span>|<span data-ttu-id="e9322-114">Ocorreu um erro ao estabelecer uma conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="e9322-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="e9322-115">Ao conectar-se ao SQL Server, essa falha pode ser provocada porque, sob as configurações padrão, o SQL Server não permite conexões remotas.</span><span class="sxs-lookup"><span data-stu-id="e9322-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="e9322-116">(provedor: Provedor TCP, erro: 0 – Nenhuma conexão pôde ser estabelecida porque o computador de destino recusou-a de forma ativa.) (Microsoft SQL Server, Erro: 10061)</span><span class="sxs-lookup"><span data-stu-id="e9322-116">(provider: TCP Provider, error: 0 - No connection could be made because the target machine actively refused it.) (Microsoft SQL Server, Error: 10061)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e9322-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="e9322-117">Explanation</span></span>  
 <span data-ttu-id="e9322-118">O servidor não respondeu à solicitação do cliente.</span><span class="sxs-lookup"><span data-stu-id="e9322-118">The server did not respond to the client request.</span></span> <span data-ttu-id="e9322-119">Esse erro pode ocorrer porque o servidor não está iniciado.</span><span class="sxs-lookup"><span data-stu-id="e9322-119">This error could occur because the server is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e9322-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="e9322-120">User Action</span></span>  
 <span data-ttu-id="e9322-121">Verifique se o servidor está iniciado.</span><span class="sxs-lookup"><span data-stu-id="e9322-121">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9322-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e9322-122">See Also</span></span>  
 <span data-ttu-id="e9322-123">[Gerenciar os serviços do Mecanismo de Banco de Dados](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="e9322-123">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="e9322-124">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="e9322-124">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="e9322-125">[Protocolos de rede e bibliotecas de rede](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="e9322-125">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="e9322-126">[Configuração de rede do cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="e9322-126">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="e9322-127">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="e9322-127">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="e9322-128">Habilitar ou desabilitar um protocolo de rede do servidor</span><span class="sxs-lookup"><span data-stu-id="e9322-128">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
