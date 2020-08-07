---
title: Propriedade Properties (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- Properties Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- Properties property
ms.assetid: 7e0a4e38-4555-4750-8fd3-4425b29e6aa1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 09836db1f510ac77635924c51e5341686627d54d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584049"
---
# <a name="properties-property-clientnetworkprotocol-class"></a><span data-ttu-id="48375-102">Propriedade Properties (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="48375-102">Properties Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="48375-103">Obtém as propriedades associadas com o protocolo de rede do cliente atual especificado pela opção [Configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="48375-103">Gets the properties associated with the current client network protocol specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48375-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="48375-104">Syntax</span></span>  
  
```  
  
object  
.Properties [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="48375-105">Partes</span><span class="sxs-lookup"><span data-stu-id="48375-105">Parts</span></span>  
 <span data-ttu-id="48375-106">*object*</span><span class="sxs-lookup"><span data-stu-id="48375-106">*object*</span></span>  
 <span data-ttu-id="48375-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa o protocolo de rede usado pelo cliente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48375-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="48375-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="48375-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="48375-109">Uma matriz de objetos da [classe ClientNetworkProtocolProperty](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) que representam as propriedades com suporte pelo protocolo de rede do cliente atual que é referenciado pela `OrderValue` propriedade.</span><span class="sxs-lookup"><span data-stu-id="48375-109">An array of [ClientNetworkProtocolProperty Class](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) objects that represent the properties supported by the current client network protocol that is referenced by the `OrderValue` property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48375-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="48375-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48375-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48375-111">See Also</span></span>  
 [<span data-ttu-id="48375-112">Configurando protocolos de cliente de servidor e bibliotecas de rede</span><span class="sxs-lookup"><span data-stu-id="48375-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
