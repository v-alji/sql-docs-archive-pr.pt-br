---
title: Método SetValue (classe ClientSettingsGeneralFlag) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ClientSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: 34443689-a0e0-4668-a811-17532c6fd271
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: fffa44bd8743f96a43ca4d1787d8d2afaad5e6cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679266"
---
# <a name="setvalue-method-clientsettingsgeneralflag-class"></a><span data-ttu-id="bdd02-102">Método SetValue (classe ClientSettingsGeneralFlag)</span><span class="sxs-lookup"><span data-stu-id="bdd02-102">SetValue Method (ClientSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="bdd02-103">Define todos os valores do sinalizador referenciado.</span><span class="sxs-lookup"><span data-stu-id="bdd02-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdd02-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bdd02-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="bdd02-105">Partes</span><span class="sxs-lookup"><span data-stu-id="bdd02-105">Parts</span></span>  
 <span data-ttu-id="bdd02-106">*object*</span><span class="sxs-lookup"><span data-stu-id="bdd02-106">*object*</span></span>  
 <span data-ttu-id="bdd02-107">Um objeto da [classe ClientSettingsGeneralFlag](clientsettingsgeneralflag-class.md) que representa um sinalizador geral para as configurações de servidor.</span><span class="sxs-lookup"><span data-stu-id="bdd02-107">A [ClientSettingsGeneralFlag Class](clientsettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="bdd02-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bdd02-108">Parameters</span></span>  
  
|<span data-ttu-id="bdd02-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="bdd02-109">Parameter</span></span>|<span data-ttu-id="bdd02-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="bdd02-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bdd02-111">*Valor*</span><span class="sxs-lookup"><span data-stu-id="bdd02-111">*Value*</span></span>|<span data-ttu-id="bdd02-112">Um valor booliano que especifica o valor do sinalizador.</span><span class="sxs-lookup"><span data-stu-id="bdd02-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bdd02-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="bdd02-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="bdd02-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="bdd02-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdd02-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="bdd02-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd02-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bdd02-116">See Also</span></span>  
 [<span data-ttu-id="bdd02-117">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="bdd02-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
