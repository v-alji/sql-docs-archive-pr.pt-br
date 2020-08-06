---
title: MSSQLSERVER_-1 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "-1"
helpviewer_keywords:
- -1 (Database Engine error)
ms.assetid: bad25b91-eaed-46c0-a5b7-71117a32304c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 880212b1d2e9572bbb31535a5ba68b445c7e6f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682259"
---
# <a name="mssqlserver_-1"></a><span data-ttu-id="c29c9-102">MSSQLSERVER_-1</span><span class="sxs-lookup"><span data-stu-id="c29c9-102">MSSQLSERVER_-1</span></span>
    
## <a name="details"></a><span data-ttu-id="c29c9-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c29c9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c29c9-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="c29c9-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="c29c9-105">ID do evento</span><span class="sxs-lookup"><span data-stu-id="c29c9-105">Event ID</span></span>|<span data-ttu-id="c29c9-106">-1</span><span class="sxs-lookup"><span data-stu-id="c29c9-106">-1</span></span>|  
|<span data-ttu-id="c29c9-107">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="c29c9-107">Event Source</span></span>|<span data-ttu-id="c29c9-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c29c9-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c29c9-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c29c9-109">Component</span></span>|<span data-ttu-id="c29c9-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c29c9-110">SQLEngine</span></span>|  
|<span data-ttu-id="c29c9-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="c29c9-111">Symbolic Name</span></span>||  
|<span data-ttu-id="c29c9-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="c29c9-112">Message Text</span></span>|<span data-ttu-id="c29c9-113">Ocorreu um erro ao estabelecer uma conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="c29c9-113">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="c29c9-114">Ao estabelecer conexão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], essa falha pode ser causada pelo fato de que as configurações padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não permitem conexões remotas.</span><span class="sxs-lookup"><span data-stu-id="c29c9-114">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this failure may be caused by the fact that under the default settings [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow remote connections.</span></span> <span data-ttu-id="c29c9-115">(provedor: adaptadores de rede do SQL, erro: 28 – O servidor não é compatível com o protocolo solicitado) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], erro: -1)</span><span class="sxs-lookup"><span data-stu-id="c29c9-115">(provider: SQL Network Interfaces, error: 28 - Server doesn't support requested protocol) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Error: -1)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c29c9-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="c29c9-116">Explanation</span></span>  
 <span data-ttu-id="c29c9-117">O cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não pode se conectar com o servidor.</span><span class="sxs-lookup"><span data-stu-id="c29c9-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="c29c9-118">Esse erro pode ser causado por um dos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="c29c9-118">This error could be caused by one of the following reasons:</span></span>  
  
-   <span data-ttu-id="c29c9-119">Um nome de instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especificado é inválido.</span><span class="sxs-lookup"><span data-stu-id="c29c9-119">A specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name is not valid.</span></span>  
  
-   <span data-ttu-id="c29c9-120">O TCP ou protocolos de pipes nomeados não estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="c29c9-120">The TCP, or named pipes protocols are not enabled.</span></span>  
  
-   <span data-ttu-id="c29c9-121">O firewall no servidor recusou a conexão.</span><span class="sxs-lookup"><span data-stu-id="c29c9-121">The firewall on the server has refused the connection.</span></span>  
  
-   <span data-ttu-id="c29c9-122">O serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (sqlbrowser) não foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="c29c9-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service (sqlbrowser) is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c29c9-123">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="c29c9-123">User Action</span></span>  
 <span data-ttu-id="c29c9-124">Para resolver esse erro, tente uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c29c9-124">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="c29c9-125">Verifique a ortografia do nome de instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que é especificado na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="c29c9-125">Check the spelling of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name that is specified in the connection string.</span></span>  
  
-   <span data-ttu-id="c29c9-126">Use a ferramenta Configuration Manager do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para permitir que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aceite conexões remotas pelo protocolo TCP ou de pipes nomeados.</span><span class="sxs-lookup"><span data-stu-id="c29c9-126">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections over the TCP or named pipes protocols.</span></span>  
  
-   <span data-ttu-id="c29c9-127">Verifique se você configurou o firewall na instância de servidor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para abrir portas para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e a porta do Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (UDP 1434).</span><span class="sxs-lookup"><span data-stu-id="c29c9-127">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to open ports for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser port (UDP 1434).</span></span>  
  
-   <span data-ttu-id="c29c9-128">Certifique-se de que o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tenha sido iniciado no servidor.</span><span class="sxs-lookup"><span data-stu-id="c29c9-128">Make sure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is started on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c29c9-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c29c9-129">See Also</span></span>  
 <span data-ttu-id="c29c9-130">[Configurar um firewall do Windows para acesso Mecanismo de Banco de Dados](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="c29c9-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="c29c9-131">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="c29c9-131">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="c29c9-132">[Protocolos de rede e bibliotecas de rede](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="c29c9-132">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="c29c9-133">[Configuração de rede do cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="c29c9-133">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="c29c9-134">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="c29c9-134">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="c29c9-135">Habilitar ou desabilitar um protocolo de rede do servidor</span><span class="sxs-lookup"><span data-stu-id="c29c9-135">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
