---
title: Propriedade PropertyValType (classe ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- PropertyValType Property (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- PropertyValType property
ms.assetid: fbd42e8e-0642-4a19-b3c8-6ce88345145f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: be6c42fbaa36080ec8144d95abb045a3b4328057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684623"
---
# <a name="propertyvaltype-property-servernetworkprotocolproperty-class"></a><span data-ttu-id="bcc6a-102">Propriedade PropertyValType (classe ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="bcc6a-102">PropertyValType Property (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="bcc6a-103">Obtém o tipo de dados do valor armazenado na propriedade referenciada.</span><span class="sxs-lookup"><span data-stu-id="bcc6a-103">Gets the data type of the value stored in the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcc6a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bcc6a-104">Syntax</span></span>  
  
```  
  
object  
.PropertyValType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="bcc6a-105">Partes</span><span class="sxs-lookup"><span data-stu-id="bcc6a-105">Parts</span></span>  
 <span data-ttu-id="bcc6a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="bcc6a-106">*object*</span></span>  
 <span data-ttu-id="bcc6a-107">A [classe ServerNetworkProtocolProperty](servernetworkprotocolproperty-class.md) que representa um atributo do protocolo de rede na instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcc6a-107">A [ServerNetworkProtocolProperty Class](servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bcc6a-108">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="bcc6a-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="bcc6a-109">Um valor `uint32` que especifica o tipo de dado do valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="bcc6a-109">A `uint32` value that specifies the data type of the property value.</span></span> <span data-ttu-id="bcc6a-110">Retorna 0 para um valor da cadeia de caracteres e 1 para um tipo numérico.</span><span class="sxs-lookup"><span data-stu-id="bcc6a-110">It returns 0 for a string value and 1 for a numerical type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcc6a-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="bcc6a-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc6a-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bcc6a-112">See Also</span></span>  
 <span data-ttu-id="bcc6a-113">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="bcc6a-113">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
