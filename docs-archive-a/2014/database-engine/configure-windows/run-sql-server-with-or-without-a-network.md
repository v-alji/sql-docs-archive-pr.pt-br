---
title: Executar o SQL Server com ou sem uma rede | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- verifying Server service has been started
- net start [SQL Server]
- command prompt [SQL Server], connections
- SQL Server services, networks
- status information [SQL Server], Server service
- running SQL Server
- networking [SQL Server], SQL Server with or without
- services [SQL Server], networks
- starting Server service
- SQL Server, running
ms.assetid: 54eac961-5c7a-4481-982d-f93a64b5c2f4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a80e7e4d42f322bc42d0c67c57e3a1f9bddb87a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574271"
---
# <a name="run-sql-server-with-or-without-a-network"></a><span data-ttu-id="36033-102">Executar o SQL Server com ou sem uma rede</span><span class="sxs-lookup"><span data-stu-id="36033-102">Run SQL Server With or Without a Network</span></span>
  <span data-ttu-id="36033-103">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode ser executado em uma rede ou funcionar sem uma rede.</span><span class="sxs-lookup"><span data-stu-id="36033-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can run on a network, or it can function without a network.</span></span>  
  
## <a name="running-sql-server-on-a-network"></a><span data-ttu-id="36033-104">Executando o SQL Server em uma rede</span><span class="sxs-lookup"><span data-stu-id="36033-104">Running SQL Server on a Network</span></span>  
 <span data-ttu-id="36033-105">Para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se comunicar por meio de uma rede, o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve estar em execução.</span><span class="sxs-lookup"><span data-stu-id="36033-105">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to communicate over a network, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service must be running.</span></span> <span data-ttu-id="36033-106">Por padrão, o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows inicia o serviço interno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automaticamente.</span><span class="sxs-lookup"><span data-stu-id="36033-106">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows automatically starts the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="36033-107">Para descobrir se o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foi iniciado, no prompt de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="36033-107">To find out whether the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has been started, at the command prompt, type the following:</span></span>  
  
 <span data-ttu-id="36033-108">**net start**</span><span class="sxs-lookup"><span data-stu-id="36033-108">**net start**</span></span>  
  
 <span data-ttu-id="36033-109">Se os serviços associados ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiverem sido iniciados, os seguintes serviços serão exibidos na saída de **net start** :</span><span class="sxs-lookup"><span data-stu-id="36033-109">If the services associated with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] have been started, the following services will appear in the **net start** output:</span></span>  
  
-   <span data-ttu-id="36033-110">Analysis Services (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="36033-110">Analysis Services (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="36033-111">SQL Server (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="36033-111">SQL Server (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="36033-112">SQL Server Agent (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="36033-112">SQL Server Agent (MSSQLSERVER)</span></span>  
  
## <a name="running-sql-server-without-a-network"></a><span data-ttu-id="36033-113">Executando o SQL Server sem uma rede</span><span class="sxs-lookup"><span data-stu-id="36033-113">Running SQL Server Without a Network</span></span>  
 <span data-ttu-id="36033-114">Ao executar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sem uma rede, não é preciso iniciar o serviço interno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="36033-114">When running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without a network, you do not need to start the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="36033-115">Como o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o SQL Server Configuration Manager e os comandos **net start** e **net stop** são funcionais até mesmo sem rede, os procedimentos para iniciar e interromper uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são idênticos em uma operação com rede ou autônoma.</span><span class="sxs-lookup"><span data-stu-id="36033-115">Because [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], SQL Server Configuration Manager, and the **net start** and **net stop** commands are functional even without a network, the procedures for starting and stopping an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are identical for a network or stand-alone operation.</span></span>  
  
 <span data-ttu-id="36033-116">Ao se conectar a uma instância de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autônomo de um cliente local, como o **sqlcmd**, você ignora a rede e se conecta diretamente à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando um pipe local.</span><span class="sxs-lookup"><span data-stu-id="36033-116">When connecting to an instance of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a local client such as **sqlcmd**, you bypass the network and connect directly to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a local pipe.</span></span> <span data-ttu-id="36033-117">A diferença entre um pipe local e um pipe de rede é se você está ou não usando uma rede.</span><span class="sxs-lookup"><span data-stu-id="36033-117">The difference between a local pipe and a network pipe is whether you are using a network.</span></span> <span data-ttu-id="36033-118">Os pipes local e de rede estabelecem uma conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o pipe padrão (\\\\.\pipe\sql\query), a menos que sejam dadas outras instruções.</span><span class="sxs-lookup"><span data-stu-id="36033-118">Both local and network pipes establish a connection with an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the standard pipe (\\\\.\pipe\sql\query), unless otherwise directed.</span></span>  
  
 <span data-ttu-id="36033-119">Ao se conectar a uma instância de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] local sem especificar um nome de servidor, você estará usando um pipe local.</span><span class="sxs-lookup"><span data-stu-id="36033-119">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without specifying a server name, you are using a local pipe.</span></span> <span data-ttu-id="36033-120">Ao se conectar a uma instância de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] local e especificar um nome de servidor explicitamente, você estará usando um pipe de rede ou outro mecanismo de IPC (comunicação entre processos) de rede, como IPX/SPX (Internetwork Packet Exchange/Sequenced Packet Exchange) (assumindo que você tenha configurado o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para usar várias redes).</span><span class="sxs-lookup"><span data-stu-id="36033-120">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and specify a server name explicitly, you are using either a network pipe or another network interprocess communication (IPC) mechanism, such as Internetwork Packet Exchange/Sequenced Packet Exchange (IPX/SPX) (assuming you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use multiple networks).</span></span> <span data-ttu-id="36033-121">Como um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autônomo não dá suporte a pipes de rede, você deve omitir o argumento **/** _<Server_name>_ desnecessário ao se conectar à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um cliente.</span><span class="sxs-lookup"><span data-stu-id="36033-121">Because a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support network pipes, you must omit the unnecessary **/**_<Server_name>_ argument when connecting to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client.</span></span> <span data-ttu-id="36033-122">Por exemplo, para se conectar a uma instância autônoma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no **osql**, digite:</span><span class="sxs-lookup"><span data-stu-id="36033-122">For example, to connect to a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from **osql**, type:</span></span>  
  
 <span data-ttu-id="36033-123">**osql /Usa /P** _\<saPassword>_</span><span class="sxs-lookup"><span data-stu-id="36033-123">**osql /Usa /P** _\<saPassword>_</span></span>  
  
  
