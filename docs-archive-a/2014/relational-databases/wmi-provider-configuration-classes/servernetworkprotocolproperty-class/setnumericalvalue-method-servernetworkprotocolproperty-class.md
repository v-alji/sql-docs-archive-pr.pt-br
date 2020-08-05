---
title: Método SetNumericalValue (classe ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: b3b4bce8-9d9e-4ccb-a223-0454281353b0
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f5a4b8d6819dae11abe4cc097f0e423c23d909e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573858"
---
# <a name="setnumericalvalue-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="75132-102">Método SetNumericalValue (classe ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="75132-102">SetNumericalValue Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="75132-103">Define o valor numérico da propriedade referenciada.</span><span class="sxs-lookup"><span data-stu-id="75132-103">Sets the numeric value of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75132-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="75132-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="75132-105">Partes</span><span class="sxs-lookup"><span data-stu-id="75132-105">Parts</span></span>  
 <span data-ttu-id="75132-106">*object*</span><span class="sxs-lookup"><span data-stu-id="75132-106">*object*</span></span>  
 <span data-ttu-id="75132-107">Um objeto [ServerNetworkProtocolProperty Class] ServerNetworkProtocolProperty-class.md) que representa um atributo do protocolo de rede na instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75132-107">A [ServerNetworkProtocolProperty Class]servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="75132-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="75132-108">Parameters</span></span>  
  
|<span data-ttu-id="75132-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="75132-109">Parameter</span></span>|<span data-ttu-id="75132-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="75132-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75132-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="75132-111">*NumValue*</span></span>|<span data-ttu-id="75132-112">Um valor `uint32` que especifica o novo valor da propriedade atual.</span><span class="sxs-lookup"><span data-stu-id="75132-112">A `uint32` value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="75132-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="75132-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="75132-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="75132-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75132-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="75132-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75132-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="75132-116">See Also</span></span>  
 <span data-ttu-id="75132-117">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="75132-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
