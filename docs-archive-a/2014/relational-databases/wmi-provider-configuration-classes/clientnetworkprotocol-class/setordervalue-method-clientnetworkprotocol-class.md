---
title: Método SetOrderValue (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetOrderValue method
ms.assetid: 15f693fd-37f6-41d9-9dab-d2c93db19895
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6839e85b6131c54e233d980c84a8727eeda2202a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583441"
---
# <a name="setordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="80dcc-102">Método SetOrderValue (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="80dcc-102">SetOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="80dcc-103">Seleciona o protocolo com o valor de ordem especificado da lista de protocolo do cliente.</span><span class="sxs-lookup"><span data-stu-id="80dcc-103">Selects the protocol with the specified order value from the client protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80dcc-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="80dcc-104">Syntax</span></span>  
  
```  
  
object  
.SetOrderValue(  
OrderValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="80dcc-105">Partes</span><span class="sxs-lookup"><span data-stu-id="80dcc-105">Parts</span></span>  
 <span data-ttu-id="80dcc-106">*object*</span><span class="sxs-lookup"><span data-stu-id="80dcc-106">*object*</span></span>  
 <span data-ttu-id="80dcc-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa o protocolo de rede usado pelo cliente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80dcc-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="80dcc-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="80dcc-108">Parameters</span></span>  
  
|<span data-ttu-id="80dcc-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="80dcc-109">Parameter</span></span>|<span data-ttu-id="80dcc-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="80dcc-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80dcc-111">*OrderValue*</span><span class="sxs-lookup"><span data-stu-id="80dcc-111">*OrderValue*</span></span>|<span data-ttu-id="80dcc-112">Um valor `int32` que define o valor de ordem.</span><span class="sxs-lookup"><span data-stu-id="80dcc-112">A u`int32` value that sets the order value.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="80dcc-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="80dcc-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="80dcc-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="80dcc-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80dcc-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="80dcc-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80dcc-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="80dcc-116">See Also</span></span>  
 [<span data-ttu-id="80dcc-117">Propriedades de Protocolos de Cliente (guia Ordem)</span><span class="sxs-lookup"><span data-stu-id="80dcc-117">Client Protocols Properties (Order Tab)</span></span>](https://technet.microsoft.com/library/ms187884.aspx)  
  
  
