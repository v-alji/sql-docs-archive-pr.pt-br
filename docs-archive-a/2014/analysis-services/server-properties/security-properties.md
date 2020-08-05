---
title: Propriedades de segurança | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], properties
- SecurityPackageList property
- BuiltinAdminsAreServerAdmins property
- DisableClientImpersonation property
- ErrorMessageMode property
- RequiredProtectionLevel property
- ServiceAccountIsServerAdmin property
- RequireClientAuthentication property
ms.assetid: 2fc7fe10-0cbb-49ac-aa8c-8ec3f7a7705f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 20133554835803908a340c5369eb66e86b119d72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573307"
---
# <a name="security-properties"></a><span data-ttu-id="b3be7-102">Propriedades de segurança</span><span class="sxs-lookup"><span data-stu-id="b3be7-102">Security Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="b3be7-103">oferece suporte às propriedades do servidor de segurança listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b3be7-103">supports the security server properties listed in the following table.</span></span> <span data-ttu-id="b3be7-104">Para obter mais informações sobre as propriedades de servidor adicionais e como defini-las, consulte [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="b3be7-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="b3be7-105">**Aplica-se a:** modo de servidor multidimensional e tabular</span><span class="sxs-lookup"><span data-stu-id="b3be7-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b3be7-106">Propriedades</span><span class="sxs-lookup"><span data-stu-id="b3be7-106">Properties</span></span>  
 `RequireClientAuthentication`  
 <span data-ttu-id="b3be7-107">Uma propriedade booliana que indica se autenticação de cliente é necessária.</span><span class="sxs-lookup"><span data-stu-id="b3be7-107">A Boolean property that indicates whether client authentication is required.</span></span>  
  
 <span data-ttu-id="b3be7-108">O valor padrão para essa propriedade é True, o que indica que autenticação de cliente é necessária.</span><span class="sxs-lookup"><span data-stu-id="b3be7-108">The default value for this property is True, which indicates that client authentication is required.</span></span>  
  
 `SecurityPackageList`  
 <span data-ttu-id="b3be7-109">Uma propriedade de cadeia de caracteres que contém uma lista separada por vírgulas de pacotes SSPI usada pelo servidor para autenticação de cliente.</span><span class="sxs-lookup"><span data-stu-id="b3be7-109">A string property that contains a comma-separated list of SSPI packages used by server for client authentication.</span></span>  
  
 `DisableClientImpersonation`  
 <span data-ttu-id="b3be7-110">Uma propriedade booliana que indica se a representação do cliente (por exemplo, de procedimentos armazenados) está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="b3be7-110">A Boolean property that indicates whether client impersonation (for example, from stored procedures) is disabled.</span></span>  
  
 <span data-ttu-id="b3be7-111">O valor padrão dessa propriedade é False, o que indica que representação do cliente está habilitada.</span><span class="sxs-lookup"><span data-stu-id="b3be7-111">The default value for this property is False, which indicates that client impersonation is enabled.</span></span>  
  
 `BuiltinAdminsAreServerAdmins`  
 <span data-ttu-id="b3be7-112">Uma propriedade booliana que indica se membros do grupo de administradores de máquina local são administradores do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3be7-112">A Boolean property that indicates whether members of the local machine administrators group are [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrators.</span></span>  
  
 `ServiceAccountIsServerAdmin`  
 <span data-ttu-id="b3be7-113">Uma propriedade booliana que indica se a conta de serviço é um administrador do servidor.</span><span class="sxs-lookup"><span data-stu-id="b3be7-113">A Boolean property that indicates whether the service account is a server administrator.</span></span>  
  
 <span data-ttu-id="b3be7-114">O valor padrão dessa propriedade é True, o que indica que a conta de serviço é um administrador do servidor.</span><span class="sxs-lookup"><span data-stu-id="b3be7-114">The default value for this property is True, which indicates that the service account is a server administrator.</span></span>  
  
 `ErrorMessageMode`  
 <span data-ttu-id="b3be7-115">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3be7-115">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="b3be7-116">Uma propriedade de inteiro de 32 bits assinada que define o nível de proteção exigido para todas as requisições do cliente.</span><span class="sxs-lookup"><span data-stu-id="b3be7-116">A signed 32-bit integer property that defines the required protection level for all client requests.</span></span> <span data-ttu-id="b3be7-117">Essa propriedade tem um dos valores listados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="b3be7-117">This property has one of the values listed in the following table.</span></span>  
  
|<span data-ttu-id="b3be7-118">Valor</span><span class="sxs-lookup"><span data-stu-id="b3be7-118">Value</span></span>|<span data-ttu-id="b3be7-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="b3be7-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b3be7-120">*0*</span><span class="sxs-lookup"><span data-stu-id="b3be7-120">*0*</span></span>|<span data-ttu-id="b3be7-121">Nenhum, texto não criptografado permitido.</span><span class="sxs-lookup"><span data-stu-id="b3be7-121">None, clear text allowed.</span></span>|  
|<span data-ttu-id="b3be7-122">*1*</span><span class="sxs-lookup"><span data-stu-id="b3be7-122">*1*</span></span>|<span data-ttu-id="b3be7-123">(Padrão) Criptografia necessária, sem log de texto não criptografado.</span><span class="sxs-lookup"><span data-stu-id="b3be7-123">(Default) Encryption required, no clear-text logging.</span></span>|  
|<span data-ttu-id="b3be7-124">*2*</span><span class="sxs-lookup"><span data-stu-id="b3be7-124">*2*</span></span>|<span data-ttu-id="b3be7-125">Solicitações de textos não criptografados são permitidas, mas apenas com assinaturas (proteção mais baixa do que criptografia).</span><span class="sxs-lookup"><span data-stu-id="b3be7-125">Clear-text requests allowed but only with signatures (weaker protection than encryption).</span></span>|  
  
 `AdministrativeDataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="b3be7-126">Uma propriedade avançada que não deve ser alterada, exceto sob orientação do suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3be7-126">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3be7-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b3be7-127">See Also</span></span>  
 <span data-ttu-id="b3be7-128">[Configurar propriedades do servidor no Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="b3be7-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="b3be7-129">Determina o Modo de Servidor de uma instância do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="b3be7-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
