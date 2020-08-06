---
title: Protocolos de cliente – propriedades TCP e IP (guia Protocolo) | Microsoft Docs
description: Saiba como especificar as opções de TCP/IP em Microsoft SQL Server Configuration Manager, como o parâmetro Keep Alive e o número da porta padrão.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], client protocols
- client protocols [SQL Server]
ms.assetid: d04f1bce-069c-4a02-b561-c87c3282be36
author: rothja
ms.author: jroth
ms.openlocfilehash: dfcf0348dc863970384a40cc9e773481adeedb35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683873"
---
# <a name="client-protocols---tcp-and-ip-properties-protocol-tab"></a><span data-ttu-id="83287-103">Protocolos de Cliente – Propriedades de TCP e IP (guia Protocolo)</span><span class="sxs-lookup"><span data-stu-id="83287-103">Client Protocols - TCP and IP Properties (Protocol Tab)</span></span>
  <span data-ttu-id="83287-104">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, use a guia **Protocolo** na caixa de diálogo **Propriedades de TCP/IP** para exibir ou especificar as opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="83287-104">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, use the **Protocol** tab on the **TCP/IP Properties** dialog box to view or specify the following options.</span></span> <span data-ttu-id="83287-105">Para se conectar a uma porta diferente, digite o número da porta na caixa **Pipe Padrão** .</span><span class="sxs-lookup"><span data-stu-id="83287-105">To connect to a different port, type the port number in the **Default Port** box.</span></span> <span data-ttu-id="83287-106">Para obter mais informações sobre cadeias de conexão, consulte [Criando uma cadeia de conexão válida usando TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span><span class="sxs-lookup"><span data-stu-id="83287-106">For more information about connection strings, see [Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="83287-107">Opções</span><span class="sxs-lookup"><span data-stu-id="83287-107">Options</span></span>  
 <span data-ttu-id="83287-108">**Pipe Padrão**</span><span class="sxs-lookup"><span data-stu-id="83287-108">**Default Port**</span></span>  
 <span data-ttu-id="83287-109">Especifica a porta que a biblioteca de rede TCP/IP usará para tentar se conectar à instância de destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83287-109">Specifies the port that the TCP/IP Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="83287-110">O valor padrão da porta é 1433.</span><span class="sxs-lookup"><span data-stu-id="83287-110">The default value port is 1433.</span></span>  
  
 <span data-ttu-id="83287-111">Ao conectar a uma instância padrão do [!INCLUDE[ssDE](../../includes/ssde-md.md)], o cliente usa esse valor.</span><span class="sxs-lookup"><span data-stu-id="83287-111">When connecting to a default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client uses this value.</span></span> <span data-ttu-id="83287-112">Se uma instância padrão tiver sido configurada para escutar em uma porta diferente, altere esse valor para esse número de porta.</span><span class="sxs-lookup"><span data-stu-id="83287-112">If a default instance has been configured to listen on a different port, change this value to that port number.</span></span>  
  
 <span data-ttu-id="83287-113">Ao se conectar a uma instância nomeada do [!INCLUDE[ssDE](../../includes/ssde-md.md)], o cliente tentará obter o número da porta no Serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executado no computador servidor.</span><span class="sxs-lookup"><span data-stu-id="83287-113">When connecting to a named instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client will attempt to obtain the port number from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service running on the server computer.</span></span> <span data-ttu-id="83287-114">Se o Serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não estiver sendo executado, o número da porta deverá ser fornecido por meio dessa configuração, ou como parte da cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="83287-114">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service is not running, the port number must be provided through this setting, or as part of the connection string.</span></span>  
  
 <span data-ttu-id="83287-115">**Habilitado**</span><span class="sxs-lookup"><span data-stu-id="83287-115">**Enabled**</span></span>  
 <span data-ttu-id="83287-116">Os valores possíveis são **Sim** e **não**.</span><span class="sxs-lookup"><span data-stu-id="83287-116">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="83287-117">**Keep Alive**</span><span class="sxs-lookup"><span data-stu-id="83287-117">**Keep Alive**</span></span>  
 <span data-ttu-id="83287-118">Este parâmetro (em milissegundos) controla a frequência das tentativas do TCP de verificar se uma conexão ociosa ainda está intacta enviando um pacote **KEEPALIVE** .</span><span class="sxs-lookup"><span data-stu-id="83287-118">This parameter (in milliseconds) controls how often TCP attempts to verify that an idle connection is still intact by sending a **KEEPALIVE** packet.</span></span> <span data-ttu-id="83287-119">O padrão é 30.000 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="83287-119">The default is 30000 milliseconds.</span></span>  
  
 <span data-ttu-id="83287-120">**Intervalo de Atividade**</span><span class="sxs-lookup"><span data-stu-id="83287-120">**Keep Alive Interval**</span></span>  
 <span data-ttu-id="83287-121">Este parâmetro (em milissegundos) determina o intervalo que separa novas transmissões de **KEEPALIVE** até que uma resposta seja recebida.</span><span class="sxs-lookup"><span data-stu-id="83287-121">This parameter (in milliseconds) determines the interval separating **KEEPALIVE** retransmissions until a response is received.</span></span> <span data-ttu-id="83287-122">O padrão é 1.000 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="83287-122">The default is 1000 milliseconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83287-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83287-123">See Also</span></span>  
 <span data-ttu-id="83287-124">[Escolhendo um protocolo de rede](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="83287-124">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 <span data-ttu-id="83287-125">[Novo alias &#40;guia alias&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span><span class="sxs-lookup"><span data-stu-id="83287-125">[New Alias &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span></span>  
 [<span data-ttu-id="83287-126">Propriedades &#60;Alias&#62; &#40;Guia Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="83287-126">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
  
