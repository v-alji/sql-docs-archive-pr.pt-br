---
title: Método SetNumericalValue (classe ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: d4d6df52-9e68-4003-9e28-ece6716ba7f1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ba963bb14e46aaa3f098ae74cd7aca92019256e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572961"
---
# <a name="setnumericalvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="99b8a-102">Método SetNumericalValue (classe ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="99b8a-102">SetNumericalValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="99b8a-103">Define o valor numérico da propriedade atual referenciado pelo valor [PropertyIdx Property (classe ClientNetworkProtocolProperty) (classe ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="99b8a-103">Sets the numeric value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99b8a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="99b8a-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="99b8a-105">Partes</span><span class="sxs-lookup"><span data-stu-id="99b8a-105">Parts</span></span>  
 <span data-ttu-id="99b8a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="99b8a-106">*object*</span></span>  
 <span data-ttu-id="99b8a-107">A [classe ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) que representa um atributo do protocolo de rede usado pelo cliente do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99b8a-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="99b8a-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="99b8a-108">Parameters</span></span>  
  
|<span data-ttu-id="99b8a-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="99b8a-109">Parameter</span></span>|<span data-ttu-id="99b8a-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="99b8a-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99b8a-111">*value*</span><span class="sxs-lookup"><span data-stu-id="99b8a-111">*value*</span></span>|<span data-ttu-id="99b8a-112">Um valor `uint32` que especifica o valor numérico da propriedade referenciada.</span><span class="sxs-lookup"><span data-stu-id="99b8a-112">A `uint32` value that specifies the numeric value of the referenced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="99b8a-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="99b8a-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="99b8a-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="99b8a-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99b8a-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="99b8a-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b8a-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="99b8a-116">See Also</span></span>  
 [<span data-ttu-id="99b8a-117">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="99b8a-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
