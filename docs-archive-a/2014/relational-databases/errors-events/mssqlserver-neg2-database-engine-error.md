---
title: MSSQLSERVER_-2 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- -2 (Database Engine error)
ms.assetid: f37a7b7d-26e1-4b9e-bcb4-57f7805393d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d39b4a11387a60056bba3f87adffcb2653b60f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680960"
---
# <a name="mssqlserver_-2"></a><span data-ttu-id="ee117-102">MSSQLSERVER_-2</span><span class="sxs-lookup"><span data-stu-id="ee117-102">MSSQLSERVER_-2</span></span>
    
## <a name="details"></a><span data-ttu-id="ee117-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ee117-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee117-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ee117-104">Product Name</span></span>|<span data-ttu-id="ee117-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ee117-105">SQL Server</span></span>|  
|<span data-ttu-id="ee117-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ee117-106">Event ID</span></span>|<span data-ttu-id="ee117-107">-2</span><span class="sxs-lookup"><span data-stu-id="ee117-107">-2</span></span>|  
|<span data-ttu-id="ee117-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ee117-108">Event Source</span></span>|<span data-ttu-id="ee117-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ee117-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ee117-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ee117-110">Component</span></span>|<span data-ttu-id="ee117-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ee117-111">SQLEngine</span></span>|  
|<span data-ttu-id="ee117-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ee117-112">Symbolic Name</span></span>||  
|<span data-ttu-id="ee117-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ee117-113">Message Text</span></span>|<span data-ttu-id="ee117-114">Tempo limite esgotado.</span><span class="sxs-lookup"><span data-stu-id="ee117-114">Timeout expired.</span></span>  <span data-ttu-id="ee117-115">O período de tempo limite acabou antes de conclusão da operação ou o servidor não está respondendo.</span><span class="sxs-lookup"><span data-stu-id="ee117-115">The timeout period elapsed prior to completion of the operation or the server is not responding.</span></span> <span data-ttu-id="ee117-116">(Microsoft SQL Server, Erro: -2)</span><span class="sxs-lookup"><span data-stu-id="ee117-116">(Microsoft SQL Server, Error: -2)</span></span>|   
  
## <a name="explanation"></a><span data-ttu-id="ee117-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="ee117-117">Explanation</span></span>  
 <span data-ttu-id="ee117-118">O cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode se conectar com o servidor.</span><span class="sxs-lookup"><span data-stu-id="ee117-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="ee117-119">Este erro pode ter ocorrido porque o firewall no servidor recusou a conexão.</span><span class="sxs-lookup"><span data-stu-id="ee117-119">This error could occur because the firewall on the server has refused the connection.</span></span> 
  
## <a name="user-action"></a><span data-ttu-id="ee117-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ee117-120">User Action</span></span>  
 <span data-ttu-id="ee117-121">Verifique se você configurou o firewall na instância do servidor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para aceitar conexões.</span><span class="sxs-lookup"><span data-stu-id="ee117-121">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee117-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ee117-122">See Also</span></span>  
 <span data-ttu-id="ee117-123">[Configurar o Firewall do Windows para permitir acesso SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span><span class="sxs-lookup"><span data-stu-id="ee117-123">[Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span></span>  
 <span data-ttu-id="ee117-124">[Configurar um firewall do Windows para acesso Mecanismo de Banco de Dados](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="ee117-124">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="ee117-125">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="ee117-125">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="ee117-126">[Protocolos de rede e bibliotecas de rede](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="ee117-126">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="ee117-127">[Configuração de rede do cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="ee117-127">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="ee117-128">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="ee117-128">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="ee117-129">Habilitar ou desabilitar um protocolo de rede do servidor</span><span class="sxs-lookup"><span data-stu-id="ee117-129">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
