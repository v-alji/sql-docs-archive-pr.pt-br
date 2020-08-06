---
title: Implementando uma extensão de segurança | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
- forms-based authentication [Reporting Services]
- custom authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: d2327e7c-0d48-49e3-bcd9-3bba4e67a68b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e5cf1fa6ce0e0a02a52e6a27f693c152d1f97152
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574515"
---
# <a name="implementing-a-security-extension"></a><span data-ttu-id="69e0d-102">Implementando uma extensão de segurança</span><span class="sxs-lookup"><span data-stu-id="69e0d-102">Implementing a Security Extension</span></span>
  <span data-ttu-id="69e0d-103">A Autenticação do Windows do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] é o principal sistema para proteger os relatórios no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69e0d-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Authentication is the primary system for securing reports in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="69e0d-104">Em determinados casos, entretanto, você pode precisar estender o sistema de segurança do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] para acomodar a segurança personalizada em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="69e0d-104">In certain cases, however, you may need to extend the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security system to accommodate custom security in your enterprise.</span></span> <span data-ttu-id="69e0d-105">Você pode fazer isso usando a plataforma de desenvolvimento fornecida pelo [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] API.</span><span class="sxs-lookup"><span data-stu-id="69e0d-105">You can do this using the development platform provided by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="69e0d-106">Esta seção apresentará uma visão geral de extensões de segurança no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69e0d-106">This section will present an overview of security extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="69e0d-107">Para obter detalhes completos sobre como implementar, implantar e remover uma extensão de segurança do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], consulte [Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="69e0d-107">For complete details about implementing, deploying, and removing a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension, please see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69e0d-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="69e0d-108">In This Section</span></span>  
 [<span data-ttu-id="69e0d-109">Visão geral das extensões de segurança</span><span class="sxs-lookup"><span data-stu-id="69e0d-109">Security Extensions Overview</span></span>](security-extensions-overview.md)  
 <span data-ttu-id="69e0d-110">Fornece uma visão geral das extensões de segurança do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="69e0d-110">Provides an overview of Reporting Services Security Extensions.</span></span>  
  
 [<span data-ttu-id="69e0d-111">Autenticação no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="69e0d-111">Authentication in Reporting Services</span></span>](authentication-in-reporting-services.md)  
 <span data-ttu-id="69e0d-112">Discute a autenticação no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69e0d-112">Discusses authentication in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="69e0d-113">Autorização no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="69e0d-113">Authorization in Reporting Services</span></span>](authorization-in-reporting-services.md)  
 <span data-ttu-id="69e0d-114">Cobre a autorização no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69e0d-114">Covers authorization in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e0d-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="69e0d-115">See Also</span></span>  
 <xref:Microsoft.ReportingServices.Interfaces>   
 <span data-ttu-id="69e0d-116">[Extensões do Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="69e0d-116">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="69e0d-117">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="69e0d-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
