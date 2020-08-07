---
title: Conectar-se ao SQL Server por meio de um servidor proxy (SQL Server Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Remote WinSock
- RWS
- LATs
- proxy servers [SQL Server]
- connections [SQL Server], proxy server
- Microsoft Proxy Server [SQL Server]
- local address tables [SQL Server]
ms.assetid: 39714de0-2a1f-4179-9091-5c3fa4612545
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: de22ad6043c509f08471a6bea40c0efa18d76842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575330"
---
# <a name="connect-to-sql-server-through-a-proxy-server-sql-server-configuration-manager"></a><span data-ttu-id="a2d60-102">Conectar-se ao SQL Server com um servidor proxy (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="a2d60-102">Connect to SQL Server Through a Proxy Server (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="a2d60-103">Este tópico descreve como conectar-se ao SQL Server por meio de um servidor proxy no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a2d60-103">This topic describes how to connect to SQL Server through a proxy server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="a2d60-104">Para escutar Remote WinSock (RWS) remotamente, defina a tabela de endereço local (LAT) para o servidor proxy, para que o endereço do nó de escuta fique fora do intervalo de entradas de LAT.</span><span class="sxs-lookup"><span data-stu-id="a2d60-104">To listen remotely by way of Remote WinSock (RWS), define the local address table (LAT) for the proxy server so that the listening node address is outside the range of LAT entries.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a2d60-105">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a2d60-105">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-enable-connections-to-sql-server-through-microsoft-proxy-server"></a><span data-ttu-id="a2d60-106">Habilitar conexões com o SQL Server usando o Microsoft Proxy Server</span><span class="sxs-lookup"><span data-stu-id="a2d60-106">To enable connections to SQL Server through Microsoft Proxy Server</span></span>  
  
1.  <span data-ttu-id="a2d60-107">Siga as etapas em [Configurar um servidor para escutar em uma porta TCP específica &#40;SQL Server Configuration Manager&#41;](configure-a-server-to-listen-on-a-specific-tcp-port.md) para determinar quais portas TCP/IP são usadas pelo [!INCLUDE[ssDE](../../includes/ssde-md.md)] ou para configurar o [!INCLUDE[ssDE](../../includes/ssde-md.md)] para usar uma porta desejada.</span><span class="sxs-lookup"><span data-stu-id="a2d60-107">Follow the steps in [Configure a Server to Listen on a Specific TCP Port &#40;SQL Server Configuration Manager&#41;](configure-a-server-to-listen-on-a-specific-tcp-port.md) to determine which TCP/IP ports are used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to use a desired port.</span></span>  
  
2.  <span data-ttu-id="a2d60-108">No servidor proxy, defina a tabela de endereço local (LAT) para o servidor proxy, para que o endereço do nó de escuta fique fora do intervalo de entradas de LAT.</span><span class="sxs-lookup"><span data-stu-id="a2d60-108">In your proxy server define the local address table (LAT) for the proxy server so that the listening node address is outside the range of LAT entries.</span></span> <span data-ttu-id="a2d60-109">Para obter mais informações, consulte a documentação do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="a2d60-109">For more information, see your proxy server documentation.</span></span>  
  
  
