---
title: MSSQLSERVER_10060 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10060"
helpviewer_keywords:
- 10060 (Database Engine error)
ms.assetid: 28c21277-cad8-406c-a955-07933a56982a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d634cfb06381fb916ef2e421e0677e76edb9ae02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684238"
---
# <a name="mssqlserver_10060"></a><span data-ttu-id="0ece1-102">MSSQLSERVER_10060</span><span class="sxs-lookup"><span data-stu-id="0ece1-102">MSSQLSERVER_10060</span></span>
    
## <a name="details"></a><span data-ttu-id="0ece1-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0ece1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ece1-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="0ece1-104">Product Name</span></span>|<span data-ttu-id="0ece1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0ece1-105">SQL Server</span></span>|  
|<span data-ttu-id="0ece1-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="0ece1-106">Event ID</span></span>|<span data-ttu-id="0ece1-107">10060</span><span class="sxs-lookup"><span data-stu-id="0ece1-107">10060</span></span>|  
|<span data-ttu-id="0ece1-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="0ece1-108">Event Source</span></span>|<span data-ttu-id="0ece1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0ece1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0ece1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0ece1-110">Component</span></span>|<span data-ttu-id="0ece1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0ece1-111">SQLEngine</span></span>|  
|<span data-ttu-id="0ece1-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="0ece1-112">Symbolic Name</span></span>||  
|<span data-ttu-id="0ece1-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="0ece1-113">Message Text</span></span>|<span data-ttu-id="0ece1-114">Ocorreu um erro ao estabelecer uma conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="0ece1-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="0ece1-115">Ao conectar-se ao SQL Server, essa falha pode ser provocada porque, sob as configurações padrão, o SQL Server não permite conexões remotas.</span><span class="sxs-lookup"><span data-stu-id="0ece1-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="0ece1-116">(provedor: Provedor TCP, erro: 0 – Falha em uma tentativa de conexão porque a parte conectada não respondeu corretamente após um período ou houve falha na conexão estabelecida devido a uma falha na resposta do host conectado.) (Microsoft SQL Server, Erro: 10060)</span><span class="sxs-lookup"><span data-stu-id="0ece1-116">(provider: TCP Provider, error: 0 - A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.) (Microsoft SQL Server, Error: 10060)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0ece1-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="0ece1-117">Explanation</span></span>  
 <span data-ttu-id="0ece1-118">O cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode se conectar com o servidor.</span><span class="sxs-lookup"><span data-stu-id="0ece1-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="0ece1-119">Esse erro pode ocorrer porque o firewall no servidor recusou a conexão ou o servidor não está configurado para aceitar conexões remotas.</span><span class="sxs-lookup"><span data-stu-id="0ece1-119">This error could occur because either the firewall on the server has refused the connection or the server is not configured to accept remote connections.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ece1-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="0ece1-120">User Action</span></span>  
 <span data-ttu-id="0ece1-121">Para resolver esse erro, tente uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="0ece1-121">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="0ece1-122">Certifique-se de que você configurou o firewall no computador para permitir que essa instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aceite conexões.</span><span class="sxs-lookup"><span data-stu-id="0ece1-122">Make sure that you have configured the firewall on the computer to allow this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
-   <span data-ttu-id="0ece1-123">Use a ferramenta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager para permitir que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aceite conexões remotas.</span><span class="sxs-lookup"><span data-stu-id="0ece1-123">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ece1-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ece1-124">See Also</span></span>  
 <span data-ttu-id="0ece1-125">[Configurar um firewall do Windows para acesso Mecanismo de Banco de Dados](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="0ece1-125">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="0ece1-126">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="0ece1-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="0ece1-127">[Protocolos de rede e bibliotecas de rede](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="0ece1-127">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="0ece1-128">[Configuração de rede do cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0ece1-128">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="0ece1-129">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="0ece1-129">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="0ece1-130">Habilitar ou desabilitar um protocolo de rede do servidor</span><span class="sxs-lookup"><span data-stu-id="0ece1-130">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
