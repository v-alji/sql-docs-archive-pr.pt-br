---
title: Propriedade MultiIpConfigurationSupport (classe ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- MultiIpConfigurationSupport Property (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- MultiIpConfigurationSupport property
ms.assetid: 442c6133-4038-42db-a67d-2631285ac76b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 80401a607c9155451a869082162affcca401ebca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568373"
---
# <a name="multiipconfigurationsupport-property-servernetworkprotocol-class"></a><span data-ttu-id="c2596-102">Propriedade MultiIpConfigurationSupport (classe ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="c2596-102">MultiIpConfigurationSupport Property (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="c2596-103">Obtém uma propriedade booliana que especifica se vários endereços IP têm suporte de um protocolo de rede do servidor.</span><span class="sxs-lookup"><span data-stu-id="c2596-103">Gets the Boolean property that specifies whether multiple IP addresses are supported by a server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2596-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c2596-104">Syntax</span></span>  
  
```  
  
object  
.MultiIpConfigurationSupport [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="c2596-105">Partes</span><span class="sxs-lookup"><span data-stu-id="c2596-105">Parts</span></span>  
 <span data-ttu-id="c2596-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c2596-106">*object*</span></span>  
 <span data-ttu-id="c2596-107">Um objeto de [Propriedade ProtocolName (classe ServerNetworkProtocol)](servernetworkprotocol-class.md) que representa o protocolo de rede usado pela instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2596-107">A [ProtocolName Property (ServerNetworkProtocol Class)](servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c2596-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="c2596-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="c2596-109">Um valor booliano que especifica se vários endereços IP têm suporte do protocolo de rede do servidor: `true` se vários endereços IP tiverem suporte do protocolo de rede do servidor ou `false` se vários endereços IP não tiverem suporte do protocolo de rede do servidor.</span><span class="sxs-lookup"><span data-stu-id="c2596-109">A Boolean value that specifies whether multiple IP addresses are supported by the server network protocol: `true` if multiple IP addresses are supported by the server network protocol, or `false` if multiple IP addresses are not supported by the server network protocol.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2596-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="c2596-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2596-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c2596-111">See Also</span></span>  
 <span data-ttu-id="c2596-112">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c2596-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
