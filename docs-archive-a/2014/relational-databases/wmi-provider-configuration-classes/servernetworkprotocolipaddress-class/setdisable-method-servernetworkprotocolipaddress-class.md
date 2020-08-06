---
title: Método SetDisable (classe ServerNetworkProtocolIPAddress) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: 7a7cc8cc-9fb8-4bf5-b483-2150d633ee10
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 9fbe928de1144c3065ddabb07bfd48606fdcea51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679251"
---
# <a name="setdisable-method-servernetworkprotocolipaddress-class"></a><span data-ttu-id="68f2e-102">Método SetDisable (classe ServerNetworkProtocolIPAddress)</span><span class="sxs-lookup"><span data-stu-id="68f2e-102">SetDisable Method (ServerNetworkProtocolIPAddress Class)</span></span>
  <span data-ttu-id="68f2e-103">Desabilita o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="68f2e-103">Disables the IP address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68f2e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="68f2e-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="68f2e-105">Partes</span><span class="sxs-lookup"><span data-stu-id="68f2e-105">Parts</span></span>  
 <span data-ttu-id="68f2e-106">*object*</span><span class="sxs-lookup"><span data-stu-id="68f2e-106">*object*</span></span>  
 <span data-ttu-id="68f2e-107">Um objeto [ServerNetworkProtocolIPAdress Class] ServerNetworkProtocolIPAddress-class.md) que representa um endereço IP para o protocolo de rede em uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="68f2e-107">A [ServerNetworkProtocolIPAdress Class]servernetworkprotocolipaddress-class.md) object that represents an IP address for the network protocol on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="68f2e-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="68f2e-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="68f2e-109">Um valor uint32, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="68f2e-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68f2e-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="68f2e-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f2e-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="68f2e-111">See Also</span></span>  
 <span data-ttu-id="68f2e-112">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="68f2e-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
