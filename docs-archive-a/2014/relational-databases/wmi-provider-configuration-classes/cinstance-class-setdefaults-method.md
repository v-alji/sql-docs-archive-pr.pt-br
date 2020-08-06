---
title: Método SetDefaults (classe CInstance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (CInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: ed9e99c2-3e28-4ee8-bc20-61ca05984973
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5e589796f973592d7f9f549bffbbf8dfbe49cc27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568385"
---
# <a name="setdefaults-method-cinstance-class"></a><span data-ttu-id="8247d-102">Método SetDefaults (classe CInstance)</span><span class="sxs-lookup"><span data-stu-id="8247d-102">SetDefaults Method (CInstance Class)</span></span>
  <span data-ttu-id="8247d-103">Define todos os valores padrão para a instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cliente com a opção de substituir os dados existentes.</span><span class="sxs-lookup"><span data-stu-id="8247d-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8247d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8247d-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="8247d-105">Partes</span><span class="sxs-lookup"><span data-stu-id="8247d-105">Parts</span></span>  
 <span data-ttu-id="8247d-106">*object*</span><span class="sxs-lookup"><span data-stu-id="8247d-106">*object*</span></span>  
 <span data-ttu-id="8247d-107">Um objeto da [class CInstance](cinstance-class.md) que representa uma instância do cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8247d-107">A [CInstance Class](cinstance-class.md) object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="8247d-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8247d-108">Parameters</span></span>  
  
|<span data-ttu-id="8247d-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="8247d-109">Parameter</span></span>|<span data-ttu-id="8247d-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="8247d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8247d-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="8247d-111">*OverwriteAll*</span></span>|<span data-ttu-id="8247d-112">Um valor booliano, que especifica se deve-se substituir valores existentes na instância do cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: `true` para substituir dados existentes, ou `false`, se os dados existentes não precisarem ser substituídos.</span><span class="sxs-lookup"><span data-stu-id="8247d-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8247d-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="8247d-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="8247d-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="8247d-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8247d-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="8247d-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8247d-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8247d-116">See Also</span></span>  
 [<span data-ttu-id="8247d-117">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="8247d-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
