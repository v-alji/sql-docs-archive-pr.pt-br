---
title: MSSQLSERVER_2 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- 2 (Database Engine error)
ms.assetid: 567fb571-7cda-4ce8-a702-cdff2df5d419
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 87d19a24219fda79de2cad4c06af4f1936b37b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581873"
---
# <a name="mssqlserver_2"></a><span data-ttu-id="9cf54-102">MSSQLSERVER_2</span><span class="sxs-lookup"><span data-stu-id="9cf54-102">MSSQLSERVER_2</span></span>
    
## <a name="details"></a><span data-ttu-id="9cf54-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9cf54-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9cf54-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="9cf54-104">Product Name</span></span>|<span data-ttu-id="9cf54-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9cf54-105">SQL Server</span></span>|  
|<span data-ttu-id="9cf54-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="9cf54-106">Event ID</span></span>|<span data-ttu-id="9cf54-107">2</span><span class="sxs-lookup"><span data-stu-id="9cf54-107">2</span></span>|  
|<span data-ttu-id="9cf54-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="9cf54-108">Event Source</span></span>|<span data-ttu-id="9cf54-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9cf54-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9cf54-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9cf54-110">Component</span></span>|<span data-ttu-id="9cf54-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9cf54-111">SQLEngine</span></span>|  
|<span data-ttu-id="9cf54-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="9cf54-112">Symbolic Name</span></span>||  
|<span data-ttu-id="9cf54-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="9cf54-113">Message Text</span></span>|<span data-ttu-id="9cf54-114">Ocorreu um erro ao estabelecer uma conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="9cf54-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="9cf54-115">Ao conectar-se ao SQL Server, essa falha pode ser provocada porque, sob as configurações padrão, o SQL Server não permite conexões remotas.</span><span class="sxs-lookup"><span data-stu-id="9cf54-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="9cf54-116">(provedor: Provedor de Pipes Nomeados, erro: 40 – não foi possível abrir uma conexão com o SQL Server) (Provedor de Dados SqlClient do .Net)</span><span class="sxs-lookup"><span data-stu-id="9cf54-116">(provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9cf54-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="9cf54-117">Explanation</span></span>  
 <span data-ttu-id="9cf54-118">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não respondeu à solicitação do cliente porque o servidor provavelmente não foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="9cf54-118">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] did not respond to the client request because the server is probably not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9cf54-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="9cf54-119">User Action</span></span>  
 <span data-ttu-id="9cf54-120">Verifique se o servidor está iniciado.</span><span class="sxs-lookup"><span data-stu-id="9cf54-120">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf54-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9cf54-121">See Also</span></span>  
 <span data-ttu-id="9cf54-122">[Gerenciar os serviços do Mecanismo de Banco de Dados](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="9cf54-122">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="9cf54-123">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="9cf54-123">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="9cf54-124">[Protocolos de rede e bibliotecas de rede](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="9cf54-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="9cf54-125">[Configuração de rede do cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="9cf54-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="9cf54-126">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="9cf54-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="9cf54-127">Habilitar ou desabilitar um protocolo de rede do servidor</span><span class="sxs-lookup"><span data-stu-id="9cf54-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
