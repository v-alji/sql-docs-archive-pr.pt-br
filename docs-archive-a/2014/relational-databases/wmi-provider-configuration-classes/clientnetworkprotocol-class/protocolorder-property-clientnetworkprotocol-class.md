---
title: Propriedade ProtocolOrder (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ProtocolOrder Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ProtocolOrder property
ms.assetid: aa09b8ab-37db-4406-8973-acf503855fd2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8bccb7109972dea4697e9e289081cbf47d2f9492
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583442"
---
# <a name="protocolorder-property-clientnetworkprotocol-class"></a><span data-ttu-id="5bf61-102">Propriedade ProtocolOrder (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="5bf61-102">ProtocolOrder Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="5bf61-103">Obtém o número de pedido do protocolo de rede do cliente atualmente referenciado como especificado pelo [método SetOrderValue (classe ClientNetworkProtocol)](clientnetworkprotocol-class.md) .</span><span class="sxs-lookup"><span data-stu-id="5bf61-103">Gets the order number of the currently referenced client network protocol as specified by the [SetOrderValue Method (ClientNetworkProtocol Class)](clientnetworkprotocol-class.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf61-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5bf61-104">Syntax</span></span>  
  
```  
  
object  
.ProtocolOrder [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="5bf61-105">Partes</span><span class="sxs-lookup"><span data-stu-id="5bf61-105">Parts</span></span>  
 <span data-ttu-id="5bf61-106">*object*</span><span class="sxs-lookup"><span data-stu-id="5bf61-106">*object*</span></span>  
 <span data-ttu-id="5bf61-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa o protocolo de rede usado pelo cliente do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5bf61-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5bf61-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="5bf61-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="5bf61-109">Um valor `uint32` que especifica o número de pedido do protocolo de rede do cliente atualmente referenciado como definido pelo método `OrderValue`.</span><span class="sxs-lookup"><span data-stu-id="5bf61-109">A `uint32` value that specifies the order number of the currently referenced client network protocol as set by the `OrderValue` method.</span></span> <span data-ttu-id="5bf61-110">Se o protocolo de rede de cliente estiver desabilitado, esse valor será zero.</span><span class="sxs-lookup"><span data-stu-id="5bf61-110">If the client network protocol is disabled, this value will be zero.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bf61-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="5bf61-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf61-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5bf61-112">See Also</span></span>  
 <span data-ttu-id="5bf61-113">[Configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="5bf61-113">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="5bf61-114">Configurando protocolos de cliente de servidor e bibliotecas de rede</span><span class="sxs-lookup"><span data-stu-id="5bf61-114">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
