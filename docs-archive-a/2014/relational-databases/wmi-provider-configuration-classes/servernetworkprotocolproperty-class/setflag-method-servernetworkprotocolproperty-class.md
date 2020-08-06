---
title: Método SetFlag (classe ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 95288931-8eb1-4477-ad80-619cf7073e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1a90b4fca194f20cc0a2d70c947577594155f051
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679752"
---
# <a name="setflag-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="4a1b4-102">Método SetFlag (classe ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="4a1b4-102">SetFlag Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="4a1b4-103">Define o sinalizador da propriedade referenciada.</span><span class="sxs-lookup"><span data-stu-id="4a1b4-103">Sets the flag of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a1b4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4a1b4-104">Syntax</span></span>  
  
```  
  
object  
.SetFlag(  
BoolValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="4a1b4-105">Partes</span><span class="sxs-lookup"><span data-stu-id="4a1b4-105">Parts</span></span>  
 <span data-ttu-id="4a1b4-106">*object*</span><span class="sxs-lookup"><span data-stu-id="4a1b4-106">*object*</span></span>  
 <span data-ttu-id="4a1b4-107">Um objeto [ServerNetworkProtocolProperty Class] ServerNetworkProtocolProperty-class.md) que representa um atributo do protocolo de rede na instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4a1b4-107">A [ServerNetworkProtocolProperty Class]servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="4a1b4-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4a1b4-108">Parameters</span></span>  
  
|<span data-ttu-id="4a1b4-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="4a1b4-109">Parameter</span></span>|<span data-ttu-id="4a1b4-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="4a1b4-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a1b4-111">*BoolValue*</span><span class="sxs-lookup"><span data-stu-id="4a1b4-111">*BoolValue*</span></span>|<span data-ttu-id="4a1b4-112">Um valor booliano que especifica o novo valor do sinalizador.</span><span class="sxs-lookup"><span data-stu-id="4a1b4-112">A Boolean value that specifies the new value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4a1b4-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="4a1b4-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="4a1b4-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="4a1b4-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a1b4-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="4a1b4-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a1b4-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4a1b4-116">See Also</span></span>  
 <span data-ttu-id="4a1b4-117">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4a1b4-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
