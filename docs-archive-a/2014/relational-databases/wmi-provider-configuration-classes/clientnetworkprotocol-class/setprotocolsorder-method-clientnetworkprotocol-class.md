---
title: Método SetProtocolsOrder (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetProtocolsOrder Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetProtocolsOrder method
ms.assetid: b86d98b9-aae4-4e74-b4da-1ec984d5c8b4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: aaa1d43c8a2f7f210f61761b28313a93ac6c7a90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583437"
---
# <a name="setprotocolsorder-method-clientnetworkprotocol-class"></a><span data-ttu-id="aeada-102">Método SetProtocolsOrder (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="aeada-102">SetProtocolsOrder Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="aeada-103">Altera a ordem da lista de protocolo.</span><span class="sxs-lookup"><span data-stu-id="aeada-103">Changes the order of the protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aeada-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aeada-104">Syntax</span></span>  
  
```  
  
object  
.SetProtocolsOrder(  
ProtocolOrderList  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="aeada-105">Partes</span><span class="sxs-lookup"><span data-stu-id="aeada-105">Parts</span></span>  
 <span data-ttu-id="aeada-106">*object*</span><span class="sxs-lookup"><span data-stu-id="aeada-106">*object*</span></span>  
 <span data-ttu-id="aeada-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa o protocolo de rede usado pelo cliente do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aeada-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="aeada-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="aeada-108">Parameters</span></span>  
  
|<span data-ttu-id="aeada-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="aeada-109">Parameter</span></span>|<span data-ttu-id="aeada-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="aeada-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aeada-111">*ProtocolOrderList*</span><span class="sxs-lookup"><span data-stu-id="aeada-111">*ProtocolOrderList*</span></span>|<span data-ttu-id="aeada-112">Uma matriz da cadeia de caracteres [] que lista os protocolos de rede do cliente na ordem nova.</span><span class="sxs-lookup"><span data-stu-id="aeada-112">A string[] array that lists the client network protocols in the new order.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="aeada-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="aeada-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="aeada-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="aeada-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aeada-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="aeada-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeada-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aeada-116">See Also</span></span>  
 <span data-ttu-id="aeada-117">[Configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="aeada-117">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="aeada-118">Configurando protocolos de cliente de servidor e bibliotecas de rede</span><span class="sxs-lookup"><span data-stu-id="aeada-118">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
