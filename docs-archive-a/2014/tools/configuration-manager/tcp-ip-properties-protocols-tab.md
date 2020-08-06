---
title: Propriedades TCP-IP (guia protocolos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], configuration options
ms.assetid: 007638fc-3a24-4460-adbe-545ded5d6f88
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d5bc28faddae9a86a6636b56b907b57a2d8711a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569798"
---
# <a name="tcp---ip-properties-protocols-tab"></a><span data-ttu-id="af37b-102">Propriedades TCP-IP (guia protocolos)</span><span class="sxs-lookup"><span data-stu-id="af37b-102">TCP - IP Properties (Protocols Tab)</span></span>
  <span data-ttu-id="af37b-103">Use a caixa de diálogo **Propriedades do TCP/IP** para configurar as opções do protocolo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="af37b-103">Use the **TCP/IP Properties** dialog box to configure the options for the TCP/IP protocol.</span></span> <span data-ttu-id="af37b-104">Clique em **TCP/IP** no painel esquerdo, para mostrar configurações individuais de endereço IP no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="af37b-104">Click **TCP/IP** in the left pane, to show individual IP address configurations in the details pane.</span></span>  
  
 <span data-ttu-id="af37b-105">O Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve ser reiniciado para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="af37b-105">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted before the changes take effect.</span></span>  
  
## <a name="options"></a><span data-ttu-id="af37b-106">Opções</span><span class="sxs-lookup"><span data-stu-id="af37b-106">Options</span></span>  
 <span data-ttu-id="af37b-107">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="af37b-107">**Enabled**</span></span>  
 <span data-ttu-id="af37b-108">Os valores possíveis são **Sim** e **Não**.</span><span class="sxs-lookup"><span data-stu-id="af37b-108">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="af37b-109">**Keep Alive**</span><span class="sxs-lookup"><span data-stu-id="af37b-109">**Keep Alive**</span></span>  
 <span data-ttu-id="af37b-110">Especifique o intervalo (em milissegundos) no qual os pacotes keep-alive são transmitidos para verificar se o computador remoto de uma conexão ainda está disponível.</span><span class="sxs-lookup"><span data-stu-id="af37b-110">Specify the interval (milliseconds) in which keep-alive packets are transmitted to verify that the computer at the remote end of a connection is still available.</span></span>  
  
 <span data-ttu-id="af37b-111">**Listen All**</span><span class="sxs-lookup"><span data-stu-id="af37b-111">**Listen All**</span></span>  
 <span data-ttu-id="af37b-112">Especifique se o SQL Server escutará em todos os endereços IP associados às placas de rede no computador.</span><span class="sxs-lookup"><span data-stu-id="af37b-112">Specify whether SQL Server will listen on all the IP addresses that are bound to network cards on the computer.</span></span> <span data-ttu-id="af37b-113">Se for definido como **No**, configure cada endereço IP separadamente usando a caixa de diálogo de propriedades de cada endereço IP.</span><span class="sxs-lookup"><span data-stu-id="af37b-113">If set to **No**, configure each IP address separately using the properties dialog box for each IP address.</span></span> <span data-ttu-id="af37b-114">Se for definido como **Yes**, as configurações da caixa de propriedades **IPAll** se aplicarão a todos os endereços IP.</span><span class="sxs-lookup"><span data-stu-id="af37b-114">If set to **Yes**, the settings of the **IPAll** properties box will apply to all IP addresses.</span></span> <span data-ttu-id="af37b-115">O valor padrão é **Yes**.</span><span class="sxs-lookup"><span data-stu-id="af37b-115">Default value is **Yes**.</span></span>  
  
 <span data-ttu-id="af37b-116">**No Delay**</span><span class="sxs-lookup"><span data-stu-id="af37b-116">**No Delay**</span></span>  
 <span data-ttu-id="af37b-117">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não implementa alterações nesta propriedade.</span><span class="sxs-lookup"><span data-stu-id="af37b-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not implement changes to this property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af37b-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af37b-118">See Also</span></span>  
 <span data-ttu-id="af37b-119">[Escolhendo um protocolo de rede](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="af37b-119">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="af37b-120">Criando uma cadeia de conexão válida usando TCP/IP</span><span class="sxs-lookup"><span data-stu-id="af37b-120">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
  
