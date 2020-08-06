---
title: Método SetStrValue (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStrValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStrValue method
ms.assetid: 1fededc3-81ba-4b08-83f9-189b96140799
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d977eb9845c820c4128d1d60337151eeb3893eb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681460"
---
# <a name="setstrvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="22329-102">Método SetStrValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="22329-102">SetStrValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="22329-103">Define o valor da cadeia de caracteres de uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="22329-103">Sets the string value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22329-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="22329-104">Syntax</span></span>  
  
```  
  
object  
.SetStrValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="22329-105">Partes</span><span class="sxs-lookup"><span data-stu-id="22329-105">Parts</span></span>  
 <span data-ttu-id="22329-106">*object*</span><span class="sxs-lookup"><span data-stu-id="22329-106">*object*</span></span>  
 <span data-ttu-id="22329-107">Um objeto da [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) que representa uma propriedade avançada.</span><span class="sxs-lookup"><span data-stu-id="22329-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="22329-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="22329-108">Parameters</span></span>  
  
|<span data-ttu-id="22329-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="22329-109">Parameter</span></span>|<span data-ttu-id="22329-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="22329-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22329-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="22329-111">*StrValue*</span></span>|<span data-ttu-id="22329-112">Um valor da cadeia de caracteres que especifica o valor da propriedade avançada.</span><span class="sxs-lookup"><span data-stu-id="22329-112">A string value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="22329-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="22329-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="22329-114">Um valor uint32, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="22329-114">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22329-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="22329-115">Remarks</span></span>  
 <span data-ttu-id="22329-116">O tipo de valor da propriedade deve ser *string* para definir a propriedade como um valor da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="22329-116">The property value type must be *string* to set the property to a string value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22329-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="22329-117">See Also</span></span>  
 <span data-ttu-id="22329-118">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="22329-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
