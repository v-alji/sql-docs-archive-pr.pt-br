---
title: Topologias para sincronização da Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Web synchronization, topologies
- IIS server configuration [SQL Server replication]
ms.assetid: 59444faf-bcb6-4421-a3df-8715753e453b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5e28ca5a222e2286d154c16ef41d3147dc56e25a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574646"
---
# <a name="topologies-for-web-synchronization"></a><span data-ttu-id="89169-102">Topologias para sincronização da Web</span><span class="sxs-lookup"><span data-stu-id="89169-102">Topologies for Web Synchronization</span></span>
  <span data-ttu-id="89169-103">Escolha uma opção entre uma variedade de topologias de replicação de sincronização da Web do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89169-103">You can choose from a variety of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Web synchronization replication topologies.</span></span> <span data-ttu-id="89169-104">Os modos comuns para configurar a sincronização da Web incluem:</span><span class="sxs-lookup"><span data-stu-id="89169-104">Common ways to configure Web synchronization include:</span></span>  
  
-   <span data-ttu-id="89169-105">Servidor único</span><span class="sxs-lookup"><span data-stu-id="89169-105">Single server</span></span>  
  
-   <span data-ttu-id="89169-106">Dois servidores</span><span class="sxs-lookup"><span data-stu-id="89169-106">Two servers</span></span>  
  
-   <span data-ttu-id="89169-107">Vários sistemas de Serviços de Informações da Internet (IIS) da [!INCLUDE[msCoName](../../includes/msconame-md.md)] e republicação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89169-107">Multiple [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) systems and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] republishing</span></span>  
  
 <span data-ttu-id="89169-108">Para obter mais informações sobre como configurar a sincronização da Web, consulte [Configurar sincronização da Web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="89169-108">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="single-server"></a><span data-ttu-id="89169-109">Servidor único</span><span class="sxs-lookup"><span data-stu-id="89169-109">Single Server</span></span>  
 <span data-ttu-id="89169-110">Na topologia mais simples, o IIS, o Editor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o Distribuidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] residem em um único servidor.</span><span class="sxs-lookup"><span data-stu-id="89169-110">In the simplest topology, IIS, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor all reside on a single server.</span></span> <span data-ttu-id="89169-111">Os assinantes sincronizam conectando-se ao IIS no Publicador.</span><span class="sxs-lookup"><span data-stu-id="89169-111">Subscribers synchronize by connecting to IIS on the Publisher.</span></span> <span data-ttu-id="89169-112">O Publicador pode ser localizado atrás de um firewall.</span><span class="sxs-lookup"><span data-stu-id="89169-112">The Publisher can be located behind a firewall.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89169-113">Essa configuração só é recomendada para cenários de intranet.</span><span class="sxs-lookup"><span data-stu-id="89169-113">This configuration is recommended only for intranet scenarios.</span></span> <span data-ttu-id="89169-114">Para demais cenários, é recomendado que o servidor de IIS e o Publicador/Distribuidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estejam em computadores separados.</span><span class="sxs-lookup"><span data-stu-id="89169-114">For other scenarios, it is recommended that the IIS server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher/Distributor be on separate computers.</span></span>  
  
 <span data-ttu-id="89169-115">![Sincronização da Web com um só servidor](media/web-sync02.gif "Sincronização da Web com um só servidor")</span><span class="sxs-lookup"><span data-stu-id="89169-115">![Web synchronization with a single server](media/web-sync02.gif "Web synchronization with a single server")</span></span>  
  
## <a name="two-servers"></a><span data-ttu-id="89169-116">Dois servidores</span><span class="sxs-lookup"><span data-stu-id="89169-116">Two Servers</span></span>  
 <span data-ttu-id="89169-117">Você pode colocar o IIS em um servidor e configurar o Publicador e o Distribuidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em outro servidor.</span><span class="sxs-lookup"><span data-stu-id="89169-117">You can place IIS on one server and configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher and Distributor on another server.</span></span> <span data-ttu-id="89169-118">O servidor que executa o IIS pode ser isolado da Internet por um firewall.</span><span class="sxs-lookup"><span data-stu-id="89169-118">The server running IIS can be isolated from the Internet by a firewall.</span></span> <span data-ttu-id="89169-119">Os assinantes sincronizam conectando-se ao IIS.</span><span class="sxs-lookup"><span data-stu-id="89169-119">Subscribers synchronize by connecting to IIS.</span></span>  
  
 <span data-ttu-id="89169-120">![Sincronização da Web com dois servidores](media/web-sync03.gif "Sincronização da Web com dois servidores")</span><span class="sxs-lookup"><span data-stu-id="89169-120">![Web synchronization with two servers](media/web-sync03.gif "Web synchronization with two servers")</span></span>  
  
## <a name="multiple-iis-systems-and-sql-server-republishing"></a><span data-ttu-id="89169-121">Vários sistemas ISS e republicação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="89169-121">Multiple IIS Systems and SQL Server Republishing</span></span>  
 <span data-ttu-id="89169-122">Se precisar dar suporte a um grande número de Assinantes que sincronizam ao mesmo tempo, você pode particionar o trabalho em vários computadores executando o IIS.</span><span class="sxs-lookup"><span data-stu-id="89169-122">If you need to support very large numbers of Subscribers that synchronize at the same time, you can partition the work across multiple computers running IIS.</span></span>  
  
 <span data-ttu-id="89169-123">![Sincronização da Web com vários servidores IIS](media/web-sync04.gif "Sincronização da Web com vários servidores IIS")</span><span class="sxs-lookup"><span data-stu-id="89169-123">![Web synchronization with multiple IIS servers](media/web-sync04.gif "Web synchronization with multiple IIS servers")</span></span>  
  
 <span data-ttu-id="89169-124">Se um equilíbrio de carga adicional for necessário no computador executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você pode criar uma hierarquia de republicação em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="89169-124">If further load balancing is required on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can create a republishing hierarchy on multiple computers.</span></span> <span data-ttu-id="89169-125">O Publicador de alto nível publica dados aos Assinantes, que por sua vez publicam novamente os dados, equilibrando a carga das solicitações dos Assinantes.</span><span class="sxs-lookup"><span data-stu-id="89169-125">The top-level Publisher publishes data to Subscribers, which in turn republish the data, load balancing requests from the Subscribers.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89169-126">Assinantes só podem sincronizar com um Publicador específico.</span><span class="sxs-lookup"><span data-stu-id="89169-126">Subscribers can only synchronize with a specific Publisher.</span></span> <span data-ttu-id="89169-127">Por exemplo, um Assinante para o republicador A não pode sincronizar com o republicador B quando A não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="89169-127">For example, a Subscriber to republisher A cannot synchronize with republisher B when A is not available.</span></span>  
  
 <span data-ttu-id="89169-128">![Sincronização da Web com republicação](media/web-sync05.gif "Sincronização da Web com republicação")</span><span class="sxs-lookup"><span data-stu-id="89169-128">![Web synchronization with republishing](media/web-sync05.gif "Web synchronization with republishing")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89169-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="89169-129">See Also</span></span>  
 <span data-ttu-id="89169-130">[Configure Web Synchronization](configure-web-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="89169-130">[Configure Web Synchronization](configure-web-synchronization.md) </span></span>  
 [<span data-ttu-id="89169-131">Sincronização da Web para replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="89169-131">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
