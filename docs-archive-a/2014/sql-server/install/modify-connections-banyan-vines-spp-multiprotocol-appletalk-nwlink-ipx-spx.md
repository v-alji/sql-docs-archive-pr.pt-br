---
title: Modificar conexões que usam protocolos de rede Banyan VINEs (SPP), multiprotocolo, AppleTalk ou NWLink IPX SPX | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], modifying connections
- SPP [SQL Server]
- NWLink IPX/SPX [SQL Server]
- connections [SQL Server]
- AppleTalk [SQL Server]
- Sequenced Packet Protocol [SQL Server]
- Multiprotocol Net-Library [SQL Server]
- Banyan VINES Sequenced Package Protocol [SQL Server]
- IPX/SPX [SQL Server]
- protocols [SQL Server], modifying connections
- RPC [SQL Server]
ms.assetid: 5c5ae453-cc5b-4898-95c7-ad34157b1f60
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 750b9c0b76ab6c3b43908ecb8454f31ac1a25b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684993"
---
# <a name="modify-connections-that-use-banyan-vines-sequenced-packet-protocol-spp-multiprotocol-appletalk-or-nwlink-ipx-spx-network-protocols"></a><span data-ttu-id="188df-102">Modificar conexões que usam protocolo de rede Banyan VINES SPP (Sequenced Packet Protocol), Multiprotocol, AppleTalk ou NWLink IPX/SPX</span><span class="sxs-lookup"><span data-stu-id="188df-102">Modify connections that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX SPX network protocols</span></span>
  <span data-ttu-id="188df-103">O Supervisor de Atualização detectou protocolos de conectividade cliente/servidor para os quais não há suporte no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="188df-103">The Upgrade Advisor has detected client server connectivity protocols that are not supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="188df-104">Os aplicativos cliente que usam protocolo de rede Banyan VINES SPP, Multiprotocol, AppleTalk ou NWLink IPX/SPX devem conectar-se usando um protocolo para o qual há suporte.</span><span class="sxs-lookup"><span data-stu-id="188df-104">Client applications that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol (RPC), AppleTalk, or NWLink IPX/SPX network protocols must connect using a supported protocol.</span></span>  
  
## <a name="component"></a><span data-ttu-id="188df-105">Componente</span><span class="sxs-lookup"><span data-stu-id="188df-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="188df-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="188df-106">Description</span></span>  
 <span data-ttu-id="188df-107">O [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] não oferece suporte aos protocolos de rede Banyan VINES SPP, Multiprotocol, AppleTalk e NWLink IPX/SPX.</span><span class="sxs-lookup"><span data-stu-id="188df-107">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] does not support the Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX/SPX network protocols.</span></span> <span data-ttu-id="188df-108">Os clientes que se conectavam anteriormente usando esses protocolos devem selecionar um protocolo diferente.</span><span class="sxs-lookup"><span data-stu-id="188df-108">Clients previously connecting with these protocols must select a different protocol.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="188df-109">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="188df-109">Corrective Action</span></span>  
 <span data-ttu-id="188df-110">Altere as configurações dos aplicativos cliente para que usem um protocolo para o qual há suporte ao conectar-se com o servidor.</span><span class="sxs-lookup"><span data-stu-id="188df-110">Change the client applications to use a supported protocol when connecting to the server.</span></span> <span data-ttu-id="188df-111">Se você tiver uma instalação de alias que use protocolos sem-suporte, esse alias deve ser modificado para que use protocolos para os quais há suporte.</span><span class="sxs-lookup"><span data-stu-id="188df-111">If you have an alias setup that uses one of the unsupported protocols then the alias must be modified to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="188df-112">Se a cadeia de conexão do aplicativo usa ou carrega especificamente um desses protocolos, especificando NETWORK = DBMSRPCN para RPC, NETWORK = DBMSADSN para AppleTalk ou NETWORK = DBMSVINN para a propriedade Banyan VINEs, ou usando um prefixo explícito, como "SPX:*servidor \ instância*" para o SPX, "BV:*Server*" para Banyan Vines, "ADSP:*Server*" para AppleTalk ou "RPC:*Server*" para multiprotocolo, você deve modificar seu aplicativo para usar um dos protocolos com suporte.</span><span class="sxs-lookup"><span data-stu-id="188df-112">If your application connection string specifically uses or loads one of these protocols, by either specifying NETWORK=DBMSRPCN for RPC, NETWORK=DBMSADSN for Appletalk, or NETWORK=DBMSVINN for Banyan VINES property, or by using an explicit prefix such as "spx:*server\instance*" for SPX, "bv:*server*" for Banyan VINES, "adsp:*server*" for AppleTalk, or "rpc:*server*" for multiprotocol, then you must modify your application to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="188df-113">Para obter mais informações, consulte ‘Escolhendo um protocolo de rede’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="188df-113">For more information, see "Choosing a Network Protocol" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188df-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="188df-114">See Also</span></span>  
 <span data-ttu-id="188df-115">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="188df-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="188df-116">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="188df-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
