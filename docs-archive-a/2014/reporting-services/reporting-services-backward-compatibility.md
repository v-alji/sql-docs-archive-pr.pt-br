---
title: Compatibilidade com versões anteriores do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- SSRS, backward compatibility
- SQL Server Reporting Services, backward compatibility
- backward compatibility [Reporting Services]
ms.assetid: 675b0e0e-cfee-4790-9675-80fc3ea6d30f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7203740ba7f52dfc2cd3793a20fed9fecf5f9468
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682106"
---
# <a name="reporting-services-backward-compatibility"></a><span data-ttu-id="b19f7-102">Compatibilidade com versões anteriores do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b19f7-102">Reporting Services Backward Compatibility</span></span>
  <span data-ttu-id="b19f7-103">Esta seção descreve as alterações no comportamento entre as versões do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b19f7-103">This section describes changes in behavior between versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="b19f7-104">Ela abrange recursos que não estão mais disponíveis ou que estão agendados para serem removidos em uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="b19f7-104">It covers features that are no longer available or are scheduled to be removed in a future release.</span></span> <span data-ttu-id="b19f7-105">Também descreve as principais alterações no produto que sabidamente interrompem um aplicativo personalizado que inclua a funcionalidade do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b19f7-105">It also describes fundamental changes to the product that are known to break a custom application that includes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b19f7-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b19f7-106">In This Section</span></span>  
  
|<span data-ttu-id="b19f7-107">Tópico</span><span class="sxs-lookup"><span data-stu-id="b19f7-107">Topic</span></span>|<span data-ttu-id="b19f7-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b19f7-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b19f7-109">Funcionalidade descontinuada do SQL Server Reporting Services no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b19f7-109">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)|<span data-ttu-id="b19f7-110">Descreve recursos que existiam em versões anteriores do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , mas que foram removidos em versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="b19f7-110">Describes features that existed in earlier versions of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] but that have been removed in later versions.</span></span>|  
|[<span data-ttu-id="b19f7-111">Recursos preteridos do SQL Server Reporting Services no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b19f7-111">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>](deprecated-features-in-sql-server-reporting-services-ssrs.md)|<span data-ttu-id="b19f7-112">Descreve recursos que existem nesta versão do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para fins de compatibilidade com versões anteriores, mas que serão removidos em uma versão futura do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b19f7-112">Describes features that exist this release of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] for backward compatibility, but which will be removed in a future version of SQL Server.</span></span>|  
|[<span data-ttu-id="b19f7-113">Alterações recentes no SQL Server Reporting Services no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b19f7-113">Breaking Changes in SQL Server Reporting Services in SQL Server 2014</span></span>](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="b19f7-114">Descreve problemas que podem ocorrer durante a atualização do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b19f7-114">Describes issues that you might encounter when you upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="b19f7-115">Alterações de comportamento do SQL Server Reporting Services no SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b19f7-115">Behavior Changes to SQL Server Reporting Services  in SQL Server 2014</span></span>](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="b19f7-116">Descreve recursos que foram alterados no [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b19f7-116">Describes features that have changed in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b19f7-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b19f7-117">See Also</span></span>  
 <span data-ttu-id="b19f7-118">[Compatibilidade com versões anteriores](../../2014/getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="b19f7-118">[Backward Compatibility](../../2014/getting-started/backward-compatibility.md) </span></span>  
 [<span data-ttu-id="b19f7-119">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="b19f7-119">Analysis Services Backward Compatibility</span></span>](../../2014/analysis-services/analysis-services-backward-compatibility.md)  
  
  
