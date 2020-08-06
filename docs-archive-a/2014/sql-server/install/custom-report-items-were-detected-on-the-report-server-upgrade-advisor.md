---
title: Foram detectados itens de relatório personalizados no servidor de relatório (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- custom report items, upgrading
ms.assetid: aee32006-65b2-4dfe-9570-d85a249d17b2
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: feacf6aa6f233f85a67b43e7b72d3a50913991bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571773"
---
# <a name="custom-report-items-were-detected-on-the-report-server-upgrade-advisor"></a><span data-ttu-id="40f0f-102">Itens de relatório personalizado detectados no servidor de relatório (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="40f0f-102">Custom report items were detected on the report server (Upgrade Advisor)</span></span>
  <span data-ttu-id="40f0f-103">Os itens de relatório personalizados que foram criados para versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] não são compatíveis com o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="40f0f-103">Custom report items that were created for previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] are not compatible with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="40f0f-104">A atualização pode continuar, mas os relatórios que usam o item de relatório personalizado não serão executados como esperado.</span><span class="sxs-lookup"><span data-stu-id="40f0f-104">Upgrade can continue, but reports that use the custom report item will not run as expected.</span></span> <span data-ttu-id="40f0f-105">O Supervisor de Atualização detectou itens de relatório personalizados.</span><span class="sxs-lookup"><span data-stu-id="40f0f-105">Upgrade Advisor detected custom report items.</span></span> <span data-ttu-id="40f0f-106">A atualização pode prosseguir, mas você deverá mover os arquivos de item de relatório personalizado manualmente para a nova pasta de instalação ao final da atualização.</span><span class="sxs-lookup"><span data-stu-id="40f0f-106">Upgrade can continue, but you must manually move the custom report item files to the new installation folder after upgrade completes.</span></span>  
  
||  
|-|  
|<span data-ttu-id="40f0f-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="40f0f-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="40f0f-108">Componente</span><span class="sxs-lookup"><span data-stu-id="40f0f-108">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="40f0f-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="40f0f-109">Description</span></span>  
 <span data-ttu-id="40f0f-110">O Supervisor de Atualização detectou configurações de extensão personalizadas do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em arquivos de configuração, indicando que sua instalação inclui um ou mais assemblies personalizados para relatórios.</span><span class="sxs-lookup"><span data-stu-id="40f0f-110">Upgrade Advisor detected custom [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] extension settings in the configuration files, indicating that your installation includes one or more custom assemblies for reports.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="40f0f-111">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="40f0f-111">Corrective Action</span></span>  
 <span data-ttu-id="40f0f-112">Concluída a atualização, mova os arquivos de item de relatório personalizado manualmente para a nova pasta de instalação.</span><span class="sxs-lookup"><span data-stu-id="40f0f-112">After upgrade completes, manually move the custom report item files to the new installation folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f0f-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="40f0f-113">See Also</span></span>  
 [<span data-ttu-id="40f0f-114">Problemas de atualização do Reporting Services &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="40f0f-114">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
