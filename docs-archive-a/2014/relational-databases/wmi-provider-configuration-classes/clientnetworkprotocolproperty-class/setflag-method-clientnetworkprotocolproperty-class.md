---
title: Método SetFlag (classe ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 0407520f-2f84-4f68-b2b7-429697286c1b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1c83a1d647b62f0e5c5acf0659d54bf787bf0c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684133"
---
# <a name="setflag-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="d4106-102">Método SetFlag (classe ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="d4106-102">SetFlag Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="d4106-103">Define o sinalizador da cadeia de caracteres da propriedade atual referenciado pelo valor [PropertyIdx Property (classe ClientNetworkProtocolProperty) (classe ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="d4106-103">Sets the flag of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4106-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d4106-104">Syntax</span></span>  
  
```  
  
object  
.SetFlag(  
BoolValue  
) [=]  
```  
  
## <a name="parts"></a><span data-ttu-id="d4106-105">Partes</span><span class="sxs-lookup"><span data-stu-id="d4106-105">Parts</span></span>  
 <span data-ttu-id="d4106-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d4106-106">*object*</span></span>  
 <span data-ttu-id="d4106-107">A [classe ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) que representa um atributo do protocolo de rede usado pelo cliente do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4106-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="d4106-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d4106-108">Parameters</span></span>  
  
|<span data-ttu-id="d4106-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="d4106-109">Parameter</span></span>|<span data-ttu-id="d4106-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="d4106-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4106-111">*BoolValue*</span><span class="sxs-lookup"><span data-stu-id="d4106-111">*BoolValue*</span></span>|<span data-ttu-id="d4106-112">Um valor booliano que especifica o novo valor do sinalizador.</span><span class="sxs-lookup"><span data-stu-id="d4106-112">A Boolean value that specifies the new value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d4106-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="d4106-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="d4106-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="d4106-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4106-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="d4106-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4106-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4106-116">See Also</span></span>  
 [<span data-ttu-id="d4106-117">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="d4106-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
