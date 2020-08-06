---
title: Método SetDefaults (classe SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: dc3c6a85-0711-4688-bf4f-91168c57af28
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: c581834d3c97bed622d16fbb35e48704f8679531
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679231"
---
# <a name="setdefaults-method-sinstance-class"></a><span data-ttu-id="05267-102">Método SetDefaults (classe SInstance)</span><span class="sxs-lookup"><span data-stu-id="05267-102">SetDefaults Method (SInstance Class)</span></span>
  <span data-ttu-id="05267-103">Define todos os valores padrão para a instância do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] com a opção de substituir os dados existentes.</span><span class="sxs-lookup"><span data-stu-id="05267-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05267-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="05267-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="05267-105">Partes</span><span class="sxs-lookup"><span data-stu-id="05267-105">Parts</span></span>  
 <span data-ttu-id="05267-106">*object*</span><span class="sxs-lookup"><span data-stu-id="05267-106">*object*</span></span>  
 <span data-ttu-id="05267-107">Um objeto de [classe SInstance](sinstance-class.md) que representa uma instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="05267-107">An [SInstance Class](sinstance-class.md) object that represents a server instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="05267-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="05267-108">Parameters</span></span>  
  
|<span data-ttu-id="05267-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="05267-109">Parameter</span></span>|<span data-ttu-id="05267-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="05267-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="05267-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="05267-111">*OverwriteAll*</span></span>|<span data-ttu-id="05267-112">Um valor booliano que especifica se deve-se substituir o valor existente na instância do cliente do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: `true` se os dados existentes forem substituídos ou `false` se os dados existentes não forem substituídos.</span><span class="sxs-lookup"><span data-stu-id="05267-112">A Boolean value that specifies whether to overwrite existing value on the instance of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client: `true` if existing data is overwritten, or `false` if existing data is not overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="05267-113">Valor da propriedade/Valor do retorno</span><span class="sxs-lookup"><span data-stu-id="05267-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="05267-114">Um valor `uint32`, que é 0 se o serviço tiver sido modificado com êxito, 1 se a solicitação não tiver suporte e qualquer outro número para indicar um erro.</span><span class="sxs-lookup"><span data-stu-id="05267-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05267-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="05267-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05267-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05267-116">See Also</span></span>  
 <span data-ttu-id="05267-117">[Configurando protocolos de rede de servidor e Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="05267-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
