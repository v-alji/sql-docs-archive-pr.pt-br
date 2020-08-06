---
title: Propriedade IpAddresses (classe ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- IpAddresses Property (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- IpAddresses property
ms.assetid: e5d66f7e-9719-436e-b723-12d56f914a05
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b94c4c11327abc1f02bd1e99c414f806f75bc145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568374"
---
# <a name="ipaddresses-property-servernetworkprotocol-class"></a><span data-ttu-id="c1ce3-102">Propriedade IpAddresses (classe ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="c1ce3-102">IpAddresses Property (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="c1ce3-103">Obtém os endereços IP associados com o protocolo de rede do servidor.</span><span class="sxs-lookup"><span data-stu-id="c1ce3-103">Gets the IP addresses associated with the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ce3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c1ce3-104">Syntax</span></span>  
  
```  
  
object  
.IpAddresses [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="c1ce3-105">Partes</span><span class="sxs-lookup"><span data-stu-id="c1ce3-105">Parts</span></span>  
 <span data-ttu-id="c1ce3-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c1ce3-106">*object*</span></span>  
 <span data-ttu-id="c1ce3-107">Um `ServerNetworkProtocol` objeto que representa o protocolo de rede usado pela instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c1ce3-107">A `ServerNetworkProtocol` object that represents the network protocol used by the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c1ce3-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="c1ce3-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="c1ce3-109">Uma matriz de objetos de [classe ServerNetworkProtocolIPAdress](../servernetworkprotocolipaddress-class/servernetworkprotocolipaddress-class.md) que representam os endereços IP com suporte no protocolo de rede do servidor.</span><span class="sxs-lookup"><span data-stu-id="c1ce3-109">An array of [ServerNetworkProtocolIPAdress Class](../servernetworkprotocolipaddress-class/servernetworkprotocolipaddress-class.md) objects that represent the IP addresses supported by the server network protocol.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1ce3-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="c1ce3-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ce3-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c1ce3-111">See Also</span></span>  
 <span data-ttu-id="c1ce3-112">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c1ce3-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
