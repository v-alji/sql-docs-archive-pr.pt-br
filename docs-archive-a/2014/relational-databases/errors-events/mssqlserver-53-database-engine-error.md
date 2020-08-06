---
title: MSSQLSERVER_53 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "53"
helpviewer_keywords:
- 53 (Database Engine error)
ms.assetid: 1234f5a2-b3d1-425a-b29f-480fa792305f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 85fda292fb956047f51b9c7cd1d229ac0afce6b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574732"
---
# <a name="mssqlserver_53"></a><span data-ttu-id="ab2e3-102">MSSQLSERVER_53</span><span class="sxs-lookup"><span data-stu-id="ab2e3-102">MSSQLSERVER_53</span></span>
    
## <a name="details"></a><span data-ttu-id="ab2e3-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ab2e3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab2e3-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ab2e3-104">Product Name</span></span>|<span data-ttu-id="ab2e3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab2e3-105">SQL Server</span></span>|  
|<span data-ttu-id="ab2e3-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ab2e3-106">Event ID</span></span>|<span data-ttu-id="ab2e3-107">53</span><span class="sxs-lookup"><span data-stu-id="ab2e3-107">53</span></span>|  
|<span data-ttu-id="ab2e3-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ab2e3-108">Event Source</span></span>|<span data-ttu-id="ab2e3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ab2e3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ab2e3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ab2e3-110">Component</span></span>|<span data-ttu-id="ab2e3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ab2e3-111">SQLEngine</span></span>|  
|<span data-ttu-id="ab2e3-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ab2e3-112">Symbolic Name</span></span>||  
|<span data-ttu-id="ab2e3-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ab2e3-113">Message Text</span></span>|<span data-ttu-id="ab2e3-114">Ocorreu um erro ao estabelecer uma conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="ab2e3-115">Ao conectar-se ao SQL Server, essa falha pode ser provocada porque, sob as configurações padrão, o SQL Server não permite conexões remotas.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="ab2e3-116">(provedor: Provedor de Pipes Nomeados, erro: 40 – não foi possível abrir uma conexão com o SQL Server) (Provedor de Dados SqlClient do .Net)</span><span class="sxs-lookup"><span data-stu-id="ab2e3-116">(provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ab2e3-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="ab2e3-117">Explanation</span></span>  
 <span data-ttu-id="ab2e3-118">O cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode se conectar com o servidor.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="ab2e3-119">Esse erro pode ocorrer porque o cliente não pode resolver o nome do servidor ou porque o nome do servidor está incorreto.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-119">This error could occur because either the client cannot resolve the name of the server or the name of the server is incorrect.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ab2e3-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ab2e3-120">User Action</span></span>  
 <span data-ttu-id="ab2e3-121">Verifique se você digitou o nome correto do servidor no cliente e se é possível resolver o nome do servidor no cliente.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-121">Make sure that you have entered the correct server name on the client, and that you can resolve the name of the server from the client.</span></span> <span data-ttu-id="ab2e3-122">Para verificar a resolução de nomes TCP/IP, é possível usar o comando **ping** no sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="ab2e3-122">To check TCP/IP name resolution, you can use the **ping** command in the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab2e3-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ab2e3-123">See Also</span></span>  
 <span data-ttu-id="ab2e3-124">[Protocolos de rede e bibliotecas de rede](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="ab2e3-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="ab2e3-125">[Configuração de rede do cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="ab2e3-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="ab2e3-126">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="ab2e3-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="ab2e3-127">Habilitar ou desabilitar um protocolo de rede do servidor</span><span class="sxs-lookup"><span data-stu-id="ab2e3-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
