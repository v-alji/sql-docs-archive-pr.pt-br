---
title: Filtros ISAPI detectados no site do servidor de relatório (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- ISAPI filters
- report servers [Reporting Services], upgrade issues
ms.assetid: dd30560d-9e16-47c7-ba68-a9743a657e4e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: bff1834ddf1b8f90787a47a8fd58a240d2b715d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685004"
---
# <a name="isapi-filters-detected-on-the-report-server-site-upgrade-advisor"></a><span data-ttu-id="eaf2d-102">Filtros ISAPI detectados no site do servidor de relatório (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="eaf2d-102">ISAPI filters detected on the report server site (Upgrade Advisor)</span></span>
  <span data-ttu-id="eaf2d-103">O Supervisor de Atualização detectou um ou mais filtros ISAPI no site que hospeda o servidor de relatório e os diretórios virtuais do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="eaf2d-103">Upgrade Advisor detected one or more ISAPI filters on the Web site that hosts the report server and Report Manager virtual directories.</span></span> <span data-ttu-id="eaf2d-104">Não há suporte para filtros ISAPI no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eaf2d-104">ISAPI filters are not supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
||  
|-|  
|<span data-ttu-id="eaf2d-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Forma.</span><span class="sxs-lookup"><span data-stu-id="eaf2d-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native .</span></span>|  
  
## <a name="component"></a><span data-ttu-id="eaf2d-106">Componente</span><span class="sxs-lookup"><span data-stu-id="eaf2d-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="eaf2d-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="eaf2d-107">Description</span></span>  
 <span data-ttu-id="eaf2d-108">Antes da atualização, verifique se os filtros ISAPI do site são usados por aplicativos do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eaf2d-108">Before upgrading, verify whether the ISAPI filters on the Web site are used by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] applications.</span></span> <span data-ttu-id="eaf2d-109">Se você não precisar do filtro ISAPI, poderá atualizar o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="eaf2d-109">If you do not require the ISAPI filter, you can upgrade the report server.</span></span> <span data-ttu-id="eaf2d-110">A Instalação criará URLs padrão sem suporte para o filtro ISAPI executado no IIS.</span><span class="sxs-lookup"><span data-stu-id="eaf2d-110">Setup will create the default URLs, without support for the ISAPI filter that runs in IIS.</span></span> <span data-ttu-id="eaf2d-111">Se precisar do filtro ISAPI, não faça a atualização até encontrar uma maneira alternativa de hospedar o filtro ISAPI (por exemplo, usando o ISA Server ou continuando a hospedar o filtro ISAPI no IIS).</span><span class="sxs-lookup"><span data-stu-id="eaf2d-111">If you require the ISAPI filter, do not upgrade until you find an alternative way of hosting the ISAPI filter (for example, using ISA Server or continuing to host the ISAPI filter in IIS).</span></span> <span data-ttu-id="eaf2d-112">O servidor de relatório suporta o ASP.NET HTTPModules como substituto dos filtros ISAPI em certos cenários.</span><span class="sxs-lookup"><span data-stu-id="eaf2d-112">The report server supports ASP.NET HTTPModules as a replacement for ISAPI filters in certain scenarios.</span></span> <span data-ttu-id="eaf2d-113">Para obter mais informações, consulte a documentação do ASP.NET sobre MSDN.</span><span class="sxs-lookup"><span data-stu-id="eaf2d-113">For more information, see the ASP.NET documentation on MSDN.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="eaf2d-114">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="eaf2d-114">Corrective Action</span></span>  
 <span data-ttu-id="eaf2d-115">Avalie e use uma solução separada para hospedar filtros ISAPI necessários para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="eaf2d-115">Evaluate and use a separate solution for hosting ISAPI filters required by your deployment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf2d-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eaf2d-116">See Also</span></span>  
 [<span data-ttu-id="eaf2d-117">Problemas de atualização do Reporting Services &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="eaf2d-117">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
