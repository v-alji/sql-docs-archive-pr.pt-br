---
title: Método SetStringValue (classe ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: 0911df30-55f7-4fca-a1fb-01d2c91c1467
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8eb4a27d700d801e3ca94362663c6d7feaa7dc86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679247"
---
# <a name="setstringvalue-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="90b60-102">Método SetStringValue (classe ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="90b60-102">SetStringValue Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="90b60-103">Define o valor da cadeia de caracteres da propriedade referenciada.</span><span class="sxs-lookup"><span data-stu-id="90b60-103">Sets the string value of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90b60-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="90b60-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="90b60-105">Partes</span><span class="sxs-lookup"><span data-stu-id="90b60-105">Parts</span></span>  
 <span data-ttu-id="90b60-106">*object*</span><span class="sxs-lookup"><span data-stu-id="90b60-106">*object*</span></span>  
 <span data-ttu-id="90b60-107">A [classe ServerNetworkProtocolProperty](servernetworkprotocolproperty-class.md) que representa um atributo do protocolo de rede na instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90b60-107">A [ServerNetworkProtocolProperty Class](servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="90b60-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="90b60-108">Parameters</span></span>  
  
|<span data-ttu-id="90b60-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="90b60-109">Parameter</span></span>|<span data-ttu-id="90b60-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="90b60-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90b60-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="90b60-111">*StrValue*</span></span>|<span data-ttu-id="90b60-112">Um valor da cadeia de caracteres que especifica o novo valor da propriedade atual.</span><span class="sxs-lookup"><span data-stu-id="90b60-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="90b60-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="90b60-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="90b60-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="90b60-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90b60-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="90b60-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b60-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90b60-116">See Also</span></span>  
 <span data-ttu-id="90b60-117">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="90b60-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
