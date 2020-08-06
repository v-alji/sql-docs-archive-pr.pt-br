---
title: Compatibilidade com versões anteriores do Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- installing Analysis Services, backward compatibility
- backward compatibility [Analysis Services]
- compatibility [Analysis Services]
- Analysis Services, backward compatibility
- upgrading Analysis Services
- SSAS, backward compatibility
- SQL Server Analysis Services, backward compatibility
ms.assetid: 618b6c3a-e20d-47a9-b2c6-6d848dfba05a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44a5296bfbd2bae746eb9936d416fd696de16cb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571219"
---
# <a name="analysis-services-backward-compatibility"></a><span data-ttu-id="83e05-102">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="83e05-102">Analysis Services Backward Compatibility</span></span>
  <span data-ttu-id="83e05-103">Os tópicos nesta seção descrevem as alterações no comportamento entre versões do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83e05-103">The topics in this section describe the changes in behavior between versions of  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83e05-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="83e05-104">In This Section</span></span>  
  
|<span data-ttu-id="83e05-105">Tópicos</span><span class="sxs-lookup"><span data-stu-id="83e05-105">Topics</span></span>|<span data-ttu-id="83e05-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="83e05-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83e05-107">Recursos do Analysis Services preteridos no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="83e05-107">Deprecated Analysis Services Features in SQL Server 2014</span></span>](deprecated-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="83e05-108">Descreve recursos que foram retidos na versão atual para manter a compatibilidade com versões anteriores, mas que serão removidos em uma versão futura do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83e05-108">Describes features that have been retained in the current version to maintain backward compatibility,  but which will be removed in a future version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="83e05-109">Funcionalidade descontinuada do Analysis Services no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="83e05-109">Discontinued Analysis Services Functionality in SQL Server 2014</span></span>](discontinued-analysis-services-functionality-in-sql-server-2014.md)|<span data-ttu-id="83e05-110">Descreve recursos que existiam em versões anteriores do  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , mas que foram removidos em versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="83e05-110">Describes features that existed in earlier versions of  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] but that have since been removed in later versions.</span></span>|  
|[<span data-ttu-id="83e05-111">Alterações recentes em recursos do Analysis Services no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="83e05-111">Breaking Changes to Analysis Services Features in SQL Server 2014</span></span>](breaking-changes-to-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="83e05-112">Descreve as alterações de código introduzidas nesta versão do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que pudesse interromper um modelo ou aplicativos personalizados ou scripts criados em versões anteriores do software.</span><span class="sxs-lookup"><span data-stu-id="83e05-112">Describes code changes introduced in this release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that could potentially break a model or custom applications or script created in previous versions of the software .</span></span>|  
|[<span data-ttu-id="83e05-113">Alterações no comportamento de recursos do Analysis Services no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="83e05-113">Behavior Changes to Analysis Services Features in SQL Server 2014</span></span>](behavior-changes-to-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="83e05-114">Descreve os recursos existentes que têm comportamentos diferentes nesta versão do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83e05-114">Describes existing features that have different behaviors in this release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="83e05-115">Exemplos comuns incluem a alteração de um padrão para um valor novo ou diferente, a desabilitação de uma operação permitida anteriormente ou configuração, ou uma apresentação a um requisito para revisar manualmente ou substituir uma definição ou configuração que será perdida durante a atualização.</span><span class="sxs-lookup"><span data-stu-id="83e05-115">Common examples include changing a default to a new or different value, disallowing a previously allowable operation or configuration, or a introducing a requirement to manually revise or replace a setting or configuration that is lost during upgrade.</span></span><br /> <span data-ttu-id="83e05-116">.</span><span class="sxs-lookup"><span data-stu-id="83e05-116">.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83e05-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83e05-117">See Also</span></span>  
 <span data-ttu-id="83e05-118">[O que há de novo no Analysis Services e Business Intelligence](what-s-new-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="83e05-118">[What's New in Analysis Services and Business Intelligence](what-s-new-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="83e05-119">Atualizar o Analysis Services</span><span class="sxs-lookup"><span data-stu-id="83e05-119">Upgrade Analysis Services</span></span>](../database-engine/install-windows/upgrade-analysis-services.md)  
  
  
