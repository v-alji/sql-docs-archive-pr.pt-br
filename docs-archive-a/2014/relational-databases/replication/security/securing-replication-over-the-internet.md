---
title: Protegendo a replicação pela Internet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- security [SQL Server replication], Internet
- Internet [SQL Server replication], security
ms.assetid: 25b7af05-2721-4b24-9083-fb671e8bf4e0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 47408b2b9559d33da4563c6fc9560d20338ee01d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685049"
---
# <a name="securing-replication-over-the-internet"></a><span data-ttu-id="33a64-102">Securing Replication Over the Internet</span><span class="sxs-lookup"><span data-stu-id="33a64-102">Securing Replication Over the Internet</span></span>
  <span data-ttu-id="33a64-103">A replicação na Internet pode fornecer flexibilidade, principalmente para Assinantes móveis, mas você deve configurar a replicação na Internet de maneira adequada para garantir proteção adequada.</span><span class="sxs-lookup"><span data-stu-id="33a64-103">Replication over the Internet can provide flexibility, particularly for mobile Subscribers, but you must configure Internet replication appropriately to ensure adequate security.</span></span> <span data-ttu-id="33a64-104">A[!INCLUDE[msCoName](../../../includes/msconame-md.md)] recomenda usar uma de duas técnicas para compartilhar informações com segurança na Internet:</span><span class="sxs-lookup"><span data-stu-id="33a64-104">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] recommends using one of two techniques for securely sharing information over the Internet:</span></span>  
  
-   <span data-ttu-id="33a64-105">Rede virtual privada (VPN)</span><span class="sxs-lookup"><span data-stu-id="33a64-105">Virtual private network (VPN)</span></span>  
  
-   <span data-ttu-id="33a64-106">Opção de sincronização da Web para replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="33a64-106">The Web synchronization option for merge replication</span></span>  
  
## <a name="virtual-private-network"></a><span data-ttu-id="33a64-107">Rede Virtual Privada</span><span class="sxs-lookup"><span data-stu-id="33a64-107">Virtual Private Network</span></span>  
 <span data-ttu-id="33a64-108">As redes virtuais privadas fornecem uma abordagem sobreposta simples e segura para replicar dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na Internet.</span><span class="sxs-lookup"><span data-stu-id="33a64-108">Virtual private networks provide a simple and secure layered approach to replicating [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data over the Internet.</span></span> <span data-ttu-id="33a64-109">A conexão VPN pela Internet opera logicamente como um link WAN (Rede de Longa Distância) entre os sites.</span><span class="sxs-lookup"><span data-stu-id="33a64-109">The VPN connection over the Internet logically operates as a Wide Area Network (WAN) link between the sites.</span></span>  
  
 <span data-ttu-id="33a64-110">Isso é obtido permitindo que o usuário faça o encapsulamento pela Internet ou por meio de outra rede pública usando um protocolo como o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] PPTP (Point-to-Point Tunneling Protocol) disponível nos sistemas operacionais [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows NT versão 4.0 ou [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000 ou L2TP (Layer Two Tunneling Protocol) disponível no sistema operacional Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="33a64-110">This is achieved by allowing the user to tunnel through the Internet or another public network using a protocol such as [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Point-to-Point Tunneling Protocol (PPTP) available with the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows NT version 4.0 or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000 operating system, or Layer Two Tunneling Protocol (L2TP) available with the Windows 2000 operating system.</span></span> <span data-ttu-id="33a64-111">Esse processo fornece segurança e recursos semelhantes para aqueles disponíveis em uma rede privada.</span><span class="sxs-lookup"><span data-stu-id="33a64-111">This process provides security and features similar to those available in a private network.</span></span>  
  
 <span data-ttu-id="33a64-112">Para obter mais informações sobre a configuração de uma VPN, consulte a documentação do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="33a64-112">For more information about setting up a VPN, see the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
## <a name="web-synchronization-through-iis"></a><span data-ttu-id="33a64-113">Sincronização da Web por IIS</span><span class="sxs-lookup"><span data-stu-id="33a64-113">Web Synchronization Through IIS</span></span>  
 <span data-ttu-id="33a64-114">A opção de sincronização da web para replicação de mesclagem fornece a capacidade de replicar dados usando o protocolo HTTPS, que pode ser uma abordagem conveniente para replicar dados através de um firewall.</span><span class="sxs-lookup"><span data-stu-id="33a64-114">The web synchronization option for merge replication provides the ability to replicate data using the HTTPS protocol, which can be a convenient approach to replicating data through a firewall.</span></span> <span data-ttu-id="33a64-115">Para obter mais informações, consulte [Configurar sincronização da Web](../configure-web-synchronization.md) e [Arquitetura de segurança para sincronização da Web](security-architecture-for-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="33a64-115">For more information, see [Configure Web Synchronization](../configure-web-synchronization.md) and [Security Architecture for Web Synchronization](security-architecture-for-web-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a64-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="33a64-116">See Also</span></span>  
 <span data-ttu-id="33a64-117">[Replication Security Best Practices](replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="33a64-117">[Replication Security Best Practices](replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="33a64-118">Segurança de Replicação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="33a64-118">SQL Server Replication Security</span></span>](view-and-modify-replication-security-settings.md)  
  
  
