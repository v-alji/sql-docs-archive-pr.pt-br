---
title: Método SetServiceAccountPassword (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccountPassword Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccountPassword method
ms.assetid: e577a1ac-985c-4799-bb38-9393efc3def2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e7a83a6d3686b2ec2df98ae79b4c9d3347f621ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679213"
---
# <a name="setserviceaccountpassword-method-sqlservice-class"></a><span data-ttu-id="ddd18-102">Método SetServiceAccountPassword (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="ddd18-102">SetServiceAccountPassword Method (SqlService Class)</span></span>
  <span data-ttu-id="ddd18-103">Modifica a senha para a conta com a qual o serviço referenciado é executado.</span><span class="sxs-lookup"><span data-stu-id="ddd18-103">Modifies the password for the account that the referenced service runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddd18-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ddd18-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccountPassword(  
AccountOldPassword , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ddd18-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ddd18-105">Parts</span></span>  
 <span data-ttu-id="ddd18-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ddd18-106">*object*</span></span>  
 <span data-ttu-id="ddd18-107">Um objeto da [classe SqlService](sqlservice-class.md) que representa o serviço.</span><span class="sxs-lookup"><span data-stu-id="ddd18-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="ddd18-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ddd18-108">Parameters</span></span>  
 <span data-ttu-id="ddd18-109">*AccountOldPassword*</span><span class="sxs-lookup"><span data-stu-id="ddd18-109">*AccountOldPassword*</span></span>  
 <span data-ttu-id="ddd18-110">Um valor da cadeia de caracteres que especifica a senha existente para a conta.</span><span class="sxs-lookup"><span data-stu-id="ddd18-110">A string value that specifies the existing password for the account.</span></span>  
  
 <span data-ttu-id="ddd18-111">*ServiceStartPassword*</span><span class="sxs-lookup"><span data-stu-id="ddd18-111">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="ddd18-112">Um valor da cadeia de caracteres que especifica a nova senha existente para a conta.</span><span class="sxs-lookup"><span data-stu-id="ddd18-112">A string value that specifies the new password for the account.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ddd18-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="ddd18-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="ddd18-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="ddd18-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddd18-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="ddd18-115">Remarks</span></span>  
  
