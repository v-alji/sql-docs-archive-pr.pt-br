---
title: Método SetBoolValue (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SetBoolValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetBoolValue method
ms.assetid: 5252b439-fce5-446a-8e57-99e3054bee69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0c7142d6f192e94e9850b3c1a8a9481dc15a222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679760"
---
# <a name="setboolvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="33f38-102">Método SetBoolValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="33f38-102">SetBoolValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="33f38-103">Define o valor booliano de uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="33f38-103">Sets the Boolean value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33f38-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="33f38-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="33f38-105">Partes</span><span class="sxs-lookup"><span data-stu-id="33f38-105">Parts</span></span>  
 <span data-ttu-id="33f38-106">*object*</span><span class="sxs-lookup"><span data-stu-id="33f38-106">*object*</span></span>  
 <span data-ttu-id="33f38-107">Um objeto da [classe SqlServiceAdvancedProperty](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) que representa uma propriedade avançada.</span><span class="sxs-lookup"><span data-stu-id="33f38-107">A [SqlServiceAdvancedProperty Class](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="33f38-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="33f38-108">Parameters</span></span>  
  
|<span data-ttu-id="33f38-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="33f38-109">Parameter</span></span>|<span data-ttu-id="33f38-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="33f38-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33f38-111">*BoolValue*</span><span class="sxs-lookup"><span data-stu-id="33f38-111">*BoolValue*</span></span>|<span data-ttu-id="33f38-112">Um valor booliano que especifica o valor da propriedade avançada.</span><span class="sxs-lookup"><span data-stu-id="33f38-112">A Boolean value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="33f38-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="33f38-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="33f38-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="33f38-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33f38-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="33f38-115">Remarks</span></span>  
 <span data-ttu-id="33f38-116">O tipo de valor da propriedade deve ser booliano para definir a propriedade como um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="33f38-116">The property value type must be Boolean to set the property to a Boolean value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f38-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="33f38-117">See Also</span></span>  
 <span data-ttu-id="33f38-118">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="33f38-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
