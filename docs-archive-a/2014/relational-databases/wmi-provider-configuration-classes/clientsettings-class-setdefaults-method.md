---
title: Método SetDefaults (classe ClientSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ClientSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 056508f3-a5c8-467c-a196-dc1ef1f5178f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b6985ebfa4a9145dd3474cec31f32cdab9c11cdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582842"
---
# <a name="setdefaults-method-clientsettings-class"></a><span data-ttu-id="75fc3-102">Método SetDefaults (classe ClientSettings)</span><span class="sxs-lookup"><span data-stu-id="75fc3-102">SetDefaults Method (ClientSettings Class)</span></span>
  <span data-ttu-id="75fc3-103">Define todos os valores padrão para a instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cliente com a opção de substituir os dados existentes.</span><span class="sxs-lookup"><span data-stu-id="75fc3-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75fc3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="75fc3-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="75fc3-105">Partes</span><span class="sxs-lookup"><span data-stu-id="75fc3-105">Parts</span></span>  
 <span data-ttu-id="75fc3-106">*object*</span><span class="sxs-lookup"><span data-stu-id="75fc3-106">*object*</span></span>  
 <span data-ttu-id="75fc3-107">Um objeto `ClientSettings` que representa uma instância de cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75fc3-107">A `ClientSettings` object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="75fc3-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="75fc3-108">Parameters</span></span>  
  
|<span data-ttu-id="75fc3-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="75fc3-109">Parameter</span></span>|<span data-ttu-id="75fc3-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="75fc3-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75fc3-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="75fc3-111">*OverwriteAll*</span></span>|<span data-ttu-id="75fc3-112">Um valor booliano, que especifica se deve-se substituir valores existentes na instância do cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75fc3-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client.</span></span> <span data-ttu-id="75fc3-113">`true` para substituir dados existentes, ou `false`, se os dados existentes não precisarem ser substituídos.</span><span class="sxs-lookup"><span data-stu-id="75fc3-113">`true` to overwrite existing data; `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="75fc3-114">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="75fc3-114">Property Value/Return Value</span></span>  
 <span data-ttu-id="75fc3-115">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="75fc3-115">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75fc3-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="75fc3-116">Remarks</span></span>  
  
