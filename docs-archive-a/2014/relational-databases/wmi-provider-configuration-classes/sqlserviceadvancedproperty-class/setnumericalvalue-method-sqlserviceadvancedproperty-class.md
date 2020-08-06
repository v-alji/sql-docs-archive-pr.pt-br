---
title: Método SetNumericalValue (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: 950ed1e8-0538-4db4-807c-a2c36f43cf6b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: db823938d77f4e2c67284cae0f11faca12aba6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684115"
---
# <a name="setnumericalvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="bfd9e-102">Método SetNumericalValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="bfd9e-102">SetNumericalValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="bfd9e-103">Define o valor numérico de uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="bfd9e-103">Sets the numeric value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfd9e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bfd9e-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="bfd9e-105">Partes</span><span class="sxs-lookup"><span data-stu-id="bfd9e-105">Parts</span></span>  
 <span data-ttu-id="bfd9e-106">*object*</span><span class="sxs-lookup"><span data-stu-id="bfd9e-106">*object*</span></span>  
 <span data-ttu-id="bfd9e-107">Um objeto da [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) que representa uma propriedade avançada.</span><span class="sxs-lookup"><span data-stu-id="bfd9e-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="bfd9e-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bfd9e-108">Parameters</span></span>  
  
|<span data-ttu-id="bfd9e-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="bfd9e-109">Parameter</span></span>|<span data-ttu-id="bfd9e-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="bfd9e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bfd9e-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="bfd9e-111">*NumValue*</span></span>|<span data-ttu-id="bfd9e-112">Um valor `uint32` que especifica o valor da propriedade avançada.</span><span class="sxs-lookup"><span data-stu-id="bfd9e-112">A `uint32` value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bfd9e-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="bfd9e-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="bfd9e-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="bfd9e-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfd9e-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="bfd9e-115">Remarks</span></span>  
 <span data-ttu-id="bfd9e-116">O tipo de valor da propriedade deve ser numérico para poder definir a propriedade como um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="bfd9e-116">The property value type must be numeric to be able to set the property to a numeric value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfd9e-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bfd9e-117">See Also</span></span>  
 <span data-ttu-id="bfd9e-118">[Iniciando e parando serviços](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="bfd9e-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
