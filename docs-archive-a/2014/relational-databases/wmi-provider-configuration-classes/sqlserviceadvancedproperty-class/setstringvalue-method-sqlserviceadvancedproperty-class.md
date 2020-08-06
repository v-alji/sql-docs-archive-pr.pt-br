---
title: Método SetStringValue (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (SqlServiceAdvancedProperty Class )
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: a02d05f6-1072-4709-9ecc-e23e51c8c898
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d7939c6af677ac77b9d8005571406315905bfd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681462"
---
# <a name="setstringvalue-method-sqlserviceadvancedproperty-class-"></a><span data-ttu-id="ab61b-102">Método SetStringValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="ab61b-102">SetStringValue Method (SqlServiceAdvancedProperty Class )</span></span>
  <span data-ttu-id="ab61b-103">Define o valor da cadeia de caracteres de uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="ab61b-103">Sets the string value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab61b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ab61b-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ab61b-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ab61b-105">Parts</span></span>  
 <span data-ttu-id="ab61b-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ab61b-106">*object*</span></span>  
 <span data-ttu-id="ab61b-107">Um objeto da [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) que representa uma propriedade avançada.</span><span class="sxs-lookup"><span data-stu-id="ab61b-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="ab61b-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ab61b-108">Parameters</span></span>  
  
|<span data-ttu-id="ab61b-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="ab61b-109">Parameter</span></span>|<span data-ttu-id="ab61b-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="ab61b-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ab61b-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="ab61b-111">*StrValue*</span></span>|<span data-ttu-id="ab61b-112">Um valor da cadeia de caracteres que especifica o valor da propriedade avançada.</span><span class="sxs-lookup"><span data-stu-id="ab61b-112">A string value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ab61b-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="ab61b-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="ab61b-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="ab61b-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab61b-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="ab61b-115">Remarks</span></span>  
 <span data-ttu-id="ab61b-116">O tipo de valor da propriedade deve ser `string` para definir a propriedade como um valor da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ab61b-116">The property value type must be `string` to be able to set the property to a string value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab61b-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ab61b-117">See Also</span></span>  
 <span data-ttu-id="ab61b-118">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ab61b-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
